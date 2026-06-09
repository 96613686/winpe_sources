# CWLIDTimerQueue::QueueWorkItem(void (*)(void *,uchar,uchar),void *,ulong,ulong)

- ea: `0x180028540`
- end: `0x18002867c`
- name: `?QueueWorkItem@CWLIDTimerQueue@@UEAAJP6AXPEAXEE@Z0KK@Z`
- size: `316`
- prototype: `int(CWLIDTimerQueue *__hidden this, void (*)(void *, unsigned __int8, unsigned __int8), void *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180003298`
- `0x18000cc9c`
- `0x18000e870`
- `0x180015ce8`
- `0x180023c68`
- `0x180028540`
- `0x180028908`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028640`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18002862d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18002862d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWLIDTimerQueue::QueueWorkItem(
        HANDLE *this,
        void (*a2)(void *, unsigned __int8, unsigned __int8),
        void *a3,
        DWORD a4,
        ULONG Flags)
{
  _QWORD *v9; // rbx
  signed int LastError; // eax
  unsigned int v11; // ebx
  const unsigned __int16 *DueTime; // [rsp+20h] [rbp-41h]
  PVOID Parameter; // [rsp+40h] [rbp-21h] BYREF
  __int64 v15; // [rsp+48h] [rbp-19h] BYREF
  _QWORD *v16; // [rsp+50h] [rbp-11h] BYREF
  _QWORD v17[11]; // [rsp+58h] [rbp-9h] BYREF
  int v18; // [rsp+C0h] [rbp+5Fh] BYREF

  v18 = 0;
  v17[0] = "CWLIDTimerQueue::QueueWorkItem";
  v17[1] = &v18;
  v17[2] = 0;
  v17[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\restricted\\ds\\inc\\idcrl\\TimerQueue.h",
    "CWLIDTimerQueue::QueueWorkItem",
    (const char *)0x11E,
    0,
    DueTime);
  if ( this[6] )
  {
    v9 = operator new(0x20u);
    *v9 = 0;
    v9[1] = this;
    v9[2] = a3;
    v9[3] = a2;
    Parameter = 0;
    v15 = 0;
    v16 = v9;
    v18 = CWLIDTimerQueue::AddTimerData(&v16, &Parameter);
    if ( v18 >= 0 && !CreateTimerQueueTimer((PHANDLE)v9, this[6], CWLIDTimerQueue::TimerDriver, Parameter, a4, 0, Flags) )
    {
      CWLIDTimerQueue::RemoveTimerData(Parameter);
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v18 = LastError;
    }
    ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>::Free(&v15);
  }
  else
  {
    v18 = -2147188728;
  }
  v11 = v18;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v17);
  return v11;
}

```

## disassembly

```asm
0x180028540  push    rbp
0x180028542  push    rbx
0x180028543  push    rsi
0x180028544  push    rdi
0x180028545  push    r14
0x180028547  push    r15
0x180028549  lea     rbp, [rsp-27h]
0x18002854e  sub     rsp, 88h
0x180028555  mov     esi, r9d
0x180028558  mov     r14, r8
0x18002855b  mov     r15, rdx
0x18002855e  mov     rdi, rcx
0x180028561  mov     [rbp+4Fh+arg_0], 0
0x180028568  lea     rdx, aCwlidtimerqueu_1; "CWLIDTimerQueue::QueueWorkItem"
0x18002856f  mov     [rbp+4Fh+var_58], rdx
0x180028573  lea     rax, [rbp+4Fh+arg_0]
0x180028577  mov     [rbp+4Fh+var_50], rax
0x18002857b  mov     [rbp+4Fh+var_48], 0
0x180028583  mov     [rbp+4Fh+var_40], 0
0x18002858b  xor     r9d, r9d; unsigned int
0x18002858e  mov     r8d, 11Eh; char *
0x180028594  lea     rcx, aOnecoreuapRest_1; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x18002859b  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800285a0  nop
0x1800285a1  cmp     qword ptr [rdi+30h], 0
0x1800285a6  jnz     short loc_1800285B4
0x1800285a8  mov     [rbp+4Fh+arg_0], 80048008h
0x1800285af  jmp     loc_18002865E
0x1800285b4  mov     [rbp+4Fh+var_68], 0
0x1800285bc  mov     ecx, 20h ; ' '; Size
0x1800285c1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800285c6  mov     rbx, rax
0x1800285c9  mov     [rbp+4Fh+var_60], rax
0x1800285cd  mov     qword ptr [rax], 0
0x1800285d4  mov     [rax+8], rdi
0x1800285d8  mov     [rax+10h], r14
0x1800285dc  mov     [rax+18h], r15
0x1800285e0  mov     [rbp+4Fh+Parameter], 0
0x1800285e8  mov     [rbp+4Fh+var_68], 0
0x1800285f0  mov     [rbp+4Fh+var_60], rax
0x1800285f4  lea     rdx, [rbp+4Fh+Parameter]
0x1800285f8  lea     rcx, [rbp+4Fh+var_60]
0x1800285fc  call    ?AddTimerData@CWLIDTimerQueue@@CAJV?$CAutoPtr@VCWLIDTimerParam@CWLIDTimerQueue@@@ATL@@PEAPEAX@Z; CWLIDTimerQueue::AddTimerData(ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,void * *)
0x180028601  mov     [rbp+4Fh+arg_0], eax
0x180028604  test    eax, eax
0x180028606  js      short loc_180028655
0x180028608  mov     eax, [rbp+4Fh+arg_20]
0x18002860b  mov     [rsp+0B0h+Flags], eax; Flags
0x18002860f  mov     [rsp+0B0h+Period], 0; Period
0x180028617  mov     dword ptr [rsp+0B0h+DueTime], esi; DueTime
0x18002861b  mov     r9, [rbp+4Fh+Parameter]; Parameter
0x18002861f  lea     r8, ?TimerDriver@CWLIDTimerQueue@@SAXPEAXE@Z; Callback
0x180028626  mov     rdx, [rdi+30h]; TimerQueue
0x18002862a  mov     rcx, rbx; phNewTimer
0x18002862d  call    cs:__imp_CreateTimerQueueTimer
0x180028633  test    eax, eax
0x180028635  jnz     short loc_180028655
0x180028637  mov     rcx, [rbp+4Fh+Parameter]; void *
0x18002863b  call    ?RemoveTimerData@CWLIDTimerQueue@@CAXPEAX@Z; CWLIDTimerQueue::RemoveTimerData(void *)
0x180028640  call    cs:__imp_GetLastError
0x180028646  test    eax, eax
0x180028648  jle     short loc_180028652
0x18002864a  movzx   eax, ax
0x18002864d  or      eax, 80070000h
0x180028652  mov     [rbp+4Fh+arg_0], eax
0x180028655  lea     rcx, [rbp+4Fh+var_68]
0x180028659  call    ?Free@?$CAutoPtr@VCWLIDTimerParam@CWLIDTimerQueue@@@ATL@@QEAAXXZ; ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>::Free(void)
0x18002865e  mov     ebx, [rbp+4Fh+arg_0]
0x180028661  lea     rcx, [rbp+4Fh+var_58]
0x180028665  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002866a  mov     eax, ebx
0x18002866c  add     rsp, 88h
0x180028673  pop     r15
0x180028675  pop     r14
0x180028677  pop     rdi
0x180028678  pop     rsi
0x180028679  pop     rbx
0x18002867a  pop     rbp
0x18002867b  retn
```
