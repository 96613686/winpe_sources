# PfIuPeriodicSync

- ea: `0x18005159c`
- end: `0x18005178f`
- name: `PfIuPeriodicSync`
- size: `499`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18003d1c0`
- `0x180051420`

## callees

- `0x18003cbe4`
- `0x18003cffc`
- `0x18005159c`
- `0x180051798`
- `0x180051bd4`
- `0x180054cdc`
- `0x1800595f0`
- `0x180078746`
- `0x1800b64c0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180051684`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180051684`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005171c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005171c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005161f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005161f`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180051655`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180051655`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180051615`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x180051615`

## pseudocode

```c
__int64 __fastcall PfIuPeriodicSync(__int64 a1, int a2)
{
  int v4; // eax
  __int16 v5; // si
  __int64 v6; // rcx
  DWORD LastError; // ebx
  __int16 v8; // r14
  __int16 v9; // ax
  __int16 v10; // si
  _DWORD *v11; // rdx
  _DWORD *v12; // rsi
  __int64 v13; // r9
  __int64 i; // rdx
  __int16 v15; // cx
  struct _RTL_CRITICAL_SECTION *v16; // r10
  _WORD v18[2]; // [rsp+20h] [rbp-40h] BYREF
  __int16 v19; // [rsp+24h] [rbp-3Ch] BYREF
  struct _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+28h] [rbp-38h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-28h] BYREF
  __int64 v22; // [rsp+48h] [rbp-18h] BYREF

  *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
  SystemPowerStatus.BatteryFullLifeTime = 0;
  SystemTime = 0;
  PfIuCheckAndEmitHistoryMeasures();
  v4 = *(_DWORD *)(a1 + 16);
  if ( v4 )
  {
    if ( v4 == 1 )
    {
      v5 = 4;
    }
    else if ( v4 == 2 )
    {
      v5 = 8;
    }
    else
    {
      v5 = 0;
    }
  }
  else
  {
    v5 = 1;
  }
  if ( GetSystemPowerStatus(&SystemPowerStatus) )
  {
    v8 = 16;
    if ( SystemPowerStatus.ACLineStatus )
      v9 = 16;
    else
      v9 = 0;
    v19 = v5 | v9;
    v10 = PfIuEnumerateBatteries(a1);
    GetLocalTime(&SystemTime);
    if ( !SystemPowerStatus.ACLineStatus )
      v8 = 0;
    v18[0] = v8 | (a2 != 0 ? 2 : 0) | (v10 << 8);
    RtlAcquireSRWLockExclusive(a1 + 48);
    v11 = *(_DWORD **)(a1 + 64);
    v12 = &v11[1401 * ((*v11 - 1) & 1LL)];
    memcpy_0(v12 + 2, &v11[1401 * (*v11 & 1LL) + 2], 0x15E4u);
    v13 = SystemTime.wMinute / 0xFu + 4 * (SystemTime.wHour + 168);
    for ( i = 0; i != 4; ++i )
    {
      v15 = *((_WORD *)v12 + v13 + 22);
      v13 = (unsigned int)(v13 + 672);
      *((_WORD *)&v22 + i) = v15;
    }
    ((void (__fastcall *)(_DWORD *, _WORD *, __int16 *, struct _SYSTEMTIME *))PfIuHistoryEntryAdd)(
      v12 + 2,
      v18,
      &v19,
      &SystemTime);
    _InterlockedAdd64(*(volatile signed __int64 **)(a1 + 64), 1u);
    RtlReleaseSRWLockExclusive(a1 + 48);
    PfIuPredictorStatsUpdate(a1, v18, &v22);
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  v22 = PfsActionItemGetCurrentTime(v6) + 9000000000LL;
  PfsActionItemQueueEx(v16 + 43, 0x33u, (unsigned __int64 *)&v22, 0);
  return LastError;
}

```

## disassembly

```asm
0x18005159c  mov     [rsp-28h+arg_8], rbx
0x1800515a1  mov     [rsp-28h+arg_10], rsi
0x1800515a6  push    rbp
0x1800515a7  push    rdi
0x1800515a8  push    r12
0x1800515aa  push    r14
0x1800515ac  push    r15
0x1800515ae  mov     rbp, rsp
0x1800515b1  sub     rsp, 60h
0x1800515b5  mov     rax, cs:__security_cookie
0x1800515bc  xor     rax, rsp
0x1800515bf  mov     [rbp+var_10], rax
0x1800515c3  xor     eax, eax
0x1800515c5  xorps   xmm0, xmm0
0x1800515c8  mov     qword ptr [rbp+SystemPowerStatus.ACLineStatus], rax
0x1800515cc  mov     r15d, edx
0x1800515cf  mov     [rbp+SystemPowerStatus.BatteryFullLifeTime], eax
0x1800515d2  mov     rdi, rcx
0x1800515d5  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800515d9  call    PfIuCheckAndEmitHistoryMeasures
0x1800515de  mov     eax, [rdi+10h]
0x1800515e1  mov     r12d, 2
0x1800515e7  lea     ebx, [r12-1]
0x1800515ec  test    eax, eax
0x1800515ee  jnz     short loc_1800515F5
0x1800515f0  movzx   esi, bx
0x1800515f3  jmp     short loc_180051611
0x1800515f5  cmp     eax, ebx
0x1800515f7  jnz     short loc_180051600
0x1800515f9  mov     esi, 4
0x1800515fe  jmp     short loc_180051611
0x180051600  cmp     eax, r12d
0x180051603  jnz     short loc_18005160C
0x180051605  mov     esi, 8
0x18005160a  jmp     short loc_180051611
0x18005160c  xor     eax, eax
0x18005160e  movzx   esi, ax
0x180051611  lea     rcx, [rbp+SystemPowerStatus]; lpSystemPowerStatus
0x180051615  call    cs:__imp_GetSystemPowerStatus
0x18005161b  test    eax, eax
0x18005161d  jnz     short loc_18005162C
0x18005161f  call    cs:__imp_GetLastError
0x180051625  mov     ebx, eax
0x180051627  jmp     loc_180051734
0x18005162c  cmp     [rbp+SystemPowerStatus.ACLineStatus], 0
0x180051630  mov     r14d, 10h
0x180051636  jz      short loc_18005163E
0x180051638  movzx   eax, r14w
0x18005163c  jmp     short loc_180051640
0x18005163e  xor     eax, eax
0x180051640  or      ax, si
0x180051643  mov     rcx, rdi
0x180051646  mov     [rbp+var_3C], ax
0x18005164a  call    PfIuEnumerateBatteries
0x18005164f  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180051653  mov     esi, eax
0x180051655  call    cs:__imp_GetLocalTime
0x18005165b  cmp     [rbp+SystemPowerStatus.ACLineStatus], 0
0x18005165f  jnz     short loc_180051667
0x180051661  xor     eax, eax
0x180051663  movzx   r14d, ax
0x180051667  shl     si, 8
0x18005166b  lea     rcx, [rdi+30h]
0x18005166f  neg     r15d
0x180051672  sbb     ax, ax
0x180051675  and     ax, r12w
0x180051679  or      si, ax
0x18005167c  or      si, r14w
0x180051680  mov     [rbp+var_40], si
0x180051684  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18005168a  mov     rdx, [rdi+40h]
0x18005168e  mov     r8d, 15E4h; Size
0x180051694  mov     ecx, [rdx]
0x180051696  lea     eax, [rcx-1]
0x180051699  and     rcx, rbx
0x18005169c  and     rax, rbx
0x18005169f  imul    rsi, rax, 15E4h
0x1800516a6  imul    rax, rcx, 15E4h
0x1800516ad  add     rsi, rdx
0x1800516b0  add     rdx, 8
0x1800516b4  lea     rcx, [rsi+8]; void *
0x1800516b8  add     rdx, rax; Src
0x1800516bb  call    memcpy_0
0x1800516c0  movzx   ecx, [rbp+SystemTime.wMinute]
0x1800516c4  mov     eax, 88888889h
0x1800516c9  movzx   r9d, [rbp+SystemTime.wHour]
0x1800516ce  mul     ecx
0x1800516d0  add     r9d, 0A8h
0x1800516d7  shr     edx, 3
0x1800516da  lea     r9d, [rdx+r9*4]
0x1800516de  xor     edx, edx
0x1800516e0  movzx   ecx, word ptr [rsi+r9*2+2Ch]
0x1800516e6  lea     r9d, [r9+2A0h]
0x1800516ed  mov     word ptr [rbp+rdx*2+var_18], cx
0x1800516f2  add     rdx, rbx
0x1800516f5  cmp     rdx, 4
0x1800516f9  jnz     short loc_1800516E0
0x1800516fb  lea     r9, [rbp+SystemTime]
0x1800516ff  lea     r8, [rbp+var_3C]
0x180051703  lea     rdx, [rbp+var_40]
0x180051707  lea     rcx, [rsi+8]
0x18005170b  call    PfIuHistoryEntryAdd
0x180051710  mov     rax, [rdi+40h]
0x180051714  lock add [rax], rbx
0x180051718  lea     rcx, [rdi+30h]
0x18005171c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180051722  lea     r8, [rbp+var_18]
0x180051726  mov     rcx, rdi
0x180051729  lea     rdx, [rbp+var_40]
0x18005172d  call    PfIuPredictorStatsUpdate
0x180051732  xor     ebx, ebx
0x180051734  mov     r10, cs:PfSvcGlobals
0x18005173b  call    PfsActionItemGetCurrentTime
0x180051740  xor     r9d, r9d
0x180051743  lea     r8, [rbp+var_18]
0x180051747  mov     rcx, 218711A00h
0x180051751  add     rax, rcx
0x180051754  lea     rcx, [r10+6B8h]; lpCriticalSection
0x18005175b  mov     [rbp+var_18], rax
0x18005175f  lea     edx, [r9+33h]
0x180051763  call    PfsActionItemQueueEx
0x180051768  mov     eax, ebx
0x18005176a  mov     rcx, [rbp+var_10]
0x18005176e  xor     rcx, rsp; StackCookie
0x180051771  call    __security_check_cookie
0x180051776  lea     r11, [rsp+60h+var_s0]
0x18005177b  mov     rbx, [r11+38h]
0x18005177f  mov     rsi, [r11+40h]
0x180051783  mov     rsp, r11
0x180051786  pop     r15
0x180051788  pop     r14
0x18005178a  pop     r12
0x18005178c  pop     rdi
0x18005178d  pop     rbp
0x18005178e  retn
```
