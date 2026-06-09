# ComTaskMgrWnd::CleanupSet::Remove(ComTaskHost *)

- ea: `0x1400043a0`
- end: `0x140004504`
- name: `?Remove@CleanupSet@ComTaskMgrWnd@@QEAAXPEAVComTaskHost@@@Z`
- size: `356`
- prototype: `void __fastcall(PSRWLOCK SRWLock, struct ComTaskHost *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140009670`

## callees

- `0x1400043a0`
- `0x140004510`
- `0x140004570`
- `0x1400045d0`
- `0x140009370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000449e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400043d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400043d2`

## pseudocode

```c
void __fastcall ComTaskMgrWnd::CleanupSet::Remove(PSRWLOCK SRWLock, struct ComTaskHost *a2)
{
  _QWORD *Ptr; // rdx
  _QWORD *v5; // r8
  _QWORD *v6; // rax
  __int64 v7; // r9
  _QWORD *v8; // rdi
  unsigned __int64 v9; // rcx
  __int64 *v10; // rax
  _QWORD *v11; // r9
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF
  PSRWLOCK v13; // [rsp+50h] [rbp+18h]
  __int64 v14; // [rsp+58h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_70d3f6ab2bd730cad06006a8dcaaa1a7_Traceguids, a2);
  v13 = SRWLock;
  AcquireSRWLockExclusive(SRWLock);
  Ptr = SRWLock[1].Ptr;
  v5 = (_QWORD *)Ptr[1];
  v6 = v5;
  v7 = (__int64)Ptr;
  v8 = Ptr;
  while ( !*((_BYTE *)v6 + 25) )
  {
    v9 = v6[4];
    if ( v9 >= (unsigned __int64)a2 )
    {
      if ( *((_BYTE *)v8 + 25) && (unsigned __int64)a2 < v9 )
        v8 = v6;
      v7 = (__int64)v6;
      v6 = (_QWORD *)*v6;
    }
    else
    {
      v6 = (_QWORD *)v6[2];
    }
  }
  if ( *((_BYTE *)v8 + 25) )
    v10 = (__int64 *)Ptr[1];
  else
    v10 = (__int64 *)*v8;
  while ( !*((_BYTE *)v10 + 25) )
  {
    if ( (unsigned __int64)a2 < v10[4] )
    {
      v8 = v10;
      v10 = (__int64 *)*v10;
    }
    else
    {
      v10 = (__int64 *)v10[2];
    }
  }
  v12 = v7;
  if ( v7 == *Ptr && v8 == Ptr )
  {
    std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Erase(
      (__int64)&SRWLock[1],
      v5);
    *((RTL_SRWLOCK *)SRWLock[1].Ptr + 1) = SRWLock[1];
    *(RTL_SRWLOCK *)SRWLock[1].Ptr = SRWLock[1];
    *((RTL_SRWLOCK *)SRWLock[1].Ptr + 2) = SRWLock[1];
    SRWLock[2].Ptr = 0;
  }
  else
  {
    while ( (_QWORD *)v7 != v8 )
    {
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ComTaskHost *>>,std::_Iterator_base0>::operator++(&v12);
      std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::erase(
        &SRWLock[1].Ptr,
        &v14,
        v11);
      v7 = v12;
    }
  }
  ReleaseSRWLockExclusive(SRWLock);
}

```

## disassembly

```asm
0x1400043a0  mov     [rsp+arg_8], rbx
0x1400043a5  push    rsi
0x1400043a6  push    rdi
0x1400043a7  push    r14
0x1400043a9  sub     rsp, 20h
0x1400043ad  mov     rbx, rdx
0x1400043b0  mov     rsi, rcx
0x1400043b3  lea     rax, WPP_GLOBAL_Control
0x1400043ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400043c1  cmp     rcx, rax
0x1400043c4  jnz     loc_1400044BB
0x1400043ca  mov     [rsp+38h+arg_10], rsi
0x1400043cf  mov     rcx, rsi; SRWLock
0x1400043d2  call    cs:__imp_AcquireSRWLockExclusive
0x1400043d8  nop
0x1400043d9  mov     rdx, [rsi+8]
0x1400043dd  mov     r8, [rdx+8]
0x1400043e1  mov     rax, r8
0x1400043e4  mov     r9, rdx
0x1400043e7  mov     rdi, rdx
0x1400043ea  cmp     byte ptr [r8+19h], 0
0x1400043ef  jnz     short loc_140004404
0x1400043f1  mov     rcx, [rax+20h]
0x1400043f5  cmp     rcx, rbx
0x1400043f8  jnb     short loc_140004451
0x1400043fa  mov     rax, [rax+10h]
0x1400043fe  cmp     byte ptr [rax+19h], 0
0x140004402  jz      short loc_1400043F1
0x140004404  cmp     byte ptr [rdi+19h], 0
0x140004408  jz      loc_1400044F3
0x14000440e  mov     rax, r8
0x140004411  cmp     byte ptr [rax+19h], 0
0x140004415  jz      loc_1400044A5
0x14000441b  mov     [rsp+38h+arg_0], r9
0x140004420  cmp     r9, [rdx]
0x140004423  jnz     short loc_14000442A
0x140004425  cmp     rdi, rdx
0x140004428  jz      short loc_140004463
0x14000442a  cmp     r9, rdi
0x14000442d  jz      short loc_14000448E
0x14000442f  lea     rcx, [rsp+38h+arg_0]
0x140004434  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVComTaskHost@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<ComTaskHost *>>,std::_Iterator_base0>::operator++(void)
0x140004439  mov     r8, r9
0x14000443c  lea     rdx, [rsp+38h+arg_18]
0x140004441  lea     rcx, [rsi+8]
0x140004445  call    ?erase@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVComTaskHost@@@std@@@std@@@2@V32@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<ComTaskHost *>>>)
0x14000444a  mov     r9, [rsp+38h+arg_0]
0x14000444f  jmp     short loc_14000442A
0x140004451  cmp     byte ptr [rdi+19h], 0
0x140004455  jnz     loc_1400044E2
0x14000445b  mov     r9, rax
0x14000445e  mov     rax, [rax]
0x140004461  jmp     short loc_1400043FE
0x140004463  mov     rdx, r8
0x140004466  lea     rcx, [rsi+8]
0x14000446a  call    ?_Erase@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Erase(std::_Tree_node<ComTaskHost *,void *> *)
0x14000446f  mov     rax, [rsi+8]
0x140004473  mov     [rax+8], rax
0x140004477  mov     rax, [rsi+8]
0x14000447b  mov     [rax], rax
0x14000447e  mov     rax, [rsi+8]
0x140004482  mov     [rax+10h], rax
0x140004486  mov     qword ptr [rsi+10h], 0
0x14000448e  mov     rcx, rsi
0x140004491  mov     rbx, [rsp+38h+arg_8]
0x140004496  add     rsp, 20h
0x14000449a  pop     r14
0x14000449c  pop     rdi
0x14000449d  pop     rsi
0x14000449e  jmp     cs:__imp_ReleaseSRWLockExclusive
0x1400044a5  cmp     rbx, [rax+20h]
0x1400044a9  jb      short loc_1400044FB
0x1400044ab  mov     rax, [rax+10h]
0x1400044af  cmp     byte ptr [rax+19h], 0
0x1400044b3  jnz     loc_14000441B
0x1400044b9  jmp     short loc_1400044A5
0x1400044bb  test    byte ptr [rcx+1Ch], 4
0x1400044bf  jz      loc_1400043CA
0x1400044c5  mov     edx, 0Ah
0x1400044ca  mov     r9, rbx
0x1400044cd  lea     r8, WPP_70d3f6ab2bd730cad06006a8dcaaa1a7_Traceguids
0x1400044d4  mov     rcx, [rcx+10h]
0x1400044d8  call    WPP_SF_q
0x1400044dd  jmp     loc_1400043CA
0x1400044e2  cmp     rbx, rcx
0x1400044e5  jnb     loc_14000445B
0x1400044eb  mov     rdi, rax
0x1400044ee  jmp     loc_14000445B
0x1400044f3  mov     rax, [rdi]
0x1400044f6  jmp     loc_140004411
0x1400044fb  mov     rdi, rax
0x1400044fe  mov     rax, [rax]
0x140004501  jmp     short loc_1400044AF
```
