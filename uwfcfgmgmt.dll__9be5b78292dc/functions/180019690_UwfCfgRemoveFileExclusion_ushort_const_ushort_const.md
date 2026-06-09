# UwfCfgRemoveFileExclusion(ushort const *,ushort const *)

- ea: `0x180019690`
- end: `0x180019729`
- name: `?UwfCfgRemoveFileExclusion@@YAJPEBG0@Z`
- size: `153`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callees

- `0x180008da0`
- `0x18000f364`
- `0x180019690`
- `0x18001aa08`
- `0x18001aa94`
- `0x18001aad4`

## pseudocode

```c
__int64 __fastcall UwfCfgRemoveFileExclusion(unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int v4; // ebx
  CUwfStaticVolumeConfiguration *v6; // [rsp+40h] [rbp+8h] BYREF
  struct CUwfStaticConfiguration *v7; // [rsp+50h] [rbp+18h] BYREF
  CUwfProvider *v8; // [rsp+58h] [rbp+20h] BYREF

  anonymous_namespace_::uwfCfgApiBreakpoint();
  v8 = 0;
  v7 = 0;
  v6 = 0;
  if ( a1 && a2 )
  {
    EnsureUwfFeatureState();
    v4 = anonymous_namespace_::uwfCfgInitialize(1, 0, &v8, &v7, a1, &v6);
    if ( v4 >= 0 )
      v4 = CUwfStaticVolumeConfiguration::RemoveFileExclusion(v6, a2);
  }
  else
  {
    v4 = -2147024809;
  }
  anonymous_namespace_::uwfCfgFinalize(v8, v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180019690  mov     [rsp+arg_8], rbx
0x180019695  push    rdi
0x180019696  sub     rsp, 30h
0x18001969a  mov     rdi, rdx
0x18001969d  mov     rbx, rcx
0x1800196a0  call    _anonymous_namespace___uwfCfgApiBreakpoint
0x1800196a5  mov     [rsp+38h+arg_18], 0
0x1800196ae  mov     [rsp+38h+arg_10], 0
0x1800196b7  mov     [rsp+38h+arg_0], 0
0x1800196c0  test    rbx, rbx
0x1800196c3  jnz     short loc_1800196CC
0x1800196c5  mov     ebx, 80070057h
0x1800196ca  jmp     short loc_18001970D
0x1800196cc  test    rdi, rdi
0x1800196cf  jz      short loc_1800196C5
0x1800196d1  call    ?EnsureUwfFeatureState@@YAJ_N@Z; EnsureUwfFeatureState(bool)
0x1800196d6  lea     rax, [rsp+38h+arg_0]
0x1800196db  xor     edx, edx
0x1800196dd  mov     [rsp+38h+var_10], rax
0x1800196e2  lea     r9, [rsp+38h+arg_10]
0x1800196e7  lea     r8, [rsp+38h+arg_18]
0x1800196ec  mov     [rsp+38h+var_18], rbx
0x1800196f1  mov     cl, 1
0x1800196f3  call    _anonymous_namespace___uwfCfgInitialize
0x1800196f8  mov     ebx, eax
0x1800196fa  test    eax, eax
0x1800196fc  js      short loc_18001970D
0x1800196fe  mov     rcx, [rsp+38h+arg_0]; this
0x180019703  mov     rdx, rdi; unsigned __int16 *
0x180019706  call    ?RemoveFileExclusion@CUwfStaticVolumeConfiguration@@QEAAJPEBG@Z; CUwfStaticVolumeConfiguration::RemoveFileExclusion(ushort const *)
0x18001970b  mov     ebx, eax
0x18001970d  mov     rdx, [rsp+38h+arg_10]
0x180019712  mov     rcx, [rsp+38h+arg_18]
0x180019717  call    _anonymous_namespace___uwfCfgFinalize
0x18001971c  mov     eax, ebx
0x18001971e  mov     rbx, [rsp+38h+arg_8]
0x180019723  add     rsp, 30h
0x180019727  pop     rdi
0x180019728  retn
```
