# CBWCRequest::AddSystemConfigurationParameters(ushort *,unsigned __int64)

- ea: `0x18000e3e8`
- end: `0x18000e7ec`
- name: `?AddSystemConfigurationParameters@CBWCRequest@@AEBAJPEAG_K@Z`
- size: `1028`
- prototype: `__int64 __fastcall(CBWCRequest *this, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f0ec`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180002ac4`
- `0x18000e3e8`
- `0x18000ee30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e7cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e7cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7be`

## string_xrefs

- `0x18000e43e`: `CBWCRequest::AddSystemConfigurationParameters`
- `0x18000e789`: `CBWCRequest::AddSystemConfigurationParameters`
- `0x18000e7ad`: `CBWCRequest::AddSystemConfigurationParameters`
- `0x18000e498`: `BWCContentProviderConfiguration::GetRemoteServerPartnerParameter`
- `0x18000e4b7`: `BWCContentProviderConfiguration::GetRemoteServerPartnerParameter`
- `0x18000e73c`: `BWCContentProviderConfiguration::GetRemoteServerPartnerParameter`
- `0x18000e753`: `BWCContentProviderConfiguration::GetRemoteServerPartnerParameter`

## pseudocode

```c
__int64 __fastcall CBWCRequest::AddSystemConfigurationParameters(
        CBWCRequest *this,
        unsigned __int16 *a2,
        unsigned __int64 a3)
{
  int v6; // ebx
  __int64 v7; // rcx
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  void *v11; // r14
  __int64 v12; // r10
  __int64 v13; // r9
  HANDLE ProcessHeap; // rax
  __int64 v16; // [rsp+38h] [rbp-81h]
  LPVOID lpMem; // [rsp+E0h] [rbp+27h] BYREF
  unsigned __int64 v18; // [rsp+128h] [rbp+6Fh] BYREF
  wchar_t *Buffer; // [rsp+138h] [rbp+7Fh] BYREF

  Buffer = 0;
  v18 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"CBWCRequest::AddSystemConfigurationParameters",
        -2147024809,
        (__int64)"Buffer");
    return (unsigned int)v6;
  }
  v7 = *(_QWORD *)this;
  lpMem = 0;
  v8 = SDiagPrviCopyPWSTR(*(const unsigned __int16 **)(v7 + 16), (unsigned __int16 **)&lpMem);
  v6 = v8;
  v11 = lpMem;
  if ( v8 == -2147024882 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0s_EventWriteTransfer(
        v10,
        SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY,
        "BWCContentProviderConfiguration::GetRemoteServerPartnerParameter");
  }
  else if ( v8 == -2147024809 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(
        v10,
        v9,
        "BWCContentProviderConfiguration::GetRemoteServerPartnerParameter",
        2147942487LL);
  }
  else
  {
    if ( v8 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        McTemplateU0sq_EventWriteTransfer(
          v10,
          v9,
          "BWCContentProviderConfiguration::GetRemoteServerPartnerParameter",
          v8);
      if ( v6 < 0 )
        goto LABEL_26;
    }
    else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    {
      McTemplateU0s_EventWriteTransfer(
        v10,
        SDIAGPRV_EVENT_DEBUG_SUCCESS,
        "BWCContentProviderConfiguration::GetRemoteServerPartnerParameter");
    }
    v12 = *((_QWORD *)this + 1);
    v6 = StringCchPrintfExW(
           a2,
           a3,
           &Buffer,
           &v18,
           0,
           L"%s&%s=%d.%d&%s=%d.%d&%s=%d&%s=%d&%s=%d&%s=%d&%s=%d&%s=%d&%s=%d",
           v11,
           L"OS",
           *(_DWORD *)v12,
           *(_DWORD *)(v12 + 4),
           L"SP",
           *(unsigned __int16 *)(v12 + 8),
           *(unsigned __int16 *)(v12 + 10),
           L"Build",
           *(_DWORD *)(v12 + 12),
           L"SKU",
           *(_DWORD *)(v12 + 16),
           L"Arch",
           *(unsigned __int16 *)(v12 + 20),
           L"Type",
           *(unsigned __int8 *)(v12 + 22),
           L"MobilePc",
           *(_DWORD *)(v12 + 132),
           L"Internal",
           *(_DWORD *)(v12 + 136),
           L"GeoId",
           *(_DWORD *)(v12 + 36));
    if ( v6 >= 0 )
    {
      if ( *(_BYTE *)(*((_QWORD *)this + 1) + 128LL) == 0xFF
        || (LODWORD(v16) = *(unsigned __int8 *)(*((_QWORD *)this + 1) + 128LL),
            v6 = StringCchPrintfExW(Buffer, v18, &Buffer, &v18, 0, L"&%s=%u", L"BIOSMajorRelease", v16),
            v6 >= 0) )
      {
        if ( *(_BYTE *)(*((_QWORD *)this + 1) + 129LL) == 0xFF
          || (LODWORD(v16) = *(unsigned __int8 *)(*((_QWORD *)this + 1) + 129LL),
              v6 = StringCchPrintfExW(Buffer, v18, &Buffer, &v18, 0, L"&%s=%u", L"BIOSMinorRelease", v16),
              v6 >= 0) )
        {
          if ( *(_BYTE *)(*((_QWORD *)this + 1) + 130LL) == 0xFF
            || (LODWORD(v16) = *(unsigned __int8 *)(*((_QWORD *)this + 1) + 130LL),
                v6 = StringCchPrintfExW(Buffer, v18, &Buffer, &v18, 0, L"&%s=%u", L"ECFirmwareMajorRelease", v16),
                v6 >= 0) )
          {
            v10 = *(unsigned __int8 *)(*((_QWORD *)this + 1) + 131LL);
            if ( (_BYTE)v10 == 0xFF )
              goto LABEL_27;
            LODWORD(v16) = *(unsigned __int8 *)(*((_QWORD *)this + 1) + 131LL);
            v6 = StringCchPrintfExW(Buffer, v18, &Buffer, &v18, 0, L"&%s=%u", L"ECFirmwareMinorRelease", v16);
          }
        }
      }
    }
  }
LABEL_26:
  if ( v6 == -2147024809 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_35;
    v13 = 2147942487LL;
    goto LABEL_34;
  }
LABEL_27:
  if ( !v6 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
      McTemplateU0s_EventWriteTransfer(
        v10,
        SDIAGPRV_EVENT_DEBUG_SUCCESS,
        "CBWCRequest::AddSystemConfigurationParameters");
    goto LABEL_35;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v13 = (unsigned int)v6;
LABEL_34:
    McTemplateU0sq_EventWriteTransfer(v10, v9, "CBWCRequest::AddSystemConfigurationParameters", v13);
  }
LABEL_35:
  if ( v11 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v11);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e3e8  mov     [rsp-8+arg_0], rbx
0x18000e3ed  push    rbp
0x18000e3ee  push    rdi
0x18000e3ef  push    r12
0x18000e3f1  push    r14
0x18000e3f3  push    r15
0x18000e3f5  lea     rbp, [rsp-37h]
0x18000e3fa  sub     rsp, 0F0h
0x18000e401  mov     [rbp+57h+Buffer], 0
0x18000e409  mov     r12, r8
0x18000e40c  mov     [rbp+57h+arg_8], 0
0x18000e414  mov     r15, rdx
0x18000e417  mov     rdi, rcx
0x18000e41a  test    rdx, rdx
0x18000e41d  jnz     short loc_18000E454
0x18000e41f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000e426  mov     ebx, 80070057h
0x18000e42b  jz      loc_18000E7D2
0x18000e431  lea     rax, aBuffer; "Buffer"
0x18000e438  mov     r9d, 80070057h
0x18000e43e  lea     r8, aCbwcrequestAdd_0; "CBWCRequest::AddSystemConfigurationPara"...
0x18000e445  mov     qword ptr [rsp+110h+var_F0], rax
0x18000e44a  call    McTemplateU0sqs_EventWriteTransfer
0x18000e44f  jmp     loc_18000E7D2
0x18000e454  mov     rcx, [rcx]
0x18000e457  lea     rdx, [rbp+57h+lpMem]; unsigned __int16 **
0x18000e45b  mov     [rbp+57h+lpMem], 0
0x18000e463  mov     rcx, [rcx+10h]; unsigned __int16 *
0x18000e467  call    ?SDiagPrviCopyPWSTR@@YAJPEBGPEAPEAG@Z; SDiagPrviCopyPWSTR(ushort const *,ushort * *)
0x18000e46c  mov     ebx, eax
0x18000e46e  mov     r14, [rbp+57h+lpMem]
0x18000e472  cmp     eax, 8007000Eh
0x18000e477  jz      loc_18000E74A
0x18000e47d  cmp     eax, 80070057h
0x18000e482  jz      loc_18000E72D
0x18000e488  test    eax, eax
0x18000e48a  jz      short loc_18000E4AE
0x18000e48c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000e493  jz      short loc_18000E4A4
0x18000e495  mov     r9d, eax
0x18000e498  lea     r8, aBwccontentprov_9; "BWCContentProviderConfiguration::GetRem"...
0x18000e49f  call    McTemplateU0sq_EventWriteTransfer
0x18000e4a4  test    ebx, ebx
0x18000e4a6  js      loc_18000E766
0x18000e4ac  jmp     short loc_18000E4CA
0x18000e4ae  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000e4b5  jz      short loc_18000E4CA
0x18000e4b7  lea     r8, aBwccontentprov_9; "BWCContentProviderConfiguration::GetRem"...
0x18000e4be  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000e4c5  call    McTemplateU0s_EventWriteTransfer
0x18000e4ca  mov     r10, [rdi+8]
0x18000e4ce  mov     eax, [r10+24h]
0x18000e4d2  mov     [rsp+110h+var_40], eax
0x18000e4d9  lea     rax, aGeoid; "GeoId"
0x18000e4e0  mov     [rsp+110h+var_48], rax
0x18000e4e8  mov     eax, [r10+88h]
0x18000e4ef  mov     [rsp+110h+var_50], eax
0x18000e4f6  lea     rax, aInternal; "Internal"
0x18000e4fd  movzx   ecx, byte ptr [r10+16h]
0x18000e502  movzx   edx, word ptr [r10+14h]
0x18000e507  movzx   r8d, word ptr [r10+0Ah]
0x18000e50c  movzx   r9d, word ptr [r10+8]
0x18000e511  mov     [rsp+110h+var_58], rax
0x18000e519  mov     eax, [r10+84h]
0x18000e520  mov     [rsp+110h+var_60], eax
0x18000e527  lea     rax, aMobilepc; "MobilePc"
0x18000e52e  mov     [rsp+110h+var_68], rax
0x18000e536  lea     rax, aType; "Type"
0x18000e53d  mov     [rsp+110h+var_70], ecx
0x18000e544  mov     rcx, r15; Buffer
0x18000e547  mov     [rsp+110h+var_78], rax
0x18000e54f  lea     rax, aArch; "Arch"
0x18000e556  mov     [rsp+110h+var_80], edx
0x18000e55d  mov     rdx, r12; unsigned __int64
0x18000e560  mov     [rsp+110h+var_88], rax
0x18000e568  mov     eax, [r10+10h]
0x18000e56c  mov     [rsp+110h+var_90], eax
0x18000e573  lea     rax, aSku; "SKU"
0x18000e57a  mov     [rsp+110h+var_98], rax
0x18000e57f  mov     eax, [r10+0Ch]
0x18000e583  mov     [rsp+110h+var_A0], eax
0x18000e587  lea     rax, aBuild; "Build"
0x18000e58e  mov     [rsp+110h+var_A8], rax
0x18000e593  lea     rax, aSp; "SP"
0x18000e59a  mov     [rsp+110h+var_B0], r8d
0x18000e59f  lea     r8, [rbp+57h+Buffer]; unsigned __int16 **
0x18000e5a3  mov     [rsp+110h+var_B8], r9d
0x18000e5a8  lea     r9, [rbp+57h+arg_8]; unsigned __int64 *
0x18000e5ac  mov     [rsp+110h+var_C0], rax
0x18000e5b1  mov     eax, [r10+4]
0x18000e5b5  mov     [rsp+110h+var_C8], eax
0x18000e5b9  mov     eax, [r10]
0x18000e5bc  mov     [rsp+110h+var_D0], eax
0x18000e5c0  lea     rax, aOs; "OS"
0x18000e5c7  mov     [rsp+110h+var_D8], rax
0x18000e5cc  lea     rax, aSSDDSDDSDSDSDS; "%s&%s=%d.%d&%s=%d.%d&%s=%d&%s=%d&%s=%d&"...
0x18000e5d3  mov     [rsp+110h+var_E0], r14
0x18000e5d8  mov     [rsp+110h+var_E8], rax; unsigned __int16 *
0x18000e5dd  mov     qword ptr [rsp+110h+var_F0], 0; unsigned int
0x18000e5e6  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000e5eb  mov     ebx, eax
0x18000e5ed  test    eax, eax
0x18000e5ef  js      loc_18000E766
0x18000e5f5  mov     rcx, [rdi+8]
0x18000e5f9  lea     r12, aSU; "&%s=%u"
0x18000e600  mov     r15b, 0FFh
0x18000e603  movzx   eax, byte ptr [rcx+80h]
0x18000e60a  cmp     al, r15b
0x18000e60d  jz      short loc_18000E64C
0x18000e60f  mov     rdx, [rbp+57h+arg_8]; unsigned __int64
0x18000e613  lea     r9, [rbp+57h+arg_8]; unsigned __int64 *
0x18000e617  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18000e61b  lea     r8, [rbp+57h+Buffer]; unsigned __int16 **
0x18000e61f  mov     dword ptr [rsp+110h+var_D8], eax
0x18000e623  lea     rax, aBiosmajorrelea; "BIOSMajorRelease"
0x18000e62a  mov     [rsp+110h+var_E0], rax
0x18000e62f  mov     [rsp+110h+var_E8], r12; unsigned __int16 *
0x18000e634  mov     qword ptr [rsp+110h+var_F0], 0; unsigned int
0x18000e63d  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000e642  mov     ebx, eax
0x18000e644  test    eax, eax
0x18000e646  js      loc_18000E766
0x18000e64c  mov     rax, [rdi+8]
0x18000e650  movzx   ecx, byte ptr [rax+81h]
0x18000e657  cmp     cl, r15b
0x18000e65a  jz      short loc_18000E699
0x18000e65c  mov     rdx, [rbp+57h+arg_8]; unsigned __int64
0x18000e660  lea     rax, aBiosminorrelea; "BIOSMinorRelease"
0x18000e667  mov     dword ptr [rsp+110h+var_D8], ecx
0x18000e66b  lea     r9, [rbp+57h+arg_8]; unsigned __int64 *
0x18000e66f  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18000e673  lea     r8, [rbp+57h+Buffer]; unsigned __int16 **
0x18000e677  mov     [rsp+110h+var_E0], rax
0x18000e67c  mov     [rsp+110h+var_E8], r12; unsigned __int16 *
0x18000e681  mov     qword ptr [rsp+110h+var_F0], 0; unsigned int
0x18000e68a  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000e68f  mov     ebx, eax
0x18000e691  test    eax, eax
0x18000e693  js      loc_18000E766
0x18000e699  mov     rax, [rdi+8]
0x18000e69d  movzx   ecx, byte ptr [rax+82h]
0x18000e6a4  cmp     cl, r15b
0x18000e6a7  jz      short loc_18000E6E6
0x18000e6a9  mov     rdx, [rbp+57h+arg_8]; unsigned __int64
0x18000e6ad  lea     rax, aEcfirmwaremajo; "ECFirmwareMajorRelease"
0x18000e6b4  mov     dword ptr [rsp+110h+var_D8], ecx
0x18000e6b8  lea     r9, [rbp+57h+arg_8]; unsigned __int64 *
0x18000e6bc  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18000e6c0  lea     r8, [rbp+57h+Buffer]; unsigned __int16 **
0x18000e6c4  mov     [rsp+110h+var_E0], rax
0x18000e6c9  mov     [rsp+110h+var_E8], r12; unsigned __int16 *
0x18000e6ce  mov     qword ptr [rsp+110h+var_F0], 0; unsigned int
0x18000e6d7  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000e6dc  mov     ebx, eax
0x18000e6de  test    eax, eax
0x18000e6e0  js      loc_18000E766
0x18000e6e6  mov     rax, [rdi+8]
0x18000e6ea  movzx   ecx, byte ptr [rax+83h]
0x18000e6f1  cmp     cl, r15b
0x18000e6f4  jz      short loc_18000E76E
0x18000e6f6  mov     rdx, [rbp+57h+arg_8]; unsigned __int64
0x18000e6fa  lea     rax, aEcfirmwaremino; "ECFirmwareMinorRelease"
0x18000e701  mov     dword ptr [rsp+110h+var_D8], ecx
0x18000e705  lea     r9, [rbp+57h+arg_8]; unsigned __int64 *
0x18000e709  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18000e70d  lea     r8, [rbp+57h+Buffer]; unsigned __int16 **
0x18000e711  mov     [rsp+110h+var_E0], rax
0x18000e716  mov     [rsp+110h+var_E8], r12; unsigned __int16 *
0x18000e71b  mov     qword ptr [rsp+110h+var_F0], 0; unsigned int
0x18000e724  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000e729  mov     ebx, eax
0x18000e72b  jmp     short loc_18000E766
0x18000e72d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000e734  jz      short loc_18000E766
0x18000e736  mov     r9d, 80070057h
0x18000e73c  lea     r8, aBwccontentprov_9; "BWCContentProviderConfiguration::GetRem"...
0x18000e743  call    McTemplateU0sq_EventWriteTransfer
0x18000e748  jmp     short loc_18000E766
0x18000e74a  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000e751  jz      short loc_18000E766
0x18000e753  lea     r8, aBwccontentprov_9; "BWCContentProviderConfiguration::GetRem"...
0x18000e75a  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000e761  call    McTemplateU0s_EventWriteTransfer
0x18000e766  cmp     ebx, 80070057h
0x18000e76c  jz      short loc_18000E79E
0x18000e76e  test    ebx, ebx
0x18000e770  jz      short loc_18000E780
0x18000e772  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000e779  jz      short loc_18000E7B9
0x18000e77b  mov     r9d, ebx
0x18000e77e  jmp     short loc_18000E7AD
0x18000e780  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000e787  jz      short loc_18000E7B9
0x18000e789  lea     r8, aCbwcrequestAdd_0; "CBWCRequest::AddSystemConfigurationPara"...
0x18000e790  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000e797  call    McTemplateU0s_EventWriteTransfer
0x18000e79c  jmp     short loc_18000E7B9
0x18000e79e  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000e7a5  jz      short loc_18000E7B9
0x18000e7a7  mov     r9d, 80070057h
0x18000e7ad  lea     r8, aCbwcrequestAdd_0; "CBWCRequest::AddSystemConfigurationPara"...
0x18000e7b4  call    McTemplateU0sq_EventWriteTransfer
0x18000e7b9  test    r14, r14
0x18000e7bc  jz      short loc_18000E7D2
0x18000e7be  call    cs:__imp_GetProcessHeap
0x18000e7c4  mov     r8, r14; lpMem
0x18000e7c7  xor     edx, edx; dwFlags
0x18000e7c9  mov     rcx, rax; hHeap
0x18000e7cc  call    cs:__imp_HeapFree
0x18000e7d2  mov     eax, ebx
0x18000e7d4  mov     rbx, [rsp+110h+arg_0]
0x18000e7dc  add     rsp, 0F0h
0x18000e7e3  pop     r15
0x18000e7e5  pop     r14
0x18000e7e7  pop     r12
0x18000e7e9  pop     rdi
0x18000e7ea  pop     rbp
0x18000e7eb  retn
```
