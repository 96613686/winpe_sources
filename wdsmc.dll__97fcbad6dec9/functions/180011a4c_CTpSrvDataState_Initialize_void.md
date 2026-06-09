# CTpSrvDataState::Initialize(void)

- ea: `0x180011a4c`
- end: `0x180011bb5`
- name: `?Initialize@CTpSrvDataState@@QEAAKXZ`
- size: `361`
- prototype: `unsigned int __fastcall(CTpSrvDataState *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800148b4`

## callees

- `0x180008d38`
- `0x18000d898`
- `0x180011a4c`
- `0x180011bbc`
- `0x180014040`
- `0x180025850`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x180011afc`
- `KERNEL32!CreateTimerQueueTimer` at `0x180011afc`
- `KERNEL32!GetCurrentThreadId` at `0x180011a99`
- `KERNEL32!GetCurrentThreadId` at `0x180011a99`
- `KERNEL32!SwitchToThread` at `0x180011ab4`
- `KERNEL32!SwitchToThread` at `0x180011ab4`
- `KERNEL32!GetLastError` at `0x180011b06`
- `KERNEL32!GetLastError` at `0x180011b06`

## pseudocode

```c
__int64 __fastcall CTpSrvDataState::Initialize(CTpSrvDataState *this)
{
  char *v1; // r14
  __int64 v2; // rax
  char *v3; // rbx
  DWORD LastError; // ebp
  int v6; // esi
  DWORD CurrentThreadId; // ecx
  signed __int32 v8; // eax
  const char *v9; // rdx
  unsigned int v10; // ebx
  const char *v11; // rdx
  const char *v12; // rdx
  const char *v13; // rdx
  char *v15; // [rsp+40h] [rbp-18h] BYREF
  int v16; // [rsp+48h] [rbp-10h]

  v1 = (char *)this + 48;
  v2 = *((_QWORD *)this + 2) + 2280LL;
  *((_DWORD *)this + 106) = 1;
  v3 = (char *)this + 128;
  *((_QWORD *)this + 3) = v2;
  LastError = 0;
  v15 = (char *)this + 128;
  v16 = 0;
  while ( 1 )
  {
    v6 = 0;
    if ( *((_DWORD *)v3 + 2) )
      break;
LABEL_6:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = _InterlockedCompareExchange((volatile signed __int32 *)v3, CurrentThreadId, 0);
    if ( !v8 || v8 == CurrentThreadId )
      break;
    if ( (unsigned int)++v6 >= *((_DWORD *)v3 + 2) )
      goto LABEL_6;
  }
  _InterlockedIncrement((volatile signed __int32 *)v3 + 1);
  *((_QWORD *)v3 + 2) = 0;
  *((_QWORD *)v3 + 6) = 0;
  *((_DWORD *)v3 + 10) = 0;
  v16 = 1;
  *((_QWORD *)v3 + 4) = v1;
  if ( !CreateTimerQueueTimer(
          (PHANDLE)v3 + 3,
          0,
          (WAITORTIMERCALLBACK)CTimer<CTpSrvSPM>::_TimerCallback,
          v3,
          0xFFFFFFFE,
          0xFFFFFFFE,
          1u) )
    LastError = GetLastError();
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v15);
  v10 = ElValidateWin32(LastError, v9, "base\\eco\\wds\\transport\\server\\mc\\tpsrvspm.cpp", 0x3Eu);
  if ( !ElValidateWin32(v10, v11, "base\\eco\\wds\\transport\\server\\mc\\tpsrvdatastate.cpp", 0x6Bu) )
  {
    v10 = CTpSrvTxRate::Initialize((CTpSrvDataState *)((char *)this + 192));
    if ( !ElValidateWin32(v10, v12, "base\\eco\\wds\\transport\\server\\mc\\tpsrvdatastate.cpp", 0x72u) )
    {
      v10 = CTimer<CTpSrvDataState>::Initialize((char *)this + 592);
      ElValidateWin32(v10, v13, "base\\eco\\wds\\transport\\server\\mc\\tpsrvdatastate.cpp", 0x79u);
    }
  }
  if ( v10 )
    CTpSrvDataState::Shutdown(this);
  return v10;
}

```

## disassembly

```asm
0x180011a4c  mov     r11, rsp
0x180011a4f  mov     [r11+8], rbx
0x180011a53  mov     [r11+10h], rbp
0x180011a57  mov     [r11+18h], rsi
0x180011a5b  mov     [r11+20h], rdi
0x180011a5f  push    r14
0x180011a61  sub     rsp, 50h
0x180011a65  mov     rax, [rcx+10h]
0x180011a69  lea     r14, [rcx+30h]
0x180011a6d  add     rax, 8E8h
0x180011a73  mov     dword ptr [rcx+1A8h], 1
0x180011a7d  lea     rbx, [r14+50h]
0x180011a81  mov     [rcx+18h], rax
0x180011a85  xor     ebp, ebp
0x180011a87  mov     [r11-18h], rbx
0x180011a8b  and     [rsp+58h+var_10], ebp
0x180011a8f  mov     rdi, rcx
0x180011a92  xor     esi, esi
0x180011a94  cmp     [rbx+8], esi
0x180011a97  jbe     short loc_180011AB4
0x180011a99  call    cs:__imp_GetCurrentThreadId
0x180011a9f  mov     ecx, eax
0x180011aa1  xor     eax, eax
0x180011aa3  lock cmpxchg [rbx], ecx
0x180011aa7  jz      short loc_180011ABC
0x180011aa9  cmp     eax, ecx
0x180011aab  jz      short loc_180011ABC
0x180011aad  inc     esi
0x180011aaf  cmp     esi, [rbx+8]
0x180011ab2  jb      short loc_180011A99
0x180011ab4  call    cs:__imp_SwitchToThread
0x180011aba  jmp     short loc_180011A92
0x180011abc  lock inc dword ptr [rbx+4]
0x180011ac0  and     [rbx+10h], rbp
0x180011ac4  lea     rcx, [rbx+18h]; phNewTimer
0x180011ac8  and     [rbx+30h], rbp
0x180011acc  lea     r8, ?_TimerCallback@?$CTimer@VCTpSrvSPM@@@@SAXPEAXE@Z; Callback
0x180011ad3  and     [rbx+28h], ebp
0x180011ad6  mov     eax, 0FFFFFFFEh
0x180011adb  mov     [rsp+58h+Flags], 1; Flags
0x180011ae3  mov     r9, rbx; Parameter
0x180011ae6  mov     [rsp+58h+Period], eax; Period
0x180011aea  xor     edx, edx; TimerQueue
0x180011aec  mov     [rsp+58h+DueTime], eax; DueTime
0x180011af0  mov     [rsp+58h+var_10], 1
0x180011af8  mov     [rbx+20h], r14
0x180011afc  call    cs:__imp_CreateTimerQueueTimer
0x180011b02  test    eax, eax
0x180011b04  jnz     short loc_180011B0E
0x180011b06  call    cs:__imp_GetLastError
0x180011b0c  mov     ebp, eax
0x180011b0e  lea     rcx, [rsp+58h+var_18]
0x180011b13  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x180011b18  mov     r9d, 3Eh ; '>'; unsigned int
0x180011b1e  lea     r8, aBaseEcoWdsTran_7; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180011b25  mov     ecx, ebp; unsigned int
0x180011b27  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011b2c  lea     rsi, aBaseEcoWdsTran_21; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180011b33  mov     r9d, 6Bh ; 'k'; unsigned int
0x180011b39  mov     r8, rsi; char *
0x180011b3c  mov     ecx, eax; unsigned int
0x180011b3e  mov     ebx, eax
0x180011b40  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011b45  test    eax, eax
0x180011b47  jnz     short loc_180011B8C
0x180011b49  lea     rcx, [rdi+0C0h]; this
0x180011b50  call    ?Initialize@CTpSrvTxRate@@QEAAKXZ; CTpSrvTxRate::Initialize(void)
0x180011b55  mov     r9d, 72h ; 'r'; unsigned int
0x180011b5b  mov     r8, rsi; char *
0x180011b5e  mov     ecx, eax; unsigned int
0x180011b60  mov     ebx, eax
0x180011b62  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011b67  test    eax, eax
0x180011b69  jnz     short loc_180011B8C
0x180011b6b  lea     rcx, [rdi+250h]; Parameter
0x180011b72  mov     rdx, rdi
0x180011b75  call    ?Initialize@?$CTimer@VCTpSrvDataState@@@@QEAAKPEAVCTpSrvDataState@@PEAXKK1K@Z; CTimer<CTpSrvDataState>::Initialize(CTpSrvDataState *,void *,ulong,ulong,void *,ulong)
0x180011b7a  mov     r9d, 79h ; 'y'; unsigned int
0x180011b80  mov     r8, rsi; char *
0x180011b83  mov     ecx, eax; unsigned int
0x180011b85  mov     ebx, eax
0x180011b87  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011b8c  test    ebx, ebx
0x180011b8e  jz      short loc_180011B98
0x180011b90  mov     rcx, rdi; this
0x180011b93  call    ?Shutdown@CTpSrvDataState@@QEAAKXZ; CTpSrvDataState::Shutdown(void)
0x180011b98  mov     rbp, [rsp+58h+arg_8]
0x180011b9d  mov     eax, ebx
0x180011b9f  mov     rbx, [rsp+58h+arg_0]
0x180011ba4  mov     rsi, [rsp+58h+arg_10]
0x180011ba9  mov     rdi, [rsp+58h+arg_18]
0x180011bae  add     rsp, 50h
0x180011bb2  pop     r14
0x180011bb4  retn
```
