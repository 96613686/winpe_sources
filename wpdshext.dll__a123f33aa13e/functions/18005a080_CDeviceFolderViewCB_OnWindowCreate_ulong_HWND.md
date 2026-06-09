# CDeviceFolderViewCB::_OnWindowCreate(ulong,HWND__ *)

- ea: `0x18005a080`
- end: `0x18005a12d`
- name: `?_OnWindowCreate@CDeviceFolderViewCB@@AEAAJKPEAUHWND__@@@Z`
- size: `173`
- prototype: `__int64 __fastcall(IUnknown *punk, unsigned int, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180059e80`

## callees

- `0x1800285c8`
- `0x18005a080`
- `0x180078010`

## import_xrefs

- `SHLWAPI!__imp_ConnectToConnectionPoint` at `0x18005a109`
- `SHLWAPI!__imp_ConnectToConnectionPoint` at `0x18005a109`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18005a0b5`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18005a0b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDeviceFolderViewCB::_OnWindowCreate(IUnknown *punk, __int64 a2, HWND a3)
{
  void *v5; // [rsp+40h] [rbp+8h] BYREF
  IUnknown *punkTarget; // [rsp+50h] [rbp+18h] BYREF

  v5 = 0;
  punkTarget = 0;
  if ( IUnknown_QueryService(
         (IUnknown *)punk[3].lpVtbl,
         (const GUID *const)&SID_DefView,
         &GUID_000214e3_0000_0000_c000_000000000046,
         &v5) >= 0
    && (*(int (__fastcall **)(void *, _QWORD, GUID *, IUnknown **))(*(_QWORD *)v5 + 120LL))(
         v5,
         0,
         &GUID_00020400_0000_0000_c000_000000000046,
         &punkTarget) >= 0 )
  {
    ConnectToConnectionPoint(punk, &DIID_DShellFolderViewEvents, 1, punkTarget, (DWORD *)&punk[8], 0);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&punkTarget);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v5);
  return 0;
}

```

## disassembly

```asm
0x18005a080  mov     rax, rsp
0x18005a083  mov     [rax+18h], r8
0x18005a087  push    rbx
0x18005a088  sub     rsp, 30h
0x18005a08c  mov     rbx, rcx
0x18005a08f  mov     qword ptr [rax+8], 0
0x18005a097  mov     qword ptr [rax+18h], 0
0x18005a09f  lea     r9, [rax+8]; ppvOut
0x18005a0a3  lea     r8, _GUID_000214e3_0000_0000_c000_000000000046; riid
0x18005a0aa  lea     rdx, SID_DefView; guidService
0x18005a0b1  mov     rcx, [rcx+18h]; punk
0x18005a0b5  call    cs:__imp_IUnknown_QueryService
0x18005a0bb  test    eax, eax
0x18005a0bd  js      short loc_18005A110
0x18005a0bf  mov     rcx, [rsp+38h+arg_0]
0x18005a0c4  mov     rax, [rcx]
0x18005a0c7  lea     r9, [rsp+38h+punkTarget]
0x18005a0cc  lea     r8, _GUID_00020400_0000_0000_c000_000000000046
0x18005a0d3  xor     edx, edx
0x18005a0d5  mov     rax, [rax+78h]
0x18005a0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a0de  test    eax, eax
0x18005a0e0  js      short loc_18005A110
0x18005a0e2  lea     rax, [rbx+40h]
0x18005a0e6  mov     [rsp+38h+ppcpOut], 0; ppcpOut
0x18005a0ef  mov     [rsp+38h+pdwCookie], rax; pdwCookie
0x18005a0f4  mov     r9, [rsp+38h+punkTarget]; punkTarget
0x18005a0f9  mov     r8d, 1; fConnect
0x18005a0ff  lea     rdx, DIID_DShellFolderViewEvents; riidEvent
0x18005a106  mov     rcx, rbx; punk
0x18005a109  call    cs:__imp_ConnectToConnectionPoint
0x18005a10f  nop
0x18005a110  lea     rcx, [rsp+38h+punkTarget]
0x18005a115  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a11a  nop
0x18005a11b  lea     rcx, [rsp+38h+arg_0]
0x18005a120  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a125  xor     eax, eax
0x18005a127  add     rsp, 30h
0x18005a12b  pop     rbx
0x18005a12c  retn
```
