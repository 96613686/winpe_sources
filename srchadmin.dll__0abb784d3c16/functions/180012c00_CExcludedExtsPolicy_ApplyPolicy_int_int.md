# CExcludedExtsPolicy::ApplyPolicy(int *,int *)

- ea: `0x180012c00`
- end: `0x180012dd9`
- name: `?ApplyPolicy@CExcludedExtsPolicy@@UEAAJPEAH0@Z`
- size: `473`
- prototype: `__int64 __fastcall(CExcludedExtsPolicy *__hidden this, int *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000564c`
- `0x1800094f0`
- `0x18000eb30`
- `0x180010c18`
- `0x180012c00`
- `0x180014374`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012da2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180012da2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012dc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012dc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012cf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012cf8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CExcludedExtsPolicy::ApplyPolicy(CExcludedExtsPolicy *this, int *a2, int *a3)
{
  signed int v3; // ebx
  unsigned __int64 v4; // rsi
  __int64 v5; // r11
  __int64 v8; // rcx
  const unsigned __int16 *v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  WCHAR *lpString2; // rdi
  __int64 v17; // rbp
  __int64 v18; // r8
  _DWORD *v19; // rsi
  signed int v20; // eax
  unsigned __int64 v22; // [rsp+78h] [rbp+10h] BYREF

  v3 = 0;
  v4 = 0;
  v5 = 0;
  *a2 = 0;
  *a3 = 0;
  while ( v3 >= 0 )
  {
    v8 = *((_QWORD *)this + v5 + 2);
    if ( v8 )
    {
      if ( *(_DWORD *)v8 )
      {
        v9 = *(const unsigned __int16 **)(v8 + 32);
        v22 = 0;
        v3 = StringCchLengthW(v9, 0xCCCCCCCu, &v22);
        if ( v3 >= 0 )
        {
          v10 = v4;
          v11 = v4 + v22;
          v12 = -1;
          if ( v4 + v22 >= v4 )
            v12 = v4 + v22;
          v4 = v12;
          v3 = v11 < v10 ? 0x80070216 : 0;
        }
      }
    }
    else
    {
      v3 = -2147024888;
    }
    v5 = (unsigned int)(v5 + 1);
    if ( (int)v5 >= 4 )
    {
      if ( v3 >= 0 && v4 )
      {
        v13 = v4 + 4;
        v14 = v4;
        v15 = -1;
        if ( v4 + 4 >= v4 )
          v15 = v4 + 4;
        v4 = v15;
        v3 = v13 < v14 ? 0x80070216 : 0;
      }
      break;
    }
  }
  lpString2 = 0;
  if ( v3 >= 0 )
  {
    if ( !v4 )
    {
LABEL_30:
      v19 = (_DWORD *)((char *)this + 48);
      if ( lpString2 )
      {
        if ( *v19 && CompareStringW(0x800u, 1u, *((PCNZWCH *)this + 10), -1, lpString2, -1) == 2 )
          goto LABEL_38;
        v20 = CTRegValue<unsigned short *>::Set((char *)this + 48, lpString2);
      }
      else
      {
        if ( !*v19 )
          goto LABEL_38;
        v20 = CRegValue::Delete((CExcludedExtsPolicy *)((char *)this + 48));
      }
      *a2 = 1;
      v3 = v20;
      goto LABEL_38;
    }
    v22 = 0;
    v3 = ULongLongMult(v4, 2u, &v22);
    if ( v3 >= 0 )
    {
      if ( v22 + 2 < v22 )
      {
        v3 = -2147024362;
      }
      else
      {
        lpString2 = (WCHAR *)CoTaskMemAlloc(v22 + 2);
        if ( lpString2 )
        {
          v17 = 0;
          *lpString2 = 0;
          v3 = 0;
          while ( v3 >= 0 )
          {
            v18 = *((_QWORD *)this + v17 + 2);
            if ( *(_DWORD *)v18 )
              v3 = StringCchCatW(lpString2, v4 + 1, *(const unsigned __int16 **)(v18 + 32));
            if ( v3 >= 0 )
              v3 = StringCchCatW(lpString2, v4 + 1, L";");
            v17 = (unsigned int)(v17 + 1);
            if ( (int)v17 >= 4 )
            {
              if ( v3 < 0 )
                break;
              goto LABEL_30;
            }
          }
        }
        else
        {
          v3 = -2147024882;
        }
      }
    }
  }
LABEL_38:
  CoTaskMemFree(lpString2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180012c00  push    rbx
0x180012c02  push    rbp
0x180012c03  push    rsi
0x180012c04  push    rdi
0x180012c05  push    r14
0x180012c07  push    r15
0x180012c09  sub     rsp, 38h
0x180012c0d  xor     ebx, ebx
0x180012c0f  xor     esi, esi
0x180012c11  xor     r11d, r11d
0x180012c14  mov     [rdx], ebx
0x180012c16  mov     [r8], ebx
0x180012c19  mov     r15, rdx
0x180012c1c  mov     r14, rcx
0x180012c1f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180012c23  mov     ebp, 80070216h
0x180012c28  test    ebx, ebx
0x180012c2a  js      loc_180012CB4
0x180012c30  mov     rcx, [r14+r11*8+10h]
0x180012c35  test    rcx, rcx
0x180012c38  jnz     short loc_180012C41
0x180012c3a  mov     ebx, 80070008h
0x180012c3f  jmp     short loc_180012C87
0x180012c41  cmp     dword ptr [rcx], 0
0x180012c44  jz      short loc_180012C87
0x180012c46  mov     rcx, [rcx+20h]; unsigned __int16 *
0x180012c4a  lea     r8, [rsp+68h+arg_8]; unsigned __int64 *
0x180012c4f  mov     edx, 0CCCCCCCh; unsigned __int64
0x180012c54  mov     [rsp+68h+arg_8], 0
0x180012c5d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180012c62  mov     ebx, eax
0x180012c64  test    eax, eax
0x180012c66  js      short loc_180012C87
0x180012c68  mov     rcx, [rsp+68h+arg_8]
0x180012c6d  mov     rdx, rsi
0x180012c70  add     rcx, rsi
0x180012c73  mov     rax, rdi
0x180012c76  cmp     rcx, rsi
0x180012c79  cmovnb  rax, rcx
0x180012c7d  cmp     rcx, rdx
0x180012c80  mov     rsi, rax
0x180012c83  sbb     ebx, ebx
0x180012c85  and     ebx, ebp
0x180012c87  inc     r11d
0x180012c8a  cmp     r11d, 4
0x180012c8e  jl      short loc_180012C28
0x180012c90  test    ebx, ebx
0x180012c92  js      short loc_180012CB4
0x180012c94  test    rsi, rsi
0x180012c97  jz      short loc_180012CB4
0x180012c99  lea     rcx, [rsi+4]
0x180012c9d  mov     rdx, rsi
0x180012ca0  cmp     rcx, rsi
0x180012ca3  mov     rax, rdi
0x180012ca6  cmovnb  rax, rcx
0x180012caa  cmp     rcx, rdx
0x180012cad  mov     rsi, rax
0x180012cb0  sbb     ebx, ebx
0x180012cb2  and     ebx, ebp
0x180012cb4  xor     edi, edi
0x180012cb6  test    ebx, ebx
0x180012cb8  js      loc_180012DC1
0x180012cbe  test    rsi, rsi
0x180012cc1  jz      loc_180012D64
0x180012cc7  lea     r8, [rsp+68h+arg_8]; unsigned __int64 *
0x180012ccc  mov     [rsp+68h+arg_8], rdi
0x180012cd1  lea     edx, [rdi+2]; unsigned __int64
0x180012cd4  mov     rcx, rsi; unsigned __int64
0x180012cd7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180012cdc  mov     ebx, eax
0x180012cde  test    eax, eax
0x180012ce0  js      loc_180012DC1
0x180012ce6  mov     rax, [rsp+68h+arg_8]
0x180012ceb  lea     rcx, [rax+2]; cb
0x180012cef  cmp     rcx, rax
0x180012cf2  jb      loc_180012D7B
0x180012cf8  call    cs:__imp_CoTaskMemAlloc
0x180012cfe  mov     rdi, rax
0x180012d01  test    rax, rax
0x180012d04  jnz     short loc_180012D10
0x180012d06  mov     ebx, 8007000Eh
0x180012d0b  jmp     loc_180012DC1
0x180012d10  xor     eax, eax
0x180012d12  xor     ebp, ebp
0x180012d14  mov     [rdi], ax
0x180012d17  xor     ebx, ebx
0x180012d19  test    ebx, ebx
0x180012d1b  js      loc_180012DC1
0x180012d21  mov     r8, [r14+rbp*8+10h]
0x180012d26  cmp     dword ptr [r8], 0
0x180012d2a  jz      short loc_180012D3E
0x180012d2c  mov     r8, [r8+20h]; unsigned __int16 *
0x180012d30  lea     rdx, [rsi+1]; unsigned __int64
0x180012d34  mov     rcx, rdi; unsigned __int16 *
0x180012d37  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012d3c  mov     ebx, eax
0x180012d3e  test    ebx, ebx
0x180012d40  js      short loc_180012D57
0x180012d42  lea     rdx, [rsi+1]; unsigned __int64
0x180012d46  mov     rcx, rdi; unsigned __int16 *
0x180012d49  lea     r8, pszSrc; ";"
0x180012d50  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012d55  mov     ebx, eax
0x180012d57  inc     ebp
0x180012d59  mov     eax, ebx
0x180012d5b  cmp     ebp, 4
0x180012d5e  jl      short loc_180012D19
0x180012d60  test    eax, eax
0x180012d62  js      short loc_180012DC1
0x180012d64  lea     rsi, [r14+30h]
0x180012d68  test    rdi, rdi
0x180012d6b  jnz     short loc_180012D7F
0x180012d6d  cmp     [rsi], edi
0x180012d6f  jz      short loc_180012DC1
0x180012d71  mov     rcx, rsi; this
0x180012d74  call    ?Delete@CRegValue@@QEAAJXZ; CRegValue::Delete(void)
0x180012d79  jmp     short loc_180012DB8
0x180012d7b  mov     ebx, ebp
0x180012d7d  jmp     short loc_180012DC1
0x180012d7f  cmp     dword ptr [rsi], 0
0x180012d82  jz      short loc_180012DAD
0x180012d84  mov     r8, [r14+50h]; lpString1
0x180012d88  or      r9d, 0FFFFFFFFh; cchCount1
0x180012d8c  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x180012d94  mov     ecx, 800h; Locale
0x180012d99  mov     [rsp+68h+lpString2], rdi; lpString2
0x180012d9e  lea     edx, [r9+2]; dwCmpFlags
0x180012da2  call    cs:__imp_CompareStringW
0x180012da8  cmp     eax, 2
0x180012dab  jz      short loc_180012DC1
0x180012dad  mov     rdx, rdi
0x180012db0  mov     rcx, rsi
0x180012db3  call    ?Set@?$CTRegValue@PEAG@@QEAAJQEAG@Z; CTRegValue<ushort *>::Set(ushort * const)
0x180012db8  mov     dword ptr [r15], 1
0x180012dbf  mov     ebx, eax
0x180012dc1  mov     rcx, rdi; pv
0x180012dc4  call    cs:__imp_CoTaskMemFree
0x180012dca  mov     eax, ebx
0x180012dcc  add     rsp, 38h
0x180012dd0  pop     r15
0x180012dd2  pop     r14
0x180012dd4  pop     rdi
0x180012dd5  pop     rsi
0x180012dd6  pop     rbp
0x180012dd7  pop     rbx
0x180012dd8  retn
```
