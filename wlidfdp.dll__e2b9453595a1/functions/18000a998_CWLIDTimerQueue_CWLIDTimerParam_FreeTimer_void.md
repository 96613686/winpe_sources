# CWLIDTimerQueue::CWLIDTimerParam::FreeTimer(void)

- ea: `0x18000a998`
- end: `0x18000aa87`
- name: `?FreeTimer@CWLIDTimerParam@CWLIDTimerQueue@@QEAAXXZ`
- size: `239`
- prototype: `void __fastcall(CWLIDTimerQueue::CWLIDTimerParam *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a838`
- `0x18000b820`

## callees

- `0x180003700`
- `0x18000505c`
- `0x180009e00`
- `0x18000a998`
- `0x18000b4e8`
- `0x18000f4cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa16`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000a9ff`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000a9ff`

## string_xrefs

- `0x18000aa41`: `DeleteTimerQueueTimer failed for Queue %p and timer %p with hr=0x%x`

## pseudocode

```c
void __fastcall CWLIDTimerQueue::CWLIDTimerParam::FreeTimer(CWLIDTimerQueue::CWLIDTimerParam *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdx
  int v3; // edx
  signed int LastError; // eax
  signed int v5; // [rsp+30h] [rbp-38h]
  int v6; // [rsp+40h] [rbp-28h] BYREF
  __int64 v7; // [rsp+48h] [rbp-20h]
  _BYTE v8[24]; // [rsp+50h] [rbp-18h] BYREF

  if ( *(_QWORD *)this )
  {
    v2 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 1);
    if ( v2 )
    {
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
        (__int64)v8,
        v2 + 2);
      if ( *(_QWORD *)(*((_QWORD *)this + 1) + 48LL) )
      {
        v6 = 0;
        v7 = 0;
        CAutoRevertToSelf::Revert((CAutoRevertToSelf *)&v6, v3);
        if ( !DeleteTimerQueueTimer(*(HANDLE *)(*((_QWORD *)this + 1) + 48LL), *(HANDLE *)this, 0)
          && GetLastError() != 997 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v5 = LastError;
          TracePrintW(
            2u,
            "onecoreuap\\restricted\\ds\\inc\\idcrl\\TimerQueue.h",
            0x52u,
            L"DeleteTimerQueueTimer failed for Queue %p and timer %p with hr=0x%x",
            *(_QWORD *)(*((_QWORD *)this + 1) + 48LL),
            *(_QWORD *)this,
            v5);
        }
        CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)&v6);
      }
      *(_QWORD *)this = 0;
      *((_QWORD *)this + 1) = 0;
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v8);
    }
  }
}

```

## disassembly

```asm
0x18000a998  push    rbx
0x18000a99a  sub     rsp, 60h
0x18000a99e  mov     rbx, rcx
0x18000a9a1  cmp     qword ptr [rcx], 0
0x18000a9a5  jz      loc_18000AA81
0x18000a9ab  mov     rdx, [rcx+8]
0x18000a9af  test    rdx, rdx
0x18000a9b2  jz      loc_18000AA81
0x18000a9b8  add     rdx, 50h ; 'P'
0x18000a9bc  lea     rcx, [rsp+68h+var_18]
0x18000a9c1  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x18000a9c6  nop
0x18000a9c7  mov     rax, [rbx+8]
0x18000a9cb  cmp     qword ptr [rax+30h], 0
0x18000a9d0  jz      loc_18000AA68
0x18000a9d6  mov     [rsp+68h+var_28], 0
0x18000a9de  mov     [rsp+68h+var_20], 0
0x18000a9e7  lea     rcx, [rsp+68h+var_28]; this
0x18000a9ec  call    ?Revert@CAutoRevertToSelf@@QEAAHH@Z; CAutoRevertToSelf::Revert(int)
0x18000a9f1  mov     rcx, [rbx+8]
0x18000a9f5  xor     r8d, r8d; CompletionEvent
0x18000a9f8  mov     rdx, [rbx]; Timer
0x18000a9fb  mov     rcx, [rcx+30h]; TimerQueue
0x18000a9ff  call    cs:__imp_DeleteTimerQueueTimer
0x18000aa05  test    eax, eax
0x18000aa07  jnz     short loc_18000AA5E
0x18000aa09  call    cs:__imp_GetLastError
0x18000aa0f  cmp     eax, 3E5h
0x18000aa14  jz      short loc_18000AA5E
0x18000aa16  call    cs:__imp_GetLastError
0x18000aa1c  test    eax, eax
0x18000aa1e  jle     short loc_18000AA28
0x18000aa20  movzx   eax, ax
0x18000aa23  or      eax, 80070000h
0x18000aa28  mov     rcx, [rbx+8]
0x18000aa2c  mov     [rsp+68h+var_38], eax
0x18000aa30  mov     rax, [rbx]
0x18000aa33  mov     [rsp+68h+var_40], rax
0x18000aa38  mov     rax, [rcx+30h]
0x18000aa3c  mov     [rsp+68h+var_48], rax
0x18000aa41  lea     r9, aDeletetimerque; "DeleteTimerQueueTimer failed for Queue "...
0x18000aa48  mov     r8d, 52h ; 'R'; unsigned int
0x18000aa4e  lea     rdx, aOnecoreuapRest_0; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x18000aa55  lea     ecx, [r8-50h]; unsigned __int8
0x18000aa59  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000aa5e  lea     rcx, [rsp+68h+var_28]; this
0x18000aa63  call    ??1CAutoRevertToSelf@@QEAA@XZ; CAutoRevertToSelf::~CAutoRevertToSelf(void)
0x18000aa68  mov     qword ptr [rbx], 0
0x18000aa6f  mov     qword ptr [rbx+8], 0
0x18000aa77  lea     rcx, [rsp+68h+var_18]
0x18000aa7c  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x18000aa81  add     rsp, 60h
0x18000aa85  pop     rbx
0x18000aa86  retn
```
