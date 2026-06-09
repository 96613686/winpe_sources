# TLoad64BitDllsMgr::DocumentPropertiesW(unsigned __int64,ushort *,ulong *,ulong *,uchar * *,ulong,uchar *,int,ulong,ulong *)

- ea: `0x140006c10`
- end: `0x140006ea2`
- name: `?DocumentPropertiesW@TLoad64BitDllsMgr@@QEAAJ_KPEAGPEAK2PEAPEAEKPEAEHK2@Z`
- size: `658`
- prototype: `int(TLoad64BitDllsMgr *__hidden this, unsigned __int64, unsigned __int16 *, unsigned int *, unsigned int *, unsigned __int8 **, unsigned int, unsigned __int8 *, int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000dc10`

## callees

- `0x140001b9c`
- `0x1400028b8`
- `0x140006894`
- `0x140006c10`
- `0x140007298`
- `0x140007d00`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140006dbd`
- `KERNEL32!GetLastError` at `0x140006e08`
- `KERNEL32!GetLastError` at `0x140006e48`
- `KERNEL32!GetLastError` at `0x140006e62`
- `KERNEL32!GetLastError` at `0x140006dbd`
- `KERNEL32!GetLastError` at `0x140006e08`
- `KERNEL32!GetLastError` at `0x140006e48`
- `KERNEL32!GetLastError` at `0x140006e62`
- `KERNEL32!GetProcAddress` at `0x140006ca7`
- `KERNEL32!GetProcAddress` at `0x140006d82`
- `KERNEL32!GetProcAddress` at `0x140006ca7`
- `KERNEL32!GetProcAddress` at `0x140006d82`
- `KERNEL32!FreeLibrary` at `0x140006e5a`
- `KERNEL32!FreeLibrary` at `0x140006e5a`
- `KERNEL32!LoadLibraryExW` at `0x140006c8b`
- `KERNEL32!LoadLibraryExW` at `0x140006c8b`
- `WINSPOOL!OpenPrinterW` at `0x140006cc3`
- `WINSPOOL!OpenPrinterW` at `0x140006cc3`
- `WINSPOOL!ClosePrinter` at `0x140006e40`
- `WINSPOOL!ClosePrinter` at `0x140006e40`
- `RPCRT4!RpcRevertToSelf` at `0x140006e7d`
- `RPCRT4!RpcRevertToSelf` at `0x140006e7d`
- `RPCRT4!RpcImpersonateClient` at `0x140006c58`
- `RPCRT4!RpcImpersonateClient` at `0x140006c58`

## pseudocode

```c
__int64 __fastcall TLoad64BitDllsMgr::DocumentPropertiesW(
        TLoad64BitDllsMgr *this,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned __int8 **a6,
        signed int a7,
        unsigned __int8 *a8,
        int a9,
        unsigned int a10,
        unsigned int *a11)
{
  TLoad64BitDllsMgr *v11; // rdi
  RPC_STATUS v15; // edx
  HMODULE Library; // rax
  HMODULE v17; // rdi
  FARPROC ProcAddress; // rsi
  int v19; // eax
  unsigned __int8 *v20; // rax
  unsigned __int8 **v21; // rbx
  unsigned int *v22; // r15
  FARPROC v23; // r14
  unsigned __int8 *v24; // rax
  int v25; // r8d
  _OWORD v27[3]; // [rsp+30h] [rbp-38h] BYREF
  HANDLE phPrinter; // [rsp+B0h] [rbp+48h] BYREF

  v11 = pGLdrObj;
  phPrinter = 0;
  memset(v27, 0, sizeof(v27));
  a7 = -1;
  v15 = RpcImpersonateClient(0);
  if ( v15 )
  {
    *a11 = v15;
    return (unsigned int)a7;
  }
  TLoad64BitDllsMgr::RefreshLifeSpan(v11);
  TLoad64BitDllsMgr::IncUIRefCnt(pGLdrObj);
  Library = LoadLibraryExW(L"winspool.drv", 0, 0x800u);
  v17 = Library;
  if ( !Library )
  {
    *a11 = GetLastError();
    goto LABEL_28;
  }
  ProcAddress = GetProcAddress(Library, "DocumentPropertySheets");
  if ( ProcAddress && OpenPrinterW(a3, &phPrinter, 0) )
  {
    *((_QWORD *)&v27[0] + 1) = phPrinter;
    LODWORD(v27[0]) = 48;
    *(_QWORD *)&v27[1] = a3;
    if ( a9
      && (HIDWORD(v27[2]) = 0,
          *(_OWORD *)((char *)&v27[1] + 8) = 0,
          v19 = ((__int64 (__fastcall *)(_QWORD, _OWORD *))ProcAddress)(0, v27),
          v19 > 0) )
    {
      DWORD2(v27[2]) = v19;
      v20 = (unsigned __int8 *)operator new[]((unsigned int)v19);
      v21 = a6;
      *a6 = v20;
      if ( v20 )
        memset_0(v20, 0, DWORD2(v27[2]));
    }
    else
    {
      v21 = a6;
      DWORD2(v27[2]) = 0;
      *a6 = 0;
    }
    v22 = a5;
    *a5 = DWORD2(v27[2]);
    *((_QWORD *)&v27[1] + 1) = a8;
    *(_QWORD *)&v27[2] = *v21;
    HIDWORD(v27[2]) = a10;
    if ( (a10 & 4) != 0 )
    {
      a7 = 0;
      v23 = GetProcAddress(v17, (LPCSTR)0xDA);
      if ( v23 )
      {
        TLoad64BitDllsMgr::IncUIRefCnt(pGLdrObj);
        if ( ((int (__fastcall *)(__int64, FARPROC, _OWORD *, signed int *))v23)(a2, ProcAddress, v27, &a7) >= 0 )
        {
          a7 = (a7 != 1) + 1;
        }
        else
        {
          a7 = -1;
          *a11 = GetLastError();
        }
        TLoad64BitDllsMgr::DecUIRefCnt(pGLdrObj);
        goto LABEL_19;
      }
      a7 = -1;
    }
    else
    {
      a7 = ((__int64 (__fastcall *)(_QWORD, _OWORD *))ProcAddress)(0, v27);
      if ( a7 >= 0 )
      {
LABEL_19:
        if ( *v21 )
        {
          v25 = *v22;
          v24 = *v21;
          if ( *((unsigned __int16 *)v24 + 34) + (unsigned int)*((unsigned __int16 *)v24 + 35) < *v22 )
            v25 = *((unsigned __int16 *)v24 + 34) + *((unsigned __int16 *)v24 + 35);
          *a4 = v25;
        }
        if ( phPrinter )
          ClosePrinter(phPrinter);
        goto LABEL_26;
      }
    }
    *a11 = GetLastError();
    goto LABEL_19;
  }
  *a11 = GetLastError();
LABEL_26:
  FreeLibrary(v17);
LABEL_28:
  TLoad64BitDllsMgr::DecUIRefCnt(pGLdrObj);
  RpcRevertToSelf();
  return (unsigned int)a7;
}

```

## disassembly

```asm
0x140006c10  mov     [rsp-40h+phPrinter], rcx
0x140006c15  push    rbp
0x140006c16  push    rbx
0x140006c17  push    rsi
0x140006c18  push    rdi
0x140006c19  push    r12
0x140006c1b  push    r13
0x140006c1d  push    r14
0x140006c1f  push    r15
0x140006c21  mov     rbp, rsp
0x140006c24  sub     rsp, 68h
0x140006c28  mov     rdi, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; TLoad64BitDllsMgr * pGLdrObj
0x140006c2f  xorps   xmm0, xmm0
0x140006c32  xor     ecx, ecx; BindingHandle
0x140006c34  mov     [rbp+phPrinter], 0
0x140006c3c  movups  [rbp+var_38], xmm0
0x140006c40  mov     r13, r9
0x140006c43  mov     rbx, r8
0x140006c46  movups  [rbp+var_28], xmm0
0x140006c4a  mov     r12, rdx
0x140006c4d  mov     [rbp+arg_30], 0FFFFFFFFh
0x140006c54  movups  xmmword ptr [rbp+Size], xmm0
0x140006c58  call    cs:__imp_RpcImpersonateClient
0x140006c5e  mov     edx, eax
0x140006c60  test    eax, eax
0x140006c62  jnz     loc_140006E85
0x140006c68  mov     rcx, rdi; this
0x140006c6b  call    ?RefreshLifeSpan@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::RefreshLifeSpan(void)
0x140006c70  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x140006c77  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x140006c7c  xor     edx, edx; hFile
0x140006c7e  lea     rcx, LibFileName; "winspool.drv"
0x140006c85  mov     r8d, 800h; dwFlags
0x140006c8b  call    cs:__imp_LoadLibraryExW
0x140006c91  mov     rdi, rax
0x140006c94  test    rax, rax
0x140006c97  jz      loc_140006E62
0x140006c9d  lea     rdx, aDocumentproper_0; "DocumentPropertySheets"
0x140006ca4  mov     rcx, rax; hModule
0x140006ca7  call    cs:__imp_GetProcAddress
0x140006cad  mov     rsi, rax
0x140006cb0  test    rax, rax
0x140006cb3  jz      loc_140006E48
0x140006cb9  xor     r8d, r8d; pDefault
0x140006cbc  lea     rdx, [rbp+phPrinter]; phPrinter
0x140006cc0  mov     rcx, rbx; pPrinterName
0x140006cc3  call    cs:__imp_OpenPrinterW
0x140006cc9  test    eax, eax
0x140006ccb  jz      loc_140006E48
0x140006cd1  cmp     [rbp+arg_40], 0
0x140006cd8  mov     rax, [rbp+phPrinter]
0x140006cdc  mov     qword ptr [rbp+var_38+8], rax
0x140006ce0  mov     dword ptr [rbp+var_38], 30h ; '0'
0x140006ce7  mov     qword ptr [rbp+var_28], rbx
0x140006ceb  jz      short loc_140006D34
0x140006ced  xorps   xmm0, xmm0
0x140006cf0  mov     dword ptr [rbp+Size+0Ch], 0
0x140006cf7  lea     rdx, [rbp+var_38]
0x140006cfb  xor     ecx, ecx
0x140006cfd  mov     rax, rsi
0x140006d00  movdqu  [rbp+var_28+8], xmm0
0x140006d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d0a  test    eax, eax
0x140006d0c  jle     short loc_140006D34
0x140006d0e  mov     ecx, eax; unsigned __int64
0x140006d10  mov     dword ptr [rbp+Size+8], eax
0x140006d13  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140006d18  mov     rbx, [rbp+arg_28]
0x140006d1c  mov     [rbx], rax
0x140006d1f  test    rax, rax
0x140006d22  jz      short loc_140006D46
0x140006d24  mov     r8d, dword ptr [rbp+Size+8]; Size
0x140006d28  xor     edx, edx; Val
0x140006d2a  mov     rcx, rax; void *
0x140006d2d  call    memset_0
0x140006d32  jmp     short loc_140006D46
0x140006d34  mov     rbx, [rbp+arg_28]
0x140006d38  mov     dword ptr [rbp+Size+8], 0
0x140006d3f  mov     qword ptr [rbx], 0
0x140006d46  mov     eax, dword ptr [rbp+Size+8]
0x140006d49  mov     r15, [rbp+arg_20]
0x140006d4d  mov     [r15], eax
0x140006d50  mov     rax, [rbp+arg_38]
0x140006d57  mov     qword ptr [rbp+var_28+8], rax
0x140006d5b  mov     rax, [rbx]
0x140006d5e  mov     [rbp+Size], rax
0x140006d62  mov     eax, [rbp+arg_48]
0x140006d68  mov     dword ptr [rbp+Size+0Ch], eax
0x140006d6b  test    al, 4
0x140006d6d  jz      loc_140006DF3
0x140006d73  mov     edx, 0DAh; lpProcName
0x140006d78  mov     [rbp+arg_30], 0
0x140006d7f  mov     rcx, rdi; hModule
0x140006d82  call    cs:__imp_GetProcAddress
0x140006d88  mov     r14, rax
0x140006d8b  test    rax, rax
0x140006d8e  jz      short loc_140006DEA
0x140006d90  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x140006d97  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x140006d9c  lea     r9, [rbp+arg_30]
0x140006da0  mov     rdx, rsi
0x140006da3  lea     r8, [rbp+var_38]
0x140006da7  mov     rcx, r12
0x140006daa  mov     rax, r14
0x140006dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006db2  test    eax, eax
0x140006db4  jns     short loc_140006DCE
0x140006db6  mov     [rbp+arg_30], 0FFFFFFFFh
0x140006dbd  call    cs:__imp_GetLastError
0x140006dc3  mov     rcx, [rbp+arg_50]
0x140006dca  mov     [rcx], eax
0x140006dcc  jmp     short loc_140006DDC
0x140006dce  xor     eax, eax
0x140006dd0  cmp     [rbp+arg_30], 1
0x140006dd4  setnz   al
0x140006dd7  inc     eax
0x140006dd9  mov     [rbp+arg_30], eax
0x140006ddc  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x140006de3  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x140006de8  jmp     short loc_140006E17
0x140006dea  mov     [rbp+arg_30], 0FFFFFFFFh
0x140006df1  jmp     short loc_140006E08
0x140006df3  lea     rdx, [rbp+var_38]
0x140006df7  xor     ecx, ecx
0x140006df9  mov     rax, rsi
0x140006dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e01  mov     [rbp+arg_30], eax
0x140006e04  test    eax, eax
0x140006e06  jns     short loc_140006E17
0x140006e08  call    cs:__imp_GetLastError
0x140006e0e  mov     rcx, [rbp+arg_50]
0x140006e15  mov     [rcx], eax
0x140006e17  mov     rax, [rbx]
0x140006e1a  test    rax, rax
0x140006e1d  jz      short loc_140006E37
0x140006e1f  movzx   edx, word ptr [rax+46h]
0x140006e23  mov     r8d, [r15]
0x140006e26  movzx   eax, word ptr [rax+44h]
0x140006e2a  add     edx, eax
0x140006e2c  cmp     edx, r8d
0x140006e2f  cmovb   r8d, edx
0x140006e33  mov     [r13+0], r8d
0x140006e37  mov     rcx, [rbp+phPrinter]; hPrinter
0x140006e3b  test    rcx, rcx
0x140006e3e  jz      short loc_140006E57
0x140006e40  call    cs:__imp_ClosePrinter
0x140006e46  jmp     short loc_140006E57
0x140006e48  call    cs:__imp_GetLastError
0x140006e4e  mov     rcx, [rbp+arg_50]
0x140006e55  mov     [rcx], eax
0x140006e57  mov     rcx, rdi; hLibModule
0x140006e5a  call    cs:__imp_FreeLibrary
0x140006e60  jmp     short loc_140006E71
0x140006e62  call    cs:__imp_GetLastError
0x140006e68  mov     rcx, [rbp+arg_50]
0x140006e6f  mov     [rcx], eax
0x140006e71  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x140006e78  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x140006e7d  call    cs:__imp_RpcRevertToSelf
0x140006e83  jmp     short loc_140006E8E
0x140006e85  mov     rax, [rbp+arg_50]
0x140006e8c  mov     [rax], edx
0x140006e8e  mov     eax, [rbp+arg_30]
0x140006e91  add     rsp, 68h
0x140006e95  pop     r15
0x140006e97  pop     r14
0x140006e99  pop     r13
0x140006e9b  pop     r12
0x140006e9d  pop     rdi
0x140006e9e  pop     rsi
0x140006e9f  pop     rbx
0x140006ea0  pop     rbp
0x140006ea1  retn
```
