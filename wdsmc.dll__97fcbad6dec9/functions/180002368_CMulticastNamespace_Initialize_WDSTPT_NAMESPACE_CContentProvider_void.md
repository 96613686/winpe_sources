# CMulticastNamespace::Initialize(_WDSTPT_NAMESPACE *,CContentProvider *,void * *)

- ea: `0x180002368`
- end: `0x1800026b0`
- name: `?Initialize@CMulticastNamespace@@QEAAKPEAU_WDSTPT_NAMESPACE@@PEAVCContentProvider@@PEAPEAX@Z`
- size: `840`
- prototype: `unsigned int __fastcall(CMulticastNamespace *__hidden this, struct _WDSTPT_NAMESPACE *Src, LPCRITICAL_SECTION lpCriticalSection, void **)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180005f18`
- `0x180006488`

## callees

- `0x180002368`
- `0x1800026b8`
- `0x1800039f0`
- `0x180009cec`
- `0x180018da4`
- `0x180022744`
- `0x1800229c0`
- `0x180025850`
- `0x180026670`
- `0x180026d3a`
- `0x180026d70`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x180002664`
- `KERNEL32!GetSystemTime` at `0x180002664`
- `KERNEL32!LeaveCriticalSection` at `0x180002600`
- `KERNEL32!LeaveCriticalSection` at `0x180002600`
- `KERNEL32!EnterCriticalSection` at `0x1800023a9`
- `KERNEL32!EnterCriticalSection` at `0x1800023a9`
- `WdsDiag!WdsDiagRecordEvent` at `0x1800025be`
- `WdsDiag!WdsDiagRecordEvent` at `0x1800025be`

## string_xrefs

- `0x1800024f7`: `Scheduled`
- `0x180002514`: `WDSMCNS[%u:%s]: Namespace Registered - Type=%s, Provider='%s', Config=`%s'`

## pseudocode

```c
__int64 __fastcall CMulticastNamespace::Initialize(
        CMulticastNamespace *this,
        struct _WDSTPT_NAMESPACE *Src,
        LPCRITICAL_SECTION lpCriticalSection,
        void **a4)
{
  const char *v8; // rdx
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // ecx
  char *v12; // rdx
  const char *v13; // rdx
  const char *v14; // rdx
  __int64 v15; // rdx
  BOOL v16; // eax
  void (*v17)(const unsigned __int16 *, ...); // rax
  const wchar_t *v18; // r9
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rax
  const unsigned __int16 *v23; // r8
  CMulticastNotification *v24; // rcx
  void *v25; // r9
  __int64 v27; // r8
  const char *v28; // rdx
  __int64 v29; // [rsp+20h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-68h] BYREF
  __int64 v31; // [rsp+68h] [rbp-60h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-58h] BYREF

  v30 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v31 = 0;
  v9 = 0;
  *(_QWORD *)&SystemTime.wYear = 0;
  *(_QWORD *)&SystemTime.wHour = 0;
  if ( !*((_QWORD *)Src + 2)
    || !*((_QWORD *)Src + 4)
    || !*((_QWORD *)Src + 6)
    || !*((_QWORD *)Src + 5)
    || *((_DWORD *)Src + 14) )
  {
    goto LABEL_10;
  }
  if ( *((_DWORD *)Src + 2) == 1 )
  {
    v11 = *((_DWORD *)Src + 20);
  }
  else if ( *((_DWORD *)Src + 2) != 2 || (v10 = *((_DWORD *)Src + 20), v11 = v10, v10 != 1) && v10 != 2 )
  {
LABEL_10:
    v9 = 87;
    goto LABEL_11;
  }
  if ( v11 == 1 && *((_DWORD *)Src + 21) || (*((_BYTE *)Src + 84) & 1) != 0 && !*((_DWORD *)Src + 22) )
    goto LABEL_10;
  if ( (*((_BYTE *)Src + 84) & 2) != 0 )
  {
    GetSystemTime(&SystemTime);
    v9 = CDate::Diff((char *)Src + 92, &SystemTime, v27, &v31);
    if ( !ElValidateWin32(v9, v28, "base\\eco\\wds\\transport\\server\\mc\\mcnamespace.cpp", 0x6A2u) && v31 < 0 )
      v9 = -1054801653;
  }
LABEL_11:
  if ( !ElValidateWin32(v9, v8, "base\\eco\\wds\\transport\\server\\mc\\mcnamespace.cpp", 0x4Fu) )
  {
    v12 = (char *)qword_1800336E8 + 320;
    *((_DWORD *)this + 14) = _InterlockedIncrement((volatile signed __int32 *)&CMulticastNamespace::sm_uNextNamespaceId);
    memmove_0((char *)this + 184, v12, 0x9Cu);
    *((_QWORD *)this + 22) = lpCriticalSection;
    v9 = CContentProvider::OpenInstance(lpCriticalSection, *((const unsigned __int16 **)Src + 6), (void **)this + 44);
    if ( !ElValidateWin32(v9, v13, "base\\eco\\wds\\transport\\server\\mc\\mcnamespace.cpp", 0x63u) )
    {
      v9 = CMulticastNamespace::DuplicateNamespace(Src, (CMulticastNamespace *)((char *)this + 64));
      if ( !ElValidateWin32(v9, v14, "base\\eco\\wds\\transport\\server\\mc\\mcnamespace.cpp", 0x6Au) )
      {
        v15 = *((unsigned int *)this + 14);
        v16 = *((_DWORD *)this + 18) == 1;
        *((_QWORD *)this + 8) = v15;
        *((_DWORD *)this + 35) = v16;
        v17 = g_ErrLibTraceFunction;
        *((_DWORD *)this + 30) = 0;
        if ( v17 )
        {
          v18 = L"Scheduled";
          if ( *((_DWORD *)Src + 2) == 1 )
            v18 = L"AutoCast";
          v17(
            L"WDSMCNS[%u:%s]: Namespace Registered - Type=%s, Provider='%s', Config=`%s'",
            v15,
            *((_QWORD *)Src + 2),
            v18,
            *((_QWORD *)Src + 5),
            *((_QWORD *)Src + 6));
        }
        LODWORD(v29) = 1;
        CPerfCounters::Batch((CPerfCounters *)&qword_1800336A0, 1u, 0, 0, v29);
        _InterlockedExchange((volatile __int32 *)this + 85, 1);
        v19 = *((_QWORD *)this + 13);
        v20 = *((_QWORD *)this + 10);
        v30 = *((_DWORD *)this + 18);
        v21 = -1;
        v22 = -1;
        do
          ++v22;
        while ( *(_WORD *)(v19 + 2 * v22) );
        do
          ++v21;
        while ( *(_WORD *)(v20 + 2 * v21) );
        ((void (__fastcall *)(__int64, __int64, __int64, __int64, __int64, __int64, int, __int64, __int64, _QWORD, __int64, int *))WdsDiagRecordEvent)(
          2,
          19,
          3,
          1,
          2 * v21 + 2,
          v20,
          1,
          2 * v22 + 2,
          v19,
          0,
          4,
          &v30);
        v23 = (const unsigned __int16 *)*((_QWORD *)this + 10);
        v24 = (CMRSWLock *)((char *)qword_1800336E8 + 864);
        *((_DWORD *)this + 86) = 1;
        CMulticastNotification::AddNotification(v24, 1u, v23, v25);
        *a4 = (void *)*((unsigned int *)this + 14);
      }
    }
  }
  if ( v9 )
  {
    *((_DWORD *)this + 30) = 1;
    CMulticastNamespace::Shutdown(this);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v9;
}

```

## disassembly

```asm
0x180002368  mov     [rsp+arg_10], rbx
0x18000236d  push    rbp
0x18000236e  push    rsi
0x18000236f  push    rdi
0x180002370  push    r12
0x180002372  push    r13
0x180002374  push    r14
0x180002376  push    r15
0x180002378  sub     rsp, 90h
0x18000237f  mov     rax, cs:__security_cookie
0x180002386  xor     rax, rsp
0x180002389  mov     [rsp+0C8h+var_48], rax
0x180002391  mov     rsi, rcx
0x180002394  xor     r13d, r13d
0x180002397  add     rcx, 10h; lpCriticalSection
0x18000239b  mov     [rsp+0C8h+var_68], r13d
0x1800023a0  mov     r12, r9
0x1800023a3  mov     rbp, r8
0x1800023a6  mov     rdi, rdx
0x1800023a9  call    cs:__imp_EnterCriticalSection
0x1800023af  xor     eax, eax
0x1800023b1  mov     [rsp+0C8h+var_60], r13
0x1800023b6  lea     r14d, [r13+1]
0x1800023ba  mov     ebx, r13d
0x1800023bd  mov     qword ptr [rsp+0C8h+SystemTime.wYear], rax
0x1800023c2  mov     qword ptr [rsp+0C8h+SystemTime.wHour], rax
0x1800023c7  cmp     [rdi+10h], r13
0x1800023cb  jz      short loc_18000240C
0x1800023cd  cmp     [rdi+20h], r13
0x1800023d1  jz      short loc_18000240C
0x1800023d3  cmp     [rdi+30h], r13
0x1800023d7  jz      short loc_18000240C
0x1800023d9  cmp     [rdi+28h], r13
0x1800023dd  jz      short loc_18000240C
0x1800023df  cmp     [rdi+38h], r13d
0x1800023e3  jnz     short loc_18000240C
0x1800023e5  cmp     [rdi+8], r14d
0x1800023e9  jz      loc_180002633
0x1800023ef  cmp     dword ptr [rdi+8], 2
0x1800023f3  jnz     short loc_18000240C
0x1800023f5  mov     eax, [rdi+50h]
0x1800023f8  mov     ecx, eax
0x1800023fa  cmp     eax, r14d
0x1800023fd  jz      loc_180002636
0x180002403  cmp     eax, 2
0x180002406  jz      loc_180002636
0x18000240c  mov     ebx, 57h ; 'W'
0x180002411  mov     r9d, 4Fh ; 'O'; unsigned int
0x180002417  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000241e  mov     ecx, ebx; unsigned int
0x180002420  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002425  test    eax, eax
0x180002427  jnz     loc_1800025EC
0x18000242d  mov     eax, r14d
0x180002430  lock xadd cs:?sm_uNextNamespaceId@CMulticastNamespace@@0KA, eax; ulong CMulticastNamespace::sm_uNextNamespaceId
0x180002438  mov     rdx, cs:qword_1800336E8
0x18000243f  lea     rcx, [rsi+0B8h]; void *
0x180002446  add     eax, r14d
0x180002449  add     rdx, 140h; Src
0x180002450  mov     r8d, 9Ch; Size
0x180002456  mov     [rsi+38h], eax
0x180002459  call    memmove_0
0x18000245e  mov     [rsi+0B0h], rbp
0x180002465  lea     r8, [rsi+160h]; void **
0x18000246c  mov     rdx, [rdi+30h]; unsigned __int16 *
0x180002470  mov     rcx, rbp; lpCriticalSection
0x180002473  call    ?OpenInstance@CContentProvider@@QEAAKPEBGPEAPEAX@Z; CContentProvider::OpenInstance(ushort const *,void * *)
0x180002478  mov     r9d, 63h ; 'c'; unsigned int
0x18000247e  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180002485  mov     ecx, eax; unsigned int
0x180002487  mov     ebx, eax
0x180002489  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000248e  test    eax, eax
0x180002490  jnz     loc_1800025EC
0x180002496  lea     rdx, [rsi+40h]; struct _WDSTPT_NAMESPACE *
0x18000249a  mov     rcx, rdi; Src
0x18000249d  call    ?DuplicateNamespace@CMulticastNamespace@@SAKPEAU_WDSTPT_NAMESPACE@@0@Z; CMulticastNamespace::DuplicateNamespace(_WDSTPT_NAMESPACE *,_WDSTPT_NAMESPACE *)
0x1800024a2  mov     r9d, 6Ah ; 'j'; unsigned int
0x1800024a8  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800024af  mov     ecx, eax; unsigned int
0x1800024b1  mov     ebx, eax
0x1800024b3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800024b8  test    eax, eax
0x1800024ba  jnz     loc_1800025EC
0x1800024c0  cmp     [rsi+48h], r14d
0x1800024c4  mov     eax, r13d
0x1800024c7  mov     edx, [rsi+38h]
0x1800024ca  cmovz   eax, r14d
0x1800024ce  mov     [rsi+40h], rdx
0x1800024d2  mov     [rsi+8Ch], eax
0x1800024d8  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800024df  mov     [rsi+78h], r13d
0x1800024e3  test    rax, rax
0x1800024e6  jz      short loc_180002521
0x1800024e8  cmp     [rdi+8], r14d
0x1800024ec  lea     rcx, aAutocast; "AutoCast"
0x1800024f3  mov     r8, [rdi+10h]
0x1800024f7  lea     r9, aScheduled; "Scheduled"
0x1800024fe  cmovz   r9, rcx
0x180002502  mov     rcx, [rdi+30h]
0x180002506  mov     [rsp+0C8h+var_A0], rcx
0x18000250b  mov     rcx, [rdi+28h]
0x18000250f  mov     [rsp+0C8h+var_A8], rcx
0x180002514  lea     rcx, aWdsmcnsUSNames_1; "WDSMCNS[%u:%s]: Namespace Registered - "...
0x18000251b  call    cs:__guard_dispatch_icall_fptr
0x180002521  xor     r9d, r9d
0x180002524  mov     dword ptr [rsp+0C8h+var_A8], r14d
0x180002529  xor     r8d, r8d
0x18000252c  lea     rcx, qword_1800336A0; this
0x180002533  mov     edx, r14d; unsigned int
0x180002536  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x18000253b  mov     eax, r14d
0x18000253e  xchg    eax, [rsi+154h]
0x180002544  mov     ecx, [rsi+48h]
0x180002547  mov     rdx, [rsi+68h]
0x18000254b  mov     r8, [rsi+50h]
0x18000254f  mov     [rsp+0C8h+var_68], ecx
0x180002553  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002557  mov     rax, rcx
0x18000255a  inc     rax
0x18000255d  cmp     [rdx+rax*2], r13w
0x180002562  jnz     short loc_18000255A
0x180002564  lea     r9, ds:2[rax*2]
0x18000256c  inc     rcx
0x18000256f  cmp     [r8+rcx*2], r13w
0x180002574  jnz     short loc_18000256C
0x180002576  lea     rax, ds:2[rcx*2]
0x18000257e  lea     rcx, [rsp+0C8h+var_68]
0x180002583  mov     [rsp+0C8h+var_70], rcx
0x180002588  mov     [rsp+0C8h+var_78], 4
0x180002591  mov     [rsp+0C8h+var_80], r13
0x180002596  mov     [rsp+0C8h+var_88], rdx
0x18000259b  mov     edx, 13h
0x1800025a0  mov     [rsp+0C8h+var_90], r9
0x1800025a5  mov     r9d, r14d
0x1800025a8  mov     [rsp+0C8h+var_98], r14d
0x1800025ad  mov     [rsp+0C8h+var_A0], r8
0x1800025b2  lea     ecx, [rdx-11h]
0x1800025b5  mov     [rsp+0C8h+var_A8], rax
0x1800025ba  lea     r8d, [rdx-10h]
0x1800025be  call    cs:__imp_?WdsDiagRecordEvent@@YAKW4_WDS_DIAG_MODULE_ID@@W4_WDS_DIAG_EVENT_ID@@KZZ; WdsDiagRecordEvent(_WDS_DIAG_MODULE_ID,_WDS_DIAG_EVENT_ID,ulong,...)
0x1800025c4  mov     rcx, cs:qword_1800336E8
0x1800025cb  mov     edx, r14d; unsigned int
0x1800025ce  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800025d2  add     rcx, 360h; this
0x1800025d9  mov     [rsi+158h], r14d
0x1800025e0  call    ?AddNotification@CMulticastNotification@@QEAAKKPEBGPEAX@Z; CMulticastNotification::AddNotification(ulong,ushort const *,void *)
0x1800025e5  mov     eax, [rsi+38h]
0x1800025e8  mov     [r12], rax
0x1800025ec  test    ebx, ebx
0x1800025ee  jz      short loc_1800025FC
0x1800025f0  mov     rcx, rsi; this
0x1800025f3  mov     [rsi+78h], r14d
0x1800025f7  call    ?Shutdown@CMulticastNamespace@@QEAAKXZ; CMulticastNamespace::Shutdown(void)
0x1800025fc  lea     rcx, [rsi+10h]; lpCriticalSection
0x180002600  call    cs:__imp_LeaveCriticalSection
0x180002606  mov     eax, ebx
0x180002608  mov     rcx, [rsp+0C8h+var_48]
0x180002610  xor     rcx, rsp; StackCookie
0x180002613  call    __security_check_cookie
0x180002618  mov     rbx, [rsp+0C8h+arg_10]
0x180002620  add     rsp, 90h
0x180002627  pop     r15
0x180002629  pop     r14
0x18000262b  pop     r13
0x18000262d  pop     r12
0x18000262f  pop     rdi
0x180002630  pop     rsi
0x180002631  pop     rbp
0x180002632  retn
0x180002633  mov     ecx, [rdi+50h]
0x180002636  cmp     ecx, r14d
0x180002639  jnz     short loc_180002645
0x18000263b  cmp     [rdi+54h], r13d
0x18000263f  jnz     loc_18000240C
0x180002645  test    [rdi+54h], r14b
0x180002649  jz      short loc_180002655
0x18000264b  cmp     [rdi+58h], r13d
0x18000264f  jz      loc_18000240C
0x180002655  test    byte ptr [rdi+54h], 2
0x180002659  jz      loc_180002411
0x18000265f  lea     rcx, [rsp+0C8h+SystemTime]; lpSystemTime
0x180002664  call    cs:__imp_GetSystemTime
0x18000266a  lea     rcx, [rdi+5Ch]
0x18000266e  lea     r9, [rsp+0C8h+var_60]
0x180002673  lea     rdx, [rsp+0C8h+SystemTime]
0x180002678  call    ?Diff@CDate@@SAKPEAU_SYSTEMTIME@@0W4OpType@1@PEA_J@Z; CDate::Diff(_SYSTEMTIME *,_SYSTEMTIME *,CDate::OpType,__int64 *)
0x18000267d  mov     r9d, 6A2h; unsigned int
0x180002683  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000268a  mov     ecx, eax; unsigned int
0x18000268c  mov     ebx, eax
0x18000268e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002693  test    eax, eax
0x180002695  jnz     loc_180002411
0x18000269b  cmp     [rsp+0C8h+var_60], r13
0x1800026a0  jge     loc_180002411
0x1800026a6  mov     ebx, 0C121010Bh
0x1800026ab  jmp     loc_180002411
```
