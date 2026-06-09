# SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>::~SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>(void)

- ea: `0x180037050`
- end: `0x1800370b9`
- name: `??1?$SP@VDH_HANDLE@@V?$SP_CPP_ARRAY@VDH_HANDLE@@@@@@QEAA@XZ`
- size: `105`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180036fc4`
- `0x180037288`
- `0x18003a240`

## callees

- `0x180003398`
- `0x180037050`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037087`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037087`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003709b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003709b`

## pseudocode

```c
int __fastcall SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>::~SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>(__int64 *a1)
{
  __int64 v1; // rax
  void *v3; // r14
  __int64 v4; // rbx
  void **i; // rdi
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  if ( *a1 )
  {
    v3 = (void *)(v1 - 8);
    v4 = *(_QWORD *)(v1 - 8);
    for ( i = (void **)(v1 + 8 * v4); v4; --v4 )
      DH_HANDLE::~DH_HANDLE(--i);
    ProcessHeap = GetProcessHeap();
    LODWORD(v1) = HeapFree(ProcessHeap, 0, v3);
    *a1 = 0;
  }
  return v1;
}

```

## disassembly

```asm
0x180037050  push    rbx
0x180037052  push    rsi
0x180037053  push    rdi
0x180037054  push    r14
0x180037056  sub     rsp, 28h
0x18003705a  mov     rax, [rcx]
0x18003705d  mov     rsi, rcx
0x180037060  test    rax, rax
0x180037063  jz      short loc_1800370AE
0x180037065  lea     r14, [rax-8]
0x180037069  mov     rbx, [r14]
0x18003706c  lea     rdi, [rax+rbx*8]
0x180037070  test    rbx, rbx
0x180037073  jz      short loc_180037087
0x180037075  sub     rdi, 8
0x180037079  mov     rcx, rdi; this
0x18003707c  call    ??1DH_HANDLE@@QEAA@XZ; DH_HANDLE::~DH_HANDLE(void)
0x180037081  sub     rbx, 1
0x180037085  jnz     short loc_180037075
0x180037087  call    cs:__imp_GetProcessHeap
0x18003708e  nop     dword ptr [rax+rax+00h]
0x180037093  mov     r8, r14; lpMem
0x180037096  xor     edx, edx; dwFlags
0x180037098  mov     rcx, rax; hHeap
0x18003709b  call    cs:__imp_HeapFree
0x1800370a2  nop     dword ptr [rax+rax+00h]
0x1800370a7  mov     qword ptr [rsi], 0
0x1800370ae  add     rsp, 28h
0x1800370b2  pop     r14
0x1800370b4  pop     rdi
0x1800370b5  pop     rsi
0x1800370b6  pop     rbx
0x1800370b7  retn
```
