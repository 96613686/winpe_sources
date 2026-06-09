# CWerComReportStringList<&WerComListConstCountFunc<11>(void *,ulong *),&WerpGetUIParamByIndex(void *,ulong,ushort const * *)>::get_Count(long *)

- ea: `0x180011240`
- end: `0x1800112fe`
- name: `?get_Count@?$CWerComReportStringList@$1??$WerComListConstCountFunc@$0L@@@YAJPEAXPEAK@Z$1?WerpGetUIParamByIndex@@YAJ0KPEAPEBG@Z@@UEAAJPEAJ@Z`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006c9c`
- `0x180007d20`
- `0x180007fe0`
- `0x18000e35c`
- `0x180011240`

## pseudocode

```c
__int64 __fastcall CWerComReportStringList<&long WerComListConstCountFunc<11>(void *,unsigned long *),&long WerpGetUIParamByIndex(void *,unsigned long,unsigned short const * *)>::get_Count(
        __int64 a1,
        _DWORD *a2)
{
  int WerApiLock; // ebx
  struct CWerComReport *v5; // rdx
  __int64 v6; // rax
  int v8; // [rsp+40h] [rbp+18h] BYREF
  __int64 v9; // [rsp+48h] [rbp+20h] BYREF

  v8 = 2;
  WerApiLock = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v8);
  if ( WerApiLock >= 0 )
  {
    v5 = *(struct CWerComReport **)(a1 + 16);
    v9 = 0;
    WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)&v9, v5);
    if ( WerApiLock >= 0 )
    {
      v6 = v9;
      *a2 = 11;
      if ( v6 )
        _InterlockedExchange((volatile __int32 *)(v6 + 48), 0);
      WerApiLock = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
          (unsigned int)WerApiLock);
      if ( v9 )
        _InterlockedExchange((volatile __int32 *)(v9 + 48), 0);
    }
  }
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v8);
  return (unsigned int)WerApiLock;
}

```

## disassembly

```asm
0x180011240  mov     rax, rsp
0x180011243  mov     [rax+8], rbx
0x180011247  mov     [rax+10h], rsi
0x18001124b  push    rdi
0x18001124c  sub     rsp, 20h
0x180011250  mov     rsi, rcx
0x180011253  mov     dword ptr [rax+18h], 2
0x18001125a  lea     rcx, [rax+18h]; this
0x18001125e  mov     rdi, rdx
0x180011261  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011266  mov     ebx, eax
0x180011268  test    eax, eax
0x18001126a  js      short loc_1800112E2
0x18001126c  mov     rdx, [rsi+10h]; struct CWerComReport *
0x180011270  lea     rcx, [rsp+28h+arg_18]; this
0x180011275  mov     [rsp+28h+arg_18], 0
0x18001127e  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x180011283  mov     ebx, eax
0x180011285  test    eax, eax
0x180011287  jns     short loc_1800112CB
0x180011289  mov     rcx, cs:WPP_GLOBAL_Control
0x180011290  lea     rax, WPP_GLOBAL_Control
0x180011297  cmp     rcx, rax
0x18001129a  jz      short loc_1800112BA
0x18001129c  test    byte ptr [rcx+1Ch], 1
0x1800112a0  jz      short loc_1800112BA
0x1800112a2  mov     rcx, [rcx+10h]
0x1800112a6  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x1800112ad  mov     edx, 11h
0x1800112b2  mov     r9d, ebx
0x1800112b5  call    WPP_SF_d
0x1800112ba  mov     rax, [rsp+28h+arg_18]
0x1800112bf  test    rax, rax
0x1800112c2  jz      short loc_1800112E2
0x1800112c4  xor     ecx, ecx
0x1800112c6  xchg    ecx, [rax+30h]
0x1800112c9  jmp     short loc_1800112E2
0x1800112cb  mov     rax, [rsp+28h+arg_18]
0x1800112d0  mov     dword ptr [rdi], 0Bh
0x1800112d6  test    rax, rax
0x1800112d9  jz      short loc_1800112E0
0x1800112db  xor     ecx, ecx
0x1800112dd  xchg    ecx, [rax+30h]
0x1800112e0  xor     ebx, ebx
0x1800112e2  lea     rcx, [rsp+28h+arg_10]; this
0x1800112e7  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x1800112ec  mov     rsi, [rsp+28h+arg_8]
0x1800112f1  mov     eax, ebx
0x1800112f3  mov     rbx, [rsp+28h+arg_0]
0x1800112f8  add     rsp, 20h
0x1800112fc  pop     rdi
0x1800112fd  retn
```
