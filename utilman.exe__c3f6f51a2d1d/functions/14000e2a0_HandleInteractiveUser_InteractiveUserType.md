# HandleInteractiveUser(InteractiveUserType)

- ea: `0x14000e2a0`
- end: `0x14000e3c4`
- name: `?HandleInteractiveUser@@YAXW4InteractiveUserType@@@Z`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140012f54`

## callees

- `0x14000ccb4`
- `0x14000e2a0`
- `0x14000e6e4`
- `0x14000e81c`
- `0x1400135a4`
- `0x1400135f0`
- `0x140017b08`
- `0x140029010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000e2f7`
- `KERNEL32!CloseHandle` at `0x14000e2f7`
- `KERNEL32!OpenMutexW` at `0x14000e2e3`
- `KERNEL32!OpenMutexW` at `0x14000e2e3`
- `KERNEL32!Sleep` at `0x14000e3a3`
- `KERNEL32!Sleep` at `0x14000e3a3`
- `ole32!CoCreateInstance` at `0x14000e343`
- `ole32!CoCreateInstance` at `0x14000e343`

## string_xrefs

- `0x14000e379`: `pagegroup=SettingsPageGroupEaseOfAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall HandleInteractiveUser(int a1)
{
  int v2; // edx
  HANDLE v3; // rax
  const unsigned __int16 *v4; // rcx
  _BYTE v5[360]; // [rsp+30h] [rbp-168h] BYREF
  int v6; // [rsp+1A8h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+1B0h] [rbp+18h] BYREF

  ATManager::ATManager((ATManager *)v5);
  if ( (unsigned int)StartList::Synchronize((StartList *)v5, v2) && !IsUtilmanRunning() )
  {
    v3 = OpenMutexW(0x100000u, 0, L"Global\\Windows.User.OOBE");
    if ( v3 )
    {
      CloseHandle(v3);
    }
    else if ( a1 != 1 )
    {
      ppv = 0;
      if ( CoCreateInstance(
             &CLSID_ApplicationActivationManager,
             0,
             1u,
             &GUID_2e941141_7f97_4756_ba1d_9decde894a3d,
             &ppv) >= 0 )
      {
        v6 = 0;
        (*(void (__fastcall **)(LPVOID, const wchar_t *, const wchar_t *, _QWORD, int *))(*(_QWORD *)ppv + 24LL))(
          ppv,
          L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
          L"pagegroup=SettingsPageGroupEaseOfAccess",
          0,
          &v6);
      }
      wil::com_ptr_t<ILightDismissProvider,wil::err_exception_policy>::~com_ptr_t<ILightDismissProvider,wil::err_exception_policy>(&ppv);
      goto LABEL_10;
    }
    LaunchEaseOfAccessDialogOutOfProccess(v4);
LABEL_10:
    Sleep(0x7D0u);
  }
  ATManager::~ATManager((ATManager *)v5);
}

```

## disassembly

```asm
0x14000e2a0  push    rbx
0x14000e2a2  sub     rsp, 190h
0x14000e2a9  mov     ebx, ecx
0x14000e2ab  lea     rcx, [rsp+198h+var_168]; this
0x14000e2b0  call    ??0ATManager@@QEAA@XZ; ATManager::ATManager(void)
0x14000e2b5  nop
0x14000e2b6  lea     rcx, [rsp+198h+var_168]; this
0x14000e2bb  call    ?Synchronize@StartList@@QEAAJH@Z; StartList::Synchronize(int)
0x14000e2c0  test    eax, eax
0x14000e2c2  jz      loc_14000E3B0
0x14000e2c8  call    ?IsUtilmanRunning@@YA_NXZ; IsUtilmanRunning(void)
0x14000e2cd  test    al, al
0x14000e2cf  jnz     loc_14000E3B0
0x14000e2d5  lea     r8, Name; "Global\\Windows.User.OOBE"
0x14000e2dc  xor     edx, edx; bInheritHandle
0x14000e2de  mov     ecx, 100000h; dwDesiredAccess
0x14000e2e3  call    cs:__imp_OpenMutexW
0x14000e2ea  nop     dword ptr [rax+rax+00h]
0x14000e2ef  test    rax, rax
0x14000e2f2  jz      short loc_14000E305
0x14000e2f4  mov     rcx, rax; hObject
0x14000e2f7  call    cs:__imp_CloseHandle
0x14000e2fe  nop     dword ptr [rax+rax+00h]
0x14000e303  jmp     short loc_14000E310
0x14000e305  mov     r8d, 1; dwClsContext
0x14000e30b  cmp     ebx, r8d
0x14000e30e  jnz     short loc_14000E31A
0x14000e310  call    ?LaunchEaseOfAccessDialogOutOfProccess@@YAXPEBG@Z; LaunchEaseOfAccessDialogOutOfProccess(ushort const *)
0x14000e315  jmp     loc_14000E39E
0x14000e31a  mov     [rsp+198h+arg_10], 0
0x14000e326  lea     rax, [rsp+198h+arg_10]
0x14000e32e  mov     [rsp+198h+ppv], rax; ppv
0x14000e333  lea     r9, _GUID_2e941141_7f97_4756_ba1d_9decde894a3d; riid
0x14000e33a  xor     edx, edx; pUnkOuter
0x14000e33c  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x14000e343  call    cs:__imp_CoCreateInstance
0x14000e34a  nop     dword ptr [rax+rax+00h]
0x14000e34f  test    eax, eax
0x14000e351  js      short loc_14000E391
0x14000e353  mov     [rsp+198h+arg_8], 0
0x14000e35e  mov     rcx, [rsp+198h+arg_10]
0x14000e366  mov     rax, [rcx]
0x14000e369  lea     rdx, [rsp+198h+arg_8]
0x14000e371  mov     [rsp+198h+ppv], rdx
0x14000e376  xor     r9d, r9d
0x14000e379  lea     r8, aPagegroupSetti; "pagegroup=SettingsPageGroupEaseOfAccess"
0x14000e380  lea     rdx, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x14000e387  mov     rax, [rax+18h]
0x14000e38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e390  nop
0x14000e391  lea     rcx, [rsp+198h+arg_10]
0x14000e399  call    ??1?$com_ptr_t@UILightDismissProvider@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ILightDismissProvider,wil::err_exception_policy>::~com_ptr_t<ILightDismissProvider,wil::err_exception_policy>(void)
0x14000e39e  mov     ecx, 7D0h; dwMilliseconds
0x14000e3a3  call    cs:__imp_Sleep
0x14000e3aa  nop     dword ptr [rax+rax+00h]
0x14000e3af  nop
0x14000e3b0  lea     rcx, [rsp+198h+var_168]; this
0x14000e3b5  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x14000e3ba  add     rsp, 190h
0x14000e3c1  pop     rbx
0x14000e3c2  retn
```
