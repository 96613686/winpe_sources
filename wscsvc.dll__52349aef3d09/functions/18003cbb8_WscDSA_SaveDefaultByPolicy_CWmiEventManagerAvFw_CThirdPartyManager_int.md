# WscDSA_SaveDefaultByPolicy(CWmiEventManagerAvFw *,CThirdPartyManager *,int *)

- ea: `0x18003cbb8`
- end: `0x18003ce11`
- name: `?WscDSA_SaveDefaultByPolicy@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@PEAH@Z`
- size: `601`
- prototype: `__int64 __fastcall(struct CWmiEventManagerAvFw *this, struct CThirdPartyManager *, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b824`
- `0x18003d100`

## callees

- `0x180002db0`
- `0x180008e48`
- `0x1800202e8`
- `0x180029158`
- `0x18003c138`
- `0x18003ca54`
- `0x18003cbb8`
- `0x18003e274`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003cc42`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003cc42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cc31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cd86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cc31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cd86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cd94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003cd94`

## string_xrefs

- `0x18003cca3`: `SOFTWARE\Policies\Microsoft\Security Center`

## pseudocode

```c
__int64 __fastcall WscDSA_SaveDefaultByPolicy(
        struct CWmiEventManagerAvFw *this,
        struct CThirdPartyManager *a2,
        int *a3)
{
  HKEY v6; // rcx
  HANDLE v7; // rax
  int RegistryStringValue; // ebx
  CThirdPartyManager *v9; // rcx
  __int64 v10; // rax
  wchar_t *v11; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v14[4]; // [rsp+30h] [rbp-A8h] BYREF
  wchar_t String2[40]; // [rsp+40h] [rbp-98h] BYREF

  v14[0] = 78;
  v6 = (HKEY)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
  if ( a3 )
    *a3 = 0;
  if ( qword_180054150 || (v7 = GetProcessHeap(), (qword_180054150 = (wchar_t *)HeapAlloc(v7, 8u, 0x4Eu)) != 0) )
  {
    RegistryStringValue = CUtil::GetRegistryStringValue(
                            v6,
                            L"SOFTWARE\\Policies\\Microsoft\\Security Center",
                            L"DefaultAntivirusGuid",
                            String2,
                            v14);
    if ( RegistryStringValue < 0 )
      goto LABEL_27;
    v10 = -1;
    do
      ++v10;
    while ( String2[v10] );
    if ( v10 != 38 )
    {
LABEL_27:
      v11 = qword_180054150;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
      qword_180054150 = 0;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
        v9 = WPP_GLOBAL_Control;
      }
      RegistryStringValue = 0;
      goto LABEL_31;
    }
    if ( (unsigned int)WscDSA_IsGroupPolicyProduct(String2) )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control )
        return (unsigned int)RegistryStringValue;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_31;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
    }
    else
    {
      RegistryStringValue = WscDSA_SaveDefaultByGuid(this, a2, String2);
      if ( RegistryStringValue >= 0 )
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_728c66c465713f49a85befae87578f6c_Traceguids, String2);
        }
        RegistryStringValue = StringCchCopyW(qword_180054150, 0x27u, String2);
        if ( RegistryStringValue >= 0 && a3 )
          *a3 = 1;
      }
    }
    goto LABEL_26;
  }
  RegistryStringValue = -2147024882;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control )
    return (unsigned int)RegistryStringValue;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_728c66c465713f49a85befae87578f6c_Traceguids, 2147942414LL);
LABEL_26:
    v9 = WPP_GLOBAL_Control;
  }
LABEL_31:
  if ( v9 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)v9 + 2),
      25,
      WPP_728c66c465713f49a85befae87578f6c_Traceguids,
      (unsigned int)RegistryStringValue);
  return (unsigned int)RegistryStringValue;
}

```

## disassembly

```asm
0x18003cbb8  push    rbx
0x18003cbba  push    rbp
0x18003cbbb  push    rsi
0x18003cbbc  push    rdi
0x18003cbbd  push    r12
0x18003cbbf  push    r14
0x18003cbc1  push    r15
0x18003cbc3  sub     rsp, 0A0h
0x18003cbca  mov     rax, cs:__security_cookie
0x18003cbd1  xor     rax, rsp
0x18003cbd4  mov     [rsp+0D8h+var_48], rax
0x18003cbdc  mov     ebx, 4Eh ; 'N'
0x18003cbe1  mov     rdi, r8
0x18003cbe4  mov     [rsp+0D8h+var_A8], ebx
0x18003cbe8  mov     rbp, rdx
0x18003cbeb  mov     rsi, rcx
0x18003cbee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cbf5  lea     r15, WPP_GLOBAL_Control
0x18003cbfc  lea     r12, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003cc03  cmp     rcx, r15
0x18003cc06  jz      short loc_18003CC1D
0x18003cc08  test    byte ptr [rcx+1Ch], 8
0x18003cc0c  jz      short loc_18003CC1D
0x18003cc0e  mov     rcx, [rcx+10h]
0x18003cc12  lea     edx, [rbx-3Ah]
0x18003cc15  mov     r8, r12
0x18003cc18  call    WPP_SF_
0x18003cc1d  xor     r14d, r14d
0x18003cc20  test    rdi, rdi
0x18003cc23  jz      short loc_18003CC28
0x18003cc25  mov     [rdi], r14d
0x18003cc28  cmp     cs:qword_180054150, r14
0x18003cc2f  jnz     short loc_18003CC8D
0x18003cc31  call    cs:__imp_GetProcessHeap
0x18003cc37  mov     r8, rbx; dwBytes
0x18003cc3a  mov     edx, 8; dwFlags
0x18003cc3f  mov     rcx, rax; hHeap
0x18003cc42  call    cs:__imp_HeapAlloc
0x18003cc48  mov     cs:qword_180054150, rax
0x18003cc4f  test    rax, rax
0x18003cc52  jnz     short loc_18003CC8D
0x18003cc54  mov     ebx, 8007000Eh
0x18003cc59  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cc60  cmp     rcx, r15
0x18003cc63  jz      loc_18003CDED
0x18003cc69  test    byte ptr [rcx+1Ch], 1
0x18003cc6d  jz      loc_18003CDCE
0x18003cc73  mov     rcx, [rcx+10h]
0x18003cc77  lea     edx, [rax+15h]
0x18003cc7a  mov     r9d, 8007000Eh
0x18003cc80  mov     r8, r12
0x18003cc83  call    WPP_SF_d
0x18003cc88  jmp     loc_18003CD76
0x18003cc8d  lea     rax, [rsp+0D8h+var_A8]
0x18003cc92  lea     r9, [rsp+0D8h+String2]; unsigned __int16 *
0x18003cc97  mov     [rsp+0D8h+var_B8], rax; unsigned int *
0x18003cc9c  lea     r8, aDefaultantivir; "DefaultAntivirusGuid"
0x18003cca3  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Security"...
0x18003ccaa  call    ?GetRegistryStringValue@CUtil@@SAJPEAUHKEY__@@PEBG1PEAGPEAK@Z; CUtil::GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ushort *,ulong *)
0x18003ccaf  mov     ebx, eax
0x18003ccb1  test    eax, eax
0x18003ccb3  js      loc_18003CD7F
0x18003ccb9  lea     rcx, [rsp+0D8h+String2]
0x18003ccbe  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003ccc2  inc     rax
0x18003ccc5  cmp     [rcx+rax*2], r14w
0x18003ccca  jnz     short loc_18003CCC2
0x18003cccc  cmp     rax, 26h ; '&'
0x18003ccd0  jnz     loc_18003CD7F
0x18003ccd6  lea     rcx, [rsp+0D8h+String2]; String2
0x18003ccdb  call    ?WscDSA_IsGroupPolicyProduct@@YAHPEBG@Z; WscDSA_IsGroupPolicyProduct(ushort const *)
0x18003cce0  test    eax, eax
0x18003cce2  jz      short loc_18003CD11
0x18003cce4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cceb  cmp     rcx, r15
0x18003ccee  jz      loc_18003CDED
0x18003ccf4  test    byte ptr [rcx+1Ch], 4
0x18003ccf8  jz      loc_18003CDCE
0x18003ccfe  mov     rcx, [rcx+10h]
0x18003cd02  mov     edx, 17h
0x18003cd07  mov     r8, r12
0x18003cd0a  call    WPP_SF_
0x18003cd0f  jmp     short loc_18003CD76
0x18003cd11  lea     r8, [rsp+0D8h+String2]; String2
0x18003cd16  mov     rdx, rbp; struct CThirdPartyManager *
0x18003cd19  mov     rcx, rsi; this
0x18003cd1c  call    ?WscDSA_SaveDefaultByGuid@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@PEBG@Z; WscDSA_SaveDefaultByGuid(CWmiEventManagerAvFw *,CThirdPartyManager *,ushort const *)
0x18003cd21  mov     ebx, eax
0x18003cd23  test    eax, eax
0x18003cd25  js      short loc_18003CD76
0x18003cd27  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cd2e  cmp     rcx, r15
0x18003cd31  jz      short loc_18003CD4F
0x18003cd33  test    byte ptr [rcx+1Ch], 4
0x18003cd37  jz      short loc_18003CD4F
0x18003cd39  mov     rcx, [rcx+10h]
0x18003cd3d  lea     r9, [rsp+0D8h+String2]
0x18003cd42  mov     edx, 18h
0x18003cd47  mov     r8, r12
0x18003cd4a  call    WPP_SF_S
0x18003cd4f  mov     rcx, cs:qword_180054150; unsigned __int16 *
0x18003cd56  lea     r8, [rsp+0D8h+String2]; unsigned __int16 *
0x18003cd5b  mov     edx, 27h ; '''; unsigned __int64
0x18003cd60  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003cd65  mov     ebx, eax
0x18003cd67  test    eax, eax
0x18003cd69  js      short loc_18003CD76
0x18003cd6b  test    rdi, rdi
0x18003cd6e  jz      short loc_18003CD76
0x18003cd70  mov     dword ptr [rdi], 1
0x18003cd76  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cd7d  jmp     short loc_18003CDCE
0x18003cd7f  mov     rbx, cs:qword_180054150
0x18003cd86  call    cs:__imp_GetProcessHeap
0x18003cd8c  mov     r8, rbx; lpMem
0x18003cd8f  xor     edx, edx; dwFlags
0x18003cd91  mov     rcx, rax; hHeap
0x18003cd94  call    cs:__imp_HeapFree
0x18003cd9a  mov     cs:qword_180054150, r14
0x18003cda1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cda8  cmp     rcx, r15
0x18003cdab  jz      short loc_18003CDCB
0x18003cdad  test    byte ptr [rcx+1Ch], 1
0x18003cdb1  jz      short loc_18003CDCB
0x18003cdb3  mov     rcx, [rcx+10h]
0x18003cdb7  mov     edx, 16h
0x18003cdbc  mov     r8, r12
0x18003cdbf  call    WPP_SF_
0x18003cdc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cdcb  mov     ebx, r14d
0x18003cdce  cmp     rcx, r15
0x18003cdd1  jz      short loc_18003CDED
0x18003cdd3  test    byte ptr [rcx+1Ch], 8
0x18003cdd7  jz      short loc_18003CDED
0x18003cdd9  mov     rcx, [rcx+10h]
0x18003cddd  mov     edx, 19h
0x18003cde2  mov     r9d, ebx
0x18003cde5  mov     r8, r12
0x18003cde8  call    WPP_SF_d
0x18003cded  mov     eax, ebx
0x18003cdef  mov     rcx, [rsp+0D8h+var_48]
0x18003cdf7  xor     rcx, rsp; StackCookie
0x18003cdfa  call    __security_check_cookie
0x18003cdff  add     rsp, 0A0h
0x18003ce06  pop     r15
0x18003ce08  pop     r14
0x18003ce0a  pop     r12
0x18003ce0c  pop     rdi
0x18003ce0d  pop     rsi
0x18003ce0e  pop     rbp
0x18003ce0f  pop     rbx
0x18003ce10  retn
```
