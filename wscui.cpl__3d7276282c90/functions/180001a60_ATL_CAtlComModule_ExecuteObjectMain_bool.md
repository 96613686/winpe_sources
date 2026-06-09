# ATL::CAtlComModule::ExecuteObjectMain(bool)

- ea: `0x180001a60`
- end: `0x180001ab0`
- name: `?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z`
- size: `80`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this, bool)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001550`
- `0x1800019c0`
- `0x18000b050`

## callees

- `0x180001a60`
- `0x18000c010`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::ExecuteObjectMain(ATL::CAtlComModule *this, unsigned __int8 a2)
{
  unsigned __int64 v2; // rbx
  unsigned __int64 i; // rax

  v2 = qword_180014AC0;
  for ( i = qword_180014AC8; v2 < i; v2 += 8LL )
  {
    if ( *(_QWORD *)v2 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v2 + 64LL))(a2);
      i = qword_180014AC8;
    }
  }
}

```

## disassembly

```asm
0x180001a60  mov     [rsp+arg_0], rbx
0x180001a65  push    rdi
0x180001a66  sub     rsp, 20h
0x180001a6a  mov     rbx, cs:qword_180014AC0
0x180001a71  movzx   edi, dl
0x180001a74  mov     rax, cs:qword_180014AC8
0x180001a7b  cmp     rbx, rax
0x180001a7e  jnb     short loc_180001AA5
0x180001a80  mov     rdx, [rbx]
0x180001a83  test    rdx, rdx
0x180001a86  jz      short loc_180001A9C
0x180001a88  mov     rax, [rdx+40h]
0x180001a8c  movzx   ecx, dil
0x180001a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a95  mov     rax, cs:qword_180014AC8
0x180001a9c  add     rbx, 8
0x180001aa0  cmp     rbx, rax
0x180001aa3  jb      short loc_180001A80
0x180001aa5  mov     rbx, [rsp+28h+arg_0]
0x180001aaa  add     rsp, 20h
0x180001aae  pop     rdi
0x180001aaf  retn
```
