# ATL::CAtlComModule::ExecuteObjectMain(bool)

- ea: `0x180004168`
- end: `0x1800041b4`
- name: `?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z`
- size: `76`
- prototype: `void __fastcall(ATL::CAtlComModule *this, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800020c0`
- `0x1800036ac`

## callees

- `0x180004168`
- `0x180012010`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::ExecuteObjectMain(ATL::CAtlComModule *this, char a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v4; // rax

  v2 = off_1800200F0;
  v4 = off_1800200F8;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v4 )
  {
    if ( *v2 )
    {
      LOBYTE(this) = a2;
      (*((void (__fastcall **)(ATL::CAtlComModule *))*v2 + 8))(this);
      v4 = off_1800200F8;
    }
    ++v2;
  }
}

```

## disassembly

```asm
0x180004168  mov     [rsp+arg_0], rbx
0x18000416d  push    rdi
0x18000416e  sub     rsp, 20h
0x180004172  mov     rbx, cs:off_1800200F0
0x180004179  mov     dil, dl
0x18000417c  mov     rax, cs:off_1800200F8
0x180004183  jmp     short loc_1800041A4
0x180004185  mov     r8, [rbx]
0x180004188  test    r8, r8
0x18000418b  jz      short loc_1800041A0
0x18000418d  mov     rax, [r8+40h]
0x180004191  mov     cl, dil
0x180004194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004199  mov     rax, cs:off_1800200F8
0x1800041a0  add     rbx, 8
0x1800041a4  cmp     rbx, rax
0x1800041a7  jb      short loc_180004185
0x1800041a9  mov     rbx, [rsp+28h+arg_0]
0x1800041ae  add     rsp, 20h
0x1800041b2  pop     rdi
0x1800041b3  retn
```
