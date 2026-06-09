# SP<_tag_TOKEN_SCARD_READERSTATE,SP_CPP_ARRAY<_tag_TOKEN_SCARD_READERSTATE>>::~SP<_tag_TOKEN_SCARD_READERSTATE,SP_CPP_ARRAY<_tag_TOKEN_SCARD_READERSTATE>>(void)

- ea: `0x180036ed8`
- end: `0x180036f45`
- name: `??1?$SP@U_tag_TOKEN_SCARD_READERSTATE@@V?$SP_CPP_ARRAY@U_tag_TOKEN_SCARD_READERSTATE@@@@@@QEAA@XZ`
- size: `109`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180037c68`
- `0x180038090`

## callees

- `0x180036ed8`
- `0x1800370c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036f13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036f13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036f27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036f27`

## pseudocode

```c
void __fastcall SP<_tag_TOKEN_SCARD_READERSTATE,SP_CPP_ARRAY<_tag_TOKEN_SCARD_READERSTATE>>::~SP<_tag_TOKEN_SCARD_READERSTATE,SP_CPP_ARRAY<_tag_TOKEN_SCARD_READERSTATE>>(
        __int64 *a1)
{
  __int64 v1; // rdx
  void *v3; // r14
  __int64 v4; // rbx
  _tag_TOKEN_SCARD_READERSTATE *i; // rdi
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  if ( *a1 )
  {
    v3 = (void *)(v1 - 8);
    v4 = *(_QWORD *)(v1 - 8);
    for ( i = (_tag_TOKEN_SCARD_READERSTATE *)(v1 + 72 * v4); v4; --v4 )
    {
      i = (_tag_TOKEN_SCARD_READERSTATE *)((char *)i - 72);
      _tag_TOKEN_SCARD_READERSTATE::~_tag_TOKEN_SCARD_READERSTATE(i);
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180036ed8  push    rbx
0x180036eda  push    rsi
0x180036edb  push    rdi
0x180036edc  push    r14
0x180036ede  sub     rsp, 28h
0x180036ee2  mov     rdx, [rcx]
0x180036ee5  mov     rsi, rcx
0x180036ee8  test    rdx, rdx
0x180036eeb  jz      short loc_180036F3A
0x180036eed  lea     r14, [rdx-8]
0x180036ef1  mov     rbx, [r14]
0x180036ef4  lea     rax, [rbx+rbx*8]
0x180036ef8  lea     rdi, [rdx+rax*8]
0x180036efc  test    rbx, rbx
0x180036eff  jz      short loc_180036F13
0x180036f01  sub     rdi, 48h ; 'H'
0x180036f05  mov     rcx, rdi; this
0x180036f08  call    ??1_tag_TOKEN_SCARD_READERSTATE@@QEAA@XZ; _tag_TOKEN_SCARD_READERSTATE::~_tag_TOKEN_SCARD_READERSTATE(void)
0x180036f0d  sub     rbx, 1
0x180036f11  jnz     short loc_180036F01
0x180036f13  call    cs:__imp_GetProcessHeap
0x180036f1a  nop     dword ptr [rax+rax+00h]
0x180036f1f  mov     r8, r14; lpMem
0x180036f22  xor     edx, edx; dwFlags
0x180036f24  mov     rcx, rax; hHeap
0x180036f27  call    cs:__imp_HeapFree
0x180036f2e  nop     dword ptr [rax+rax+00h]
0x180036f33  mov     qword ptr [rsi], 0
0x180036f3a  add     rsp, 28h
0x180036f3e  pop     r14
0x180036f40  pop     rdi
0x180036f41  pop     rsi
0x180036f42  pop     rbx
0x180036f43  retn
```
