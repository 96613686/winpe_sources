# CWerComReport::get_LegacyBucketId(ushort * *)

- ea: `0x180011740`
- end: `0x180011796`
- name: `?get_LegacyBucketId@CWerComReport@@UEAAJPEAPEAG@Z`
- size: `86`
- prototype: `int(CWerComReport *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x180010734`
- `0x180011740`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_LegacyBucketId(CWerComReport *this, unsigned __int16 **a2)
{
  int LegacyBucketId; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  LegacyBucketId = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( LegacyBucketId >= 0 )
    LegacyBucketId = CWerComReport::_get_LegacyBucketId((CWerComReport *)((char *)this - 24), a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)LegacyBucketId;
}

```

## disassembly

```asm
0x180011740  mov     rax, rsp
0x180011743  mov     [rax+8], rbx
0x180011747  mov     [rax+10h], rsi
0x18001174b  push    rdi
0x18001174c  sub     rsp, 20h
0x180011750  mov     rsi, rcx
0x180011753  mov     dword ptr [rax+18h], 2
0x18001175a  lea     rcx, [rax+18h]; this
0x18001175e  mov     rdi, rdx
0x180011761  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011766  mov     ebx, eax
0x180011768  test    eax, eax
0x18001176a  js      short loc_18001177A
0x18001176c  lea     rcx, [rsi-18h]; this
0x180011770  mov     rdx, rdi; unsigned __int16 **
0x180011773  call    ?_get_LegacyBucketId@CWerComReport@@QEAAJPEAPEAG@Z; CWerComReport::_get_LegacyBucketId(ushort * *)
0x180011778  mov     ebx, eax
0x18001177a  lea     rcx, [rsp+28h+arg_10]; this
0x18001177f  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011784  mov     rsi, [rsp+28h+arg_8]
0x180011789  mov     eax, ebx
0x18001178b  mov     rbx, [rsp+28h+arg_0]
0x180011790  add     rsp, 20h
0x180011794  pop     rdi
0x180011795  retn
```
