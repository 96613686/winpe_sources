# CWerComReport::get_ReportTime(unsigned __int64 *)

- ea: `0x180011980`
- end: `0x1800119d6`
- name: `?get_ReportTime@CWerComReport@@UEAAJPEA_K@Z`
- size: `86`
- prototype: `int(CWerComReport *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x180010b28`
- `0x180011980`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_ReportTime(CWerComReport *this, unsigned __int64 *a2)
{
  int ReportTime; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  ReportTime = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( ReportTime >= 0 )
    ReportTime = CWerComReport::_get_ReportTime((CWerComReport *)((char *)this - 24), a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)ReportTime;
}

```

## disassembly

```asm
0x180011980  mov     rax, rsp
0x180011983  mov     [rax+8], rbx
0x180011987  mov     [rax+10h], rsi
0x18001198b  push    rdi
0x18001198c  sub     rsp, 20h
0x180011990  mov     rsi, rcx
0x180011993  mov     dword ptr [rax+18h], 2
0x18001199a  lea     rcx, [rax+18h]; this
0x18001199e  mov     rdi, rdx
0x1800119a1  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x1800119a6  mov     ebx, eax
0x1800119a8  test    eax, eax
0x1800119aa  js      short loc_1800119BA
0x1800119ac  lea     rcx, [rsi-18h]; this
0x1800119b0  mov     rdx, rdi; unsigned __int64 *
0x1800119b3  call    ?_get_ReportTime@CWerComReport@@QEAAJPEA_K@Z; CWerComReport::_get_ReportTime(unsigned __int64 *)
0x1800119b8  mov     ebx, eax
0x1800119ba  lea     rcx, [rsp+28h+arg_10]; this
0x1800119bf  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x1800119c4  mov     rsi, [rsp+28h+arg_8]
0x1800119c9  mov     eax, ebx
0x1800119cb  mov     rbx, [rsp+28h+arg_0]
0x1800119d0  add     rsp, 20h
0x1800119d4  pop     rdi
0x1800119d5  retn
```
