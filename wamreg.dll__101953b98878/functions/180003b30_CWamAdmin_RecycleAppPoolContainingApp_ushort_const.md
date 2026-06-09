# CWamAdmin::RecycleAppPoolContainingApp(ushort const *)

- ea: `0x180003b30`
- end: `0x180003b8a`
- name: `?RecycleAppPoolContainingApp@CWamAdmin@@AEAAJPEBG@Z`
- size: `90`
- prototype: `__int64 __fastcall(CWamAdmin *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180002460`

## callees

- `0x180001084`
- `0x180003b30`
- `0x180005f74`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall CWamAdmin::RecycleAppPoolContainingApp(CWamAdmin *this, const unsigned __int16 *a2)
{
  int v3; // ebx
  void *Block; // [rsp+40h] [rbp+18h] BYREF

  Block = 0;
  v3 = WamRegMetabaseConfig::MDGetStringAttribute(this, a2, 9101, (unsigned __int16 **)&Block);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(char *, void *))(*((_QWORD *)this + 2) + 64LL))((char *)this + 16, Block);
    operator delete(Block);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003b30  mov     [rsp+arg_0], rbx
0x180003b35  push    rdi
0x180003b36  sub     rsp, 20h
0x180003b3a  lea     r9, [rsp+28h+Block]; unsigned __int16 **
0x180003b3f  mov     [rsp+28h+Block], 0
0x180003b48  mov     r8d, 238Dh; unsigned int
0x180003b4e  mov     rdi, rcx
0x180003b51  call    ?MDGetStringAttribute@WamRegMetabaseConfig@@QEAAJPEBGKPEAPEAG@Z; WamRegMetabaseConfig::MDGetStringAttribute(ushort const *,ulong,ushort * *)
0x180003b56  mov     ebx, eax
0x180003b58  test    eax, eax
0x180003b5a  js      short loc_180003B7D
0x180003b5c  mov     rdx, [rsp+28h+Block]
0x180003b61  lea     rcx, [rdi+10h]
0x180003b65  mov     rax, [rcx]
0x180003b68  mov     rax, [rax+40h]
0x180003b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b71  mov     rcx, [rsp+28h+Block]; Block
0x180003b76  mov     ebx, eax
0x180003b78  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003b7d  mov     eax, ebx
0x180003b7f  mov     rbx, [rsp+28h+arg_0]
0x180003b84  add     rsp, 20h
0x180003b88  pop     rdi
0x180003b89  retn
```
