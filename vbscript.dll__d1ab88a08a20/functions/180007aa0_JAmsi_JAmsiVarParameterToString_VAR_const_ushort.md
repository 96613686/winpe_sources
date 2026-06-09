# JAmsi::JAmsiVarParameterToString(VAR const *,ushort * *)

- ea: `0x180007aa0`
- end: `0x180007dc7`
- name: `?JAmsiVarParameterToString@JAmsi@@AEAA_NPEBVVAR@@PEAPEAG@Z`
- size: `807`
- prototype: `bool __fastcall(JAmsi *__hidden this, const struct VAR *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180007130`

## callees

- `0x180007aa0`
- `0x1800468c4`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x180007b94`
- `msvcrt!_snwprintf_s` at `0x180007bfb`
- `msvcrt!_snwprintf_s` at `0x180007c74`
- `msvcrt!_snwprintf_s` at `0x180007cd1`
- `msvcrt!_snwprintf_s` at `0x180007d42`
- `msvcrt!_snwprintf_s` at `0x180007b94`
- `msvcrt!_snwprintf_s` at `0x180007bfb`
- `msvcrt!_snwprintf_s` at `0x180007c74`
- `msvcrt!_snwprintf_s` at `0x180007cd1`
- `msvcrt!_snwprintf_s` at `0x180007d42`
- `msvcrt!wcscpy_s` at `0x180007db0`
- `msvcrt!wcscpy_s` at `0x180007db0`

## pseudocode

```c
bool __fastcall JAmsi::JAmsiVarParameterToString(JAmsi *this, const struct VAR *a2, unsigned __int16 **a3)
{
  int v5; // ecx
  __int64 v6; // rcx
  __int64 v7; // rax
  unsigned int v9; // r14d
  wchar_t *v10; // rax
  wchar_t *v11; // rsi
  bool result; // al
  wchar_t *v13; // rax
  wchar_t *v14; // rsi
  int v15; // eax
  wchar_t *v16; // rax
  wchar_t *v17; // rsi
  wchar_t *v18; // rax
  wchar_t *v19; // rax
  wchar_t *v20; // rax
  unsigned __int16 *v21; // rbx

  while ( 1 )
  {
    while ( 1 )
    {
      if ( !a2 )
        goto LABEL_37;
      v5 = *(unsigned __int16 *)a2;
      if ( (v5 & 0x4000) != 0 && (v5 & 0xFFF) == 0xC )
        break;
      switch ( v5 )
      {
        case 8:
          v6 = *((_QWORD *)a2 + 1);
          if ( !v6 )
          {
LABEL_37:
            v20 = (wchar_t *)operator new[](0x10u);
            v21 = v20;
            if ( v20 )
            {
              *v20 = 0;
              wcscpy_s(v20, 8u, L"\"\"");
              result = 1;
              *a3 = v21;
              return result;
            }
            return 0;
          }
          v7 = -1;
          while ( *(_WORD *)(v6 + 2 * v7++ + 2) != 0 )
            ;
          v9 = v7 + 3;
          v10 = (wchar_t *)operator new[](saturated_mul((unsigned int)(v7 + 3), 2u));
          v11 = v10;
          if ( !v10 )
            return 0;
          *v10 = 0;
          if ( _snwprintf_s(v10, v9, 0xFFFFFFFFFFFFFFFFuLL, L"\"%s\"", *((_QWORD *)a2 + 1)) == -1 )
          {
            v11[v9 - 2] = 34;
            v11[v9 - 1] = 0;
          }
          goto LABEL_14;
        case 2:
        case 3:
          v13 = (wchar_t *)operator new[](0x20u);
          v14 = v13;
          if ( v13 )
          {
            *v13 = 0;
            if ( *(_WORD *)a2 == 3 )
              v15 = *((_DWORD *)a2 + 2);
            else
              v15 = *((__int16 *)a2 + 4);
            _snwprintf_s(v14, 0x10u, 0xFFFFFFFFFFFFFFFFuLL, L"\"%d\"", v15);
            result = 1;
            *a3 = v14;
            return result;
          }
          return 0;
        case 11:
          v19 = (wchar_t *)operator new[](0x14u);
          v11 = v19;
          if ( !v19 )
            return 0;
          *v19 = 0;
          if ( _snwprintf_s(
                 v19,
                 0xAu,
                 0xFFFFFFFFFFFFFFFFuLL,
                 L"\"%s\"",
                 *(wchar_t **)((char *)off_18007CC98 + (*((_WORD *)a2 + 4) != 0 ? 8 : 0))) == -1 )
            *((_DWORD *)v11 + 4) = 34;
LABEL_14:
          *a3 = v11;
          return 1;
      }
      if ( v5 != 74 )
      {
        v18 = (wchar_t *)operator new[](0x62u);
        v11 = v18;
        if ( !v18 )
          return 0;
        *v18 = 0;
        if ( _snwprintf_s(
               v18,
               0x31u,
               0xFFFFFFFFFFFFFFFFuLL,
               L"\"Unsupported parameter type %08x\"",
               *(unsigned __int16 *)a2) == -1 )
          *(_DWORD *)(v11 + 47) = 34;
        goto LABEL_14;
      }
      if ( *((const struct VAR **)a2 + 1) == a2 )
        return 1;
      a2 = (const struct VAR *)*((_QWORD *)a2 + 1);
    }
    if ( (v5 & 0x2000) != 0 )
      break;
    a2 = (const struct VAR *)*((_QWORD *)a2 + 1);
  }
  v16 = (wchar_t *)operator new[](0x62u);
  v17 = v16;
  if ( !v16 )
    return 0;
  *v16 = 0;
  if ( _snwprintf_s(v16, 0x31u, 0xFFFFFFFFFFFFFFFFuLL, L"\"Unsupported parameter type %08x\"", *(unsigned __int16 *)a2) == -1 )
    *(_DWORD *)(v17 + 47) = 34;
  *a3 = v17;
  return 1;
}

```

## disassembly

```asm
0x180007aa0  push    rbx
0x180007aa2  push    r12
0x180007aa4  sub     rsp, 38h
0x180007aa8  mov     [rsp+48h+arg_0], rbp
0x180007aad  mov     r12, r8
0x180007ab0  mov     [rsp+48h+arg_8], rsi
0x180007ab5  mov     rbx, rdx
0x180007ab8  mov     [rsp+48h+arg_10], rdi
0x180007abd  mov     r9d, 0FFFh
0x180007ac3  mov     [rsp+48h+arg_18], r14
0x180007ac8  mov     [rsp+48h+var_18], r15
0x180007acd  test    rbx, rbx
0x180007ad0  jz      loc_180007D84
0x180007ad6  movzx   ecx, word ptr [rbx]
0x180007ad9  bt      cx, 0Eh
0x180007ade  jb      short loc_180007B53
0x180007ae0  cmp     ecx, 8
0x180007ae3  jnz     loc_180007BB0
0x180007ae9  mov     rcx, [rbx+8]
0x180007aed  test    rcx, rcx
0x180007af0  jz      loc_180007D84
0x180007af6  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180007afd  mov     rax, rdi
0x180007b00  cmp     word ptr [rcx+rax*2+2], 0
0x180007b06  lea     rax, [rax+1]
0x180007b0a  jnz     short loc_180007B00
0x180007b0c  lea     r14d, [rax+3]
0x180007b10  mov     eax, 2
0x180007b15  mov     ebp, r14d
0x180007b18  mul     rbp
0x180007b1b  cmovb   rax, rdi
0x180007b1f  mov     rcx, rax; unsigned __int64
0x180007b22  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007b27  mov     rsi, rax
0x180007b2a  test    rax, rax
0x180007b2d  jnz     short loc_180007B74
0x180007b2f  xor     al, al
0x180007b31  mov     r15, [rsp+48h+var_18]
0x180007b36  mov     r14, [rsp+48h+arg_18]
0x180007b3b  mov     rdi, [rsp+48h+arg_10]
0x180007b40  mov     rsi, [rsp+48h+arg_8]
0x180007b45  mov     rbp, [rsp+48h+arg_0]
0x180007b4a  add     rsp, 38h
0x180007b4e  pop     r12
0x180007b50  pop     rbx
0x180007b51  retn
0x180007b53  movzx   eax, cx
0x180007b56  and     ax, r9w
0x180007b5a  cmp     ax, 0Ch
0x180007b5e  jnz     short loc_180007AE0
0x180007b60  bt      cx, 0Dh
0x180007b65  jb      loc_180007C3A
0x180007b6b  mov     rbx, [rbx+8]
0x180007b6f  jmp     loc_180007ACD
0x180007b74  xor     r15d, r15d
0x180007b77  lea     r9, aS; "\"%s\""
0x180007b7e  mov     [rax], r15w
0x180007b82  mov     r8, rdi; MaxCount
0x180007b85  mov     rcx, [rbx+8]
0x180007b89  mov     rdx, rbp; BufferCount
0x180007b8c  mov     [rsp+48h+var_28], rcx
0x180007b91  mov     rcx, rsi; Buffer
0x180007b94  call    cs:__imp__snwprintf_s
0x180007b9b  nop     dword ptr [rax+rax+00h]
0x180007ba0  cmp     eax, edi
0x180007ba2  jz      loc_180007D6C
0x180007ba8  mov     [r12], rsi
0x180007bac  mov     al, 1
0x180007bae  jmp     short loc_180007B31
0x180007bb0  mov     edx, ecx
0x180007bb2  sub     edx, 2
0x180007bb5  jnz     short loc_180007C12
0x180007bb7  mov     ecx, 20h ; ' '; unsigned __int64
0x180007bbc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007bc1  mov     rsi, rax
0x180007bc4  test    rax, rax
0x180007bc7  jz      loc_180007B2F
0x180007bcd  xor     r15d, r15d
0x180007bd0  mov     [rax], r15w
0x180007bd4  cmp     word ptr [rbx], 3
0x180007bd8  jnz     loc_180007D63
0x180007bde  mov     eax, [rbx+8]
0x180007be1  lea     r9, aD; "\"%d\""
0x180007be8  mov     dword ptr [rsp+48h+var_28], eax
0x180007bec  mov     edx, 10h; BufferCount
0x180007bf1  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180007bf8  mov     rcx, rsi; Buffer
0x180007bfb  call    cs:__imp__snwprintf_s
0x180007c02  nop     dword ptr [rax+rax+00h]
0x180007c07  mov     al, 1
0x180007c09  mov     [r12], rsi
0x180007c0d  jmp     loc_180007B31
0x180007c12  sub     edx, 1
0x180007c15  jz      short loc_180007BB7
0x180007c17  sub     edx, 8
0x180007c1a  jz      loc_180007CF2
0x180007c20  cmp     edx, 3Fh ; '?'
0x180007c23  jnz     short loc_180007C97
0x180007c25  mov     rax, [rbx+8]
0x180007c29  cmp     rax, rbx
0x180007c2c  jz      loc_180007BAC
0x180007c32  mov     rbx, rax
0x180007c35  jmp     loc_180007ACD
0x180007c3a  mov     ecx, 62h ; 'b'; unsigned __int64
0x180007c3f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007c44  mov     rsi, rax
0x180007c47  test    rax, rax
0x180007c4a  jz      loc_180007B2F
0x180007c50  xor     r15d, r15d
0x180007c53  lea     r9, aUnsupportedPar; "\"Unsupported parameter type %08x\""
0x180007c5a  mov     [rax], r15w
0x180007c5e  mov     edx, 31h ; '1'; BufferCount
0x180007c63  movzx   ecx, word ptr [rbx]
0x180007c66  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180007c6d  mov     dword ptr [rsp+48h+var_28], ecx
0x180007c71  mov     rcx, rax; Buffer
0x180007c74  call    cs:__imp__snwprintf_s
0x180007c7b  nop     dword ptr [rax+rax+00h]
0x180007c80  cmp     eax, 0FFFFFFFFh
0x180007c83  jnz     short loc_180007C8C
0x180007c85  mov     dword ptr [rsi+5Eh], 22h ; '"'
0x180007c8c  mov     [r12], rsi
0x180007c90  mov     al, 1
0x180007c92  jmp     loc_180007B31
0x180007c97  mov     ecx, 62h ; 'b'; unsigned __int64
0x180007c9c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007ca1  mov     rsi, rax
0x180007ca4  test    rax, rax
0x180007ca7  jz      loc_180007B2F
0x180007cad  xor     r15d, r15d
0x180007cb0  lea     r9, aUnsupportedPar; "\"Unsupported parameter type %08x\""
0x180007cb7  mov     [rax], r15w
0x180007cbb  mov     edx, 31h ; '1'; BufferCount
0x180007cc0  movzx   ecx, word ptr [rbx]
0x180007cc3  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180007cca  mov     dword ptr [rsp+48h+var_28], ecx
0x180007cce  mov     rcx, rax; Buffer
0x180007cd1  call    cs:__imp__snwprintf_s
0x180007cd8  nop     dword ptr [rax+rax+00h]
0x180007cdd  cmp     eax, 0FFFFFFFFh
0x180007ce0  jnz     loc_180007BA8
0x180007ce6  mov     dword ptr [rsi+5Eh], 22h ; '"'
0x180007ced  jmp     loc_180007BA8
0x180007cf2  mov     ecx, 14h; unsigned __int64
0x180007cf7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007cfc  mov     rsi, rax
0x180007cff  test    rax, rax
0x180007d02  jz      loc_180007B2F
0x180007d08  xor     r15d, r15d
0x180007d0b  lea     r9, aS; "\"%s\""
0x180007d12  mov     [rax], r15w
0x180007d16  mov     edx, 0Ah; BufferCount
0x180007d1b  movzx   ecx, word ptr [rbx+8]
0x180007d1f  lea     rax, off_18007CC98; "false"
0x180007d26  neg     cx
0x180007d29  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180007d30  sbb     rcx, rcx
0x180007d33  and     ecx, 8
0x180007d36  mov     rcx, [rcx+rax]
0x180007d3a  mov     [rsp+48h+var_28], rcx
0x180007d3f  mov     rcx, rsi; Buffer
0x180007d42  call    cs:__imp__snwprintf_s
0x180007d49  nop     dword ptr [rax+rax+00h]
0x180007d4e  cmp     eax, 0FFFFFFFFh
0x180007d51  jnz     loc_180007BA8
0x180007d57  mov     dword ptr [rsi+10h], 22h ; '"'
0x180007d5e  jmp     loc_180007BA8
0x180007d63  movsx   eax, word ptr [rbx+8]
0x180007d67  jmp     loc_180007BE1
0x180007d6c  lea     eax, [r14-2]
0x180007d70  mov     word ptr [rsi+rax*2], 22h ; '"'
0x180007d76  lea     eax, [r14-1]
0x180007d7a  mov     [rsi+rax*2], r15w
0x180007d7f  jmp     loc_180007BA8
0x180007d84  mov     ecx, 10h; unsigned __int64
0x180007d89  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007d8e  mov     rbx, rax
0x180007d91  test    rax, rax
0x180007d94  jz      loc_180007B2F
0x180007d9a  xor     r15d, r15d
0x180007d9d  lea     r8, asc_180083F4C; "\"\""
0x180007da4  mov     edx, 8; SizeInWords
0x180007da9  mov     [rax], r15w
0x180007dad  mov     rcx, rax; Destination
0x180007db0  call    cs:__imp_wcscpy_s
0x180007db7  nop     dword ptr [rax+rax+00h]
0x180007dbc  mov     al, 1
0x180007dbe  mov     [r12], rbx
0x180007dc2  jmp     loc_180007B31
```
