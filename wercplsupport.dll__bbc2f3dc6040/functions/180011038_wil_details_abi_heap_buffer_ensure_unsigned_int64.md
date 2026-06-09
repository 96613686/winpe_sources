# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180011038`
- end: `0x18001110b`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c760`
- `0x18000cd54`
- `0x18000df18`

## callees

- `0x18000c354`
- `0x180011038`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800110ba`
- `msvcrt!memcpy_s` at `0x1800110ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011079`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001109d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800110f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001109d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800110f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800110db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800110db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800110cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800110cd`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  char *v7; // rax
  char *v8; // rbx
  rsize_t v10; // r15
  void *v11; // rbp
  HANDLE ProcessHeap; // rax

  v3 = a2;
  v4 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( a2 + *((_QWORD *)this + 1) - *(_QWORD *)this >= v4 )
  {
    if ( a2 < 2 * v4 )
      v3 = 2 * v4;
    if ( v4 < v3 )
    {
      LastError = GetLastError();
      v6 = (v3 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
      v7 = (char *)wil::details::ProcessHeapAlloc(0, v6);
      v8 = v7;
      if ( !v7 )
      {
        SetLastError(LastError);
        return 0;
      }
      v10 = *((_QWORD *)this + 1) - *(_QWORD *)this;
      memcpy_s(v7, v6, *(const void *const *)this, v10);
      v11 = (void *)*((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = v8;
      if ( v11 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v11);
      }
      *(_QWORD *)this = v8;
      *((_QWORD *)this + 1) = &v8[v10];
      *((_QWORD *)this + 2) = &v8[v6];
      SetLastError(LastError);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180011038  push    rbx
0x18001103a  push    rbp
0x18001103b  push    rsi
0x18001103c  push    rdi
0x18001103d  push    r14
0x18001103f  push    r15
0x180011041  sub     rsp, 28h
0x180011045  mov     rdi, rcx
0x180011048  mov     rbx, rdx
0x18001104b  mov     rcx, [rcx+10h]
0x18001104f  mov     rax, [rdi+8]
0x180011053  sub     rax, [rdi]
0x180011056  sub     rcx, [rdi]
0x180011059  add     rax, rdx
0x18001105c  cmp     rax, rcx
0x18001105f  jb      loc_1800110FC
0x180011065  lea     rax, [rcx+rcx]
0x180011069  cmp     rdx, rax
0x18001106c  cmovb   rbx, rax
0x180011070  cmp     rcx, rbx
0x180011073  jnb     loc_1800110FC
0x180011079  call    cs:__imp_GetLastError
0x18001107f  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180011083  xor     ecx, ecx; dwFlags
0x180011085  mov     esi, eax
0x180011087  lea     r14, [rbx+40h]
0x18001108b  mov     rdx, r14; dwBytes
0x18001108e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180011093  mov     rbx, rax
0x180011096  test    rax, rax
0x180011099  jnz     short loc_1800110A7
0x18001109b  mov     ecx, esi; dwErrCode
0x18001109d  call    cs:__imp_SetLastError
0x1800110a3  xor     al, al
0x1800110a5  jmp     short loc_1800110FE
0x1800110a7  mov     r15, [rdi+8]
0x1800110ab  mov     rdx, r14; DestinationSize
0x1800110ae  sub     r15, [rdi]
0x1800110b1  mov     rcx, rbx; Destination
0x1800110b4  mov     r8, [rdi]; Source
0x1800110b7  mov     r9, r15; SourceSize
0x1800110ba  call    cs:__imp_memcpy_s
0x1800110c0  mov     rbp, [rdi+18h]
0x1800110c4  mov     [rdi+18h], rbx
0x1800110c8  test    rbp, rbp
0x1800110cb  jz      short loc_1800110E1
0x1800110cd  call    cs:__imp_GetProcessHeap
0x1800110d3  mov     r8, rbp; lpMem
0x1800110d6  xor     edx, edx; dwFlags
0x1800110d8  mov     rcx, rax; hHeap
0x1800110db  call    cs:__imp_HeapFree
0x1800110e1  lea     rax, [r15+rbx]
0x1800110e5  mov     [rdi], rbx
0x1800110e8  mov     [rdi+8], rax
0x1800110ec  mov     ecx, esi; dwErrCode
0x1800110ee  lea     rax, [r14+rbx]
0x1800110f2  mov     [rdi+10h], rax
0x1800110f6  call    cs:__imp_SetLastError
0x1800110fc  mov     al, 1
0x1800110fe  add     rsp, 28h
0x180011102  pop     r15
0x180011104  pop     r14
0x180011106  pop     rdi
0x180011107  pop     rsi
0x180011108  pop     rbp
0x180011109  pop     rbx
0x18001110a  retn
```
