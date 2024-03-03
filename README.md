# Data-Products
This is the user-interface definition of a Shiny web application. You can
# run the application by clicking 'Run App' above.
#
# Find out more about building applications with Shiny here:
#
#    http://shiny.rstudio.com/
#

library(shiny)

# Define UI for application
ui <-fluidPage(
    
    # Input number
    
    titlePanel("My First App"),
    
    # Sidebar with a slider input for number
    sidebarLayout(
        sidebarPanel(
            sliderInput(inputId ="num",
                        label = "No input required",
                        min = 0,
                        max = 110,
                        value = 20),
        ),
        
        # Show a plot of the plot
        plotOutput("hist")
    )
)
#
# This is the server logic of a Shiny web application. You can run the
# application by clicking 'Run App' above.
#
# Find out more about building applications with Shiny here:
#
#    http://shiny.rstudio.com/
#

library(shiny)

# Define server logic reguired
server <- function(input, output) {
    # Rcode
    
    output$hist <- renderPlot({
        hist(rnorm(input$num))
        
    })
    
}
