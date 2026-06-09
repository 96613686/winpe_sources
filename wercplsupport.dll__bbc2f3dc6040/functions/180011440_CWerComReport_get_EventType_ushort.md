# CWerComReport::get_EventType(ushort * *)

- ea: `0x180011440`
- end: `0x180011496`
- name: `?get_EventType@CWerComReport@@UEAAJPEAPEAG@Z`
- size: `86`
- prototype: `int(CWerComReport *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x1800101bc`
- `0x180011440`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_EventType(CWerComReport *this, unsigned __int16 **a2)
{
  int EventType; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  EventType = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( EventType >= 0 )
    EventType = CWerComReport::_get_EventType((CWerComReport *)((char *)this - 24), a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)EventType;
}

```

## disassembly

```asm
0x180011440  mov     rax, rsp
0x180011443  mov     [rax+8], rbx
0x180011447  mov     [rax+10h], rsi
0x18001144b  push    rdi
0x18001144c  sub     rsp, 20h
0x180011450  mov     rsi, rcx
0x180011453  mov     dword ptr [rax+18h], 2
0x18001145a  lea     rcx, [rax+18h]; this
0x18001145e  mov     rdi, rdx
0x180011461  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011466  mov     ebx, eax
0x180011468  test    eax, eax
0x18001146a  js      short loc_18001147A
0x18001146c  lea     rcx, [rsi-18h]; this
0x180011470  mov     rdx, rdi; unsigned __int16 **
0x180011473  call    ?_get_EventType@CWerComReport@@QEAAJPEAPEAG@Z; CWerComReport::_get_EventType(ushort * *)
0x180011478  mov     ebx, eax
0x18001147a  lea     rcx, [rsp+28h+arg_10]; this
0x18001147f  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011484  mov     rsi, [rsp+28h+arg_8]
0x180011489  mov     eax, ebx
0x18001148b  mov     rbx, [rsp+28h+arg_0]
0x180011490  add     rsp, 20h
0x180011494  pop     rdi
0x180011495  retn
```
