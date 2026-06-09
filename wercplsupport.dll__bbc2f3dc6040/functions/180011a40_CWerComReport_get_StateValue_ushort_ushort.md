# CWerComReport::get_StateValue(ushort *,ushort * *)

- ea: `0x180011a40`
- end: `0x180011a90`
- name: `?get_StateValue@CWerComReport@@UEAAJPEAGPEAPEAG@Z`
- size: `80`
- prototype: `int(CWerComReport *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x180010d10`
- `0x180011a40`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_StateValue(CWerComReport *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  int StateValue; // ebx
  int v8; // [rsp+68h] [rbp+20h] BYREF

  v8 = 2;
  StateValue = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v8);
  if ( StateValue >= 0 )
    StateValue = CWerComReport::_get_StateValue((CWerComReport *)((char *)this - 24), a2, a3);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v8);
  return (unsigned int)StateValue;
}

```

## disassembly

```asm
0x180011a40  push    rbx
0x180011a42  push    rbp
0x180011a43  push    rsi
0x180011a44  push    rdi
0x180011a45  sub     rsp, 28h
0x180011a49  mov     rbp, rcx
0x180011a4c  mov     [rsp+48h+arg_18], 2
0x180011a54  lea     rcx, [rsp+48h+arg_18]; this
0x180011a59  mov     rdi, r8
0x180011a5c  mov     rsi, rdx
0x180011a5f  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011a64  mov     ebx, eax
0x180011a66  test    eax, eax
0x180011a68  js      short loc_180011A7B
0x180011a6a  lea     rcx, [rbp-18h]; this
0x180011a6e  mov     r8, rdi; unsigned __int16 **
0x180011a71  mov     rdx, rsi; unsigned __int16 *
0x180011a74  call    ?_get_StateValue@CWerComReport@@QEAAJPEAGPEAPEAG@Z; CWerComReport::_get_StateValue(ushort *,ushort * *)
0x180011a79  mov     ebx, eax
0x180011a7b  lea     rcx, [rsp+48h+arg_18]; this
0x180011a80  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011a85  mov     eax, ebx
0x180011a87  add     rsp, 28h
0x180011a8b  pop     rdi
0x180011a8c  pop     rsi
0x180011a8d  pop     rbp
0x180011a8e  pop     rbx
0x180011a8f  retn
```
