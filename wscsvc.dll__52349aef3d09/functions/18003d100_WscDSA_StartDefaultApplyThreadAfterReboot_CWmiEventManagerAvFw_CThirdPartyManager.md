# WscDSA_StartDefaultApplyThreadAfterReboot(CWmiEventManagerAvFw *,CThirdPartyManager *)

- ea: `0x18003d100`
- end: `0x18003d28c`
- name: `?WscDSA_StartDefaultApplyThreadAfterReboot@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(struct CWmiEventManagerAvFw *, struct CThirdPartyManager *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x1800224a0`

## callees

- `0x180008e48`
- `0x1800202e8`
- `0x18003bf04`
- `0x18003c204`
- `0x18003ca54`
- `0x18003cbb8`
- `0x18003cfe8`
- `0x18003d100`
- `0x18003e140`
- `0x18003fc30`

## pseudocode

```c
__int64 __fastcall WscDSA_StartDefaultApplyThreadAfterReboot(
        struct CWmiEventManagerAvFw *a1,
        struct CThirdPartyManager *a2)
{
  struct CThirdPartyManager *v2; // rbx
  struct CWmiEventManagerAvFw *v3; // rdi
  int v4; // esi
  const unsigned __int16 *v5; // rdx
  HKEY v6; // rcx
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // rdx
  HKEY v9; // rcx
  const unsigned __int16 *v10; // r8
  unsigned int started; // eax
  unsigned int v12; // ebx
  unsigned int v14[4]; // [rsp+30h] [rbp-98h] BYREF
  wchar_t String2[40]; // [rsp+40h] [rbp-88h] BYREF

  v2 = WscServiceUtils::g_pAntiVirusManager;
  v3 = g_pWmiEventManagerAvFw;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
  v14[0] = 0;
  v4 = 6;
  WscDSA_SaveDefaultByPolicy(v3, v2, (int *)v14);
  if ( v14[0] )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
    }
  }
  else if ( dword_180054158 )
  {
    v14[0] = 78;
    if ( (unsigned int)WscDSA_GetGuidFromRegistry(v6, v5, v7, String2, v14) )
    {
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
      }
      if ( (int)WscDSA_SaveDefaultByGuid(v3, v2, String2) >= 0 )
        CUtil::DeleteRegistryValue(v9, v8, v10);
    }
    else
    {
      v4 = 7;
      WscDSA_OutOfBoxExperience(v3, v2);
    }
  }
  started = WscDSA_StartDefaultApplyThread(v3, v2, v4);
  v12 = started;
  dword_18005415C = 0;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_728c66c465713f49a85befae87578f6c_Traceguids, started);
  return v12;
}

```

## disassembly

```asm
0x18003d100  push    rbx
0x18003d102  push    rsi
0x18003d103  push    rdi
0x18003d104  push    r15
0x18003d106  sub     rsp, 0A8h
0x18003d10d  mov     rax, cs:__security_cookie
0x18003d114  xor     rax, rsp
0x18003d117  mov     [rsp+0C8h+var_38], rax
0x18003d11f  mov     rbx, cs:?g_pAntiVirusManager@WscServiceUtils@@3PEAVCAntiVirusManager@@EA; CAntiVirusManager * WscServiceUtils::g_pAntiVirusManager
0x18003d126  mov     rdi, cs:?g_pWmiEventManagerAvFw@@3PEAVCWmiEventManagerAvFw@@EA; CWmiEventManagerAvFw * g_pWmiEventManagerAvFw
0x18003d12d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d134  lea     r15, WPP_GLOBAL_Control
0x18003d13b  cmp     rcx, r15
0x18003d13e  jz      short loc_18003D15B
0x18003d140  test    byte ptr [rcx+1Ch], 8
0x18003d144  jz      short loc_18003D15B
0x18003d146  mov     rcx, [rcx+10h]
0x18003d14a  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003d151  mov     edx, 68h ; 'h'
0x18003d156  call    WPP_SF_
0x18003d15b  lea     r8, [rsp+0C8h+var_98]; int *
0x18003d160  mov     [rsp+0C8h+var_98], 0
0x18003d168  mov     rdx, rbx; struct CThirdPartyManager *
0x18003d16b  mov     rcx, rdi; this
0x18003d16e  mov     esi, 6
0x18003d173  call    ?WscDSA_SaveDefaultByPolicy@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@PEAH@Z; WscDSA_SaveDefaultByPolicy(CWmiEventManagerAvFw *,CThirdPartyManager *,int *)
0x18003d178  cmp     [rsp+0C8h+var_98], 0
0x18003d17d  jz      short loc_18003D1AE
0x18003d17f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d186  cmp     rcx, r15
0x18003d189  jz      loc_18003D229
0x18003d18f  test    byte ptr [rcx+1Ch], 4
0x18003d193  jz      loc_18003D229
0x18003d199  mov     rcx, [rcx+10h]
0x18003d19d  lea     edx, [rsi+63h]
0x18003d1a0  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003d1a7  call    WPP_SF_
0x18003d1ac  jmp     short loc_18003D229
0x18003d1ae  cmp     cs:dword_180054158, 0
0x18003d1b5  jz      short loc_18003D229
0x18003d1b7  lea     rax, [rsp+0C8h+var_98]
0x18003d1bc  mov     [rsp+0C8h+var_98], 4Eh ; 'N'
0x18003d1c4  lea     r9, [rsp+0C8h+String2]; unsigned __int16 *
0x18003d1c9  mov     [rsp+0C8h+var_A8], rax; unsigned int *
0x18003d1ce  call    ?WscDSA_GetGuidFromRegistry@@YAHPEAUHKEY__@@PEBG1PEAGPEAK@Z; WscDSA_GetGuidFromRegistry(HKEY__ *,ushort const *,ushort const *,ushort *,ulong *)
0x18003d1d3  test    eax, eax
0x18003d1d5  jz      short loc_18003D219
0x18003d1d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d1de  cmp     rcx, r15
0x18003d1e1  jz      short loc_18003D1FE
0x18003d1e3  test    byte ptr [rcx+1Ch], 4
0x18003d1e7  jz      short loc_18003D1FE
0x18003d1e9  mov     rcx, [rcx+10h]
0x18003d1ed  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003d1f4  mov     edx, 6Ah ; 'j'
0x18003d1f9  call    WPP_SF_
0x18003d1fe  lea     r8, [rsp+0C8h+String2]; String2
0x18003d203  mov     rdx, rbx; struct CThirdPartyManager *
0x18003d206  mov     rcx, rdi; this
0x18003d209  call    ?WscDSA_SaveDefaultByGuid@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@PEBG@Z; WscDSA_SaveDefaultByGuid(CWmiEventManagerAvFw *,CThirdPartyManager *,ushort const *)
0x18003d20e  test    eax, eax
0x18003d210  js      short loc_18003D229
0x18003d212  call    ?DeleteRegistryValue@CUtil@@SAJPEAUHKEY__@@PEBG1@Z; CUtil::DeleteRegistryValue(HKEY__ *,ushort const *,ushort const *)
0x18003d217  jmp     short loc_18003D229
0x18003d219  mov     rdx, rbx; struct CThirdPartyManager *
0x18003d21c  mov     rcx, rdi; this
0x18003d21f  mov     esi, 7
0x18003d224  call    ?WscDSA_OutOfBoxExperience@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@@Z; WscDSA_OutOfBoxExperience(CWmiEventManagerAvFw *,CThirdPartyManager *)
0x18003d229  mov     r8d, esi; unsigned int
0x18003d22c  mov     rdx, rbx; struct CThirdPartyManager *
0x18003d22f  mov     rcx, rdi; struct CWmiEventManagerAvFw *
0x18003d232  call    ?WscDSA_StartDefaultApplyThread@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@K@Z; WscDSA_StartDefaultApplyThread(CWmiEventManagerAvFw *,CThirdPartyManager *,ulong)
0x18003d237  mov     ebx, eax
0x18003d239  mov     cs:dword_18005415C, 0
0x18003d243  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d24a  cmp     rcx, r15
0x18003d24d  jz      short loc_18003D26D
0x18003d24f  test    byte ptr [rcx+1Ch], 8
0x18003d253  jz      short loc_18003D26D
0x18003d255  mov     rcx, [rcx+10h]
0x18003d259  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003d260  mov     edx, 6Bh ; 'k'
0x18003d265  mov     r9d, eax
0x18003d268  call    WPP_SF_d
0x18003d26d  mov     eax, ebx
0x18003d26f  mov     rcx, [rsp+0C8h+var_38]
0x18003d277  xor     rcx, rsp; StackCookie
0x18003d27a  call    __security_check_cookie
0x18003d27f  add     rsp, 0A8h
0x18003d286  pop     r15
0x18003d288  pop     rdi
0x18003d289  pop     rsi
0x18003d28a  pop     rbx
0x18003d28b  retn
```
