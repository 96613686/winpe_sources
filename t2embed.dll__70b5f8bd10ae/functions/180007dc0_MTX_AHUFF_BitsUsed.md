# MTX_AHUFF_BitsUsed

- ea: `0x180007dc0`
- end: `0x180007fa4`
- name: `MTX_AHUFF_BitsUsed`
- size: `484`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800067cc`
- `0x180006c10`
- `0x180006d30`
- `0x180007210`
- `0x1800075a0`
- `0x180007bf0`

## callees

- `0x180007dc0`
- `0x18001c9ec`

## pseudocode

```c
__int64 __fastcall MTX_AHUFF_BitsUsed(int a1)
{
  if ( a1 < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (a1 & 0xFFFF0000) != 0 )
  {
    if ( (a1 & 0xFF000000) != 0 )
    {
      if ( (a1 & 0xF0000000) != 0 )
      {
        if ( (a1 & 0xC0000000) != 0 )
          return (unsigned int)(((a1 >> 31) & 1) + 31);
        else
          return (unsigned int)(((a1 & 0x20000000) != 0) + 29);
      }
      else if ( (a1 & 0xC000000) != 0 )
      {
        return (unsigned int)(((a1 & 0x8000000) != 0) + 27);
      }
      else
      {
        return (unsigned int)(((a1 & 0x2000000) != 0) + 25);
      }
    }
    if ( (a1 & 0xF00000) != 0 )
    {
      if ( (a1 & 0xC00000) != 0 )
        return (unsigned int)(((a1 & 0x800000) != 0) + 23);
      else
        return (unsigned int)(((a1 & 0x200000) != 0) + 21);
    }
    if ( (a1 & 0xC0000) != 0 )
      return (unsigned int)(((a1 & 0x80000) != 0) + 19);
    else
      return (unsigned int)(((a1 & 0x20000) != 0) + 17);
  }
  else if ( (a1 & 0xFF00) != 0 )
  {
    if ( (a1 & 0xF000) != 0 )
    {
      if ( (a1 & 0xC000) != 0 )
        return (unsigned int)(((a1 & 0x8000) != 0) + 15);
      else
        return (unsigned int)(((a1 & 0x2000) != 0) + 13);
    }
    else if ( (a1 & 0xC00) != 0 )
    {
      return (unsigned int)(((a1 & 0x800) != 0) + 11);
    }
    else
    {
      return (unsigned int)(((a1 & 0x200) != 0) + 9);
    }
  }
  else if ( (a1 & 0xF0) != 0 )
  {
    if ( (a1 & 0xC0) != 0 )
      return (unsigned int)(((a1 & 0x80u) != 0) + 7);
    else
      return (unsigned int)(((a1 & 0x20) != 0) + 5);
  }
  else
  {
    if ( (a1 & 0xC) == 0 )
      return (unsigned int)(((a1 & 2) != 0) + 1);
    return (unsigned int)((a1 & 8) != 0) + 3;
  }
}

```

## disassembly

```asm
0x180007dc0  push    rbx
0x180007dc2  sub     rsp, 20h
0x180007dc6  mov     ebx, ecx
0x180007dc8  test    ecx, ecx
0x180007dca  js      loc_180007F08
0x180007dd0  test    ebx, 0FFFF0000h
0x180007dd6  jnz     loc_180007EBE
0x180007ddc  test    ebx, 0FF00h
0x180007de2  jnz     short loc_180007E03
0x180007de4  test    bl, 0F0h
0x180007de7  jnz     short loc_180007E2A
0x180007de9  test    bl, 0Ch
0x180007dec  jnz     short loc_180007E5B
0x180007dee  test    bl, 2
0x180007df1  mov     ebx, 0
0x180007df6  setnz   bl
0x180007df9  inc     ebx
0x180007dfb  mov     eax, ebx
0x180007dfd  add     rsp, 20h
0x180007e01  pop     rbx
0x180007e02  retn
0x180007e03  test    ebx, 0F000h
0x180007e09  jnz     short loc_180007E71
0x180007e0b  test    ebx, 0C00h
0x180007e11  jnz     short loc_180007E90
0x180007e13  bt      ebx, 9
0x180007e17  mov     ebx, 0
0x180007e1c  setb    bl
0x180007e1f  add     ebx, 9
0x180007e22  mov     eax, ebx
0x180007e24  add     rsp, 20h
0x180007e28  pop     rbx
0x180007e29  retn
0x180007e2a  test    bl, 0C0h
0x180007e2d  jz      short loc_180007E45
0x180007e2f  test    bl, 80h
0x180007e32  mov     ebx, 0
0x180007e37  setnz   bl
0x180007e3a  add     ebx, 7
0x180007e3d  mov     eax, ebx
0x180007e3f  add     rsp, 20h
0x180007e43  pop     rbx
0x180007e44  retn
0x180007e45  test    bl, 20h
0x180007e48  mov     ebx, 0
0x180007e4d  setnz   bl
0x180007e50  add     ebx, 5
0x180007e53  mov     eax, ebx
0x180007e55  add     rsp, 20h
0x180007e59  pop     rbx
0x180007e5a  retn
0x180007e5b  test    bl, 8
0x180007e5e  mov     ebx, 0
0x180007e63  setnz   bl
0x180007e66  add     ebx, 3
0x180007e69  mov     eax, ebx
0x180007e6b  add     rsp, 20h
0x180007e6f  pop     rbx
0x180007e70  retn
0x180007e71  test    ebx, 0C000h
0x180007e77  jnz     short loc_180007EA7
0x180007e79  bt      ebx, 0Dh
0x180007e7d  mov     ebx, 0
0x180007e82  setb    bl
0x180007e85  add     ebx, 0Dh
0x180007e88  mov     eax, ebx
0x180007e8a  add     rsp, 20h
0x180007e8e  pop     rbx
0x180007e8f  retn
0x180007e90  bt      ebx, 0Bh
0x180007e94  mov     ebx, 0
0x180007e99  setb    bl
0x180007e9c  add     ebx, 0Bh
0x180007e9f  mov     eax, ebx
0x180007ea1  add     rsp, 20h
0x180007ea5  pop     rbx
0x180007ea6  retn
0x180007ea7  bt      ebx, 0Fh
0x180007eab  mov     ebx, 0
0x180007eb0  setb    bl
0x180007eb3  add     ebx, 0Fh
0x180007eb6  mov     eax, ebx
0x180007eb8  add     rsp, 20h
0x180007ebc  pop     rbx
0x180007ebd  retn
0x180007ebe  test    ebx, 0FF000000h
0x180007ec4  jnz     short loc_180007F12
0x180007ec6  test    ebx, 0F00000h
0x180007ecc  jnz     loc_180007F74
0x180007ed2  test    ebx, 0C0000h
0x180007ed8  jnz     short loc_180007EF1
0x180007eda  bt      ebx, 11h
0x180007ede  mov     ebx, 0
0x180007ee3  setb    bl
0x180007ee6  add     ebx, 11h
0x180007ee9  mov     eax, ebx
0x180007eeb  add     rsp, 20h
0x180007eef  pop     rbx
0x180007ef0  retn
0x180007ef1  bt      ebx, 13h
0x180007ef5  mov     ebx, 0
0x180007efa  setb    bl
0x180007efd  add     ebx, 13h
0x180007f00  mov     eax, ebx
0x180007f02  add     rsp, 20h
0x180007f06  pop     rbx
0x180007f07  retn
0x180007f08  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007f0d  jmp     loc_180007DD0
0x180007f12  test    ebx, 0F0000000h
0x180007f18  jz      short loc_180007F44
0x180007f1a  test    ebx, 0C0000000h
0x180007f20  jz      short loc_180007F30
0x180007f22  sar     ebx, 1Fh
0x180007f25  and     ebx, 1
0x180007f28  add     ebx, 1Fh
0x180007f2b  jmp     loc_180007DFB
0x180007f30  bt      ebx, 1Dh
0x180007f34  mov     ebx, 0
0x180007f39  setb    bl
0x180007f3c  add     ebx, 1Dh
0x180007f3f  jmp     loc_180007DFB
0x180007f44  test    ebx, 0C000000h
0x180007f4a  jz      short loc_180007F60
0x180007f4c  bt      ebx, 1Bh
0x180007f50  mov     ebx, 0
0x180007f55  setb    bl
0x180007f58  add     ebx, 1Bh
0x180007f5b  jmp     loc_180007DFB
0x180007f60  bt      ebx, 19h
0x180007f64  mov     ebx, 0
0x180007f69  setb    bl
0x180007f6c  add     ebx, 19h
0x180007f6f  jmp     loc_180007DFB
0x180007f74  test    ebx, 0C00000h
0x180007f7a  jz      short loc_180007F90
0x180007f7c  bt      ebx, 17h
0x180007f80  mov     ebx, 0
0x180007f85  setb    bl
0x180007f88  add     ebx, 17h
0x180007f8b  jmp     loc_180007DFB
0x180007f90  bt      ebx, 15h
0x180007f94  mov     ebx, 0
0x180007f99  setb    bl
0x180007f9c  add     ebx, 15h
0x180007f9f  jmp     loc_180007DFB
```
