# ClearList<std::set<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>>>(std::set<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>> &)

- ea: `0x1400042d4`
- end: `0x140004355`
- name: `??$ClearList@V?$set@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@@std@@@@YAXAEAV?$set@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@@std@@@Z`
- size: `129`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400042a0`

## callees

- `0x1400042d4`
- `0x140004360`
- `0x14000733c`
- `0x14000c010`

## pseudocode

```c
void __fastcall ClearList<std::set<ComTaskHost *>>(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 i; // rax

  if ( *(_QWORD *)(a1 + 8) )
  {
    v2 = **(_QWORD **)a1;
    while ( v2 != *(_QWORD *)a1 )
    {
      v3 = *(_QWORD *)(v2 + 32);
      if ( v3 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 40LL))(v3, 1);
      if ( !*(_BYTE *)(v2 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)(v2 + 16) + 25LL) )
        {
          for ( i = *(_QWORD *)(v2 + 8); !*(_BYTE *)(i + 25) && v2 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
            v2 = i;
        }
        else
        {
          i = std::_Tree_val<std::_Tree_simple_types<ComTaskHost *>>::_Min();
        }
        v2 = i;
      }
    }
    std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::clear(a1);
  }
}

```

## disassembly

```asm
0x1400042d4  mov     [rsp+arg_0], rbx
0x1400042d9  push    rdi
0x1400042da  sub     rsp, 20h
0x1400042de  cmp     qword ptr [rcx+8], 0
0x1400042e3  mov     rdi, rcx
0x1400042e6  jz      short loc_14000434A
0x1400042e8  mov     rbx, [rcx]
0x1400042eb  mov     rbx, [rbx]
0x1400042ee  cmp     rbx, [rdi]
0x1400042f1  jz      short loc_140004342
0x1400042f3  mov     rcx, [rbx+20h]
0x1400042f7  test    rcx, rcx
0x1400042fa  jz      short loc_14000430D
0x1400042fc  mov     rax, [rcx]
0x1400042ff  mov     edx, 1
0x140004304  mov     rax, [rax+28h]
0x140004308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000430d  cmp     byte ptr [rbx+19h], 0
0x140004311  jnz     short loc_1400042EE
0x140004313  mov     rcx, [rbx+10h]
0x140004317  cmp     byte ptr [rcx+19h], 0
0x14000431b  jnz     short loc_140004324
0x14000431d  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@PEAVComTaskHost@@@std@@@std@@SAPEAU?$_Tree_node@PEAVComTaskHost@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<ComTaskHost *>>::_Min(std::_Tree_node<ComTaskHost *,void *> *)
0x140004322  jmp     short loc_14000433D
0x140004324  mov     rax, [rbx+8]
0x140004328  jmp     short loc_140004337
0x14000432a  cmp     rbx, [rax+10h]
0x14000432e  jnz     short loc_14000433D
0x140004330  mov     rbx, rax
0x140004333  mov     rax, [rax+8]
0x140004337  cmp     byte ptr [rax+19h], 0
0x14000433b  jz      short loc_14000432A
0x14000433d  mov     rbx, rax
0x140004340  jmp     short loc_1400042EE
0x140004342  mov     rcx, rdi
0x140004345  call    ?clear@?$_Tree@V?$_Tset_traits@PEAVComTaskHost@@U?$less@PEAVComTaskHost@@@std@@V?$allocator@PEAVComTaskHost@@@3@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<ComTaskHost *,std::less<ComTaskHost *>,std::allocator<ComTaskHost *>,0>>::clear(void)
0x14000434a  mov     rbx, [rsp+28h+arg_0]
0x14000434f  add     rsp, 20h
0x140004353  pop     rdi
0x140004354  retn
```
