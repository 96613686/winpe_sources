# CWerComReport::get_FileNames(IWerStringList * *)

- ea: `0x1800114a0`
- end: `0x1800114f6`
- name: `?get_FileNames@CWerComReport@@UEAAJPEAPEAUIWerStringList@@@Z`
- size: `86`
- prototype: `int(CWerComReport *__hidden this, struct IWerStringList **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x1800102f8`
- `0x1800114a0`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_FileNames(CWerComReport *this, struct IWerStringList **a2)
{
  int FileNames; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  FileNames = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( FileNames >= 0 )
    FileNames = CWerComReport::_get_FileNames((CWerComReport *)((char *)this - 24), a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)FileNames;
}

```

## disassembly

```asm
0x1800114a0  mov     rax, rsp
0x1800114a3  mov     [rax+8], rbx
0x1800114a7  mov     [rax+10h], rsi
0x1800114ab  push    rdi
0x1800114ac  sub     rsp, 20h
0x1800114b0  mov     rsi, rcx
0x1800114b3  mov     dword ptr [rax+18h], 2
0x1800114ba  lea     rcx, [rax+18h]; this
0x1800114be  mov     rdi, rdx
0x1800114c1  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x1800114c6  mov     ebx, eax
0x1800114c8  test    eax, eax
0x1800114ca  js      short loc_1800114DA
0x1800114cc  lea     rcx, [rsi-18h]; this
0x1800114d0  mov     rdx, rdi; struct IWerStringList **
0x1800114d3  call    ?_get_FileNames@CWerComReport@@QEAAJPEAPEAUIWerStringList@@@Z; CWerComReport::_get_FileNames(IWerStringList * *)
0x1800114d8  mov     ebx, eax
0x1800114da  lea     rcx, [rsp+28h+arg_10]; this
0x1800114df  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x1800114e4  mov     rsi, [rsp+28h+arg_8]
0x1800114e9  mov     eax, ebx
0x1800114eb  mov     rbx, [rsp+28h+arg_0]
0x1800114f0  add     rsp, 20h
0x1800114f4  pop     rdi
0x1800114f5  retn
```
