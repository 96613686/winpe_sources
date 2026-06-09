# AslTelemetryCreate

- ea: `0x14000c1a0`
- end: `0x14000c3e2`
- name: `AslTelemetryCreate`
- size: `578`
- prototype: `__int64 __fastcall(_QWORD *, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140005668`

## callees

- `0x140001214`
- `0x14000c1a0`
- `0x14000c3e8`
- `0x14000d710`
- `0x14001008c`
- `0x14002e3e2`

## import_xrefs

- `msvcrt!strcpy_s` at `0x14000c255`
- `msvcrt!strcpy_s` at `0x14000c255`
- `ntdll!RtlAllocateHeap` at `0x14000c1ea`
- `ntdll!RtlAllocateHeap` at `0x14000c2f3`
- `ntdll!RtlAllocateHeap` at `0x14000c1ea`
- `ntdll!RtlAllocateHeap` at `0x14000c2f3`
- `ntdll!RtlInitializeCriticalSection` at `0x14000c221`
- `ntdll!RtlInitializeCriticalSection` at `0x14000c221`
- `ntdll!RtlFreeHeap` at `0x14000c283`
- `ntdll!RtlFreeHeap` at `0x14000c33f`
- `ntdll!RtlFreeHeap` at `0x14000c376`
- `ntdll!RtlFreeHeap` at `0x14000c283`
- `ntdll!RtlFreeHeap` at `0x14000c33f`
- `ntdll!RtlFreeHeap` at `0x14000c376`

## string_xrefs

- `0x14000c205`: `AslTelemetryCreate`

## pseudocode

```c
__int64 __fastcall AslTelemetryCreate(_QWORD *a1, const char *a2)
{
  char *Heap; // rax
  char *v5; // rbx
  unsigned int v6; // edi
  void *v7; // r8
  PVOID ProcessHeap; // r9
  PVOID v9; // rax
  PVOID v10; // rdi
  void *v11; // r8
  void *v12; // r8

  if ( _InterlockedIncrement(&dword_140042B10) == 1 )
    TraceLoggingRegister_EventRegister_2U();
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xF8u);
  v5 = Heap;
  if ( !Heap )
  {
    v6 = -1073741801;
    AslLogCallPrintf(1, "AslTelemetryCreate", 204, "Out of memory");
    return v6;
  }
  RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 88));
  *((_QWORD *)v5 + 28) = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                        * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
  strcpy_s(v5, 0x40u, a2);
  v6 = AslAnsiStringCreate((PANSI_STRING)(v5 + 72));
  if ( (v6 & 0x80000000) != 0 )
  {
LABEL_20:
    AslTelemetryDelete(v5);
    return v6;
  }
  v7 = (void *)*((_QWORD *)v5 + 21);
  if ( v7 )
    RtlFreeHeap(*((HANDLE *)v5 + 16), 0, v7);
  *((_OWORD *)v5 + 8) = 0;
  *((_OWORD *)v5 + 9) = 0;
  *((_OWORD *)v5 + 10) = 0;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  *((_QWORD *)v5 + 16) = ProcessHeap;
  *((_QWORD *)v5 + 20) = 64;
  *((_QWORD *)v5 + 17) = 72;
  if ( !is_mul_ok(0, 0x48u) || !is_mul_ok(0x40u, 0x48u) )
  {
    v6 = -1073741675;
    goto LABEL_14;
  }
  v9 = RtlAllocateHeap(ProcessHeap, (0x40 * (unsigned __int128)0x48u) >> 64, 0x1200u);
  v10 = v9;
  if ( !v9 )
  {
    v6 = -1073741801;
LABEL_14:
    v11 = (void *)*((_QWORD *)v5 + 21);
    if ( v11 )
      RtlFreeHeap(*((HANDLE *)v5 + 16), 0, v11);
    *((_OWORD *)v5 + 8) = 0;
    *((_OWORD *)v5 + 9) = 0;
    *((_OWORD *)v5 + 10) = 0;
    goto LABEL_20;
  }
  memset_0(v9, 0, 0x1200u);
  *((_QWORD *)v5 + 21) = v10;
  *((_QWORD *)v5 + 19) = 64;
  v12 = (void *)*((_QWORD *)v5 + 27);
  if ( v12 )
    RtlFreeHeap(*((HANDLE *)v5 + 22), 0, v12);
  v6 = 0;
  *((_OWORD *)v5 + 11) = 0;
  *((_OWORD *)v5 + 12) = 0;
  *((_OWORD *)v5 + 13) = 0;
  *((_QWORD *)v5 + 22) = NtCurrentPeb()->ProcessHeap;
  *((_QWORD *)v5 + 26) = 4;
  *((_QWORD *)v5 + 23) = 48;
  *a1 = v5;
  return v6;
}

```

## disassembly

```asm
0x14000c1a0  mov     [rsp+arg_0], rbx
0x14000c1a5  mov     [rsp+arg_8], rbp
0x14000c1aa  push    rsi
0x14000c1ab  push    rdi
0x14000c1ac  push    r14
0x14000c1ae  sub     rsp, 20h
0x14000c1b2  mov     esi, 1
0x14000c1b7  mov     rdi, rdx
0x14000c1ba  mov     eax, esi
0x14000c1bc  mov     r14, rcx
0x14000c1bf  lock xadd cs:dword_140042B10, eax
0x14000c1c7  add     eax, esi
0x14000c1c9  cmp     eax, esi
0x14000c1cb  jnz     short loc_14000C1D2
0x14000c1cd  call    TraceLoggingRegister_EventRegister_2U
0x14000c1d2  mov     rcx, gs:60h
0x14000c1db  mov     edx, 8; Flags
0x14000c1e0  mov     r8d, 0F8h; Size
0x14000c1e6  mov     rcx, [rcx+30h]; HeapHandle
0x14000c1ea  call    cs:__imp_RtlAllocateHeap
0x14000c1f0  mov     rbx, rax
0x14000c1f3  test    rax, rax
0x14000c1f6  jnz     short loc_14000C21D
0x14000c1f8  lea     r9, aOutOfMemory; "Out of memory"
0x14000c1ff  mov     r8d, 0CCh
0x14000c205  lea     rdx, aAsltelemetrycr; "AslTelemetryCreate"
0x14000c20c  mov     ecx, esi
0x14000c20e  mov     edi, 0C0000017h
0x14000c213  call    AslLogCallPrintf
0x14000c218  jmp     loc_14000C3CD
0x14000c21d  lea     rcx, [rax+58h]; CriticalSection
0x14000c221  call    cs:__imp_RtlInitializeCriticalSection
0x14000c227  mov     ecx, ds:7FFE0004h
0x14000c22e  mov     eax, 7FFE0320h
0x14000c233  shl     rcx, 20h
0x14000c237  mov     ebp, 40h ; '@'
0x14000c23c  mov     r8, rdi; Source
0x14000c23f  mov     rax, [rax]
0x14000c242  shl     rax, 8
0x14000c246  mul     rcx
0x14000c249  mov     rcx, rbx; Destination
0x14000c24c  mov     [rbx+0E0h], rdx
0x14000c253  mov     edx, ebp; SizeInBytes
0x14000c255  call    cs:__imp_strcpy_s
0x14000c25b  lea     rcx, [rbx+48h]; DestinationString
0x14000c25f  call    AslAnsiStringCreate
0x14000c264  mov     edi, eax
0x14000c266  test    eax, eax
0x14000c268  js      loc_14000C3C5
0x14000c26e  mov     r8, [rbx+0A8h]; P
0x14000c275  test    r8, r8
0x14000c278  jz      short loc_14000C289
0x14000c27a  mov     rcx, [rbx+80h]; HeapHandle
0x14000c281  xor     edx, edx; Flags
0x14000c283  call    cs:__imp_RtlFreeHeap
0x14000c289  xorps   xmm0, xmm0
0x14000c28c  mov     [rsp+38h+arg_10], 0
0x14000c295  movups  xmmword ptr [rbx+80h], xmm0
0x14000c29c  mov     r8d, 48h ; 'H'
0x14000c2a2  xor     ecx, ecx
0x14000c2a4  movups  xmmword ptr [rbx+90h], xmm0
0x14000c2ab  movups  xmmword ptr [rbx+0A0h], xmm0
0x14000c2b2  mov     rax, gs:60h
0x14000c2bb  mov     r9, [rax+30h]
0x14000c2bf  mov     eax, r8d
0x14000c2c2  mul     rcx
0x14000c2c5  mov     [rbx+80h], r9
0x14000c2cc  mov     [rbx+0A0h], rbp
0x14000c2d3  mov     [rbx+88h], r8
0x14000c2da  test    rdx, rdx
0x14000c2dd  jnz     short loc_14000C325
0x14000c2df  mov     eax, r8d
0x14000c2e2  mul     rbp
0x14000c2e5  mov     rsi, rax
0x14000c2e8  test    rdx, rdx
0x14000c2eb  jnz     short loc_14000C325
0x14000c2ed  mov     r8, rax; Size
0x14000c2f0  mov     rcx, r9; HeapHandle
0x14000c2f3  call    cs:__imp_RtlAllocateHeap
0x14000c2f9  mov     rdi, rax
0x14000c2fc  test    rax, rax
0x14000c2ff  jz      short loc_14000C31E
0x14000c301  mov     r8, rsi; Size
0x14000c304  xor     edx, edx; Val
0x14000c306  mov     rcx, rax; void *
0x14000c309  call    memset_0
0x14000c30e  mov     [rbx+0A8h], rdi
0x14000c315  mov     [rbx+98h], rbp
0x14000c31c  jmp     short loc_14000C361
0x14000c31e  mov     edi, 0C0000017h
0x14000c323  jmp     short loc_14000C32A
0x14000c325  mov     edi, 0C0000095h
0x14000c32a  mov     r8, [rbx+0A8h]; P
0x14000c331  test    r8, r8
0x14000c334  jz      short loc_14000C345
0x14000c336  mov     rcx, [rbx+80h]; HeapHandle
0x14000c33d  xor     edx, edx; Flags
0x14000c33f  call    cs:__imp_RtlFreeHeap
0x14000c345  xorps   xmm0, xmm0
0x14000c348  movups  xmmword ptr [rbx+80h], xmm0
0x14000c34f  movups  xmmword ptr [rbx+90h], xmm0
0x14000c356  movups  xmmword ptr [rbx+0A0h], xmm0
0x14000c35d  test    edi, edi
0x14000c35f  js      short loc_14000C3C5
0x14000c361  mov     r8, [rbx+0D8h]; P
0x14000c368  test    r8, r8
0x14000c36b  jz      short loc_14000C37C
0x14000c36d  mov     rcx, [rbx+0B0h]; HeapHandle
0x14000c374  xor     edx, edx; Flags
0x14000c376  call    cs:__imp_RtlFreeHeap
0x14000c37c  xorps   xmm0, xmm0
0x14000c37f  xor     edi, edi
0x14000c381  movups  xmmword ptr [rbx+0B0h], xmm0
0x14000c388  movups  xmmword ptr [rbx+0C0h], xmm0
0x14000c38f  movups  xmmword ptr [rbx+0D0h], xmm0
0x14000c396  mov     rax, gs:60h
0x14000c39f  mov     rcx, [rax+30h]
0x14000c3a3  mov     [rbx+0B0h], rcx
0x14000c3aa  mov     qword ptr [rbx+0D0h], 4
0x14000c3b5  mov     qword ptr [rbx+0B8h], 30h ; '0'
0x14000c3c0  mov     [r14], rbx
0x14000c3c3  jmp     short loc_14000C3CD
0x14000c3c5  mov     rcx, rbx; P
0x14000c3c8  call    AslTelemetryDelete
0x14000c3cd  mov     rbx, [rsp+38h+arg_0]
0x14000c3d2  mov     eax, edi
0x14000c3d4  mov     rbp, [rsp+38h+arg_8]
0x14000c3d9  add     rsp, 20h
0x14000c3dd  pop     r14
0x14000c3df  pop     rdi
0x14000c3e0  pop     rsi
0x14000c3e1  retn
```
