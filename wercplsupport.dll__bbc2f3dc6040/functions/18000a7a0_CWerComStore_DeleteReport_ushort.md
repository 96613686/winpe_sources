# CWerComStore::DeleteReport(ushort *)

- ea: `0x18000a7a0`
- end: `0x18000a7f6`
- name: `?DeleteReport@CWerComStore@@UEAAJPEAG@Z`
- size: `86`
- prototype: `int(CWerComStore *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x18000a7a0`
- `0x18000f148`

## pseudocode

```c
__int64 __fastcall CWerComStore::DeleteReport(CWerComStore *this, unsigned __int16 *a2)
{
  int v4; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  v4 = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( v4 >= 0 )
    v4 = CWerComStore::_DeleteReport((CWerComStore *)((char *)this - 24), a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000a7a0  mov     rax, rsp
0x18000a7a3  mov     [rax+8], rbx
0x18000a7a7  mov     [rax+10h], rsi
0x18000a7ab  push    rdi
0x18000a7ac  sub     rsp, 20h
0x18000a7b0  mov     rsi, rcx
0x18000a7b3  mov     dword ptr [rax+18h], 2
0x18000a7ba  lea     rcx, [rax+18h]; this
0x18000a7be  mov     rdi, rdx
0x18000a7c1  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18000a7c6  mov     ebx, eax
0x18000a7c8  test    eax, eax
0x18000a7ca  js      short loc_18000A7DA
0x18000a7cc  lea     rcx, [rsi-18h]; this
0x18000a7d0  mov     rdx, rdi; unsigned __int16 *
0x18000a7d3  call    ?_DeleteReport@CWerComStore@@QEAAJPEAG@Z; CWerComStore::_DeleteReport(ushort *)
0x18000a7d8  mov     ebx, eax
0x18000a7da  lea     rcx, [rsp+28h+arg_10]; this
0x18000a7df  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18000a7e4  mov     rsi, [rsp+28h+arg_8]
0x18000a7e9  mov     eax, ebx
0x18000a7eb  mov     rbx, [rsp+28h+arg_0]
0x18000a7f0  add     rsp, 20h
0x18000a7f4  pop     rdi
0x18000a7f5  retn
```
