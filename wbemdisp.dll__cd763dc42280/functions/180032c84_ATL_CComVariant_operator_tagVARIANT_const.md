# ATL::CComVariant::operator==(tagVARIANT const &)

- ea: `0x180032c84`
- end: `0x180032dab`
- name: `??8CComVariant@ATL@@QEBA_NAEBUtagVARIANT@@@Z`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003379c`

## callees

- `0x180032c84`
- `0x180034053`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x180032d63`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180032d6f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180032d83`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180032d63`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180032d6f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180032d83`

## pseudocode

```c
char __fastcall ATL::CComVariant::operator==(unsigned __int16 *a1, __int64 a2)
{
  unsigned int v4; // eax
  char v6; // di
  bool v7; // zf
  UINT v9; // ebx
  UINT v10; // eax

  if ( a1 == (unsigned __int16 *)a2 )
    return 1;
  v4 = *a1;
  if ( (_WORD)v4 != *(_WORD *)a2 )
    return 0;
  if ( v4 > 0x11 )
  {
    if ( v4 != 4095 )
      return 0;
    goto LABEL_30;
  }
  if ( v4 == 17 )
    return *((_BYTE *)a1 + 8) == *(_BYTE *)(a2 + 8);
  if ( v4 > 5 )
  {
    if ( v4 != 8 )
    {
      if ( v4 != 9 )
      {
        if ( v4 == 10 )
          return *((_DWORD *)a1 + 2) == *(_DWORD *)(a2 + 8);
        if ( v4 == 11 )
          return a1[4] == *(_WORD *)(a2 + 8);
        if ( v4 != 13 )
          return 0;
      }
      return *((_QWORD *)a1 + 1) == *(_QWORD *)(a2 + 8);
    }
LABEL_30:
    v9 = SysStringByteLen(*(BSTR *)(a2 + 8));
    v6 = 0;
    if ( SysStringByteLen(*((BSTR *)a1 + 1)) != v9 )
      return v6;
    v10 = SysStringByteLen(*((BSTR *)a1 + 1));
    v7 = memcmp_0(*((const void **)a1 + 1), *(const void **)(a2 + 8), v10) == 0;
LABEL_14:
    if ( !v7 )
      return v6;
    return 1;
  }
  if ( v4 == 5 )
    return *((double *)a1 + 1) == *(double *)(a2 + 8);
  v6 = 0;
  if ( *a1 && v4 != 1 )
  {
    if ( v4 != 2 )
    {
      if ( v4 != 3 )
      {
        if ( v4 != 4 )
          return 0;
        v7 = *((float *)a1 + 2) == *(float *)(a2 + 8);
        goto LABEL_14;
      }
      return *((_DWORD *)a1 + 2) == *(_DWORD *)(a2 + 8);
    }
    return a1[4] == *(_WORD *)(a2 + 8);
  }
  return 1;
}

```

## disassembly

```asm
0x180032c84  push    rbx
0x180032c86  push    rbp
0x180032c87  push    rsi
0x180032c88  push    rdi
0x180032c89  sub     rsp, 28h
0x180032c8d  mov     rbp, rdx
0x180032c90  mov     rsi, rcx
0x180032c93  cmp     rcx, rdx
0x180032c96  jz      loc_180032DA0
0x180032c9c  movzx   eax, word ptr [rcx]
0x180032c9f  cmp     ax, [rdx]
0x180032ca2  jz      short loc_180032CAB
0x180032ca4  xor     al, al
0x180032ca6  jmp     loc_180032DA2
0x180032cab  mov     ecx, eax
0x180032cad  cmp     eax, 11h
0x180032cb0  ja      loc_180032D53
0x180032cb6  jz      loc_180032D4B
0x180032cbc  cmp     eax, 5
0x180032cbf  ja      short loc_180032D0F
0x180032cc1  jz      short loc_180032CFD
0x180032cc3  xor     edi, edi
0x180032cc5  test    eax, eax
0x180032cc7  jz      loc_180032DA0
0x180032ccd  sub     ecx, 1
0x180032cd0  jz      loc_180032DA0
0x180032cd6  sub     ecx, 1
0x180032cd9  jz      short loc_180032D36
0x180032cdb  sub     ecx, 1
0x180032cde  jz      short loc_180032D43
0x180032ce0  cmp     ecx, 1
0x180032ce3  jnz     short loc_180032CA4
0x180032ce5  movss   xmm0, dword ptr [rsi+8]
0x180032cea  ucomiss xmm0, dword ptr [rdx+8]
0x180032cee  jp      short loc_180032CF5
0x180032cf0  jnz     short loc_180032CF5
0x180032cf2  mov     dil, 1
0x180032cf5  mov     al, dil
0x180032cf8  jmp     loc_180032DA2
0x180032cfd  movsd   xmm0, qword ptr [rsi+8]
0x180032d02  ucomisd xmm0, qword ptr [rdx+8]
0x180032d07  jp      short loc_180032D0B
0x180032d09  jz      short loc_180032CF2
0x180032d0b  xor     edi, edi
0x180032d0d  jmp     short loc_180032CF5
0x180032d0f  sub     ecx, 8
0x180032d12  jz      short loc_180032D5F
0x180032d14  sub     ecx, 1
0x180032d17  jz      short loc_180032D2C
0x180032d19  sub     ecx, 1
0x180032d1c  jz      short loc_180032D43
0x180032d1e  sub     ecx, 1
0x180032d21  jz      short loc_180032D36
0x180032d23  cmp     ecx, 2
0x180032d26  jnz     loc_180032CA4
0x180032d2c  mov     rax, [rdx+8]
0x180032d30  cmp     [rsi+8], rax
0x180032d34  jmp     short loc_180032D3E
0x180032d36  movzx   eax, word ptr [rdx+8]
0x180032d3a  cmp     [rsi+8], ax
0x180032d3e  setz    al
0x180032d41  jmp     short loc_180032DA2
0x180032d43  mov     eax, [rdx+8]
0x180032d46  cmp     [rsi+8], eax
0x180032d49  jmp     short loc_180032D3E
0x180032d4b  mov     al, [rdx+8]
0x180032d4e  cmp     [rsi+8], al
0x180032d51  jmp     short loc_180032D3E
0x180032d53  cmp     ecx, 0FFFh
0x180032d59  jnz     loc_180032CA4
0x180032d5f  mov     rcx, [rdx+8]; bstr
0x180032d63  call    cs:__imp_SysStringByteLen
0x180032d69  mov     rcx, [rsi+8]; bstr
0x180032d6d  mov     ebx, eax
0x180032d6f  call    cs:__imp_SysStringByteLen
0x180032d75  xor     edi, edi
0x180032d77  cmp     eax, ebx
0x180032d79  jnz     loc_180032CF5
0x180032d7f  mov     rcx, [rsi+8]; bstr
0x180032d83  call    cs:__imp_SysStringByteLen
0x180032d89  mov     rdx, [rbp+8]; Buf2
0x180032d8d  mov     rcx, [rsi+8]; Buf1
0x180032d91  mov     r8d, eax; Size
0x180032d94  call    memcmp_0
0x180032d99  test    eax, eax
0x180032d9b  jmp     loc_180032CF0
0x180032da0  mov     al, 1
0x180032da2  add     rsp, 28h
0x180032da6  pop     rdi
0x180032da7  pop     rsi
0x180032da8  pop     rbp
0x180032da9  pop     rbx
0x180032daa  retn
```
