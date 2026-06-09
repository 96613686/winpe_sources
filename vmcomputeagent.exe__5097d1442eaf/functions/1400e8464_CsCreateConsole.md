# CsCreateConsole

- ea: `0x1400e8464`
- end: `0x1400e8695`
- name: `CsCreateConsole`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400e4970`

## callees

- `0x1400e8464`
- `0x1400e869c`
- `0x1400e8b3c`

## import_xrefs

- `ntdll!NtCreateEvent` at `0x1400e8583`
- `ntdll!NtCreateEvent` at `0x1400e8583`
- `ntdll!TpAllocIoCompletion` at `0x1400e864c`
- `ntdll!TpAllocIoCompletion` at `0x1400e864c`
- `ntdll!RtlInitializeSRWLock` at `0x1400e8534`
- `ntdll!RtlInitializeSRWLock` at `0x1400e853e`
- `ntdll!RtlInitializeSRWLock` at `0x1400e8534`
- `ntdll!RtlInitializeSRWLock` at `0x1400e853e`
- `ntdll!RtlFreeHeap` at `0x1400e85a1`
- `ntdll!RtlFreeHeap` at `0x1400e867b`
- `ntdll!RtlFreeHeap` at `0x1400e85a1`
- `ntdll!RtlFreeHeap` at `0x1400e867b`
- `ntdll!RtlAllocateHeap` at `0x1400e84ad`
- `ntdll!RtlAllocateHeap` at `0x1400e84ad`
- `ntdll!NtDeviceIoControlFile` at `0x1400e85fc`
- `ntdll!NtDeviceIoControlFile` at `0x1400e85fc`
- `ntdll!NtClose` at `0x1400e860b`
- `ntdll!NtClose` at `0x1400e8663`
- `ntdll!NtClose` at `0x1400e860b`
- `ntdll!NtClose` at `0x1400e8663`

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
  v13[24] = v13 + 23;
  v13[9] = v13 + 8;
  v13[8] = v13 + 8;
  *v15 = v15;
  v13[11] = v13 + 10;
  v16 = v13 + 1;
  v13[10] = v13 + 10;
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
0x1400e8464  mov     rax, rsp
0x1400e8467  push    rbx
0x1400e8468  push    rbp
0x1400e8469  push    rsi
0x1400e846a  push    rdi
0x1400e846b  push    r14
0x1400e846d  sub     rsp, 70h
0x1400e8471  mov     r14, rcx
0x1400e8474  mov     qword ptr [rax+40h], 0
0x1400e847c  xorps   xmm0, xmm0
0x1400e847f  mov     qword ptr [rax-48h], 0
0x1400e8487  movups  xmmword ptr [rax-40h], xmm0
0x1400e848b  mov     rcx, gs:60h
0x1400e8494  mov     rsi, r8
0x1400e8497  mov     rbp, rdx
0x1400e849a  mov     r8d, 998h; Size
0x1400e84a0  mov     edx, 8; Flags
0x1400e84a5  movzx   ebx, r9w
0x1400e84a9  mov     rcx, [rcx+30h]; HeapHandle
0x1400e84ad  call    cs:__imp_RtlAllocateHeap
0x1400e84b3  mov     rdi, rax
0x1400e84b6  test    rax, rax
0x1400e84b9  jnz     short loc_1400E84C5
0x1400e84bb  mov     eax, 0C000009Ah
0x1400e84c0  jmp     loc_1400E868A
0x1400e84c5  mov     [rax+28h], bx
0x1400e84c9  lea     rcx, [rdi+68h]
0x1400e84cd  mov     [rax], rbp
0x1400e84d0  lea     rbx, [rdi+0B8h]
0x1400e84d7  movzx   eax, [rsp+98h+arg_20]
0x1400e84df  mov     [rdi+2Ah], ax
0x1400e84e3  movzx   eax, [rsp+98h+arg_28]
0x1400e84eb  mov     [rdi+2Ch], ax
0x1400e84ef  movzx   eax, [rsp+98h+arg_30]
0x1400e84f7  mov     [rdi+2Eh], ax
0x1400e84fb  lea     rax, ?Callbacks@ConsoleToPipeRedirector@@0U_CS_CONSOLE_CALLBACK@@B; _CS_CONSOLE_CALLBACK const ConsoleToPipeRedirector::Callbacks
0x1400e8502  mov     [rdi+20h], rax
0x1400e8506  mov     byte ptr [rdi+38h], 0
0x1400e850a  mov     [rdi+10h], rsi
0x1400e850e  mov     qword ptr [rdi+88h], 0
0x1400e8519  mov     dword ptr [rdi+90h], 0
0x1400e8523  mov     dword ptr [rdi+84h], 7
0x1400e852d  mov     [rdi+0B0h], rbx
0x1400e8534  call    cs:__imp_RtlInitializeSRWLock
0x1400e853a  lea     rcx, [rdi+30h]
0x1400e853e  call    cs:__imp_RtlInitializeSRWLock
0x1400e8544  lea     rax, [rdi+40h]
0x1400e8548  mov     [rbx+8], rbx
0x1400e854c  mov     [rax+8], rax
0x1400e8550  xor     r9d, r9d; EventType
0x1400e8553  mov     [rax], rax
0x1400e8556  xor     r8d, r8d; ObjectAttributes
0x1400e8559  lea     rax, [rdi+50h]
0x1400e855d  mov     [rbx], rbx
0x1400e8560  mov     [rax+8], rax
0x1400e8564  lea     rbx, [rdi+8]
0x1400e8568  mov     [rax], rax
0x1400e856b  mov     edx, 100002h; DesiredAccess
0x1400e8570  lea     rax, [rdi+70h]
0x1400e8574  mov     [rsp+98h+InitialState], 0; InitialState
0x1400e8579  mov     rcx, rbx; EventHandle
0x1400e857c  mov     [rax+8], rax
0x1400e8580  mov     [rax], rax
0x1400e8583  call    cs:__imp_NtCreateEvent
0x1400e8589  mov     esi, eax
0x1400e858b  test    eax, eax
0x1400e858d  jns     short loc_1400E85AE
0x1400e858f  mov     rcx, gs:60h
0x1400e8598  mov     r8, rdi; P
0x1400e859b  xor     edx, edx; Flags
0x1400e859d  mov     rcx, [rcx+30h]; HeapHandle
0x1400e85a1  call    cs:__imp_RtlFreeHeap
0x1400e85a7  mov     eax, esi
0x1400e85a9  jmp     loc_1400E868A
0x1400e85ae  mov     rax, [rbx]
0x1400e85b1  xor     r9d, r9d; ApcContext
0x1400e85b4  mov     [rsp+98h+OutputBufferLength], 0; OutputBufferLength
0x1400e85bc  xor     r8d, r8d; ApcRoutine
0x1400e85bf  mov     [rsp+98h+OutputBuffer], 0; OutputBuffer
0x1400e85c8  xor     edx, edx; Event
0x1400e85ca  mov     [rsp+98h+arg_38], rax
0x1400e85d2  mov     rcx, rbp; FileHandle
0x1400e85d5  mov     [rsp+98h+InputBufferLength], 8; InputBufferLength
0x1400e85dd  lea     rax, [rsp+98h+arg_38]
0x1400e85e5  mov     [rsp+98h+InputBuffer], rax; InputBuffer
0x1400e85ea  lea     rax, [rsp+98h+IoStatusBlock]
0x1400e85ef  mov     [rsp+98h+IoControlCode], 50001Fh; IoControlCode
0x1400e85f7  mov     qword ptr [rsp+98h+InitialState], rax; IoStatusBlock
0x1400e85fc  call    cs:__imp_NtDeviceIoControlFile
0x1400e8602  mov     esi, eax
0x1400e8604  test    eax, eax
0x1400e8606  jns     short loc_1400E8616
0x1400e8608  mov     rcx, [rbx]; Handle
0x1400e860b  call    cs:__imp_NtClose
0x1400e8611  jmp     loc_1400E858F
0x1400e8616  mov     rdx, rdi
0x1400e8619  lea     rcx, [rsp+98h+var_48]
0x1400e861e  call    CspAllocateServerScreen
0x1400e8623  mov     esi, eax
0x1400e8625  test    eax, eax
0x1400e8627  js      short loc_1400E8608
0x1400e8629  mov     rsi, [rsp+98h+var_48]
0x1400e862e  lea     rcx, [rdi+18h]
0x1400e8632  mov     rdx, [rdi]
0x1400e8635  lea     r8, CspConsoleIoRead
0x1400e863c  mov     r9, rdi
0x1400e863f  mov     [rdi+60h], rsi
0x1400e8643  mov     qword ptr [rsp+98h+InitialState], 0
0x1400e864c  call    cs:__imp_TpAllocIoCompletion
0x1400e8652  mov     ebp, eax
0x1400e8654  test    eax, eax
0x1400e8656  jns     short loc_1400E8685
0x1400e8658  mov     rcx, rsi
0x1400e865b  call    CspFreeServerScreen
0x1400e8660  mov     rcx, [rbx]; Handle
0x1400e8663  call    cs:__imp_NtClose
0x1400e8669  mov     rcx, gs:60h
0x1400e8672  mov     r8, rdi; P
0x1400e8675  xor     edx, edx; Flags
0x1400e8677  mov     rcx, [rcx+30h]; HeapHandle
0x1400e867b  call    cs:__imp_RtlFreeHeap
0x1400e8681  mov     eax, ebp
0x1400e8683  jmp     short loc_1400E868A
0x1400e8685  mov     [r14], rdi
0x1400e8688  xor     eax, eax
0x1400e868a  add     rsp, 70h
0x1400e868e  pop     r14
0x1400e8690  pop     rdi
0x1400e8691  pop     rsi
0x1400e8692  pop     rbp
0x1400e8693  pop     rbx
0x1400e8694  retn
```
