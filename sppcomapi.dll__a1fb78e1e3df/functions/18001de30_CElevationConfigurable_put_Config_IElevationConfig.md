# CElevationConfigurable::put_Config(IElevationConfig *)

- ea: `0x18001de30`
- end: `0x18001de8a`
- name: `?put_Config@CElevationConfigurable@@UEAAJPEAUIElevationConfig@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(CElevationConfigurable *__hidden this, struct IElevationConfig *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180004288`
- `0x18001de30`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CElevationConfigurable::put_Config(CElevationConfigurable *this, struct IElevationConfig *a2)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 1) = 0;
  }
  if ( a2 )
  {
    *((_QWORD *)this + 1) = a2;
    (*(void (__fastcall **)(struct IElevationConfig *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  return 0;
}

```

## disassembly

```asm
0x18001de30  mov     [rsp+arg_0], rbx
0x18001de35  push    rdi
0x18001de36  sub     rsp, 20h
0x18001de3a  mov     rdi, rcx
0x18001de3d  mov     rbx, rdx
0x18001de40  mov     rcx, [rcx+8]
0x18001de44  test    rcx, rcx
0x18001de47  jz      short loc_18001DE5D
0x18001de49  mov     rax, [rcx]
0x18001de4c  mov     rax, [rax+10h]
0x18001de50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de55  mov     qword ptr [rdi+8], 0
0x18001de5d  test    rbx, rbx
0x18001de60  jz      short loc_18001DE75
0x18001de62  mov     [rdi+8], rbx
0x18001de66  mov     rcx, rbx
0x18001de69  mov     rax, [rbx]
0x18001de6c  mov     rax, [rax+8]
0x18001de70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de75  xor     ecx, ecx
0x18001de77  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001de7c  mov     rbx, [rsp+28h+arg_0]
0x18001de81  xor     eax, eax
0x18001de83  add     rsp, 20h
0x18001de87  pop     rdi
0x18001de88  retn
```
