# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18001b784`
- end: `0x18001b92d`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a050`
- `0x18001b684`
- `0x18001b6b8`

## callees

- `0x180019328`
- `0x18001b784`
- `0x18001b934`
- `0x18001cd14`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b833`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b89d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b8d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b833`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b89d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b8d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b841`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b8ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b8de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b841`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b8ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b8de`

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
0x18001b784  mov     [rsp+Buf1], rdx
0x18001b789  push    rbx
0x18001b78a  push    rbp
0x18001b78b  push    rsi
0x18001b78c  push    rdi
0x18001b78d  push    r12
0x18001b78f  push    r13
0x18001b791  push    r14
0x18001b793  push    r15
0x18001b795  sub     rsp, 58h
0x18001b799  mov     ebp, [rsp+98h+arg_28]
0x18001b7a0  mov     r13, r9
0x18001b7a3  mov     r12, [rsp+98h+arg_20]
0x18001b7ab  mov     r15, r8
0x18001b7ae  mov     [rsp+98h+var_70], ebp; unsigned int
0x18001b7b2  mov     rsi, rdx
0x18001b7b5  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18001b7ba  mov     rbx, rcx
0x18001b7bd  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18001b7c2  test    al, al
0x18001b7c4  jz      short loc_18001B7CD
0x18001b7c6  mov     al, 1
0x18001b7c8  jmp     loc_18001B90E
0x18001b7cd  lea     rdx, [r12+20h]
0x18001b7d2  add     rdx, r15; unsigned __int64
0x18001b7d5  lea     r14, [rbx+18h]
0x18001b7d9  cmp     qword ptr [r14], 0
0x18001b7dd  jnz     loc_18001B8E6
0x18001b7e3  xorps   xmm0, xmm0
0x18001b7e6  lea     rcx, [rsp+98h+var_68]; this
0x18001b7eb  xorps   xmm1, xmm1
0x18001b7ee  add     rdx, 0Ah; unsigned __int64
0x18001b7f2  movdqu  [rsp+98h+var_68], xmm0
0x18001b7f8  movdqu  [rsp+98h+var_58], xmm1
0x18001b7fe  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001b803  test    al, al
0x18001b805  jz      loc_18001B8C6
0x18001b80b  mov     rdi, qword ptr [rsp+98h+var_58]
0x18001b810  mov     rsi, qword ptr [rsp+98h+var_68]
0x18001b815  sub     rdi, rsi
0x18001b818  cmp     rdi, 0Ah
0x18001b81c  jb      loc_18001B91F
0x18001b822  mov     rbp, [rbx+30h]
0x18001b826  mov     qword ptr [rbx+30h], 0
0x18001b82e  test    rbp, rbp
0x18001b831  jz      short loc_18001B847
0x18001b833  call    cs:__imp_GetProcessHeap
0x18001b839  mov     r8, rbp; lpMem
0x18001b83c  xor     edx, edx; dwFlags
0x18001b83e  mov     rcx, rax; hHeap
0x18001b841  call    cs:__imp_HeapFree
0x18001b847  mov     [r14], rsi
0x18001b84a  lea     rax, [rdi+rsi]
0x18001b84e  mov     [rbx+28h], rax
0x18001b852  xor     edi, edi
0x18001b854  xor     eax, eax
0x18001b856  mov     byte ptr [rbx+39h], 0
0x18001b85a  mov     [rsi], ax
0x18001b85d  movzx   eax, word ptr [rbx]
0x18001b860  mov     [rsi+2], ax
0x18001b864  movzx   eax, word ptr [rbx+2]
0x18001b868  mov     [rsi+4], ax
0x18001b86c  mov     al, [rbx+4]
0x18001b86f  mov     [rsi+8], al
0x18001b872  movzx   eax, word ptr [rbx+6]
0x18001b876  mov     [rsi+6], ax
0x18001b87a  mov     al, [rbx+8]
0x18001b87d  mov     [rsi+9], al
0x18001b880  mov     rax, [r14]
0x18001b883  add     rax, 0Ah
0x18001b887  mov     [rbx+20h], rax
0x18001b88b  mov     rsi, [rbx+30h]
0x18001b88f  mov     rax, qword ptr [rsp+98h+var_58+8]
0x18001b894  mov     [rbx+30h], rax
0x18001b898  test    rsi, rsi
0x18001b89b  jz      short loc_18001B8B1
0x18001b89d  call    cs:__imp_GetProcessHeap
0x18001b8a3  mov     r8, rsi; lpMem
0x18001b8a6  xor     edx, edx; dwFlags
0x18001b8a8  mov     rcx, rax; hHeap
0x18001b8ab  call    cs:__imp_HeapFree
0x18001b8b1  mov     rsi, [rsp+98h+Buf1]
0x18001b8b9  mov     ebp, [rsp+98h+arg_28]
0x18001b8c0  mov     byte ptr [rbx+3Ah], 1
0x18001b8c4  jmp     short loc_18001B8CB
0x18001b8c6  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x18001b8cb  test    rdi, rdi
0x18001b8ce  jz      short loc_18001B8F4
0x18001b8d0  call    cs:__imp_GetProcessHeap
0x18001b8d6  mov     r8, rdi; lpMem
0x18001b8d9  xor     edx, edx; dwFlags
0x18001b8db  mov     rcx, rax; hHeap
0x18001b8de  call    cs:__imp_HeapFree
0x18001b8e4  jmp     short loc_18001B8F4
0x18001b8e6  cmp     byte ptr [rbx+3Ah], 0
0x18001b8ea  jz      short loc_18001B8F4
0x18001b8ec  mov     rcx, r14; this
0x18001b8ef  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001b8f4  mov     [rsp+98h+var_70], ebp; unsigned int
0x18001b8f8  mov     r9, r13; void *
0x18001b8fb  mov     r8, r15; Size
0x18001b8fe  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18001b903  mov     rdx, rsi; Buf1
0x18001b906  mov     rcx, rbx; this
0x18001b909  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18001b90e  add     rsp, 58h
0x18001b912  pop     r15
0x18001b914  pop     r14
0x18001b916  pop     r13
0x18001b918  pop     r12
0x18001b91a  pop     rdi
0x18001b91b  pop     rsi
0x18001b91c  pop     rbp
0x18001b91d  pop     rbx
0x18001b91e  retn
0x18001b91f  mov     rcx, [rsp+98h]; this
0x18001b927  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
