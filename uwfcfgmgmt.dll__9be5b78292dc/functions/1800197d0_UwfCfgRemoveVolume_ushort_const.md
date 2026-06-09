# UwfCfgRemoveVolume(ushort const *)

- ea: `0x1800197d0`
- end: `0x1800198c2`
- name: `?UwfCfgRemoveVolume@@YAJPEBG@Z`
- size: `242`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x180007420`
- `0x18000ee48`
- `0x18000f364`
- `0x180011130`
- `0x1800197d0`
- `0x18001aa08`
- `0x18001aa94`
- `0x18001aad4`
- `0x18001afe2`
- `0x18001b020`

## pseudocode

```c
__int64 __fastcall UwfCfgRemoveVolume(const unsigned __int16 *a1)
{
  CUwfStaticConfiguration *v2; // rdi
  int Config; // ebx
  __int64 v4; // rcx
  unsigned int v5; // edx
  CUwfStaticConfiguration *v7; // [rsp+30h] [rbp-59h] BYREF
  struct CUwfStaticVolumeConfiguration *v8; // [rsp+38h] [rbp-51h] BYREF
  __int64 v9; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int16 v10[48]; // [rsp+50h] [rbp-39h] BYREF

  anonymous_namespace_::uwfCfgApiBreakpoint();
  v2 = 0;
  v9 = 0;
  v7 = 0;
  v8 = 0;
  memset_0(v10, 0, 0x5Au);
  if ( a1 )
  {
    EnsureUwfFeatureState();
    LOBYTE(v4) = 1;
    Config = anonymous_namespace_::uwfCfgInitialize(v4, 0, &v9, &v7, 0, 0);
    if ( Config < 0 || (Config = ConstructVolumeNameFromVolumeIdentifier(v10, v5, a1), Config < 0) )
    {
      v2 = v7;
    }
    else
    {
      v2 = v7;
      Config = VolumeGetConfig(v7, v10, 0, &v8);
      if ( Config >= 0 )
      {
        if ( v8 )
          Config = CUwfStaticConfiguration::DeleteVolume(v2, *((_DWORD *)v8 + 3));
        else
          Config = -2147467259;
      }
    }
  }
  else
  {
    Config = -2147024809;
  }
  anonymous_namespace_::uwfCfgFinalize(v9, v2);
  return (unsigned int)Config;
}

```

## disassembly

```asm
0x1800197d0  push    rbp
0x1800197d2  push    rbx
0x1800197d3  push    rsi
0x1800197d4  push    rdi
0x1800197d5  lea     rbp, [rsp-3Fh]
0x1800197da  sub     rsp, 0C8h
0x1800197e1  mov     rax, cs:__security_cookie
0x1800197e8  xor     rax, rsp
0x1800197eb  mov     [rbp+57h+var_30], rax
0x1800197ef  mov     rsi, rcx
0x1800197f2  call    _anonymous_namespace___uwfCfgApiBreakpoint
0x1800197f7  xor     edi, edi
0x1800197f9  mov     [rbp+57h+var_A0], 0
0x180019801  xor     edx, edx; Val
0x180019803  mov     [rbp+57h+var_B0], rdi
0x180019807  lea     rcx, [rbp+57h+var_90]; void *
0x18001980b  mov     [rbp+57h+var_A8], rdi
0x18001980f  lea     r8d, [rdi+5Ah]; Size
0x180019813  call    memset_0
0x180019818  test    rsi, rsi
0x18001981b  jnz     short loc_180019824
0x18001981d  mov     ebx, 80070057h
0x180019822  jmp     short loc_18001989C
0x180019824  call    ?EnsureUwfFeatureState@@YAJ_N@Z; EnsureUwfFeatureState(bool)
0x180019829  lea     r9, [rbp+57h+var_B0]
0x18001982d  mov     [rsp+0E0h+var_B8], rdi
0x180019832  lea     r8, [rbp+57h+var_A0]
0x180019836  mov     [rsp+0E0h+var_C0], rdi
0x18001983b  xor     edx, edx
0x18001983d  mov     cl, 1
0x18001983f  call    _anonymous_namespace___uwfCfgInitialize
0x180019844  mov     ebx, eax
0x180019846  test    eax, eax
0x180019848  js      short loc_180019898
0x18001984a  mov     r8, rsi; unsigned __int16 *
0x18001984d  lea     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x180019851  call    ?ConstructVolumeNameFromVolumeIdentifier@@YAJPEAGKPEBG@Z; ConstructVolumeNameFromVolumeIdentifier(ushort *,ulong,ushort const *)
0x180019856  mov     ebx, eax
0x180019858  test    eax, eax
0x18001985a  js      short loc_180019898
0x18001985c  mov     rdi, [rbp+57h+var_B0]
0x180019860  lea     r9, [rbp+57h+var_A8]; struct CUwfStaticVolumeConfiguration **
0x180019864  mov     rcx, rdi; this
0x180019867  lea     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x18001986b  xor     r8d, r8d; unsigned __int16 *
0x18001986e  call    ?VolumeGetConfig@@YAJPEAVCUwfStaticConfiguration@@PEBG1PEAPEAVCUwfStaticVolumeConfiguration@@@Z; VolumeGetConfig(CUwfStaticConfiguration *,ushort const *,ushort const *,CUwfStaticVolumeConfiguration * *)
0x180019873  mov     ebx, eax
0x180019875  test    eax, eax
0x180019877  js      short loc_18001989C
0x180019879  mov     rdx, [rbp+57h+var_A8]
0x18001987d  test    rdx, rdx
0x180019880  jnz     short loc_180019889
0x180019882  mov     ebx, 80004005h
0x180019887  jmp     short loc_18001989C
0x180019889  mov     edx, [rdx+0Ch]; unsigned int
0x18001988c  mov     rcx, rdi; this
0x18001988f  call    ?DeleteVolume@CUwfStaticConfiguration@@QEAAJK@Z; CUwfStaticConfiguration::DeleteVolume(ulong)
0x180019894  mov     ebx, eax
0x180019896  jmp     short loc_18001989C
0x180019898  mov     rdi, [rbp+57h+var_B0]
0x18001989c  mov     rcx, [rbp+57h+var_A0]
0x1800198a0  mov     rdx, rdi
0x1800198a3  call    _anonymous_namespace___uwfCfgFinalize
0x1800198a8  mov     eax, ebx
0x1800198aa  mov     rcx, [rbp+57h+var_30]
0x1800198ae  xor     rcx, rsp; StackCookie
0x1800198b1  call    __security_check_cookie
0x1800198b6  add     rsp, 0C8h
0x1800198bd  pop     rdi
0x1800198be  pop     rsi
0x1800198bf  pop     rbx
0x1800198c0  pop     rbp
0x1800198c1  retn
```
