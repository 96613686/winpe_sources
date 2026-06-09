# ATL::CComObject<CParseTreeNode>::`vector deleting destructor'(uint)

- ea: `0x180009520`
- end: `0x180009554`
- name: `??_E?$CComObject@VCParseTreeNode@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002594`
- `0x180009178`
- `0x180009520`

## pseudocode

```c
CParseTreeNode *__fastcall ATL::CComObject<CParseTreeNode>::`vector deleting destructor'(CParseTreeNode *a1, char a2)
{
  ATL::CComObject<CParseTreeNode>::~CComObject<CParseTreeNode>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180009520  mov     [rsp+arg_0], rbx
0x180009525  push    rdi
0x180009526  sub     rsp, 20h
0x18000952a  mov     ebx, edx
0x18000952c  mov     rdi, rcx
0x18000952f  call    ??1?$CComObject@VCParseTreeNode@@@ATL@@UEAA@XZ; ATL::CComObject<CParseTreeNode>::~CComObject<CParseTreeNode>(void)
0x180009534  test    bl, 1
0x180009537  jz      short loc_180009546
0x180009539  mov     edx, 68h ; 'h'; unsigned __int64
0x18000953e  mov     rcx, rdi; void *
0x180009541  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009546  mov     rbx, [rsp+28h+arg_0]
0x18000954b  mov     rax, rdi
0x18000954e  add     rsp, 20h
0x180009552  pop     rdi
0x180009553  retn
```
