# CWerComStore::ArchiveReport(ushort *,ushort * *)

- ea: `0x18000a360`
- end: `0x18000a3b0`
- name: `?ArchiveReport@CWerComStore@@UEAAJPEAGPEAPEAG@Z`
- size: `80`
- prototype: `int(CWerComStore *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x18000a360`
- `0x18000ef80`

## pseudocode

```c
__int64 __fastcall CWerComStore::ArchiveReport(CWerComStore *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  int v6; // ebx
  int v8; // [rsp+68h] [rbp+20h] BYREF

  v8 = 2;
  v6 = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v8);
  if ( v6 >= 0 )
    v6 = CWerComStore::_ArchiveReport((CWerComStore *)((char *)this - 24), a2, a3);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000a360  push    rbx
0x18000a362  push    rbp
0x18000a363  push    rsi
0x18000a364  push    rdi
0x18000a365  sub     rsp, 28h
0x18000a369  mov     rbp, rcx
0x18000a36c  mov     [rsp+48h+arg_18], 2
0x18000a374  lea     rcx, [rsp+48h+arg_18]; this
0x18000a379  mov     rdi, r8
0x18000a37c  mov     rsi, rdx
0x18000a37f  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18000a384  mov     ebx, eax
0x18000a386  test    eax, eax
0x18000a388  js      short loc_18000A39B
0x18000a38a  lea     rcx, [rbp-18h]; this
0x18000a38e  mov     r8, rdi; unsigned __int16 **
0x18000a391  mov     rdx, rsi; unsigned __int16 *
0x18000a394  call    ?_ArchiveReport@CWerComStore@@QEAAJPEAGPEAPEAG@Z; CWerComStore::_ArchiveReport(ushort *,ushort * *)
0x18000a399  mov     ebx, eax
0x18000a39b  lea     rcx, [rsp+48h+arg_18]; this
0x18000a3a0  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18000a3a5  mov     eax, ebx
0x18000a3a7  add     rsp, 28h
0x18000a3ab  pop     rdi
0x18000a3ac  pop     rsi
0x18000a3ad  pop     rbp
0x18000a3ae  pop     rbx
0x18000a3af  retn
```
