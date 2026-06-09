# CTpSrvTxRate::OnTimer(CTimer<CTpSrvTxRate> *)

- ea: `0x18000de34`
- end: `0x18000e1d6`
- name: `?OnTimer@CTpSrvTxRate@@QEAAXPEAV?$CTimer@VCTpSrvTxRate@@@@@Z`
- size: `930`
- prototype: `__int64 __fastcall(CTpSrvTxRate *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e1e0`

## callees

- `0x180008d38`
- `0x18000daa4`
- `0x18000dbb8`
- `0x18000de34`
- `0x18001a9a8`
- `0x1800227d4`
- `0x1800247d4`
- `0x180025850`
- `0x180026694`
- `0x180026d3a`
- `0x180026d46`
- `0x180026d70`

## import_xrefs

- `KERNEL32!ChangeTimerQueueTimer` at `0x18000e15b`
- `KERNEL32!ChangeTimerQueueTimer` at `0x18000e15b`
- `KERNEL32!GetCurrentThreadId` at `0x18000e105`
- `KERNEL32!GetCurrentThreadId` at `0x18000e105`
- `KERNEL32!SwitchToThread` at `0x18000e121`
- `KERNEL32!SwitchToThread` at `0x18000e121`
- `KERNEL32!GetLastError` at `0x18000e165`
- `KERNEL32!GetLastError` at `0x18000e165`
- `KERNEL32!LeaveCriticalSection` at `0x18000e04b`
- `KERNEL32!LeaveCriticalSection` at `0x18000e0c1`
- `KERNEL32!LeaveCriticalSection` at `0x18000e197`
- `KERNEL32!LeaveCriticalSection` at `0x18000e04b`
- `KERNEL32!LeaveCriticalSection` at `0x18000e0c1`
- `KERNEL32!LeaveCriticalSection` at `0x18000e197`
- `KERNEL32!EnterCriticalSection` at `0x18000de67`
- `KERNEL32!EnterCriticalSection` at `0x18000e03b`
- `KERNEL32!EnterCriticalSection` at `0x18000de67`
- `KERNEL32!EnterCriticalSection` at `0x18000e03b`

## pseudocode

```c
void __fastcall CTpSrvTxRate::OnTimer(LPCRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // r12
  int v3; // r13d
  int v4; // r14d
  int OwningThread_high; // edi
  int v6; // ecx
  int v7; // ebp
  int v8; // r15d
  unsigned int v9; // ebx
  LPCRITICAL_SECTION v10; // rcx
  unsigned int v11; // r12d
  unsigned __int64 v12; // rax
  struct _RTL_CRITICAL_SECTION *v13; // rax
  __int64 v14; // r8
  LPCRITICAL_SECTION v15; // rcx
  int v16; // ebx
  unsigned int v17; // eax
  LPCRITICAL_SECTION v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // rdi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rbx
  char *v21; // rsi
  DWORD LastError; // ebx
  int v23; // edi
  DWORD CurrentThreadId; // ecx
  signed __int32 v25; // eax
  const char *v26; // rdx
  char *v27; // [rsp+40h] [rbp-48h] BYREF
  int v28; // [rsp+48h] [rbp-40h]
  struct _RTL_CRITICAL_SECTION *v29; // [rsp+90h] [rbp+8h]
  int v30; // [rsp+98h] [rbp+10h]

  v1 = *this;
  v3 = 0;
  v29 = *this;
  v4 = 0;
  OwningThread_high = 0;
  EnterCriticalSection(*this);
  v6 = (_DWORD)this[14] & 3;
  v7 = 1;
  if ( v6 == 3 && this[19][2].LockCount )
  {
    v8 = 1;
    goto LABEL_4;
  }
  v8 = 0;
  if ( v6 == 3 || ((_BYTE)this[14] & 1) != 0 )
  {
LABEL_4:
    v30 = 0;
    if ( v8 )
      OwningThread_high = HIDWORD(this[19][2].OwningThread);
    goto LABEL_6;
  }
  v30 = 1;
  OwningThread_high = HIDWORD(this[19][2].LockSemaphore);
LABEL_6:
  v9 = 2 * OwningThread_high;
  if ( 2 * OwningThread_high )
  {
    if ( v9 > 0x1D4C0 )
      v9 = 120000;
    if ( (unsigned int)(2 * OwningThread_high) < 0x3E8 )
      v9 = 1000;
  }
  else
  {
    v9 = 5000;
  }
  if ( 100 * *((_DWORD *)this + 32) < v9 )
  {
    v10 = this[17];
    *((_DWORD *)this + 32) = 0;
    if ( v10 )
    {
      operator delete(v10);
      this[17] = 0;
    }
    *((_DWORD *)this + 36) = 0;
    v11 = v9 / 0x64;
    v12 = 4LL * (v9 / 0x64);
    if ( !is_mul_ok(v9 / 0x64, 4u) )
      v12 = -1;
    v13 = (struct _RTL_CRITICAL_SECTION *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
    if ( v13 )
    {
      *((_DWORD *)this + 32) = v11;
      this[17] = v13;
      memset_0(v13, 0, 4LL * v11);
      *((_DWORD *)this + 36) = 0;
    }
    else
    {
      v3 = 8;
    }
    if ( g_ErrLibTraceFunctionEx )
    {
      v14 = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)&this[1][55].OwningThread, 0);
      g_ErrLibTraceFunctionEx(
        0x10000u,
        L"WDSMCTP[0x%x] Tracking tx rate: DataInterval=%ums, WaitTime=%ums; status 0x%08x",
        v14,
        v9,
        OwningThread_high,
        v3);
    }
    v1 = v29;
  }
  v15 = this[17];
  v16 = *((_DWORD *)this + 6);
  if ( v15 )
  {
    memmove_0(v15, (char *)&v15->DebugInfo + 4, 4LL * (unsigned int)(*((_DWORD *)this + 32) - 1));
    *((_DWORD *)&this[17]->DebugInfo + (unsigned int)(*((_DWORD *)this + 32) - 1)) = v16;
    v17 = *((_DWORD *)this + 36);
    if ( v17 < *((_DWORD *)this + 32) )
      *((_DWORD *)this + 36) = v17 + 1;
  }
  *((_DWORD *)this + 6) = 0;
  if ( *((_DWORD *)this + 24) == 1 )
  {
    if ( this[15] )
    {
      if ( CStopwatch::CurrentMs((CStopwatch *)(this + 20)) - (unsigned __int64)this[15] > 0x4E20 )
        v4 = 1;
    }
    else
    {
      v18 = this[2];
      v19 = *(struct _RTL_CRITICAL_SECTION **)&v18->LockCount;
      EnterCriticalSection(v19);
      DebugInfo = v18[11].DebugInfo;
      LeaveCriticalSection(v19);
      if ( DebugInfo )
        this[15] = (LPCRITICAL_SECTION)CStopwatch::CurrentMs((CStopwatch *)(this + 20));
    }
    if ( v8 || v30 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&this[1][56], 0) == *((_DWORD *)this + 22) )
      {
        v7 = 0;
        LeaveCriticalSection(v1);
        if ( v4 )
        {
          if ( ((_BYTE)this[14] & 3) == 3 )
            CTpSrvTxRate::ProcessAutoKick((CTpSrvTxRate *)this);
          else
            CTpSrvTxRate::ProcessMultistream((CTpSrvTxRate *)this);
        }
      }
      else
      {
        *((_DWORD *)this + 22) = _InterlockedExchangeAdd((volatile signed __int32 *)&this[1][56], 0);
      }
    }
  }
  v21 = (char *)(this + 4);
  v28 = 0;
  v27 = v21;
  LastError = 0;
  while ( 1 )
  {
    v23 = 0;
    if ( *((_DWORD *)v21 + 2) )
      break;
LABEL_48:
    SwitchToThread();
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v25 = _InterlockedCompareExchange((volatile signed __int32 *)v21, CurrentThreadId, 0);
    if ( !v25 || v25 == CurrentThreadId )
      break;
    if ( (unsigned int)++v23 >= *((_DWORD *)v21 + 2) )
      goto LABEL_48;
  }
  _InterlockedAdd((volatile signed __int32 *)v21 + 1, 1u);
  v28 = 1;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v21 + 10, 0) == 1 )
  {
    LastError = 5023;
  }
  else if ( !ChangeTimerQueueTimer(*((HANDLE *)v21 + 2), *((HANDLE *)v21 + 3), 0x64u, 0xFFFFFFFE) )
  {
    LastError = GetLastError();
  }
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(&v27);
  ElValidateWin32(LastError, v26, "base\\eco\\wds\\transport\\server\\mc\\tpsrvtxrate.cpp", 0x285u);
  if ( v7 )
    LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x18000de34  mov     [rsp+arg_10], rbx
0x18000de39  mov     [rsp+arg_8], rdx
0x18000de3e  push    rbp
0x18000de3f  push    rsi
0x18000de40  push    rdi
0x18000de41  push    r12
0x18000de43  push    r13
0x18000de45  push    r14
0x18000de47  push    r15
0x18000de49  sub     rsp, 50h
0x18000de4d  mov     r12, [rcx]
0x18000de50  mov     rsi, rcx
0x18000de53  xor     r13d, r13d
0x18000de56  mov     [rsp+88h+arg_0], r12
0x18000de5e  mov     rcx, r12; lpCriticalSection
0x18000de61  mov     r14d, r13d
0x18000de64  mov     edi, r13d
0x18000de67  call    cs:__imp_EnterCriticalSection
0x18000de6d  mov     ecx, [rsi+70h]
0x18000de70  lea     edx, [r13+1]
0x18000de74  and     ecx, 3
0x18000de77  mov     ebp, edx
0x18000de79  cmp     ecx, 3
0x18000de7c  jnz     short loc_18000DEB3
0x18000de7e  mov     rax, [rsi+98h]
0x18000de85  cmp     [rax+58h], r13d
0x18000de89  jz      short loc_18000DEB3
0x18000de8b  mov     r15d, edx
0x18000de8e  mov     dword ptr [rsp+88h+arg_8], r13d
0x18000de96  test    r15d, r15d
0x18000de99  jz      short loc_18000DEA5
0x18000de9b  mov     rax, [rsi+98h]
0x18000dea2  mov     edi, [rax+64h]
0x18000dea5  lea     ebx, [rdi+rdi]
0x18000dea8  test    ebx, ebx
0x18000deaa  jnz     short loc_18000DED3
0x18000deac  mov     ebx, 1388h
0x18000deb1  jmp     short loc_18000DEE9
0x18000deb3  mov     r15d, r13d
0x18000deb6  cmp     ecx, 3
0x18000deb9  jz      short loc_18000DE8E
0x18000debb  test    [rsi+70h], dl
0x18000debe  jnz     short loc_18000DE8E
0x18000dec0  mov     rax, [rsi+98h]
0x18000dec7  mov     dword ptr [rsp+88h+arg_8], edx
0x18000dece  mov     edi, [rax+6Ch]
0x18000ded1  jmp     short loc_18000DEA5
0x18000ded3  mov     ecx, 1D4C0h
0x18000ded8  mov     eax, ebx
0x18000deda  cmp     ebx, ecx
0x18000dedc  cmova   ebx, ecx
0x18000dedf  mov     ecx, 3E8h
0x18000dee4  cmp     eax, ecx
0x18000dee6  cmovb   ebx, ecx
0x18000dee9  imul    eax, [rsi+80h], 64h ; 'd'
0x18000def0  cmp     eax, ebx
0x18000def2  jnb     loc_18000DFCD
0x18000def8  mov     rcx, [rsi+88h]; void *
0x18000deff  mov     [rsi+80h], r13d
0x18000df06  test    rcx, rcx
0x18000df09  jz      short loc_18000DF17
0x18000df0b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000df10  mov     [rsi+88h], r13
0x18000df17  mov     eax, 51EB851Fh
0x18000df1c  mov     [rsi+90h], r13d
0x18000df23  mul     ebx
0x18000df25  mov     eax, 4
0x18000df2a  mov     r12d, edx
0x18000df2d  shr     r12d, 5
0x18000df31  mov     ecx, r12d
0x18000df34  mul     rcx
0x18000df37  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000df3e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000df45  cmovo   rax, rcx
0x18000df49  mov     rcx, rax; unsigned __int64
0x18000df4c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000df51  test    rax, rax
0x18000df54  jnz     short loc_18000DF5C
0x18000df56  lea     r13d, [rax+8]
0x18000df5a  jmp     short loc_18000DF82
0x18000df5c  mov     r8d, r12d
0x18000df5f  xor     edx, edx; Val
0x18000df61  shl     r8, 2; Size
0x18000df65  mov     rcx, rax; void *
0x18000df68  mov     [rsi+80h], r12d
0x18000df6f  mov     [rsi+88h], rax
0x18000df76  call    memset_0
0x18000df7b  and     [rsi+90h], r13d
0x18000df82  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, r14; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000df89  jz      short loc_18000DFC0
0x18000df8b  mov     rax, [rsi+8]
0x18000df8f  xor     r8d, r8d
0x18000df92  lock xadd [rax+8A8h], r8d
0x18000df9b  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000dfa2  lea     rdx, aWdsmctp0xXTrac; "WDSMCTP[0x%x] Tracking tx rate: DataInt"...
0x18000dfa9  mov     [rsp+88h+var_60], r13d
0x18000dfae  mov     r9d, ebx
0x18000dfb1  mov     ecx, 10000h
0x18000dfb6  mov     [rsp+88h+var_68], edi
0x18000dfba  call    cs:__guard_dispatch_icall_fptr
0x18000dfc0  mov     r12, [rsp+88h+arg_0]
0x18000dfc8  mov     edx, ebp
0x18000dfca  xor     r13d, r13d
0x18000dfcd  mov     rcx, [rsi+88h]; void *
0x18000dfd4  mov     ebx, [rsi+18h]
0x18000dfd7  test    rcx, rcx
0x18000dfda  jz      short loc_18000E01D
0x18000dfdc  mov     r8d, [rsi+80h]
0x18000dfe3  sub     r8d, edx
0x18000dfe6  lea     rdx, [rcx+4]; Src
0x18000dfea  shl     r8, 2; Size
0x18000dfee  call    memmove_0
0x18000dff3  mov     ecx, [rsi+80h]
0x18000dff9  mov     edx, ebp
0x18000dffb  mov     rax, [rsi+88h]
0x18000e002  sub     ecx, edx
0x18000e004  mov     [rax+rcx*4], ebx
0x18000e007  mov     eax, [rsi+90h]
0x18000e00d  cmp     eax, [rsi+80h]
0x18000e013  jnb     short loc_18000E01D
0x18000e015  inc     eax
0x18000e017  mov     [rsi+90h], eax
0x18000e01d  mov     [rsi+18h], r13d
0x18000e021  cmp     [rsi+60h], edx
0x18000e024  jnz     loc_18000E0E5
0x18000e02a  cmp     [rsi+78h], r13
0x18000e02e  jnz     short loc_18000E068
0x18000e030  mov     rbx, [rsi+10h]
0x18000e034  mov     rdi, [rbx+8]
0x18000e038  mov     rcx, rdi; lpCriticalSection
0x18000e03b  call    cs:__imp_EnterCriticalSection
0x18000e041  mov     rbx, [rbx+1B8h]
0x18000e048  mov     rcx, rdi; lpCriticalSection
0x18000e04b  call    cs:__imp_LeaveCriticalSection
0x18000e051  test    rbx, rbx
0x18000e054  jz      short loc_18000E084
0x18000e056  lea     rcx, [rsi+0A0h]; this
0x18000e05d  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x18000e062  mov     [rsi+78h], rax
0x18000e066  jmp     short loc_18000E084
0x18000e068  lea     rcx, [rsi+0A0h]; this
0x18000e06f  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x18000e074  sub     rax, [rsi+78h]
0x18000e078  cmp     rax, 4E20h
0x18000e07e  mov     eax, ebp
0x18000e080  cmova   r14d, eax
0x18000e084  test    r15d, r15d
0x18000e087  jnz     short loc_18000E093
0x18000e089  cmp     dword ptr [rsp+88h+arg_8], r13d
0x18000e091  jz      short loc_18000E0E5
0x18000e093  mov     rax, [rsi+8]
0x18000e097  mov     ecx, r13d
0x18000e09a  lock xadd [rax+8C0h], ecx
0x18000e0a2  cmp     ecx, [rsi+58h]
0x18000e0a5  jz      short loc_18000E0BB
0x18000e0a7  mov     rcx, [rsi+8]
0x18000e0ab  mov     eax, r13d
0x18000e0ae  lock xadd [rcx+8C0h], eax
0x18000e0b6  mov     [rsi+58h], eax
0x18000e0b9  jmp     short loc_18000E0E5
0x18000e0bb  mov     rcx, r12; lpCriticalSection
0x18000e0be  mov     ebp, r13d
0x18000e0c1  call    cs:__imp_LeaveCriticalSection
0x18000e0c7  test    r14d, r14d
0x18000e0ca  jz      short loc_18000E0E5
0x18000e0cc  mov     eax, [rsi+70h]
0x18000e0cf  mov     rcx, rsi; this
0x18000e0d2  and     eax, 3
0x18000e0d5  cmp     al, 3
0x18000e0d7  jnz     short loc_18000E0E0
0x18000e0d9  call    ?ProcessAutoKick@CTpSrvTxRate@@AEAAXXZ; CTpSrvTxRate::ProcessAutoKick(void)
0x18000e0de  jmp     short loc_18000E0E5
0x18000e0e0  call    ?ProcessMultistream@CTpSrvTxRate@@AEAAXXZ; CTpSrvTxRate::ProcessMultistream(void)
0x18000e0e5  add     rsi, 20h ; ' '
0x18000e0e9  mov     [rsp+88h+var_40], r13d
0x18000e0ee  mov     [rsp+88h+var_48], rsi
0x18000e0f3  mov     ebx, r13d
0x18000e0f6  mov     edi, r13d
0x18000e0f9  cmp     [rsi+8], r13d
0x18000e0fd  jbe     short loc_18000E121
0x18000e0ff  mov     r14d, 1
0x18000e105  call    cs:__imp_GetCurrentThreadId
0x18000e10b  mov     ecx, eax
0x18000e10d  xor     eax, eax
0x18000e10f  lock cmpxchg [rsi], ecx
0x18000e113  jz      short loc_18000E129
0x18000e115  cmp     eax, ecx
0x18000e117  jz      short loc_18000E129
0x18000e119  add     edi, r14d
0x18000e11c  cmp     edi, [rsi+8]
0x18000e11f  jb      short loc_18000E105
0x18000e121  call    cs:__imp_SwitchToThread
0x18000e127  jmp     short loc_18000E0F6
0x18000e129  lock add [rsi+4], r14d
0x18000e12e  mov     [rsp+88h+var_40], r14d
0x18000e133  mov     eax, r13d
0x18000e136  lock xadd [rsi+28h], eax
0x18000e13b  cmp     eax, r14d
0x18000e13e  jnz     short loc_18000E147
0x18000e140  mov     ebx, 139Fh
0x18000e145  jmp     short loc_18000E16D
0x18000e147  mov     rdx, [rsi+18h]; Timer
0x18000e14b  mov     r9d, 0FFFFFFFEh; Period
0x18000e151  mov     rcx, [rsi+10h]; TimerQueue
0x18000e155  mov     r8d, 64h ; 'd'; DueTime
0x18000e15b  call    cs:__imp_ChangeTimerQueueTimer
0x18000e161  test    eax, eax
0x18000e163  jnz     short loc_18000E16D
0x18000e165  call    cs:__imp_GetLastError
0x18000e16b  mov     ebx, eax
0x18000e16d  lea     rcx, [rsp+88h+var_48]
0x18000e172  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18000e177  mov     r9d, 285h; unsigned int
0x18000e17d  lea     r8, aBaseEcoWdsTran; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000e184  mov     ecx, ebx; unsigned int
0x18000e186  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e18b  test    ebp, ebp
0x18000e18d  jz      short loc_18000E1BE
0x18000e18f  add     ebp, 0FFFFFFFFh
0x18000e192  jnz     short loc_18000E19D
0x18000e194  mov     rcx, r12; lpCriticalSection
0x18000e197  call    cs:__imp_LeaveCriticalSection
0x18000e19d  test    ebp, ebp
0x18000e19f  jz      short loc_18000E1BE
0x18000e1a1  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x18000e1a8  mov     [rsp+88h+var_68], r13d; int
0x18000e1ad  mov     edx, 16Ah; unsigned int
0x18000e1b2  lea     rcx, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x18000e1b9  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18000e1be  mov     rbx, [rsp+88h+arg_10]
0x18000e1c6  add     rsp, 50h
0x18000e1ca  pop     r15
0x18000e1cc  pop     r14
0x18000e1ce  pop     r13
0x18000e1d0  pop     r12
0x18000e1d2  pop     rdi
0x18000e1d3  pop     rsi
0x18000e1d4  pop     rbp
0x18000e1d5  retn
```
