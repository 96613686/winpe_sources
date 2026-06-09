# CsCreateConsole

- ea: `0x1400fe49c`
- end: `0x1400fe70a`
- name: `CsCreateConsole`
- size: `622`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400fe2c0`

## callees

- `0x1400fe49c`
- `0x140126eb4`
- `0x14029de70`

## import_xrefs

- `ntdll!NtCreateEvent` at `0x1400fe5cd`
- `ntdll!NtCreateEvent` at `0x1400fe5cd`
- `ntdll!RtlInitializeSRWLock` at `0x1400fe572`
- `ntdll!RtlInitializeSRWLock` at `0x1400fe582`
- `ntdll!RtlInitializeSRWLock` at `0x1400fe572`
- `ntdll!RtlInitializeSRWLock` at `0x1400fe582`
- `ntdll!NtDeviceIoControlFile` at `0x1400fe652`
- `ntdll!NtDeviceIoControlFile` at `0x1400fe652`
- `ntdll!RtlAllocateHeap` at `0x1400fe4e5`
- `ntdll!RtlAllocateHeap` at `0x1400fe4e5`
- `ntdll!NtClose` at `0x1400fe667`
- `ntdll!NtClose` at `0x1400fe6cb`
- `ntdll!NtClose` at `0x1400fe667`
- `ntdll!NtClose` at `0x1400fe6cb`
- `ntdll!RtlFreeHeap` at `0x1400fe5f1`
- `ntdll!RtlFreeHeap` at `0x1400fe6e9`
- `ntdll!RtlFreeHeap` at `0x1400fe5f1`
- `ntdll!RtlFreeHeap` at `0x1400fe6e9`
- `ntdll!TpAllocIoCompletion` at `0x1400fe6ae`
- `ntdll!TpAllocIoCompletion` at `0x1400fe6ae`

## pseudocode

```c
__int64 __fastcall CsCreateConsole(
        void ***a1,
        void *a2,
        __int64 a3,
        __int16 a4,
        __int16 a5,
        __int16 a6,
        __int16 a7,
        HANDLE InputBuffer)
{
  _QWORD *Heap; // rax
  void **v13; // rdi
  _QWORD *v15; // rbx
  HANDLE *v16; // rbx
  NTSTATUS Event; // esi
  void *v18; // rsi
  void *v19; // rdx
  int v20; // ebp
  void *v21; // [rsp+50h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-40h] BYREF

  InputBuffer = 0;
  v21 = 0;
  IoStatusBlock = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x998u);
  v13 = (void **)Heap;
  if ( !Heap )
    return 3221225626LL;
  *((_WORD *)Heap + 20) = a4;
  *Heap = a2;
  v15 = Heap + 23;
  *((_WORD *)Heap + 21) = a5;
  *((_WORD *)Heap + 22) = a6;
  *((_WORD *)Heap + 23) = a7;
  Heap[4] = &ConsoleToPipeRedirector::Callbacks;
  *((_BYTE *)Heap + 56) = 0;
  Heap[2] = a3;
  Heap[17] = 0;
  *((_DWORD *)Heap + 36) = 0;
  *((_DWORD *)Heap + 33) = 7;
  Heap[22] = Heap + 23;
  RtlInitializeSRWLock(Heap + 13);
  RtlInitializeSRWLock(v13 + 6);
  v13[9] = v13 + 8;
  v13[8] = v13 + 8;
  v13[11] = v13 + 10;
  v13[10] = v13 + 10;
  v13[24] = v13 + 23;
  *v15 = v15;
  v16 = v13 + 1;
  v13[15] = v13 + 14;
  v13[14] = v13 + 14;
  Event = NtCreateEvent(v13 + 1, 0x100002u, 0, NotificationEvent, 0);
  if ( Event < 0 )
    goto LABEL_4;
  InputBuffer = *v16;
  Event = NtDeviceIoControlFile(a2, 0, 0, 0, &IoStatusBlock, 0x50001Fu, &InputBuffer, 8u, 0, 0);
  if ( Event < 0 || (Event = CspAllocateServerScreen(&v21, v13), Event < 0) )
  {
    NtClose(*v16);
LABEL_4:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
    return (unsigned int)Event;
  }
  v18 = v21;
  v19 = *v13;
  v13[12] = v21;
  v20 = TpAllocIoCompletion(v13 + 3, v19, CspConsoleIoRead, v13, 0);
  if ( v20 >= 0 )
  {
    *a1 = v13;
    return 0;
  }
  else
  {
    CspFreeServerScreen(v18);
    NtClose(*v16);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
    return (unsigned int)v20;
  }
}

```

## disassembly

```asm
0x1400fe49c  mov     rax, rsp
0x1400fe49f  push    rbx
0x1400fe4a0  push    rbp
0x1400fe4a1  push    rsi
0x1400fe4a2  push    rdi
0x1400fe4a3  push    r14
0x1400fe4a5  sub     rsp, 70h
0x1400fe4a9  mov     r14, rcx
0x1400fe4ac  mov     qword ptr [rax+40h], 0
0x1400fe4b4  xorps   xmm0, xmm0
0x1400fe4b7  mov     qword ptr [rax-48h], 0
0x1400fe4bf  movups  xmmword ptr [rax-40h], xmm0
0x1400fe4c3  mov     rcx, gs:60h
0x1400fe4cc  mov     rsi, r8
0x1400fe4cf  mov     rbp, rdx
0x1400fe4d2  mov     r8d, 998h; Size
0x1400fe4d8  mov     edx, 8; Flags
0x1400fe4dd  movzx   ebx, r9w
0x1400fe4e1  mov     rcx, [rcx+30h]; HeapHandle
0x1400fe4e5  call    cs:__imp_RtlAllocateHeap
0x1400fe4ec  nop     dword ptr [rax+rax+00h]
0x1400fe4f1  mov     rdi, rax
0x1400fe4f4  test    rax, rax
0x1400fe4f7  jnz     short loc_1400FE503
0x1400fe4f9  mov     eax, 0C000009Ah
0x1400fe4fe  jmp     loc_1400FE6FE
0x1400fe503  mov     [rax+28h], bx
0x1400fe507  lea     rcx, [rdi+68h]
0x1400fe50b  mov     [rax], rbp
0x1400fe50e  lea     rbx, [rdi+0B8h]
0x1400fe515  movzx   eax, [rsp+98h+arg_20]
0x1400fe51d  mov     [rdi+2Ah], ax
0x1400fe521  movzx   eax, [rsp+98h+arg_28]
0x1400fe529  mov     [rdi+2Ch], ax
0x1400fe52d  movzx   eax, [rsp+98h+arg_30]
0x1400fe535  mov     [rdi+2Eh], ax
0x1400fe539  lea     rax, ?Callbacks@ConsoleToPipeRedirector@@0U_CS_CONSOLE_CALLBACK@@B; _CS_CONSOLE_CALLBACK const ConsoleToPipeRedirector::Callbacks
0x1400fe540  mov     [rdi+20h], rax
0x1400fe544  mov     byte ptr [rdi+38h], 0
0x1400fe548  mov     [rdi+10h], rsi
0x1400fe54c  mov     qword ptr [rdi+88h], 0
0x1400fe557  mov     dword ptr [rdi+90h], 0
0x1400fe561  mov     dword ptr [rdi+84h], 7
0x1400fe56b  mov     [rdi+0B0h], rbx
0x1400fe572  call    cs:__imp_RtlInitializeSRWLock
0x1400fe579  nop     dword ptr [rax+rax+00h]
0x1400fe57e  lea     rcx, [rdi+30h]
0x1400fe582  call    cs:__imp_RtlInitializeSRWLock
0x1400fe589  nop     dword ptr [rax+rax+00h]
0x1400fe58e  lea     rax, [rdi+40h]
0x1400fe592  mov     [rsp+98h+InitialState], 0; InitialState
0x1400fe597  mov     [rax+8], rax
0x1400fe59b  xor     r9d, r9d; EventType
0x1400fe59e  mov     [rax], rax
0x1400fe5a1  xor     r8d, r8d; ObjectAttributes
0x1400fe5a4  lea     rax, [rdi+50h]
0x1400fe5a8  mov     edx, 100002h; DesiredAccess
0x1400fe5ad  mov     [rax+8], rax
0x1400fe5b1  mov     [rax], rax
0x1400fe5b4  lea     rax, [rdi+70h]
0x1400fe5b8  mov     [rbx+8], rbx
0x1400fe5bc  mov     [rbx], rbx
0x1400fe5bf  lea     rbx, [rdi+8]
0x1400fe5c3  mov     rcx, rbx; EventHandle
0x1400fe5c6  mov     [rax+8], rax
0x1400fe5ca  mov     [rax], rax
0x1400fe5cd  call    cs:__imp_NtCreateEvent
0x1400fe5d4  nop     dword ptr [rax+rax+00h]
0x1400fe5d9  mov     esi, eax
0x1400fe5db  test    eax, eax
0x1400fe5dd  jns     short loc_1400FE604
0x1400fe5df  mov     rcx, gs:60h
0x1400fe5e8  mov     r8, rdi; P
0x1400fe5eb  xor     edx, edx; Flags
0x1400fe5ed  mov     rcx, [rcx+30h]; HeapHandle
0x1400fe5f1  call    cs:__imp_RtlFreeHeap
0x1400fe5f8  nop     dword ptr [rax+rax+00h]
0x1400fe5fd  mov     eax, esi
0x1400fe5ff  jmp     loc_1400FE6FE
0x1400fe604  mov     rax, [rbx]
0x1400fe607  xor     r9d, r9d; ApcContext
0x1400fe60a  mov     [rsp+98h+OutputBufferLength], 0; OutputBufferLength
0x1400fe612  xor     r8d, r8d; ApcRoutine
0x1400fe615  mov     [rsp+98h+OutputBuffer], 0; OutputBuffer
0x1400fe61e  xor     edx, edx; Event
0x1400fe620  mov     [rsp+98h+arg_38], rax
0x1400fe628  mov     rcx, rbp; FileHandle
0x1400fe62b  mov     [rsp+98h+InputBufferLength], 8; InputBufferLength
0x1400fe633  lea     rax, [rsp+98h+arg_38]
0x1400fe63b  mov     [rsp+98h+InputBuffer], rax; InputBuffer
0x1400fe640  lea     rax, [rsp+98h+IoStatusBlock]
0x1400fe645  mov     [rsp+98h+IoControlCode], 50001Fh; IoControlCode
0x1400fe64d  mov     qword ptr [rsp+98h+InitialState], rax; IoStatusBlock
0x1400fe652  call    cs:__imp_NtDeviceIoControlFile
0x1400fe659  nop     dword ptr [rax+rax+00h]
0x1400fe65e  mov     esi, eax
0x1400fe660  test    eax, eax
0x1400fe662  jns     short loc_1400FE678
0x1400fe664  mov     rcx, [rbx]; Handle
0x1400fe667  call    cs:__imp_NtClose
0x1400fe66e  nop     dword ptr [rax+rax+00h]
0x1400fe673  jmp     loc_1400FE5DF
0x1400fe678  mov     rdx, rdi
0x1400fe67b  lea     rcx, [rsp+98h+var_48]
0x1400fe680  call    CspAllocateServerScreen
0x1400fe685  mov     esi, eax
0x1400fe687  test    eax, eax
0x1400fe689  js      short loc_1400FE664
0x1400fe68b  mov     rsi, [rsp+98h+var_48]
0x1400fe690  lea     rcx, [rdi+18h]
0x1400fe694  mov     rdx, [rdi]
0x1400fe697  lea     r8, CspConsoleIoRead
0x1400fe69e  mov     r9, rdi
0x1400fe6a1  mov     [rdi+60h], rsi
0x1400fe6a5  mov     qword ptr [rsp+98h+InitialState], 0
0x1400fe6ae  call    cs:__imp_TpAllocIoCompletion
0x1400fe6b5  nop     dword ptr [rax+rax+00h]
0x1400fe6ba  mov     ebp, eax
0x1400fe6bc  test    eax, eax
0x1400fe6be  jns     short loc_1400FE6F9
0x1400fe6c0  mov     rcx, rsi
0x1400fe6c3  call    CspFreeServerScreen
0x1400fe6c8  mov     rcx, [rbx]; Handle
0x1400fe6cb  call    cs:__imp_NtClose
0x1400fe6d2  nop     dword ptr [rax+rax+00h]
0x1400fe6d7  mov     rcx, gs:60h
0x1400fe6e0  mov     r8, rdi; P
0x1400fe6e3  xor     edx, edx; Flags
0x1400fe6e5  mov     rcx, [rcx+30h]; HeapHandle
0x1400fe6e9  call    cs:__imp_RtlFreeHeap
0x1400fe6f0  nop     dword ptr [rax+rax+00h]
0x1400fe6f5  mov     eax, ebp
0x1400fe6f7  jmp     short loc_1400FE6FE
0x1400fe6f9  mov     [r14], rdi
0x1400fe6fc  xor     eax, eax
0x1400fe6fe  add     rsp, 70h
0x1400fe702  pop     r14
0x1400fe704  pop     rdi
0x1400fe705  pop     rsi
0x1400fe706  pop     rbp
0x1400fe707  pop     rbx
0x1400fe708  retn
```
