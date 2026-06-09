# PublisherManifestConfig::Free(void)

- ea: `0x180009a34`
- end: `0x180009aeb`
- name: `?Free@PublisherManifestConfig@@AEAAXXZ`
- size: `183`
- prototype: `void __fastcall(PublisherManifestConfig *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800087c8`
- `0x180008970`
- `0x180009620`
- `0x1800096ec`
- `0x180009710`
- `0x180018484`
- `0x180026ba8`

## callees

- `0x180009a34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009aba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009ad8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009aba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009ad8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aca`

## pseudocode

```c
void __fastcall PublisherManifestConfig::Free(PublisherManifestConfig *this)
{
  void *v1; // rdi
  void *v3; // rdi
  void *v4; // rdi
  void *v5; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v7; // rax
  HANDLE v8; // rax
  HANDLE v9; // rax

  v1 = (void *)*((_QWORD *)this + 1);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v3);
    *((_QWORD *)this + 2) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v4);
    *((_QWORD *)this + 3) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 4);
  if ( v5 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v5);
    *((_QWORD *)this + 4) = 0;
  }
}

```

## disassembly

```asm
0x180009a34  mov     [rsp+arg_0], rbx
0x180009a39  push    rdi
0x180009a3a  sub     rsp, 20h
0x180009a3e  mov     rdi, [rcx+8]
0x180009a42  mov     rbx, rcx
0x180009a45  test    rdi, rdi
0x180009a48  jnz     short loc_180009A70
0x180009a4a  mov     rdi, [rbx+10h]
0x180009a4e  test    rdi, rdi
0x180009a51  jnz     short loc_180009AAC
0x180009a53  mov     rdi, [rbx+18h]
0x180009a57  test    rdi, rdi
0x180009a5a  jnz     short loc_180009ACA
0x180009a5c  mov     rdi, [rbx+20h]
0x180009a60  test    rdi, rdi
0x180009a63  jnz     short loc_180009A8E
0x180009a65  mov     rbx, [rsp+28h+arg_0]
0x180009a6a  add     rsp, 20h
0x180009a6e  pop     rdi
0x180009a6f  retn
0x180009a70  call    cs:__imp_GetProcessHeap
0x180009a76  mov     r8, rdi; lpMem
0x180009a79  xor     edx, edx; dwFlags
0x180009a7b  mov     rcx, rax; hHeap
0x180009a7e  call    cs:__imp_HeapFree
0x180009a84  mov     qword ptr [rbx+8], 0
0x180009a8c  jmp     short loc_180009A4A
0x180009a8e  call    cs:__imp_GetProcessHeap
0x180009a94  mov     r8, rdi; lpMem
0x180009a97  xor     edx, edx; dwFlags
0x180009a99  mov     rcx, rax; hHeap
0x180009a9c  call    cs:__imp_HeapFree
0x180009aa2  mov     qword ptr [rbx+20h], 0
0x180009aaa  jmp     short loc_180009A65
0x180009aac  call    cs:__imp_GetProcessHeap
0x180009ab2  mov     r8, rdi; lpMem
0x180009ab5  xor     edx, edx; dwFlags
0x180009ab7  mov     rcx, rax; hHeap
0x180009aba  call    cs:__imp_HeapFree
0x180009ac0  mov     qword ptr [rbx+10h], 0
0x180009ac8  jmp     short loc_180009A53
0x180009aca  call    cs:__imp_GetProcessHeap
0x180009ad0  mov     r8, rdi; lpMem
0x180009ad3  xor     edx, edx; dwFlags
0x180009ad5  mov     rcx, rax; hHeap
0x180009ad8  call    cs:__imp_HeapFree
0x180009ade  mov     qword ptr [rbx+18h], 0
0x180009ae6  jmp     loc_180009A5C
```
