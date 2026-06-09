# SystemSettings::IsOn(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint)

- ea: `0x140018f28`
- end: `0x140018fce`
- name: `?IsOn@SystemSettings@@SAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@I@Z`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400189dc`

## callees

- `0x140002480`
- `0x140018f28`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x140018fa0`
- `USER32!SystemParametersInfoW` at `0x140018fa0`

## pseudocode

```c
__int64 __fastcall SystemSettings::IsOn(_QWORD *a1, unsigned int a2)
{
  __int64 v2; // r10
  unsigned __int16 *v3; // rax
  __int64 v4; // r8
  int v5; // edx
  int v6; // ecx
  UINT v7; // edx
  UINT v8; // ecx
  _OWORD pvParam[4]; // [rsp+20h] [rbp-58h] BYREF

  v2 = 32LL * a2;
  v3 = *(unsigned __int16 **)((char *)&SystemSettings::_systemSetting + v2);
  v4 = *a1 - (_QWORD)v3;
  do
  {
    v5 = *(unsigned __int16 *)((char *)v3 + v4);
    v6 = *v3 - v5;
    if ( v6 )
      break;
    ++v3;
  }
  while ( v5 );
  if ( !v6
    && *(_DWORD *)((char *)&SystemSettings::_systemSetting + v2 + 16) == 2
    && (v7 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v2 + 20),
        v8 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v2 + 8),
        memset(pvParam, 0, 60),
        LODWORD(pvParam[0]) = v7,
        SystemParametersInfoW(v8, v7, pvParam, 0)) )
  {
    return BYTE4(pvParam[0]) & 1;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x140018f28  sub     rsp, 78h
0x140018f2c  mov     rax, cs:__security_cookie
0x140018f33  xor     rax, rsp
0x140018f36  mov     [rsp+78h+var_18], rax
0x140018f3b  mov     r8, [rcx]
0x140018f3e  lea     r11, ?_systemSetting@SystemSettings@@0PAUSystemSetting@@A; SystemSetting near * SystemSettings::_systemSetting
0x140018f45  mov     r10d, edx
0x140018f48  shl     r10, 5
0x140018f4c  mov     rax, [r10+r11]
0x140018f50  sub     r8, rax
0x140018f53  movzx   ecx, word ptr [rax]
0x140018f56  movzx   edx, word ptr [rax+r8]
0x140018f5b  sub     ecx, edx
0x140018f5d  jnz     short loc_140018F67
0x140018f5f  add     rax, 2
0x140018f63  test    edx, edx
0x140018f65  jnz     short loc_140018F53
0x140018f67  test    ecx, ecx
0x140018f69  jnz     short loc_140018FB9
0x140018f6b  cmp     dword ptr [r10+r11+10h], 2
0x140018f71  jnz     short loc_140018FB9
0x140018f73  mov     edx, [r10+r11+14h]; uiParam
0x140018f78  lea     r8, [rsp+78h+pvParam]; pvParam
0x140018f7d  mov     ecx, [r10+r11+8]; uiAction
0x140018f82  xorps   xmm0, xmm0
0x140018f85  movups  [rsp+78h+pvParam], xmm0
0x140018f8a  xor     r9d, r9d; fWinIni
0x140018f8d  mov     dword ptr [rsp+78h+pvParam], edx
0x140018f91  movups  xmmword ptr [rsp+78h+var_38], xmm0
0x140018f96  movups  xmmword ptr [rsp+78h+var_38+0Ch], xmm0
0x140018f9b  movups  [rsp+78h+var_48], xmm0
0x140018fa0  call    cs:__imp_SystemParametersInfoW
0x140018fa7  nop     dword ptr [rax+rax+00h]
0x140018fac  test    eax, eax
0x140018fae  jz      short loc_140018FB9
0x140018fb0  mov     eax, dword ptr [rsp+78h+pvParam+4]
0x140018fb4  and     eax, 1
0x140018fb7  jmp     short loc_140018FBB
0x140018fb9  xor     eax, eax
0x140018fbb  mov     rcx, [rsp+78h+var_18]
0x140018fc0  xor     rcx, rsp; StackCookie
0x140018fc3  call    __security_check_cookie
0x140018fc8  add     rsp, 78h
0x140018fcc  retn
```
