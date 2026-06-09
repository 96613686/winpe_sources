# EXFORMOBJ_vComputeWtoDAccelFlags

- ea: `0x140001810`
- end: `0x14000188f`
- name: `EXFORMOBJ_vComputeWtoDAccelFlags`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001810`
- `0x140018450`

## pseudocode

```c
__int64 __fastcall EXFORMOBJ_vComputeWtoDAccelFlags(__int64 *a1)
{
  __int64 result; // rax
  int v2; // ecx
  int v3; // edx

  result = *a1;
  if ( !*a1 )
    RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&anon_ccdb91336a64480ff5dc1631ec8ffbe4_15_llvm_1499869916920363649);
  v2 = 8;
  if ( !*(_DWORD *)(result + 24) )
    v2 = ((*(_DWORD *)(result + 28) == 0) << 6) | 8;
  if ( *(float *)(result + 4) != 0.0 || *(float *)(result + 8) != 0.0 )
    goto LABEL_9;
  v3 = v2 | 1;
  if ( *(float *)result == 16.0 && *(float *)(result + 12) == 16.0 )
  {
    v2 |= 3u;
LABEL_9:
    v3 = v2;
  }
  *(_DWORD *)(result + 32) = v3;
  return result;
}

```

## disassembly

```asm
0x140001810  sub     rsp, 28h
0x140001814  mov     rax, [rcx]
0x140001817  test    rax, rax
0x14000181a  jz      short loc_140001882
0x14000181c  mov     ecx, 8
0x140001821  cmp     dword ptr [rax+18h], 0
0x140001825  jnz     short loc_140001836
0x140001827  xor     ecx, ecx
0x140001829  cmp     dword ptr [rax+1Ch], 0
0x14000182d  setz    cl
0x140001830  shl     ecx, 6
0x140001833  or      ecx, 8
0x140001836  movss   xmm1, dword ptr [rax+4]
0x14000183b  xorps   xmm0, xmm0
0x14000183e  ucomiss xmm1, xmm0
0x140001841  jnz     short loc_140001878
0x140001843  jp      short loc_140001878
0x140001845  movss   xmm1, dword ptr [rax+8]
0x14000184a  ucomiss xmm1, xmm0
0x14000184d  jnz     short loc_140001878
0x14000184f  jp      short loc_140001878
0x140001851  mov     edx, ecx
0x140001853  or      edx, 1
0x140001856  movss   xmm0, dword ptr [rax]
0x14000185a  ucomiss xmm0, cs:__real@41800000
0x140001861  jnz     short loc_14000187A
0x140001863  jp      short loc_14000187A
0x140001865  movss   xmm0, dword ptr [rax+0Ch]
0x14000186a  ucomiss xmm0, cs:__real@41800000
0x140001871  jnz     short loc_14000187A
0x140001873  jp      short loc_14000187A
0x140001875  or      ecx, 3
0x140001878  mov     edx, ecx
0x14000187a  mov     [rax+20h], edx
0x14000187d  add     rsp, 28h
0x140001881  retn
0x140001882  lea     rcx, anon_ccdb91336a64480ff5dc1631ec8ffbe4_15_llvm_1499869916920363649
0x140001889  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
```
