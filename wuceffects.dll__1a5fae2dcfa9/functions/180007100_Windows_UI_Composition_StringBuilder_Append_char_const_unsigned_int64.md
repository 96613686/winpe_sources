# Windows::UI::Composition::StringBuilder::Append(char const *,unsigned __int64)

- ea: `0x180007100`
- end: `0x18000738c`
- name: `?Append@StringBuilder@Composition@UI@Windows@@QEAAXPEBD_K@Z`
- size: `652`
- prototype: `void __fastcall(Windows::UI::Composition::StringBuilder *__hidden this, const char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006960`
- `0x180006e1c`

## callees

- `0x180006410`
- `0x180007100`
- `0x180007bc0`
- `0x180028b20`
- `0x18002b8b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800071ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800071ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071da`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::UI::Composition::StringBuilder::Append(
        Windows::UI::Composition::StringBuilder *this,
        const char *a2,
        __int64 a3)
{
  const char *v3; // r14
  const char *v5; // r12
  unsigned __int64 v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned __int64 v9; // rdi
  __int64 v10; // r15
  HANDLE ProcessHeap; // rax
  LPVOID v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  const char *v16; // rsi
  unsigned __int64 v17; // r15
  __int64 v18; // r13
  unsigned __int64 v19; // rax
  const char *v20; // r14
  const char *v21; // rdi
  void **pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  const char *v23; // [rsp+28h] [rbp-30h]
  __int64 v24; // [rsp+30h] [rbp-28h]
  Windows::UI::Composition::StringBuilder *v25; // [rsp+40h] [rbp-18h] BYREF
  const char *v26; // [rsp+48h] [rbp-10h]

  v3 = a2;
  v5 = &a2[a3];
  if ( a2 != &a2[a3] )
  {
    v6 = *((_QWORD *)this + 4);
    v25 = this;
    v26 = (const char *)v6;
    if ( v6 <= v6 >> 1 )
    {
      v13 = v6;
      do
      {
        --v5;
        if ( (*((_BYTE *)this + 24) & 0xF) == 0 && *((_QWORD *)this + 2) <= (unsigned __int64)(v13 + 16) >> 4 )
          std::deque<char>::_Growmap(this);
        v14 = *((_QWORD *)this + 2);
        v15 = *((_QWORD *)this + 3) & (16 * v14 - 1);
        *((_QWORD *)this + 3) = v15;
        if ( !v15 )
          v15 = 16 * v14;
        v16 = (const char *)(v15 - 1);
        v17 = (unsigned __int64)(v15 - 1) >> 4;
        v18 = 8 * (v17 & (v14 - 1));
        if ( !*(_QWORD *)(*((_QWORD *)this + 1) + v18) )
          *(_QWORD *)(*((_QWORD *)this + 1) + v18) = operator new(0x10u);
        *(_BYTE *)(((unsigned __int8)v16 & 0xF)
                 + *(_QWORD *)(*((_QWORD *)this + 1) + 8 * (v17 & (*((_QWORD *)this + 2) - 1LL)))) = *v5;
        *((_QWORD *)this + 3) = v16;
        v13 = *((_QWORD *)this + 4) + 1LL;
        *((_QWORD *)this + 4) = v13;
      }
      while ( v5 != v3 );
      v19 = v13 - v6;
      v20 = &v16[v19];
      if ( v16 != &v16[v19] )
      {
        v21 = &v20[v6];
        if ( v20 != v21 )
        {
          pExceptionObject = (void **)this;
          v23 = &v16[v19];
          v25 = this;
          v26 = v16;
          std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(
            &v25,
            &pExceptionObject);
          v25 = this;
          v26 = v21;
          pExceptionObject = (void **)this;
          v23 = v20;
          std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(
            &pExceptionObject,
            &v25);
          v25 = this;
          v26 = v21;
          pExceptionObject = (void **)this;
          v23 = v16;
          std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(
            &pExceptionObject,
            &v25);
        }
      }
    }
    else
    {
      do
      {
        if ( ((*((_BYTE *)this + 24) + (_BYTE)v6) & 0xF) == 0 && *((_QWORD *)this + 2) <= (v6 + 16) >> 4 )
          std::deque<char>::_Growmap(this);
        v7 = *((_QWORD *)this + 2);
        v8 = *((_QWORD *)this + 3) & (16 * v7 - 1);
        *((_QWORD *)this + 3) = v8;
        v9 = v8 + *((_QWORD *)this + 4);
        v10 = 8 * ((v9 >> 4) & (v7 - 1));
        if ( !*(_QWORD *)(v10 + *((_QWORD *)this + 1)) )
        {
          ProcessHeap = GetProcessHeap();
          v12 = HeapAlloc(ProcessHeap, 0, 0x10u);
          if ( !v12 )
          {
            v24 = 0;
            v23 = "bad allocation";
            pExceptionObject = &std::bad_alloc::`vftable';
            throw (std::bad_alloc *)&pExceptionObject;
          }
          *(_QWORD *)(v10 + *((_QWORD *)this + 1)) = v12;
        }
        *(_BYTE *)((v9 & 0xF) + *(_QWORD *)(*((_QWORD *)this + 1) + 8 * ((v9 >> 4) & (*((_QWORD *)this + 2) - 1LL)))) = *v3;
        v6 = ++*((_QWORD *)this + 4);
        ++v3;
      }
      while ( v3 != v5 );
    }
  }
}

```

## disassembly

```asm
0x180007100  push    rbp
0x180007102  push    rbx
0x180007103  push    rsi
0x180007104  push    rdi
0x180007105  push    r12
0x180007107  push    r13
0x180007109  push    r14
0x18000710b  push    r15
0x18000710d  mov     rbp, rsp
0x180007110  sub     rsp, 58h
0x180007114  mov     r14, rdx
0x180007117  mov     rbx, rcx
0x18000711a  lea     r12, [rdx+r8]
0x18000711e  cmp     rdx, r12
0x180007121  jz      loc_1800071C9
0x180007127  mov     rdi, [rcx+20h]
0x18000712b  mov     rax, rdi
0x18000712e  shr     rax, 1
0x180007131  mov     [rbp+var_18], rcx
0x180007135  mov     [rbp+var_10], rdi
0x180007139  cmp     rdi, rax
0x18000713c  jbe     loc_180007205
0x180007142  nop     dword ptr [rax+00h]
0x180007146  nop     word ptr [rax+rax+00000000h]
0x180007150  movzx   eax, dil
0x180007154  add     al, [rbx+18h]
0x180007157  test    al, 0Fh
0x180007159  jz      loc_180007309
0x18000715f  mov     rdx, [rbx+10h]
0x180007163  mov     rcx, rdx
0x180007166  shl     rcx, 4
0x18000716a  dec     rcx
0x18000716d  and     rcx, [rbx+18h]
0x180007171  mov     [rbx+18h], rcx
0x180007175  mov     rdi, [rbx+20h]
0x180007179  add     rdi, rcx
0x18000717c  mov     rsi, rdi
0x18000717f  shr     rsi, 4
0x180007183  lea     rax, [rdx-1]
0x180007187  and     rax, rsi
0x18000718a  lea     r15, ds:0[rax*8]
0x180007192  mov     rax, [rbx+8]
0x180007196  cmp     qword ptr [r15+rax], 0
0x18000719b  jz      short loc_1800071DA
0x18000719d  mov     rax, [rbx+10h]
0x1800071a1  dec     rax
0x1800071a4  and     rax, rsi
0x1800071a7  mov     rcx, [rbx+8]
0x1800071ab  and     edi, 0Fh
0x1800071ae  mov     rcx, [rcx+rax*8]
0x1800071b2  movzx   eax, byte ptr [r14]
0x1800071b6  mov     [rdi+rcx], al
0x1800071b9  inc     qword ptr [rbx+20h]
0x1800071bd  mov     rdi, [rbx+20h]
0x1800071c1  inc     r14
0x1800071c4  cmp     r14, r12
0x1800071c7  jnz     short loc_180007150
0x1800071c9  add     rsp, 58h
0x1800071cd  pop     r15
0x1800071cf  pop     r14
0x1800071d1  pop     r13
0x1800071d3  pop     r12
0x1800071d5  pop     rdi
0x1800071d6  pop     rsi
0x1800071d7  pop     rbx
0x1800071d8  pop     rbp
0x1800071d9  retn
0x1800071da  call    cs:__imp_GetProcessHeap
0x1800071e0  nop
0x1800071e1  mov     rcx, rax; hHeap
0x1800071e4  xor     edx, edx; dwFlags
0x1800071e6  mov     r8d, 10h; dwBytes
0x1800071ec  call    cs:__imp_HeapAlloc
0x1800071f2  test    rax, rax
0x1800071f5  jz      loc_18000735E
0x1800071fb  mov     rcx, [rbx+8]
0x1800071ff  mov     [r15+rcx], rax
0x180007203  jmp     short loc_18000719D
0x180007205  mov     rax, rdi
0x180007208  dec     r12
0x18000720b  test    byte ptr [rbx+18h], 0Fh
0x18000720f  jz      loc_180007328
0x180007215  mov     rdx, [rbx+10h]
0x180007219  mov     rcx, rdx
0x18000721c  shl     rcx, 4
0x180007220  lea     rax, [rcx-1]
0x180007224  and     rax, [rbx+18h]
0x180007228  mov     [rbx+18h], rax
0x18000722c  cmovz   rax, rcx
0x180007230  lea     rsi, [rax-1]
0x180007234  mov     r15, rsi
0x180007237  shr     r15, 4
0x18000723b  lea     rax, [rdx-1]
0x18000723f  and     rax, r15
0x180007242  lea     r13, ds:0[rax*8]
0x18000724a  mov     rax, [rbx+8]
0x18000724e  cmp     qword ptr [rax+r13], 0
0x180007253  jz      loc_180007347
0x180007259  mov     rax, [rbx+10h]
0x18000725d  dec     rax
0x180007260  and     rax, r15
0x180007263  mov     rcx, [rbx+8]
0x180007267  mov     rdx, rsi
0x18000726a  and     edx, 0Fh
0x18000726d  mov     rcx, [rcx+rax*8]
0x180007271  movzx   eax, byte ptr [r12]
0x180007276  mov     [rdx+rcx], al
0x180007279  mov     [rbx+18h], rsi
0x18000727d  mov     rax, [rbx+20h]
0x180007281  inc     rax
0x180007284  mov     [rbx+20h], rax
0x180007288  cmp     r12, r14
0x18000728b  jnz     loc_180007208
0x180007291  sub     rax, rdi
0x180007294  lea     r14, [rax+rsi]
0x180007298  cmp     rsi, r14
0x18000729b  jz      loc_1800071C9
0x1800072a1  add     rdi, r14
0x1800072a4  cmp     r14, rdi
0x1800072a7  jz      loc_1800071C9
0x1800072ad  mov     [rbp+pExceptionObject], rbx
0x1800072b1  mov     qword ptr [rbp+var_30], r14
0x1800072b5  mov     [rbp+var_18], rbx
0x1800072b9  mov     [rbp+var_10], rsi
0x1800072bd  lea     rdx, [rbp+pExceptionObject]
0x1800072c1  lea     rcx, [rbp+var_18]
0x1800072c5  call    ??$reverse@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@std@@@std@@YAXV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@0@0@Z; std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>)
0x1800072ca  mov     [rbp+var_18], rbx
0x1800072ce  mov     [rbp+var_10], rdi
0x1800072d2  mov     [rbp+pExceptionObject], rbx
0x1800072d6  mov     qword ptr [rbp+var_30], r14
0x1800072da  lea     rdx, [rbp+var_18]
0x1800072de  lea     rcx, [rbp+pExceptionObject]
0x1800072e2  call    ??$reverse@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@std@@@std@@YAXV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@0@0@Z; std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>)
0x1800072e7  mov     [rbp+var_18], rbx
0x1800072eb  mov     [rbp+var_10], rdi
0x1800072ef  mov     [rbp+pExceptionObject], rbx
0x1800072f3  mov     qword ptr [rbp+var_30], rsi
0x1800072f7  lea     rdx, [rbp+var_18]
0x1800072fb  lea     rcx, [rbp+pExceptionObject]
0x1800072ff  call    ??$reverse@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@std@@@std@@YAXV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@D@std@@@std@@@0@0@Z; std::reverse<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>>(std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<char>>>)
0x180007304  jmp     loc_1800071C9
0x180007309  lea     rax, [rdi+10h]
0x18000730d  shr     rax, 4
0x180007311  cmp     [rbx+10h], rax
0x180007315  ja      loc_18000715F
0x18000731b  mov     rcx, rbx
0x18000731e  call    ?_Growmap@?$deque@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::deque<char>::_Growmap(unsigned __int64)
0x180007323  jmp     loc_18000715F
0x180007328  add     rax, 10h
0x18000732c  shr     rax, 4
0x180007330  cmp     [rbx+10h], rax
0x180007334  ja      loc_180007215
0x18000733a  mov     rcx, rbx
0x18000733d  call    ?_Growmap@?$deque@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::deque<char>::_Growmap(unsigned __int64)
0x180007342  jmp     loc_180007215
0x180007347  mov     ecx, 10h; dwBytes
0x18000734c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007351  mov     rcx, [rbx+8]
0x180007355  mov     [rcx+r13], rax
0x180007359  jmp     loc_180007259
0x18000735e  xorps   xmm0, xmm0
0x180007361  movups  [rbp+var_30], xmm0
0x180007365  lea     rax, aBadAllocation; "bad allocation"
0x18000736c  mov     qword ptr [rbp+var_30], rax
0x180007370  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180007377  mov     [rbp+pExceptionObject], rax
0x18000737b  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180007382  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180007386  call    _CxxThrowException_0
```
