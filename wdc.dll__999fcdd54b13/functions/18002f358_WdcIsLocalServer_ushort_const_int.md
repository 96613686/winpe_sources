# WdcIsLocalServer(ushort const *,int *)

- ea: `0x18002f358`
- end: `0x18002f474`
- name: `?WdcIsLocalServer@@YAJPEBGPEAH@Z`
- size: `284`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180032c40`
- `0x180056280`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18002f358`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f38d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f428`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f38d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f428`
- `KERNEL32!GetLastError` at `0x18002f3fb`
- `KERNEL32!GetLastError` at `0x18002f3fb`
- `KERNEL32!GetComputerNameW` at `0x18002f3f1`
- `KERNEL32!GetComputerNameW` at `0x18002f3f1`

## pseudocode

```c
__int64 __fastcall WdcIsLocalServer(const unsigned __int16 *a1, int *a2)
{
  unsigned int v2; // ebx
  const unsigned __int16 *v4; // rdi
  const char *v5; // rdx
  int v6; // r8d
  WCHAR *v7; // r14
  signed int LastError; // eax
  const char *v10; // rdx
  int v11; // r8d
  DWORD nSize; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  nSize = 16;
  v4 = a1;
  if ( a1 && *a1 )
  {
    if ( !(unsigned int)_o__wcsicmp(a1, L".") )
    {
LABEL_7:
      *a2 = 1;
      return v2;
    }
    v7 = (WCHAR *)WdcAlloc(2LL * nSize, v5, v6);
    if ( !v7 )
    {
      v2 = -2147024882;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\resourcemonitornode.cpp",
        "WdcIsLocalServer",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      goto LABEL_7;
    }
    *v7 = 0;
    if ( GetComputerNameW(v7, &nSize) )
      goto LABEL_16;
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( (v2 & 0x80000000) == 0 )
      {
LABEL_16:
        while ( *v4 == 92 )
          ++v4;
        *a2 = _o__wcsicmp(v7, v4) == 0;
        goto LABEL_20;
      }
    }
    else
    {
      v2 = -2147467259;
    }
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\resourcemonitornode.cpp",
      "WdcIsLocalServer",
      0,
      L"FAILURE: 0x%08x",
      v2);
    *a2 = 1;
LABEL_20:
    WdcFree(v7, v10, v11);
    return v2;
  }
  *a2 = 1;
  return v2;
}

```

## disassembly

```asm
0x18002f358  push    rbx
0x18002f35a  push    rsi
0x18002f35b  push    rdi
0x18002f35c  push    r14
0x18002f35e  sub     rsp, 38h
0x18002f362  xor     ebx, ebx
0x18002f364  mov     [rsp+58h+nSize], 10h
0x18002f36c  mov     rsi, rdx
0x18002f36f  mov     rdi, rcx
0x18002f372  test    rcx, rcx
0x18002f375  jnz     short loc_18002F37F
0x18002f377  mov     dword ptr [rdx], 1
0x18002f37d  jmp     short loc_18002F3D7
0x18002f37f  xor     eax, eax
0x18002f381  cmp     ax, [rcx]
0x18002f384  jz      short loc_18002F377
0x18002f386  lea     rdx, asc_180094934; "."
0x18002f38d  call    cs:__imp__o__wcsicmp
0x18002f393  test    eax, eax
0x18002f395  jz      short loc_18002F3D1
0x18002f397  mov     ecx, [rsp+58h+nSize]
0x18002f39b  add     rcx, rcx; dwBytes
0x18002f39e  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18002f3a3  mov     r14, rax
0x18002f3a6  test    rax, rax
0x18002f3a9  jnz     short loc_18002F3E3
0x18002f3ab  mov     ebx, 8007000Eh
0x18002f3b0  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002f3b7  xor     r8d, r8d; int
0x18002f3ba  mov     [rsp+58h+var_38], ebx
0x18002f3be  lea     rdx, aWdcislocalserv; "WdcIsLocalServer"
0x18002f3c5  lea     rcx, aBaseDiagnosisP_54; "base\\diagnosis\\pdui\\perfmon\\mmc\\re"...
0x18002f3cc  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002f3d1  mov     dword ptr [rsi], 1
0x18002f3d7  mov     eax, ebx
0x18002f3d9  add     rsp, 38h
0x18002f3dd  pop     r14
0x18002f3df  pop     rdi
0x18002f3e0  pop     rsi
0x18002f3e1  pop     rbx
0x18002f3e2  retn
0x18002f3e3  xor     eax, eax
0x18002f3e5  lea     rdx, [rsp+58h+nSize]; nSize
0x18002f3ea  mov     rcx, r14; lpBuffer
0x18002f3ed  mov     [r14], ax
0x18002f3f1  call    cs:__imp_GetComputerNameW
0x18002f3f7  test    eax, eax
0x18002f3f9  jnz     short loc_18002F41C
0x18002f3fb  call    cs:__imp_GetLastError
0x18002f401  mov     ebx, eax
0x18002f403  test    eax, eax
0x18002f405  jz      short loc_18002F439
0x18002f407  jle     short loc_18002F412
0x18002f409  movzx   ebx, ax
0x18002f40c  or      ebx, 80070000h
0x18002f412  test    ebx, ebx
0x18002f414  js      short loc_18002F43E
0x18002f416  jmp     short loc_18002F41C
0x18002f418  add     rdi, 2
0x18002f41c  cmp     word ptr [rdi], 5Ch ; '\'
0x18002f420  jz      short loc_18002F418
0x18002f422  mov     rdx, rdi
0x18002f425  mov     rcx, r14
0x18002f428  call    cs:__imp__o__wcsicmp
0x18002f42e  xor     ecx, ecx
0x18002f430  test    eax, eax
0x18002f432  setz    cl
0x18002f435  mov     [rsi], ecx
0x18002f437  jmp     short loc_18002F467
0x18002f439  mov     ebx, 80004005h
0x18002f43e  mov     eax, ebx
0x18002f440  mov     [rsp+58h+var_38], ebx
0x18002f444  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002f44b  xor     r8d, r8d; int
0x18002f44e  lea     rdx, aWdcislocalserv; "WdcIsLocalServer"
0x18002f455  lea     rcx, aBaseDiagnosisP_54; "base\\diagnosis\\pdui\\perfmon\\mmc\\re"...
0x18002f45c  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002f461  mov     dword ptr [rsi], 1
0x18002f467  mov     rcx, r14; void *
0x18002f46a  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18002f46f  jmp     loc_18002F3D7
```
