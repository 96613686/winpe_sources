# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000c82c`
- end: `0x18000c8fe`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180007e68`
- `0x18000800c`
- `0x1800088a8`
- `0x18000b3d8`
- `0x18000b5e0`

## callees

- `0x180007d28`
- `0x18000c82c`
- `0x18000d1bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c8c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c8c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c8ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c8ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c891`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c891`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c86d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c86d`

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
0x18000c82c  push    rbx
0x18000c82e  push    rbp
0x18000c82f  push    rsi
0x18000c830  push    rdi
0x18000c831  push    r14
0x18000c833  push    r15
0x18000c835  sub     rsp, 28h
0x18000c839  mov     rdi, rcx
0x18000c83c  mov     rbx, rdx
0x18000c83f  mov     rcx, [rcx+10h]
0x18000c843  mov     rax, [rdi+8]
0x18000c847  sub     rax, [rdi]
0x18000c84a  sub     rcx, [rdi]
0x18000c84d  add     rax, rdx
0x18000c850  cmp     rax, rcx
0x18000c853  jb      loc_18000C8EF
0x18000c859  lea     rax, [rcx+rcx]
0x18000c85d  cmp     rdx, rax
0x18000c860  cmovb   rbx, rax
0x18000c864  cmp     rcx, rbx
0x18000c867  jnb     loc_18000C8EF
0x18000c86d  call    cs:__imp_GetLastError
0x18000c873  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000c877  xor     ecx, ecx; dwFlags
0x18000c879  mov     esi, eax
0x18000c87b  lea     r14, [rbx+40h]
0x18000c87f  mov     rdx, r14; dwBytes
0x18000c882  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c887  mov     rbx, rax
0x18000c88a  test    rax, rax
0x18000c88d  jnz     short loc_18000C89B
0x18000c88f  mov     ecx, esi; dwErrCode
0x18000c891  call    cs:__imp_SetLastError
0x18000c897  xor     al, al
0x18000c899  jmp     short loc_18000C8F1
0x18000c89b  mov     r15, [rdi+8]
0x18000c89f  mov     rdx, r14; DestinationSize
0x18000c8a2  sub     r15, [rdi]
0x18000c8a5  mov     rcx, rbx; Destination
0x18000c8a8  mov     r8, [rdi]; Source
0x18000c8ab  mov     r9, r15; SourceSize
0x18000c8ae  call    memcpy_s
0x18000c8b3  mov     rbp, [rdi+18h]
0x18000c8b7  mov     [rdi+18h], rbx
0x18000c8bb  test    rbp, rbp
0x18000c8be  jz      short loc_18000C8D4
0x18000c8c0  call    cs:__imp_GetProcessHeap
0x18000c8c6  mov     r8, rbp; lpMem
0x18000c8c9  xor     edx, edx; dwFlags
0x18000c8cb  mov     rcx, rax; hHeap
0x18000c8ce  call    cs:__imp_HeapFree
0x18000c8d4  lea     rax, [r15+rbx]
0x18000c8d8  mov     [rdi], rbx
0x18000c8db  mov     [rdi+8], rax
0x18000c8df  mov     ecx, esi; dwErrCode
0x18000c8e1  lea     rax, [r14+rbx]
0x18000c8e5  mov     [rdi+10h], rax
0x18000c8e9  call    cs:__imp_SetLastError
0x18000c8ef  mov     al, 1
0x18000c8f1  add     rsp, 28h
0x18000c8f5  pop     r15
0x18000c8f7  pop     r14
0x18000c8f9  pop     rdi
0x18000c8fa  pop     rsi
0x18000c8fb  pop     rbp
0x18000c8fc  pop     rbx
0x18000c8fd  retn
```
