# SAL2::CSALFileSize::Worker::Worker(long *)

- ea: `0x1800984c8`
- end: `0x18009860c`
- name: `??0Worker@CSALFileSize@SAL2@@AEAA@PEAJ@Z`
- size: `324`
- prototype: `__int64 __fastcall(SAL2::CSALFileSize::Worker *__hidden this, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800987cc`

## callees

- `0x180061f34`
- `0x1800627f0`
- `0x18008530c`
- `0x1800984c8`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1800985b7`
- `KERNEL32!CreateThread` at `0x1800985b7`
- `KERNEL32!CreateEventW` at `0x180098564`
- `KERNEL32!CreateEventW` at `0x180098564`
- `KERNEL32!InitializeCriticalSection` at `0x180098512`
- `KERNEL32!InitializeCriticalSection` at `0x180098512`
- `KERNEL32!GetLastError` at `0x180098576`
- `KERNEL32!GetLastError` at `0x1800985c7`
- `KERNEL32!GetLastError` at `0x180098576`
- `KERNEL32!GetLastError` at `0x1800985c7`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall SAL2::CSALFileSize::Worker::Worker(
        struct _RTL_CRITICAL_SECTION *this,
        struct _GUID *a2,
        unsigned __int64 a3,
        unsigned __int64 a4)
{
  int Data1; // ebx
  struct CEhEventTracer *p_LockCount; // rcx
  unsigned int v8; // r8d
  HANDLE EventW; // rax
  signed int v10; // eax
  void *v11; // r8
  signed int LastError; // eax
  unsigned __int64 dwCreationFlags; // [rsp+20h] [rbp-18h]
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF
  HANDLE v16; // [rsp+48h] [rbp+10h] BYREF

  SBEBasicTracers::SBEBasicTracers((SBEBasicTracers *)this, a2, a3, a4, dwCreationFlags);
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&SAL2::CSALFileSize::Worker::`vftable';
  LODWORD(this[6].LockSemaphore) = 0;
  HIDWORD(this[6].LockSemaphore) = 0;
  this[6].SpinCount = 0;
  InitializeCriticalSection(this + 7);
  Data1 = a2->Data1;
  *(_QWORD *)&this[8].LockCount = this + 8;
  this[8].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&this[8];
  this[8].OwningThread = 0;
  ThreadId = 0;
  if ( Data1 >= 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    this[6].SpinCount = (ULONG_PTR)EventW;
    if ( EventW )
    {
      v16 = CreateThread(0, 0, SAL2::CSALFileSize::Worker::WorkerThreadThunk, this, 0, &ThreadId);
      if ( v16 )
      {
        SAL2::CloseHandle((SAL2 *)&v16, 0, v11);
        goto LABEL_13;
      }
      LastError = GetLastError();
      Data1 = LastError;
      if ( LastError > 0 )
        Data1 = (unsigned __int16)LastError | 0x80070000;
      p_LockCount = (struct CEhEventTracer *)&this[1].LockCount;
      v8 = 552;
    }
    else
    {
      v10 = GetLastError();
      Data1 = v10;
      if ( v10 > 0 )
        Data1 = (unsigned __int16)v10 | 0x80070000;
      p_LockCount = (struct CEhEventTracer *)&this[1].LockCount;
      v8 = 548;
    }
  }
  else
  {
    p_LockCount = (struct CEhEventTracer *)&this[2].LockCount;
    v8 = 544;
  }
  SBEBasicTracers::EtwTraceError(p_LockCount, "multimedia\\dshow\\filters\\sbe\\sal\\salfilesize.cpp", v8, Data1);
LABEL_13:
  a2->Data1 = Data1;
  return this;
}

```

## disassembly

```asm
0x1800984c8  mov     [rsp+arg_10], rbx
0x1800984cd  mov     [rsp+arg_18], rsi
0x1800984d2  push    rdi
0x1800984d3  sub     rsp, 30h
0x1800984d7  mov     rsi, rdx
0x1800984da  mov     rdi, rcx
0x1800984dd  call    ??0SBEBasicTracers@@QEAA@AEBU_GUID@@_K11@Z; SBEBasicTracers::SBEBasicTracers(_GUID const &,unsigned __int64,unsigned __int64,unsigned __int64)
0x1800984e2  lea     rax, ??_7Worker@CSALFileSize@SAL2@@6B@; const SAL2::CSALFileSize::Worker::`vftable'
0x1800984e9  mov     [rdi], rax
0x1800984ec  lea     rcx, [rdi+118h]; lpCriticalSection
0x1800984f3  mov     dword ptr [rdi+108h], 0
0x1800984fd  mov     dword ptr [rdi+10Ch], 0
0x180098507  mov     qword ptr [rdi+110h], 0
0x180098512  call    cs:__imp_InitializeCriticalSection
0x180098518  mov     ebx, [rsi]
0x18009851a  lea     rax, [rdi+140h]
0x180098521  mov     [rax+8], rax
0x180098525  mov     [rax], rax
0x180098528  mov     qword ptr [rax+10h], 0
0x180098530  mov     [rsp+38h+ThreadId], 0
0x180098538  test    ebx, ebx
0x18009853a  jns     short loc_18009855A
0x18009853c  lea     rcx, [rdi+58h]; struct CEhEventTracer *
0x180098540  mov     r8d, 220h; unsigned int
0x180098546  mov     r9d, ebx; unsigned int
0x180098549  lea     rdx, aMultimediaDsho_30; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180098550  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x180098555  jmp     loc_1800985F7
0x18009855a  xor     r9d, r9d; lpName
0x18009855d  xor     r8d, r8d; bInitialState
0x180098560  xor     edx, edx; bManualReset
0x180098562  xor     ecx, ecx; lpEventAttributes
0x180098564  call    cs:__imp_CreateEventW
0x18009856a  mov     [rdi+110h], rax
0x180098571  test    rax, rax
0x180098574  jnz     short loc_180098597
0x180098576  call    cs:__imp_GetLastError
0x18009857c  mov     ebx, eax
0x18009857e  test    eax, eax
0x180098580  jle     short loc_18009858B
0x180098582  movzx   ebx, ax
0x180098585  or      ebx, 80070000h
0x18009858b  lea     rcx, [rdi+30h]
0x18009858f  mov     r8d, 224h
0x180098595  jmp     short loc_180098546
0x180098597  lea     rax, [rsp+38h+ThreadId]
0x18009859c  mov     r9, rdi; lpParameter
0x18009859f  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800985a4  lea     r8, ?WorkerThreadThunk@Worker@CSALFileSize@SAL2@@CAKPEAX@Z; lpStartAddress
0x1800985ab  xor     edx, edx; dwStackSize
0x1800985ad  mov     dword ptr [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800985b5  xor     ecx, ecx; lpThreadAttributes
0x1800985b7  call    cs:__imp_CreateThread
0x1800985bd  mov     [rsp+38h+arg_8], rax
0x1800985c2  test    rax, rax
0x1800985c5  jnz     short loc_1800985EB
0x1800985c7  call    cs:__imp_GetLastError
0x1800985cd  mov     ebx, eax
0x1800985cf  test    eax, eax
0x1800985d1  jle     short loc_1800985DC
0x1800985d3  movzx   ebx, ax
0x1800985d6  or      ebx, 80070000h
0x1800985dc  lea     rcx, [rdi+30h]
0x1800985e0  mov     r8d, 228h
0x1800985e6  jmp     loc_180098546
0x1800985eb  xor     edx, edx; void **
0x1800985ed  lea     rcx, [rsp+38h+arg_8]; this
0x1800985f2  call    ?CloseHandle@SAL2@@YAXAEAPEAXPEAX@Z; SAL2::CloseHandle(void * &,void *)
0x1800985f7  mov     [rsi], ebx
0x1800985f9  mov     rax, rdi
0x1800985fc  mov     rbx, [rsp+38h+arg_10]
0x180098601  mov     rsi, [rsp+38h+arg_18]
0x180098606  add     rsp, 30h
0x18009860a  pop     rdi
0x18009860b  retn
```
