# SclCloneString

- ea: `0x18000a75c`
- end: `0x18000a7ea`
- name: `SclCloneString`
- size: `142`
- prototype: `__int64 __fastcall(_WORD *, __int64, _QWORD *, _QWORD *)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000548c`
- `0x180007944`
- `0x180007ac4`
- `0x18000911c`
- `0x180009cd0`
- `0x18000acec`
- `0x18000d124`
- `0x18000deec`

## callees

- `0x18000a6ec`
- `0x18000a75c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000a78a`
- `ntdll!RtlAllocateHeap` at `0x18000a78a`
- `ntdll!RtlFreeHeap` at `0x18000a7d7`
- `ntdll!RtlFreeHeap` at `0x18000a7d7`

## pseudocode

```c
__int64 __fastcall SclCloneString(_WORD *a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  unsigned __int64 v5; // rbx
  SIZE_T v6; // rsi
  _WORD *Heap; // rax
  int v10; // ebx
  void *v11; // r11

  v5 = 2 * a2;
  v6 = 2 * a2 + 2;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( Heap )
  {
    v10 = RtlStringCbCopyNW(Heap, v6, a1, v5);
    if ( v10 < 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    }
    else
    {
      *a3 = v11;
      if ( a4 )
        *a4 = (unsigned int)v6;
    }
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a75c  push    rbx
0x18000a75e  push    rbp
0x18000a75f  push    rsi
0x18000a760  push    rdi
0x18000a761  push    r14
0x18000a763  sub     rsp, 20h
0x18000a767  mov     rbp, rcx
0x18000a76a  lea     rbx, [rdx+rdx]
0x18000a76e  mov     rcx, gs:60h
0x18000a777  lea     rsi, [rbx+2]
0x18000a77b  mov     r14, r8
0x18000a77e  xor     edx, edx; Flags
0x18000a780  mov     r8, rsi; Size
0x18000a783  mov     rdi, r9
0x18000a786  mov     rcx, [rcx+30h]; HeapHandle
0x18000a78a  call    cs:__imp_RtlAllocateHeap
0x18000a790  mov     r11, rax
0x18000a793  test    rax, rax
0x18000a796  jnz     short loc_18000A79F
0x18000a798  mov     ebx, 0C0000017h
0x18000a79d  jmp     short loc_18000A7DD
0x18000a79f  mov     r9, rbx
0x18000a7a2  mov     r8, rbp
0x18000a7a5  mov     rdx, rsi
0x18000a7a8  mov     rcx, r11
0x18000a7ab  call    RtlStringCbCopyNW
0x18000a7b0  mov     ebx, eax
0x18000a7b2  test    eax, eax
0x18000a7b4  js      short loc_18000A7C5
0x18000a7b6  mov     [r14], r11
0x18000a7b9  test    rdi, rdi
0x18000a7bc  jz      short loc_18000A7DD
0x18000a7be  mov     ecx, esi
0x18000a7c0  mov     [rdi], rcx
0x18000a7c3  jmp     short loc_18000A7DD
0x18000a7c5  mov     rcx, gs:60h
0x18000a7ce  mov     r8, r11; P
0x18000a7d1  xor     edx, edx; Flags
0x18000a7d3  mov     rcx, [rcx+30h]; HeapHandle
0x18000a7d7  call    cs:__imp_RtlFreeHeap
0x18000a7dd  mov     eax, ebx
0x18000a7df  add     rsp, 20h
0x18000a7e3  pop     r14
0x18000a7e5  pop     rdi
0x18000a7e6  pop     rsi
0x18000a7e7  pop     rbp
0x18000a7e8  pop     rbx
0x18000a7e9  retn
```
