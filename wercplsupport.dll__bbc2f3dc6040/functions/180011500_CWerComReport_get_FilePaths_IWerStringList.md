# CWerComReport::get_FilePaths(IWerStringList * *)

- ea: `0x180011500`
- end: `0x180011556`
- name: `?get_FilePaths@CWerComReport@@UEAAJPEAPEAUIWerStringList@@@Z`
- size: `86`
- prototype: `int(CWerComReport *__hidden this, struct IWerStringList **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x180010400`
- `0x180011500`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_FilePaths(CWerComReport *this, struct IWerStringList **a2)
{
  int FilePaths; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  FilePaths = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( FilePaths >= 0 )
    FilePaths = CWerComReport::_get_FilePaths((CWerComReport *)((char *)this - 24), a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)FilePaths;
}

```

## disassembly

```asm
0x180011500  mov     rax, rsp
0x180011503  mov     [rax+8], rbx
0x180011507  mov     [rax+10h], rsi
0x18001150b  push    rdi
0x18001150c  sub     rsp, 20h
0x180011510  mov     rsi, rcx
0x180011513  mov     dword ptr [rax+18h], 2
0x18001151a  lea     rcx, [rax+18h]; this
0x18001151e  mov     rdi, rdx
0x180011521  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011526  mov     ebx, eax
0x180011528  test    eax, eax
0x18001152a  js      short loc_18001153A
0x18001152c  lea     rcx, [rsi-18h]; this
0x180011530  mov     rdx, rdi; struct IWerStringList **
0x180011533  call    ?_get_FilePaths@CWerComReport@@QEAAJPEAPEAUIWerStringList@@@Z; CWerComReport::_get_FilePaths(IWerStringList * *)
0x180011538  mov     ebx, eax
0x18001153a  lea     rcx, [rsp+28h+arg_10]; this
0x18001153f  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011544  mov     rsi, [rsp+28h+arg_8]
0x180011549  mov     eax, ebx
0x18001154b  mov     rbx, [rsp+28h+arg_0]
0x180011550  add     rsp, 20h
0x180011554  pop     rdi
0x180011555  retn
```
