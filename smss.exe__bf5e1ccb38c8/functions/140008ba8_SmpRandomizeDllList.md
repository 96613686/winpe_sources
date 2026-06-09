# SmpRandomizeDllList

- ea: `0x140008ba8`
- end: `0x140008cc7`
- name: `SmpRandomizeDllList`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140008470`

## callees

- `0x140008ba8`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x140008c13`
- `ntdll!NtQueryInformationProcess` at `0x140008c13`
- `ntdll!RtlAllocateHeap` at `0x140008c55`
- `ntdll!RtlAllocateHeap` at `0x140008c55`
- `ntdll!RtlRandomEx` at `0x140008c79`
- `ntdll!RtlRandomEx` at `0x140008c79`
- `ntdll!qsort_s` at `0x140008cae`
- `ntdll!qsort_s` at `0x140008cae`

## pseudocode

```c
NTSTATUS __fastcall SmpRandomizeDllList(_QWORD **a1, _QWORD *a2, unsigned int *a3)
{
  unsigned __int64 v6; // rax
  NTSTATUS result; // eax
  unsigned int v8; // eax
  _QWORD *v9; // rcx
  rsize_t v10; // r12
  PVOID Heap; // rax
  void *v12; // rbp
  _QWORD *v13; // rsi
  _QWORD *v14; // r14

  if ( *a1 == a1 )
  {
    *a2 = 0;
    *a3 = 0;
  }
  else
  {
    if ( !Seed )
    {
      v6 = __rdtsc();
      if ( (_DWORD)v6 )
      {
        Seed = v6;
      }
      else
      {
        result = NtQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessCookie, &Seed, 4u, 0);
        if ( result < 0 )
          return result;
      }
    }
    v8 = *a3;
    if ( !*a3 )
    {
      v9 = *a1;
      while ( v9 != a1 )
      {
        v9 = (_QWORD *)*v9;
        ++v8;
      }
      *a3 = v8;
    }
    v10 = v8;
    Heap = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), SmBaseTag, 16LL * v8);
    v12 = Heap;
    if ( !Heap )
      return -1073741670;
    v13 = *a1;
    v14 = Heap;
    while ( v13 != a1 )
    {
      *(_DWORD *)v14 = RtlRandomEx(&Seed);
      v14[1] = v13;
      v14 += 2;
      v13 = (_QWORD *)*v13;
    }
    qsort_s(v12, v10, 0x10u, SmpSortDllList, 0);
    *a2 = v12;
  }
  return 0;
}

```

## disassembly

```asm
0x140008ba8  push    rbp
0x140008baa  push    rsi
0x140008bab  push    rdi
0x140008bac  push    r12
0x140008bae  push    r14
0x140008bb0  push    r15
0x140008bb2  sub     rsp, 38h
0x140008bb6  mov     rsi, r8
0x140008bb9  mov     r15, rdx
0x140008bbc  mov     rdi, rcx
0x140008bbf  cmp     [rcx], rcx
0x140008bc2  jnz     short loc_140008BD7
0x140008bc4  mov     qword ptr [rdx], 0
0x140008bcb  mov     dword ptr [r8], 0
0x140008bd2  jmp     loc_140008CB7
0x140008bd7  cmp     cs:Seed, 0
0x140008bde  jnz     short loc_140008C21
0x140008be0  rdtsc
0x140008be2  shl     rdx, 20h
0x140008be6  or      rax, rdx
0x140008be9  test    eax, eax
0x140008beb  jz      short loc_140008BF5
0x140008bed  mov     cs:Seed, eax
0x140008bf3  jmp     short loc_140008C21
0x140008bf5  mov     r9d, 4; ProcessInformationLength
0x140008bfb  mov     [rsp+68h+ReturnLength], 0; ReturnLength
0x140008c04  lea     r8, Seed; ProcessInformation
0x140008c0b  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140008c0f  lea     edx, [r9+20h]; ProcessInformationClass
0x140008c13  call    cs:__imp_NtQueryInformationProcess
0x140008c19  test    eax, eax
0x140008c1b  js      loc_140008CB9
0x140008c21  mov     eax, [rsi]
0x140008c23  test    eax, eax
0x140008c25  jnz     short loc_140008C38
0x140008c27  mov     rcx, [rdi]
0x140008c2a  jmp     short loc_140008C31
0x140008c2c  mov     rcx, [rcx]
0x140008c2f  inc     eax
0x140008c31  cmp     rcx, rdi
0x140008c34  jnz     short loc_140008C2C
0x140008c36  mov     [rsi], eax
0x140008c38  mov     rcx, gs:60h
0x140008c41  mov     edx, cs:SmBaseTag; Flags
0x140008c47  mov     r8d, eax
0x140008c4a  shl     r8, 4; Size
0x140008c4e  mov     rcx, [rcx+30h]; HeapHandle
0x140008c52  mov     r12d, eax
0x140008c55  call    cs:__imp_RtlAllocateHeap
0x140008c5b  mov     rbp, rax
0x140008c5e  test    rax, rax
0x140008c61  jnz     short loc_140008C6A
0x140008c63  mov     eax, 0C000009Ah
0x140008c68  jmp     short loc_140008CB9
0x140008c6a  mov     rsi, [rdi]
0x140008c6d  mov     r14, rbp
0x140008c70  jmp     short loc_140008C8D
0x140008c72  lea     rcx, Seed; Seed
0x140008c79  call    cs:__imp_RtlRandomEx
0x140008c7f  mov     [r14], eax
0x140008c82  mov     [r14+8], rsi
0x140008c86  lea     r14, [r14+10h]
0x140008c8a  mov     rsi, [rsi]
0x140008c8d  cmp     rsi, rdi
0x140008c90  jnz     short loc_140008C72
0x140008c92  lea     r9, SmpSortDllList; PtFuncCompare
0x140008c99  mov     [rsp+68h+ReturnLength], 0; Context
0x140008ca2  mov     r8d, 10h; SizeOfElements
0x140008ca8  mov     rdx, r12; NumOfElements
0x140008cab  mov     rcx, rbp; Base
0x140008cae  call    cs:__imp_qsort_s
0x140008cb4  mov     [r15], rbp
0x140008cb7  xor     eax, eax
0x140008cb9  add     rsp, 38h
0x140008cbd  pop     r15
0x140008cbf  pop     r14
0x140008cc1  pop     r12
0x140008cc3  pop     rdi
0x140008cc4  pop     rsi
0x140008cc5  pop     rbp
0x140008cc6  retn
```
