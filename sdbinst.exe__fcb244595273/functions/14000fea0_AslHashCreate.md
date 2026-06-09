# AslHashCreate

- ea: `0x14000fea0`
- end: `0x14000ffd8`
- name: `AslHashCreate`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140015104`

## callees

- `0x14000fea0`
- `0x14000ffe0`
- `0x14001008c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14000fef3`
- `ntdll!RtlAllocateHeap` at `0x14000ff50`
- `ntdll!RtlAllocateHeap` at `0x14000fef3`
- `ntdll!RtlAllocateHeap` at `0x14000ff50`

## string_xrefs

- `0x14000fec5`: `AslHashCreateEx`
- `0x14000ff11`: `AslHashCreateEx`
- `0x14000ff80`: `AslHashCreateEx`
- `0x14000ffa4`: `AslHashCreateEx failed for Size = 8147 [%x]`
- `0x14000ffb5`: `AslHashCreate`

## pseudocode

```c
__int64 __fastcall AslHashCreate(_QWORD *a1)
{
  int v2; // ebx
  _DWORD *Heap; // rax
  _QWORD *v4; // rsi
  __int64 v5; // r8
  PVOID v6; // rax

  if ( !a1 )
  {
    AslLogCallPrintf(1, "AslHashCreateEx", 73, "Invalid parameter");
    v2 = -1073741811;
LABEL_12:
    AslLogCallPrintf(1, "AslHashCreate", 140, "AslHashCreateEx failed for Size = 8147 [%x]", v2);
    return (unsigned int)v2;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
  v4 = Heap;
  if ( !Heap )
  {
    v5 = 80;
LABEL_5:
    v2 = -1073741801;
    AslLogCallPrintf(1, "AslHashCreateEx", v5, "Out of memory");
    goto LABEL_11;
  }
  *Heap = 8147;
  if ( is_mul_ok(8u, 0x1FD3u) )
  {
    v6 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xFE98u);
    v4[1] = v6;
    if ( !v6 )
    {
      v5 = 95;
      goto LABEL_5;
    }
    *a1 = v4;
    v4 = 0;
    v2 = 0;
  }
  else
  {
    v2 = -1073741675;
    AslLogCallPrintf(1, "AslHashCreateEx", 88, "RtlSIZETMult failed for Size = %d [%x]", 8147, -1073741675);
  }
LABEL_11:
  AslHashFree(v4);
  if ( v2 < 0 )
    goto LABEL_12;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000fea0  mov     [rsp+arg_8], rbx
0x14000fea5  mov     [rsp+arg_10], rbp
0x14000feaa  push    rsi
0x14000feab  sub     rsp, 30h
0x14000feaf  mov     rbx, rcx
0x14000feb2  test    rcx, rcx
0x14000feb5  jnz     short loc_14000FEDB
0x14000feb7  lea     r8d, [rcx+49h]
0x14000febb  lea     ecx, [rbx+1]
0x14000febe  lea     r9, aInvalidParamet_0; "Invalid parameter"
0x14000fec5  lea     rdx, aAslhashcreatee; "AslHashCreateEx"
0x14000fecc  call    AslLogCallPrintf
0x14000fed1  mov     ebx, 0C000000Dh
0x14000fed6  jmp     loc_14000FFA4
0x14000fedb  mov     rcx, gs:60h
0x14000fee4  mov     ebp, 8
0x14000fee9  mov     edx, ebp; Flags
0x14000feeb  mov     rcx, [rcx+30h]; HeapHandle
0x14000feef  lea     r8d, [rbp+8]; Size
0x14000fef3  call    cs:__imp_RtlAllocateHeap
0x14000fef9  mov     rsi, rax
0x14000fefc  test    rax, rax
0x14000feff  jnz     short loc_14000FF24
0x14000ff01  lea     r8d, [rbp+48h]
0x14000ff05  lea     r9, aOutOfMemory; "Out of memory"
0x14000ff0c  mov     ecx, 1
0x14000ff11  lea     rdx, aAslhashcreatee; "AslHashCreateEx"
0x14000ff18  mov     ebx, 0C0000017h
0x14000ff1d  call    AslLogCallPrintf
0x14000ff22  jmp     short loc_14000FF98
0x14000ff24  mov     ecx, 1FD3h
0x14000ff29  mov     [rsp+38h+arg_0], 0
0x14000ff32  mov     [rax], ecx
0x14000ff34  mov     eax, ecx
0x14000ff36  mul     rbp
0x14000ff39  test    rdx, rdx
0x14000ff3c  jnz     short loc_14000FF6E
0x14000ff3e  mov     rcx, gs:60h
0x14000ff47  mov     r8, rax; Size
0x14000ff4a  mov     edx, ebp; Flags
0x14000ff4c  mov     rcx, [rcx+30h]; HeapHandle
0x14000ff50  call    cs:__imp_RtlAllocateHeap
0x14000ff56  mov     [rsi+8], rax
0x14000ff5a  test    rax, rax
0x14000ff5d  jnz     short loc_14000FF65
0x14000ff5f  lea     r8d, [rax+5Fh]
0x14000ff63  jmp     short loc_14000FF05
0x14000ff65  mov     [rbx], rsi
0x14000ff68  xor     esi, esi
0x14000ff6a  xor     ebx, ebx
0x14000ff6c  jmp     short loc_14000FF98
0x14000ff6e  mov     r8d, 58h ; 'X'
0x14000ff74  lea     r9, aRtlsizetmultFa; "RtlSIZETMult failed for Size = %d [%x]"
0x14000ff7b  mov     ebx, 0C0000095h
0x14000ff80  lea     rdx, aAslhashcreatee; "AslHashCreateEx"
0x14000ff87  mov     [rsp+38h+var_10], ebx
0x14000ff8b  mov     [rsp+38h+var_18], ecx
0x14000ff8f  lea     ecx, [r8-57h]
0x14000ff93  call    AslLogCallPrintf
0x14000ff98  mov     rcx, rsi; P
0x14000ff9b  call    AslHashFree
0x14000ffa0  test    ebx, ebx
0x14000ffa2  jns     short loc_14000FFC6
0x14000ffa4  lea     r9, aAslhashcreatee_0; "AslHashCreateEx failed for Size = 8147 "...
0x14000ffab  mov     [rsp+38h+var_18], ebx
0x14000ffaf  mov     r8d, 8Ch
0x14000ffb5  lea     rdx, aAslhashcreate; "AslHashCreate"
0x14000ffbc  mov     ecx, 1
0x14000ffc1  call    AslLogCallPrintf
0x14000ffc6  mov     rbp, [rsp+38h+arg_10]
0x14000ffcb  mov     eax, ebx
0x14000ffcd  mov     rbx, [rsp+38h+arg_8]
0x14000ffd2  add     rsp, 30h
0x14000ffd6  pop     rsi
0x14000ffd7  retn
```
