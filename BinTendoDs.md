---
tags:
  - code
  - U19
date: 2023-09-02 14:26
File Modified: 2023-09-17 15:29
File Folder: C#
Type: Code
---

---


```C#
using System;
using System.Windows.Forms;

namespace YourNamespace
{
    public partial class YourForm : Form
    {
        public YourForm()
        {
            InitializeComponent();
        }

        private void buttonConvert_Click(object sender, EventArgs e)
        {
            // Read the user input from the input TextBox
            string userInput = textBoxInput.Text;

            // Check which conversion type is selected (from radio buttons)
            if (radioButtonDenary.Checked)
            {
                // Handle Denary conversion
                if (int.TryParse(userInput, out int denaryValue))
                {
                    textBoxOutput.Text = denaryValue.ToString(); // Convert to Denary
                }
                else
                {
                    MessageBox.Show("Invalid input. Please enter a valid integer.");
                }
            }
            else if (radioButtonBinary.Checked)
            {
                // Handle Binary conversion
                if (IsBinary(userInput))
                {
                    int denaryBinaryValue = Convert.ToInt32(userInput, 2);
                    textBoxOutput.Text = denaryBinaryValue.ToString(); // Convert Binary to Denary
                }
                else
                {
                    MessageBox.Show("Invalid binary input. Please enter a valid binary number.");
                }
            }
            else if (radioButtonHexadecimal.Checked)
            {
                // Handle Hexadecimal conversion
                if (IsHexadecimal(userInput))
                {
                    int denaryHexadecimalValue = Convert.ToInt32(userInput, 16);
                    textBoxOutput.Text = denaryHexadecimalValue.ToString(); // Convert Hexadecimal to Denary
                }
                else
                {
                    MessageBox.Show("Invalid hexadecimal input. Please enter a valid hexadecimal number.");
                }
            }
            else if (radioButtonASCII.Checked)
            {
                // Handle ASCII conversion
                if (userInput.Length == 1)
                {
                    int denaryASCIIValue = (int)userInput[0];
                    textBoxOutput.Text = denaryASCIIValue.ToString(); // Convert ASCII to Denary
                }
                else
                {
                    MessageBox.Show("Invalid input. Please enter a single character.");
                }
            }
            else if (radioButtonOctal.Checked)
            {
                // Handle Octal conversion
                if (IsOctal(userInput))
                {
                    int denaryOctalValue = Convert.ToInt32(userInput, 8);
                    textBoxOutput.Text = denaryOctalValue.ToString(); // Convert Octal to Denary
                }
                else
                {
                    MessageBox.Show("Invalid octal input. Please enter a valid octal number.");
                }
            }
            else
            {
                MessageBox.Show("Please select a conversion type.");
            }
        }

        // Helper function to check if a string is a valid binary number
        private bool IsBinary(string input)
        {
            foreach (char c in input)
            {
                if (c != '0' && c != '1')
                {
                    return false;
                }
            }
            return true;
        }

        // Helper function to check if a string is a valid hexadecimal number
        private bool IsHexadecimal(string input)
        {
            foreach (char c in input)
            {
                if (!char.IsDigit(c) && (c < 'A' || c > 'F') && (c < 'a' || c > 'f'))
                {
                    return false;
                }
            }
            return true;
        }

        // Helper function to check if a string is a valid octal number
        private bool IsOctal(string input)
        {
            foreach (char c in input)
            {
                if (c < '0' || c > '7')
                {
                    return false;
                }
            }
            return true;
        }

        private void radioButtonDenary_CheckedChanged(object sender, EventArgs e)
        {
            // Handle Denary radio button change, if needed
        }

        private void comboBoxOutputFormat_SelectedIndexChanged(object sender, EventArgs e)
        {
            // Convert the result to the selected output format (from comboBox)
            string selectedOutputFormat = comboBoxOutputFormat.SelectedItem.ToString();
            ConvertToOutputFormat(selectedOutputFormat);
        }

        // Helper function to convert the result to the selected output format
        private void ConvertToOutputFormat(string outputFormat)
        {
            // Get the Denary value from textBoxOutput
            if (int.TryParse(textBoxOutput.Text, out int denaryValue))
            {
                // Convert to the selected output format and display it
                switch (outputFormat)
                {
                    case "Denary":
                        textBoxOutput.Text = denaryValue.ToString(); // Already in Denary
                        break;
                    case "Binary":
                        textBoxOutput.Text = Convert.ToString(denaryValue, 2); // Convert to Binary
                        break;
                    case "Hexadecimal":
                        textBoxOutput.Text = Convert.ToString(denaryValue, 16); // Convert to Hexadecimal
                        break;
                    case "ASCII":
                        textBoxOutput.Text = ((char)denaryValue).ToString(); // Convert to ASCII
                        break;
                    case "Octal":
                        textBoxOutput.Text = Convert.ToString(denaryValue, 8); // Convert to Octal
                        break;
                    default:
                        // Handle invalid output format
                        MessageBox.Show("Invalid output format selected.");
                        break;
                }
            }
        }
    }
}


```
# DropDownEvent

```C#

    // Convert the result to the selected output format (from comboBox)
    string selectedOutputFormat = comboBoxOutputFormat.SelectedItem.ToString();
    ConvertToOutputFormat(selectedOutputFormat);
}

// Helper function to convert the result to the selected output format
private void ConvertToOutputFormat(string outputFormat)
{
    // Get the Denary value from textBoxOutput
    if (int.TryParse(textBoxOutput.Text, out int denaryValue))
    {
        // Convert to the selected output format and display it
        switch (outputFormat)
        {
            case "Denary":
                textBoxOutput.Text = denaryValue.ToString(); // Already in Denary
                break;
            case "Binary":
                textBoxOutput.Text = Convert.ToString(denaryValue, 2); // Convert to Binary
                break;
            case "Hexadecimal":
                textBoxOutput.Text = Convert.ToString(denaryValue, 16); // Convert to Hexadecimal
                break;
            case "ASCII":
                textBoxOutput.Text = ((char)denaryValue).ToString(); // Convert to ASCII
                break;
            case "Octal":
                textBoxOutput.Text = Convert.ToString(denaryValue, 8); // Convert to Octal
                break;
            default:
                // Handle invalid output format
                MessageBox.Show("Invalid output format selected.");
                break;
        }
    }


```


