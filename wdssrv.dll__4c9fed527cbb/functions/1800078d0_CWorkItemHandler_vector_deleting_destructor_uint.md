# CWorkItemHandler::`vector deleting destructor'(uint)

- ea: `0x1800078d0`
- end: `0x180007946`
- name: `??_ECWorkItemHandler@@UEAAPEAXI@Z`
- size: `118`
- prototype: `void *__fastcall(CWorkItemHandler *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800078d0`

## import_xrefs

- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180007926`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180007926`
- `WdsServerCommonLib!??1CCompPort@@QEAA@XZ` at `0x180007902`
- `WdsServerCommonLib!??1CCompPort@@QEAA@XZ` at `0x180007902`
- `WdsServerCommonLib!??1ICpRecvRequest@@MEAA@XZ` at `0x180007911`
- `WdsServerCommonLib!??1ICpRecvRequest@@MEAA@XZ` at `0x180007911`
- `WdsServerCommonLib!?Shutdown@CCompPort@@QEAAKXZ` at `0x1800078f2`
- `WdsServerCommonLib!?Shutdown@CCompPort@@QEAAKXZ` at `0x1800078f2`

## pseudocode

```c
CWorkItemHandler *__fastcall CWorkItemHandler::`vector deleting destructor'(CWorkItemHandler *this, char a2)
{
  *(_QWORD *)this = &CWorkItemHandler::`vftable';
  CCompPort::Shutdown((CWorkItemHandler *)((char *)this + 8));
  CCompPort::~CCompPort((CWorkItemHandler *)((char *)this + 8));
  ICpRecvRequest::~ICpRecvRequest(this);
  if ( (a2 & 1) != 0 )
    WdsPrivateHpFree(this);
  return this;
}

```

## disassembly

```asm
0x1800078d0  mov     [rsp+arg_0], rbx
0x1800078d5  mov     [rsp+arg_8], rsi
0x1800078da  push    rdi
0x1800078db  sub     rsp, 20h
0x1800078df  lea     rax, ??_7CWorkItemHandler@@6B@; const CWorkItemHandler::`vftable'
0x1800078e6  mov     rsi, rcx
0x1800078e9  mov     [rcx], rax
0x1800078ec  mov     edi, edx
0x1800078ee  add     rcx, 8
0x1800078f2  call    cs:__imp_?Shutdown@CCompPort@@QEAAKXZ; CCompPort::Shutdown(void)
0x1800078f9  nop     dword ptr [rax+rax+00h]
0x1800078fe  lea     rcx, [rsi+8]
0x180007902  call    cs:__imp_??1CCompPort@@QEAA@XZ; CCompPort::~CCompPort(void)
0x180007909  nop     dword ptr [rax+rax+00h]
0x18000790e  mov     rcx, rsi
0x180007911  call    cs:__imp_??1ICpRecvRequest@@MEAA@XZ; ICpRecvRequest::~ICpRecvRequest(void)
0x180007918  nop     dword ptr [rax+rax+00h]
0x18000791d  test    dil, 1
0x180007921  jz      short loc_180007932
0x180007923  mov     rcx, rsi
0x180007926  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x18000792d  nop     dword ptr [rax+rax+00h]
0x180007932  mov     rbx, [rsp+28h+arg_0]
0x180007937  mov     rax, rsi
0x18000793a  mov     rsi, [rsp+28h+arg_8]
0x18000793f  add     rsp, 20h
0x180007943  pop     rdi
0x180007944  retn
```
