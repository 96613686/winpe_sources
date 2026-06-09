# CPVRAsyncWriter::CPVRAsyncWriter(void *,void *,ulong,ulong,ulong,ulong,CAsyncIo *,CPVRIOCounters *,ulong,void * *,void (*)(void *,ulong,__int64,__int64),void *,int,ulong *)

- ea: `0x180077a4c`
- end: `0x180077c15`
- name: `??0CPVRAsyncWriter@@QEAA@PEAX0KKKKPEAVCAsyncIo@@PEAVCPVRIOCounters@@KPEAPEAXP6AX0K_J4@Z0HPEAK@Z`
- size: `457`
- prototype: `CPVRAsyncWriter *(CPVRAsyncWriter *__hidden this, void *, void *, unsigned int, unsigned int, unsigned int, unsigned int, struct CAsyncIo *, struct CPVRIOCounters *, unsigned int, void **, void (*)(void *, unsigned int, __int64, __int64), void *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180077d14`

## callees

- `0x180077a4c`
- `0x180078dac`

## import_xrefs

- `KERNEL32!DuplicateHandle` at `0x180077b71`
- `KERNEL32!DuplicateHandle` at `0x180077bba`
- `KERNEL32!DuplicateHandle` at `0x180077b71`
- `KERNEL32!DuplicateHandle` at `0x180077bba`
- `KERNEL32!CreateEventW` at `0x180077be9`
- `KERNEL32!CreateEventW` at `0x180077be9`
- `KERNEL32!InitializeCriticalSection` at `0x180077b20`
- `KERNEL32!InitializeCriticalSection` at `0x180077b20`
- `KERNEL32!GetLastError` at `0x180077b7b`
- `KERNEL32!GetLastError` at `0x180077bfb`
- `KERNEL32!GetLastError` at `0x180077b7b`
- `KERNEL32!GetLastError` at `0x180077bfb`
- `KERNEL32!GetCurrentProcess` at `0x180077b43`
- `KERNEL32!GetCurrentProcess` at `0x180077b4c`
- `KERNEL32!GetCurrentProcess` at `0x180077b8d`
- `KERNEL32!GetCurrentProcess` at `0x180077b96`
- `KERNEL32!GetCurrentProcess` at `0x180077b43`
- `KERNEL32!GetCurrentProcess` at `0x180077b4c`
- `KERNEL32!GetCurrentProcess` at `0x180077b8d`
- `KERNEL32!GetCurrentProcess` at `0x180077b96`

## pseudocode

```c
CPVRAsyncWriter *__fastcall CPVRAsyncWriter::CPVRAsyncWriter(
        CPVRAsyncWriter *this,
        void *a2,
        void *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        struct CAsyncIo *a8,
        struct CPVRIOCounters *a9,
        unsigned int a10,
        void **a11,
        void (*a12)(void *, unsigned int, __int64, __int64),
        void *a13,
        int a14,
        unsigned int *a15)
{
  HANDLE *v15; // r15
  HANDLE CurrentProcess; // rbx
  HANDLE v20; // rax
  HANDLE v21; // rbx
  HANDLE v22; // rax
  unsigned int v23; // eax
  HANDLE EventW; // rax

  v15 = (HANDLE *)((char *)this + 16);
  *((_DWORD *)this + 8) = 0;
  *(_QWORD *)this = &CPVRAsyncWriter::`vftable';
  *((_QWORD *)this + 1) = a8;
  *((_QWORD *)this + 3) = -1;
  *((_QWORD *)this + 2) = -1;
  *((_DWORD *)this + 28) = a14;
  *((_QWORD *)this + 10) = &CPVRWriteBufferStreamWriter::`vftable';
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 30) = a6;
  *((_DWORD *)this + 31) = a7;
  *((_QWORD *)this + 17) = a9;
  *((_QWORD *)this + 21) = a12;
  *((_QWORD *)this + 22) = a13;
  *((_DWORD *)this + 46) = a10;
  *((_QWORD *)this + 24) = a11;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 20) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 1);
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 1) + 184LL));
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 17) + 24LL));
  *((_DWORD *)this + 36) = 0;
  CurrentProcess = GetCurrentProcess();
  v20 = GetCurrentProcess();
  if ( !DuplicateHandle(v20, a3, CurrentProcess, (LPHANDLE)this + 3, 0, 0, 2u)
    || (v21 = GetCurrentProcess(), v22 = GetCurrentProcess(), !DuplicateHandle(v22, a2, v21, v15, 0, 0, 2u))
    || (v23 = CAsyncIo::Bind(*((_QWORD *)this + 1), *v15), (*a15 = v23) == 0)
    && (EventW = CreateEventW(0, 1, 0, 0), (*((_QWORD *)this + 20) = EventW) == 0) )
  {
    *a15 = GetLastError();
  }
  return this;
}

```

## disassembly

```asm
0x180077a4c  push    rbx
0x180077a4e  push    rbp
0x180077a4f  push    rsi
0x180077a50  push    rdi
0x180077a51  push    r12
0x180077a53  push    r14
0x180077a55  push    r15
0x180077a57  sub     rsp, 40h
0x180077a5b  xor     r12d, r12d
0x180077a5e  lea     r15, [rcx+10h]
0x180077a62  mov     [rcx+20h], r12d
0x180077a66  lea     rax, ??_7CPVRAsyncWriter@@6B@; const CPVRAsyncWriter::`vftable'
0x180077a6d  mov     [rcx], rax
0x180077a70  mov     r14, rcx
0x180077a73  mov     rax, [rsp+78h+arg_38]
0x180077a7b  mov     rsi, r8
0x180077a7e  mov     [rcx+8], rax
0x180077a82  mov     rbp, rdx
0x180077a85  or      rax, 0FFFFFFFFFFFFFFFFh
0x180077a89  mov     [rcx+18h], rax
0x180077a8d  mov     [r15], rax
0x180077a90  mov     eax, [rsp+78h+arg_68]
0x180077a97  mov     [rcx+70h], eax
0x180077a9a  lea     rax, ??_7CPVRWriteBufferStreamWriter@@6B@; const CPVRWriteBufferStreamWriter::`vftable'
0x180077aa1  mov     [rcx+50h], rax
0x180077aa5  mov     eax, [rsp+78h+arg_28]
0x180077aac  mov     [rcx+58h], r12
0x180077ab0  mov     [rcx+60h], r12
0x180077ab4  mov     [rcx+68h], r12
0x180077ab8  mov     [rcx+78h], eax
0x180077abb  mov     eax, [rsp+78h+arg_30]
0x180077ac2  mov     [rcx+7Ch], eax
0x180077ac5  mov     rax, [rsp+78h+arg_40]
0x180077acd  mov     [rcx+88h], rax
0x180077ad4  mov     rax, [rsp+78h+arg_58]
0x180077adc  mov     [rcx+0A8h], rax
0x180077ae3  mov     rax, [rsp+78h+arg_60]
0x180077aeb  mov     [rcx+0B0h], rax
0x180077af2  mov     eax, [rsp+78h+arg_48]
0x180077af9  mov     [rcx+0B8h], eax
0x180077aff  mov     rax, [rsp+78h+arg_50]
0x180077b07  mov     [rcx+0C0h], rax
0x180077b0e  mov     [rcx+80h], r12
0x180077b15  mov     [rcx+0A0h], r12
0x180077b1c  add     rcx, 28h ; '('; lpCriticalSection
0x180077b20  call    cs:__imp_InitializeCriticalSection
0x180077b26  mov     rax, [r14+8]
0x180077b2a  lock inc dword ptr [rax+0B8h]
0x180077b31  mov     rax, [r14+88h]
0x180077b38  lock inc dword ptr [rax+18h]
0x180077b3c  mov     [r14+90h], r12d
0x180077b43  call    cs:__imp_GetCurrentProcess
0x180077b49  mov     rbx, rax
0x180077b4c  call    cs:__imp_GetCurrentProcess
0x180077b52  mov     [rsp+78h+dwOptions], 2; dwOptions
0x180077b5a  lea     r9, [r14+18h]; lpTargetHandle
0x180077b5e  mov     rcx, rax; hSourceProcessHandle
0x180077b61  mov     [rsp+78h+bInheritHandle], r12d; bInheritHandle
0x180077b66  mov     r8, rbx; hTargetProcessHandle
0x180077b69  mov     [rsp+78h+dwDesiredAccess], r12d; dwDesiredAccess
0x180077b6e  mov     rdx, rsi; hSourceHandle
0x180077b71  call    cs:__imp_DuplicateHandle
0x180077b77  test    eax, eax
0x180077b79  jnz     short loc_180077B8D
0x180077b7b  call    cs:__imp_GetLastError
0x180077b81  mov     rcx, [rsp+78h+arg_70]
0x180077b89  mov     [rcx], eax
0x180077b8b  jmp     short loc_180077C03
0x180077b8d  call    cs:__imp_GetCurrentProcess
0x180077b93  mov     rbx, rax
0x180077b96  call    cs:__imp_GetCurrentProcess
0x180077b9c  mov     [rsp+78h+dwOptions], 2; dwOptions
0x180077ba4  mov     r9, r15; lpTargetHandle
0x180077ba7  mov     rcx, rax; hSourceProcessHandle
0x180077baa  mov     [rsp+78h+bInheritHandle], r12d; bInheritHandle
0x180077baf  mov     r8, rbx; hTargetProcessHandle
0x180077bb2  mov     [rsp+78h+dwDesiredAccess], r12d; dwDesiredAccess
0x180077bb7  mov     rdx, rbp; hSourceHandle
0x180077bba  call    cs:__imp_DuplicateHandle
0x180077bc0  test    eax, eax
0x180077bc2  jz      short loc_180077B7B
0x180077bc4  mov     rdx, [r15]; FileHandle
0x180077bc7  mov     rcx, [r14+8]; CompletionKey
0x180077bcb  call    ?Bind@CAsyncIo@@QEAAKPEAX_K@Z; CAsyncIo::Bind(void *,unsigned __int64)
0x180077bd0  mov     rbx, [rsp+78h+arg_70]
0x180077bd8  mov     [rbx], eax
0x180077bda  test    eax, eax
0x180077bdc  jnz     short loc_180077C03
0x180077bde  xor     r9d, r9d; lpName
0x180077be1  lea     edx, [rax+1]; bManualReset
0x180077be4  xor     r8d, r8d; bInitialState
0x180077be7  xor     ecx, ecx; lpEventAttributes
0x180077be9  call    cs:__imp_CreateEventW
0x180077bef  mov     [r14+0A0h], rax
0x180077bf6  test    rax, rax
0x180077bf9  jnz     short loc_180077C03
0x180077bfb  call    cs:__imp_GetLastError
0x180077c01  mov     [rbx], eax
0x180077c03  mov     rax, r14
0x180077c06  add     rsp, 40h
0x180077c0a  pop     r15
0x180077c0c  pop     r14
0x180077c0e  pop     r12
0x180077c10  pop     rdi
0x180077c11  pop     rsi
0x180077c12  pop     rbp
0x180077c13  pop     rbx
0x180077c14  retn
```
