# ComputeFlushPeriod

- ea: `0x18000aec0`
- end: `0x18000af4d`
- name: `ComputeFlushPeriod`
- size: `141`
- prototype: `__int64 __fastcall(unsigned __int64, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b7d0`

## callees

- `0x18000b66c`

## pseudocode

```c
__int64 __fastcall ComputeFlushPeriod(unsigned __int64 a1, int a2)
{
  __int64 v2; // rax
  __int128 v4; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int64 v5; // [rsp+40h] [rbp+8h] BYREF
  int v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = a2;
  v2 = *(_QWORD *)(a1 + 328);
  v5 = a1 >> 4;
  v6 = 0;
  v4 = *(_OWORD *)(*(_QWORD *)(v2 + 8) - 16LL);
  RunningHash(&v6, &v4, 16);
  RunningHash(&v6, &v5, 8);
  return 32769 * ((9 * v6) ^ ((unsigned int)(9 * v6) >> 11)) % 0x927C0 + 600000;
}

```

## disassembly

```asm
0x18000aec0  mov     [rsp+arg_8], edx
0x18000aec4  sub     rsp, 38h
0x18000aec8  mov     rax, [rcx+148h]
0x18000aecf  mov     r8d, 10h
0x18000aed5  shr     rcx, 4
0x18000aed9  mov     [rsp+38h+arg_0], rcx
0x18000aede  lea     rcx, [rsp+38h+arg_8]
0x18000aee3  mov     [rsp+38h+arg_8], 0
0x18000aeeb  mov     rdx, [rax+8]
0x18000aeef  movups  xmm0, xmmword ptr [rdx-10h]
0x18000aef3  lea     rdx, [rsp+38h+var_18]
0x18000aef8  movdqu  [rsp+38h+var_18], xmm0
0x18000aefe  call    RunningHash
0x18000af03  lea     rcx, [rsp+38h+arg_8]
0x18000af08  mov     r8d, 8
0x18000af0e  lea     rdx, [rsp+38h+arg_0]
0x18000af13  call    RunningHash
0x18000af18  mov     edx, [rsp+38h+arg_8]
0x18000af1c  lea     eax, [rdx+rdx*8]
0x18000af1f  mov     ecx, eax
0x18000af21  shr     ecx, 0Bh
0x18000af24  xor     ecx, eax
0x18000af26  mov     eax, 6FD91D85h
0x18000af2b  imul    r8d, ecx, 8001h
0x18000af32  mul     r8d
0x18000af35  shr     edx, 12h
0x18000af38  imul    ecx, edx, 927C0h
0x18000af3e  sub     r8d, ecx
0x18000af41  lea     eax, [r8+927C0h]
0x18000af48  add     rsp, 38h
0x18000af4c  retn
```
