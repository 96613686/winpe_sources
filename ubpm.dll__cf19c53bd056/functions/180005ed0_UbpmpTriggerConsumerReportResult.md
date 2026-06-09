# UbpmpTriggerConsumerReportResult

- ea: `0x180005ed0`
- end: `0x180006485`
- name: `UbpmpTriggerConsumerReportResult`
- size: `1461`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180003050`
- `0x180006650`
- `0x180008f30`
- `0x18000a710`
- `0x18000c650`

## callees

- `0x180004e10`
- `0x180005ed0`
- `0x180015e10`
- `0x180034ec4`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180006085`
- `ntdll!RtlInitUnicodeString` at `0x180006224`
- `ntdll!RtlInitUnicodeString` at `0x180006085`
- `ntdll!RtlInitUnicodeString` at `0x180006224`
- `ntdll!RtlHashUnicodeString` at `0x18000609f`
- `ntdll!RtlHashUnicodeString` at `0x18000623e`
- `ntdll!RtlHashUnicodeString` at `0x18000609f`
- `ntdll!RtlHashUnicodeString` at `0x18000623e`
- `ntdll!WinSqmIsOptedIn` at `0x180005f7a`
- `ntdll!WinSqmIsOptedIn` at `0x1800063ef`
- `ntdll!WinSqmIsOptedIn` at `0x180005f7a`
- `ntdll!WinSqmIsOptedIn` at `0x1800063ef`
- `ntdll!WinSqmAddToStream` at `0x180006447`
- `ntdll!WinSqmAddToStream` at `0x180006447`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000639f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000639f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005f89`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005f89`

## pseudocode

```c
__int64 __fastcall UbpmpTriggerConsumerReportResult(__int64 a1, int a2, char a3)
{
  unsigned int v6; // r12d
  int v7; // esi
  ULONG v8; // ebx
  unsigned int v9; // r14d
  unsigned __int64 v10; // r9
  unsigned __int64 v11; // r8
  __int64 v12; // rdx
  NTSTATUS v13; // eax
  ULONG v14; // r15d
  struct _FILETIME v15; // rax
  DWORD dwHighDateTime; // eax
  unsigned __int64 v17; // r9
  unsigned __int64 v18; // r10
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rax
  int *v24; // rcx
  __int64 v25; // rax
  unsigned int v27; // eax
  char v29; // [rsp+30h] [rbp-D0h]
  ULONG HashValue; // [rsp+34h] [rbp-CCh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  int v32; // [rsp+40h] [rbp-C0h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v34; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v35[2]; // [rsp+5Ch] [rbp-A4h] BYREF
  int IsOptedIn; // [rsp+64h] [rbp-9Ch]
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[36]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE UserData[24]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v41; // [rsp+B8h] [rbp-48h]
  __int128 v42; // [rsp+C8h] [rbp-38h]
  __int128 v43; // [rsp+D8h] [rbp-28h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  _DWORD *v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]
  unsigned int *v47; // [rsp+100h] [rbp+0h]
  __int64 v48; // [rsp+108h] [rbp+8h]
  ULONG *p_HashValue; // [rsp+110h] [rbp+10h]
  __int64 v50; // [rsp+118h] [rbp+18h]

  SystemTimeAsFileTime = 0;
  memset(v39, 0, sizeof(v39));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_SL(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      75,
      (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
      *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
      a2);
  v6 = UbpmStatsOperation(a1, 0, v39);
  if ( !v6 )
  {
    IsOptedIn = WinSqmIsOptedIn();
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( a3 == 1 )
    {
      v7 = *(_DWORD *)&v39[24];
      v8 = 0x7FFFFFFF;
      v32 = 0;
      if ( *(_QWORD *)&v39[12] )
      {
        LODWORD(v10) = 0;
        if ( *(_QWORD *)&v39[12] < *(unsigned __int64 *)&SystemTimeAsFileTime
          && *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v39[12] < 0x98968000000000uLL )
        {
          v10 = (*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v39[12]) / 0x989680uLL;
        }
        v9 = (unsigned int)v10 / 0x3C;
      }
      else
      {
        v9 = 0x7FFFFFFF;
      }
      if ( *(_DWORD *)&v39[32] || *(_DWORD *)&v39[28] )
      {
        LODWORD(v11) = 0;
        if ( *(_QWORD *)&v39[28] < *(unsigned __int64 *)&SystemTimeAsFileTime
          && *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v39[28] < 0x98968000000000uLL )
        {
          v11 = (*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v39[28]) / 0x989680uLL;
        }
        v8 = (unsigned int)v11 / 0x3C;
      }
      v12 = *(_QWORD *)(a1 + 24);
      HashValue = 0;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v12 + 8));
      v13 = RtlHashUnicodeString(&DestinationString, 1u, 1u, &HashValue);
      v14 = 0;
      *(_DWORD *)&v39[24] = a2;
      *(struct _FILETIME *)&v39[12] = SystemTimeAsFileTime;
      if ( v13 >= 0 )
        v14 = HashValue;
LABEL_55:
      v6 = UbpmStatsOperation(a1, 1, v39);
      if ( !v6 )
      {
        if ( IsOptedIn )
        {
          *(_DWORD *)UserData = 0;
          *(_OWORD *)&UserData[8] = 0;
          v44 = 0;
          v41 = 0;
          v42 = 0;
          v43 = 0;
          if ( (unsigned int)WinSqmIsOptedIn() )
          {
            if ( v14 )
            {
              LODWORD(v44) = v32;
              *(_DWORD *)&UserData[8] = v14;
              *(_DWORD *)UserData = 1;
              LODWORD(v41) = v7;
              *(_DWORD *)&UserData[16] = 1;
              LODWORD(v42) = v9;
              DWORD2(v41) = 1;
              LODWORD(v43) = v8;
              DWORD2(v42) = 1;
              DWORD2(v43) = 1;
              WinSqmAddToStream(0, 11240, 5, UserData);
            }
          }
        }
      }
      goto LABEL_60;
    }
    if ( !a3 )
    {
      v7 = *(_DWORD *)&v39[24];
      v29 = 0;
      if ( *(_DWORD *)&v39[24] != -2147023605
        && *(_DWORD *)&v39[24] != 1291
        && *(_DWORD *)&v39[24] != -2147023829
        && *(_DWORD *)&v39[24] != 1067 )
      {
        if ( a2 != -2147023605 && a2 != 1291 && a2 != -2147023829 )
        {
          v15 = *(struct _FILETIME *)&v39[28];
          if ( a2 != 1067 )
            v15 = SystemTimeAsFileTime;
          *(struct _FILETIME *)&v39[28] = v15;
        }
        v7 = a2;
        *(_DWORD *)&v39[24] = a2;
        v29 = 1;
      }
      dwHighDateTime = SystemTimeAsFileTime.dwHighDateTime;
      v8 = 0x7FFFFFFF;
      v32 = 1;
      if ( *(_QWORD *)&v39[12] )
      {
        LODWORD(v17) = 0;
        v18 = *(unsigned int *)&v39[12] | (HIDWORD(*(_QWORD *)&v39[12]) << 32);
        if ( v18 < *(_QWORD *)&SystemTimeAsFileTime && *(_QWORD *)&SystemTimeAsFileTime - v18 < 0x98968000000000LL )
          v17 = (*(_QWORD *)&SystemTimeAsFileTime - v18) / 0x989680;
        dwHighDateTime = SystemTimeAsFileTime.dwHighDateTime;
        v9 = (unsigned int)v17 / 0x3C;
      }
      else
      {
        v9 = 0x7FFFFFFF;
      }
      if ( *(_DWORD *)&v39[32] || *(_DWORD *)&v39[28] )
      {
        LODWORD(v19) = 0;
        v20 = SystemTimeAsFileTime.dwLowDateTime | ((unsigned __int64)dwHighDateTime << 32);
        if ( *(_QWORD *)&v39[28] < v20 )
        {
          v21 = v20 - *(_QWORD *)&v39[28];
          if ( v21 < 0x98968000000000LL )
            v19 = v21 / 0x989680;
        }
        v8 = (unsigned int)v19 / 0x3C;
      }
      v22 = *(_QWORD *)(a1 + 24);
      HashValue = 0;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v22 + 8));
      v14 = 0;
      if ( RtlHashUnicodeString(&DestinationString, 1u, 1u, &HashValue) >= 0 )
        v14 = HashValue;
      if ( (unsigned int)dword_18004C0F0 > 3 )
      {
        v35[0] = *(_DWORD *)&v39[24];
        v37 = *(_QWORD *)&v39[28];
        v38 = *(_QWORD *)&v39[12];
        v23 = *(_QWORD *)(a1 + 24);
        HashValue = v8;
        v34 = v9;
        v50 = 4;
        v24 = *(int **)(v23 + 8);
        p_HashValue = &HashValue;
        v47 = &v34;
        v45 = v35;
        *((_QWORD *)&v43 + 1) = &v37;
        *((_QWORD *)&v42 + 1) = &v38;
        v48 = 4;
        v46 = 4;
        v44 = 8;
        *(_QWORD *)&v43 = 8;
        if ( v24 )
        {
          v25 = -1;
          while ( *((_WORD *)v24 + ++v25) != 0 )
            ;
          v27 = 2 * v25 + 2;
        }
        else
        {
          v24 = &dword_1800405F4;
          v27 = 2;
        }
        *(_QWORD *)&v42 = v27;
        *(_DWORD *)(&DestinationString.MaximumLength + 1) = 3;
        *(_QWORD *)UserData = off_18004C0F8;
        *((_QWORD *)&v41 + 1) = v24;
        *(_DWORD *)&DestinationString.Length = 184549376;
        DestinationString.Buffer = 0;
        *(_QWORD *)&UserData[8] = *(unsigned __int16 *)off_18004C0F8 | 0x200000000LL;
        *(_QWORD *)&UserData[16] = &byte_180043167;
        *(_QWORD *)&v41 = 0x10000007FLL;
        v35[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(
          RegHandle,
          (PCEVENT_DESCRIPTOR)&DestinationString,
          0,
          0,
          8u,
          (PEVENT_DATA_DESCRIPTOR)UserData);
      }
      if ( v29 == 1 )
        goto LABEL_55;
    }
  }
LABEL_60:
  UbpmTriggerConsumerPublishStateChange(a1);
  return v6;
}

```

## disassembly

```asm
0x180005ed0  push    rbp
0x180005ed2  push    rbx
0x180005ed3  push    rdi
0x180005ed4  push    r12
0x180005ed6  push    r13
0x180005ed8  push    r14
0x180005eda  lea     rbp, [rsp-38h]
0x180005edf  sub     rsp, 138h
0x180005ee6  mov     rax, cs:__security_cookie
0x180005eed  xor     rax, rsp
0x180005ef0  mov     [rbp+60h+var_40], rax
0x180005ef4  xor     eax, eax
0x180005ef6  xorps   xmm0, xmm0
0x180005ef9  xor     r14d, r14d
0x180005efc  mov     dword ptr [rbp+60h+var_D8+10h], eax
0x180005eff  mov     qword ptr [rsp+160h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180005f04  movzx   ebx, r8b
0x180005f08  mov     edi, edx
0x180005f0a  mov     r13, rcx
0x180005f0d  movups  [rsp+160h+var_E8], xmm0
0x180005f12  movups  xmmword ptr [rbp+60h+var_D8], xmm0
0x180005f16  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f1d  lea     rax, WPP_GLOBAL_Control
0x180005f24  cmp     rcx, rax
0x180005f27  jz      short loc_180005F50
0x180005f29  test    byte ptr [rcx+1Ch], 4
0x180005f2d  jz      short loc_180005F50
0x180005f2f  mov     r9, [r13+18h]
0x180005f33  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180005f3a  mov     rcx, [rcx+10h]
0x180005f3e  mov     edx, 4Bh ; 'K'
0x180005f43  mov     [rsp+160h+UserDataCount], edi
0x180005f47  mov     r9, [r9+8]
0x180005f4b  call    WPP_SF_SL
0x180005f50  lea     r8, [rsp+160h+var_E8]
0x180005f55  xor     edx, edx
0x180005f57  mov     rcx, r13
0x180005f5a  call    UbpmStatsOperation
0x180005f5f  mov     r12d, eax
0x180005f62  test    eax, eax
0x180005f64  jnz     loc_18000645D
0x180005f6a  mov     [rsp+160h+arg_10], rsi
0x180005f72  mov     [rsp+160h+var_30], r15
0x180005f7a  call    cs:__imp_WinSqmIsOptedIn
0x180005f80  lea     rcx, [rsp+160h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005f85  mov     [rsp+160h+var_FC], eax
0x180005f89  call    cs:__imp_GetSystemTimeAsFileTime
0x180005f8f  cmp     bl, 1
0x180005f92  jnz     loc_1800060C3
0x180005f98  mov     r8d, dword ptr [rbp+60h+var_D8]
0x180005f9c  mov     r15, 98968000000000h
0x180005fa6  mov     esi, dword ptr [rbp+60h+var_D8+8]
0x180005fa9  mov     r11, 0D6BF94D5E57A42BDh
0x180005fb3  mov     rcx, qword ptr [rsp+160h+SystemTimeAsFileTime.dwLowDateTime]
0x180005fb8  mov     ebx, 7FFFFFFFh
0x180005fbd  mov     r12d, [rsp+160h+SystemTimeAsFileTime.dwHighDateTime]
0x180005fc2  mov     r10d, dword ptr [rbp+60h+var_E8+0Ch]
0x180005fc6  mov     [rsp+160h+var_120], r14d
0x180005fcb  test    r8d, r8d
0x180005fce  jnz     short loc_180005FDA
0x180005fd0  test    r10d, r10d
0x180005fd3  jnz     short loc_180005FDA
0x180005fd5  mov     r14d, ebx
0x180005fd8  jmp     short loc_180006019
0x180005fda  shl     r8, 20h
0x180005fde  mov     rdx, r12
0x180005fe1  shl     rdx, 20h
0x180005fe5  or      r8, r10
0x180005fe8  mov     eax, ecx
0x180005fea  mov     r9d, r14d
0x180005fed  or      rdx, rax
0x180005ff0  cmp     r8, rdx
0x180005ff3  jnb     short loc_18000600A
0x180005ff5  sub     rdx, r8
0x180005ff8  cmp     rdx, r15
0x180005ffb  jnb     short loc_18000600A
0x180005ffd  mov     rax, r11
0x180006000  mul     rdx
0x180006003  mov     r9, rdx
0x180006006  shr     r9, 17h
0x18000600a  mov     eax, 88888889h
0x18000600f  mul     r9d
0x180006012  mov     r14d, edx
0x180006015  shr     r14d, 5
0x180006019  mov     r9d, dword ptr [rbp+60h+var_D8+10h]
0x18000601d  mov     r10d, dword ptr [rbp+60h+var_D8+0Ch]
0x180006021  test    r9d, r9d
0x180006024  jnz     short loc_18000602B
0x180006026  test    r10d, r10d
0x180006029  jz      short loc_180006068
0x18000602b  shl     r9, 20h
0x18000602f  mov     rdx, r12
0x180006032  shl     rdx, 20h
0x180006036  xor     r8d, r8d
0x180006039  mov     eax, ecx
0x18000603b  or      r9, r10
0x18000603e  or      rdx, rax
0x180006041  cmp     r9, rdx
0x180006044  jnb     short loc_18000605B
0x180006046  sub     rdx, r9
0x180006049  cmp     rdx, r15
0x18000604c  jnb     short loc_18000605B
0x18000604e  mov     rax, r11
0x180006051  mul     rdx
0x180006054  mov     r8, rdx
0x180006057  shr     r8, 17h
0x18000605b  mov     eax, 88888889h
0x180006060  mul     r8d
0x180006063  mov     ebx, edx
0x180006065  shr     ebx, 5
0x180006068  mov     rdx, [r13+18h]
0x18000606c  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x180006071  xorps   xmm0, xmm0
0x180006074  mov     [rsp+160h+HashValue], 0
0x18000607c  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x180006081  mov     rdx, [rdx+8]; SourceString
0x180006085  call    cs:__imp_RtlInitUnicodeString
0x18000608b  mov     r8d, 1; HashAlgorithm
0x180006091  lea     r9, [rsp+160h+HashValue]; HashValue
0x180006096  movzx   edx, r8b; CaseInSensitive
0x18000609a  lea     rcx, [rsp+160h+DestinationString]; String
0x18000609f  call    cs:__imp_RtlHashUnicodeString
0x1800060a5  xor     r15d, r15d
0x1800060a8  mov     dword ptr [rbp+60h+var_D8+8], edi
0x1800060ab  test    eax, eax
0x1800060ad  mov     rax, qword ptr [rsp+160h+SystemTimeAsFileTime.dwLowDateTime]
0x1800060b2  mov     qword ptr [rbp+60h+var_E8+0Ch], rax
0x1800060b6  cmovns  r15d, [rsp+160h+HashValue]
0x1800060bc  xor     edi, edi
0x1800060be  jmp     loc_1800063B0
0x1800060c3  test    bl, bl
0x1800060c5  jnz     loc_18000644D
0x1800060cb  mov     esi, dword ptr [rbp+60h+var_D8+8]
0x1800060ce  mov     rcx, qword ptr [rsp+160h+SystemTimeAsFileTime.dwLowDateTime]
0x1800060d3  mov     [rsp+160h+var_130], r14b
0x1800060d8  cmp     esi, 8007050Bh
0x1800060de  jz      short loc_18000612C
0x1800060e0  cmp     esi, 50Bh
0x1800060e6  jz      short loc_18000612C
0x1800060e8  cmp     esi, 8007042Bh
0x1800060ee  jz      short loc_18000612C
0x1800060f0  cmp     esi, 42Bh
0x1800060f6  jz      short loc_18000612C
0x1800060f8  cmp     edi, 8007050Bh
0x1800060fe  jz      short loc_180006122
0x180006100  cmp     edi, 50Bh
0x180006106  jz      short loc_180006122
0x180006108  cmp     edi, 8007042Bh
0x18000610e  jz      short loc_180006122
0x180006110  mov     rax, qword ptr [rbp+60h+var_D8+0Ch]
0x180006114  cmp     edi, 42Bh
0x18000611a  cmovnz  rax, rcx
0x18000611e  mov     qword ptr [rbp+60h+var_D8+0Ch], rax
0x180006122  mov     esi, edi
0x180006124  mov     dword ptr [rbp+60h+var_D8+8], edi
0x180006127  mov     [rsp+160h+var_130], 1
0x18000612c  mov     r8, qword ptr [rbp+60h+var_E8+0Ch]
0x180006130  mov     r15, 98968000000000h
0x18000613a  mov     eax, [rsp+160h+SystemTimeAsFileTime.dwHighDateTime]
0x18000613e  mov     r11, 0D6BF94D5E57A42BDh
0x180006148  mov     edi, dword ptr [rbp+60h+var_E8+0Ch]
0x18000614b  mov     ebx, 7FFFFFFFh
0x180006150  shr     r8, 20h
0x180006154  mov     [rsp+160h+var_120], 1
0x18000615c  test    r8d, r8d
0x18000615f  jnz     short loc_18000616A
0x180006161  test    edi, edi
0x180006163  jnz     short loc_18000616A
0x180006165  mov     r14d, ebx
0x180006168  jmp     short loc_1800061B0
0x18000616a  mov     rdx, rax
0x18000616d  mov     r10, r8
0x180006170  shl     rdx, 20h
0x180006174  mov     r9d, r14d
0x180006177  shl     r10, 20h
0x18000617b  mov     eax, ecx
0x18000617d  or      r10, rdi
0x180006180  or      rdx, rax
0x180006183  cmp     r10, rdx
0x180006186  jnb     short loc_18000619D
0x180006188  sub     rdx, r10
0x18000618b  cmp     rdx, r15
0x18000618e  jnb     short loc_18000619D
0x180006190  mov     rax, r11
0x180006193  mul     rdx
0x180006196  mov     r9, rdx
0x180006199  shr     r9, 17h
0x18000619d  mov     eax, 88888889h
0x1800061a2  mul     r9d
0x1800061a5  mov     eax, [rsp+160h+SystemTimeAsFileTime.dwHighDateTime]
0x1800061a9  mov     r14d, edx
0x1800061ac  shr     r14d, 5
0x1800061b0  mov     r9, qword ptr [rbp+60h+var_D8+0Ch]
0x1800061b4  mov     r10d, dword ptr [rbp+60h+var_D8+0Ch]
0x1800061b8  shr     r9, 20h
0x1800061bc  test    r9d, r9d
0x1800061bf  jnz     short loc_1800061CA
0x1800061c1  test    r10d, r10d
0x1800061c4  jnz     short loc_1800061CA
0x1800061c6  xor     edi, edi
0x1800061c8  jmp     short loc_18000620B
0x1800061ca  mov     edx, eax
0x1800061cc  xor     edi, edi
0x1800061ce  mov     eax, ecx
0x1800061d0  mov     r8d, edi
0x1800061d3  shl     rdx, 20h
0x1800061d7  mov     rcx, r9
0x1800061da  shl     rcx, 20h
0x1800061de  or      rdx, rax
0x1800061e1  or      rcx, r10
0x1800061e4  cmp     rcx, rdx
0x1800061e7  jnb     short loc_1800061FE
0x1800061e9  sub     rdx, rcx
0x1800061ec  cmp     rdx, r15
0x1800061ef  jnb     short loc_1800061FE
0x1800061f1  mov     rax, r11
0x1800061f4  mul     rdx
0x1800061f7  mov     r8, rdx
0x1800061fa  shr     r8, 17h
0x1800061fe  mov     eax, 88888889h
0x180006203  mul     r8d
0x180006206  mov     ebx, edx
0x180006208  shr     ebx, 5
0x18000620b  mov     rdx, [r13+18h]
0x18000620f  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x180006214  xorps   xmm0, xmm0
0x180006217  mov     [rsp+160h+HashValue], edi
0x18000621b  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x180006220  mov     rdx, [rdx+8]; SourceString
0x180006224  call    cs:__imp_RtlInitUnicodeString
0x18000622a  mov     r8d, 1; HashAlgorithm
0x180006230  lea     r9, [rsp+160h+HashValue]; HashValue
0x180006235  movzx   edx, r8b; CaseInSensitive
0x180006239  lea     rcx, [rsp+160h+DestinationString]; String
0x18000623e  call    cs:__imp_RtlHashUnicodeString
0x180006244  test    eax, eax
0x180006246  mov     r15d, edi
0x180006249  mov     eax, cs:dword_18004C0F0
0x18000624f  cmovns  r15d, [rsp+160h+HashValue]
0x180006255  cmp     eax, 3
0x180006258  jbe     loc_1800063A5
0x18000625e  mov     eax, dword ptr [rbp+60h+var_D8+8]
0x180006261  mov     [rsp+160h+var_104], eax
0x180006265  mov     rax, qword ptr [rbp+60h+var_D8+0Ch]
0x180006269  mov     [rsp+160h+var_F8], rax
0x18000626e  mov     rax, qword ptr [rbp+60h+var_E8+0Ch]
0x180006272  mov     [rsp+160h+var_F0], rax
0x180006277  mov     rax, [r13+18h]
0x18000627b  mov     [rsp+160h+HashValue], ebx
0x18000627f  mov     [rsp+160h+var_108], r14d
0x180006284  mov     [rbp+60h+var_48], 4
0x18000628c  mov     rcx, [rax+8]
0x180006290  lea     rax, [rsp+160h+HashValue]
0x180006295  mov     [rbp+60h+var_50], rax
0x180006299  lea     rax, [rsp+160h+var_108]
0x18000629e  mov     [rbp+60h+var_60], rax
0x1800062a2  lea     rax, [rsp+160h+var_104]
0x1800062a7  mov     [rbp+60h+var_70], rax
0x1800062ab  lea     rax, [rsp+160h+var_F8]
0x1800062b0  mov     qword ptr [rbp+60h+var_88+8], rax
0x1800062b4  lea     rax, [rsp+160h+var_F0]
0x1800062b9  mov     qword ptr [rbp+60h+var_98+8], rax
0x1800062bd  mov     [rbp+60h+var_58], 4
0x1800062c5  mov     [rbp+60h+var_68], 4
0x1800062cd  mov     [rbp+60h+var_78], 8
0x1800062d5  mov     qword ptr [rbp+60h+var_88], 8
0x1800062dd  test    rcx, rcx
0x1800062e0  jz      short loc_180006305
0x1800062e2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800062e9  nop     dword ptr [rax+00000000h]
0x1800062f0  cmp     word ptr [rcx+rax*2+2], 0
0x1800062f6  lea     rax, [rax+1]
0x1800062fa  jnz     short loc_1800062F0
0x1800062fc  lea     eax, ds:2[rax*2]
0x180006303  jmp     short loc_180006311
0x180006305  lea     rcx, dword_1800405F4
0x18000630c  mov     eax, 2
0x180006311  mov     dword ptr [rbp+60h+var_98], eax
0x180006314  lea     rdx, [rsp+160h+DestinationString]; EventDescriptor
0x180006319  movzx   eax, cs:word_18004315D
0x180006320  xor     r9d, r9d; RelatedActivityId
0x180006323  mov     dword ptr [rsp+160h+DestinationString+4], eax
0x180006327  xor     r8d, r8d; ActivityId
0x18000632a  mov     rax, cs:off_18004C0F8
0x180006331  mov     qword ptr [rbp+60h+var_C0], rax
0x180006335  mov     qword ptr [rbp+60h+var_A8+8], rcx
0x180006339  lea     rcx, _TraceLoggingMetadata
0x180006340  mov     dword ptr [rbp+60h+var_98+4], edi
0x180006343  mov     dword ptr [rsp+160h+DestinationString.Length], 0B000000h
0x18000634b  mov     [rsp+160h+DestinationString.Buffer], rdi
0x180006350  movzx   eax, word ptr [rax]
0x180006353  mov     dword ptr [rbp+60h+var_C0+8], eax
0x180006356  lea     rax, byte_180043167
0x18000635d  mov     qword ptr [rbp+60h+var_C0+10h], rax
0x180006361  lea     rax, _TraceLoggingMetadataEnd
0x180006368  sub     eax, ecx
0x18000636a  mov     dword ptr [rbp+60h+var_C0+0Ch], 2
0x180006371  mov     dword ptr [rbp+60h+var_A8], 7Fh
0x180006378  mov     dword ptr [rbp+60h+var_A8+4], 1
0x18000637f  mov     [rsp+160h+var_100], eax
  ... truncated ...
```
