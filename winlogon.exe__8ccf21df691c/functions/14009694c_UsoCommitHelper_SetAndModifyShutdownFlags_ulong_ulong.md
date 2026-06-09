# UsoCommitHelper::SetAndModifyShutdownFlags(ulong,ulong &)

- ea: `0x14009694c`
- end: `0x140096c70`
- name: `?SetAndModifyShutdownFlags@UsoCommitHelper@@SAJKAEAK@Z`
- size: `804`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14008a85c`

## callees

- `0x14000aa04`
- `0x14000b41c`
- `0x14000b43c`
- `0x140031a90`
- `0x14005eebc`
- `0x140096928`
- `0x14009694c`
- `0x1400a1010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140096a14`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140096a14`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400969ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400969ab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140096a74`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140096a74`

## string_xrefs

- `0x1400969c6`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usocommithelperlib\usocommithelper.cpp`
- `0x140096a3f`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usocommithelperlib\usocommithelper.cpp`
- `0x140096a87`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usocommithelperlib\usocommithelper.cpp`
- `0x140096b2a`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usocommithelperlib\usocommithelper.cpp`
- `0x140096b6b`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usocommithelperlib\usocommithelper.cpp`
- `0x140096bce`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usocommithelperlib\usocommithelper.cpp`
- `0x140096ab4`: `UsoCommitHelper`
- `0x14009699d`: `SOFTWARE\Microsoft\WindowsUpdate\Orchestrator`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall UsoCommitHelper::SetAndModifyShutdownFlags(unsigned int a1, unsigned int *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  unsigned int ValueW; // eax
  __int64 v9; // rdx
  HRESULT v10; // eax
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-50h]
  int phkResulta; // [rsp+20h] [rbp-50h]
  __int64 v20; // [rsp+40h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-28h] BYREF
  int (__fastcall ***v22)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-20h] BYREF
  __int64 v23; // [rsp+58h] [rbp-18h] BYREF
  __int64 *v24; // [rsp+60h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  unsigned int v27; // [rsp+A0h] [rbp+30h] BYREF
  int pvData; // [rsp+B0h] [rbp+40h] BYREF
  DWORD pcbData; // [rsp+B8h] [rbp+48h] BYREF

  v27 = a1;
  hkey = 0;
  v4 = UsoCommitHelper::RemoveCommitStatusKey();
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = (unsigned int)v4;
    v7 = 39;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usocommithelperlib\\usocommithelper.cpp",
      (const char *)v6,
      phkResult);
    goto LABEL_29;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WindowsUpdate\\Orchestrator", 0, 0x20019u, &hkey);
  if ( ValueW - 2 <= 1 )
    goto LABEL_32;
  if ( ValueW )
  {
    v9 = 52;
LABEL_6:
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v9,
           (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usocommithelperlib\\usocommithelper.cpp",
           (const char *)ValueW,
           phkResult);
LABEL_29:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return v5;
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"EnhancedShutdownEnabled", 0x18u, 0, &pvData, &pcbData);
  if ( ValueW == 2 )
  {
LABEL_32:
    *a2 = v27;
    goto LABEL_33;
  }
  if ( ValueW )
  {
    v9 = 71;
    goto LABEL_6;
  }
  if ( !pvData )
  {
    v5 = -2147024809;
    v6 = 2147942487LL;
    v7 = 73;
    goto LABEL_12;
  }
  ppv = 0;
  v10 = CoCreateInstance(
          &GUID_b91d5831_b1bd_4608_8198_d72e155020f7,
          0,
          4u,
          &GUID_c57692f8_8f5f_47cb_9381_34329b40285a,
          &ppv);
  v5 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usocommithelperlib\\usocommithelper.cpp",
      (const char *)(unsigned int)v10,
      phkResulta);
LABEL_28:
    wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(&ppv);
    goto LABEL_29;
  }
  v22 = 0;
  v20 = 0;
  v11 = *(_QWORD *)ppv;
  v22 = 0;
  if ( (*(int (__fastcall **)(LPVOID, const wchar_t *, _QWORD))(v11 + 40))(ppv, L"UsoCommitHelper", &v22) >= 0 )
  {
    v20 = 0;
    if ( (**v22)(v22, &GUID_ae55c2d9_f522_453f_a27c_bc455cd564da, &v20) >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v20 + 544LL))(v20, a1, &v27);
      v5 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x53,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usocommithelperlib\\usocommithelper.cpp",
          (const char *)(unsigned int)v12,
          phkResulta);
LABEL_27:
        wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(&v20);
        wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(&v22);
        goto LABEL_28;
      }
      goto LABEL_31;
    }
  }
  v24 = 0;
  v13 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 **))ppv)(
          ppv,
          &GUID_07f3afac_7c8a_4ce7_a5e0_3d24ee8a77e0,
          &v24);
  v5 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usocommithelperlib\\usocommithelper.cpp",
      (const char *)(unsigned int)v13,
      phkResulta);
LABEL_26:
    wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(&v24);
    goto LABEL_27;
  }
  v23 = 0;
  v14 = *v24;
  v23 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v14 + 48))(v24, &v23);
  v5 = v15;
  if ( v15 < 0 )
  {
    v16 = 91;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usocommithelperlib\\usocommithelper.cpp",
      (const char *)(unsigned int)v15,
      phkResulta);
    wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(&v23);
    goto LABEL_26;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v23 + 272LL))(v23, a1, &v27);
  v5 = v15;
  if ( v15 < 0 )
  {
    v16 = 93;
    goto LABEL_25;
  }
  wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(&v23);
  wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(&v24);
LABEL_31:
  *a2 = v27;
  wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(&v20);
  wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(&v22);
  wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(&ppv);
LABEL_33:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return 0;
}

```

## disassembly

```asm
0x14009694c  push    rbp
0x14009694e  push    rbx
0x14009694f  push    rsi
0x140096950  push    rdi
0x140096951  push    r14
0x140096953  mov     rbp, rsp
0x140096956  sub     rsp, 70h
0x14009695a  mov     rdi, rdx
0x14009695d  mov     esi, ecx
0x14009695f  mov     [rbp+arg_0], ecx
0x140096962  xor     r14d, r14d
0x140096965  mov     [rbp+hkey], r14
0x140096969  call    ?RemoveCommitStatusKey@UsoCommitHelper@@CAJXZ; UsoCommitHelper::RemoveCommitStatusKey(void)
0x14009696e  mov     ebx, eax
0x140096970  test    eax, eax
0x140096972  jns     short loc_140096980
0x140096974  mov     r9d, eax
0x140096977  lea     edx, [r14+27h]
0x14009697b  jmp     loc_140096A3F
0x140096980  xor     edx, edx
0x140096982  lea     rcx, [rbp+hkey]
0x140096986  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x14009698b  lea     rax, [rbp+hkey]
0x14009698f  mov     [rsp+70h+phkResult], rax; unsigned int
0x140096994  mov     r9d, 20019h; samDesired
0x14009699a  xor     r8d, r8d; ulOptions
0x14009699d  lea     rdx, aSoftwareMicros_25; "SOFTWARE\\Microsoft\\WindowsUpdate\\Orc"...
0x1400969a4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400969ab  call    cs:__imp_RegOpenKeyExW
0x1400969b1  lea     ecx, [rax-2]
0x1400969b4  cmp     ecx, 1
0x1400969b7  jbe     loc_140096C55
0x1400969bd  test    eax, eax
0x1400969bf  jz      short loc_1400969E0
0x1400969c1  mov     edx, 34h ; '4'; void *
0x1400969c6  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1400969cd  mov     r9d, eax; char *
0x1400969d0  mov     rcx, [rbp+28h]; this
0x1400969d4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400969d9  mov     ebx, eax
0x1400969db  jmp     loc_140096C11
0x1400969e0  mov     [rbp+arg_10], r14d
0x1400969e4  mov     ebx, 4
0x1400969e9  mov     [rbp+arg_18], ebx
0x1400969ec  lea     rax, [rbp+arg_18]
0x1400969f0  mov     [rsp+70h+pcbData], rax; pcbData
0x1400969f5  lea     rax, [rbp+arg_10]
0x1400969f9  mov     [rsp+70h+pvData], rax; pvData
0x1400969fe  mov     [rsp+70h+phkResult], r14; int
0x140096a03  lea     r9d, [rbx+14h]; dwFlags
0x140096a07  lea     r8, aEnhancedshutdo; "EnhancedShutdownEnabled"
0x140096a0e  xor     edx, edx; lpSubKey
0x140096a10  mov     rcx, [rbp+hkey]; hkey
0x140096a14  call    cs:__imp_RegGetValueW
0x140096a1a  cmp     eax, 2
0x140096a1d  jz      loc_140096C55
0x140096a23  test    eax, eax
0x140096a25  jz      short loc_140096A2C
0x140096a27  lea     edx, [rbx+43h]
0x140096a2a  jmp     short loc_1400969C6
0x140096a2c  cmp     [rbp+arg_10], r14d
0x140096a30  jnz     short loc_140096A54
0x140096a32  mov     ebx, 80070057h
0x140096a37  mov     r9d, ebx; char *
0x140096a3a  mov     edx, 49h ; 'I'; void *
0x140096a3f  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x140096a46  mov     rcx, [rbp+28h]; this
0x140096a4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096a4f  jmp     loc_140096C11
0x140096a54  mov     [rbp+ppv], r14
0x140096a58  lea     rax, [rbp+ppv]
0x140096a5c  mov     [rsp+70h+phkResult], rax; int
0x140096a61  lea     r9, _GUID_c57692f8_8f5f_47cb_9381_34329b40285a; riid
0x140096a68  mov     r8d, ebx; dwClsContext
0x140096a6b  xor     edx, edx; pUnkOuter
0x140096a6d  lea     rcx, _GUID_b91d5831_b1bd_4608_8198_d72e155020f7; rclsid
0x140096a74  call    cs:__imp_CoCreateInstance
0x140096a7a  mov     ebx, eax
0x140096a7c  test    eax, eax
0x140096a7e  jns     short loc_140096A9D
0x140096a80  mov     rcx, [rbp+28h]; this
0x140096a84  mov     r9d, eax; char *
0x140096a87  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x140096a8e  mov     edx, 4Ch ; 'L'; void *
0x140096a93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096a98  jmp     loc_140096C07
0x140096a9d  mov     [rbp+var_20], r14
0x140096aa1  mov     [rbp+var_30], r14
0x140096aa5  mov     rcx, [rbp+ppv]
0x140096aa9  mov     rax, [rcx]
0x140096aac  mov     [rbp+var_20], r14
0x140096ab0  lea     r8, [rbp+var_20]
0x140096ab4  lea     rdx, aUsocommithelpe; "UsoCommitHelper"
0x140096abb  mov     rax, [rax+28h]
0x140096abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096ac4  test    eax, eax
0x140096ac6  js      short loc_140096B40
0x140096ac8  mov     rcx, [rbp+var_30]
0x140096acc  mov     [rbp+var_30], r14
0x140096ad0  test    rcx, rcx
0x140096ad3  jz      short loc_140096AE2
0x140096ad5  mov     rax, [rcx]
0x140096ad8  mov     rax, [rax+10h]
0x140096adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096ae1  nop
0x140096ae2  mov     rcx, [rbp+var_20]
0x140096ae6  mov     rax, [rcx]
0x140096ae9  lea     r8, [rbp+var_30]
0x140096aed  lea     rdx, _GUID_ae55c2d9_f522_453f_a27c_bc455cd564da
0x140096af4  mov     rax, [rax]
0x140096af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096afc  test    eax, eax
0x140096afe  js      short loc_140096B40
0x140096b00  mov     rcx, [rbp+var_30]
0x140096b04  mov     rax, [rcx]
0x140096b07  lea     r8, [rbp+arg_0]
0x140096b0b  mov     edx, esi
0x140096b0d  mov     rax, [rax+220h]
0x140096b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096b19  mov     ebx, eax
0x140096b1b  test    eax, eax
0x140096b1d  jns     loc_140096C31
0x140096b23  mov     rcx, [rbp+28h]; this
0x140096b27  mov     r9d, eax; char *
0x140096b2a  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x140096b31  mov     edx, 53h ; 'S'; void *
0x140096b36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096b3b  jmp     loc_140096BF3
0x140096b40  mov     [rbp+var_10], r14
0x140096b44  mov     rcx, [rbp+ppv]
0x140096b48  mov     rax, [rcx]
0x140096b4b  lea     r8, [rbp+var_10]
0x140096b4f  lea     rdx, _GUID_07f3afac_7c8a_4ce7_a5e0_3d24ee8a77e0
0x140096b56  mov     rax, [rax]
0x140096b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096b5e  mov     ebx, eax
0x140096b60  test    eax, eax
0x140096b62  jns     short loc_140096B7E
0x140096b64  mov     rcx, [rbp+28h]; this
0x140096b68  mov     r9d, eax; char *
0x140096b6b  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x140096b72  mov     edx, 58h ; 'X'; void *
0x140096b77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096b7c  jmp     short loc_140096BE9
0x140096b7e  mov     [rbp+var_18], r14
0x140096b82  mov     rcx, [rbp+var_10]
0x140096b86  mov     rax, [rcx]
0x140096b89  mov     [rbp+var_18], r14
0x140096b8d  lea     rdx, [rbp+var_18]
0x140096b91  mov     rax, [rax+30h]
0x140096b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096b9a  mov     ebx, eax
0x140096b9c  test    eax, eax
0x140096b9e  jns     short loc_140096BA7
0x140096ba0  mov     edx, 5Bh ; '['
0x140096ba5  jmp     short loc_140096BCB
0x140096ba7  mov     rcx, [rbp+var_18]
0x140096bab  mov     rax, [rcx]
0x140096bae  lea     r8, [rbp+arg_0]
0x140096bb2  mov     edx, esi
0x140096bb4  mov     rax, [rax+110h]
0x140096bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140096bc0  mov     ebx, eax
0x140096bc2  test    eax, eax
0x140096bc4  jns     short loc_140096C1E
0x140096bc6  mov     edx, 5Dh ; ']'; void *
0x140096bcb  mov     r9d, eax; char *
0x140096bce  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x140096bd5  mov     rcx, [rbp+28h]; this
0x140096bd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140096bde  nop
0x140096bdf  lea     rcx, [rbp+var_18]
0x140096be3  call    ??1?$com_ptr_t@UIUpdateSessionOrchestrator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(void)
0x140096be8  nop
0x140096be9  lea     rcx, [rbp+var_10]
0x140096bed  call    ??1?$com_ptr_t@UIUpdateSessionOrchestrator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(void)
0x140096bf2  nop
0x140096bf3  lea     rcx, [rbp+var_30]
0x140096bf7  call    ??1?$com_ptr_t@UIUpdateSessionOrchestrator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(void)
0x140096bfc  nop
0x140096bfd  lea     rcx, [rbp+var_20]
0x140096c01  call    ??1?$com_ptr_t@UIUpdateSessionOrchestrator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(void)
0x140096c06  nop
0x140096c07  lea     rcx, [rbp+ppv]
0x140096c0b  call    ??1?$com_ptr_t@UIUpdateSessionOrchestrator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(void)
0x140096c10  nop
0x140096c11  lea     rcx, [rbp+hkey]
0x140096c15  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140096c1a  mov     eax, ebx
0x140096c1c  jmp     short loc_140096C65
0x140096c1e  lea     rcx, [rbp+var_18]
0x140096c22  call    ??1?$com_ptr_t@UIUpdateSessionOrchestrator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(void)
0x140096c27  nop
0x140096c28  lea     rcx, [rbp+var_10]
0x140096c2c  call    ??1?$com_ptr_t@UIUpdateSessionOrchestrator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(void)
0x140096c31  mov     eax, [rbp+arg_0]
0x140096c34  mov     [rdi], eax
0x140096c36  lea     rcx, [rbp+var_30]
0x140096c3a  call    ??1?$com_ptr_t@UIUpdateSessionOrchestrator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(void)
0x140096c3f  nop
0x140096c40  lea     rcx, [rbp+var_20]
0x140096c44  call    ??1?$com_ptr_t@UIUpdateSessionOrchestrator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(void)
0x140096c49  nop
0x140096c4a  lea     rcx, [rbp+ppv]
0x140096c4e  call    ??1?$com_ptr_t@UIUpdateSessionOrchestrator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>::~com_ptr_t<IUpdateSessionOrchestrator,wil::err_returncode_policy>(void)
0x140096c53  jmp     short loc_140096C5A
0x140096c55  mov     eax, [rbp+arg_0]
0x140096c58  mov     [rdi], eax
0x140096c5a  lea     rcx, [rbp+hkey]
0x140096c5e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140096c63  xor     eax, eax
0x140096c65  add     rsp, 70h
0x140096c69  pop     r14
0x140096c6b  pop     rdi
0x140096c6c  pop     rsi
0x140096c6d  pop     rbx
0x140096c6e  pop     rbp
0x140096c6f  retn
```
