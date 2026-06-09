# ATL::CAtlMap<uint,_tagpropertykey,ATL::CElementTraits<uint>,CStructTraits<_tagpropertykey>>::UpdateRehashThresholds(void)

- ea: `0x180013390`
- end: `0x180013407`
- name: `?UpdateRehashThresholds@?$CAtlMap@IU_tagpropertykey@@V?$CElementTraits@I@ATL@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@AEAAXXZ`
- size: `119`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800122fc`
- `0x180012a70`
- `0x180013088`
- `0x180027374`
- `0x180027f3c`
- `0x1800293e8`
- `0x18002bcd8`

## callees

- `0x180013390`

## pseudocode

```c
unsigned __int64 __fastcall ATL::CAtlMap<unsigned int,_tagpropertykey,ATL::CElementTraits<unsigned int>,CStructTraits<_tagpropertykey>>::UpdateRehashThresholds(
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
0x180013390  mov     eax, [rcx+10h]
0x180013393  xorps   xmm0, xmm0
0x180013396  movss   xmm2, cs:__real@5f000000
0x18001339e  xor     edx, edx
0x1800133a0  mov     r8, 8000000000000000h
0x1800133aa  cvtsi2ss xmm0, rax
0x1800133af  movaps  xmm1, xmm0
0x1800133b2  mulss   xmm1, dword ptr [rcx+1Ch]
0x1800133b7  comiss  xmm1, xmm2
0x1800133ba  jb      short loc_1800133C8
0x1800133bc  subss   xmm1, xmm2
0x1800133c0  comiss  xmm1, xmm2
0x1800133c3  jnb     short loc_1800133C8
0x1800133c5  mov     rdx, r8
0x1800133c8  mulss   xmm0, dword ptr [rcx+18h]
0x1800133cd  cvttss2si rax, xmm1
0x1800133d2  add     rax, rdx
0x1800133d5  xor     edx, edx
0x1800133d7  comiss  xmm0, xmm2
0x1800133da  mov     [rcx+20h], rax
0x1800133de  jb      short loc_1800133EC
0x1800133e0  subss   xmm0, xmm2
0x1800133e4  comiss  xmm0, xmm2
0x1800133e7  jnb     short loc_1800133EC
0x1800133e9  mov     rdx, r8
0x1800133ec  cvttss2si rax, xmm0
0x1800133f1  add     rax, rdx
0x1800133f4  mov     [rcx+28h], rax
0x1800133f8  cmp     rax, 11h
0x1800133fc  jnb     short locret_180013406
0x1800133fe  mov     qword ptr [rcx+28h], 0
0x180013406  retn
```
