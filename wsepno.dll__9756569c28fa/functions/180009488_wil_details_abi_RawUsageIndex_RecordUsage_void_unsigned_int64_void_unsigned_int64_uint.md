# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180009488`
- end: `0x180009631`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180005390`
- `0x180009384`
- `0x1800093b8`

## callees

- `0x180009488`
- `0x180009638`
- `0x18000b4c0`
- `0x18000b74c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009545`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009545`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009537`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009537`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095d4`

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
0x180009488  mov     [rsp+Buf1], rdx
0x18000948d  push    rbx
0x18000948e  push    rbp
0x18000948f  push    rsi
0x180009490  push    rdi
0x180009491  push    r12
0x180009493  push    r13
0x180009495  push    r14
0x180009497  push    r15
0x180009499  sub     rsp, 58h
0x18000949d  mov     ebp, [rsp+98h+arg_28]
0x1800094a4  mov     r13, r9
0x1800094a7  mov     r12, [rsp+98h+arg_20]
0x1800094af  mov     r15, r8
0x1800094b2  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800094b6  mov     rsi, rdx
0x1800094b9  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800094be  mov     rbx, rcx
0x1800094c1  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800094c6  test    al, al
0x1800094c8  jz      short loc_1800094D1
0x1800094ca  mov     al, 1
0x1800094cc  jmp     loc_180009612
0x1800094d1  lea     rdx, [r12+20h]
0x1800094d6  add     rdx, r15; unsigned __int64
0x1800094d9  lea     r14, [rbx+18h]
0x1800094dd  cmp     qword ptr [r14], 0
0x1800094e1  jnz     loc_1800095EA
0x1800094e7  xorps   xmm0, xmm0
0x1800094ea  lea     rcx, [rsp+98h+var_68]; this
0x1800094ef  xorps   xmm1, xmm1
0x1800094f2  add     rdx, 0Ah; unsigned __int64
0x1800094f6  movdqu  [rsp+98h+var_68], xmm0
0x1800094fc  movdqu  [rsp+98h+var_58], xmm1
0x180009502  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180009507  test    al, al
0x180009509  jz      loc_1800095CA
0x18000950f  mov     rdi, qword ptr [rsp+98h+var_58]
0x180009514  mov     rsi, qword ptr [rsp+98h+var_68]
0x180009519  sub     rdi, rsi
0x18000951c  cmp     rdi, 0Ah
0x180009520  jb      loc_180009623
0x180009526  mov     rbp, [rbx+30h]
0x18000952a  mov     qword ptr [rbx+30h], 0
0x180009532  test    rbp, rbp
0x180009535  jz      short loc_18000954B
0x180009537  call    cs:__imp_GetProcessHeap
0x18000953d  mov     r8, rbp; lpMem
0x180009540  xor     edx, edx; dwFlags
0x180009542  mov     rcx, rax; hHeap
0x180009545  call    cs:__imp_HeapFree
0x18000954b  mov     [r14], rsi
0x18000954e  lea     rax, [rdi+rsi]
0x180009552  mov     [rbx+28h], rax
0x180009556  xor     edi, edi
0x180009558  xor     eax, eax
0x18000955a  mov     byte ptr [rbx+39h], 0
0x18000955e  mov     [rsi], ax
0x180009561  movzx   eax, word ptr [rbx]
0x180009564  mov     [rsi+2], ax
0x180009568  movzx   eax, word ptr [rbx+2]
0x18000956c  mov     [rsi+4], ax
0x180009570  mov     al, [rbx+4]
0x180009573  mov     [rsi+8], al
0x180009576  movzx   eax, word ptr [rbx+6]
0x18000957a  mov     [rsi+6], ax
0x18000957e  mov     al, [rbx+8]
0x180009581  mov     [rsi+9], al
0x180009584  mov     rax, [r14]
0x180009587  add     rax, 0Ah
0x18000958b  mov     [rbx+20h], rax
0x18000958f  mov     rsi, [rbx+30h]
0x180009593  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180009598  mov     [rbx+30h], rax
0x18000959c  test    rsi, rsi
0x18000959f  jz      short loc_1800095B5
0x1800095a1  call    cs:__imp_GetProcessHeap
0x1800095a7  mov     r8, rsi; lpMem
0x1800095aa  xor     edx, edx; dwFlags
0x1800095ac  mov     rcx, rax; hHeap
0x1800095af  call    cs:__imp_HeapFree
0x1800095b5  mov     rsi, [rsp+98h+Buf1]
0x1800095bd  mov     ebp, [rsp+98h+arg_28]
0x1800095c4  mov     byte ptr [rbx+3Ah], 1
0x1800095c8  jmp     short loc_1800095CF
0x1800095ca  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x1800095cf  test    rdi, rdi
0x1800095d2  jz      short loc_1800095F8
0x1800095d4  call    cs:__imp_GetProcessHeap
0x1800095da  mov     r8, rdi; lpMem
0x1800095dd  xor     edx, edx; dwFlags
0x1800095df  mov     rcx, rax; hHeap
0x1800095e2  call    cs:__imp_HeapFree
0x1800095e8  jmp     short loc_1800095F8
0x1800095ea  cmp     byte ptr [rbx+3Ah], 0
0x1800095ee  jz      short loc_1800095F8
0x1800095f0  mov     rcx, r14; this
0x1800095f3  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800095f8  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800095fc  mov     r9, r13; void *
0x1800095ff  mov     r8, r15; Size
0x180009602  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180009607  mov     rdx, rsi; Buf1
0x18000960a  mov     rcx, rbx; this
0x18000960d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180009612  add     rsp, 58h
0x180009616  pop     r15
0x180009618  pop     r14
0x18000961a  pop     r13
0x18000961c  pop     r12
0x18000961e  pop     rdi
0x18000961f  pop     rsi
0x180009620  pop     rbp
0x180009621  pop     rbx
0x180009622  retn
0x180009623  mov     rcx, [rsp+98h]; this
0x18000962b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
