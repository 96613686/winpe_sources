# CWLIDTimerQueue::QueueWorkItem(void (*)(void *,uchar,uchar),void *,ulong,ulong)

- ea: `0x18000b080`
- end: `0x18000b1b9`
- name: `?QueueWorkItem@CWLIDTimerQueue@@UEAAJP6AXPEAXEE@Z0KK@Z`
- size: `313`
- prototype: `__int64 __fastcall(HANDLE *this, void (*)(void *, unsigned __int8, unsigned __int8), void *, unsigned int, ULONG Flags)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002c20`
- `0x1800054dc`
- `0x180008edc`
- `0x18000a134`
- `0x18000a838`
- `0x18000b080`
- `0x18000b4b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b17d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b17d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000b16a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000b16a`

## pseudocode

```c
__int64 __fastcall CWLIDTimerQueue::QueueWorkItem(
        HANDLE *this,
        void (*a2)(void *, unsigned __int8, unsigned __int8),
        void *a3,
        unsigned int a4,
        ULONG Flags)
{
  __int64 v9; // rdx
  int v10; // r8d
  _QWORD *v11; // rbx
  signed int LastError; // eax
  unsigned int v13; // ebx
  const unsigned __int16 *DueTime; // [rsp+20h] [rbp-41h]
  PVOID Parameter; // [rsp+40h] [rbp-21h] BYREF
  CWLIDTimerQueue::CWLIDTimerParam *v17; // [rsp+48h] [rbp-19h] BYREF
  _QWORD *v18; // [rsp+50h] [rbp-11h] BYREF
  _QWORD v19[11]; // [rsp+58h] [rbp-9h] BYREF
  int v20; // [rsp+C0h] [rbp+5Fh] BYREF

  v20 = 0;
  v19[0] = "CWLIDTimerQueue::QueueWorkItem";
  v19[1] = &v20;
  v19[2] = 0;
  v19[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\restricted\\ds\\inc\\idcrl\\TimerQueue.h",
    "CWLIDTimerQueue::QueueWorkItem",
    (const char *)0x11E,
    a4,
    DueTime);
  if ( this[6] )
  {
    v11 = operator new(0x20u);
    *v11 = 0;
    v11[1] = this;
    v11[2] = a3;
    v11[3] = a2;
    Parameter = 0;
    v17 = 0;
    v18 = v11;
    v20 = CWLIDTimerQueue::AddTimerData(&v18, &Parameter);
    if ( v20 >= 0
      && !CreateTimerQueueTimer((PHANDLE)v11, this[6], CWLIDTimerQueue::TimerDriver, Parameter, a4, 0, Flags) )
    {
      CWLIDTimerQueue::RemoveTimerData(Parameter);
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v20 = LastError;
    }
    ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>::Free(&v17);
  }
  else
  {
    v20 = -2147188728;
  }
  v13 = v20;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v19, v9, v10);
  return v13;
}

```

## disassembly

```asm
0x18000b080  push    rbp
0x18000b082  push    rbx
0x18000b083  push    rsi
0x18000b084  push    rdi
0x18000b085  push    r14
0x18000b087  push    r15
0x18000b089  lea     rbp, [rsp-27h]
0x18000b08e  sub     rsp, 88h
0x18000b095  mov     esi, r9d
0x18000b098  mov     r14, r8
0x18000b09b  mov     r15, rdx
0x18000b09e  mov     rdi, rcx
0x18000b0a1  mov     [rbp+4Fh+arg_0], 0
0x18000b0a8  lea     rdx, aCwlidtimerqueu_1; "CWLIDTimerQueue::QueueWorkItem"
0x18000b0af  mov     [rbp+4Fh+var_58], rdx
0x18000b0b3  lea     rax, [rbp+4Fh+arg_0]
0x18000b0b7  mov     [rbp+4Fh+var_50], rax
0x18000b0bb  mov     [rbp+4Fh+var_48], 0
0x18000b0c3  mov     [rbp+4Fh+var_40], 0
0x18000b0cb  mov     r8d, 11Eh; char *
0x18000b0d1  lea     rcx, aOnecoreuapRest_0; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x18000b0d8  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000b0dd  nop
0x18000b0de  cmp     qword ptr [rdi+30h], 0
0x18000b0e3  jnz     short loc_18000B0F1
0x18000b0e5  mov     [rbp+4Fh+arg_0], 80048008h
0x18000b0ec  jmp     loc_18000B19B
0x18000b0f1  mov     [rbp+4Fh+var_68], 0
0x18000b0f9  mov     ecx, 20h ; ' '; Size
0x18000b0fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b103  mov     rbx, rax
0x18000b106  mov     [rbp+4Fh+var_60], rax
0x18000b10a  mov     qword ptr [rax], 0
0x18000b111  mov     [rax+8], rdi
0x18000b115  mov     [rax+10h], r14
0x18000b119  mov     [rax+18h], r15
0x18000b11d  mov     [rbp+4Fh+Parameter], 0
0x18000b125  mov     [rbp+4Fh+var_68], 0
0x18000b12d  mov     [rbp+4Fh+var_60], rax
0x18000b131  lea     rdx, [rbp+4Fh+Parameter]
0x18000b135  lea     rcx, [rbp+4Fh+var_60]
0x18000b139  call    ?AddTimerData@CWLIDTimerQueue@@CAJV?$CAutoPtr@VCWLIDTimerParam@CWLIDTimerQueue@@@ATL@@PEAPEAX@Z; CWLIDTimerQueue::AddTimerData(ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,void * *)
0x18000b13e  mov     [rbp+4Fh+arg_0], eax
0x18000b141  test    eax, eax
0x18000b143  js      short loc_18000B192
0x18000b145  mov     eax, [rbp+4Fh+arg_20]
0x18000b148  mov     [rsp+0B0h+Flags], eax; Flags
0x18000b14c  mov     [rsp+0B0h+Period], 0; Period
0x18000b154  mov     dword ptr [rsp+0B0h+DueTime], esi; DueTime
0x18000b158  mov     r9, [rbp+4Fh+Parameter]; Parameter
0x18000b15c  lea     r8, ?TimerDriver@CWLIDTimerQueue@@SAXPEAXE@Z; Callback
0x18000b163  mov     rdx, [rdi+30h]; TimerQueue
0x18000b167  mov     rcx, rbx; phNewTimer
0x18000b16a  call    cs:__imp_CreateTimerQueueTimer
0x18000b170  test    eax, eax
0x18000b172  jnz     short loc_18000B192
0x18000b174  mov     rcx, [rbp+4Fh+Parameter]; void *
0x18000b178  call    ?RemoveTimerData@CWLIDTimerQueue@@CAXPEAX@Z; CWLIDTimerQueue::RemoveTimerData(void *)
0x18000b17d  call    cs:__imp_GetLastError
0x18000b183  test    eax, eax
0x18000b185  jle     short loc_18000B18F
0x18000b187  movzx   eax, ax
0x18000b18a  or      eax, 80070000h
0x18000b18f  mov     [rbp+4Fh+arg_0], eax
0x18000b192  lea     rcx, [rbp+4Fh+var_68]
0x18000b196  call    ?Free@?$CAutoPtr@VCWLIDTimerParam@CWLIDTimerQueue@@@ATL@@QEAAXXZ; ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>::Free(void)
0x18000b19b  mov     ebx, [rbp+4Fh+arg_0]
0x18000b19e  lea     rcx, [rbp+4Fh+var_58]
0x18000b1a2  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000b1a7  mov     eax, ebx
0x18000b1a9  add     rsp, 88h
0x18000b1b0  pop     r15
0x18000b1b2  pop     r14
0x18000b1b4  pop     rdi
0x18000b1b5  pop     rsi
0x18000b1b6  pop     rbx
0x18000b1b7  pop     rbp
0x18000b1b8  retn
```
