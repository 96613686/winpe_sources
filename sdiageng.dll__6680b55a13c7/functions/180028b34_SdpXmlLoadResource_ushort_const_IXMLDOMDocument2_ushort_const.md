# SdpXmlLoadResource(ushort const *,IXMLDOMDocument2 * *,ushort const *)

- ea: `0x180028b34`
- end: `0x180028f1b`
- name: `?SdpXmlLoadResource@@YAJPEBGPEAPEAUIXMLDOMDocument2@@0@Z`
- size: `999`
- prototype: `__int64 __fastcall(LPCWSTR lpName, LPVOID *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800176dc`
- `0x1800217ac`

## callees

- `0x180001ca6`
- `0x180026fa0`
- `0x180028b34`
- `0x18002a010`

## import_xrefs

- `KERNEL32!LoadResource` at `0x180028c84`
- `KERNEL32!LoadResource` at `0x180028c84`
- `KERNEL32!FindResourceExW` at `0x180028c67`
- `KERNEL32!FindResourceExW` at `0x180028c67`
- `KERNEL32!GlobalFree` at `0x180028ec0`
- `KERNEL32!GlobalFree` at `0x180028ec0`
- `KERNEL32!GlobalAlloc` at `0x180028cef`
- `KERNEL32!GlobalAlloc` at `0x180028cef`
- `KERNEL32!LockResource` at `0x180028c9a`
- `KERNEL32!LockResource` at `0x180028c9a`
- `KERNEL32!SizeofResource` at `0x180028cbf`
- `KERNEL32!SizeofResource` at `0x180028cbf`
- `KERNEL32!GlobalLock` at `0x180028d09`
- `KERNEL32!GlobalLock` at `0x180028d09`
- `KERNEL32!GlobalUnlock` at `0x180028e40`
- `KERNEL32!GlobalUnlock` at `0x180028e40`
- `KERNEL32!GetLastError` at `0x180028c39`
- `KERNEL32!GetLastError` at `0x180028cc9`
- `KERNEL32!GetLastError` at `0x180028e02`
- `KERNEL32!GetLastError` at `0x180028e48`
- `KERNEL32!GetLastError` at `0x180028e62`
- `KERNEL32!GetLastError` at `0x180028e7c`
- `KERNEL32!GetLastError` at `0x180028c39`
- `KERNEL32!GetLastError` at `0x180028cc9`
- `KERNEL32!GetLastError` at `0x180028e02`
- `KERNEL32!GetLastError` at `0x180028e48`
- `KERNEL32!GetLastError` at `0x180028e62`
- `KERNEL32!GetLastError` at `0x180028e7c`
- `KERNEL32!GetModuleHandleExW` at `0x180028c29`
- `KERNEL32!GetModuleHandleExW` at `0x180028c29`
- `ole32!CreateStreamOnHGlobal` at `0x180028d3a`
- `ole32!CreateStreamOnHGlobal` at `0x180028d3a`
- `ole32!CoCreateInstance` at `0x180028bd6`
- `ole32!CoCreateInstance` at `0x180028bd6`
- `OLEAUT32!__imp_VariantInit` at `0x180028b81`
- `OLEAUT32!__imp_VariantInit` at `0x180028b81`
- `OLEAUT32!__imp_VariantClear` at `0x180028eca`
- `OLEAUT32!__imp_VariantClear` at `0x180028eca`

## string_xrefs

- `0x180028d4f`: `SdpXmlLoadResource`
- `0x180028e16`: `SdpXmlLoadResource`
- `0x180028ea1`: `SdpXmlLoadResource`

## pseudocode

```c
__int64 __fastcall SdpXmlLoadResource(LPCWSTR lpName, LPVOID *a2, const unsigned __int16 *a3)
{
  void *v6; // rdi
  int v7; // r9d
  unsigned int v8; // r8d
  signed int v9; // ebx
  HRESULT v10; // eax
  int v11; // eax
  signed int LastError; // eax
  HRSRC Resource; // rbx
  char *v14; // rcx
  const void *v15; // r14
  DWORD v16; // eax
  signed int v17; // eax
  DWORD v18; // ebx
  char *v19; // rax
  char *v20; // rax
  char *v21; // rsi
  HRESULT v22; // eax
  unsigned int v23; // r8d
  __int64 (__fastcall *v24)(LPVOID, __int128 *, __int16 *); // rax
  LPVOID v25; // rcx
  signed int v26; // eax
  signed int v27; // eax
  signed int v28; // eax
  signed int v29; // eax
  LPVOID ppv; // [rsp+30h] [rbp-50h] BYREF
  HMODULE phModule; // [rsp+38h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-40h] BYREF
  __int128 v34; // [rsp+60h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+70h] [rbp-10h]
  __int16 v36; // [rsp+C0h] [rbp+40h] BYREF
  LPSTREAM ppstm; // [rsp+D8h] [rbp+58h] BYREF

  phModule = 0;
  v36 = -1;
  ppv = 0;
  ppstm = 0;
  v6 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !lpName )
  {
    v7 = -2147024809;
    v8 = 606;
    v9 = -2147024809;
LABEL_52:
    SdpDebugTrace(1u, L"SdpXmlLoadResource", v8, v7);
    goto LABEL_53;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    v8 = 607;
    v9 = -2147024809;
    goto LABEL_52;
  }
  v10 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x15u, &IID_IXMLDOMDocument2, &ppv);
  v9 = v10;
  if ( v10 < 0 )
  {
    v7 = v10;
    v8 = 617;
    goto LABEL_52;
  }
  v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  v9 = v11;
  if ( v11 < 0 )
  {
    v7 = v11;
    v8 = 620;
    goto LABEL_52;
  }
  if ( !GetModuleHandleExW(2u, L"sdiageng", &phModule) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
    {
      v8 = 628;
LABEL_51:
      v7 = v9;
      goto LABEL_52;
    }
  }
  Resource = FindResourceExW(phModule, a3, lpName, 0);
  if ( (unsigned __int64)Resource - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v29 = GetLastError();
    v9 = v29;
    if ( v29 > 0 )
      v9 = (unsigned __int16)v29 | 0x80070000;
    v8 = 637;
    goto LABEL_49;
  }
  v14 = (char *)LoadResource(phModule, Resource);
  if ( (unsigned __int64)(v14 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v28 = GetLastError();
    v9 = v28;
    if ( v28 > 0 )
      v9 = (unsigned __int16)v28 | 0x80070000;
    v8 = 643;
    goto LABEL_49;
  }
  v15 = LockResource(v14);
  if ( !v15 )
  {
    v9 = -2147467261;
    v8 = 649;
    goto LABEL_51;
  }
  v16 = SizeofResource(phModule, Resource);
  if ( !v16 )
  {
    v17 = GetLastError();
    v9 = v17;
    if ( v17 > 0 )
      v9 = (unsigned __int16)v17 | 0x80070000;
    v8 = 655;
LABEL_49:
    if ( v9 >= 0 )
      v9 = -2147467259;
    goto LABEL_51;
  }
  v18 = v16;
  v19 = (char *)GlobalAlloc(2u, v16);
  v6 = v19;
  if ( (unsigned __int64)(v19 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v27 = GetLastError();
    v9 = v27;
    if ( v27 > 0 )
      v9 = (unsigned __int16)v27 | 0x80070000;
    v8 = 658;
    goto LABEL_49;
  }
  v20 = (char *)GlobalLock(v19);
  v21 = v20;
  if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    memcpy_0(v20, v15, v18);
    v22 = CreateStreamOnHGlobal(v6, 1, &ppstm);
    v9 = v22;
    if ( v22 >= 0 )
    {
      v22 = (**(__int64 (__fastcall ***)(LPSTREAM, GUID *, ULONG *))ppstm)(ppstm, &IID_IUnknown, (ULONG *)&pvarg.cyVal);
      v9 = v22;
      if ( v22 >= 0 )
      {
        pRecInfo = pvarg.pRecInfo;
        pvarg.vt = 13;
        v24 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int16 *))(*(_QWORD *)ppv + 464LL);
        v34 = *(_OWORD *)&pvarg.vt;
        v22 = v24(ppv, &v34, &v36);
        v9 = v22;
        if ( v22 >= 0 )
        {
          if ( v36 )
          {
            v25 = ppv;
            *a2 = ppv;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 8LL))(v25);
            goto LABEL_39;
          }
          v22 = -2147467259;
          v23 = 681;
          v9 = -2147467259;
        }
        else
        {
          v23 = 680;
        }
      }
      else
      {
        v23 = 675;
      }
    }
    else
    {
      v23 = 669;
    }
    SdpDebugTrace(1u, L"SdpXmlLoadResource", v23, v22);
LABEL_39:
    GlobalUnlock(v6);
    goto LABEL_53;
  }
  v26 = GetLastError();
  v9 = v26;
  if ( v26 > 0 )
    v9 = (unsigned __int16)v26 | 0x80070000;
  if ( v9 >= 0 )
    v9 = -2147467259;
  SdpDebugTrace(1u, L"SdpXmlLoadResource", 0x295u, v9);
  if ( v21 )
    goto LABEL_39;
LABEL_53:
  if ( !ppstm && v6 )
    GlobalFree(v6);
  VariantClear(&pvarg);
  if ( ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180028b34  mov     [rsp-38h+arg_8], rbx
0x180028b39  push    rbp
0x180028b3a  push    rsi
0x180028b3b  push    rdi
0x180028b3c  push    r12
0x180028b3e  push    r13
0x180028b40  push    r14
0x180028b42  push    r15
0x180028b44  mov     rbp, rsp
0x180028b47  sub     rsp, 80h
0x180028b4e  xor     r12d, r12d
0x180028b51  xor     eax, eax
0x180028b53  mov     qword ptr [rbp+pvarg+10h], rax
0x180028b57  mov     rsi, rcx
0x180028b5a  or      eax, 0FFFFFFFFh
0x180028b5d  mov     [rbp+phModule], r12
0x180028b61  xorps   xmm0, xmm0
0x180028b64  mov     [rbp+arg_0], ax
0x180028b68  lea     rcx, [rbp+pvarg]; pvarg
0x180028b6c  mov     [rbp+var_50], r12
0x180028b70  mov     r14, r8
0x180028b73  mov     [rbp+ppstm], r12
0x180028b77  mov     r15, rdx
0x180028b7a  mov     edi, r12d
0x180028b7d  movups  xmmword ptr [rbp+pvarg], xmm0
0x180028b81  call    cs:__imp_VariantInit
0x180028b87  test    rsi, rsi
0x180028b8a  jnz     short loc_180028BA0
0x180028b8c  mov     r9d, 80070057h
0x180028b92  mov     r8d, 25Eh
0x180028b98  mov     ebx, r9d
0x180028b9b  jmp     loc_180028EA1
0x180028ba0  test    r15, r15
0x180028ba3  jnz     short loc_180028BB9
0x180028ba5  mov     r9d, 80070057h
0x180028bab  mov     r8d, 25Fh
0x180028bb1  mov     ebx, r9d
0x180028bb4  jmp     loc_180028EA1
0x180028bb9  xor     edx, edx; pUnkOuter
0x180028bbb  lea     rax, [rbp+var_50]
0x180028bbf  lea     r9, IID_IXMLDOMDocument2; riid
0x180028bc6  mov     [rsp+80h+ppv], rax; ppv
0x180028bcb  lea     rcx, CLSID_DOMDocument60; rclsid
0x180028bd2  lea     r8d, [rdx+15h]; dwClsContext
0x180028bd6  call    cs:__imp_CoCreateInstance
0x180028bdc  mov     ebx, eax
0x180028bde  test    eax, eax
0x180028be0  jns     short loc_180028BF0
0x180028be2  mov     r9d, eax
0x180028be5  mov     r8d, 269h
0x180028beb  jmp     loc_180028EA1
0x180028bf0  mov     rcx, [rbp+var_50]
0x180028bf4  xor     edx, edx
0x180028bf6  mov     rax, [rcx]
0x180028bf9  mov     rax, [rax+1F8h]
0x180028c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c05  mov     ebx, eax
0x180028c07  test    eax, eax
0x180028c09  jns     short loc_180028C19
0x180028c0b  mov     r9d, eax
0x180028c0e  mov     r8d, 26Ch
0x180028c14  jmp     loc_180028EA1
0x180028c19  lea     r8, [rbp+phModule]; phModule
0x180028c1d  mov     ecx, 2; dwFlags
0x180028c22  lea     rdx, ModuleName; "sdiageng"
0x180028c29  call    cs:__imp_GetModuleHandleExW
0x180028c2f  mov     r13d, 80070000h
0x180028c35  test    eax, eax
0x180028c37  jnz     short loc_180028C5A
0x180028c39  call    cs:__imp_GetLastError
0x180028c3f  mov     ebx, eax
0x180028c41  test    eax, eax
0x180028c43  jle     short loc_180028C4B
0x180028c45  movzx   ebx, ax
0x180028c48  or      ebx, r13d
0x180028c4b  test    ebx, ebx
0x180028c4d  jns     short loc_180028C5A
0x180028c4f  mov     r8d, 274h
0x180028c55  jmp     loc_180028E9E
0x180028c5a  mov     rcx, [rbp+phModule]; hModule
0x180028c5e  xor     r9d, r9d; wLanguage
0x180028c61  mov     r8, rsi; lpName
0x180028c64  mov     rdx, r14; lpType
0x180028c67  call    cs:__imp_FindResourceExW
0x180028c6d  mov     rbx, rax
0x180028c70  dec     rax
0x180028c73  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028c77  ja      loc_180028E7C
0x180028c7d  mov     rcx, [rbp+phModule]; hModule
0x180028c81  mov     rdx, rbx; hResInfo
0x180028c84  call    cs:__imp_LoadResource
0x180028c8a  mov     rcx, rax; hResData
0x180028c8d  dec     rax
0x180028c90  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028c94  ja      loc_180028E62
0x180028c9a  call    cs:__imp_LockResource
0x180028ca0  mov     r14, rax
0x180028ca3  test    rax, rax
0x180028ca6  jnz     short loc_180028CB8
0x180028ca8  mov     ebx, 80004003h
0x180028cad  mov     r8d, 289h
0x180028cb3  jmp     loc_180028E9E
0x180028cb8  mov     rcx, [rbp+phModule]; hModule
0x180028cbc  mov     rdx, rbx; hResInfo
0x180028cbf  call    cs:__imp_SizeofResource
0x180028cc5  test    eax, eax
0x180028cc7  jnz     short loc_180028CE6
0x180028cc9  call    cs:__imp_GetLastError
0x180028ccf  mov     ebx, eax
0x180028cd1  test    eax, eax
0x180028cd3  jle     short loc_180028CDB
0x180028cd5  movzx   ebx, ax
0x180028cd8  or      ebx, r13d
0x180028cdb  mov     r8d, 28Fh
0x180028ce1  jmp     loc_180028E94
0x180028ce6  mov     edx, eax; dwBytes
0x180028ce8  mov     ecx, 2; uFlags
0x180028ced  mov     ebx, eax
0x180028cef  call    cs:__imp_GlobalAlloc
0x180028cf5  mov     rdi, rax
0x180028cf8  lea     rcx, [rax-1]
0x180028cfc  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180028d00  ja      loc_180028E48
0x180028d06  mov     rcx, rax; hMem
0x180028d09  call    cs:__imp_GlobalLock
0x180028d0f  mov     rsi, rax
0x180028d12  lea     rcx, [rax-1]
0x180028d16  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180028d1a  ja      loc_180028E02
0x180028d20  mov     r8d, ebx; Size
0x180028d23  mov     rdx, r14; Src
0x180028d26  mov     rcx, rax; void *
0x180028d29  call    memcpy_0
0x180028d2e  lea     r8, [rbp+ppstm]; ppstm
0x180028d32  mov     edx, 1; fDeleteOnRelease
0x180028d37  mov     rcx, rdi; hGlobal
0x180028d3a  call    cs:__imp_CreateStreamOnHGlobal
0x180028d40  mov     ebx, eax
0x180028d42  test    eax, eax
0x180028d44  jns     short loc_180028D65
0x180028d46  mov     r8d, 29Dh; int
0x180028d4c  mov     r9d, eax; int
0x180028d4f  lea     rdx, aSdpxmlloadreso; "SdpXmlLoadResource"
0x180028d56  mov     ecx, 1; Level
0x180028d5b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180028d60  jmp     loc_180028E3D
0x180028d65  mov     rcx, [rbp+ppstm]
0x180028d69  lea     r8, [rbp+pvarg+8]
0x180028d6d  lea     rdx, IID_IUnknown
0x180028d74  mov     rax, [rcx]
0x180028d77  mov     rax, [rax]
0x180028d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d7f  mov     ebx, eax
0x180028d81  test    eax, eax
0x180028d83  jns     short loc_180028D8D
0x180028d85  mov     r8d, 2A3h
0x180028d8b  jmp     short loc_180028D4C
0x180028d8d  mov     rcx, [rbp+var_50]
0x180028d91  lea     r8, [rbp+arg_0]
0x180028d95  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180028d9a  lea     rdx, [rbp+var_20]
0x180028d9e  mov     eax, 0Dh
0x180028da3  movsd   [rbp+var_10], xmm1
0x180028da8  mov     word ptr [rbp+pvarg], ax
0x180028dac  mov     rax, [rcx]
0x180028daf  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180028db3  mov     rax, [rax+1D0h]
0x180028dba  movaps  [rbp+var_20], xmm0
0x180028dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028dc3  mov     ebx, eax
0x180028dc5  test    eax, eax
0x180028dc7  jns     short loc_180028DD4
0x180028dc9  mov     r8d, 2A8h
0x180028dcf  jmp     loc_180028D4C
0x180028dd4  cmp     [rbp+arg_0], r12w
0x180028dd9  jnz     short loc_180028DED
0x180028ddb  mov     eax, 80004005h
0x180028de0  mov     r8d, 2A9h
0x180028de6  mov     ebx, eax
0x180028de8  jmp     loc_180028D4C
0x180028ded  mov     rcx, [rbp+var_50]
0x180028df1  mov     [r15], rcx
0x180028df4  mov     rax, [rcx]
0x180028df7  mov     rax, [rax+8]
0x180028dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e00  jmp     short loc_180028E3D
0x180028e02  call    cs:__imp_GetLastError
0x180028e08  mov     ebx, eax
0x180028e0a  test    eax, eax
0x180028e0c  jle     short loc_180028E14
0x180028e0e  movzx   ebx, ax
0x180028e11  or      ebx, r13d
0x180028e14  test    ebx, ebx
0x180028e16  lea     rdx, aSdpxmlloadreso; "SdpXmlLoadResource"
0x180028e1d  mov     eax, 80004005h
0x180028e22  mov     r8d, 295h; int
0x180028e28  cmovns  ebx, eax
0x180028e2b  mov     ecx, 1; Level
0x180028e30  mov     r9d, ebx; int
0x180028e33  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180028e38  test    rsi, rsi
0x180028e3b  jz      short loc_180028EB2
0x180028e3d  mov     rcx, rdi; hMem
0x180028e40  call    cs:__imp_GlobalUnlock
0x180028e46  jmp     short loc_180028EB2
0x180028e48  call    cs:__imp_GetLastError
0x180028e4e  mov     ebx, eax
0x180028e50  test    eax, eax
0x180028e52  jle     short loc_180028E5A
0x180028e54  movzx   ebx, ax
0x180028e57  or      ebx, r13d
0x180028e5a  mov     r8d, 292h
0x180028e60  jmp     short loc_180028E94
0x180028e62  call    cs:__imp_GetLastError
0x180028e68  mov     ebx, eax
0x180028e6a  test    eax, eax
0x180028e6c  jle     short loc_180028E74
0x180028e6e  movzx   ebx, ax
0x180028e71  or      ebx, r13d
0x180028e74  mov     r8d, 283h
0x180028e7a  jmp     short loc_180028E94
0x180028e7c  call    cs:__imp_GetLastError
0x180028e82  mov     ebx, eax
0x180028e84  test    eax, eax
0x180028e86  jle     short loc_180028E8E
0x180028e88  movzx   ebx, ax
0x180028e8b  or      ebx, r13d
0x180028e8e  mov     r8d, 27Dh; int
0x180028e94  test    ebx, ebx
0x180028e96  mov     eax, 80004005h
0x180028e9b  cmovns  ebx, eax
0x180028e9e  mov     r9d, ebx; int
0x180028ea1  lea     rdx, aSdpxmlloadreso; "SdpXmlLoadResource"
0x180028ea8  mov     ecx, 1; Level
0x180028ead  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180028eb2  cmp     [rbp+ppstm], r12
0x180028eb6  jnz     short loc_180028EC6
0x180028eb8  test    rdi, rdi
0x180028ebb  jz      short loc_180028EC6
0x180028ebd  mov     rcx, rdi; hMem
0x180028ec0  call    cs:__imp_GlobalFree
0x180028ec6  lea     rcx, [rbp+pvarg]; pvarg
0x180028eca  call    cs:__imp_VariantClear
0x180028ed0  mov     rcx, [rbp+ppstm]
0x180028ed4  test    rcx, rcx
0x180028ed7  jz      short loc_180028EE9
0x180028ed9  mov     rax, [rcx]
0x180028edc  mov     rax, [rax+10h]
0x180028ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ee5  mov     [rbp+ppstm], r12
0x180028ee9  mov     rcx, [rbp+var_50]
0x180028eed  test    rcx, rcx
0x180028ef0  jz      short loc_180028EFE
0x180028ef2  mov     rax, [rcx]
0x180028ef5  mov     rax, [rax+10h]
0x180028ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028efe  mov     eax, ebx
0x180028f00  mov     rbx, [rsp+80h+arg_8]
0x180028f08  add     rsp, 80h
0x180028f0f  pop     r15
0x180028f11  pop     r14
0x180028f13  pop     r13
0x180028f15  pop     r12
0x180028f17  pop     rdi
0x180028f18  pop     rsi
0x180028f19  pop     rbp
0x180028f1a  retn
```
