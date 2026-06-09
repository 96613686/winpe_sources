# wil::details::HrToNtStatus(long)

- ea: `0x140007a8c`
- end: `0x140007c48`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140003aec`
- `0x140003bc0`
- `0x140003c10`
- `0x140003c74`
- `0x140004090`
- `0x1400067e8`
- `0x14000f984`
- `0x14000fa90`

## callees

- `0x140007a8c`

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
0x140007a8c  mov     eax, 800700EAh
0x140007a91  cmp     ecx, eax
0x140007a93  jg      loc_140007B68
0x140007a99  jz      loc_140007B5E
0x140007a9f  mov     eax, 80070057h
0x140007aa4  cmp     ecx, eax
0x140007aa6  jg      short loc_140007B12
0x140007aa8  jz      short loc_140007B08
0x140007aaa  cmp     ecx, 80004005h
0x140007ab0  jz      short loc_140007AFE
0x140007ab2  cmp     ecx, 80070001h
0x140007ab8  jz      short loc_140007AF4
0x140007aba  cmp     ecx, 80070002h
0x140007ac0  jz      short loc_140007AEA
0x140007ac2  cmp     ecx, 80070003h
0x140007ac8  jz      short loc_140007AE0
0x140007aca  cmp     ecx, 8007000Eh
0x140007ad0  jnz     loc_140007BED
0x140007ad6  mov     ecx, 0C0000017h
0x140007adb  jmp     loc_140007C45
0x140007ae0  mov     ecx, 0C000003Ah
0x140007ae5  jmp     loc_140007C45
0x140007aea  mov     ecx, 0C0000034h
0x140007aef  jmp     loc_140007C45
0x140007af4  mov     ecx, 0C0000002h
0x140007af9  jmp     loc_140007C45
0x140007afe  mov     ecx, 0C0000001h
0x140007b03  jmp     loc_140007C45
0x140007b08  mov     ecx, 0C000000Dh
0x140007b0d  jmp     loc_140007C45
0x140007b12  cmp     ecx, 80070070h
0x140007b18  jz      short loc_140007B54
0x140007b1a  cmp     ecx, 8007007Ah
0x140007b20  jz      short loc_140007B4A
0x140007b22  cmp     ecx, 8007007Bh
0x140007b28  jz      short loc_140007B40
0x140007b2a  cmp     ecx, 8007007Eh
0x140007b30  jnz     loc_140007BED
0x140007b36  mov     ecx, 0C0000135h
0x140007b3b  jmp     loc_140007C45
0x140007b40  mov     ecx, 0C0000033h
0x140007b45  jmp     loc_140007C45
0x140007b4a  mov     ecx, 0C0000023h
0x140007b4f  jmp     loc_140007C45
0x140007b54  mov     ecx, 0C000007Fh
0x140007b59  jmp     loc_140007C45
0x140007b5e  mov     ecx, 80000005h
0x140007b63  jmp     loc_140007C45
0x140007b68  mov     eax, 8007047Eh
0x140007b6d  cmp     ecx, eax
0x140007b6f  jg      short loc_140007BD1
0x140007b71  jz      short loc_140007BCA
0x140007b73  cmp     ecx, 80070216h
0x140007b79  jz      short loc_140007BC3
0x140007b7b  cmp     ecx, 8007023Eh
0x140007b81  jz      short loc_140007BB9
0x140007b83  cmp     ecx, 80070246h
0x140007b89  jz      short loc_140007BAF
0x140007b8b  cmp     ecx, 80070247h
0x140007b91  jz      short loc_140007BA5
0x140007b93  cmp     ecx, 80070272h
0x140007b99  jnz     short loc_140007BED
0x140007b9b  mov     ecx, 0C0000273h
0x140007ba0  jmp     loc_140007C45
0x140007ba5  mov     ecx, 0C0000163h
0x140007baa  jmp     loc_140007C45
0x140007baf  mov     ecx, 0C0000161h
0x140007bb4  jmp     loc_140007C45
0x140007bb9  mov     ecx, 0C0000025h
0x140007bbe  jmp     loc_140007C45
0x140007bc3  mov     ecx, 0C0000095h
0x140007bc8  jmp     short loc_140007C45
0x140007bca  mov     ecx, 0C0000059h
0x140007bcf  jmp     short loc_140007C45
0x140007bd1  cmp     ecx, 8007050Ch
0x140007bd7  jz      short loc_140007C40
0x140007bd9  cmp     ecx, 8007054Fh
0x140007bdf  jz      short loc_140007C39
0x140007be1  cmp     ecx, 800705B9h
0x140007be7  jz      short loc_140007C32
0x140007be9  test    ecx, ecx
0x140007beb  jz      short loc_140007C2E
0x140007bed  bt      ecx, 1Ch
0x140007bf1  jnb     short loc_140007BF9
0x140007bf3  btr     ecx, 1Ch
0x140007bf7  jmp     short loc_140007C45
0x140007bf9  mov     eax, ecx
0x140007bfb  and     eax, 1FFF0000h
0x140007c00  cmp     eax, 70000h
0x140007c05  jnz     short loc_140007C18
0x140007c07  movzx   ecx, cx
0x140007c0a  mov     eax, ecx
0x140007c0c  or      eax, 0C0070000h
0x140007c11  test    ecx, ecx
0x140007c13  cmovnz  ecx, eax
0x140007c16  jmp     short loc_140007C45
0x140007c18  cmp     eax, 90000h
0x140007c1d  jnz     short loc_140007C39
0x140007c1f  test    ecx, ecx
0x140007c21  jle     short loc_140007C45
0x140007c23  movzx   ecx, cx
0x140007c26  or      ecx, 0C0090000h
0x140007c2c  jmp     short loc_140007C45
0x140007c2e  xor     ecx, ecx
0x140007c30  jmp     short loc_140007C45
0x140007c32  mov     ecx, 0C000A083h
0x140007c37  jmp     short loc_140007C45
0x140007c39  mov     ecx, 0C00000E5h
0x140007c3e  jmp     short loc_140007C45
0x140007c40  mov     ecx, 0C000042Bh
0x140007c45  mov     eax, ecx
0x140007c47  retn
```
