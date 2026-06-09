# ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::UpdateRehashThresholds(void)

- ea: `0x18000b958`
- end: `0x18000b9cf`
- name: `?UpdateRehashThresholds@?$CAtlMap@PEAXV?$CAutoPtr@VCWLIDTimerParam@CWLIDTimerQueue@@@ATL@@V?$CElementTraits@PEAX@2@V?$CAutoPtrElementTraits@VCWLIDTimerParam@CWLIDTimerQueue@@@2@@ATL@@AEAAXXZ`
- size: `119`
- prototype: `unsigned __int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180002280`
- `0x18000aae4`
- `0x18000b1c0`

## callees

- `0x18000b958`

## pseudocode

```c
unsigned __int64 __fastcall ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::UpdateRehashThresholds(
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
0x18000b958  mov     eax, [rcx+10h]
0x18000b95b  xorps   xmm0, xmm0
0x18000b95e  movss   xmm2, cs:__real@5f000000
0x18000b966  xor     edx, edx
0x18000b968  mov     r8, 8000000000000000h
0x18000b972  cvtsi2ss xmm0, rax
0x18000b977  movaps  xmm1, xmm0
0x18000b97a  mulss   xmm1, dword ptr [rcx+1Ch]
0x18000b97f  comiss  xmm1, xmm2
0x18000b982  jb      short loc_18000B990
0x18000b984  subss   xmm1, xmm2
0x18000b988  comiss  xmm1, xmm2
0x18000b98b  jnb     short loc_18000B990
0x18000b98d  mov     rdx, r8
0x18000b990  mulss   xmm0, dword ptr [rcx+18h]
0x18000b995  cvttss2si rax, xmm1
0x18000b99a  add     rax, rdx
0x18000b99d  xor     edx, edx
0x18000b99f  comiss  xmm0, xmm2
0x18000b9a2  mov     [rcx+20h], rax
0x18000b9a6  jb      short loc_18000B9B4
0x18000b9a8  subss   xmm0, xmm2
0x18000b9ac  comiss  xmm0, xmm2
0x18000b9af  jnb     short loc_18000B9B4
0x18000b9b1  mov     rdx, r8
0x18000b9b4  cvttss2si rax, xmm0
0x18000b9b9  add     rax, rdx
0x18000b9bc  mov     [rcx+28h], rax
0x18000b9c0  cmp     rax, 11h
0x18000b9c4  jnb     short locret_18000B9CE
0x18000b9c6  mov     qword ptr [rcx+28h], 0
0x18000b9ce  retn
```
