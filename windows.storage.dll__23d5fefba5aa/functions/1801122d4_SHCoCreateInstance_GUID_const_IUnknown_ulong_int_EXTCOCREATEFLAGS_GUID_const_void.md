# _SHCoCreateInstance(_GUID const &,IUnknown *,ulong,int,EXTCOCREATEFLAGS,_GUID const &,void * *)

- ea: `0x1801122d4`
- end: `0x18011265e`
- name: `?_SHCoCreateInstance@@YAJAEBU_GUID@@PEAUIUnknown@@KHW4EXTCOCREATEFLAGS@@0PEAPEAX@Z`
- size: `906`
- prototype: ``
- caller_count: `31`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180065890`
- `0x18008b6c0`
- `0x180091244`
- `0x180092a70`
- `0x1800add84`
- `0x1800c9598`
- `0x180111b48`
- `0x180111e04`
- `0x180111f90`
- `0x180112200`
- `0x180112240`
- `0x180147dbc`
- `0x180180ba0`
- `0x1801d6478`
- `0x180246ac4`
- `0x1802471d4`
- `0x18032ab98`
- `0x18032af00`
- `0x18032b690`
- `0x180331290`
- `0x18033a118`
- `0x18033bfc0`
- `0x180523820`
- `0x18054bd34`
- `0x18058531c`
- `0x1805b6510`
- `0x1805beda4`
- `0x1805dfa30`
- `0x1805dfb70`
- `0x1805ebe30`
- `0x1805f9598`

## callees

- `0x1801122d4`
- `0x1801d6e80`
- `0x1801d7050`
- `0x1801d7180`
- `0x1801e6f50`
- `0x1803b1f60`
- `0x1805df964`
- `0x1805df9f0`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801124cf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801124f9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801124cf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1801124f9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1801124b9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1801124e3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1801124b9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1801124e3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180112523`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801125b3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180112523`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801125b3`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x180112612`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x180112612`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHPinDllOfCLSID` at `0x180112625`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!SHPinDllOfCLSID` at `0x180112625`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHStringFromGUIDW` at `0x18011233d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHStringFromGUIDW` at `0x18011233d`

## string_xrefs

- `0x1801123a7`: `shell32.dll`
- `0x1801124f2`: `shell32.dll`
- `0x1801124c8`: `windows.storage.dll`
- `0x1801123d1`: `windows.system.launcher.dll`
- `0x180112405`: `windows.fileexplorer.common.dll`

## pseudocode

```c
__int64 __fastcall _SHCoCreateInstance(
        const struct _GUID *a1,
        IUnknown *a2,
        DWORD a3,
        int a4,
        int a5,
        IID *riid,
        LPVOID *ppv)
{
  unsigned int ClassObject; // ebx
  unsigned int v11; // r9d
  int v12; // r14d
  int v13; // eax
  int v14; // ebx
  unsigned int v15; // r9d
  int ServerInfo; // eax
  const WCHAR *FileNameW; // rax
  const WCHAR *v18; // rax
  int ShouldLoadShellExt; // eax
  int v20; // esi
  DWORD v21; // r8d
  struct IUnknown *v22; // r15
  HRESULT Instance; // eax
  int v26; // [rsp+34h] [rbp-CCh] BYREF
  LPUNKNOWN pUnkOuter; // [rsp+38h] [rbp-C8h]
  _BYTE v28[80]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[264]; // [rsp+90h] [rbp-70h] BYREF

  pUnkOuter = a2;
  *ppv = 0;
  ClassObject = -2147467259;
  if ( (int)SHStringFromGUIDW(a1, v28, 39) < 0 )
    return ClassObject;
  v26 = 0;
  pszPath[0] = 0;
  v12 = 1;
  if ( (a3 & 1) != 0 && (a5 & 1) == 0 )
  {
    ClassObject = _CreateFromDllGetClassObject(
                    (int (*)(const struct _GUID *, const struct _GUID *, void **))DllGetClassObject,
                    a1,
                    a2,
                    riid,
                    ppv);
    if ( ClassObject == -2147221231 )
    {
      v13 = _CreateFromSystem32Dll(L"shell32.dll", a1, a2, riid, ppv);
      ClassObject = v13;
      if ( v13 == -2147221231 || v13 == -2147024770 )
      {
        ClassObject = _CreateFromSystem32Dll(L"windows.system.launcher.dll", a1, a2, riid, ppv);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_61110674>::GetImpl'::`2'::impl) )
        {
          if ( ClassObject == -2147221231 )
            ClassObject = _CreateFromSystem32Dll(L"windows.fileexplorer.common.dll", a1, a2, riid, ppv);
        }
      }
    }
    if ( (int)(ClassObject + 0x80000000) < 0 || ClassObject == -2147467262 )
      return ClassObject;
  }
  if ( (a3 & 0x17) == 1 )
  {
    ServerInfo = _GetServerInfo(L"\\InProcServer32", a1, pszPath, v11, &v26);
    ClassObject = ServerInfo;
    if ( ServerInfo < 0 )
      return ClassObject;
    if ( !ServerInfo )
    {
      FileNameW = PathFindFileNameW(pszPath);
      if ( !StrCmpICW(FileNameW, L"windows.storage.dll")
        || (v18 = PathFindFileNameW(pszPath), !StrCmpICW(v18, L"shell32.dll")) )
      {
        if ( (a5 & 1) != 0 )
          return (unsigned int)CoCreateInstance(a1, a2, a3, riid, ppv);
        else
          return (unsigned int)-2147221231;
      }
    }
    v14 = a4;
  }
  else
  {
    v14 = a4;
    v12 = 0;
    if ( !a4 )
      goto LABEL_31;
    if ( (int)_GetServerInfo(L"\\InProcServer32", a1, pszPath, v11, 0) < 0 )
    {
      _GetServerInfo(L"\\LocalServer32", a1, pszPath, v15, 0);
      goto LABEL_25;
    }
  }
  if ( v14 )
  {
LABEL_25:
    ShouldLoadShellExt = _ShouldLoadShellExt(a1, v28, riid, a3, a5, pszPath);
    v20 = ShouldLoadShellExt;
    if ( !ShouldLoadShellExt )
      return (unsigned int)-2147024891;
    if ( ShouldLoadShellExt == 1 )
    {
      if ( v12 )
        return (unsigned int)-2144926975;
      a3 &= ~1u;
    }
    goto LABEL_32;
  }
LABEL_31:
  v20 = 2;
LABEL_32:
  v21 = a3;
  v22 = pUnkOuter;
  Instance = CoCreateInstance(a1, pUnkOuter, v21, riid, ppv);
  ClassObject = Instance;
  if ( Instance >= 0 )
    goto LABEL_41;
  if ( v20 == 1 && Instance == -2147221164 )
    return (unsigned int)-2144926975;
  if ( v12 && v26 && (Instance == -2147221163 || Instance == -2147221008) )
  {
    ClassObject = _CreateFromDll(pszPath, a1, v22, riid, ppv);
    if ( (ClassObject & 0x80000000) == 0 )
    {
LABEL_41:
      if ( v12 && (SHGetObjectCompatFlags(0, a1) & 8) != 0 )
        SHPinDllOfCLSID(a1);
    }
  }
  return ClassObject;
}

```

## disassembly

```asm
0x1801122d4  mov     [rsp-8+arg_18], rbx
0x1801122d9  push    rbp
0x1801122da  push    rsi
0x1801122db  push    rdi
0x1801122dc  push    r12
0x1801122de  push    r13
0x1801122e0  push    r14
0x1801122e2  push    r15
0x1801122e4  lea     rbp, [rsp-1B0h]
0x1801122ec  sub     rsp, 2B0h
0x1801122f3  mov     rax, cs:__security_cookie
0x1801122fa  xor     rax, rsp
0x1801122fd  mov     [rbp+1E0h+var_40], rax
0x180112304  mov     r13, [rbp+1E0h+arg_30]
0x18011230b  mov     r15d, r8d
0x18011230e  mov     r12, [rbp+1E0h+riid]
0x180112315  mov     rsi, rdx
0x180112318  mov     [rsp+2E0h+pUnkOuter], rdx
0x18011231d  mov     r8d, 27h ; '''
0x180112323  lea     rdx, [rsp+2E0h+var_2A0]
0x180112328  mov     [rsp+2E0h+var_2B0], r9d
0x18011232d  mov     qword ptr [r13+0], 0
0x180112335  mov     rdi, rcx
0x180112338  mov     ebx, 80004005h
0x18011233d  call    cs:__imp_SHStringFromGUIDW
0x180112344  nop     dword ptr [rax+rax+00h]
0x180112349  test    eax, eax
0x18011234b  js      loc_180112631
0x180112351  xor     eax, eax
0x180112353  mov     [rsp+2E0h+var_2AC], 0
0x18011235b  mov     [rbp+1E0h+pszPath], ax
0x18011235f  lea     r14d, [rax+1]
0x180112363  test    r14b, r15b
0x180112366  jz      loc_180112432
0x18011236c  test    byte ptr [rbp+1E0h+arg_20], r14b
0x180112373  jnz     loc_180112432
0x180112379  mov     r9, r12; struct _GUID *
0x18011237c  mov     [rsp+2E0h+ppv], r13; void **
0x180112381  mov     r8, rsi; struct IUnknown *
0x180112384  lea     rcx, DllGetClassObject; int (*)(const struct _GUID *, const struct _GUID *, void **)
0x18011238b  mov     rdx, rdi; struct _GUID *
0x18011238e  call    ?_CreateFromDllGetClassObject@@YAJP6AJAEBU_GUID@@0PEAPEAX@Z0PEAUIUnknown@@01@Z; _CreateFromDllGetClassObject(long (*)(_GUID const &,_GUID const &,void * *),_GUID const &,IUnknown *,_GUID const &,void * *)
0x180112393  mov     ebx, eax
0x180112395  cmp     eax, 80040111h
0x18011239a  jnz     short loc_180112416
0x18011239c  mov     r9, r12; struct _GUID *
0x18011239f  mov     [rsp+2E0h+ppv], r13; void **
0x1801123a4  mov     r8, rsi; struct IUnknown *
0x1801123a7  lea     rcx, aShell32Dll; "shell32.dll"
0x1801123ae  mov     rdx, rdi; struct _GUID *
0x1801123b1  call    ?_CreateFromSystem32Dll@@YAJPEBGAEBU_GUID@@PEAUIUnknown@@1PEAPEAX@Z; _CreateFromSystem32Dll(ushort const *,_GUID const &,IUnknown *,_GUID const &,void * *)
0x1801123b6  mov     ebx, eax
0x1801123b8  cmp     eax, 80040111h
0x1801123bd  jz      short loc_1801123C6
0x1801123bf  cmp     eax, 8007007Eh
0x1801123c4  jnz     short loc_180112416
0x1801123c6  mov     r9, r12; struct _GUID *
0x1801123c9  mov     [rsp+2E0h+ppv], r13; void **
0x1801123ce  mov     r8, rsi; struct IUnknown *
0x1801123d1  lea     rcx, aWindowsSystemL; "windows.system.launcher.dll"
0x1801123d8  mov     rdx, rdi; struct _GUID *
0x1801123db  call    ?_CreateFromSystem32Dll@@YAJPEBGAEBU_GUID@@PEAUIUnknown@@1PEAPEAX@Z; _CreateFromSystem32Dll(ushort const *,_GUID const &,IUnknown *,_GUID const &,void * *)
0x1801123e0  mov     ebx, eax
0x1801123e2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_61110674@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_61110674@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674> `wil::Feature<__WilFeatureTraits_Feature_61110674>::GetImpl(void)'::`2'::impl
0x1801123e9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_61110674@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61110674>::__private_IsEnabled(wil::ReportingKind)
0x1801123ee  test    al, al
0x1801123f0  jz      short loc_180112416
0x1801123f2  cmp     ebx, 80040111h
0x1801123f8  jnz     short loc_180112416
0x1801123fa  mov     r9, r12; struct _GUID *
0x1801123fd  mov     [rsp+2E0h+ppv], r13; void **
0x180112402  mov     r8, rsi; struct IUnknown *
0x180112405  lea     rcx, aWindowsFileexp; "windows.fileexplorer.common.dll"
0x18011240c  mov     rdx, rdi; struct _GUID *
0x18011240f  call    ?_CreateFromSystem32Dll@@YAJPEBGAEBU_GUID@@PEAUIUnknown@@1PEAPEAX@Z; _CreateFromSystem32Dll(ushort const *,_GUID const &,IUnknown *,_GUID const &,void * *)
0x180112414  mov     ebx, eax
0x180112416  mov     ecx, 80000000h
0x18011241b  lea     eax, [rbx+rcx]
0x18011241e  test    ecx, eax
0x180112420  jnz     loc_180112631
0x180112426  cmp     ebx, 80004002h
0x18011242c  jz      loc_180112631
0x180112432  mov     eax, r15d
0x180112435  and     al, 17h
0x180112437  cmp     al, r14b
0x18011243a  jz      short loc_180112488
0x18011243c  mov     ebx, [rsp+2E0h+var_2B0]
0x180112440  xor     r14d, r14d
0x180112443  test    ebx, ebx
0x180112445  jz      loc_180112598
0x18011244b  lea     r8, [rbp+1E0h+pszPath]; unsigned __int16 *
0x18011244f  mov     [rsp+2E0h+ppv], r14; int *
0x180112454  mov     rdx, rdi; struct _GUID *
0x180112457  lea     rcx, aInprocserver32; "\\InProcServer32"
0x18011245e  call    ?_GetServerInfo@@YAJPEBGAEBU_GUID@@PEAGIPEAH@Z; _GetServerInfo(ushort const *,_GUID const &,ushort *,uint,int *)
0x180112463  test    eax, eax
0x180112465  jns     loc_180112544
0x18011246b  lea     r8, [rbp+1E0h+pszPath]; unsigned __int16 *
0x18011246f  mov     [rsp+2E0h+ppv], r14; int *
0x180112474  mov     rdx, rdi; struct _GUID *
0x180112477  lea     rcx, aLocalserver32_0; "\\LocalServer32"
0x18011247e  call    ?_GetServerInfo@@YAJPEBGAEBU_GUID@@PEAGIPEAH@Z; _GetServerInfo(ushort const *,_GUID const &,ushort *,uint,int *)
0x180112483  jmp     loc_180112548
0x180112488  lea     rax, [rsp+2E0h+var_2AC]
0x18011248d  mov     rdx, rdi; struct _GUID *
0x180112490  lea     r8, [rbp+1E0h+pszPath]; unsigned __int16 *
0x180112494  mov     [rsp+2E0h+ppv], rax; int *
0x180112499  lea     rcx, aInprocserver32; "\\InProcServer32"
0x1801124a0  call    ?_GetServerInfo@@YAJPEBGAEBU_GUID@@PEAGIPEAH@Z; _GetServerInfo(ushort const *,_GUID const &,ushort *,uint,int *)
0x1801124a5  mov     ebx, eax
0x1801124a7  test    eax, eax
0x1801124a9  js      loc_180112631
0x1801124af  jnz     loc_180112540
0x1801124b5  lea     rcx, [rbp+1E0h+pszPath]; pszPath
0x1801124b9  call    cs:__imp_PathFindFileNameW
0x1801124c0  nop     dword ptr [rax+rax+00h]
0x1801124c5  mov     rcx, rax; pszStr1
0x1801124c8  lea     rdx, aWindowsStorage_16; "windows.storage.dll"
0x1801124cf  call    cs:__imp_StrCmpICW
0x1801124d6  nop     dword ptr [rax+rax+00h]
0x1801124db  test    eax, eax
0x1801124dd  jz      short loc_180112509
0x1801124df  lea     rcx, [rbp+1E0h+pszPath]; pszPath
0x1801124e3  call    cs:__imp_PathFindFileNameW
0x1801124ea  nop     dword ptr [rax+rax+00h]
0x1801124ef  mov     rcx, rax; pszStr1
0x1801124f2  lea     rdx, aShell32Dll; "shell32.dll"
0x1801124f9  call    cs:__imp_StrCmpICW
0x180112500  nop     dword ptr [rax+rax+00h]
0x180112505  test    eax, eax
0x180112507  jnz     short loc_180112540
0x180112509  test    byte ptr [rbp+1E0h+arg_20], 1
0x180112510  jz      short loc_180112536
0x180112512  mov     r9, r12; riid
0x180112515  mov     [rsp+2E0h+ppv], r13; ppv
0x18011251a  mov     r8d, r15d; dwClsContext
0x18011251d  mov     rdx, rsi; pUnkOuter
0x180112520  mov     rcx, rdi; rclsid
0x180112523  call    cs:__imp_CoCreateInstance
0x18011252a  nop     dword ptr [rax+rax+00h]
0x18011252f  mov     ebx, eax
0x180112531  jmp     loc_180112631
0x180112536  mov     ebx, 80040111h
0x18011253b  jmp     loc_180112631
0x180112540  mov     ebx, [rsp+2E0h+var_2B0]
0x180112544  test    ebx, ebx
0x180112546  jz      short loc_180112598
0x180112548  lea     rax, [rbp+1E0h+pszPath]
0x18011254c  mov     r9d, r15d
0x18011254f  mov     [rsp+2E0h+var_2B8], rax
0x180112554  lea     rdx, [rsp+2E0h+var_2A0]
0x180112559  mov     eax, [rbp+1E0h+arg_20]
0x18011255f  mov     r8, r12
0x180112562  mov     rcx, rdi
0x180112565  mov     dword ptr [rsp+2E0h+ppv], eax
0x180112569  call    ?_ShouldLoadShellExt@@YA?AW4ExtLoadPolicy@@AEBU_GUID@@PEBG0KK1@Z; _ShouldLoadShellExt(_GUID const &,ushort const *,_GUID const &,ulong,ulong,ushort const *)
0x18011256e  mov     esi, eax
0x180112570  test    eax, eax
0x180112572  jnz     short loc_18011257E
0x180112574  mov     ebx, 80070005h
0x180112579  jmp     loc_180112631
0x18011257e  cmp     eax, 1
0x180112581  jnz     short loc_18011259D
0x180112583  test    r14d, r14d
0x180112586  jz      short loc_180112592
0x180112588  mov     ebx, 80270301h
0x18011258d  jmp     loc_180112631
0x180112592  and     r15d, 0FFFFFFFEh
0x180112596  jmp     short loc_18011259D
0x180112598  mov     esi, 2
0x18011259d  mov     r8d, r15d; dwClsContext
0x1801125a0  mov     [rsp+2E0h+ppv], r13; ppv
0x1801125a5  mov     r15, [rsp+2E0h+pUnkOuter]
0x1801125aa  mov     r9, r12; riid
0x1801125ad  mov     rdx, r15; pUnkOuter
0x1801125b0  mov     rcx, rdi; rclsid
0x1801125b3  call    cs:__imp_CoCreateInstance
0x1801125ba  nop     dword ptr [rax+rax+00h]
0x1801125bf  mov     ebx, eax
0x1801125c1  test    eax, eax
0x1801125c3  jns     short loc_180112608
0x1801125c5  cmp     esi, 1
0x1801125c8  jnz     short loc_1801125D1
0x1801125ca  cmp     eax, 80040154h
0x1801125cf  jz      short loc_180112588
0x1801125d1  test    r14d, r14d
0x1801125d4  jz      short loc_180112631
0x1801125d6  cmp     [rsp+2E0h+var_2AC], 0
0x1801125db  jz      short loc_180112631
0x1801125dd  cmp     eax, 80040155h
0x1801125e2  jz      short loc_1801125EB
0x1801125e4  cmp     eax, 800401F0h
0x1801125e9  jnz     short loc_180112631
0x1801125eb  mov     r9, r12; struct _GUID *
0x1801125ee  mov     [rsp+2E0h+ppv], r13; void **
0x1801125f3  mov     r8, r15; struct IUnknown *
0x1801125f6  lea     rcx, [rbp+1E0h+pszPath]; unsigned __int16 *
0x1801125fa  mov     rdx, rdi; struct _GUID *
0x1801125fd  call    ?_CreateFromDll@@YAJPEBGAEBU_GUID@@PEAUIUnknown@@1PEAPEAX@Z; _CreateFromDll(ushort const *,_GUID const &,IUnknown *,_GUID const &,void * *)
0x180112602  mov     ebx, eax
0x180112604  test    eax, eax
0x180112606  js      short loc_180112631
0x180112608  test    r14d, r14d
0x18011260b  jz      short loc_180112631
0x18011260d  mov     rdx, rdi
0x180112610  xor     ecx, ecx
0x180112612  call    cs:__imp_SHGetObjectCompatFlags
0x180112619  nop     dword ptr [rax+rax+00h]
0x18011261e  test    al, 8
0x180112620  jz      short loc_180112631
0x180112622  mov     rcx, rdi
0x180112625  call    cs:__imp_SHPinDllOfCLSID
0x18011262c  nop     dword ptr [rax+rax+00h]
0x180112631  mov     eax, ebx
0x180112633  mov     rcx, [rbp+1E0h+var_40]
0x18011263a  xor     rcx, rsp; StackCookie
0x18011263d  call    __security_check_cookie
0x180112642  mov     rbx, [rsp+2E0h+arg_18]
0x18011264a  add     rsp, 2B0h
0x180112651  pop     r15
0x180112653  pop     r14
0x180112655  pop     r13
0x180112657  pop     r12
0x180112659  pop     rdi
0x18011265a  pop     rsi
0x18011265b  pop     rbp
0x18011265c  retn
```
