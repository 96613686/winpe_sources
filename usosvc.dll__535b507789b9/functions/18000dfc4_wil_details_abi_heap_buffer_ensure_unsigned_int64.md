# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000dfc4`
- end: `0x18000e096`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c420`
- `0x18000c9ec`
- `0x18000d9d8`

## callees

- `0x180005768`
- `0x180006a98`
- `0x18000dfc4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e058`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e058`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e066`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e066`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e029`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e081`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e029`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e005`

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
0x18000dfc4  push    rbx
0x18000dfc6  push    rbp
0x18000dfc7  push    rsi
0x18000dfc8  push    rdi
0x18000dfc9  push    r14
0x18000dfcb  push    r15
0x18000dfcd  sub     rsp, 28h
0x18000dfd1  mov     rdi, rcx
0x18000dfd4  mov     rbx, rdx
0x18000dfd7  mov     rcx, [rcx+10h]
0x18000dfdb  mov     rax, [rdi+8]
0x18000dfdf  sub     rax, [rdi]
0x18000dfe2  sub     rcx, [rdi]
0x18000dfe5  add     rax, rdx
0x18000dfe8  cmp     rax, rcx
0x18000dfeb  jb      loc_18000E087
0x18000dff1  lea     rax, [rcx+rcx]
0x18000dff5  cmp     rdx, rax
0x18000dff8  cmovb   rbx, rax
0x18000dffc  cmp     rcx, rbx
0x18000dfff  jnb     loc_18000E087
0x18000e005  call    cs:__imp_GetLastError
0x18000e00b  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000e00f  xor     ecx, ecx; dwFlags
0x18000e011  mov     esi, eax
0x18000e013  lea     r14, [rbx+40h]
0x18000e017  mov     rdx, r14; dwBytes
0x18000e01a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000e01f  mov     rbx, rax
0x18000e022  test    rax, rax
0x18000e025  jnz     short loc_18000E033
0x18000e027  mov     ecx, esi; dwErrCode
0x18000e029  call    cs:__imp_SetLastError
0x18000e02f  xor     al, al
0x18000e031  jmp     short loc_18000E089
0x18000e033  mov     r15, [rdi+8]
0x18000e037  mov     rdx, r14; DestinationSize
0x18000e03a  sub     r15, [rdi]
0x18000e03d  mov     rcx, rbx; Destination
0x18000e040  mov     r8, [rdi]; Source
0x18000e043  mov     r9, r15; SourceSize
0x18000e046  call    memcpy_s
0x18000e04b  mov     rbp, [rdi+18h]
0x18000e04f  mov     [rdi+18h], rbx
0x18000e053  test    rbp, rbp
0x18000e056  jz      short loc_18000E06C
0x18000e058  call    cs:__imp_GetProcessHeap
0x18000e05e  mov     r8, rbp; lpMem
0x18000e061  xor     edx, edx; dwFlags
0x18000e063  mov     rcx, rax; hHeap
0x18000e066  call    cs:__imp_HeapFree
0x18000e06c  lea     rax, [r15+rbx]
0x18000e070  mov     [rdi], rbx
0x18000e073  mov     [rdi+8], rax
0x18000e077  mov     ecx, esi; dwErrCode
0x18000e079  lea     rax, [r14+rbx]
0x18000e07d  mov     [rdi+10h], rax
0x18000e081  call    cs:__imp_SetLastError
0x18000e087  mov     al, 1
0x18000e089  add     rsp, 28h
0x18000e08d  pop     r15
0x18000e08f  pop     r14
0x18000e091  pop     rdi
0x18000e092  pop     rsi
0x18000e093  pop     rbp
0x18000e094  pop     rbx
0x18000e095  retn
```
