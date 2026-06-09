# CSubscriptionMgr::AbortAll(void)

- ea: `0x1800189c0`
- end: `0x180018a2a`
- name: `?AbortAll@CSubscriptionMgr@@UEAAJXZ`
- size: `106`
- prototype: `__int64 __fastcall(CSubscriptionMgr *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800189c0`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800189ed`
- `ole32!CoCreateInstance` at `0x1800189ed`

## pseudocode

```c
__int64 __fastcall CSubscriptionMgr::AbortAll(CSubscriptionMgr *this)
{
  unsigned int v1; // ebx
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  if ( CoCreateInstance(&CLSID_SubscriptionThrottler, 0, 5u, &IID_ISubscriptionThrottler, &ppv) < 0 )
  {
    return 1;
  }
  else
  {
    v1 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 40LL))(ppv);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return v1;
}

```

## disassembly

```asm
0x1800189c0  push    rbx
0x1800189c2  sub     rsp, 30h
0x1800189c6  xor     edx, edx; pUnkOuter
0x1800189c8  mov     [rsp+38h+arg_8], 0
0x1800189d1  lea     rax, [rsp+38h+arg_8]
0x1800189d6  lea     r9, IID_ISubscriptionThrottler; riid
0x1800189dd  mov     [rsp+38h+ppv], rax; ppv
0x1800189e2  lea     rcx, CLSID_SubscriptionThrottler; rclsid
0x1800189e9  lea     r8d, [rdx+5]; dwClsContext
0x1800189ed  call    cs:__imp_CoCreateInstance
0x1800189f3  test    eax, eax
0x1800189f5  js      short loc_180018A1D
0x1800189f7  mov     rcx, [rsp+38h+arg_8]
0x1800189fc  mov     rax, [rcx]
0x1800189ff  mov     rax, [rax+28h]
0x180018a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a08  mov     rcx, [rsp+38h+arg_8]
0x180018a0d  mov     ebx, eax
0x180018a0f  mov     rdx, [rcx]
0x180018a12  mov     rax, [rdx+10h]
0x180018a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a1b  jmp     short loc_180018A22
0x180018a1d  mov     ebx, 1
0x180018a22  mov     eax, ebx
0x180018a24  add     rsp, 30h
0x180018a28  pop     rbx
0x180018a29  retn
```
