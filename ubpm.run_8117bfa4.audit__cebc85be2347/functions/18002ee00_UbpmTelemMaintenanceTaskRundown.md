# UbpmTelemMaintenanceTaskRundown

- ea: `0x18002ee00`
- end: `0x18002f4a5`
- name: `UbpmTelemMaintenanceTaskRundown`
- size: `1701`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180030d58`
- `0x180038f40`

## callees

- `0x180015c7c`
- `0x1800182a0`
- `0x180018560`
- `0x180027ce8`
- `0x18002b5bc`
- `0x18002ee00`
- `0x180040260`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002eec8`
- `ntdll!RtlInitUnicodeString` at `0x18002eec8`
- `ntdll!RtlHashUnicodeString` at `0x18002eee6`
- `ntdll!RtlHashUnicodeString` at `0x18002eee6`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002ee98`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002ee98`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002ee7a`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002ee7a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002f033`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002f033`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002ee67`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002ee67`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002f35a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002f3ca`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002f35a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002f3ca`

## pseudocode

```c
LONG __fastcall UbpmTelemMaintenanceTaskRundown(unsigned __int8 a1, __int64 a2, unsigned __int8 a3)
{
  __int16 v3; // r12
  __int16 v5; // r15
  _QWORD *v6; // r14
  const WCHAR *v7; // rdx
  ULONG v8; // esi
  LONG result; // eax
  __int64 *v10; // rcx
  __int64 v11; // rax
  bool v12; // zf
  int v13; // eax
  int *v14; // rax
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  char IsCritical; // al
  __int64 v20; // rcx
  int v21; // r8d
  int v22; // r9d
  LONG v23; // eax
  FILETIME *p_dwHighDateTime; // rcx
  int v25; // r8d
  int v26; // r9d
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rdx
  ULONG HashValue; // [rsp+F0h] [rbp-80h] BYREF
  char v30; // [rsp+F4h] [rbp-7Ch] BYREF
  _BYTE v31[3]; // [rsp+F5h] [rbp-7Bh] BYREF
  unsigned int v32; // [rsp+F8h] [rbp-78h] BYREF
  __int16 v33; // [rsp+FCh] [rbp-74h] BYREF
  __int16 v34; // [rsp+FEh] [rbp-72h] BYREF
  __int16 v35; // [rsp+100h] [rbp-70h] BYREF
  __int16 v36; // [rsp+102h] [rbp-6Eh] BYREF
  __int16 v37; // [rsp+104h] [rbp-6Ch] BYREF
  __int16 v38; // [rsp+106h] [rbp-6Ah] BYREF
  __int16 v39; // [rsp+108h] [rbp-68h] BYREF
  __int16 v40; // [rsp+10Ah] [rbp-66h] BYREF
  __int16 v41; // [rsp+10Ch] [rbp-64h] BYREF
  __int16 v42; // [rsp+10Eh] [rbp-62h] BYREF
  __int16 v43; // [rsp+110h] [rbp-60h] BYREF
  __int16 v44; // [rsp+112h] [rbp-5Eh] BYREF
  __int16 v45; // [rsp+114h] [rbp-5Ch] BYREF
  __int16 v46; // [rsp+116h] [rbp-5Ah] BYREF
  ULONG v47; // [rsp+118h] [rbp-58h] BYREF
  int v48; // [rsp+11Ch] [rbp-54h] BYREF
  FILETIME v49; // [rsp+120h] [rbp-50h] BYREF
  FILETIME v50; // [rsp+128h] [rbp-48h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+130h] [rbp-40h] BYREF
  DWORD dwLowDateTime; // [rsp+140h] [rbp-30h] BYREF
  __int64 v53; // [rsp+148h] [rbp-28h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+150h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+158h] [rbp-18h] BYREF
  __int128 *v56; // [rsp+168h] [rbp-8h] BYREF
  __int64 v57; // [rsp+170h] [rbp+0h] BYREF
  __int64 v58; // [rsp+178h] [rbp+8h] BYREF
  FILETIME FileTime1[5]; // [rsp+180h] [rbp+10h] BYREF
  __int128 v60; // [rsp+1A8h] [rbp+38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+1C0h] [rbp+50h] BYREF
  int *v62; // [rsp+1D0h] [rbp+60h]
  int v63; // [rsp+1D8h] [rbp+68h]
  int v64; // [rsp+1DCh] [rbp+6Ch]
  ULONG *p_HashValue; // [rsp+1E0h] [rbp+70h]
  __int64 v66; // [rsp+1E8h] [rbp+78h]
  __int64 *v67; // [rsp+1F0h] [rbp+80h]
  int v68; // [rsp+1F8h] [rbp+88h]
  int v69; // [rsp+1FCh] [rbp+8Ch]

  v3 = a1;
  v53 = 0;
  v49 = 0;
  memset(FileTime1, 0, 36);
  v50 = 0;
  *(_QWORD *)&EventDescriptor.Id = 0;
  SystemTimeAsFileTime = 0;
  v60 = 0;
  v5 = a3;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  RtlAcquireSRWLockShared(&g_SystemSetup);
  v60 = xmmword_18004FB52;
  RtlReleaseSRWLockShared(&g_SystemSetup);
  v6 = *(_QWORD **)(a2 + 24);
  HashValue = 0;
  memset(FileTime1, 0, 36);
  v7 = (const WCHAR *)v6[1];
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, v7);
  v8 = 0;
  if ( RtlHashUnicodeString(&DestinationString, 1u, 1u, &HashValue) >= 0 )
    v8 = HashValue;
  if ( (unsigned int)UbpmStatsOperation(a2, 0, FileTime1) )
  {
    result = dword_18004F0F0;
    if ( (unsigned int)dword_18004F0F0 > 4 )
    {
      result = qword_18004F100;
      if ( (qword_18004F100 & 0x400000000000LL) != 0 )
      {
        result = 0;
        if ( (qword_18004F108 & 0x400000000000LL) == qword_18004F108 )
        {
          v10 = *(__int64 **)(*(_QWORD *)(a2 + 24) + 8LL);
          HashValue = v8;
          if ( v10 )
          {
            v11 = -1;
            do
              v12 = *((_WORD *)v10 + ++v11) == 0;
            while ( !v12 );
            v13 = 2 * v11 + 2;
          }
          else
          {
            v10 = &qword_1800439C0;
            v13 = 2;
          }
          v68 = v13;
          p_HashValue = &HashValue;
          *(_DWORD *)&EventDescriptor.Level = 4;
          UserData.Ptr = (ULONGLONG)off_18004F0F8;
          v67 = v10;
          v69 = 0;
          v66 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0x400000000000LL;
          UserData.Size = *(unsigned __int16 *)off_18004F0F8;
          v14 = &dword_1800469A4;
          v63 = 59;
LABEL_13:
          v62 = v14;
          UserData.Reserved = 2;
          v64 = 1;
          v32 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
        }
      }
    }
  }
  else if ( FileTime1[1].dwLowDateTime || FileTime1[0].dwHighDateTime )
  {
    if ( (unsigned int)dword_18004F0F0 > 4
      && (qword_18004F100 & 0x400000000000LL) != 0
      && (qword_18004F108 & 0x400000000000LL) == qword_18004F108 )
    {
      dwLowDateTime = FileTime1[3].dwLowDateTime;
      v56 = &v60;
      v57 = *(_QWORD *)&FileTime1[3].dwHighDateTime;
      v58 = *(_QWORD *)&FileTime1[1].dwHighDateTime;
      v18 = v6[5];
      v33 = v5;
      v47 = **(_DWORD **)(v18 + 32);
      IsCritical = UbpmpMaintenanceTaskIsCritical(a2);
      v20 = v6[6];
      v30 = IsCritical;
      v31[0] = *(_BYTE *)(v20 + 28);
      v34 = *(_WORD *)(v20 + 26);
      v35 = *(_WORD *)(v20 + 24);
      v36 = *(_WORD *)(v20 + 22);
      v37 = *(_WORD *)(v20 + 20);
      v38 = *(_WORD *)(v20 + 18);
      v39 = *(_WORD *)(v20 + 16);
      v40 = *(_WORD *)(v20 + 14);
      v41 = *(_WORD *)(v20 + 12);
      v42 = *(_WORD *)(v20 + 10);
      v43 = *(_WORD *)(v20 + 8);
      v44 = *(_WORD *)(v20 + 6);
      v45 = *(_WORD *)(v20 + 4);
      v46 = *(_WORD *)(v20 + 2);
      LOWORD(v32) = *(_WORD *)v20;
      *(_QWORD *)&DestinationString.Length = v6[1];
      LOWORD(HashValue) = v3;
      v48 = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        v20,
        (unsigned int)&byte_18004652F,
        v21,
        v22,
        (__int64)&v48,
        (__int64)&DestinationString,
        (__int64)&HashValue,
        (__int64)&v32,
        (__int64)&v46,
        (__int64)&v45,
        (__int64)&v44,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)v31,
        (__int64)&v30,
        (__int64)&v47,
        (__int64)&v33,
        (__int64)&v58,
        (__int64)&v57,
        (__int64)&v56,
        (__int64)&dwLowDateTime);
    }
    if ( !FileTime1[4].dwLowDateTime
      || !FileTime1[3].dwHighDateTime
      || (v23 = CompareFileTime(
                  (const FILETIME *)&FileTime1[0].dwHighDateTime,
                  (const FILETIME *)&FileTime1[3].dwHighDateTime),
          p_dwHighDateTime = (FILETIME *)&FileTime1[3].dwHighDateTime,
          v23 >= 0) )
    {
      p_dwHighDateTime = (FILETIME *)&FileTime1[0].dwHighDateTime;
    }
    result = UbpmpMaintenanceComputeCompletionPeriod(
               p_dwHighDateTime,
               (FILETIME *)&FileTime1[0].dwHighDateTime,
               *(struct _UBPM_TIMESPAN **)(*(_QWORD *)(a2 + 24) + 48LL),
               (__int64)&v49);
    if ( !result )
    {
      result = UbpmpMaintenanceComputeCompletionPeriod(
                 &SystemTimeAsFileTime,
                 (FILETIME *)&FileTime1[0].dwHighDateTime,
                 *(struct _UBPM_TIMESPAN **)(*(_QWORD *)(a2 + 24) + 48LL),
                 (__int64)&EventDescriptor);
      if ( !result )
      {
        result = CompareFileTime(&v49, &v50);
        if ( result < 0 )
        {
          result = 0;
          v27 = (*(_QWORD *)&v50 - *(_QWORD *)&v49) / 0x989680uLL;
          if ( v27 < 0x1518000000000LL )
          {
            v28 = v27 / 0x15180;
            result = v28 - 1;
            if ( (unsigned int)(v28 - 1) <= 0x3B )
            {
              result = dword_18004F0F0;
              if ( (unsigned int)dword_18004F0F0 > 4 )
              {
                result = qword_18004F100;
                if ( (qword_18004F100 & 0x400000000000LL) != 0 )
                {
                  result = 0;
                  if ( (qword_18004F108 & 0x400000000000LL) == qword_18004F108 )
                  {
                    v48 = v28;
                    v47 = v8;
                    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                             qword_18004F108,
                             (unsigned int)byte_180046C93,
                             v25,
                             v26,
                             (__int64)&v47,
                             (__int64)&v48);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    result = dword_18004F0F0;
    if ( (unsigned int)dword_18004F0F0 > 4 )
    {
      result = qword_18004F100;
      if ( (qword_18004F100 & 0x400000000000LL) != 0 )
      {
        result = 0;
        if ( (qword_18004F108 & 0x400000000000LL) == qword_18004F108 )
        {
          v15 = *(__int64 **)(*(_QWORD *)(a2 + 24) + 8LL);
          HashValue = v8;
          if ( v15 )
          {
            v16 = -1;
            do
              v12 = *((_WORD *)v15 + ++v16) == 0;
            while ( !v12 );
            v17 = 2 * v16 + 2;
          }
          else
          {
            v15 = &qword_1800439C0;
            v17 = 2;
          }
          v68 = v17;
          p_HashValue = &HashValue;
          *(_DWORD *)&EventDescriptor.Level = 4;
          UserData.Ptr = (ULONGLONG)off_18004F0F8;
          v67 = v15;
          v69 = 0;
          v66 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0x400000000000LL;
          UserData.Size = *(unsigned __int16 *)off_18004F0F8;
          v14 = (int *)byte_180046C53;
          v63 = 63;
          goto LABEL_13;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002ee00  push    rbp
0x18002ee02  push    rbx
0x18002ee03  push    rsi
0x18002ee04  push    rdi
0x18002ee05  push    r12
0x18002ee07  push    r13
0x18002ee09  push    r14
0x18002ee0b  push    r15
0x18002ee0d  lea     rbp, [rsp-0A8h]
0x18002ee15  sub     rsp, 218h
0x18002ee1c  mov     rax, cs:__security_cookie
0x18002ee23  xor     rax, rsp
0x18002ee26  mov     [rbp+0E0h+var_50], rax
0x18002ee2d  xor     r13d, r13d
0x18002ee30  movzx   r12d, cl
0x18002ee34  xorps   xmm0, xmm0
0x18002ee37  mov     [rbp+0E0h+var_108], r13
0x18002ee3b  xor     eax, eax
0x18002ee3d  mov     qword ptr [rbp+0E0h+var_130.dwLowDateTime], r13
0x18002ee41  lea     rcx, [rbp+0E0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002ee45  mov     [rbp+0E0h+var_B0], eax
0x18002ee48  movups  xmmword ptr [rbp+0E0h+FileTime1.dwLowDateTime], xmm0
0x18002ee4c  mov     qword ptr [rbp+0E0h+var_128.dwLowDateTime], r13
0x18002ee50  mov     rdi, rdx
0x18002ee53  movups  xmmword ptr [rbp+0E0h+FileTime2.dwLowDateTime], xmm0
0x18002ee57  mov     qword ptr [rbp+0E0h+EventDescriptor.Id], r13
0x18002ee5b  mov     qword ptr [rbp+0E0h+SystemTimeAsFileTime.dwLowDateTime], r13
0x18002ee5f  movups  [rbp+0E0h+var_A8], xmm0
0x18002ee63  movzx   r15d, r8b
0x18002ee67  call    cs:__imp_GetSystemTimeAsFileTime
0x18002ee6e  nop     dword ptr [rax+rax+00h]
0x18002ee73  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x18002ee7a  call    cs:__imp_RtlAcquireSRWLockShared
0x18002ee81  nop     dword ptr [rax+rax+00h]
0x18002ee86  movups  xmm0, cs:xmmword_18004FB52
0x18002ee8d  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x18002ee94  movups  [rbp+0E0h+var_A8], xmm0
0x18002ee98  call    cs:__imp_RtlReleaseSRWLockShared
0x18002ee9f  nop     dword ptr [rax+rax+00h]
0x18002eea4  mov     r14, [rdi+18h]
0x18002eea8  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x18002eeac  xorps   xmm0, xmm0
0x18002eeaf  mov     [rbp+0E0h+HashValue], r13d
0x18002eeb3  xor     eax, eax
0x18002eeb5  movups  xmmword ptr [rbp+0E0h+FileTime1.dwLowDateTime], xmm0
0x18002eeb9  mov     [rbp+0E0h+var_B0], eax
0x18002eebc  movups  xmmword ptr [rbp+0E0h+FileTime2.dwLowDateTime], xmm0
0x18002eec0  mov     rdx, [r14+8]; SourceString
0x18002eec4  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x18002eec8  call    cs:__imp_RtlInitUnicodeString
0x18002eecf  nop     dword ptr [rax+rax+00h]
0x18002eed4  mov     r8d, 1; HashAlgorithm
0x18002eeda  lea     r9, [rbp+0E0h+HashValue]; HashValue
0x18002eede  movzx   edx, r8b; CaseInSensitive
0x18002eee2  lea     rcx, [rbp+0E0h+DestinationString]; String
0x18002eee6  call    cs:__imp_RtlHashUnicodeString
0x18002eeed  nop     dword ptr [rax+rax+00h]
0x18002eef2  mov     esi, r13d
0x18002eef5  lea     r8, [rbp+0E0h+FileTime1]
0x18002eef9  test    eax, eax
0x18002eefb  mov     rcx, rdi
0x18002eefe  cmovns  esi, [rbp+0E0h+HashValue]
0x18002ef02  xor     edx, edx
0x18002ef04  call    UbpmStatsOperation
0x18002ef09  test    eax, eax
0x18002ef0b  jz      loc_18002F044
0x18002ef11  mov     eax, cs:dword_18004F0F0
0x18002ef17  cmp     eax, 4
0x18002ef1a  jbe     loc_18002F481
0x18002ef20  mov     rcx, cs:qword_18004F108
0x18002ef27  mov     rbx, 400000000000h
0x18002ef31  mov     rax, cs:qword_18004F100
0x18002ef38  test    rbx, rax
0x18002ef3b  jz      loc_18002F481
0x18002ef41  mov     rax, rcx
0x18002ef44  and     rax, rbx
0x18002ef47  cmp     rax, rcx
0x18002ef4a  jnz     loc_18002F481
0x18002ef50  mov     rax, [rdi+18h]
0x18002ef54  mov     rcx, [rax+8]
0x18002ef58  mov     [rbp+0E0h+HashValue], esi
0x18002ef5b  test    rcx, rcx
0x18002ef5e  jz      short loc_18002EF85
0x18002ef60  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002ef67  nop     word ptr [rax+rax+00000000h]
0x18002ef70  cmp     [rcx+rax*2+2], r13w
0x18002ef76  lea     rax, [rax+1]
0x18002ef7a  jnz     short loc_18002EF70
0x18002ef7c  lea     eax, ds:2[rax*2]
0x18002ef83  jmp     short loc_18002EF91
0x18002ef85  lea     rcx, qword_1800439C0
0x18002ef8c  mov     eax, 2
0x18002ef91  mov     [rbp+0E0h+var_58], eax
0x18002ef97  lea     rax, [rbp+0E0h+HashValue]
0x18002ef9b  mov     [rbp+0E0h+var_70], rax
0x18002ef9f  movzx   eax, cs:word_18004699A
0x18002efa6  mov     dword ptr [rbp+0E0h+EventDescriptor.Level], eax
0x18002efa9  mov     rax, cs:off_18004F0F8
0x18002efb0  mov     [rbp+0E0h+var_90.Ptr], rax
0x18002efb4  mov     [rbp+0E0h+var_60], rcx
0x18002efbb  mov     [rbp+0E0h+var_54], r13d
0x18002efc2  mov     [rbp+0E0h+var_68], 4
0x18002efca  mov     dword ptr [rbp+0E0h+EventDescriptor.Id], 0B000000h
0x18002efd1  mov     [rbp+0E0h+EventDescriptor.Keyword], rbx
0x18002efd5  movzx   eax, word ptr [rax]
0x18002efd8  mov     [rbp+0E0h+var_90.Size], eax
0x18002efdb  lea     rax, dword_1800469A4
0x18002efe2  mov     [rbp+0E0h+var_78], 3Bh ; ';'
0x18002efe9  mov     [rbp+0E0h+var_80], rax
0x18002efed  lea     rcx, _TraceLoggingMetadata
0x18002eff4  lea     rax, _TraceLoggingMetadataEnd
0x18002effb  mov     dword ptr [rbp+0E0h+var_90.0Ch], 2
0x18002f002  sub     eax, ecx
0x18002f004  mov     [rbp+0E0h+var_74], 1
0x18002f00b  mov     [rbp+0E0h+var_158], eax
0x18002f00e  lea     rdx, [rbp+0E0h+EventDescriptor]; EventDescriptor
0x18002f012  mov     eax, [rbp+0E0h+var_158]
0x18002f015  xor     r9d, r9d; RelatedActivityId
0x18002f018  mov     rcx, cs:RegHandle; RegHandle
0x18002f01f  lea     rax, [rbp+0E0h+var_90]
0x18002f023  mov     [rsp+250h+UserData], rax; UserData
0x18002f028  xor     r8d, r8d; ActivityId
0x18002f02b  mov     [rsp+250h+UserDataCount], 4; UserDataCount
0x18002f033  call    cs:__imp_EventWriteTransfer
0x18002f03a  nop     dword ptr [rax+rax+00h]
0x18002f03f  jmp     loc_18002F481
0x18002f044  cmp     [rbp+0E0h+FileTime1.dwLowDateTime+8], r13d
0x18002f048  jnz     loc_18002F12E
0x18002f04e  cmp     [rbp+0E0h+FileTime1.dwHighDateTime], r13d
0x18002f052  jnz     loc_18002F12E
0x18002f058  mov     eax, cs:dword_18004F0F0
0x18002f05e  cmp     eax, 4
0x18002f061  jbe     loc_18002F481
0x18002f067  mov     rcx, cs:qword_18004F108
0x18002f06e  mov     rbx, 400000000000h
0x18002f078  mov     rax, cs:qword_18004F100
0x18002f07f  test    rbx, rax
0x18002f082  jz      loc_18002F481
0x18002f088  mov     rax, rcx
0x18002f08b  and     rax, rbx
0x18002f08e  cmp     rax, rcx
0x18002f091  jnz     loc_18002F481
0x18002f097  mov     rax, [rdi+18h]
0x18002f09b  mov     rcx, [rax+8]
0x18002f09f  mov     [rbp+0E0h+HashValue], esi
0x18002f0a2  test    rcx, rcx
0x18002f0a5  jz      short loc_18002F0C5
0x18002f0a7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002f0ae  xchg    ax, ax
0x18002f0b0  cmp     [rcx+rax*2+2], r13w
0x18002f0b6  lea     rax, [rax+1]
0x18002f0ba  jnz     short loc_18002F0B0
0x18002f0bc  lea     eax, ds:2[rax*2]
0x18002f0c3  jmp     short loc_18002F0D1
0x18002f0c5  lea     rcx, qword_1800439C0
0x18002f0cc  mov     eax, 2
0x18002f0d1  mov     [rbp+0E0h+var_58], eax
0x18002f0d7  lea     rax, [rbp+0E0h+HashValue]
0x18002f0db  mov     [rbp+0E0h+var_70], rax
0x18002f0df  movzx   eax, cs:word_180046C49
0x18002f0e6  mov     dword ptr [rbp+0E0h+EventDescriptor.Level], eax
0x18002f0e9  mov     rax, cs:off_18004F0F8
0x18002f0f0  mov     [rbp+0E0h+var_90.Ptr], rax
0x18002f0f4  mov     [rbp+0E0h+var_60], rcx
0x18002f0fb  mov     [rbp+0E0h+var_54], r13d
0x18002f102  mov     [rbp+0E0h+var_68], 4
0x18002f10a  mov     dword ptr [rbp+0E0h+EventDescriptor.Id], 0B000000h
0x18002f111  mov     [rbp+0E0h+EventDescriptor.Keyword], rbx
0x18002f115  movzx   eax, word ptr [rax]
0x18002f118  mov     [rbp+0E0h+var_90.Size], eax
0x18002f11b  lea     rax, byte_180046C53
0x18002f122  mov     [rbp+0E0h+var_78], 3Fh ; '?'
0x18002f129  jmp     loc_18002EFE9
0x18002f12e  mov     eax, cs:dword_18004F0F0
0x18002f134  mov     rbx, 400000000000h
0x18002f13e  cmp     eax, 4
0x18002f141  jbe     loc_18002F346
0x18002f147  mov     rcx, cs:qword_18004F108
0x18002f14e  mov     rax, cs:qword_18004F100
0x18002f155  test    rbx, rax
0x18002f158  jz      loc_18002F346
0x18002f15e  mov     rax, rcx
0x18002f161  and     rax, rbx
0x18002f164  cmp     rax, rcx
0x18002f167  jnz     loc_18002F346
0x18002f16d  mov     eax, [rbp+0E0h+FileTime2.dwLowDateTime+8]
0x18002f170  mov     [rbp+0E0h+var_110], eax
0x18002f173  lea     rax, [rbp+0E0h+var_A8]
0x18002f177  mov     [rbp+0E0h+var_E8], rax
0x18002f17b  mov     rax, qword ptr [rbp+0E0h+FileTime2.dwHighDateTime+8]
0x18002f17f  mov     [rbp+0E0h+var_E0], rax
0x18002f183  mov     rax, qword ptr [rbp+0E0h+FileTime1.dwHighDateTime+8]
0x18002f187  mov     [rbp+0E0h+var_D8], rax
0x18002f18b  mov     rax, [r14+28h]
0x18002f18f  mov     [rbp+0E0h+var_154], r15w
0x18002f194  mov     rcx, [rax+20h]
0x18002f198  mov     eax, [rcx]
0x18002f19a  mov     rcx, rdi
0x18002f19d  mov     [rbp+0E0h+var_138], eax
0x18002f1a0  call    UbpmpMaintenanceTaskIsCritical
0x18002f1a5  mov     rcx, [r14+30h]
0x18002f1a9  mov     [rbp+0E0h+var_15C], al
0x18002f1ac  movzx   eax, byte ptr [rcx+1Ch]
0x18002f1b0  mov     [rbp+0E0h+var_15B], al
0x18002f1b3  movzx   eax, word ptr [rcx+1Ah]
0x18002f1b7  mov     [rbp+0E0h+var_152], ax
0x18002f1bb  movzx   eax, word ptr [rcx+18h]
0x18002f1bf  mov     [rbp+0E0h+var_150], ax
0x18002f1c3  movzx   eax, word ptr [rcx+16h]
0x18002f1c7  mov     [rbp+0E0h+var_14E], ax
0x18002f1cb  movzx   eax, word ptr [rcx+14h]
0x18002f1cf  mov     [rbp+0E0h+var_14C], ax
0x18002f1d3  movzx   eax, word ptr [rcx+12h]
0x18002f1d7  mov     [rbp+0E0h+var_14A], ax
0x18002f1db  movzx   eax, word ptr [rcx+10h]
0x18002f1df  mov     [rbp+0E0h+var_148], ax
0x18002f1e3  movzx   eax, word ptr [rcx+0Eh]
0x18002f1e7  mov     [rbp+0E0h+var_146], ax
0x18002f1eb  movzx   eax, word ptr [rcx+0Ch]
0x18002f1ef  mov     [rbp+0E0h+var_144], ax
0x18002f1f3  movzx   eax, word ptr [rcx+0Ah]
0x18002f1f7  mov     [rbp+0E0h+var_142], ax
0x18002f1fb  movzx   eax, word ptr [rcx+8]
0x18002f1ff  mov     [rbp+0E0h+var_140], ax
0x18002f203  movzx   eax, word ptr [rcx+6]
0x18002f207  mov     [rbp+0E0h+var_13E], ax
0x18002f20b  movzx   eax, word ptr [rcx+4]
0x18002f20f  mov     [rbp+0E0h+var_13C], ax
0x18002f213  movzx   eax, word ptr [rcx+2]
0x18002f217  mov     [rbp+0E0h+var_13A], ax
0x18002f21b  movzx   eax, word ptr [rcx]
0x18002f21e  mov     word ptr [rbp+0E0h+var_158], ax
0x18002f222  mov     rax, [r14+8]
0x18002f226  mov     qword ptr [rbp+0E0h+DestinationString.Length], rax
0x18002f22a  lea     rax, [rbp+0E0h+var_110]
0x18002f22e  mov     [rsp+250h+var_170], rax
0x18002f236  lea     rax, [rbp+0E0h+var_E8]
0x18002f23a  mov     [rsp+250h+var_178], rax
0x18002f242  lea     rax, [rbp+0E0h+var_E0]
0x18002f246  mov     [rsp+250h+var_180], rax
0x18002f24e  lea     rax, [rbp+0E0h+var_D8]
0x18002f252  mov     [rsp+250h+var_188], rax
0x18002f25a  lea     rax, [rbp+0E0h+var_154]
0x18002f25e  mov     [rsp+250h+var_190], rax
0x18002f266  lea     rax, [rbp+0E0h+var_138]
0x18002f26a  mov     [rsp+250h+var_198], rax
0x18002f272  lea     rax, [rbp+0E0h+var_15C]
0x18002f276  mov     [rsp+250h+var_1A0], rax
0x18002f27e  lea     rax, [rbp+0E0h+var_15B]
0x18002f282  mov     [rsp+250h+var_1A8], rax
0x18002f28a  lea     rax, [rbp+0E0h+var_152]
0x18002f28e  mov     [rsp+250h+var_1B0], rax
0x18002f296  lea     rax, [rbp+0E0h+var_150]
0x18002f29a  mov     [rsp+250h+var_1B8], rax
0x18002f2a2  lea     rax, [rbp+0E0h+var_14E]
0x18002f2a6  mov     [rsp+250h+var_1C0], rax
0x18002f2ae  lea     rax, [rbp+0E0h+var_14C]
0x18002f2b2  mov     [rsp+250h+var_1C8], rax
0x18002f2ba  lea     rax, [rbp+0E0h+var_14A]
0x18002f2be  mov     [rsp+250h+var_1D0], rax
0x18002f2c6  lea     rax, [rbp+0E0h+var_148]
0x18002f2ca  mov     [rsp+250h+var_1D8], rax
0x18002f2cf  lea     rax, [rbp+0E0h+var_146]
0x18002f2d3  mov     [rsp+250h+var_1E0], rax
0x18002f2d8  mov     word ptr [rbp+0E0h+HashValue], r12w
0x18002f2dd  mov     [rbp+0E0h+var_134], esi
0x18002f2e0  lea     rax, [rbp+0E0h+var_144]
0x18002f2e4  mov     [rsp+250h+var_1E8], rax
0x18002f2e9  lea     rdx, byte_18004652F
0x18002f2f0  lea     rax, [rbp+0E0h+var_142]
0x18002f2f4  mov     [rsp+250h+var_1F0], rax
0x18002f2f9  lea     rax, [rbp+0E0h+var_140]
0x18002f2fd  mov     [rsp+250h+var_1F8], rax
0x18002f302  lea     rax, [rbp+0E0h+var_13E]
0x18002f306  mov     [rsp+250h+var_200], rax
0x18002f30b  lea     rax, [rbp+0E0h+var_13C]
0x18002f30f  mov     [rsp+250h+var_208], rax
0x18002f314  lea     rax, [rbp+0E0h+var_13A]
0x18002f318  mov     [rsp+250h+var_210], rax
0x18002f31d  lea     rax, [rbp+0E0h+var_158]
0x18002f321  mov     [rsp+250h+var_218], rax
0x18002f326  lea     rax, [rbp+0E0h+HashValue]
0x18002f32a  mov     [rsp+250h+var_220], rax
0x18002f32f  lea     rax, [rbp+0E0h+DestinationString]
0x18002f333  mov     [rsp+250h+UserData], rax
0x18002f338  lea     rax, [rbp+0E0h+var_134]
0x18002f33c  mov     qword ptr [rsp+250h+UserDataCount], rax
0x18002f341  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U?$_tlgWrapperByVal@$00@@U4@U1@U3@U?$_tlgWrapperByVal@$07@@U5@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@55555555555555AEBU?$_tlgWrapperByVal@$00@@635AEBU?$_tlgWrapperByVal@$07@@7AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18002f346  cmp     [rbp+0E0h+var_B0], r13d
0x18002f34a  jz      short loc_18002F36E
0x18002f34c  cmp     [rbp+0E0h+FileTime2.dwHighDateTime+8], r13d
0x18002f350  jz      short loc_18002F36E
0x18002f352  lea     rdx, [rbp+0E0h+FileTime2.dwHighDateTime+8]; lpFileTime2
0x18002f356  lea     rcx, [rbp+0E0h+FileTime1.dwHighDateTime]; lpFileTime1
0x18002f35a  call    cs:__imp_CompareFileTime
0x18002f361  nop     dword ptr [rax+rax+00h]
0x18002f366  lea     rcx, [rbp+0E0h+FileTime2.dwHighDateTime+8]
0x18002f36a  test    eax, eax
0x18002f36c  js      short loc_18002F372
0x18002f36e  lea     rcx, [rbp+0E0h+FileTime1.dwHighDateTime]; lpFileTime2
  ... truncated ...
```
