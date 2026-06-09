# CWerComStore::LoadReport(ushort *,IWerReport * *)

- ea: `0x18000bd90`
- end: `0x18000bde0`
- name: `?LoadReport@CWerComStore@@UEAAJPEAGPEAPEAUIWerReport@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWerComStore *this, unsigned __int16 *, struct IWerReport **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x18000bd90`
- `0x18000fb0c`

## pseudocode

```c
__int64 __fastcall CWerComStore::LoadReport(CWerComStore *this, unsigned __int16 *a2, struct IWerReport **a3)
{
  int Report; // ebx
  int v8; // [rsp+68h] [rbp+20h] BYREF

  v8 = 2;
  Report = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v8);
  if ( Report >= 0 )
    Report = CWerComStore::_LoadReport((CWerComStore *)((char *)this - 24), a2, a3);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v8);
  return (unsigned int)Report;
}

```

## disassembly

```asm
0x18000bd90  push    rbx
0x18000bd92  push    rbp
0x18000bd93  push    rsi
0x18000bd94  push    rdi
0x18000bd95  sub     rsp, 28h
0x18000bd99  mov     rbp, rcx
0x18000bd9c  mov     [rsp+48h+arg_18], 2
0x18000bda4  lea     rcx, [rsp+48h+arg_18]; this
0x18000bda9  mov     rdi, r8
0x18000bdac  mov     rsi, rdx
0x18000bdaf  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18000bdb4  mov     ebx, eax
0x18000bdb6  test    eax, eax
0x18000bdb8  js      short loc_18000BDCB
0x18000bdba  lea     rcx, [rbp-18h]; this
0x18000bdbe  mov     r8, rdi; struct IWerReport **
0x18000bdc1  mov     rdx, rsi; unsigned __int16 *
0x18000bdc4  call    ?_LoadReport@CWerComStore@@QEAAJPEAGPEAPEAUIWerReport@@@Z; CWerComStore::_LoadReport(ushort *,IWerReport * *)
0x18000bdc9  mov     ebx, eax
0x18000bdcb  lea     rcx, [rsp+48h+arg_18]; this
0x18000bdd0  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18000bdd5  mov     eax, ebx
0x18000bdd7  add     rsp, 28h
0x18000bddb  pop     rdi
0x18000bddc  pop     rsi
0x18000bddd  pop     rbp
0x18000bdde  pop     rbx
0x18000bddf  retn
```
