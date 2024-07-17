from ._anvil_designer import Form1Template
from anvil import *
import anvil.server
import anvil.tables as tables
import anvil.tables.query as q
from anvil.tables import app_tables


class Form1(Form1Template):
  def __init__(self, **properties):
    # Set Form properties and Data Bindings.
    self.init_components(**properties)

    # Any code you write here will run before the form opens.

  def button_1_click(self, **event_args):
    """This method is called when the button is clicked"""
    name  = self.text_box_1.text
    age = int(self.text_box_2.text)
    guardian = self.text_box_3.text
    batch = bool(self.radio_button_1.selected)
    batch1= bool(self.radio_button_2.selected)
  
    
    mobile = int(self.text_box_4.text)
    anvil.server.call('submit',name=name,age=age,guardian=guardian,batch=batch,batch1=batch1,mobile=mobile)
    Notification("Your Response has been Recorded").show()  
    
