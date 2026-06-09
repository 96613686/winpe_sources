# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140009860`
- end: `0x140009a09`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400088e0`
- `0x140009760`
- `0x140009794`

## callees

- `0x140009860`
- `0x140009a10`
- `0x14000aaa0`
- `0x14000ab0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000991d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009987`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400099ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000991d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009987`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400099ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000990f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009979`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400099ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000990f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009979`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400099ac`

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
0x140009860  mov     [rsp+Buf1], rdx
0x140009865  push    rbx
0x140009866  push    rbp
0x140009867  push    rsi
0x140009868  push    rdi
0x140009869  push    r12
0x14000986b  push    r13
0x14000986d  push    r14
0x14000986f  push    r15
0x140009871  sub     rsp, 58h
0x140009875  mov     ebp, [rsp+98h+arg_28]
0x14000987c  mov     r13, r9
0x14000987f  mov     r12, [rsp+98h+arg_20]
0x140009887  mov     r15, r8
0x14000988a  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000988e  mov     rsi, rdx
0x140009891  mov     [rsp+98h+var_78], r12; unsigned __int64
0x140009896  mov     rbx, rcx
0x140009899  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000989e  test    al, al
0x1400098a0  jz      short loc_1400098A9
0x1400098a2  mov     al, 1
0x1400098a4  jmp     loc_1400099EA
0x1400098a9  lea     rdx, [r12+20h]
0x1400098ae  add     rdx, r15; unsigned __int64
0x1400098b1  lea     r14, [rbx+18h]
0x1400098b5  cmp     qword ptr [r14], 0
0x1400098b9  jnz     loc_1400099C2
0x1400098bf  xorps   xmm0, xmm0
0x1400098c2  lea     rcx, [rsp+98h+var_68]; this
0x1400098c7  xorps   xmm1, xmm1
0x1400098ca  add     rdx, 0Ah; unsigned __int64
0x1400098ce  movdqu  [rsp+98h+var_68], xmm0
0x1400098d4  movdqu  [rsp+98h+var_58], xmm1
0x1400098da  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400098df  test    al, al
0x1400098e1  jz      loc_1400099A2
0x1400098e7  mov     rdi, qword ptr [rsp+98h+var_58]
0x1400098ec  mov     rsi, qword ptr [rsp+98h+var_68]
0x1400098f1  sub     rdi, rsi
0x1400098f4  cmp     rdi, 0Ah
0x1400098f8  jb      loc_1400099FB
0x1400098fe  mov     rbp, [rbx+30h]
0x140009902  mov     qword ptr [rbx+30h], 0
0x14000990a  test    rbp, rbp
0x14000990d  jz      short loc_140009923
0x14000990f  call    cs:__imp_GetProcessHeap
0x140009915  mov     r8, rbp; lpMem
0x140009918  xor     edx, edx; dwFlags
0x14000991a  mov     rcx, rax; hHeap
0x14000991d  call    cs:__imp_HeapFree
0x140009923  mov     [r14], rsi
0x140009926  lea     rax, [rdi+rsi]
0x14000992a  mov     [rbx+28h], rax
0x14000992e  xor     edi, edi
0x140009930  xor     eax, eax
0x140009932  mov     byte ptr [rbx+39h], 0
0x140009936  mov     [rsi], ax
0x140009939  movzx   eax, word ptr [rbx]
0x14000993c  mov     [rsi+2], ax
0x140009940  movzx   eax, word ptr [rbx+2]
0x140009944  mov     [rsi+4], ax
0x140009948  mov     al, [rbx+4]
0x14000994b  mov     [rsi+8], al
0x14000994e  movzx   eax, word ptr [rbx+6]
0x140009952  mov     [rsi+6], ax
0x140009956  mov     al, [rbx+8]
0x140009959  mov     [rsi+9], al
0x14000995c  mov     rax, [r14]
0x14000995f  add     rax, 0Ah
0x140009963  mov     [rbx+20h], rax
0x140009967  mov     rsi, [rbx+30h]
0x14000996b  mov     rax, qword ptr [rsp+98h+var_58+8]
0x140009970  mov     [rbx+30h], rax
0x140009974  test    rsi, rsi
0x140009977  jz      short loc_14000998D
0x140009979  call    cs:__imp_GetProcessHeap
0x14000997f  mov     r8, rsi; lpMem
0x140009982  xor     edx, edx; dwFlags
0x140009984  mov     rcx, rax; hHeap
0x140009987  call    cs:__imp_HeapFree
0x14000998d  mov     rsi, [rsp+98h+Buf1]
0x140009995  mov     ebp, [rsp+98h+arg_28]
0x14000999c  mov     byte ptr [rbx+3Ah], 1
0x1400099a0  jmp     short loc_1400099A7
0x1400099a2  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x1400099a7  test    rdi, rdi
0x1400099aa  jz      short loc_1400099D0
0x1400099ac  call    cs:__imp_GetProcessHeap
0x1400099b2  mov     r8, rdi; lpMem
0x1400099b5  xor     edx, edx; dwFlags
0x1400099b7  mov     rcx, rax; hHeap
0x1400099ba  call    cs:__imp_HeapFree
0x1400099c0  jmp     short loc_1400099D0
0x1400099c2  cmp     byte ptr [rbx+3Ah], 0
0x1400099c6  jz      short loc_1400099D0
0x1400099c8  mov     rcx, r14; this
0x1400099cb  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400099d0  mov     [rsp+98h+var_70], ebp; unsigned int
0x1400099d4  mov     r9, r13; void *
0x1400099d7  mov     r8, r15; Size
0x1400099da  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1400099df  mov     rdx, rsi; Buf1
0x1400099e2  mov     rcx, rbx; this
0x1400099e5  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1400099ea  add     rsp, 58h
0x1400099ee  pop     r15
0x1400099f0  pop     r14
0x1400099f2  pop     r13
0x1400099f4  pop     r12
0x1400099f6  pop     rdi
0x1400099f7  pop     rsi
0x1400099f8  pop     rbp
0x1400099f9  pop     rbx
0x1400099fa  retn
0x1400099fb  mov     rcx, [rsp+98h]; this
0x140009a03  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
