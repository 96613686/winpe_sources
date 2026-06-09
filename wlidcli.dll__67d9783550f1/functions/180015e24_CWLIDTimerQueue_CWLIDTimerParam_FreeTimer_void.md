# CWLIDTimerQueue::CWLIDTimerParam::FreeTimer(void)

- ea: `0x180015e24`
- end: `0x180015f16`
- name: `?FreeTimer@CWLIDTimerParam@CWLIDTimerQueue@@QEAAXXZ`
- size: `242`
- prototype: `void __fastcall(CWLIDTimerQueue::CWLIDTimerParam *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015ce8`
- `0x1800291f0`

## callees

- `0x18000c270`
- `0x18000c354`
- `0x18001365c`
- `0x180015e24`
- `0x1800193b4`
- `0x1800530e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ea5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ea5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180015e8e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180015e8e`

## string_xrefs

- `0x180015ed0`: `DeleteTimerQueueTimer failed for Queue %p and timer %p with hr=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWLIDTimerQueue::CWLIDTimerParam::FreeTimer(CWLIDTimerQueue::CWLIDTimerParam *this)
{
  __int64 v2; // rdx
  signed int LastError; // eax
  signed int v4; // [rsp+30h] [rbp-38h]
  HANDLE v5[2]; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v6[24]; // [rsp+50h] [rbp-18h] BYREF

  if ( *(_QWORD *)this )
  {
    v2 = *((_QWORD *)this + 1);
    if ( v2 )
    {
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
        (__int64)v6,
        v2 + 80,
        1);
      if ( *(_QWORD *)(*((_QWORD *)this + 1) + 48LL) )
      {
        LODWORD(v5[0]) = 0;
        v5[1] = 0;
        CAutoRevertToSelf::Revert(v5);
        if ( !DeleteTimerQueueTimer(*(HANDLE *)(*((_QWORD *)this + 1) + 48LL), *(HANDLE *)this, 0)
          && GetLastError() != 997 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v4 = LastError;
          TracePrintW(
            2u,
            "onecoreuap\\restricted\\ds\\inc\\idcrl\\TimerQueue.h",
            0x52u,
            L"DeleteTimerQueueTimer failed for Queue %p and timer %p with hr=0x%x",
            *(_QWORD *)(*((_QWORD *)this + 1) + 48LL),
            *(_QWORD *)this,
            v4);
        }
        CAutoRevertToSelf::~CAutoRevertToSelf((CAutoRevertToSelf *)v5);
      }
      *(_QWORD *)this = 0;
      *((_QWORD *)this + 1) = 0;
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v6);
    }
  }
}

```

## disassembly

```asm
0x180015e24  push    rbx
0x180015e26  sub     rsp, 60h
0x180015e2a  mov     rbx, rcx
0x180015e2d  cmp     qword ptr [rcx], 0
0x180015e31  jz      loc_180015F10
0x180015e37  mov     rdx, [rcx+8]
0x180015e3b  test    rdx, rdx
0x180015e3e  jz      loc_180015F10
0x180015e44  add     rdx, 50h ; 'P'
0x180015e48  mov     r8b, 1
0x180015e4b  lea     rcx, [rsp+68h+var_18]
0x180015e50  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x180015e55  nop
0x180015e56  mov     rax, [rbx+8]
0x180015e5a  cmp     qword ptr [rax+30h], 0
0x180015e5f  jz      loc_180015EF7
0x180015e65  mov     [rsp+68h+var_28], 0
0x180015e6d  mov     [rsp+68h+var_20], 0
0x180015e76  lea     rcx, [rsp+68h+var_28]; this
0x180015e7b  call    ?Revert@CAutoRevertToSelf@@QEAAHH@Z; CAutoRevertToSelf::Revert(int)
0x180015e80  mov     rcx, [rbx+8]
0x180015e84  xor     r8d, r8d; CompletionEvent
0x180015e87  mov     rdx, [rbx]; Timer
0x180015e8a  mov     rcx, [rcx+30h]; TimerQueue
0x180015e8e  call    cs:__imp_DeleteTimerQueueTimer
0x180015e94  test    eax, eax
0x180015e96  jnz     short loc_180015EED
0x180015e98  call    cs:__imp_GetLastError
0x180015e9e  cmp     eax, 3E5h
0x180015ea3  jz      short loc_180015EED
0x180015ea5  call    cs:__imp_GetLastError
0x180015eab  test    eax, eax
0x180015ead  jle     short loc_180015EB7
0x180015eaf  movzx   eax, ax
0x180015eb2  or      eax, 80070000h
0x180015eb7  mov     rcx, [rbx+8]
0x180015ebb  mov     [rsp+68h+var_38], eax
0x180015ebf  mov     rax, [rbx]
0x180015ec2  mov     [rsp+68h+var_40], rax
0x180015ec7  mov     rax, [rcx+30h]
0x180015ecb  mov     [rsp+68h+var_48], rax
0x180015ed0  lea     r9, aDeletetimerque; "DeleteTimerQueueTimer failed for Queue "...
0x180015ed7  mov     r8d, 52h ; 'R'; unsigned int
0x180015edd  lea     rdx, aOnecoreuapRest_1; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x180015ee4  lea     ecx, [r8-50h]; unsigned __int8
0x180015ee8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180015eed  lea     rcx, [rsp+68h+var_28]; this
0x180015ef2  call    ??1CAutoRevertToSelf@@QEAA@XZ; CAutoRevertToSelf::~CAutoRevertToSelf(void)
0x180015ef7  mov     qword ptr [rbx], 0
0x180015efe  mov     qword ptr [rbx+8], 0
0x180015f06  lea     rcx, [rsp+68h+var_18]
0x180015f0b  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180015f10  add     rsp, 60h
0x180015f14  pop     rbx
0x180015f15  retn
```
