# CTnMultiResNode::AddChild(CTnMultiResNode *)

- ea: `0x180009848`
- end: `0x180009872`
- name: `?AddChild@CTnMultiResNode@@QEAAXPEAV1@@Z`
- size: `42`
- prototype: `void __fastcall(CTnMultiResNode *__hidden this, struct CTnMultiResNode *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180009930`
- `0x18000a14c`
- `0x18000a298`
- `0x18000aad0`
- `0x18000d1c0`

## callees

- `0x180009848`
- `0x180009c04`

## pseudocode

```c
void __fastcall CTnMultiResNode::AddChild(CTnMultiResNode *this, struct CTnMultiResNode *a2)
{
  __int64 *v2; // rcx
  __int64 i; // rax

  if ( a2 )
  {
    v2 = (__int64 *)((char *)this + 72);
    for ( i = *v2; i; i = *(_QWORD *)i )
    {
      if ( *(struct CTnMultiResNode **)(i + 16) == a2 )
        return;
    }
    CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::AddTail(v2, (__int64)a2);
  }
}

```

## disassembly

```asm
0x180009848  sub     rsp, 28h
0x18000984c  test    rdx, rdx
0x18000984f  jz      short loc_18000986D
0x180009851  add     rcx, 48h ; 'H'
0x180009855  mov     rax, [rcx]
0x180009858  jmp     short loc_180009863
0x18000985a  cmp     [rax+10h], rdx
0x18000985e  jz      short loc_18000986D
0x180009860  mov     rax, [rax]
0x180009863  test    rax, rax
0x180009866  jnz     short loc_18000985A
0x180009868  call    ?AddTail@?$CSPList@PEAUSStrCost@CTnMultiResStringPackage@@PEAU12@@@QEAAPEAXPEAUSStrCost@CTnMultiResStringPackage@@@Z; CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::AddTail(CTnMultiResStringPackage::SStrCost *)
0x18000986d  add     rsp, 28h
0x180009871  retn
```
