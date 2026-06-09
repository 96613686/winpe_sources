# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000cd54`
- end: `0x18000cefd`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800097a0`
- `0x18000cc54`
- `0x18000cc88`

## callees

- `0x18000cd54`
- `0x18000cf04`
- `0x18000f22c`
- `0x180011038`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ceae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ce7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ceae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cea0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ce6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cea0`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        size_t a3,
        void *a4,
        char *a5,
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
  char *v25; // [rsp+20h] [rbp-78h]
  __int128 v26; // [rsp+30h] [rbp-68h] BYREF
  __int128 v27; // [rsp+40h] [rbp-58h]
  wil::details::in1diag4 *retaddr; // [rsp+98h] [rbp+0h]

  v6 = a6;
  v9 = a2;
  if ( wil::details_abi::RawUsageIndex::RecordUsageInternal(this, a2, a3, a4, (unsigned __int64)a5, a6) )
    return 1;
  v12 = (unsigned __int64)&a5[a3 + 32];
  v13 = (_QWORD *)((char *)this + 24);
  if ( *((_QWORD *)this + 3) )
  {
    if ( *((_BYTE *)this + 58) )
      wil::details_abi::heap_buffer::ensure((wil::details_abi::RawUsageIndex *)((char *)this + 24), v12);
  }
  else
  {
    v26 = 0;
    v27 = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&v26, v12 + 10) )
    {
      v17 = v26;
      v18 = v27 - v26;
      if ( (_QWORD)v27 - (_QWORD)v26 < 0xAu )
        wil::details::in1diag4::_FailFast_Unexpected(retaddr, v14, v15, v16, v25);
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
      *((_QWORD *)this + 6) = *((_QWORD *)&v27 + 1);
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
      v21 = (void *)*((_QWORD *)&v27 + 1);
    }
    if ( v21 )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v21);
    }
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, v9, a3, a4, (unsigned __int64)a5, v6);
}

```

## disassembly

```asm
0x18000cd54  mov     [rsp+Buf1], rdx
0x18000cd59  push    rbx
0x18000cd5a  push    rbp
0x18000cd5b  push    rsi
0x18000cd5c  push    rdi
0x18000cd5d  push    r12
0x18000cd5f  push    r13
0x18000cd61  push    r14
0x18000cd63  push    r15
0x18000cd65  sub     rsp, 58h
0x18000cd69  mov     ebp, [rsp+98h+arg_28]
0x18000cd70  mov     r13, r9
0x18000cd73  mov     r12, [rsp+98h+arg_20]
0x18000cd7b  mov     r15, r8
0x18000cd7e  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000cd82  mov     rsi, rdx
0x18000cd85  mov     [rsp+98h+var_78], r12; char *
0x18000cd8a  mov     rbx, rcx
0x18000cd8d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000cd92  test    al, al
0x18000cd94  jz      short loc_18000CD9D
0x18000cd96  mov     al, 1
0x18000cd98  jmp     loc_18000CEDE
0x18000cd9d  lea     rdx, [r12+20h]
0x18000cda2  add     rdx, r15; unsigned __int64
0x18000cda5  lea     r14, [rbx+18h]
0x18000cda9  cmp     qword ptr [r14], 0
0x18000cdad  jnz     loc_18000CEB6
0x18000cdb3  xorps   xmm0, xmm0
0x18000cdb6  lea     rcx, [rsp+98h+var_68]; this
0x18000cdbb  xorps   xmm1, xmm1
0x18000cdbe  add     rdx, 0Ah; unsigned __int64
0x18000cdc2  movdqu  [rsp+98h+var_68], xmm0
0x18000cdc8  movdqu  [rsp+98h+var_58], xmm1
0x18000cdce  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000cdd3  test    al, al
0x18000cdd5  jz      loc_18000CE96
0x18000cddb  mov     rdi, qword ptr [rsp+98h+var_58]
0x18000cde0  mov     rsi, qword ptr [rsp+98h+var_68]
0x18000cde5  sub     rdi, rsi
0x18000cde8  cmp     rdi, 0Ah
0x18000cdec  jb      loc_18000CEEF
0x18000cdf2  mov     rbp, [rbx+30h]
0x18000cdf6  mov     qword ptr [rbx+30h], 0
0x18000cdfe  test    rbp, rbp
0x18000ce01  jz      short loc_18000CE17
0x18000ce03  call    cs:__imp_GetProcessHeap
0x18000ce09  mov     r8, rbp; lpMem
0x18000ce0c  xor     edx, edx; dwFlags
0x18000ce0e  mov     rcx, rax; hHeap
0x18000ce11  call    cs:__imp_HeapFree
0x18000ce17  mov     [r14], rsi
0x18000ce1a  lea     rax, [rdi+rsi]
0x18000ce1e  mov     [rbx+28h], rax
0x18000ce22  xor     edi, edi
0x18000ce24  xor     eax, eax
0x18000ce26  mov     byte ptr [rbx+39h], 0
0x18000ce2a  mov     [rsi], ax
0x18000ce2d  movzx   eax, word ptr [rbx]
0x18000ce30  mov     [rsi+2], ax
0x18000ce34  movzx   eax, word ptr [rbx+2]
0x18000ce38  mov     [rsi+4], ax
0x18000ce3c  mov     al, [rbx+4]
0x18000ce3f  mov     [rsi+8], al
0x18000ce42  movzx   eax, word ptr [rbx+6]
0x18000ce46  mov     [rsi+6], ax
0x18000ce4a  mov     al, [rbx+8]
0x18000ce4d  mov     [rsi+9], al
0x18000ce50  mov     rax, [r14]
0x18000ce53  add     rax, 0Ah
0x18000ce57  mov     [rbx+20h], rax
0x18000ce5b  mov     rsi, [rbx+30h]
0x18000ce5f  mov     rax, qword ptr [rsp+98h+var_58+8]
0x18000ce64  mov     [rbx+30h], rax
0x18000ce68  test    rsi, rsi
0x18000ce6b  jz      short loc_18000CE81
0x18000ce6d  call    cs:__imp_GetProcessHeap
0x18000ce73  mov     r8, rsi; lpMem
0x18000ce76  xor     edx, edx; dwFlags
0x18000ce78  mov     rcx, rax; hHeap
0x18000ce7b  call    cs:__imp_HeapFree
0x18000ce81  mov     rsi, [rsp+98h+Buf1]
0x18000ce89  mov     ebp, [rsp+98h+arg_28]
0x18000ce90  mov     byte ptr [rbx+3Ah], 1
0x18000ce94  jmp     short loc_18000CE9B
0x18000ce96  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x18000ce9b  test    rdi, rdi
0x18000ce9e  jz      short loc_18000CEC4
0x18000cea0  call    cs:__imp_GetProcessHeap
0x18000cea6  mov     r8, rdi; lpMem
0x18000cea9  xor     edx, edx; dwFlags
0x18000ceab  mov     rcx, rax; hHeap
0x18000ceae  call    cs:__imp_HeapFree
0x18000ceb4  jmp     short loc_18000CEC4
0x18000ceb6  cmp     byte ptr [rbx+3Ah], 0
0x18000ceba  jz      short loc_18000CEC4
0x18000cebc  mov     rcx, r14; this
0x18000cebf  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000cec4  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000cec8  mov     r9, r13; void *
0x18000cecb  mov     r8, r15; Size
0x18000cece  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000ced3  mov     rdx, rsi; Buf1
0x18000ced6  mov     rcx, rbx; this
0x18000ced9  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000cede  add     rsp, 58h
0x18000cee2  pop     r15
0x18000cee4  pop     r14
0x18000cee6  pop     r13
0x18000cee8  pop     r12
0x18000ceea  pop     rdi
0x18000ceeb  pop     rsi
0x18000ceec  pop     rbp
0x18000ceed  pop     rbx
0x18000ceee  retn
0x18000ceef  mov     rcx, [rsp+98h]; this
0x18000cef7  call    ?_FailFast_Unexpected@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_Unexpected(void *,uint,char const *,char const *)
```
