# UwfCfgRemoveRegExclusion(ushort const *)

- ea: `0x180019730`
- end: `0x1800197bc`
- name: `?UwfCfgRemoveRegExclusion@@YAJPEBG@Z`
- size: `140`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180008f60`
- `0x18000f364`
- `0x180019730`
- `0x18001aa08`
- `0x18001aa94`
- `0x18001aad4`

## pseudocode

```c
__int64 __fastcall UwfCfgRemoveRegExclusion(const unsigned __int16 *a1)
{
  CUwfStaticConfiguration *v2; // rbx
  unsigned int v3; // edi
  int v4; // eax
  CUwfStaticConfiguration *v6; // [rsp+40h] [rbp+8h] BYREF
  CUwfProvider *v7; // [rsp+48h] [rbp+10h] BYREF

  anonymous_namespace_::uwfCfgApiBreakpoint();
  v2 = 0;
  v7 = 0;
  v6 = 0;
  if ( a1 )
  {
    EnsureUwfFeatureState();
    v4 = anonymous_namespace_::uwfCfgInitialize(1, 0, &v7, &v6, 0, 0);
    v2 = v6;
    v3 = v4;
    if ( v4 >= 0 )
      v3 = CUwfStaticConfiguration::RemoveRegKeyExclusion(v6, a1);
  }
  else
  {
    v3 = -2147024809;
  }
  anonymous_namespace_::uwfCfgFinalize(v7, v2);
  return v3;
}

```

## disassembly

```asm
0x180019730  mov     [rsp+arg_10], rbx
0x180019735  mov     [rsp+arg_18], rsi
0x18001973a  push    rdi
0x18001973b  sub     rsp, 30h
0x18001973f  mov     rsi, rcx
0x180019742  call    _anonymous_namespace___uwfCfgApiBreakpoint
0x180019747  xor     ebx, ebx
0x180019749  mov     [rsp+38h+arg_8], 0
0x180019752  mov     [rsp+38h+arg_0], rbx
0x180019757  test    rsi, rsi
0x18001975a  jnz     short loc_180019763
0x18001975c  mov     edi, 80070057h
0x180019761  jmp     short loc_18001979D
0x180019763  call    ?EnsureUwfFeatureState@@YAJ_N@Z; EnsureUwfFeatureState(bool)
0x180019768  lea     r9, [rsp+38h+arg_0]
0x18001976d  mov     [rsp+38h+var_10], rbx
0x180019772  lea     r8, [rsp+38h+arg_8]
0x180019777  mov     [rsp+38h+var_18], rbx
0x18001977c  xor     edx, edx
0x18001977e  mov     cl, 1
0x180019780  call    _anonymous_namespace___uwfCfgInitialize
0x180019785  mov     rbx, [rsp+38h+arg_0]
0x18001978a  mov     edi, eax
0x18001978c  test    eax, eax
0x18001978e  js      short loc_18001979D
0x180019790  mov     rdx, rsi; unsigned __int16 *
0x180019793  mov     rcx, rbx; this
0x180019796  call    ?RemoveRegKeyExclusion@CUwfStaticConfiguration@@QEAAJPEBG@Z; CUwfStaticConfiguration::RemoveRegKeyExclusion(ushort const *)
0x18001979b  mov     edi, eax
0x18001979d  mov     rcx, [rsp+38h+arg_8]
0x1800197a2  mov     rdx, rbx
0x1800197a5  call    _anonymous_namespace___uwfCfgFinalize
0x1800197aa  mov     rbx, [rsp+38h+arg_10]
0x1800197af  mov     eax, edi
0x1800197b1  mov     rsi, [rsp+38h+arg_18]
0x1800197b6  add     rsp, 30h
0x1800197ba  pop     rdi
0x1800197bb  retn
```
