# CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&WerpGetFilePathByIndex(void *,ulong,ushort const * *)>::get_Count(long *)

- ea: `0x180011310`
- end: `0x1800113d6`
- name: `?get_Count@?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?WerpGetFilePathByIndex@@YAJ0KPEAPEBG@Z@@UEAAJPEAJ@Z`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006c9c`
- `0x180007d20`
- `0x180007fe0`
- `0x18000e35c`
- `0x180011310`

## import_xrefs

- `wer!WerpGetNumFiles` at `0x18001139d`
- `wer!WerpGetNumFiles` at `0x18001139d`

## pseudocode

```c
__int64 __fastcall CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long WerpGetFilePathByIndex(void *,unsigned long,unsigned short const * *)>::get_Count(
        __int64 a1,
        _DWORD *a2)
{
  int WerApiLock; // ebx
  struct CWerComReport *v5; // rdx
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF
  int v9; // [rsp+58h] [rbp+20h] BYREF

  v9 = 2;
  WerApiLock = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v9);
  if ( WerApiLock >= 0 )
  {
    v5 = *(struct CWerComReport **)(a1 + 16);
    v8 = 0;
    v7[0] = 0;
    WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)v7, v5);
    if ( WerApiLock >= 0 )
    {
      WerApiLock = WerpGetNumFiles(*(_QWORD *)(a1 + 8), &v8);
      *a2 = v8;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
        (unsigned int)WerApiLock);
    }
    if ( v7[0] )
      _InterlockedExchange((volatile __int32 *)(v7[0] + 48LL), 0);
  }
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v9);
  return (unsigned int)WerApiLock;
}

```

## disassembly

```asm
0x180011310  mov     rax, rsp
0x180011313  mov     [rax+8], rbx
0x180011317  mov     [rax+10h], rsi
0x18001131b  push    rdi
0x18001131c  sub     rsp, 30h
0x180011320  mov     rdi, rcx
0x180011323  mov     dword ptr [rax+20h], 2
0x18001132a  lea     rcx, [rax+20h]; this
0x18001132e  mov     rsi, rdx
0x180011331  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011336  mov     ebx, eax
0x180011338  test    eax, eax
0x18001133a  js      short loc_1800113BA
0x18001133c  mov     rdx, [rdi+10h]; struct CWerComReport *
0x180011340  lea     rcx, [rsp+38h+var_18]; this
0x180011345  mov     [rsp+38h+arg_10], 0
0x18001134d  mov     [rsp+38h+var_18], 0
0x180011356  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x18001135b  mov     ebx, eax
0x18001135d  test    eax, eax
0x18001135f  jns     short loc_180011394
0x180011361  mov     rcx, cs:WPP_GLOBAL_Control
0x180011368  lea     rax, WPP_GLOBAL_Control
0x18001136f  cmp     rcx, rax
0x180011372  jz      short loc_1800113AB
0x180011374  test    byte ptr [rcx+1Ch], 1
0x180011378  jz      short loc_1800113AB
0x18001137a  mov     rcx, [rcx+10h]
0x18001137e  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180011385  mov     edx, 11h
0x18001138a  mov     r9d, ebx
0x18001138d  call    WPP_SF_d
0x180011392  jmp     short loc_1800113AB
0x180011394  mov     rcx, [rdi+8]
0x180011398  lea     rdx, [rsp+38h+arg_10]
0x18001139d  call    cs:__imp_WerpGetNumFiles
0x1800113a3  mov     ebx, eax
0x1800113a5  mov     eax, [rsp+38h+arg_10]
0x1800113a9  mov     [rsi], eax
0x1800113ab  mov     rax, [rsp+38h+var_18]
0x1800113b0  test    rax, rax
0x1800113b3  jz      short loc_1800113BA
0x1800113b5  xor     ecx, ecx
0x1800113b7  xchg    ecx, [rax+30h]
0x1800113ba  lea     rcx, [rsp+38h+arg_18]; this
0x1800113bf  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x1800113c4  mov     rsi, [rsp+38h+arg_8]
0x1800113c9  mov     eax, ebx
0x1800113cb  mov     rbx, [rsp+38h+arg_0]
0x1800113d0  add     rsp, 30h
0x1800113d4  pop     rdi
0x1800113d5  retn
```
