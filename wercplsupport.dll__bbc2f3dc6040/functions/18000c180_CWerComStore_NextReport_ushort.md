# CWerComStore::NextReport(ushort * *)

- ea: `0x18000c180`
- end: `0x18000c1d6`
- name: `?NextReport@CWerComStore@@UEAAJPEAPEAG@Z`
- size: `86`
- prototype: `__int64 __fastcall(CWerComStore *this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x18000c180`
- `0x18000fd54`

## pseudocode

```c
__int64 __fastcall CWerComStore::NextReport(CWerComStore *this, unsigned __int16 **a2)
{
  int Report; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  Report = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( Report >= 0 )
    Report = CWerComStore::_NextReport((CWerComStore *)((char *)this - 24), a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)Report;
}

```

## disassembly

```asm
0x18000c180  mov     rax, rsp
0x18000c183  mov     [rax+8], rbx
0x18000c187  mov     [rax+10h], rsi
0x18000c18b  push    rdi
0x18000c18c  sub     rsp, 20h
0x18000c190  mov     rsi, rcx
0x18000c193  mov     dword ptr [rax+18h], 2
0x18000c19a  lea     rcx, [rax+18h]; this
0x18000c19e  mov     rdi, rdx
0x18000c1a1  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18000c1a6  mov     ebx, eax
0x18000c1a8  test    eax, eax
0x18000c1aa  js      short loc_18000C1BA
0x18000c1ac  lea     rcx, [rsi-18h]; this
0x18000c1b0  mov     rdx, rdi; unsigned __int16 **
0x18000c1b3  call    ?_NextReport@CWerComStore@@QEAAJPEAPEAG@Z; CWerComStore::_NextReport(ushort * *)
0x18000c1b8  mov     ebx, eax
0x18000c1ba  lea     rcx, [rsp+28h+arg_10]; this
0x18000c1bf  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18000c1c4  mov     rsi, [rsp+28h+arg_8]
0x18000c1c9  mov     eax, ebx
0x18000c1cb  mov     rbx, [rsp+28h+arg_0]
0x18000c1d0  add     rsp, 20h
0x18000c1d4  pop     rdi
0x18000c1d5  retn
```
