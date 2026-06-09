# NThreadingLibrary::TWorkCrew::TWorkCrew(void)

- ea: `0x140012fdc`
- end: `0x14001316d`
- name: `??0TWorkCrew@NThreadingLibrary@@QEAA@XZ`
- size: `401`
- prototype: `__int64 __fastcall(NThreadingLibrary::TWorkCrew *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140010400`

## callees

- `0x1400112c8`
- `0x140012bd4`
- `0x140012fdc`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1400130d3`
- `KERNEL32!CreateEventW` at `0x1400130fa`
- `KERNEL32!CreateEventW` at `0x1400130d3`
- `KERNEL32!CreateEventW` at `0x1400130fa`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14001302e`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14001302e`
- `ntdll!RtlNtStatusToDosError` at `0x14001312f`
- `ntdll!RtlNtStatusToDosError` at `0x14001312f`
- `ntdll!TpSetWait` at `0x140013155`
- `ntdll!TpSetWait` at `0x140013155`
- `ntdll!TpAllocWait` at `0x140013127`
- `ntdll!TpAllocWait` at `0x140013127`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall NThreadingLibrary::TWorkCrew::TWorkCrew(struct _RTL_CRITICAL_SECTION *this)
{
  NCoreLibrary *v2; // rcx
  LONG LastErrorAsFailHR; // eax
  signed int LockCount; // edi
  HANDLE EventW; // rax
  NCoreLibrary *v6; // rcx
  HANDLE v7; // rax
  NCoreLibrary *v8; // rcx
  NTSTATUS v9; // eax
  signed int v10; // eax

  this->LockCount = 1;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&NThreadingLibrary::TWorkCrew::`vftable'{for `NCoreLibrary::TReferenceCount'};
  this->LockSemaphore = 0;
  this->OwningThread = &NThreadingLibrary::TWorkCrew::`vftable'{for `NThreadingLibrary::TTpSetWorkEnv'};
  LODWORD(this->SpinCount) = 2003985271;
  LODWORD(this[2].DebugInfo) = 0;
  HIDWORD(this[2].DebugInfo) = 0;
  this[2].LockCount = -2147467259;
  HIDWORD(this[2].DebugInfo) = 0;
  LODWORD(this[2].DebugInfo) = 0;
  if ( InitializeCriticalSectionAndSpinCount(this + 1, 0x80000000) )
    LastErrorAsFailHR = 0;
  else
    LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v2);
  this[2].LockCount = LastErrorAsFailHR;
  LockCount = this[2].LockCount;
  this[2].LockSemaphore = &NCoreLibrary::TLink::`vftable';
  LODWORD(this[2].SpinCount) = 1802398836;
  this[3].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&this[2].LockSemaphore;
  *(_QWORD *)&this[3].LockCount = (char *)this + 104;
  this[3].LockSemaphore = &NCoreLibrary::TLink::`vftable';
  LODWORD(this[3].SpinCount) = 1802398836;
  this[4].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&this[3].LockSemaphore;
  *(_QWORD *)&this[4].LockCount = (char *)this + 144;
  LODWORD(this[2].OwningThread) = 1953721460;
  LODWORD(this[3].OwningThread) = 1953721460;
  HIDWORD(this[4].SpinCount) = -2147467259;
  this[5].OwningThread = 0;
  LODWORD(this[4].OwningThread) = 0;
  this[4].LockSemaphore = 0;
  LODWORD(this[4].SpinCount) = 0;
  LODWORD(this[5].DebugInfo) = 0;
  *(_QWORD *)&this[5].LockCount = 0;
  this[5].LockSemaphore = 0;
  if ( LockCount >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *(_QWORD *)&this[5].LockCount = EventW;
    if ( EventW || (LockCount = NCoreLibrary::GetLastErrorAsHResult(v6), LockCount >= 0) )
    {
      v7 = CreateEventW(0, 0, 0, 0);
      this[4].LockSemaphore = v7;
      if ( v7 || (LockCount = NCoreLibrary::GetLastErrorAsHResult(v8), LockCount >= 0) )
      {
        v9 = TpAllocWait(&this[5].OwningThread, NThreadingLibrary::TWorkCrew::CancelWorkThread, this, 0);
        v10 = RtlNtStatusToDosError(v9);
        LockCount = v10;
        if ( v10 > 0 )
          LockCount = (unsigned __int16)v10 | 0x80070000;
        if ( LockCount >= 0 )
          TpSetWait(this[5].OwningThread, this[4].LockSemaphore, 0);
      }
    }
  }
  HIDWORD(this[4].SpinCount) = LockCount;
  return this;
}

```

## disassembly

```asm
0x140012fdc  push    rbx
0x140012fde  push    rbp
0x140012fdf  push    rsi
0x140012fe0  push    rdi
0x140012fe1  sub     rsp, 28h
0x140012fe5  mov     dword ptr [rcx+8], 1
0x140012fec  lea     rax, ??_7TWorkCrew@NThreadingLibrary@@6BTReferenceCount@NCoreLibrary@@@; const NThreadingLibrary::TWorkCrew::`vftable'{for `NCoreLibrary::TReferenceCount'}
0x140012ff3  mov     [rcx], rax
0x140012ff6  xor     ebp, ebp
0x140012ff8  mov     [rcx+18h], rbp
0x140012ffc  lea     rax, ??_7TWorkCrew@NThreadingLibrary@@6BTTpSetWorkEnv@1@@; const NThreadingLibrary::TWorkCrew::`vftable'{for `NThreadingLibrary::TTpSetWorkEnv'}
0x140013003  mov     [rcx+10h], rax
0x140013007  mov     rbx, rcx
0x14001300a  mov     dword ptr [rcx+20h], 77726377h
0x140013011  mov     esi, 80004005h
0x140013016  mov     [rcx+50h], ebp
0x140013019  mov     edx, 80000000h; dwSpinCount
0x14001301e  mov     [rcx+54h], ebp
0x140013021  mov     [rcx+58h], esi
0x140013024  mov     [rcx+54h], ebp
0x140013027  mov     [rcx+50h], ebp
0x14001302a  add     rcx, 28h ; '('; lpCriticalSection
0x14001302e  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140013034  test    eax, eax
0x140013036  jz      short loc_14001303C
0x140013038  mov     eax, ebp
0x14001303a  jmp     short loc_140013041
0x14001303c  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x140013041  mov     [rbx+58h], eax
0x140013044  lea     r8, ??_7TLink@NCoreLibrary@@6B@; const NCoreLibrary::TLink::`vftable'
0x14001304b  mov     edi, [rbx+58h]
0x14001304e  lea     rax, [rbx+68h]
0x140013052  mov     [rax], r8
0x140013055  mov     ecx, 6B6E6C74h
0x14001305a  mov     [rax+8], ecx
0x14001305d  mov     edx, 74736C74h
0x140013062  mov     [rax+10h], rax
0x140013066  mov     [rax+18h], rax
0x14001306a  lea     rax, [rbx+90h]
0x140013071  mov     [rax], r8
0x140013074  mov     [rax+8], ecx
0x140013077  mov     [rax+10h], rax
0x14001307b  mov     [rax+18h], rax
0x14001307f  mov     [rbx+60h], edx
0x140013082  mov     [rbx+88h], edx
0x140013088  mov     [rbx+0C4h], esi
0x14001308e  lea     rsi, [rbx+0D8h]
0x140013095  mov     [rsi], rbp
0x140013098  mov     [rbx+0B0h], ebp
0x14001309e  mov     [rbx+0B8h], rbp
0x1400130a5  mov     [rbx+0C0h], ebp
0x1400130ab  mov     [rbx+0C8h], ebp
0x1400130b1  mov     [rbx+0D0h], rbp
0x1400130b8  mov     [rbx+0E0h], rbp
0x1400130bf  test    edi, edi
0x1400130c1  js      loc_14001315B
0x1400130c7  xor     r9d, r9d; lpName
0x1400130ca  xor     r8d, r8d; bInitialState
0x1400130cd  xor     ecx, ecx; lpEventAttributes
0x1400130cf  lea     edx, [r9+1]; bManualReset
0x1400130d3  call    cs:__imp_CreateEventW
0x1400130d9  mov     [rbx+0D0h], rax
0x1400130e0  test    rax, rax
0x1400130e3  jnz     short loc_1400130F0
0x1400130e5  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x1400130ea  mov     edi, eax
0x1400130ec  test    eax, eax
0x1400130ee  js      short loc_14001315B
0x1400130f0  xor     r9d, r9d; lpName
0x1400130f3  xor     r8d, r8d; bInitialState
0x1400130f6  xor     edx, edx; bManualReset
0x1400130f8  xor     ecx, ecx; lpEventAttributes
0x1400130fa  call    cs:__imp_CreateEventW
0x140013100  mov     [rbx+0B8h], rax
0x140013107  test    rax, rax
0x14001310a  jnz     short loc_140013117
0x14001310c  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x140013111  mov     edi, eax
0x140013113  test    eax, eax
0x140013115  js      short loc_14001315B
0x140013117  xor     r9d, r9d
0x14001311a  lea     rdx, ?CancelWorkThread@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; NThreadingLibrary::TWorkCrew::CancelWorkThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)
0x140013121  mov     r8, rbx
0x140013124  mov     rcx, rsi
0x140013127  call    cs:__imp_TpAllocWait
0x14001312d  mov     ecx, eax; Status
0x14001312f  call    cs:__imp_RtlNtStatusToDosError
0x140013135  mov     edi, eax
0x140013137  test    eax, eax
0x140013139  jle     short loc_140013144
0x14001313b  movzx   edi, ax
0x14001313e  or      edi, 80070000h
0x140013144  test    edi, edi
0x140013146  js      short loc_14001315B
0x140013148  mov     rdx, [rbx+0B8h]
0x14001314f  xor     r8d, r8d
0x140013152  mov     rcx, [rsi]
0x140013155  call    cs:__imp_TpSetWait
0x14001315b  mov     [rbx+0C4h], edi
0x140013161  mov     rax, rbx
0x140013164  add     rsp, 28h
0x140013168  pop     rdi
0x140013169  pop     rsi
0x14001316a  pop     rbp
0x14001316b  pop     rbx
0x14001316c  retn
```
