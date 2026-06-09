# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::UpdateRehashThresholds(void)

- ea: `0x180021cdc`
- end: `0x180021d53`
- name: `?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCSimpleBuffer@@V?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VCSimpleBuffer@@@2@@ATL@@AEAAXXZ`
- size: `119`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180021294`
- `0x1800217fc`
- `0x180022300`

## callees

- `0x180021cdc`

## pseudocode

```c
unsigned __int64 __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CSimpleBuffer>>::UpdateRehashThresholds(
        __int64 a1)
{
  unsigned __int64 v1; // rdx
  float v2; // xmm0_4
  float v3; // xmm1_4
  float v4; // xmm0_4
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdx
  unsigned __int64 result; // rax

  v1 = 0;
  v2 = (float)*(int *)(a1 + 16);
  v3 = v2 * *(float *)(a1 + 28);
  if ( v3 >= 9.223372e18 )
  {
    v3 = v3 - 9.223372e18;
    if ( v3 < 9.223372e18 )
      v1 = 0x8000000000000000uLL;
  }
  v4 = v2 * *(float *)(a1 + 24);
  v5 = v1 + (unsigned int)(int)v3;
  v6 = 0;
  *(_QWORD *)(a1 + 32) = v5;
  if ( v4 >= 9.223372e18 )
  {
    v4 = v4 - 9.223372e18;
    if ( v4 < 9.223372e18 )
      v6 = 0x8000000000000000uLL;
  }
  result = v6 + (unsigned int)(int)v4;
  *(_QWORD *)(a1 + 40) = result;
  if ( result < 0x11 )
    *(_QWORD *)(a1 + 40) = 0;
  return result;
}

```

## disassembly

```asm
0x180021cdc  mov     eax, [rcx+10h]
0x180021cdf  xorps   xmm0, xmm0
0x180021ce2  movss   xmm2, cs:__real@5f000000
0x180021cea  xor     edx, edx
0x180021cec  mov     r8, 8000000000000000h
0x180021cf6  cvtsi2ss xmm0, rax
0x180021cfb  movaps  xmm1, xmm0
0x180021cfe  mulss   xmm1, dword ptr [rcx+1Ch]
0x180021d03  comiss  xmm1, xmm2
0x180021d06  jb      short loc_180021D14
0x180021d08  subss   xmm1, xmm2
0x180021d0c  comiss  xmm1, xmm2
0x180021d0f  jnb     short loc_180021D14
0x180021d11  mov     rdx, r8
0x180021d14  mulss   xmm0, dword ptr [rcx+18h]
0x180021d19  cvttss2si rax, xmm1
0x180021d1e  add     rax, rdx
0x180021d21  xor     edx, edx
0x180021d23  comiss  xmm0, xmm2
0x180021d26  mov     [rcx+20h], rax
0x180021d2a  jb      short loc_180021D38
0x180021d2c  subss   xmm0, xmm2
0x180021d30  comiss  xmm0, xmm2
0x180021d33  jnb     short loc_180021D38
0x180021d35  mov     rdx, r8
0x180021d38  cvttss2si rax, xmm0
0x180021d3d  add     rax, rdx
0x180021d40  mov     [rcx+28h], rax
0x180021d44  cmp     rax, 11h
0x180021d48  jnb     short locret_180021D52
0x180021d4a  mov     qword ptr [rcx+28h], 0
0x180021d52  retn
```
