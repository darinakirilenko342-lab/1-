
import flet as ft

def main(page: ft.Page):

    page.title = "Messenger"
    page.theme_mode = ft.ThemeMode.DARK
    page.window.width = 1200
    page.window.height = 700
    page.padding = 0
    page.spacing = 0
    page.bgcolor = "#1e1e2f"

    top_panel = ft.Row(
        alignment=ft.MainAxisAlignment.SPACE_BETWEEN,
        controls=[
            ft.Row(
                controls=[
                    ft.Text(
                        "Emma",
                        size=24,
                        weight=ft.FontWeight.BOLD,
                        color="white"
                    ),
                    ft.Container(
                        width=10,
                        height=10,
                        border_radius=5,
                        bgcolor="green"
                    )
                ]
            ),
            ft.Row(
                controls=[
                    ft.IconButton(
                        icon=ft.Icons.CALL,
                        icon_color="white"
                    ),
                    ft.IconButton(
                        icon=ft.Icons.VIDEO_CALL,
                        icon_color="white"
                    ),
                    ft.IconButton(
                        icon=ft.Icons.INFO_OUTLINE,
                        icon_color="white"
                    ),
                ]
            )
        ]
    )

    sidebar = ft.Container(
        width=320,
        bgcolor="#2b2d42",
        padding=15,
        content=ft.Column(
            controls=[
                ft.Text(
                    "Chats",
                    size=28,
                    weight=ft.FontWeight.BOLD,
                    color="white"
                ),

                ft.Divider(color="#555"),

                ft.TextField(
                    hint_text="Search...",
                    border_radius=20,
                    filled=True,
                    bgcolor="#3a3d5c",
                    border_color="transparent",
                    color="white"
                ),

                ft.Container(height=10),

                ft.ListTile(
                    leading=ft.CircleAvatar(
                        content=ft.Text("E"),
                        bgcolor="blue"
                    ),
                    title=ft.Text("Emma", color="white"),
                    subtitle=ft.Text(
                        "Hey 👋",
                        color="gray"
                    ),
                ),

                ft.ListTile(
                    leading=ft.CircleAvatar(
                        content=ft.Text("L"),
                        bgcolor="purple"
                    ),
                    title=ft.Text("Lucas", color="white"),
                    subtitle=ft.Text(
                        "See you soon",
                        color="gray"
                    ),
                ),

                ft.ListTile(
                    leading=ft.CircleAvatar(
                        content=ft.Text("M"),
                        bgcolor="orange"
                    ),
                    title=ft.Text("Mia", color="white"),
                    subtitle=ft.Text(
                        "Thank you!",
                        color="gray"
                    ),
                ),

                ft.ListTile(
                    leading=ft.CircleAvatar(
                        content=ft.Text("N"),
                        bgcolor="green"
                    ),
                    title=ft.Text("Noah", color="white"),
                    subtitle=ft.Text(
                        "Let's play",
                        color="gray"
                    ),
                ),

                ft.ListTile(
                    leading=ft.CircleAvatar(
                        content=ft.Text("S"),
                        bgcolor="red"
                    ),
                    title=ft.Text("Sophia", color="white"),
                    subtitle=ft.Text(
                        "Good night 🌙",
                        color="gray"
                    ),
                ),

                ft.ListTile(
                    leading=ft.CircleAvatar(
                        content=ft.Text("J"),
                        bgcolor="teal"
                    ),
                    title=ft.Text("James", color="white"),
                    subtitle=ft.Text(
                        "Send the photo",
                        color="gray"
                    ),
                ),
            ],
            spacing=5,
        )
    )

    chat_area = ft.Container(
        expand=True,
        bgcolor="#1f2235",
        padding=20,
        content=ft.Column(
            controls=[

                top_panel,

                ft.Divider(color="#555"),

                ft.Container(
                    expand=True,
                    content=ft.Column(
                        spacing=15,
                        controls=[

                            ft.Container(
                                bgcolor="#4c6ef5",
                                padding=10,
                                border_radius=25,
                                content=ft.Column(
                                    tight=True,
                                    controls=[
                                        ft.Text(
                                            "Hello!",
                                            color="white"
                                        ),
                                        ft.Text(
                                            "14:15",
                                            size=10,
                                            color="lightgrey"
                                        )
                                    ]
                                )
                            ),

                            ft.Container(
                                bgcolor="#353a50",
                                padding=10,
                                border_radius=25,
                                content=ft.Column(
                                    tight=True,
                                    controls=[
                                        ft.Text(
                                            "Hi, how are you?",
                                            color="white"
                                        ),
                                        ft.Text(
                                            "14:16",
                                            size=10,
                                            color="lightgrey"
                                        )
                                    ]
                                )
                            ),
                        ]
                    )
                ),

                ft.Row(
                    controls=[
                        ft.TextField(
                            hint_text="Write a message...",
                            expand=True,
                            border_radius=25,
                            filled=True,
                            bgcolor="#2b2d42",
                            border_color="transparent",
                            color="white"
                        ),

                        ft.IconButton(
                            icon=ft.Icons.SEND,
                            icon_color="white",
                            bgcolor="#4c6ef5"
                        )
                    ]
                )
            ],
            expand=True
        )
    )

    page.add(
        ft.Row(
            controls=[
                sidebar,
                chat_area
            ],
            expand=True,
            spacing=0
        )
    )

ft.app(target=main)

