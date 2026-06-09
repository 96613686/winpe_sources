# WxNewStringAtoWCchCp<WxCoTaskAllocator>(char const *,ulong,ulong,ushort * *)

- ea: `0x18000c4d0`
- end: `0x18000c665`
- name: `??$WxNewStringAtoWCchCp@VWxCoTaskAllocator@@@@YAJPEBDKKPEAPEAG@Z`
- size: `405`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, int cbMultiByte, UINT CodePage, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bd94`

## callees

- `0x18000bfd0`
- `0x18000c4d0`
- `0x1800a2660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c620`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c529`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c590`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c529`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c590`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c556`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c556`

## pseudocode

```c
__int64 __fastcall WxNewStringAtoWCchCp<WxCoTaskAllocator>(
        LPCCH lpMultiByteStr,
        int cbMultiByte,
        UINT CodePage,
        _QWORD *a4)
{
  void *v4; // rbx
  int v9; // r15d
  int v10; // eax
  int cchWideChar; // r12d
  unsigned int v12; // ecx
  size_t v13; // rax
  void *v14; // rax
  void *lpWideCharStr; // r14
  int v16; // eax
  signed int v17; // edi
  signed int LastError; // eax
  signed int v20; // eax
  size_t v21; // [rsp+30h] [rbp-58h]
  void *v22; // [rsp+38h] [rbp-50h] BYREF

  v4 = 0;
  if ( a4 && (*a4 = 0, lpMultiByteStr) )
  {
    v9 = -1;
    if ( cbMultiByte != -1 )
      v9 = cbMultiByte;
    v10 = MultiByteToWideChar(CodePage, 0, lpMultiByteStr, v9, 0, 0);
    cchWideChar = v10;
    if ( v10 )
    {
      v12 = 2 * v10;
      v13 = (unsigned int)(2 * v10 + 2);
      v22 = 0;
      if ( cbMultiByte == -1 )
        v13 = v12;
      v21 = v13;
      v14 = CoTaskMemAlloc((unsigned int)v13);
      lpWideCharStr = v14;
      if ( v14 )
      {
        memset_0(v14, 0, v21);
        v4 = lpWideCharStr;
        v22 = lpWideCharStr;
        v16 = MultiByteToWideChar(CodePage, 0, lpMultiByteStr, v9, (LPWSTR)lpWideCharStr, cchWideChar);
        if ( v16 )
        {
          if ( cbMultiByte != -1 )
            *((_WORD *)lpWideCharStr + v16) = 0;
          *a4 = lpWideCharStr;
          v4 = 0;
          v22 = 0;
          v17 = 0;
        }
        else
        {
          LastError = GetLastError();
          v17 = LastError;
          if ( LastError > 0 )
            v17 = (unsigned __int16)LastError | 0x80070000;
          if ( v17 >= 0 )
            v17 = -2147418113;
        }
      }
      else
      {
        v17 = -2147024882;
      }
      if ( v4 )
        WxCoTaskAllocator::Free(&v22);
    }
    else
    {
      v20 = GetLastError();
      v17 = v20;
      if ( v20 > 0 )
        v17 = (unsigned __int16)v20 | 0x80070000;
      if ( v17 >= 0 )
        return (unsigned int)-2147418113;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18000c4d0  push    rbx
0x18000c4d2  push    rbp
0x18000c4d3  push    rsi
0x18000c4d4  push    rdi
0x18000c4d5  push    r12
0x18000c4d7  push    r13
0x18000c4d9  push    r14
0x18000c4db  push    r15
0x18000c4dd  sub     rsp, 48h
0x18000c4e1  xor     ebx, ebx
0x18000c4e3  mov     rdi, r9
0x18000c4e6  mov     [rsp+88h+var_54], ebx
0x18000c4ea  mov     r13d, r8d
0x18000c4ed  mov     esi, edx
0x18000c4ef  mov     rbp, rcx
0x18000c4f2  test    r9, r9
0x18000c4f5  jz      loc_18000C5E8
0x18000c4fb  mov     [r9], rbx
0x18000c4fe  test    rcx, rcx
0x18000c501  jz      loc_18000C64C
0x18000c507  or      r14d, 0FFFFFFFFh
0x18000c50b  mov     [rsp+88h+cchWideChar], ebx; cchWideChar
0x18000c50f  cmp     edx, r14d
0x18000c512  mov     [rsp+88h+lpWideCharStr], rbx; lpWideCharStr
0x18000c517  mov     r8, rcx; lpMultiByteStr
0x18000c51a  mov     r15d, r14d
0x18000c51d  cmovnz  r15d, edx
0x18000c521  mov     ecx, r13d; CodePage
0x18000c524  mov     r9d, r15d; cbMultiByte
0x18000c527  xor     edx, edx; dwFlags
0x18000c529  call    cs:__imp_MultiByteToWideChar
0x18000c52f  mov     r12d, eax
0x18000c532  test    eax, eax
0x18000c534  jz      loc_18000C620
0x18000c53a  lea     ecx, [rax+rax]
0x18000c53d  mov     [rsp+88h+var_54], ebx
0x18000c541  lea     eax, [rcx+2]
0x18000c544  mov     [rsp+88h+var_50], rbx
0x18000c549  cmp     esi, r14d
0x18000c54c  cmovz   eax, ecx
0x18000c54f  mov     ecx, eax; cb
0x18000c551  mov     [rsp+30h], rax
0x18000c556  call    cs:__imp_CoTaskMemAlloc
0x18000c55c  mov     r14, rax
0x18000c55f  test    rax, rax
0x18000c562  jz      short loc_18000C5D1
0x18000c564  mov     r8, [rsp+30h]; Size
0x18000c569  xor     edx, edx; Val
0x18000c56b  mov     rcx, rax; void *
0x18000c56e  call    memset_0
0x18000c573  mov     rbx, r14
0x18000c576  mov     [rsp+88h+var_50], rbx
0x18000c57b  mov     [rsp+88h+cchWideChar], r12d; cchWideChar
0x18000c580  mov     r9d, r15d; cbMultiByte
0x18000c583  mov     r8, rbp; lpMultiByteStr
0x18000c586  mov     [rsp+88h+lpWideCharStr], rbx; lpWideCharStr
0x18000c58b  xor     edx, edx; dwFlags
0x18000c58d  mov     ecx, r13d; CodePage
0x18000c590  call    cs:__imp_MultiByteToWideChar
0x18000c596  test    eax, eax
0x18000c598  jz      short loc_18000C5F7
0x18000c59a  cmp     esi, 0FFFFFFFFh
0x18000c59d  jnz     loc_18000C656
0x18000c5a3  mov     [rdi], rbx
0x18000c5a6  xor     ebx, ebx
0x18000c5a8  mov     [rsp+88h+var_50], rbx
0x18000c5ad  xor     edi, edi
0x18000c5af  test    rbx, rbx
0x18000c5b2  jz      short loc_18000C5BE
0x18000c5b4  lea     rcx, [rsp+88h+var_50]; void **
0x18000c5b9  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x18000c5be  mov     eax, edi
0x18000c5c0  add     rsp, 48h
0x18000c5c4  pop     r15
0x18000c5c6  pop     r14
0x18000c5c8  pop     r13
0x18000c5ca  pop     r12
0x18000c5cc  pop     rdi
0x18000c5cd  pop     rsi
0x18000c5ce  pop     rbp
0x18000c5cf  pop     rbx
0x18000c5d0  retn
0x18000c5d1  mov     [rsp+88h+var_54], 4Ch ; 'L'
0x18000c5d9  mov     edi, 8007000Eh
0x18000c5de  mov     [rsp+88h+var_54], 0C5h
0x18000c5e6  jmp     short loc_18000C5AF
0x18000c5e8  mov     [rsp+88h+var_54], 9Dh
0x18000c5f0  mov     edi, 80070057h
0x18000c5f5  jmp     short loc_18000C5BE
0x18000c5f7  call    cs:__imp_GetLastError
0x18000c5fd  mov     edi, eax
0x18000c5ff  test    eax, eax
0x18000c601  jle     short loc_18000C60C
0x18000c603  movzx   edi, ax
0x18000c606  or      edi, 80070000h
0x18000c60c  test    edi, edi
0x18000c60e  mov     [rsp+88h+var_54], 0D1h
0x18000c616  mov     eax, 8000FFFFh
0x18000c61b  cmovns  edi, eax
0x18000c61e  jmp     short loc_18000C5AF
0x18000c620  call    cs:__imp_GetLastError
0x18000c626  mov     edi, eax
0x18000c628  test    eax, eax
0x18000c62a  jle     short loc_18000C635
0x18000c62c  movzx   edi, ax
0x18000c62f  or      edi, 80070000h
0x18000c635  test    edi, edi
0x18000c637  mov     [rsp+88h+var_54], 0B6h
0x18000c63f  mov     eax, 8000FFFFh
0x18000c644  cmovns  edi, eax
0x18000c647  jmp     loc_18000C5BE
0x18000c64c  mov     [rsp+88h+var_54], 0A0h
0x18000c654  jmp     short loc_18000C5F0
0x18000c656  movsxd  rcx, eax
0x18000c659  xor     eax, eax
0x18000c65b  mov     [r14+rcx*2], ax
0x18000c660  jmp     loc_18000C5A3
```
