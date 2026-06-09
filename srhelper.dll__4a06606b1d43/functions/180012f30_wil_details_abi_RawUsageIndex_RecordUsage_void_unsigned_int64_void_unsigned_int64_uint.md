# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180012f30`
- end: `0x1800130d9`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800106f0`
- `0x180012e30`
- `0x180012e64`

## callees

- `0x180012f30`
- `0x1800130e0`
- `0x1800149b8`
- `0x180014a04`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180012fed`
- `KERNEL32!HeapFree` at `0x180013057`
- `KERNEL32!HeapFree` at `0x18001308a`
- `KERNEL32!HeapFree` at `0x180012fed`
- `KERNEL32!HeapFree` at `0x180013057`
- `KERNEL32!HeapFree` at `0x18001308a`
- `KERNEL32!GetProcessHeap` at `0x180012fdf`
- `KERNEL32!GetProcessHeap` at `0x180013049`
- `KERNEL32!GetProcessHeap` at `0x18001307c`
- `KERNEL32!GetProcessHeap` at `0x180012fdf`
- `KERNEL32!GetProcessHeap` at `0x180013049`
- `KERNEL32!GetProcessHeap` at `0x18001307c`

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
0x180012f30  mov     [rsp+Buf1], rdx
0x180012f35  push    rbx
0x180012f36  push    rbp
0x180012f37  push    rsi
0x180012f38  push    rdi
0x180012f39  push    r12
0x180012f3b  push    r13
0x180012f3d  push    r14
0x180012f3f  push    r15
0x180012f41  sub     rsp, 58h
0x180012f45  mov     ebp, [rsp+98h+arg_28]
0x180012f4c  mov     r13, r9
0x180012f4f  mov     r12, [rsp+98h+arg_20]
0x180012f57  mov     r15, r8
0x180012f5a  mov     [rsp+98h+var_70], ebp; unsigned int
0x180012f5e  mov     rsi, rdx
0x180012f61  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180012f66  mov     rbx, rcx
0x180012f69  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180012f6e  test    al, al
0x180012f70  jz      short loc_180012F79
0x180012f72  mov     al, 1
0x180012f74  jmp     loc_1800130BA
0x180012f79  lea     rdx, [r12+20h]
0x180012f7e  add     rdx, r15; unsigned __int64
0x180012f81  lea     r14, [rbx+18h]
0x180012f85  cmp     qword ptr [r14], 0
0x180012f89  jnz     loc_180013092
0x180012f8f  xorps   xmm0, xmm0
0x180012f92  lea     rcx, [rsp+98h+var_68]; this
0x180012f97  xorps   xmm1, xmm1
0x180012f9a  add     rdx, 0Ah; unsigned __int64
0x180012f9e  movdqu  [rsp+98h+var_68], xmm0
0x180012fa4  movdqu  [rsp+98h+var_58], xmm1
0x180012faa  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180012faf  test    al, al
0x180012fb1  jz      loc_180013072
0x180012fb7  mov     rdi, qword ptr [rsp+98h+var_58]
0x180012fbc  mov     rsi, qword ptr [rsp+98h+var_68]
0x180012fc1  sub     rdi, rsi
0x180012fc4  cmp     rdi, 0Ah
0x180012fc8  jb      loc_1800130CB
0x180012fce  mov     rbp, [rbx+30h]
0x180012fd2  mov     qword ptr [rbx+30h], 0
0x180012fda  test    rbp, rbp
0x180012fdd  jz      short loc_180012FF3
0x180012fdf  call    cs:__imp_GetProcessHeap
0x180012fe5  mov     r8, rbp; lpMem
0x180012fe8  xor     edx, edx; dwFlags
0x180012fea  mov     rcx, rax; hHeap
0x180012fed  call    cs:__imp_HeapFree
0x180012ff3  mov     [r14], rsi
0x180012ff6  lea     rax, [rdi+rsi]
0x180012ffa  mov     [rbx+28h], rax
0x180012ffe  xor     edi, edi
0x180013000  xor     eax, eax
0x180013002  mov     byte ptr [rbx+39h], 0
0x180013006  mov     [rsi], ax
0x180013009  movzx   eax, word ptr [rbx]
0x18001300c  mov     [rsi+2], ax
0x180013010  movzx   eax, word ptr [rbx+2]
0x180013014  mov     [rsi+4], ax
0x180013018  mov     al, [rbx+4]
0x18001301b  mov     [rsi+8], al
0x18001301e  movzx   eax, word ptr [rbx+6]
0x180013022  mov     [rsi+6], ax
0x180013026  mov     al, [rbx+8]
0x180013029  mov     [rsi+9], al
0x18001302c  mov     rax, [r14]
0x18001302f  add     rax, 0Ah
0x180013033  mov     [rbx+20h], rax
0x180013037  mov     rsi, [rbx+30h]
0x18001303b  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180013040  mov     [rbx+30h], rax
0x180013044  test    rsi, rsi
0x180013047  jz      short loc_18001305D
0x180013049  call    cs:__imp_GetProcessHeap
0x18001304f  mov     r8, rsi; lpMem
0x180013052  xor     edx, edx; dwFlags
0x180013054  mov     rcx, rax; hHeap
0x180013057  call    cs:__imp_HeapFree
0x18001305d  mov     rsi, [rsp+98h+Buf1]
0x180013065  mov     ebp, [rsp+98h+arg_28]
0x18001306c  mov     byte ptr [rbx+3Ah], 1
0x180013070  jmp     short loc_180013077
0x180013072  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180013077  test    rdi, rdi
0x18001307a  jz      short loc_1800130A0
0x18001307c  call    cs:__imp_GetProcessHeap
0x180013082  mov     r8, rdi; lpMem
0x180013085  xor     edx, edx; dwFlags
0x180013087  mov     rcx, rax; hHeap
0x18001308a  call    cs:__imp_HeapFree
0x180013090  jmp     short loc_1800130A0
0x180013092  cmp     byte ptr [rbx+3Ah], 0
0x180013096  jz      short loc_1800130A0
0x180013098  mov     rcx, r14; this
0x18001309b  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800130a0  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800130a4  mov     r9, r13; void *
0x1800130a7  mov     r8, r15; Size
0x1800130aa  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800130af  mov     rdx, rsi; Buf1
0x1800130b2  mov     rcx, rbx; this
0x1800130b5  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800130ba  add     rsp, 58h
0x1800130be  pop     r15
0x1800130c0  pop     r14
0x1800130c2  pop     r13
0x1800130c4  pop     r12
0x1800130c6  pop     rdi
0x1800130c7  pop     rsi
0x1800130c8  pop     rbp
0x1800130c9  pop     rbx
0x1800130ca  retn
0x1800130cb  mov     rcx, [rsp+98h]; this
0x1800130d3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
