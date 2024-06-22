import qrcode
from PIL import Image

def generate_qr_code_with_logo(data, logo_path, output_path):
    # Gerar QR code
    qr = qrcode.QRCode(
        version=1,
        error_correction=qrcode.constants.ERROR_CORRECT_L,
        box_size=10,
        border=1,
    )
    qr.add_data(data)
    qr.make(fit=True)

    qr_code = qr.make_image(fill_color="#02153d", back_color="white")

    # Adicionar logo
    logo = Image.open(logo_path)
    #logo = logo.resize((110,110))  # Ajuste o tamanho da logo conforme necessário
    logo = logo.resize((60,60))

    # Calcular a posição para centralizar a logo no QR code
    pos = ((qr_code.size[0] - logo.size[0]) // 2, (qr_code.size[1] - logo.size[1]) // 2)

    # Colar a logo no QR code
    qr_code.paste(logo, pos)

    # Salvar a imagem resultante
    qr_code.save(output_path)

if __name__ == "__main__":
    # Substitua os valores abaixo com seus dados e caminhos de arquivo desejados
    data_to_encode = "https://t.me/stack_fy_bot"
    logo_path = "logo.png"
    output_image_path = "STACKFbot.png"

    generate_qr_code_with_logo(data_to_encode, logo_path, output_image_path)
