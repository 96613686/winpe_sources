# ATL::CAtlComModule::ExecuteObjectMain(bool)

- ea: `0x18001be38`
- end: `0x18001be84`
- name: `?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z`
- size: `76`
- prototype: `void __fastcall(ATL::CAtlComModule *this, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001890`
- `0x18001b144`

## callees

- `0x18001be38`
- `0x180037010`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::ExecuteObjectMain(ATL::CAtlComModule *this, char a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v4; // rax

  v2 = off_1800480F0;
  v4 = off_1800480F8;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v4 )
  {
    if ( *v2 )
    {
      LOBYTE(this) = a2;
      (*((void (__fastcall **)(ATL::CAtlComModule *))*v2 + 8))(this);
      v4 = off_1800480F8;
    }
    ++v2;
  }
}

```

## disassembly

```asm
0x18001be38  mov     [rsp+arg_0], rbx
0x18001be3d  push    rdi
0x18001be3e  sub     rsp, 20h
0x18001be42  mov     rbx, cs:off_1800480F0
0x18001be49  mov     dil, dl
0x18001be4c  mov     rax, cs:off_1800480F8
0x18001be53  jmp     short loc_18001BE74
0x18001be55  mov     r8, [rbx]
0x18001be58  test    r8, r8
0x18001be5b  jz      short loc_18001BE70
0x18001be5d  mov     rax, [r8+40h]
0x18001be61  mov     cl, dil
0x18001be64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be69  mov     rax, cs:off_1800480F8
0x18001be70  add     rbx, 8
0x18001be74  cmp     rbx, rax
0x18001be77  jb      short loc_18001BE55
0x18001be79  mov     rbx, [rsp+28h+arg_0]
0x18001be7e  add     rsp, 20h
0x18001be82  pop     rdi
0x18001be83  retn
```
