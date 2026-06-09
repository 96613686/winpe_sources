# CTaskNameHolder::CTaskNameHolder(char const *)

- ea: `0x180019c80`
- end: `0x180019d68`
- name: `??0CTaskNameHolder@@QEAA@PEBD@Z`
- size: `232`
- prototype: `CTaskNameHolder *(CTaskNameHolder *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001bb80`
- `0x18001bc90`

## callees

- `0x180005e18`
- `0x180019c80`
- `0x18001ac00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019cd8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019d27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019cd8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019d27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019cc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019cc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019d13`

## pseudocode

```c
CTaskNameHolder *__fastcall CTaskNameHolder::CTaskNameHolder(CTaskNameHolder *this, char *a2)
{
  __int64 v4; // rax
  SIZE_T v5; // rbp
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v7; // rax
  HANDLE v8; // rax
  char *v9; // rax

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    v5 = (unsigned int)(v4 + 1);
    ProcessHeap = GetProcessHeap();
    v7 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2 * v5);
    *(_QWORD *)this = v7;
    if ( v7 && (int)StringCchPrintfW(v7, (unsigned int)v5, L"%S", a2) < 0 )
      *(_WORD *)(*(_QWORD *)this + 2LL * (unsigned int)(v5 - 1)) = 0;
    v8 = GetProcessHeap();
    v9 = (char *)HeapAlloc(v8, 0, v5);
    *((_QWORD *)this + 1) = v9;
    if ( v9 && (int)StringCchCopyA(v9, v5, a2) < 0 )
      *(_BYTE *)((unsigned int)(v5 - 1) + *((_QWORD *)this + 1)) = 0;
  }
  return this;
}

```

## disassembly

```asm
0x180019c80  push    rbx
0x180019c82  push    rbp
0x180019c83  push    rsi
0x180019c84  push    rdi
0x180019c85  push    r14
0x180019c87  sub     rsp, 20h
0x180019c8b  mov     qword ptr [rcx], 0
0x180019c92  mov     rsi, rdx
0x180019c95  mov     qword ptr [rcx+8], 0
0x180019c9d  mov     rdi, rcx
0x180019ca0  test    rdx, rdx
0x180019ca3  jz      loc_180019D59
0x180019ca9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019cad  inc     rax
0x180019cb0  cmp     byte ptr [rdx+rax], 0
0x180019cb4  jnz     short loc_180019CAD
0x180019cb6  lea     ebp, [rax+1]
0x180019cb9  mov     r14d, ebp
0x180019cbc  lea     rbx, ds:0[rbp*2]
0x180019cc4  call    cs:__imp_GetProcessHeap
0x180019ccb  nop     dword ptr [rax+rax+00h]
0x180019cd0  mov     r8, rbx; dwBytes
0x180019cd3  xor     edx, edx; dwFlags
0x180019cd5  mov     rcx, rax; hHeap
0x180019cd8  call    cs:__imp_HeapAlloc
0x180019cdf  nop     dword ptr [rax+rax+00h]
0x180019ce4  mov     [rdi], rax
0x180019ce7  test    rax, rax
0x180019cea  jz      short loc_180019D13
0x180019cec  mov     r9, rsi
0x180019cef  lea     r8, aS_5; "%S"
0x180019cf6  mov     edx, r14d; unsigned __int64
0x180019cf9  mov     rcx, rax; unsigned __int16 *
0x180019cfc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019d01  test    eax, eax
0x180019d03  jns     short loc_180019D13
0x180019d05  mov     rcx, [rdi]
0x180019d08  lea     r8d, [rbp-1]
0x180019d0c  xor     eax, eax
0x180019d0e  mov     [rcx+r8*2], ax
0x180019d13  call    cs:__imp_GetProcessHeap
0x180019d1a  nop     dword ptr [rax+rax+00h]
0x180019d1f  mov     r8, r14; dwBytes
0x180019d22  xor     edx, edx; dwFlags
0x180019d24  mov     rcx, rax; hHeap
0x180019d27  call    cs:__imp_HeapAlloc
0x180019d2e  nop     dword ptr [rax+rax+00h]
0x180019d33  mov     [rdi+8], rax
0x180019d37  test    rax, rax
0x180019d3a  jz      short loc_180019D59
0x180019d3c  mov     r8, rsi; char *
0x180019d3f  mov     rdx, r14; unsigned __int64
0x180019d42  mov     rcx, rax; char *
0x180019d45  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180019d4a  test    eax, eax
0x180019d4c  jns     short loc_180019D59
0x180019d4e  mov     rax, [rdi+8]
0x180019d52  lea     ecx, [rbp-1]
0x180019d55  mov     byte ptr [rcx+rax], 0
0x180019d59  mov     rax, rdi
0x180019d5c  add     rsp, 20h
0x180019d60  pop     r14
0x180019d62  pop     rdi
0x180019d63  pop     rsi
0x180019d64  pop     rbp
0x180019d65  pop     rbx
0x180019d66  retn
```
