# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000c9ec`
- end: `0x18000cba1`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `437`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b1f0`
- `0x18000c8e8`
- `0x18000c91c`

## callees

- `0x180009d24`
- `0x18000c9ec`
- `0x18000cba8`
- `0x18000dfc4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cb05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cb38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cb05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cb38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000caa9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000caa9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb46`

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
  const char *v14; // r9
  __int64 v15; // rsi
  __int64 v16; // rdi
  void *v17; // rbp
  HANDLE ProcessHeap; // rax
  void *v19; // rdi
  void *v20; // rsi
  HANDLE v21; // rax
  HANDLE v22; // rax
  __int128 v23; // [rsp+30h] [rbp-68h] BYREF
  __int128 v24; // [rsp+40h] [rbp-58h]
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
    v23 = 0;
    v24 = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&v23, v12 + 10) )
    {
      v15 = v23;
      v16 = v24 - v23;
      if ( (_QWORD)v24 - (_QWORD)v23 < 0xAu )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x14C9,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Staging.h",
          v14);
      v17 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = 0;
      if ( v17 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v17);
      }
      *v13 = v15;
      *((_QWORD *)this + 5) = v16 + v15;
      v19 = 0;
      *((_BYTE *)this + 57) = 0;
      *(_WORD *)v15 = 0;
      *(_WORD *)(v15 + 2) = *(_WORD *)this;
      *(_WORD *)(v15 + 4) = *((_WORD *)this + 1);
      *(_BYTE *)(v15 + 8) = *((_BYTE *)this + 4);
      *(_WORD *)(v15 + 6) = *((_WORD *)this + 3);
      *(_BYTE *)(v15 + 9) = *((_BYTE *)this + 8);
      *((_QWORD *)this + 4) = *v13 + 10LL;
      v20 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = *((_QWORD *)&v24 + 1);
      if ( v20 )
      {
        v21 = GetProcessHeap();
        HeapFree(v21, 0, v20);
      }
      v9 = a2;
      v6 = a6;
      *((_BYTE *)this + 58) = 1;
    }
    else
    {
      v19 = (void *)*((_QWORD *)&v24 + 1);
    }
    if ( v19 )
    {
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v19);
    }
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, v9, a3, a4, a5, v6);
}

```

## disassembly

```asm
0x18000c9ec  mov     [rsp+Buf1], rdx
0x18000c9f1  push    rbx
0x18000c9f2  push    rbp
0x18000c9f3  push    rsi
0x18000c9f4  push    rdi
0x18000c9f5  push    r12
0x18000c9f7  push    r13
0x18000c9f9  push    r14
0x18000c9fb  push    r15
0x18000c9fd  sub     rsp, 58h
0x18000ca01  mov     ebp, [rsp+98h+arg_28]
0x18000ca08  mov     r13, r9
0x18000ca0b  mov     r12, [rsp+98h+arg_20]
0x18000ca13  mov     r15, r8
0x18000ca16  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000ca1a  mov     rsi, rdx
0x18000ca1d  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000ca22  mov     rbx, rcx
0x18000ca25  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000ca2a  test    al, al
0x18000ca2c  jz      short loc_18000CA35
0x18000ca2e  mov     al, 1
0x18000ca30  jmp     loc_18000CB76
0x18000ca35  lea     rdx, [r12+20h]
0x18000ca3a  add     rdx, r15; unsigned __int64
0x18000ca3d  lea     r14, [rbx+18h]
0x18000ca41  cmp     qword ptr [r14], 0
0x18000ca45  jnz     loc_18000CB4E
0x18000ca4b  xorps   xmm0, xmm0
0x18000ca4e  lea     rcx, [rsp+98h+var_68]; this
0x18000ca53  xorps   xmm1, xmm1
0x18000ca56  add     rdx, 0Ah; unsigned __int64
0x18000ca5a  movdqu  [rsp+98h+var_68], xmm0
0x18000ca60  movdqu  [rsp+98h+var_58], xmm1
0x18000ca66  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000ca6b  test    al, al
0x18000ca6d  jz      loc_18000CB2E
0x18000ca73  mov     rdi, qword ptr [rsp+98h+var_58]
0x18000ca78  mov     rsi, qword ptr [rsp+98h+var_68]
0x18000ca7d  sub     rdi, rsi
0x18000ca80  cmp     rdi, 0Ah
0x18000ca84  jb      loc_18000CB87
0x18000ca8a  mov     rbp, [rbx+30h]
0x18000ca8e  mov     qword ptr [rbx+30h], 0
0x18000ca96  test    rbp, rbp
0x18000ca99  jz      short loc_18000CAAF
0x18000ca9b  call    cs:__imp_GetProcessHeap
0x18000caa1  mov     r8, rbp; lpMem
0x18000caa4  xor     edx, edx; dwFlags
0x18000caa6  mov     rcx, rax; hHeap
0x18000caa9  call    cs:__imp_HeapFree
0x18000caaf  mov     [r14], rsi
0x18000cab2  lea     rax, [rdi+rsi]
0x18000cab6  mov     [rbx+28h], rax
0x18000caba  xor     edi, edi
0x18000cabc  xor     eax, eax
0x18000cabe  mov     byte ptr [rbx+39h], 0
0x18000cac2  mov     [rsi], ax
0x18000cac5  movzx   eax, word ptr [rbx]
0x18000cac8  mov     [rsi+2], ax
0x18000cacc  movzx   eax, word ptr [rbx+2]
0x18000cad0  mov     [rsi+4], ax
0x18000cad4  mov     al, [rbx+4]
0x18000cad7  mov     [rsi+8], al
0x18000cada  movzx   eax, word ptr [rbx+6]
0x18000cade  mov     [rsi+6], ax
0x18000cae2  mov     al, [rbx+8]
0x18000cae5  mov     [rsi+9], al
0x18000cae8  mov     rax, [r14]
0x18000caeb  add     rax, 0Ah
0x18000caef  mov     [rbx+20h], rax
0x18000caf3  mov     rsi, [rbx+30h]
0x18000caf7  mov     rax, qword ptr [rsp+98h+var_58+8]
0x18000cafc  mov     [rbx+30h], rax
0x18000cb00  test    rsi, rsi
0x18000cb03  jz      short loc_18000CB19
0x18000cb05  call    cs:__imp_GetProcessHeap
0x18000cb0b  mov     r8, rsi; lpMem
0x18000cb0e  xor     edx, edx; dwFlags
0x18000cb10  mov     rcx, rax; hHeap
0x18000cb13  call    cs:__imp_HeapFree
0x18000cb19  mov     rsi, [rsp+98h+Buf1]
0x18000cb21  mov     ebp, [rsp+98h+arg_28]
0x18000cb28  mov     byte ptr [rbx+3Ah], 1
0x18000cb2c  jmp     short loc_18000CB33
0x18000cb2e  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x18000cb33  test    rdi, rdi
0x18000cb36  jz      short loc_18000CB5C
0x18000cb38  call    cs:__imp_GetProcessHeap
0x18000cb3e  mov     r8, rdi; lpMem
0x18000cb41  xor     edx, edx; dwFlags
0x18000cb43  mov     rcx, rax; hHeap
0x18000cb46  call    cs:__imp_HeapFree
0x18000cb4c  jmp     short loc_18000CB5C
0x18000cb4e  cmp     byte ptr [rbx+3Ah], 0
0x18000cb52  jz      short loc_18000CB5C
0x18000cb54  mov     rcx, r14; this
0x18000cb57  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000cb5c  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000cb60  mov     r9, r13; void *
0x18000cb63  mov     r8, r15; Size
0x18000cb66  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000cb6b  mov     rdx, rsi; Buf1
0x18000cb6e  mov     rcx, rbx; this
0x18000cb71  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000cb76  add     rsp, 58h
0x18000cb7a  pop     r15
0x18000cb7c  pop     r14
0x18000cb7e  pop     r13
0x18000cb80  pop     r12
0x18000cb82  pop     rdi
0x18000cb83  pop     rsi
0x18000cb84  pop     rbp
0x18000cb85  pop     rbx
0x18000cb86  retn
0x18000cb87  mov     rcx, [rsp+98h]; this
0x18000cb8f  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Stagi"...
0x18000cb96  mov     edx, 14C9h; void *
0x18000cb9b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
