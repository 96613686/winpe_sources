# CWerComReport::CancelSubmitReport(void)

- ea: `0x18000a3c0`
- end: `0x18000a408`
- name: `?CancelSubmitReport@CWerComReport@@UEAAJXZ`
- size: `72`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x18000a3c0`

## import_xrefs

- `wer!WerpCancelUpload` at `0x18000a3e9`
- `wer!WerpCancelUpload` at `0x18000a3e9`

## pseudocode

```c
__int64 __fastcall CWerComReport::CancelSubmitReport(CWerComReport *this)
{
  int v2; // ebx
  int v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 2;
  v2 = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v4);
  if ( v2 >= 0 )
    v2 = WerpCancelUpload(*((_QWORD *)this + 1));
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000a3c0  mov     [rsp+arg_0], rbx
0x18000a3c5  push    rdi
0x18000a3c6  sub     rsp, 20h
0x18000a3ca  mov     rdi, rcx
0x18000a3cd  mov     [rsp+28h+arg_8], 2
0x18000a3d5  lea     rcx, [rsp+28h+arg_8]; this
0x18000a3da  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18000a3df  mov     ebx, eax
0x18000a3e1  test    eax, eax
0x18000a3e3  js      short loc_18000A3F1
0x18000a3e5  mov     rcx, [rdi+8]
0x18000a3e9  call    cs:__imp_WerpCancelUpload
0x18000a3ef  mov     ebx, eax
0x18000a3f1  lea     rcx, [rsp+28h+arg_8]; this
0x18000a3f6  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18000a3fb  mov     eax, ebx
0x18000a3fd  mov     rbx, [rsp+28h+arg_0]
0x18000a402  add     rsp, 20h
0x18000a406  pop     rdi
0x18000a407  retn
```
