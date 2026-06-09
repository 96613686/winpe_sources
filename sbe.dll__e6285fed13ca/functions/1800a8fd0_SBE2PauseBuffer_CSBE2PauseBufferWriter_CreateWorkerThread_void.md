# SBE2PauseBuffer::CSBE2PauseBufferWriter::CreateWorkerThread(void)

- ea: `0x1800a8fd0`
- end: `0x1800a90a8`
- name: `?CreateWorkerThread@CSBE2PauseBufferWriter@SBE2PauseBuffer@@AEAAJXZ`
- size: `216`
- prototype: `__int64 __fastcall(SBE2PauseBuffer::CSBE2PauseBufferWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800a9490`

## callees

- `0x1800605d0`
- `0x1800627f0`
- `0x1800a8fd0`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1800a904c`
- `KERNEL32!CreateThread` at `0x1800a904c`
- `KERNEL32!CreateEventW` at `0x1800a8ff8`
- `KERNEL32!CreateEventW` at `0x1800a8ff8`
- `KERNEL32!GetLastError` at `0x1800a900d`
- `KERNEL32!GetLastError` at `0x1800a905a`
- `KERNEL32!GetLastError` at `0x1800a900d`
- `KERNEL32!GetLastError` at `0x1800a905a`

## string_xrefs

- `0x1800a907c`: `multimedia\dshow\filters\sbe\pausebuffer\pbwriter.cpp`

## pseudocode

```c
__int64 __fastcall SBE2PauseBuffer::CSBE2PauseBufferWriter::CreateWorkerThread(
        SBE2PauseBuffer::CSBE2PauseBufferWriter *this)
{
  SBECoreUtil *v1; // rsi
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  unsigned int v6; // r8d
  HANDLE Thread; // rax
  signed int v8; // eax
  void **v9; // rdx
  void *v10; // r8
  void **v11; // rdx
  void *v12; // r8

  v1 = (SBE2PauseBuffer::CSBE2PauseBufferWriter *)((char *)this + 904);
  if ( !*((_QWORD *)this + 113) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 114) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v6 = 158;
LABEL_10:
      SBEBasicTracers::EtwTraceError(
        (SBE2PauseBuffer::CSBE2PauseBufferWriter *)((char *)this + 48),
        "multimedia\\dshow\\filters\\sbe\\pausebuffer\\pbwriter.cpp",
        v6,
        v5);
      SBECoreUtil::CloseHandle((SBE2PauseBuffer::CSBE2PauseBufferWriter *)((char *)this + 912), v9, v10);
      SBECoreUtil::CloseHandle(v1, v11, v12);
      return v5;
    }
    Thread = CreateThread(
               0,
               0,
               SBE2PauseBuffer::CSBE2PauseBufferWriter::WorkerThreadThunk,
               this,
               0,
               (LPDWORD)this + 224);
    *(_QWORD *)v1 = Thread;
    if ( !Thread )
    {
      v8 = GetLastError();
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      v6 = 161;
      goto LABEL_10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800a8fd0  push    rbx
0x1800a8fd2  push    rsi
0x1800a8fd3  push    rdi
0x1800a8fd4  push    r14
0x1800a8fd6  sub     rsp, 38h
0x1800a8fda  lea     rsi, [rcx+388h]
0x1800a8fe1  mov     rdi, rcx
0x1800a8fe4  cmp     qword ptr [rsi], 0
0x1800a8fe8  jnz     loc_1800A909C
0x1800a8fee  xor     r9d, r9d; lpName
0x1800a8ff1  xor     r8d, r8d; bInitialState
0x1800a8ff4  xor     edx, edx; bManualReset
0x1800a8ff6  xor     ecx, ecx; lpEventAttributes
0x1800a8ff8  call    cs:__imp_CreateEventW
0x1800a8ffe  lea     r14, [rdi+390h]
0x1800a9005  mov     [r14], rax
0x1800a9008  test    rax, rax
0x1800a900b  jnz     short loc_1800A902A
0x1800a900d  call    cs:__imp_GetLastError
0x1800a9013  mov     ebx, eax
0x1800a9015  test    eax, eax
0x1800a9017  jle     short loc_1800A9022
0x1800a9019  movzx   ebx, ax
0x1800a901c  or      ebx, 80070000h
0x1800a9022  mov     r8d, 9Eh
0x1800a9028  jmp     short loc_1800A9075
0x1800a902a  lea     rax, [rdi+380h]
0x1800a9031  mov     r9, rdi; lpParameter
0x1800a9034  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x1800a9039  lea     r8, ?WorkerThreadThunk@CSBE2PauseBufferWriter@SBE2PauseBuffer@@CAKPEAX@Z; lpStartAddress
0x1800a9040  xor     edx, edx; dwStackSize
0x1800a9042  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x1800a904a  xor     ecx, ecx; lpThreadAttributes
0x1800a904c  call    cs:__imp_CreateThread
0x1800a9052  mov     [rsi], rax
0x1800a9055  test    rax, rax
0x1800a9058  jnz     short loc_1800A909C
0x1800a905a  call    cs:__imp_GetLastError
0x1800a9060  mov     ebx, eax
0x1800a9062  test    eax, eax
0x1800a9064  jle     short loc_1800A906F
0x1800a9066  movzx   ebx, ax
0x1800a9069  or      ebx, 80070000h
0x1800a906f  mov     r8d, 0A1h; unsigned int
0x1800a9075  lea     rcx, [rdi+30h]; struct CEhEventTracer *
0x1800a9079  mov     r9d, ebx; unsigned int
0x1800a907c  lea     rdx, aMultimediaDsho_27; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800a9083  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x1800a9088  mov     rcx, r14; this
0x1800a908b  call    ?CloseHandle@SBECoreUtil@@YAXAEAPEAXPEAX@Z; SBECoreUtil::CloseHandle(void * &,void *)
0x1800a9090  mov     rcx, rsi; this
0x1800a9093  call    ?CloseHandle@SBECoreUtil@@YAXAEAPEAXPEAX@Z; SBECoreUtil::CloseHandle(void * &,void *)
0x1800a9098  mov     eax, ebx
0x1800a909a  jmp     short loc_1800A909E
0x1800a909c  xor     eax, eax
0x1800a909e  add     rsp, 38h
0x1800a90a2  pop     r14
0x1800a90a4  pop     rdi
0x1800a90a5  pop     rsi
0x1800a90a6  pop     rbx
0x1800a90a7  retn
```
