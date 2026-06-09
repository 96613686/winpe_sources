# CProtectionTicket::CProtectionTicket(unsigned __int64,ulong,uchar *,std::vector<uchar,wil::secure_allocator<uchar>> &&,_WINBIO_RPC_NGC_AUTHORIZATION *)

- ea: `0x180058d68`
- end: `0x180058e17`
- name: `??0CProtectionTicket@@QEAA@_KKPEAE$$QEAV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAU_WINBIO_RPC_NGC_AUTHORIZATION@@@Z`
- size: `175`
- prototype: `__int64 __fastcall(__int64, __int64, int, void *, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180092c3c`

## callees

- `0x180058e20`
- `0x180069cc8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180058dd0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180058dd0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180058dbc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180058dbc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180058dad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180058dad`

## pseudocode

```c
__int64 __fastcall CProtectionTicket::CProtectionTicket(
        __int64 a1,
        __int64 a2,
        int a3,
        void *a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v7; // rdx
  DWORD LengthSid; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)a1 = a2;
  v7 = a5;
  *(_DWORD *)(a1 + 8) = a3;
  std::vector<AuthorizedPresence>::vector<AuthorizedPresence>(a1 + 88, v7);
  *(_QWORD *)(a1 + 112) = a6;
  memset_0((void *)(a1 + 12), 0, 0x44u);
  LengthSid = GetLengthSid(a4);
  CopySid(LengthSid, (PSID)(a1 + 12), a4);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(_QWORD *)(a1 + 80) = *(_QWORD *)&SystemTimeAsFileTime + 200000000LL;
  return a1;
}

```

## disassembly

```asm
0x180058d68  mov     [rsp+arg_8], rbx
0x180058d6d  mov     [rsp+arg_10], rsi
0x180058d72  push    rdi
0x180058d73  sub     rsp, 20h
0x180058d77  mov     [rcx], rdx
0x180058d7a  mov     rsi, rcx
0x180058d7d  mov     rdx, [rsp+28h+arg_20]
0x180058d82  mov     rdi, r9
0x180058d85  mov     [rcx+8], r8d
0x180058d89  add     rcx, 58h ; 'X'
0x180058d8d  call    ??0?$vector@UAuthorizedPresence@@V?$allocator@UAuthorizedPresence@@@std@@@std@@QEAA@$$QEAV01@@Z; std::vector<AuthorizedPresence>::vector<AuthorizedPresence>(std::vector<AuthorizedPresence> &&)
0x180058d92  mov     rdx, [rsp+28h+arg_28]
0x180058d97  lea     rcx, [rsi+0Ch]; void *
0x180058d9b  mov     [rsi+70h], rdx
0x180058d9f  xor     edx, edx; Val
0x180058da1  lea     r8d, [rdx+44h]; Size
0x180058da5  call    memset_0
0x180058daa  mov     rcx, rdi; pSid
0x180058dad  call    cs:__imp_GetLengthSid
0x180058db3  mov     r8, rdi; pSourceSid
0x180058db6  lea     rdx, [rsi+0Ch]; pDestinationSid
0x180058dba  mov     ecx, eax; nDestinationSidLength
0x180058dbc  call    cs:__imp_CopySid
0x180058dc2  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180058dc7  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180058dd0  call    cs:__imp_GetSystemTimeAsFileTime
0x180058dd6  mov     eax, [rsp+28h+SystemTimeAsFileTime.dwHighDateTime]
0x180058dda  mov     rbx, [rsp+28h+arg_8]
0x180058ddf  mov     dword ptr [rsp+28h+arg_28+4], eax
0x180058de3  mov     eax, [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x180058de7  mov     dword ptr [rsp+28h+arg_28], eax
0x180058deb  mov     rax, [rsp+28h+arg_28]
0x180058df0  add     rax, 0BEBC200h
0x180058df6  mov     [rsp+28h+arg_28], rax
0x180058dfb  shr     rax, 20h
0x180058dff  mov     [rsi+54h], eax
0x180058e02  mov     eax, dword ptr [rsp+28h+arg_28]
0x180058e06  mov     [rsi+50h], eax
0x180058e09  mov     rax, rsi
0x180058e0c  mov     rsi, [rsp+28h+arg_10]
0x180058e11  add     rsp, 20h
0x180058e15  pop     rdi
0x180058e16  retn
```
