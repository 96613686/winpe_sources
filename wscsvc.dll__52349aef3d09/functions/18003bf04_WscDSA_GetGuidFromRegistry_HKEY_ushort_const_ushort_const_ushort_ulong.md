# WscDSA_GetGuidFromRegistry(HKEY__ *,ushort const *,ushort const *,ushort *,ulong *)

- ea: `0x18003bf04`
- end: `0x18003bfae`
- name: `?WscDSA_GetGuidFromRegistry@@YAHPEAUHKEY__@@PEBG1PEAGPEAK@Z`
- size: `170`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003d100`

## callees

- `0x180008e48`
- `0x1800202e8`
- `0x18003bf04`
- `0x18003d550`
- `0x18003e274`

## string_xrefs

- `0x18003bf55`: `SOFTWARE\Microsoft\Security Center\Svc\DSA`

## pseudocode

```c
__int64 __fastcall WscDSA_GetGuidFromRegistry(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int *a5)
{
  unsigned int v6; // ebx
  HKEY v7; // rcx
  int RegistryStringValue; // edi

  v6 = 0;
  v7 = (HKEY)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
  RegistryStringValue = CUtil::GetRegistryStringValue(
                          v7,
                          L"SOFTWARE\\Microsoft\\Security Center\\Svc\\DSA",
                          L"OemDefaultAntivirus",
                          a4,
                          a5);
  if ( RegistryStringValue >= 0 && (unsigned int)WscDSA_VerifyInputGuid(a4) )
    v6 = 1;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_728c66c465713f49a85befae87578f6c_Traceguids,
      (unsigned int)RegistryStringValue);
  return v6;
}

```

## disassembly

```asm
0x18003bf04  push    rbx
0x18003bf06  push    rbp
0x18003bf07  push    rsi
0x18003bf08  push    rdi
0x18003bf09  sub     rsp, 38h
0x18003bf0d  mov     rsi, r9
0x18003bf10  xor     ebx, ebx
0x18003bf12  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bf19  lea     rbp, WPP_GLOBAL_Control
0x18003bf20  cmp     rcx, rbp
0x18003bf23  jz      short loc_18003BF3E
0x18003bf25  test    byte ptr [rcx+1Ch], 8
0x18003bf29  jz      short loc_18003BF3E
0x18003bf2b  mov     rcx, [rcx+10h]
0x18003bf2f  lea     edx, [rbx+12h]
0x18003bf32  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003bf39  call    WPP_SF_
0x18003bf3e  mov     rax, [rsp+58h+arg_20]
0x18003bf46  lea     r8, aOemdefaultanti; "OemDefaultAntivirus"
0x18003bf4d  mov     r9, rsi; unsigned __int16 *
0x18003bf50  mov     [rsp+58h+var_38], rax; unsigned int *
0x18003bf55  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Security Center\\S"...
0x18003bf5c  call    ?GetRegistryStringValue@CUtil@@SAJPEAUHKEY__@@PEBG1PEAGPEAK@Z; CUtil::GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ushort *,ulong *)
0x18003bf61  mov     edi, eax
0x18003bf63  test    eax, eax
0x18003bf65  js      short loc_18003BF79
0x18003bf67  mov     rcx, rsi; unsigned __int16 *
0x18003bf6a  call    ?WscDSA_VerifyInputGuid@@YAHPEBG@Z; WscDSA_VerifyInputGuid(ushort const *)
0x18003bf6f  test    eax, eax
0x18003bf71  mov     ecx, 1
0x18003bf76  cmovnz  ebx, ecx
0x18003bf79  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bf80  cmp     rcx, rbp
0x18003bf83  jz      short loc_18003BFA3
0x18003bf85  test    byte ptr [rcx+1Ch], 8
0x18003bf89  jz      short loc_18003BFA3
0x18003bf8b  mov     rcx, [rcx+10h]
0x18003bf8f  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003bf96  mov     edx, 13h
0x18003bf9b  mov     r9d, edi
0x18003bf9e  call    WPP_SF_d
0x18003bfa3  mov     eax, ebx
0x18003bfa5  add     rsp, 38h
0x18003bfa9  pop     rdi
0x18003bfaa  pop     rsi
0x18003bfab  pop     rbp
0x18003bfac  pop     rbx
0x18003bfad  retn
```
