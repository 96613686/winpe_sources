# HashTable<bool>::Cleanup(void)

- ea: `0x180070110`
- end: `0x18007019c`
- name: `?Cleanup@?$HashTable@_N@@QEAAXXZ`
- size: `140`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18006fec8`
- `0x18006ffd4`
- `0x1800923ec`

## callees

- `0x180070110`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x18007018b`
- `ntdll!RtlDeleteHashTable` at `0x18007018b`
- `ntdll!RtlInitEnumerationHashTable` at `0x18007013e`
- `ntdll!RtlInitEnumerationHashTable` at `0x18007013e`
- `ntdll!RtlRemoveEntryHashTable` at `0x18007014c`
- `ntdll!RtlRemoveEntryHashTable` at `0x18007014c`
- `ntdll!RtlEndEnumerationHashTable` at `0x180070182`
- `ntdll!RtlEndEnumerationHashTable` at `0x180070182`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18007016c`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18007016c`
- `ntdll!RtlFreeHeap` at `0x18007015e`
- `ntdll!RtlFreeHeap` at `0x18007015e`

## pseudocode

```c
void __fastcall HashTable<bool>::Cleanup(_QWORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rcx
  void *v5; // rdi
  _OWORD v6[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v7; // [rsp+40h] [rbp-18h]

  v2 = *a1;
  if ( v2 )
  {
    memset(v6, 0, sizeof(v6));
    v7 = 0;
    RtlInitEnumerationHashTable(v2, v6);
    while ( 1 )
    {
      v3 = RtlEnumerateEntryHashTable(*a1, v6);
      v4 = *a1;
      v5 = (void *)v3;
      if ( !v3 )
        break;
      RtlRemoveEntryHashTable(v4, v3, 0);
      RtlFreeHeap(pUserHeap, 0, v5);
    }
    RtlEndEnumerationHashTable(v4, v6);
    RtlDeleteHashTable(*a1);
  }
}

```

## disassembly

```asm
0x180070110  mov     [rsp+arg_0], rbx
0x180070115  push    rdi
0x180070116  sub     rsp, 50h
0x18007011a  mov     rbx, rcx
0x18007011d  mov     rcx, [rcx]
0x180070120  test    rcx, rcx
0x180070123  jz      short loc_180070191
0x180070125  xorps   xmm0, xmm0
0x180070128  lea     rdx, [rsp+58h+var_38]
0x18007012d  xor     eax, eax
0x18007012f  movups  [rsp+58h+var_38], xmm0
0x180070134  mov     [rsp+58h+var_18], rax
0x180070139  movups  [rsp+58h+var_28], xmm0
0x18007013e  call    cs:__imp_RtlInitEnumerationHashTable
0x180070144  jmp     short loc_180070164
0x180070146  xor     r8d, r8d
0x180070149  mov     rdx, rdi
0x18007014c  call    cs:__imp_RtlRemoveEntryHashTable
0x180070152  mov     rcx, cs:pUserHeap; HeapHandle
0x180070159  mov     r8, rdi; P
0x18007015c  xor     edx, edx; Flags
0x18007015e  call    cs:__imp_RtlFreeHeap
0x180070164  mov     rcx, [rbx]
0x180070167  lea     rdx, [rsp+58h+var_38]
0x18007016c  call    cs:__imp_RtlEnumerateEntryHashTable
0x180070172  mov     rcx, [rbx]
0x180070175  mov     rdi, rax
0x180070178  test    rax, rax
0x18007017b  jnz     short loc_180070146
0x18007017d  lea     rdx, [rsp+58h+var_38]
0x180070182  call    cs:__imp_RtlEndEnumerationHashTable
0x180070188  mov     rcx, [rbx]
0x18007018b  call    cs:__imp_RtlDeleteHashTable
0x180070191  mov     rbx, [rsp+58h+arg_0]
0x180070196  add     rsp, 50h
0x18007019a  pop     rdi
0x18007019b  retn
```
