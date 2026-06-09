# CLicensingStateTools::get_IsConnectedToInternet(INetworkListManager *,short *)

- ea: `0x1800059f0`
- end: `0x180005aa9`
- name: `?get_IsConnectedToInternet@CLicensingStateTools@@UEAAJPEAUINetworkListManager@@PEAF@Z`
- size: `185`
- prototype: `__int64 __fastcall(CLicensingStateTools *__hidden this, struct INetworkListManager *, __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x1800059f0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005a35`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005a35`

## pseudocode

```c
__int64 __fastcall CLicensingStateTools::get_IsConnectedToInternet(
        CLicensingStateTools *this,
        struct INetworkListManager *a2,
        __int16 *a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  HRESULT v6; // eax
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  ppv = 0;
  if ( a3 )
  {
    if ( a2 )
    {
      ppv = a2;
      ((void (__fastcall *)(struct INetworkListManager *))a2->lpVtbl->AddRef)(a2);
    }
    else
    {
      v6 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &IID_INetworkListManager, &ppv);
      v4 = v6;
      if ( v6 < 0 )
      {
LABEL_8:
        v5 = (unsigned int)v6;
        goto LABEL_9;
      }
    }
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)ppv + 88LL))(ppv, a3);
    v4 = v6;
    if ( v6 >= 0 )
      goto LABEL_10;
    goto LABEL_8;
  }
  v4 = -2147024809;
  v5 = 2147942487LL;
LABEL_9:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
LABEL_10:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v4;
}

```

## disassembly

```asm
0x1800059f0  mov     [rsp+arg_0], rbx
0x1800059f5  push    rdi
0x1800059f6  sub     rsp, 30h
0x1800059fa  mov     [rsp+38h+arg_10], 0
0x180005a03  mov     rdi, r8
0x180005a06  test    r8, r8
0x180005a09  jnz     short loc_180005A14
0x180005a0b  mov     ebx, 80070057h
0x180005a10  mov     ecx, ebx
0x180005a12  jmp     short loc_180005A79
0x180005a14  test    rdx, rdx
0x180005a17  jnz     short loc_180005A49
0x180005a19  lea     rax, [rsp+38h+arg_10]
0x180005a1e  lea     r9, IID_INetworkListManager; riid
0x180005a25  mov     [rsp+38h+ppv], rax; ppv
0x180005a2a  lea     r8d, [rdx+1]; dwClsContext
0x180005a2e  lea     rcx, CLSID_NetworkListManager; rclsid
0x180005a35  call    cs:__imp_CoCreateInstance
0x180005a3c  nop     dword ptr [rax+rax+00h]
0x180005a41  mov     ebx, eax
0x180005a43  test    eax, eax
0x180005a45  jns     short loc_180005A5D
0x180005a47  jmp     short loc_180005A77
0x180005a49  mov     [rsp+38h+arg_10], rdx
0x180005a4e  mov     rcx, rdx
0x180005a51  mov     rax, [rdx]
0x180005a54  mov     rax, [rax+8]
0x180005a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a5d  mov     rcx, [rsp+38h+arg_10]
0x180005a62  mov     rdx, rdi
0x180005a65  mov     rax, [rcx]
0x180005a68  mov     rax, [rax+58h]
0x180005a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a71  mov     ebx, eax
0x180005a73  test    eax, eax
0x180005a75  jns     short loc_180005A7E
0x180005a77  mov     ecx, eax
0x180005a79  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180005a7e  mov     ecx, ebx
0x180005a80  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180005a85  mov     rcx, [rsp+38h+arg_10]
0x180005a8a  test    rcx, rcx
0x180005a8d  jz      short loc_180005A9B
0x180005a8f  mov     rax, [rcx]
0x180005a92  mov     rax, [rax+10h]
0x180005a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a9b  mov     eax, ebx
0x180005a9d  mov     rbx, [rsp+38h+arg_0]
0x180005aa2  add     rsp, 30h
0x180005aa6  pop     rdi
0x180005aa7  retn
```
