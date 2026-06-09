# HrWrappedCreateAccountManager(IImnAccountManager3 * *)

- ea: `0x180028314`
- end: `0x1800285ad`
- name: `?HrWrappedCreateAccountManager@@YAJPEAPEAUIImnAccountManager3@@@Z`
- size: `665`
- prototype: `__int64 __fastcall(struct IImnAccountManager3 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800285b4`

## callees

- `0x1800045e4`
- `0x18001d778`
- `0x180028314`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180028413`
- `ADVAPI32!RegOpenKeyExW` at `0x180028413`
- `ADVAPI32!RegCloseKey` at `0x180028581`
- `ADVAPI32!RegCloseKey` at `0x180028581`
- `ADVAPI32!RegQueryValueExW` at `0x18002844a`
- `ADVAPI32!RegQueryValueExW` at `0x18002844a`
- `KERNEL32!LoadLibraryW` at `0x180028498`
- `KERNEL32!LoadLibraryW` at `0x180028498`
- `KERNEL32!GetProcAddress` at `0x1800284b4`
- `KERNEL32!GetProcAddress` at `0x1800284b4`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002846a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002846a`
- `ole32!CoGetMalloc` at `0x180028545`
- `ole32!CoGetMalloc` at `0x180028545`
- `ole32!StringFromCLSID` at `0x180028395`
- `ole32!StringFromCLSID` at `0x180028395`
- `ole32!CoCreateInstance` at `0x180028522`
- `ole32!CoCreateInstance` at `0x180028522`

## string_xrefs

- `0x1800283bb`: `CLSID\`
- `0x1800284aa`: `HrCreateAccountManager`

## pseudocode

```c
__int64 __fastcall HrWrappedCreateAccountManager(struct IImnAccountManager3 **a1)
{
  LSTATUS v2; // ebx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  HRESULT Instance; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v9; // [rsp+40h] [rbp-C0h] BYREF
  LPMALLOC ppMalloc; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Data[264]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v14[264]; // [rsp+480h] [rbp+380h] BYREF
  WCHAR Dst[264]; // [rsp+690h] [rbp+590h] BYREF

  v9 = 0;
  lpsz = 0;
  cbData = 261;
  Type = 0;
  hKey = 0;
  if ( qword_1800ACC40 )
    return 1247;
  g_lpAccountManager = 0;
  if ( StringFromCLSID(&CLSID_ImnAccountManager, &lpsz) < 0 )
    goto LABEL_13;
  StringCchCopyW(v14, 0x104u, lpsz);
  StringCchCopyW(SubKey, 0x104u, L"CLSID\\");
  StringCchCatW(SubKey, 0x104u, v14);
  StringCchCatW(SubKey, 0x104u, L"\\InprocServer32");
  if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 1u, &hKey) )
    goto LABEL_13;
  cbData = 260;
  v2 = RegQueryValueExW(hKey, 0, 0, &Type, (LPBYTE)Data, &cbData);
  if ( Type == 2 )
  {
    if ( !ExpandEnvironmentStringsW(Data, Dst, 0x104u) )
      goto LABEL_13;
    StringCchCopyW(Data, 0x104u, Dst);
  }
  if ( !v2 )
  {
    LibraryW = LoadLibraryW(Data);
    qword_1800ACC40 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "HrCreateAccountManager");
      if ( ProcAddress )
      {
        Instance = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v9);
        if ( Instance >= 0 )
        {
          Instance = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IImnAccountManager3 ***))v9)(
                       v9,
                       &IID_IImnAccountManager2,
                       &g_lpAccountManager);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        goto LABEL_14;
      }
    }
  }
LABEL_13:
  Instance = CoCreateInstance(&CLSID_ImnAccountManager, 0, 1u, &IID_IImnAccountManager2, (LPVOID *)&g_lpAccountManager);
LABEL_14:
  if ( lpsz )
  {
    ppMalloc = 0;
    CoGetMalloc(1u, &ppMalloc);
    if ( ppMalloc )
    {
      ((void (__fastcall *)(LPMALLOC, LPOLESTR))ppMalloc->lpVtbl->Free)(ppMalloc, lpsz);
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180028314  mov     [rsp-8+arg_0], rbx
0x180028319  mov     [rsp-8+arg_8], rsi
0x18002831e  push    rbp
0x18002831f  lea     rbp, [rsp-7B0h]
0x180028327  sub     rsp, 8B0h
0x18002832e  mov     rax, cs:__security_cookie
0x180028335  xor     rax, rsp
0x180028338  mov     [rbp+7B0h+var_10], rax
0x18002833f  cmp     cs:qword_1800ACC40, 0
0x180028347  mov     [rsp+8B0h+var_870], 0
0x180028350  mov     [rsp+8B0h+lpsz], 0
0x180028359  mov     [rsp+8B0h+cbData], 105h
0x180028361  mov     [rsp+8B0h+Type], 0
0x180028369  mov     [rsp+8B0h+hKey], 0
0x180028372  jz      short loc_18002837E
0x180028374  mov     eax, 4DFh
0x180028379  jmp     loc_180028589
0x18002837e  lea     rdx, [rsp+8B0h+lpsz]; lplpsz
0x180028383  mov     cs:?g_lpAccountManager@@3PEAUIImnAccountManager3@@EA, 0; IImnAccountManager3 * g_lpAccountManager
0x18002838e  lea     rcx, CLSID_ImnAccountManager; rclsid
0x180028395  call    cs:__imp_StringFromCLSID
0x18002839b  test    eax, eax
0x18002839d  js      loc_180028502
0x1800283a3  mov     r8, [rsp+8B0h+lpsz]; unsigned __int16 *
0x1800283a8  lea     rcx, [rbp+7B0h+var_430]; unsigned __int16 *
0x1800283af  mov     esi, 104h
0x1800283b4  mov     edx, esi; unsigned __int64
0x1800283b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800283bb  lea     r8, aClsid; "CLSID\\"
0x1800283c2  mov     edx, esi; unsigned __int64
0x1800283c4  lea     rcx, [rsp+8B0h+SubKey]; unsigned __int16 *
0x1800283c9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800283ce  lea     r8, [rbp+7B0h+var_430]; unsigned __int16 *
0x1800283d5  mov     edx, esi; unsigned __int64
0x1800283d7  lea     rcx, [rsp+8B0h+SubKey]; unsigned __int16 *
0x1800283dc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800283e1  lea     r8, aInprocserver32; "\\InprocServer32"
0x1800283e8  mov     edx, esi; unsigned __int64
0x1800283ea  lea     rcx, [rsp+8B0h+SubKey]; unsigned __int16 *
0x1800283ef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800283f4  lea     rax, [rsp+8B0h+hKey]
0x1800283f9  mov     r9d, 1; samDesired
0x1800283ff  xor     r8d, r8d; ulOptions
0x180028402  mov     [rsp+8B0h+phkResult], rax; phkResult
0x180028407  lea     rdx, [rsp+8B0h+SubKey]; lpSubKey
0x18002840c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180028413  call    cs:__imp_RegOpenKeyExW
0x180028419  test    eax, eax
0x18002841b  jnz     loc_180028502
0x180028421  mov     rcx, [rsp+8B0h+hKey]; hKey
0x180028426  lea     rax, [rsp+8B0h+cbData]
0x18002842b  mov     [rsp+8B0h+lpcbData], rax; lpcbData
0x180028430  lea     r9, [rsp+8B0h+Type]; lpType
0x180028435  lea     rax, [rbp+7B0h+Data]
0x18002843c  mov     [rsp+8B0h+cbData], esi
0x180028440  xor     r8d, r8d; lpReserved
0x180028443  mov     [rsp+8B0h+phkResult], rax; lpData
0x180028448  xor     edx, edx; lpValueName
0x18002844a  call    cs:__imp_RegQueryValueExW
0x180028450  cmp     [rsp+8B0h+Type], 2
0x180028455  mov     ebx, eax
0x180028457  jnz     short loc_18002848D
0x180028459  mov     r8d, esi; nSize
0x18002845c  lea     rdx, [rbp+7B0h+Dst]; lpDst
0x180028463  lea     rcx, [rbp+7B0h+Data]; lpSrc
0x18002846a  call    cs:__imp_ExpandEnvironmentStringsW
0x180028470  test    eax, eax
0x180028472  jz      loc_180028502
0x180028478  lea     r8, [rbp+7B0h+Dst]; unsigned __int16 *
0x18002847f  mov     edx, esi; unsigned __int64
0x180028481  lea     rcx, [rbp+7B0h+Data]; unsigned __int16 *
0x180028488  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002848d  test    ebx, ebx
0x18002848f  jnz     short loc_180028502
0x180028491  lea     rcx, [rbp+7B0h+Data]; lpLibFileName
0x180028498  call    cs:__imp_LoadLibraryW
0x18002849e  mov     cs:qword_1800ACC40, rax
0x1800284a5  test    rax, rax
0x1800284a8  jz      short loc_180028502
0x1800284aa  lea     rdx, aHrcreateaccoun; "HrCreateAccountManager"
0x1800284b1  mov     rcx, rax; hModule
0x1800284b4  call    cs:__imp_GetProcAddress
0x1800284ba  test    rax, rax
0x1800284bd  jz      short loc_180028502
0x1800284bf  lea     rcx, [rsp+8B0h+var_870]
0x1800284c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284c9  mov     ebx, eax
0x1800284cb  test    eax, eax
0x1800284cd  js      short loc_18002852A
0x1800284cf  mov     rcx, [rsp+8B0h+var_870]
0x1800284d4  lea     r8, ?g_lpAccountManager@@3PEAUIImnAccountManager3@@EA; IImnAccountManager3 * g_lpAccountManager
0x1800284db  lea     rdx, IID_IImnAccountManager2
0x1800284e2  mov     rax, [rcx]
0x1800284e5  mov     rax, [rax]
0x1800284e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284ed  mov     rcx, [rsp+8B0h+var_870]
0x1800284f2  mov     ebx, eax
0x1800284f4  mov     rax, [rcx]
0x1800284f7  mov     rax, [rax+10h]
0x1800284fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028500  jmp     short loc_18002852A
0x180028502  lea     rdx, ?g_lpAccountManager@@3PEAUIImnAccountManager3@@EA; IImnAccountManager3 * g_lpAccountManager
0x180028509  mov     [rsp+8B0h+phkResult], rdx; ppv
0x18002850e  lea     r9, IID_IImnAccountManager2; riid
0x180028515  xor     edx, edx; pUnkOuter
0x180028517  lea     rcx, CLSID_ImnAccountManager; rclsid
0x18002851e  lea     r8d, [rdx+1]; dwClsContext
0x180028522  call    cs:__imp_CoCreateInstance
0x180028528  mov     ebx, eax
0x18002852a  cmp     [rsp+8B0h+lpsz], 0
0x180028530  jz      short loc_180028577
0x180028532  lea     rdx, [rsp+8B0h+ppMalloc]; ppMalloc
0x180028537  mov     [rsp+8B0h+ppMalloc], 0
0x180028540  mov     ecx, 1; dwMemContext
0x180028545  call    cs:__imp_CoGetMalloc
0x18002854b  mov     rcx, [rsp+8B0h+ppMalloc]
0x180028550  test    rcx, rcx
0x180028553  jz      short loc_180028577
0x180028555  mov     rax, [rcx]
0x180028558  mov     rdx, [rsp+8B0h+lpsz]
0x18002855d  mov     rax, [rax+28h]
0x180028561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028566  mov     rcx, [rsp+8B0h+ppMalloc]
0x18002856b  mov     rax, [rcx]
0x18002856e  mov     rax, [rax+10h]
0x180028572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028577  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18002857c  test    rcx, rcx
0x18002857f  jz      short loc_180028587
0x180028581  call    cs:__imp_RegCloseKey
0x180028587  mov     eax, ebx
0x180028589  mov     rcx, [rbp+7B0h+var_10]
0x180028590  xor     rcx, rsp; StackCookie
0x180028593  call    __security_check_cookie
0x180028598  lea     r11, [rsp+8B0h+var_s0]
0x1800285a0  mov     rbx, [r11+10h]
0x1800285a4  mov     rsi, [r11+18h]
0x1800285a8  mov     rsp, r11
0x1800285ab  pop     rbp
0x1800285ac  retn
```
