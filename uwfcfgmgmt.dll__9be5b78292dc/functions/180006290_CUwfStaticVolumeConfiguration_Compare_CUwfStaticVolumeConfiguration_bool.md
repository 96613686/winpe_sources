# CUwfStaticVolumeConfiguration::Compare(CUwfStaticVolumeConfiguration &,bool *)

- ea: `0x180006290`
- end: `0x180006306`
- name: `?Compare@CUwfStaticVolumeConfiguration@@QEAAJAEAV1@PEA_N@Z`
- size: `118`
- prototype: `__int64 __fastcall(CUwfStaticVolumeConfiguration *__hidden this, struct CUwfStaticVolumeConfiguration *, bool *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006290`
- `0x18000630c`
- `0x18000658c`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::Compare(
        CUwfStaticVolumeConfiguration *this,
        struct CUwfStaticVolumeConfiguration *a2,
        bool *a3)
{
  int v6; // ecx
  bool v7; // al
  bool v9; // [rsp+30h] [rbp+8h] BYREF
  bool v10; // [rsp+38h] [rbp+10h] BYREF

  v9 = 0;
  v10 = 0;
  if ( this == a2 )
  {
    v6 = 0;
  }
  else
  {
    v6 = CUwfStaticVolumeConfiguration::CompareEssentialValues(this, a2, &v9);
    if ( v6 < 0 || (v6 = CUwfStaticVolumeConfiguration::CompareOptionalValues(this, a2, &v10), v6 < 0) || !v9 || !v10 )
    {
      v7 = 0;
      goto LABEL_9;
    }
  }
  v7 = 1;
LABEL_9:
  *a3 = v7;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006290  mov     rax, rsp
0x180006293  mov     [rax+18h], rbx
0x180006297  mov     [rax+20h], rsi
0x18000629b  push    rdi
0x18000629c  sub     rsp, 20h
0x1800062a0  mov     byte ptr [rax+8], 0
0x1800062a4  mov     rbx, r8
0x1800062a7  mov     byte ptr [rax+10h], 0
0x1800062ab  mov     rdi, rdx
0x1800062ae  mov     rsi, rcx
0x1800062b1  cmp     rcx, rdx
0x1800062b4  jnz     short loc_1800062BC
0x1800062b6  xor     ecx, ecx; this
0x1800062b8  mov     al, 1
0x1800062ba  jmp     short loc_1800062F2
0x1800062bc  lea     r8, [rsp+28h+arg_0]; bool *
0x1800062c1  call    ?CompareEssentialValues@CUwfStaticVolumeConfiguration@@AEAAJAEAV1@PEA_N@Z; CUwfStaticVolumeConfiguration::CompareEssentialValues(CUwfStaticVolumeConfiguration &,bool *)
0x1800062c6  mov     ecx, eax
0x1800062c8  test    eax, eax
0x1800062ca  js      short loc_1800062F0
0x1800062cc  lea     r8, [rsp+28h+arg_8]; bool *
0x1800062d1  mov     rdx, rdi; struct CUwfStaticVolumeConfiguration *
0x1800062d4  mov     rcx, rsi; this
0x1800062d7  call    ?CompareOptionalValues@CUwfStaticVolumeConfiguration@@AEAAJAEAV1@PEA_N@Z; CUwfStaticVolumeConfiguration::CompareOptionalValues(CUwfStaticVolumeConfiguration &,bool *)
0x1800062dc  mov     ecx, eax
0x1800062de  test    eax, eax
0x1800062e0  js      short loc_1800062F0
0x1800062e2  cmp     [rsp+28h+arg_0], 0
0x1800062e7  jz      short loc_1800062F0
0x1800062e9  cmp     [rsp+28h+arg_8], 0
0x1800062ee  jnz     short loc_1800062B8
0x1800062f0  xor     al, al
0x1800062f2  mov     [rbx], al
0x1800062f4  mov     eax, ecx
0x1800062f6  mov     rbx, [rsp+28h+arg_10]
0x1800062fb  mov     rsi, [rsp+28h+arg_18]
0x180006300  add     rsp, 20h
0x180006304  pop     rdi
0x180006305  retn
```
