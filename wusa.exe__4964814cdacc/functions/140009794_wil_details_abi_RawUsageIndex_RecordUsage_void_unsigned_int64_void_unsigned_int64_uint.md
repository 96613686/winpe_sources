# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140009794`
- end: `0x140009949`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `437`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140005300`
- `0x140009694`
- `0x1400096c8`

## callees

- `0x140009794`
- `0x140009950`
- `0x14000c0dc`
- `0x14000c16c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140009851`
- `KERNEL32!HeapFree` at `0x1400098bb`
- `KERNEL32!HeapFree` at `0x1400098ee`
- `KERNEL32!HeapFree` at `0x140009851`
- `KERNEL32!HeapFree` at `0x1400098bb`
- `KERNEL32!HeapFree` at `0x1400098ee`
- `KERNEL32!GetProcessHeap` at `0x140009843`
- `KERNEL32!GetProcessHeap` at `0x1400098ad`
- `KERNEL32!GetProcessHeap` at `0x1400098e0`
- `KERNEL32!GetProcessHeap` at `0x140009843`
- `KERNEL32!GetProcessHeap` at `0x1400098ad`
- `KERNEL32!GetProcessHeap` at `0x1400098e0`

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
0x140009794  mov     [rsp+Buf1], rdx
0x140009799  push    rbx
0x14000979a  push    rbp
0x14000979b  push    rsi
0x14000979c  push    rdi
0x14000979d  push    r12
0x14000979f  push    r13
0x1400097a1  push    r14
0x1400097a3  push    r15
0x1400097a5  sub     rsp, 58h
0x1400097a9  mov     ebp, [rsp+98h+arg_28]
0x1400097b0  mov     r13, r9
0x1400097b3  mov     r12, [rsp+98h+arg_20]
0x1400097bb  mov     r15, r8
0x1400097be  mov     [rsp+98h+var_70], ebp; unsigned int
0x1400097c2  mov     rsi, rdx
0x1400097c5  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1400097ca  mov     rbx, rcx
0x1400097cd  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1400097d2  test    al, al
0x1400097d4  jz      short loc_1400097DD
0x1400097d6  mov     al, 1
0x1400097d8  jmp     loc_14000991E
0x1400097dd  lea     rdx, [r12+20h]
0x1400097e2  add     rdx, r15; unsigned __int64
0x1400097e5  lea     r14, [rbx+18h]
0x1400097e9  cmp     qword ptr [r14], 0
0x1400097ed  jnz     loc_1400098F6
0x1400097f3  xorps   xmm0, xmm0
0x1400097f6  lea     rcx, [rsp+98h+var_68]; this
0x1400097fb  xorps   xmm1, xmm1
0x1400097fe  add     rdx, 0Ah; unsigned __int64
0x140009802  movdqu  [rsp+98h+var_68], xmm0
0x140009808  movdqu  [rsp+98h+var_58], xmm1
0x14000980e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140009813  test    al, al
0x140009815  jz      loc_1400098D6
0x14000981b  mov     rdi, qword ptr [rsp+98h+var_58]
0x140009820  mov     rsi, qword ptr [rsp+98h+var_68]
0x140009825  sub     rdi, rsi
0x140009828  cmp     rdi, 0Ah
0x14000982c  jb      loc_14000992F
0x140009832  mov     rbp, [rbx+30h]
0x140009836  mov     qword ptr [rbx+30h], 0
0x14000983e  test    rbp, rbp
0x140009841  jz      short loc_140009857
0x140009843  call    cs:__imp_GetProcessHeap
0x140009849  mov     r8, rbp; lpMem
0x14000984c  xor     edx, edx; dwFlags
0x14000984e  mov     rcx, rax; hHeap
0x140009851  call    cs:__imp_HeapFree
0x140009857  mov     [r14], rsi
0x14000985a  lea     rax, [rdi+rsi]
0x14000985e  mov     [rbx+28h], rax
0x140009862  xor     edi, edi
0x140009864  xor     eax, eax
0x140009866  mov     byte ptr [rbx+39h], 0
0x14000986a  mov     [rsi], ax
0x14000986d  movzx   eax, word ptr [rbx]
0x140009870  mov     [rsi+2], ax
0x140009874  movzx   eax, word ptr [rbx+2]
0x140009878  mov     [rsi+4], ax
0x14000987c  mov     al, [rbx+4]
0x14000987f  mov     [rsi+8], al
0x140009882  movzx   eax, word ptr [rbx+6]
0x140009886  mov     [rsi+6], ax
0x14000988a  mov     al, [rbx+8]
0x14000988d  mov     [rsi+9], al
0x140009890  mov     rax, [r14]
0x140009893  add     rax, 0Ah
0x140009897  mov     [rbx+20h], rax
0x14000989b  mov     rsi, [rbx+30h]
0x14000989f  mov     rax, qword ptr [rsp+98h+var_58+8]
0x1400098a4  mov     [rbx+30h], rax
0x1400098a8  test    rsi, rsi
0x1400098ab  jz      short loc_1400098C1
0x1400098ad  call    cs:__imp_GetProcessHeap
0x1400098b3  mov     r8, rsi; lpMem
0x1400098b6  xor     edx, edx; dwFlags
0x1400098b8  mov     rcx, rax; hHeap
0x1400098bb  call    cs:__imp_HeapFree
0x1400098c1  mov     rsi, [rsp+98h+Buf1]
0x1400098c9  mov     ebp, [rsp+98h+arg_28]
0x1400098d0  mov     byte ptr [rbx+3Ah], 1
0x1400098d4  jmp     short loc_1400098DB
0x1400098d6  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x1400098db  test    rdi, rdi
0x1400098de  jz      short loc_140009904
0x1400098e0  call    cs:__imp_GetProcessHeap
0x1400098e6  mov     r8, rdi; lpMem
0x1400098e9  xor     edx, edx; dwFlags
0x1400098eb  mov     rcx, rax; hHeap
0x1400098ee  call    cs:__imp_HeapFree
0x1400098f4  jmp     short loc_140009904
0x1400098f6  cmp     byte ptr [rbx+3Ah], 0
0x1400098fa  jz      short loc_140009904
0x1400098fc  mov     rcx, r14; this
0x1400098ff  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140009904  mov     [rsp+98h+var_70], ebp; unsigned int
0x140009908  mov     r9, r13; void *
0x14000990b  mov     r8, r15; Size
0x14000990e  mov     [rsp+98h+var_78], r12; unsigned __int64
0x140009913  mov     rdx, rsi; Buf1
0x140009916  mov     rcx, rbx; this
0x140009919  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000991e  add     rsp, 58h
0x140009922  pop     r15
0x140009924  pop     r14
0x140009926  pop     r13
0x140009928  pop     r12
0x14000992a  pop     rdi
0x14000992b  pop     rsi
0x14000992c  pop     rbp
0x14000992d  pop     rbx
0x14000992e  retn
0x14000992f  mov     rcx, [rsp+98h]; this
0x140009937  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Stagi"...
0x14000993e  mov     edx, 14C9h; void *
0x140009943  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
