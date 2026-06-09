# wil::details::HrToNtStatus(long)

- ea: `0x18000ba88`
- end: `0x18000bc44`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180008740`
- `0x1800087ec`
- `0x18000883c`
- `0x1800088fc`
- `0x18000adec`
- `0x18000bdfc`

## callees

- `0x18000ba88`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  if ( (int)this > -2147024662 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          LODWORD(this) = -1073740757;
          return (unsigned int)this;
        case 0x8007054F:
          goto LABEL_53;
        case 0x800705B9:
          LODWORD(this) = -1073700733;
          return (unsigned int)this;
        case 0:
          LODWORD(this) = 0;
          return (unsigned int)this;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x8007047E:
          LODWORD(this) = -1073741735;
          return (unsigned int)this;
        case 0x80070216:
          LODWORD(this) = -1073741675;
          return (unsigned int)this;
        case 0x8007023E:
          LODWORD(this) = -1073741787;
          return (unsigned int)this;
        case 0x80070246:
          LODWORD(this) = -1073741471;
          return (unsigned int)this;
        case 0x80070247:
          LODWORD(this) = -1073741469;
          return (unsigned int)this;
        case 0x80070272:
          LODWORD(this) = -1073741197;
          return (unsigned int)this;
      }
    }
  }
  else
  {
    if ( (_DWORD)this == -2147024662 )
    {
      LODWORD(this) = -2147483643;
      return (unsigned int)this;
    }
    if ( (int)this > -2147024809 )
    {
      switch ( (_DWORD)this )
      {
        case 0x80070070:
          LODWORD(this) = -1073741697;
          return (unsigned int)this;
        case 0x8007007A:
          LODWORD(this) = -1073741789;
          return (unsigned int)this;
        case 0x8007007B:
          LODWORD(this) = -1073741773;
          return (unsigned int)this;
        case 0x8007007E:
          LODWORD(this) = -1073741515;
          return (unsigned int)this;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x80070057:
          LODWORD(this) = -1073741811;
          return (unsigned int)this;
        case 0x80004005:
          LODWORD(this) = -1073741823;
          return (unsigned int)this;
        case 0x80070001:
          LODWORD(this) = -1073741822;
          return (unsigned int)this;
        case 0x80070002:
          LODWORD(this) = -1073741772;
          return (unsigned int)this;
        case 0x80070003:
          LODWORD(this) = -1073741766;
          return (unsigned int)this;
        case 0x8007000E:
          LODWORD(this) = -1073741801;
          return (unsigned int)this;
      }
    }
  }
  if ( ((unsigned int)this & 0x10000000) != 0 )
  {
    LODWORD(this) = (unsigned int)this & 0xEFFFFFFF;
    return (unsigned int)this;
  }
  if ( ((unsigned int)this & 0x1FFF0000) == 0x70000 )
  {
    LODWORD(this) = (unsigned __int16)this;
    if ( (_WORD)this )
      LODWORD(this) = (unsigned __int16)this | 0xC0070000;
    return (unsigned int)this;
  }
  if ( ((unsigned int)this & 0x1FFF0000) != 0x90000 )
  {
LABEL_53:
    LODWORD(this) = -1073741595;
    return (unsigned int)this;
  }
  if ( (int)this > 0 )
    LODWORD(this) = (unsigned __int16)this | 0xC0090000;
  return (unsigned int)this;
}

```

## disassembly

```asm
0x18000ba88  mov     eax, 800700EAh
0x18000ba8d  cmp     ecx, eax
0x18000ba8f  jg      loc_18000BB64
0x18000ba95  jz      loc_18000BB5A
0x18000ba9b  mov     eax, 80070057h
0x18000baa0  cmp     ecx, eax
0x18000baa2  jg      short loc_18000BB0E
0x18000baa4  jz      short loc_18000BB04
0x18000baa6  cmp     ecx, 80004005h
0x18000baac  jz      short loc_18000BAFA
0x18000baae  cmp     ecx, 80070001h
0x18000bab4  jz      short loc_18000BAF0
0x18000bab6  cmp     ecx, 80070002h
0x18000babc  jz      short loc_18000BAE6
0x18000babe  cmp     ecx, 80070003h
0x18000bac4  jz      short loc_18000BADC
0x18000bac6  cmp     ecx, 8007000Eh
0x18000bacc  jnz     loc_18000BBE9
0x18000bad2  mov     ecx, 0C0000017h
0x18000bad7  jmp     loc_18000BC41
0x18000badc  mov     ecx, 0C000003Ah
0x18000bae1  jmp     loc_18000BC41
0x18000bae6  mov     ecx, 0C0000034h
0x18000baeb  jmp     loc_18000BC41
0x18000baf0  mov     ecx, 0C0000002h
0x18000baf5  jmp     loc_18000BC41
0x18000bafa  mov     ecx, 0C0000001h
0x18000baff  jmp     loc_18000BC41
0x18000bb04  mov     ecx, 0C000000Dh
0x18000bb09  jmp     loc_18000BC41
0x18000bb0e  cmp     ecx, 80070070h
0x18000bb14  jz      short loc_18000BB50
0x18000bb16  cmp     ecx, 8007007Ah
0x18000bb1c  jz      short loc_18000BB46
0x18000bb1e  cmp     ecx, 8007007Bh
0x18000bb24  jz      short loc_18000BB3C
0x18000bb26  cmp     ecx, 8007007Eh
0x18000bb2c  jnz     loc_18000BBE9
0x18000bb32  mov     ecx, 0C0000135h
0x18000bb37  jmp     loc_18000BC41
0x18000bb3c  mov     ecx, 0C0000033h
0x18000bb41  jmp     loc_18000BC41
0x18000bb46  mov     ecx, 0C0000023h
0x18000bb4b  jmp     loc_18000BC41
0x18000bb50  mov     ecx, 0C000007Fh
0x18000bb55  jmp     loc_18000BC41
0x18000bb5a  mov     ecx, 80000005h
0x18000bb5f  jmp     loc_18000BC41
0x18000bb64  mov     eax, 8007047Eh
0x18000bb69  cmp     ecx, eax
0x18000bb6b  jg      short loc_18000BBCD
0x18000bb6d  jz      short loc_18000BBC6
0x18000bb6f  cmp     ecx, 80070216h
0x18000bb75  jz      short loc_18000BBBF
0x18000bb77  cmp     ecx, 8007023Eh
0x18000bb7d  jz      short loc_18000BBB5
0x18000bb7f  cmp     ecx, 80070246h
0x18000bb85  jz      short loc_18000BBAB
0x18000bb87  cmp     ecx, 80070247h
0x18000bb8d  jz      short loc_18000BBA1
0x18000bb8f  cmp     ecx, 80070272h
0x18000bb95  jnz     short loc_18000BBE9
0x18000bb97  mov     ecx, 0C0000273h
0x18000bb9c  jmp     loc_18000BC41
0x18000bba1  mov     ecx, 0C0000163h
0x18000bba6  jmp     loc_18000BC41
0x18000bbab  mov     ecx, 0C0000161h
0x18000bbb0  jmp     loc_18000BC41
0x18000bbb5  mov     ecx, 0C0000025h
0x18000bbba  jmp     loc_18000BC41
0x18000bbbf  mov     ecx, 0C0000095h
0x18000bbc4  jmp     short loc_18000BC41
0x18000bbc6  mov     ecx, 0C0000059h
0x18000bbcb  jmp     short loc_18000BC41
0x18000bbcd  cmp     ecx, 8007050Ch
0x18000bbd3  jz      short loc_18000BC3C
0x18000bbd5  cmp     ecx, 8007054Fh
0x18000bbdb  jz      short loc_18000BC35
0x18000bbdd  cmp     ecx, 800705B9h
0x18000bbe3  jz      short loc_18000BC2E
0x18000bbe5  test    ecx, ecx
0x18000bbe7  jz      short loc_18000BC2A
0x18000bbe9  bt      ecx, 1Ch
0x18000bbed  jnb     short loc_18000BBF5
0x18000bbef  btr     ecx, 1Ch
0x18000bbf3  jmp     short loc_18000BC41
0x18000bbf5  mov     eax, ecx
0x18000bbf7  and     eax, 1FFF0000h
0x18000bbfc  cmp     eax, 70000h
0x18000bc01  jnz     short loc_18000BC14
0x18000bc03  movzx   ecx, cx
0x18000bc06  mov     eax, ecx
0x18000bc08  or      eax, 0C0070000h
0x18000bc0d  test    ecx, ecx
0x18000bc0f  cmovnz  ecx, eax
0x18000bc12  jmp     short loc_18000BC41
0x18000bc14  cmp     eax, 90000h
0x18000bc19  jnz     short loc_18000BC35
0x18000bc1b  test    ecx, ecx
0x18000bc1d  jle     short loc_18000BC41
0x18000bc1f  movzx   ecx, cx
0x18000bc22  or      ecx, 0C0090000h
0x18000bc28  jmp     short loc_18000BC41
0x18000bc2a  xor     ecx, ecx
0x18000bc2c  jmp     short loc_18000BC41
0x18000bc2e  mov     ecx, 0C000A083h
0x18000bc33  jmp     short loc_18000BC41
0x18000bc35  mov     ecx, 0C00000E5h
0x18000bc3a  jmp     short loc_18000BC41
0x18000bc3c  mov     ecx, 0C000042Bh
0x18000bc41  mov     eax, ecx
0x18000bc43  retn
```
