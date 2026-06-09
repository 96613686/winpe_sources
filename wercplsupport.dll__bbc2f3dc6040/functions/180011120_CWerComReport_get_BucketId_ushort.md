# CWerComReport::get_BucketId(ushort * *)

- ea: `0x180011120`
- end: `0x180011176`
- name: `?get_BucketId@CWerComReport@@UEAAJPEAPEAG@Z`
- size: `86`
- prototype: `int(CWerComReport *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x18000fef4`
- `0x180011120`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_BucketId(CWerComReport *this, unsigned __int16 **a2)
{
  int BucketId; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  BucketId = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( BucketId >= 0 )
    BucketId = CWerComReport::_get_BucketId((CWerComReport *)((char *)this - 24), a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)BucketId;
}

```

## disassembly

```asm
0x180011120  mov     rax, rsp
0x180011123  mov     [rax+8], rbx
0x180011127  mov     [rax+10h], rsi
0x18001112b  push    rdi
0x18001112c  sub     rsp, 20h
0x180011130  mov     rsi, rcx
0x180011133  mov     dword ptr [rax+18h], 2
0x18001113a  lea     rcx, [rax+18h]; this
0x18001113e  mov     rdi, rdx
0x180011141  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011146  mov     ebx, eax
0x180011148  test    eax, eax
0x18001114a  js      short loc_18001115A
0x18001114c  lea     rcx, [rsi-18h]; this
0x180011150  mov     rdx, rdi; unsigned __int16 **
0x180011153  call    ?_get_BucketId@CWerComReport@@QEAAJPEAPEAG@Z; CWerComReport::_get_BucketId(ushort * *)
0x180011158  mov     ebx, eax
0x18001115a  lea     rcx, [rsp+28h+arg_10]; this
0x18001115f  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011164  mov     rsi, [rsp+28h+arg_8]
0x180011169  mov     eax, ebx
0x18001116b  mov     rbx, [rsp+28h+arg_0]
0x180011170  add     rsp, 20h
0x180011174  pop     rdi
0x180011175  retn
```
