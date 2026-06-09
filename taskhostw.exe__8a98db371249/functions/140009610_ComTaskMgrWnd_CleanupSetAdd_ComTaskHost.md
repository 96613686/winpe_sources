# ComTaskMgrWnd::CleanupSetAdd(ComTaskHost *)

- ea: `0x140009610`
- end: `0x14000965b`
- name: `?CleanupSetAdd@ComTaskMgrWnd@@UEAAXPEAVComTaskHost@@@Z`
- size: `75`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct ComTaskHost *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005340`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009654`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009627`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009627`

## pseudocode

```c
void __fastcall ComTaskMgrWnd::CleanupSetAdd(RTL_SRWLOCK *this, struct ComTaskHost *a2)
{
  __int64 **v2; // rbx
  __int64 v3; // r8
  _BYTE v4[24]; // [rsp+30h] [rbp-18h] BYREF
  struct ComTaskHost *v5; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v6; // [rsp+58h] [rbp+10h]

  v2 = (__int64 **)&this[9];
  v5 = a2;
  v6 = this + 9;
  AcquireSRWLockExclusive(this + 9);
  std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Insert_nohint<ComTaskHost * const &,std::_Nil>(
    v2 + 1,
    (__int64)v4,
    v3,
    (unsigned __int64 *)&v5);
  ReleaseSRWLockExclusive((PSRWLOCK)v2);
}

```

## disassembly

```asm
0x140009610  push    rbx
0x140009612  sub     rsp, 40h
0x140009616  lea     rbx, [rcx+48h]
0x14000961a  mov     [rsp+48h+arg_0], rdx
0x14000961f  mov     [rsp+48h+arg_8], rbx
0x140009624  mov     rcx, rbx; SRWLock
0x140009627  call    cs:__imp_AcquireSRWLockExclusive
0x14000962d  nop
0x14000962e  lea     rcx, [rbx+8]
0x140009632  mov     al, cs:byte_140015A00
0x140009638  mov     [rsp+48h+var_28], al
0x14000963c  lea     r9, [rsp+48h+arg_0]
0x140009641  lea     rdx, [rsp+48h+var_18]
0x140009646  call    ??$_Insert_nohint@AEBQEAVComTaskHost@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVComTaskHost@@@std@@@std@@@std@@_N@1@_NAEBQEAVComTaskHost@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::_Insert_nohint<ComTaskHost * const &,std::_Nil>(bool,ComTaskHost * const &,std::_Nil)
0x14000964b  nop
0x14000964c  mov     rcx, rbx
0x14000964f  add     rsp, 40h
0x140009653  pop     rbx
0x140009654  jmp     cs:__imp_ReleaseSRWLockExclusive
```
