# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006fb4`
- end: `0x18000715d`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003db0`
- `0x180006eb4`
- `0x180006ee8`

## callees

- `0x180006fb4`
- `0x180007164`
- `0x180008d34`
- `0x180008d9c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007071`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800070db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000710e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007071`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800070db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000710e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007063`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800070cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007100`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007063`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800070cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007100`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
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
0x180006fb4  mov     [rsp+Buf1], rdx
0x180006fb9  push    rbx
0x180006fba  push    rbp
0x180006fbb  push    rsi
0x180006fbc  push    rdi
0x180006fbd  push    r12
0x180006fbf  push    r13
0x180006fc1  push    r14
0x180006fc3  push    r15
0x180006fc5  sub     rsp, 58h
0x180006fc9  mov     ebp, [rsp+98h+arg_28]
0x180006fd0  mov     r13, r9
0x180006fd3  mov     r12, [rsp+98h+arg_20]
0x180006fdb  mov     r15, r8
0x180006fde  mov     [rsp+98h+var_70], ebp; unsigned int
0x180006fe2  mov     rsi, rdx
0x180006fe5  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180006fea  mov     rbx, rcx
0x180006fed  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180006ff2  test    al, al
0x180006ff4  jz      short loc_180006FFD
0x180006ff6  mov     al, 1
0x180006ff8  jmp     loc_18000713E
0x180006ffd  lea     rdx, [r12+20h]
0x180007002  add     rdx, r15; unsigned __int64
0x180007005  lea     r14, [rbx+18h]
0x180007009  cmp     qword ptr [r14], 0
0x18000700d  jnz     loc_180007116
0x180007013  xorps   xmm0, xmm0
0x180007016  lea     rcx, [rsp+98h+var_68]; this
0x18000701b  xorps   xmm1, xmm1
0x18000701e  add     rdx, 0Ah; unsigned __int64
0x180007022  movdqu  [rsp+98h+var_68], xmm0
0x180007028  movdqu  [rsp+98h+var_58], xmm1
0x18000702e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007033  test    al, al
0x180007035  jz      loc_1800070F6
0x18000703b  mov     rdi, qword ptr [rsp+98h+var_58]
0x180007040  mov     rsi, qword ptr [rsp+98h+var_68]
0x180007045  sub     rdi, rsi
0x180007048  cmp     rdi, 0Ah
0x18000704c  jb      loc_18000714F
0x180007052  mov     rbp, [rbx+30h]
0x180007056  mov     qword ptr [rbx+30h], 0
0x18000705e  test    rbp, rbp
0x180007061  jz      short loc_180007077
0x180007063  call    cs:__imp_GetProcessHeap
0x180007069  mov     r8, rbp; lpMem
0x18000706c  xor     edx, edx; dwFlags
0x18000706e  mov     rcx, rax; hHeap
0x180007071  call    cs:__imp_HeapFree
0x180007077  mov     [r14], rsi
0x18000707a  lea     rax, [rdi+rsi]
0x18000707e  mov     [rbx+28h], rax
0x180007082  xor     edi, edi
0x180007084  xor     eax, eax
0x180007086  mov     byte ptr [rbx+39h], 0
0x18000708a  mov     [rsi], ax
0x18000708d  movzx   eax, word ptr [rbx]
0x180007090  mov     [rsi+2], ax
0x180007094  movzx   eax, word ptr [rbx+2]
0x180007098  mov     [rsi+4], ax
0x18000709c  mov     al, [rbx+4]
0x18000709f  mov     [rsi+8], al
0x1800070a2  movzx   eax, word ptr [rbx+6]
0x1800070a6  mov     [rsi+6], ax
0x1800070aa  mov     al, [rbx+8]
0x1800070ad  mov     [rsi+9], al
0x1800070b0  mov     rax, [r14]
0x1800070b3  add     rax, 0Ah
0x1800070b7  mov     [rbx+20h], rax
0x1800070bb  mov     rsi, [rbx+30h]
0x1800070bf  mov     rax, qword ptr [rsp+98h+var_58+8]
0x1800070c4  mov     [rbx+30h], rax
0x1800070c8  test    rsi, rsi
0x1800070cb  jz      short loc_1800070E1
0x1800070cd  call    cs:__imp_GetProcessHeap
0x1800070d3  mov     r8, rsi; lpMem
0x1800070d6  xor     edx, edx; dwFlags
0x1800070d8  mov     rcx, rax; hHeap
0x1800070db  call    cs:__imp_HeapFree
0x1800070e1  mov     rsi, [rsp+98h+Buf1]
0x1800070e9  mov     ebp, [rsp+98h+arg_28]
0x1800070f0  mov     byte ptr [rbx+3Ah], 1
0x1800070f4  jmp     short loc_1800070FB
0x1800070f6  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x1800070fb  test    rdi, rdi
0x1800070fe  jz      short loc_180007124
0x180007100  call    cs:__imp_GetProcessHeap
0x180007106  mov     r8, rdi; lpMem
0x180007109  xor     edx, edx; dwFlags
0x18000710b  mov     rcx, rax; hHeap
0x18000710e  call    cs:__imp_HeapFree
0x180007114  jmp     short loc_180007124
0x180007116  cmp     byte ptr [rbx+3Ah], 0
0x18000711a  jz      short loc_180007124
0x18000711c  mov     rcx, r14; this
0x18000711f  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007124  mov     [rsp+98h+var_70], ebp; unsigned int
0x180007128  mov     r9, r13; void *
0x18000712b  mov     r8, r15; Size
0x18000712e  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180007133  mov     rdx, rsi; Buf1
0x180007136  mov     rcx, rbx; this
0x180007139  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000713e  add     rsp, 58h
0x180007142  pop     r15
0x180007144  pop     r14
0x180007146  pop     r13
0x180007148  pop     r12
0x18000714a  pop     rdi
0x18000714b  pop     rsi
0x18000714c  pop     rbp
0x18000714d  pop     rbx
0x18000714e  retn
0x18000714f  mov     rcx, [rsp+98h]; this
0x180007157  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
