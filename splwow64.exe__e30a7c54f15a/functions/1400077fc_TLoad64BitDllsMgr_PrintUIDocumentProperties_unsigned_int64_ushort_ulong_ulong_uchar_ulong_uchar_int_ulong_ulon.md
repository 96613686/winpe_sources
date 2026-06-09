# TLoad64BitDllsMgr::PrintUIDocumentProperties(unsigned __int64,ushort *,ulong *,ulong *,uchar * *,ulong,uchar *,int,ulong,ulong,ulong *)

- ea: `0x1400077fc`
- end: `0x140007a95`
- name: `?PrintUIDocumentProperties@TLoad64BitDllsMgr@@QEAAJ_KPEAGPEAK2PEAPEAEKPEAEHKK2@Z`
- size: `665`
- prototype: `int(TLoad64BitDllsMgr *__hidden this, unsigned __int64, unsigned __int16 *, unsigned int *, unsigned int *, unsigned __int8 **, unsigned int, unsigned __int8 *, int, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000df00`

## callees

- `0x140001b9c`
- `0x140006894`
- `0x140007298`
- `0x1400077fc`
- `0x140007d00`
- `0x1400085d8`
- `0x140012e84`
- `0x140012f28`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400079d9`
- `KERNEL32!GetLastError` at `0x140007a34`
- `KERNEL32!GetLastError` at `0x140007a4e`
- `KERNEL32!GetLastError` at `0x1400079d9`
- `KERNEL32!GetLastError` at `0x140007a34`
- `KERNEL32!GetLastError` at `0x140007a4e`
- `KERNEL32!GetProcAddress` at `0x1400078d1`
- `KERNEL32!GetProcAddress` at `0x140007984`
- `KERNEL32!GetProcAddress` at `0x1400078d1`
- `KERNEL32!GetProcAddress` at `0x140007984`
- `KERNEL32!FreeLibrary` at `0x140007a1d`
- `KERNEL32!FreeLibrary` at `0x140007a46`
- `KERNEL32!FreeLibrary` at `0x140007a1d`
- `KERNEL32!FreeLibrary` at `0x140007a46`
- `KERNEL32!LoadLibraryExW` at `0x1400078b5`
- `KERNEL32!LoadLibraryExW` at `0x140007968`
- `KERNEL32!LoadLibraryExW` at `0x1400078b5`
- `KERNEL32!LoadLibraryExW` at `0x140007968`
- `WINSPOOL!OpenPrinterW` at `0x1400078ed`
- `WINSPOOL!OpenPrinterW` at `0x1400078ed`
- `WINSPOOL!ClosePrinter` at `0x140007a2c`
- `WINSPOOL!ClosePrinter` at `0x140007a2c`
- `RPCRT4!RpcRevertToSelf` at `0x140007a69`
- `RPCRT4!RpcRevertToSelf` at `0x140007a69`
- `RPCRT4!RpcImpersonateClient` at `0x140007848`
- `RPCRT4!RpcImpersonateClient` at `0x140007848`

## string_xrefs

- `0x140007871`: `TLoad64BitDllsMgr::PrintUIDocumentProperties`
- `0x14000795e`: `printui.dll`

## pseudocode

```c
__int64 __fastcall TLoad64BitDllsMgr::PrintUIDocumentProperties(
        TLoad64BitDllsMgr *this,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned __int8 **a6,
        unsigned int a7,
        unsigned __int8 *a8,
        int a9,
        unsigned int a10,
        unsigned int a11,
        unsigned int *a12)
{
  TLoad64BitDllsMgr *v12; // rbx
  unsigned int v14; // r13d
  RPC_STATUS v15; // eax
  const unsigned __int16 *v16; // rdx
  NSecurityLibrary *v17; // rcx
  HMODULE Library; // rax
  HMODULE v19; // rdi
  FARPROC ProcAddress; // rbx
  unsigned __int8 *v21; // rcx
  unsigned int v22; // eax
  unsigned __int8 **v23; // r12
  unsigned int *v24; // r14
  HMODULE v25; // rax
  HMODULE v26; // rbx
  FARPROC v27; // r15
  unsigned __int8 *v28; // rcx
  int v29; // r9d
  _OWORD v31[3]; // [rsp+40h] [rbp-30h] BYREF
  HANDLE phPrinter; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v33; // [rsp+B8h] [rbp+48h]
  unsigned int *v34; // [rsp+C8h] [rbp+58h]

  v34 = a4;
  v33 = a2;
  v12 = pGLdrObj;
  phPrinter = 0;
  memset(v31, 0, sizeof(v31));
  v14 = -1;
  v15 = RpcImpersonateClient(0);
  if ( v15 )
  {
    *a12 = v15;
  }
  else
  {
    if ( !NSecurityLibrary::IsClientAppContainer(0) || NSecurityLibrary::HasCapability(v17, v16) )
    {
      TLoad64BitDllsMgr::RefreshLifeSpan(v12);
      TLoad64BitDllsMgr::IncUIRefCnt(pGLdrObj);
      Library = LoadLibraryExW(L"winspool.drv", 0, 0x800u);
      v19 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "DocumentPropertySheets");
        if ( ProcAddress && OpenPrinterW(a3, &phPrinter, 0) )
        {
          *((_QWORD *)&v31[0] + 1) = phPrinter;
          LODWORD(v31[0]) = 48;
          *(_QWORD *)&v31[1] = a3;
          if ( a9 )
          {
            HIDWORD(v31[2]) = 0;
            *(_OWORD *)((char *)&v31[1] + 8) = 0;
            DWORD2(v31[2]) = ((__int64 (__fastcall *)(_QWORD, _OWORD *))ProcAddress)(0, v31);
            v21 = (unsigned __int8 *)operator new[](DWORD2(v31[2]));
            v22 = DWORD2(v31[2]);
          }
          else
          {
            v22 = 0;
            DWORD2(v31[2]) = 0;
            v21 = 0;
          }
          v23 = a6;
          v24 = a5;
          *a6 = v21;
          *v24 = v22;
          v25 = LoadLibraryExW(L"printui.dll", 0, 0x800u);
          v26 = v25;
          if ( v25 )
          {
            v27 = GetProcAddress(v25, "DocumentPropertiesWrap");
            if ( v27 )
            {
              TLoad64BitDllsMgr::IncUIRefCnt(pGLdrObj);
              v14 = ((__int64 (__fastcall *)(__int64, HANDLE, unsigned __int16 *, unsigned __int8 *, unsigned __int8 *, unsigned int, unsigned int))v27)(
                      v33,
                      phPrinter,
                      a3,
                      *v23,
                      a8,
                      a10,
                      a11);
              *a12 = GetLastError();
              TLoad64BitDllsMgr::DecUIRefCnt(pGLdrObj);
              if ( *v23 )
              {
                v29 = *v24;
                v28 = *v23;
                if ( *((unsigned __int16 *)v28 + 34) + (unsigned int)*((unsigned __int16 *)v28 + 35) < *v24 )
                  v29 = *((unsigned __int16 *)v28 + 34) + *((unsigned __int16 *)v28 + 35);
                *v34 = v29;
              }
            }
            FreeLibrary(v26);
          }
          if ( phPrinter )
            ClosePrinter(phPrinter);
        }
        else
        {
          *a12 = GetLastError();
        }
        FreeLibrary(v19);
      }
      else
      {
        *a12 = GetLastError();
      }
      TLoad64BitDllsMgr::DecUIRefCnt(pGLdrObj);
    }
    else
    {
      SplWow64Telemetry::WriteDbgTraceError("TLoad64BitDllsMgr::PrintUIDocumentProperties", L"called from AppContainer");
      *a12 = 5;
    }
    RpcRevertToSelf();
  }
  return v14;
}

```

## disassembly

```asm
0x1400077fc  mov     rax, rsp
0x1400077ff  mov     [rax+18h], rbx
0x140007803  mov     [rax+20h], r9
0x140007807  mov     [rax+10h], rdx
0x14000780b  mov     [rax+8], rcx
0x14000780f  push    rbp
0x140007810  push    rsi
0x140007811  push    rdi
0x140007812  push    r12
0x140007814  push    r13
0x140007816  push    r14
0x140007818  push    r15
0x14000781a  mov     rbp, rsp
0x14000781d  sub     rsp, 70h
0x140007821  mov     rbx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; TLoad64BitDllsMgr * pGLdrObj
0x140007828  xorps   xmm0, xmm0
0x14000782b  xor     ecx, ecx; BindingHandle
0x14000782d  mov     [rbp+phPrinter], 0
0x140007835  movups  [rbp+var_30], xmm0
0x140007839  mov     rsi, r8
0x14000783c  or      r13d, 0FFFFFFFFh
0x140007840  movups  [rbp+var_20], xmm0
0x140007844  movups  [rbp+var_10], xmm0
0x140007848  call    cs:__imp_RpcImpersonateClient
0x14000784e  mov     ecx, eax; this
0x140007850  test    eax, eax
0x140007852  jnz     loc_140007A71
0x140007858  call    ?IsClientAppContainer@NSecurityLibrary@@YA_NXZ; NSecurityLibrary::IsClientAppContainer(void)
0x14000785d  test    al, al
0x14000785f  jz      short loc_14000788F
0x140007861  call    ?HasCapability@NSecurityLibrary@@YA_NPEBG@Z; NSecurityLibrary::HasCapability(ushort const *)
0x140007866  test    al, al
0x140007868  jnz     short loc_14000788F
0x14000786a  lea     rdx, aCalledFromAppc; "called from AppContainer"
0x140007871  lea     rcx, aTload64bitdlls_6; "TLoad64BitDllsMgr::PrintUIDocumentPrope"...
0x140007878  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000787d  mov     rax, [rbp+arg_58]
0x140007884  mov     dword ptr [rax], 5
0x14000788a  jmp     loc_140007A69
0x14000788f  mov     rcx, rbx; this
0x140007892  call    ?RefreshLifeSpan@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::RefreshLifeSpan(void)
0x140007897  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000789e  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x1400078a3  mov     r15d, 800h
0x1400078a9  lea     rcx, LibFileName; "winspool.drv"
0x1400078b0  mov     r8d, r15d; dwFlags
0x1400078b3  xor     edx, edx; hFile
0x1400078b5  call    cs:__imp_LoadLibraryExW
0x1400078bb  mov     rdi, rax
0x1400078be  test    rax, rax
0x1400078c1  jz      loc_140007A4E
0x1400078c7  lea     rdx, aDocumentproper_0; "DocumentPropertySheets"
0x1400078ce  mov     rcx, rax; hModule
0x1400078d1  call    cs:__imp_GetProcAddress
0x1400078d7  mov     rbx, rax
0x1400078da  test    rax, rax
0x1400078dd  jz      loc_140007A34
0x1400078e3  xor     r8d, r8d; pDefault
0x1400078e6  lea     rdx, [rbp+phPrinter]; phPrinter
0x1400078ea  mov     rcx, rsi; pPrinterName
0x1400078ed  call    cs:__imp_OpenPrinterW
0x1400078f3  test    eax, eax
0x1400078f5  jz      loc_140007A34
0x1400078fb  cmp     [rbp+arg_40], 0
0x140007902  mov     rax, [rbp+phPrinter]
0x140007906  mov     qword ptr [rbp+var_30+8], rax
0x14000790a  mov     dword ptr [rbp+var_30], 30h ; '0'
0x140007911  mov     qword ptr [rbp+var_20], rsi
0x140007915  jz      short loc_140007946
0x140007917  xorps   xmm0, xmm0
0x14000791a  mov     dword ptr [rbp+var_10+0Ch], 0
0x140007921  lea     rdx, [rbp+var_30]
0x140007925  xor     ecx, ecx
0x140007927  mov     rax, rbx
0x14000792a  movdqu  [rbp+var_20+8], xmm0
0x14000792f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007934  mov     ecx, eax; unsigned __int64
0x140007936  mov     dword ptr [rbp+var_10+8], ecx
0x140007939  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000793e  mov     rcx, rax
0x140007941  mov     eax, dword ptr [rbp+var_10+8]
0x140007944  jmp     short loc_14000794D
0x140007946  xor     eax, eax
0x140007948  mov     dword ptr [rbp+var_10+8], eax
0x14000794b  xor     ecx, ecx
0x14000794d  mov     r12, [rbp+arg_28]
0x140007951  mov     r8d, r15d; dwFlags
0x140007954  mov     r14, [rbp+arg_20]
0x140007958  xor     edx, edx; hFile
0x14000795a  mov     [r12], rcx
0x14000795e  lea     rcx, aPrintuiDll; "printui.dll"
0x140007965  mov     [r14], eax
0x140007968  call    cs:__imp_LoadLibraryExW
0x14000796e  mov     rbx, rax
0x140007971  test    rax, rax
0x140007974  jz      loc_140007A23
0x14000797a  lea     rdx, aDocumentproper; "DocumentPropertiesWrap"
0x140007981  mov     rcx, rax; hModule
0x140007984  call    cs:__imp_GetProcAddress
0x14000798a  mov     r15, rax
0x14000798d  test    rax, rax
0x140007990  jz      loc_140007A1A
0x140007996  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000799d  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x1400079a2  mov     eax, [rbp+arg_50]
0x1400079a8  mov     r8, rsi
0x1400079ab  mov     r9, [r12]
0x1400079af  mov     rdx, [rbp+phPrinter]
0x1400079b3  mov     rcx, [rbp+arg_8]
0x1400079b7  mov     [rsp+70h+var_40], eax
0x1400079bb  mov     eax, [rbp+arg_48]
0x1400079c1  mov     [rsp+70h+var_48], eax
0x1400079c5  mov     rax, [rbp+arg_38]
0x1400079c9  mov     [rsp+70h+var_50], rax
0x1400079ce  mov     rax, r15
0x1400079d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400079d6  mov     r13d, eax
0x1400079d9  call    cs:__imp_GetLastError
0x1400079df  mov     rcx, [rbp+arg_58]
0x1400079e6  mov     [rcx], eax
0x1400079e8  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x1400079ef  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x1400079f4  mov     rcx, [r12]
0x1400079f8  test    rcx, rcx
0x1400079fb  jz      short loc_140007A1A
0x1400079fd  movzx   r8d, word ptr [rcx+46h]
0x140007a02  mov     r9d, [r14]
0x140007a05  movzx   ecx, word ptr [rcx+44h]
0x140007a09  mov     rax, [rbp+arg_18]
0x140007a0d  add     r8d, ecx
0x140007a10  cmp     r8d, r9d
0x140007a13  cmovb   r9d, r8d
0x140007a17  mov     [rax], r9d
0x140007a1a  mov     rcx, rbx; hLibModule
0x140007a1d  call    cs:__imp_FreeLibrary
0x140007a23  mov     rcx, [rbp+phPrinter]; hPrinter
0x140007a27  test    rcx, rcx
0x140007a2a  jz      short loc_140007A43
0x140007a2c  call    cs:__imp_ClosePrinter
0x140007a32  jmp     short loc_140007A43
0x140007a34  call    cs:__imp_GetLastError
0x140007a3a  mov     rcx, [rbp+arg_58]
0x140007a41  mov     [rcx], eax
0x140007a43  mov     rcx, rdi; hLibModule
0x140007a46  call    cs:__imp_FreeLibrary
0x140007a4c  jmp     short loc_140007A5D
0x140007a4e  call    cs:__imp_GetLastError
0x140007a54  mov     rcx, [rbp+arg_58]
0x140007a5b  mov     [rcx], eax
0x140007a5d  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x140007a64  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x140007a69  call    cs:__imp_RpcRevertToSelf
0x140007a6f  jmp     short loc_140007A7A
0x140007a71  mov     rax, [rbp+arg_58]
0x140007a78  mov     [rax], ecx
0x140007a7a  mov     rbx, [rsp+70h+arg_10]
0x140007a82  mov     eax, r13d
0x140007a85  add     rsp, 70h
0x140007a89  pop     r15
0x140007a8b  pop     r14
0x140007a8d  pop     r13
0x140007a8f  pop     r12
0x140007a91  pop     rdi
0x140007a92  pop     rsi
0x140007a93  pop     rbp
0x140007a94  retn
```
