# ATL::CAtlMap<ulong,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::UpdateRehashThresholds(void)

- ea: `0x180015024`
- end: `0x18001509b`
- name: `?UpdateRehashThresholds@?$CAtlMap@KPEAVSqmSessionContext@CSqmSessionMgr@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmSessionContext@CSqmSessionMgr@@@4@@ATL@@AEAAXXZ`
- size: `119`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800016e0`
- `0x1800147f0`
- `0x180014a14`
- `0x180014aec`
- `0x1800154d4`

## callees

- `0x180015024`

## pseudocode

```c
unsigned __int64 __fastcall ATL::CAtlMap<unsigned long,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::UpdateRehashThresholds(
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
0x180015024  mov     eax, [rcx+10h]
0x180015027  xorps   xmm0, xmm0
0x18001502a  movss   xmm2, cs:__real@5f000000
0x180015032  xor     edx, edx
0x180015034  mov     r8, 8000000000000000h
0x18001503e  cvtsi2ss xmm0, rax
0x180015043  movaps  xmm1, xmm0
0x180015046  mulss   xmm1, dword ptr [rcx+1Ch]
0x18001504b  comiss  xmm1, xmm2
0x18001504e  jb      short loc_18001505C
0x180015050  subss   xmm1, xmm2
0x180015054  comiss  xmm1, xmm2
0x180015057  jnb     short loc_18001505C
0x180015059  mov     rdx, r8
0x18001505c  mulss   xmm0, dword ptr [rcx+18h]
0x180015061  cvttss2si rax, xmm1
0x180015066  add     rax, rdx
0x180015069  xor     edx, edx
0x18001506b  comiss  xmm0, xmm2
0x18001506e  mov     [rcx+20h], rax
0x180015072  jb      short loc_180015080
0x180015074  subss   xmm0, xmm2
0x180015078  comiss  xmm0, xmm2
0x18001507b  jnb     short loc_180015080
0x18001507d  mov     rdx, r8
0x180015080  cvttss2si rax, xmm0
0x180015085  add     rax, rdx
0x180015088  mov     [rcx+28h], rax
0x18001508c  cmp     rax, 11h
0x180015090  jnb     short locret_18001509A
0x180015092  mov     qword ptr [rcx+28h], 0
0x18001509a  retn
```
