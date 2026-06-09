# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140007e00`
- end: `0x140007fa9`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140005410`
- `0x140007d00`
- `0x140007d34`

## callees

- `0x140007e00`
- `0x140007fb0`
- `0x14000a038`
- `0x14000a09c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007ebd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007f27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007f5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007ebd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007f27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007f5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007eaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007f19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007f4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007eaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007f19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007f4c`

## pseudocode

```c
bool __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        size_t a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  unsigned int v6; // ebp
  void *v9; // rsi
  unsigned __int64 v12; // rdx
  _QWORD *v13; // r14
  void *v14; // rdx
  unsigned int v15; // r8d
  const char *v16; // r9
  __int64 v17; // rsi
  __int64 v18; // rdi
  void *v19; // rbp
  HANDLE ProcessHeap; // rax
  void *v21; // rdi
  void *v22; // rsi
  HANDLE v23; // rax
  HANDLE v24; // rax
  __int128 v25; // [rsp+30h] [rbp-68h] BYREF
  __int128 v26; // [rsp+40h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v6 = a6;
  v9 = a2;
  if ( wil::details_abi::RawUsageIndex::RecordUsageInternal(this, a2, a3, a4, a5, a6) )
    return 1;
  v12 = a3 + a5 + 32;
  v13 = (_QWORD *)((char *)this + 24);
  if ( *((_QWORD *)this + 3) )
  {
    if ( *((_BYTE *)this + 58) )
      wil::details_abi::heap_buffer::ensure((wil::details_abi::RawUsageIndex *)((char *)this + 24), v12);
  }
  else
  {
    v25 = 0;
    v26 = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&v25, v12 + 10) )
    {
      v17 = v25;
      v18 = v26 - v25;
      if ( (_QWORD)v26 - (_QWORD)v25 < 0xAu )
        wil::details::in1diag3::_FailFast_Unexpected(retaddr, v14, v15, v16);
      v19 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = 0;
      if ( v19 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v19);
      }
      *v13 = v17;
      *((_QWORD *)this + 5) = v18 + v17;
      v21 = 0;
      *((_BYTE *)this + 57) = 0;
      *(_WORD *)v17 = 0;
      *(_WORD *)(v17 + 2) = *(_WORD *)this;
      *(_WORD *)(v17 + 4) = *((_WORD *)this + 1);
      *(_BYTE *)(v17 + 8) = *((_BYTE *)this + 4);
      *(_WORD *)(v17 + 6) = *((_WORD *)this + 3);
      *(_BYTE *)(v17 + 9) = *((_BYTE *)this + 8);
      *((_QWORD *)this + 4) = *v13 + 10LL;
      v22 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = *((_QWORD *)&v26 + 1);
      if ( v22 )
      {
        v23 = GetProcessHeap();
        HeapFree(v23, 0, v22);
      }
      v9 = a2;
      v6 = a6;
      *((_BYTE *)this + 58) = 1;
    }
    else
    {
      v21 = (void *)*((_QWORD *)&v26 + 1);
    }
    if ( v21 )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v21);
    }
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, v9, a3, a4, a5, v6);
}

```

## disassembly

```asm
0x140007e00  mov     [rsp+Buf1], rdx
0x140007e05  push    rbx
0x140007e06  push    rbp
0x140007e07  push    rsi
0x140007e08  push    rdi
0x140007e09  push    r12
0x140007e0b  push    r13
0x140007e0d  push    r14
0x140007e0f  push    r15
0x140007e11  sub     rsp, 58h
0x140007e15  mov     ebp, [rsp+98h+arg_28]
0x140007e1c  mov     r13, r9
0x140007e1f  mov     r12, [rsp+98h+arg_20]
0x140007e27  mov     r15, r8
0x140007e2a  mov     [rsp+98h+var_70], ebp; unsigned int
0x140007e2e  mov     rsi, rdx
0x140007e31  mov     [rsp+98h+var_78], r12; unsigned __int64
0x140007e36  mov     rbx, rcx
0x140007e39  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140007e3e  test    al, al
0x140007e40  jz      short loc_140007E49
0x140007e42  mov     al, 1
0x140007e44  jmp     loc_140007F8A
0x140007e49  lea     rdx, [r12+20h]
0x140007e4e  add     rdx, r15; unsigned __int64
0x140007e51  lea     r14, [rbx+18h]
0x140007e55  cmp     qword ptr [r14], 0
0x140007e59  jnz     loc_140007F62
0x140007e5f  xorps   xmm0, xmm0
0x140007e62  lea     rcx, [rsp+98h+var_68]; this
0x140007e67  xorps   xmm1, xmm1
0x140007e6a  add     rdx, 0Ah; unsigned __int64
0x140007e6e  movdqu  [rsp+98h+var_68], xmm0
0x140007e74  movdqu  [rsp+98h+var_58], xmm1
0x140007e7a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140007e7f  test    al, al
0x140007e81  jz      loc_140007F42
0x140007e87  mov     rdi, qword ptr [rsp+98h+var_58]
0x140007e8c  mov     rsi, qword ptr [rsp+98h+var_68]
0x140007e91  sub     rdi, rsi
0x140007e94  cmp     rdi, 0Ah
0x140007e98  jb      loc_140007F9B
0x140007e9e  mov     rbp, [rbx+30h]
0x140007ea2  mov     qword ptr [rbx+30h], 0
0x140007eaa  test    rbp, rbp
0x140007ead  jz      short loc_140007EC3
0x140007eaf  call    cs:__imp_GetProcessHeap
0x140007eb5  mov     r8, rbp; lpMem
0x140007eb8  xor     edx, edx; dwFlags
0x140007eba  mov     rcx, rax; hHeap
0x140007ebd  call    cs:__imp_HeapFree
0x140007ec3  mov     [r14], rsi
0x140007ec6  lea     rax, [rdi+rsi]
0x140007eca  mov     [rbx+28h], rax
0x140007ece  xor     edi, edi
0x140007ed0  xor     eax, eax
0x140007ed2  mov     byte ptr [rbx+39h], 0
0x140007ed6  mov     [rsi], ax
0x140007ed9  movzx   eax, word ptr [rbx]
0x140007edc  mov     [rsi+2], ax
0x140007ee0  movzx   eax, word ptr [rbx+2]
0x140007ee4  mov     [rsi+4], ax
0x140007ee8  mov     al, [rbx+4]
0x140007eeb  mov     [rsi+8], al
0x140007eee  movzx   eax, word ptr [rbx+6]
0x140007ef2  mov     [rsi+6], ax
0x140007ef6  mov     al, [rbx+8]
0x140007ef9  mov     [rsi+9], al
0x140007efc  mov     rax, [r14]
0x140007eff  add     rax, 0Ah
0x140007f03  mov     [rbx+20h], rax
0x140007f07  mov     rsi, [rbx+30h]
0x140007f0b  mov     rax, qword ptr [rsp+98h+var_58+8]
0x140007f10  mov     [rbx+30h], rax
0x140007f14  test    rsi, rsi
0x140007f17  jz      short loc_140007F2D
0x140007f19  call    cs:__imp_GetProcessHeap
0x140007f1f  mov     r8, rsi; lpMem
0x140007f22  xor     edx, edx; dwFlags
0x140007f24  mov     rcx, rax; hHeap
0x140007f27  call    cs:__imp_HeapFree
0x140007f2d  mov     rsi, [rsp+98h+Buf1]
0x140007f35  mov     ebp, [rsp+98h+arg_28]
0x140007f3c  mov     byte ptr [rbx+3Ah], 1
0x140007f40  jmp     short loc_140007F47
0x140007f42  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x140007f47  test    rdi, rdi
0x140007f4a  jz      short loc_140007F70
0x140007f4c  call    cs:__imp_GetProcessHeap
0x140007f52  mov     r8, rdi; lpMem
0x140007f55  xor     edx, edx; dwFlags
0x140007f57  mov     rcx, rax; hHeap
0x140007f5a  call    cs:__imp_HeapFree
0x140007f60  jmp     short loc_140007F70
0x140007f62  cmp     byte ptr [rbx+3Ah], 0
0x140007f66  jz      short loc_140007F70
0x140007f68  mov     rcx, r14; this
0x140007f6b  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140007f70  mov     [rsp+98h+var_70], ebp; unsigned int
0x140007f74  mov     r9, r13; void *
0x140007f77  mov     r8, r15; Size
0x140007f7a  mov     [rsp+98h+var_78], r12; unsigned __int64
0x140007f7f  mov     rdx, rsi; Buf1
0x140007f82  mov     rcx, rbx; this
0x140007f85  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140007f8a  add     rsp, 58h
0x140007f8e  pop     r15
0x140007f90  pop     r14
0x140007f92  pop     r13
0x140007f94  pop     r12
0x140007f96  pop     rdi
0x140007f97  pop     rsi
0x140007f98  pop     rbp
0x140007f99  pop     rbx
0x140007f9a  retn
0x140007f9b  mov     rcx, [rsp+98h]; this
0x140007fa3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
