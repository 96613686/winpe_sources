# EXFORMOBJ_vComputeAccelFlags

- ea: `0x140001730`
- end: `0x1400017ff`
- name: `EXFORMOBJ_vComputeAccelFlags`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001730`
- `0x140018450`

## pseudocode

```c
__int64 __fastcall EXFORMOBJ_vComputeAccelFlags(__int64 *a1, int a2)
{
  __int64 result; // rax
  int v3; // ecx
  float v4; // xmm0_4

  result = *a1;
  if ( !*a1 )
    RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed(&off_14001B000);
  *(_DWORD *)(result + 32) = a2;
  v3 = a2;
  if ( !*(_DWORD *)(result + 24) )
  {
    v3 = a2;
    if ( !*(_DWORD *)(result + 28) )
    {
      v3 = a2 | 0x40;
      *(_DWORD *)(result + 32) = a2 | 0x40;
    }
  }
  if ( *(float *)(result + 4) == 0.0 && *(float *)(result + 8) == 0.0 )
  {
    *(_DWORD *)(result + 32) = v3 | 1;
    v4 = *(float *)result;
    if ( a2 == 8 )
    {
      if ( v4 == 16.0 && *(float *)(result + 12) == 16.0 )
        goto LABEL_17;
    }
    else
    {
      if ( a2 == 32 )
      {
        if ( v4 != 1.0 || *(float *)(result + 12) != 1.0 )
          return result;
LABEL_17:
        *(_DWORD *)(result + 32) = v3 | 3;
        return result;
      }
      if ( v4 == 0.0625 && *(float *)(result + 12) == 0.0625 )
        goto LABEL_17;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140001730  sub     rsp, 28h
0x140001734  mov     rax, [rcx]
0x140001737  test    rax, rax
0x14000173a  jz      loc_1400017F2
0x140001740  mov     [rax+20h], edx
0x140001743  cmp     dword ptr [rax+18h], 0
0x140001747  mov     ecx, edx
0x140001749  jnz     short loc_14000175B
0x14000174b  cmp     dword ptr [rax+1Ch], 0
0x14000174f  mov     ecx, edx
0x140001751  jnz     short loc_14000175B
0x140001753  mov     ecx, edx
0x140001755  or      ecx, 40h
0x140001758  mov     [rax+20h], ecx
0x14000175b  movss   xmm1, dword ptr [rax+4]
0x140001760  xorps   xmm0, xmm0
0x140001763  ucomiss xmm1, xmm0
0x140001766  jnz     short loc_1400017AA
0x140001768  jp      short loc_1400017AA
0x14000176a  movss   xmm1, dword ptr [rax+8]
0x14000176f  ucomiss xmm1, xmm0
0x140001772  jnz     short loc_1400017AA
0x140001774  jp      short loc_1400017AA
0x140001776  mov     r8d, ecx
0x140001779  or      r8d, 1
0x14000177d  mov     [rax+20h], r8d
0x140001781  movss   xmm0, dword ptr [rax]
0x140001785  cmp     edx, 8
0x140001788  jz      short loc_1400017AF
0x14000178a  cmp     edx, 20h ; ' '
0x14000178d  jnz     short loc_1400017CC
0x14000178f  ucomiss xmm0, cs:__real@3f800000
0x140001796  jnz     short loc_1400017AA
0x140001798  jp      short loc_1400017AA
0x14000179a  movss   xmm0, dword ptr [rax+0Ch]
0x14000179f  ucomiss xmm0, cs:__real@3f800000
0x1400017a6  jnz     short loc_1400017AA
0x1400017a8  jnp     short loc_1400017E7
0x1400017aa  add     rsp, 28h
0x1400017ae  retn
0x1400017af  ucomiss xmm0, cs:__real@41800000
0x1400017b6  jnz     short loc_1400017AA
0x1400017b8  jp      short loc_1400017AA
0x1400017ba  movss   xmm0, dword ptr [rax+0Ch]
0x1400017bf  ucomiss xmm0, cs:__real@41800000
0x1400017c6  jnz     short loc_1400017AA
0x1400017c8  jnp     short loc_1400017E7
0x1400017ca  jmp     short loc_1400017AA
0x1400017cc  ucomiss xmm0, cs:__real@3d800000
0x1400017d3  jnz     short loc_1400017AA
0x1400017d5  jp      short loc_1400017AA
0x1400017d7  movss   xmm0, dword ptr [rax+0Ch]
0x1400017dc  ucomiss xmm0, cs:__real@3d800000
0x1400017e3  jnz     short loc_1400017AA
0x1400017e5  jp      short loc_1400017AA
0x1400017e7  or      ecx, 3
0x1400017ea  mov     [rax+20h], ecx
0x1400017ed  add     rsp, 28h
0x1400017f1  retn
0x1400017f2  lea     rcx, off_14001B000; "gdi_rust\\src\\xform\\mod.rs"
0x1400017f9  call    _RNvNtCs9MWeMO1rkJG_4core6option13unwrap_failed
```
