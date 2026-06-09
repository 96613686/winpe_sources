# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x14000ab0c`
- end: `0x14000abde`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400092c4`
- `0x140009860`
- `0x14000a508`

## callees

- `0x14000220c`
- `0x1400058a8`
- `0x14000ab0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000abae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000abae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000aba0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000aba0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ab4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ab4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ab71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000abc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ab71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000abc9`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // r8
  char *v8; // rax
  char *v9; // rbx
  rsize_t v11; // r15
  void *v12; // rbp
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
      v8 = (char *)wil::details::ProcessHeapAlloc(0, v6, v7);
      v9 = v8;
      if ( !v8 )
      {
        SetLastError(LastError);
        return 0;
      }
      v11 = *((_QWORD *)this + 1) - *(_QWORD *)this;
      memcpy_s(v8, v6, *(const void *const *)this, v11);
      v12 = (void *)*((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = v9;
      if ( v12 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v12);
      }
      *(_QWORD *)this = v9;
      *((_QWORD *)this + 1) = &v9[v11];
      *((_QWORD *)this + 2) = &v9[v6];
      SetLastError(LastError);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14000ab0c  push    rbx
0x14000ab0e  push    rbp
0x14000ab0f  push    rsi
0x14000ab10  push    rdi
0x14000ab11  push    r14
0x14000ab13  push    r15
0x14000ab15  sub     rsp, 28h
0x14000ab19  mov     rdi, rcx
0x14000ab1c  mov     rbx, rdx
0x14000ab1f  mov     rcx, [rcx+10h]
0x14000ab23  mov     rax, [rdi+8]
0x14000ab27  sub     rax, [rdi]
0x14000ab2a  sub     rcx, [rdi]
0x14000ab2d  add     rax, rdx
0x14000ab30  cmp     rax, rcx
0x14000ab33  jb      loc_14000ABCF
0x14000ab39  lea     rax, [rcx+rcx]
0x14000ab3d  cmp     rdx, rax
0x14000ab40  cmovb   rbx, rax
0x14000ab44  cmp     rcx, rbx
0x14000ab47  jnb     loc_14000ABCF
0x14000ab4d  call    cs:__imp_GetLastError
0x14000ab53  and     rbx, 0FFFFFFFFFFFFFFC0h
0x14000ab57  xor     ecx, ecx; dwFlags
0x14000ab59  mov     esi, eax
0x14000ab5b  lea     r14, [rbx+40h]
0x14000ab5f  mov     rdx, r14; dwBytes
0x14000ab62  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000ab67  mov     rbx, rax
0x14000ab6a  test    rax, rax
0x14000ab6d  jnz     short loc_14000AB7B
0x14000ab6f  mov     ecx, esi; dwErrCode
0x14000ab71  call    cs:__imp_SetLastError
0x14000ab77  xor     al, al
0x14000ab79  jmp     short loc_14000ABD1
0x14000ab7b  mov     r15, [rdi+8]
0x14000ab7f  mov     rdx, r14; DestinationSize
0x14000ab82  sub     r15, [rdi]
0x14000ab85  mov     rcx, rbx; Destination
0x14000ab88  mov     r8, [rdi]; Source
0x14000ab8b  mov     r9, r15; SourceSize
0x14000ab8e  call    memcpy_s
0x14000ab93  mov     rbp, [rdi+18h]
0x14000ab97  mov     [rdi+18h], rbx
0x14000ab9b  test    rbp, rbp
0x14000ab9e  jz      short loc_14000ABB4
0x14000aba0  call    cs:__imp_GetProcessHeap
0x14000aba6  mov     r8, rbp; lpMem
0x14000aba9  xor     edx, edx; dwFlags
0x14000abab  mov     rcx, rax; hHeap
0x14000abae  call    cs:__imp_HeapFree
0x14000abb4  lea     rax, [r15+rbx]
0x14000abb8  mov     [rdi], rbx
0x14000abbb  mov     [rdi+8], rax
0x14000abbf  mov     ecx, esi; dwErrCode
0x14000abc1  lea     rax, [r14+rbx]
0x14000abc5  mov     [rdi+10h], rax
0x14000abc9  call    cs:__imp_SetLastError
0x14000abcf  mov     al, 1
0x14000abd1  add     rsp, 28h
0x14000abd5  pop     r15
0x14000abd7  pop     r14
0x14000abd9  pop     rdi
0x14000abda  pop     rsi
0x14000abdb  pop     rbp
0x14000abdc  pop     rbx
0x14000abdd  retn
```
