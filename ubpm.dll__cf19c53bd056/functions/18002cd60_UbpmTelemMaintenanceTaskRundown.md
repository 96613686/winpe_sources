# UbpmTelemMaintenanceTaskRundown

- ea: `0x18002cd60`
- end: `0x18002d3d8`
- name: `UbpmTelemMaintenanceTaskRundown`
- size: `1656`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002eb98`
- `0x180036940`

## callees

- `0x1800139cc`
- `0x180015e10`
- `0x1800160b0`
- `0x180025ddc`
- `0x1800295cc`
- `0x18002cd60`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002ce16`
- `ntdll!RtlInitUnicodeString` at `0x18002ce16`
- `ntdll!RtlHashUnicodeString` at `0x18002ce2e`
- `ntdll!RtlHashUnicodeString` at `0x18002ce2e`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002cdec`
- `ntdll!RtlReleaseSRWLockShared` at `0x18002cdec`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002cdd4`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002cdd4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002cf73`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002cf73`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002cdc7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002cdc7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002d29a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002d304`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002d29a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002d304`

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
  int *v10; // rcx
  __int64 v11; // rax
  bool v12; // zf
  int v13; // eax
  int *v14; // rax
  int *v15; // rcx
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
  int *v67; // [rsp+1F0h] [rbp+80h]
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
  v60 = xmmword_18004CA52;
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
    result = dword_18004C0F0;
    if ( (unsigned int)dword_18004C0F0 > 4 )
    {
      result = qword_18004C100;
      if ( (qword_18004C100 & 0x400000000000LL) != 0 )
      {
        result = 0;
        if ( (qword_18004C108 & 0x400000000000LL) == qword_18004C108 )
        {
          v10 = *(int **)(*(_QWORD *)(a2 + 24) + 8LL);
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
            v10 = &dword_1800405F4;
            v13 = 2;
          }
          v68 = v13;
          p_HashValue = &HashValue;
          *(_DWORD *)&EventDescriptor.Level = 4;
          UserData.Ptr = (ULONGLONG)off_18004C0F8;
          v67 = v10;
          v69 = 0;
          v66 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0x400000000000LL;
          UserData.Size = *(unsigned __int16 *)off_18004C0F8;
          v14 = &dword_18004393C;
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
    if ( (unsigned int)dword_18004C0F0 > 4
      && (qword_18004C100 & 0x400000000000LL) != 0
      && (qword_18004C108 & 0x400000000000LL) == qword_18004C108 )
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
        (unsigned int)&byte_1800434C7,
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
               (__int64)&v49);
    if ( !result )
    {
      result = UbpmpMaintenanceComputeCompletionPeriod(
                 &SystemTimeAsFileTime,
                 (FILETIME *)&FileTime1[0].dwHighDateTime,
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
              result = dword_18004C0F0;
              if ( (unsigned int)dword_18004C0F0 > 4 )
              {
                result = qword_18004C100;
                if ( (qword_18004C100 & 0x400000000000LL) != 0 )
                {
                  result = 0;
                  if ( (qword_18004C108 & 0x400000000000LL) == qword_18004C108 )
                  {
                    v48 = v28;
                    v47 = v8;
                    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                             qword_18004C108,
                             (unsigned int)byte_180043C2B,
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
    result = dword_18004C0F0;
    if ( (unsigned int)dword_18004C0F0 > 4 )
    {
      result = qword_18004C100;
      if ( (qword_18004C100 & 0x400000000000LL) != 0 )
      {
        result = 0;
        if ( (qword_18004C108 & 0x400000000000LL) == qword_18004C108 )
        {
          v15 = *(int **)(*(_QWORD *)(a2 + 24) + 8LL);
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
            v15 = &dword_1800405F4;
            v17 = 2;
          }
          v68 = v17;
          p_HashValue = &HashValue;
          *(_DWORD *)&EventDescriptor.Level = 4;
          UserData.Ptr = (ULONGLONG)off_18004C0F8;
          v67 = v15;
          v69 = 0;
          v66 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0x400000000000LL;
          UserData.Size = *(unsigned __int16 *)off_18004C0F8;
          v14 = (int *)byte_180043BEB;
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
0x18002cd60  push    rbp
0x18002cd62  push    rbx
0x18002cd63  push    rsi
0x18002cd64  push    rdi
0x18002cd65  push    r12
0x18002cd67  push    r13
0x18002cd69  push    r14
0x18002cd6b  push    r15
0x18002cd6d  lea     rbp, [rsp-0A8h]
0x18002cd75  sub     rsp, 218h
0x18002cd7c  mov     rax, cs:__security_cookie
0x18002cd83  xor     rax, rsp
0x18002cd86  mov     [rbp+0E0h+var_50], rax
0x18002cd8d  xor     r13d, r13d
0x18002cd90  movzx   r12d, cl
0x18002cd94  xorps   xmm0, xmm0
0x18002cd97  mov     [rbp+0E0h+var_108], r13
0x18002cd9b  xor     eax, eax
0x18002cd9d  mov     qword ptr [rbp+0E0h+var_130.dwLowDateTime], r13
0x18002cda1  lea     rcx, [rbp+0E0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002cda5  mov     [rbp+0E0h+var_B0], eax
0x18002cda8  movups  xmmword ptr [rbp+0E0h+FileTime1.dwLowDateTime], xmm0
0x18002cdac  mov     qword ptr [rbp+0E0h+var_128.dwLowDateTime], r13
0x18002cdb0  mov     rdi, rdx
0x18002cdb3  movups  xmmword ptr [rbp+0E0h+FileTime2.dwLowDateTime], xmm0
0x18002cdb7  mov     qword ptr [rbp+0E0h+EventDescriptor.Id], r13
0x18002cdbb  mov     qword ptr [rbp+0E0h+SystemTimeAsFileTime.dwLowDateTime], r13
0x18002cdbf  movups  [rbp+0E0h+var_A8], xmm0
0x18002cdc3  movzx   r15d, r8b
0x18002cdc7  call    cs:__imp_GetSystemTimeAsFileTime
0x18002cdcd  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x18002cdd4  call    cs:__imp_RtlAcquireSRWLockShared
0x18002cdda  movups  xmm0, cs:xmmword_18004CA52
0x18002cde1  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x18002cde8  movups  [rbp+0E0h+var_A8], xmm0
0x18002cdec  call    cs:__imp_RtlReleaseSRWLockShared
0x18002cdf2  mov     r14, [rdi+18h]
0x18002cdf6  lea     rcx, [rbp+0E0h+DestinationString]; DestinationString
0x18002cdfa  xorps   xmm0, xmm0
0x18002cdfd  mov     [rbp+0E0h+HashValue], r13d
0x18002ce01  xor     eax, eax
0x18002ce03  movups  xmmword ptr [rbp+0E0h+FileTime1.dwLowDateTime], xmm0
0x18002ce07  mov     [rbp+0E0h+var_B0], eax
0x18002ce0a  movups  xmmword ptr [rbp+0E0h+FileTime2.dwLowDateTime], xmm0
0x18002ce0e  mov     rdx, [r14+8]; SourceString
0x18002ce12  movups  xmmword ptr [rbp+0E0h+DestinationString.Length], xmm0
0x18002ce16  call    cs:__imp_RtlInitUnicodeString
0x18002ce1c  mov     r8d, 1; HashAlgorithm
0x18002ce22  lea     r9, [rbp+0E0h+HashValue]; HashValue
0x18002ce26  movzx   edx, r8b; CaseInSensitive
0x18002ce2a  lea     rcx, [rbp+0E0h+DestinationString]; String
0x18002ce2e  call    cs:__imp_RtlHashUnicodeString
0x18002ce34  mov     esi, r13d
0x18002ce37  lea     r8, [rbp+0E0h+FileTime1]
0x18002ce3b  test    eax, eax
0x18002ce3d  mov     rcx, rdi
0x18002ce40  cmovns  esi, [rbp+0E0h+HashValue]
0x18002ce44  xor     edx, edx
0x18002ce46  call    UbpmStatsOperation
0x18002ce4b  test    eax, eax
0x18002ce4d  jz      loc_18002CF7E
0x18002ce53  mov     eax, cs:dword_18004C0F0
0x18002ce59  cmp     eax, 4
0x18002ce5c  jbe     loc_18002D3B5
0x18002ce62  mov     rcx, cs:qword_18004C108
0x18002ce69  mov     rbx, 400000000000h
0x18002ce73  mov     rax, cs:qword_18004C100
0x18002ce7a  test    rbx, rax
0x18002ce7d  jz      loc_18002D3B5
0x18002ce83  mov     rax, rcx
0x18002ce86  and     rax, rbx
0x18002ce89  cmp     rax, rcx
0x18002ce8c  jnz     loc_18002D3B5
0x18002ce92  mov     rax, [rdi+18h]
0x18002ce96  mov     rcx, [rax+8]
0x18002ce9a  mov     [rbp+0E0h+HashValue], esi
0x18002ce9d  test    rcx, rcx
0x18002cea0  jz      short loc_18002CEC5
0x18002cea2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002cea9  nop     dword ptr [rax+00000000h]
0x18002ceb0  cmp     [rcx+rax*2+2], r13w
0x18002ceb6  lea     rax, [rax+1]
0x18002ceba  jnz     short loc_18002CEB0
0x18002cebc  lea     eax, ds:2[rax*2]
0x18002cec3  jmp     short loc_18002CED1
0x18002cec5  lea     rcx, dword_1800405F4
0x18002cecc  mov     eax, 2
0x18002ced1  mov     [rbp+0E0h+var_58], eax
0x18002ced7  lea     rax, [rbp+0E0h+HashValue]
0x18002cedb  mov     [rbp+0E0h+var_70], rax
0x18002cedf  movzx   eax, cs:word_180043932
0x18002cee6  mov     dword ptr [rbp+0E0h+EventDescriptor.Level], eax
0x18002cee9  mov     rax, cs:off_18004C0F8
0x18002cef0  mov     [rbp+0E0h+var_90.Ptr], rax
0x18002cef4  mov     [rbp+0E0h+var_60], rcx
0x18002cefb  mov     [rbp+0E0h+var_54], r13d
0x18002cf02  mov     [rbp+0E0h+var_68], 4
0x18002cf0a  mov     dword ptr [rbp+0E0h+EventDescriptor.Id], 0B000000h
0x18002cf11  mov     [rbp+0E0h+EventDescriptor.Keyword], rbx
0x18002cf15  movzx   eax, word ptr [rax]
0x18002cf18  mov     [rbp+0E0h+var_90.Size], eax
0x18002cf1b  lea     rax, dword_18004393C
0x18002cf22  mov     [rbp+0E0h+var_78], 3Bh ; ';'
0x18002cf29  mov     [rbp+0E0h+var_80], rax
0x18002cf2d  lea     rcx, _TraceLoggingMetadata
0x18002cf34  lea     rax, _TraceLoggingMetadataEnd
0x18002cf3b  mov     dword ptr [rbp+0E0h+var_90.0Ch], 2
0x18002cf42  sub     eax, ecx
0x18002cf44  mov     [rbp+0E0h+var_74], 1
0x18002cf4b  mov     [rbp+0E0h+var_158], eax
0x18002cf4e  lea     rdx, [rbp+0E0h+EventDescriptor]; EventDescriptor
0x18002cf52  mov     eax, [rbp+0E0h+var_158]
0x18002cf55  xor     r9d, r9d; RelatedActivityId
0x18002cf58  mov     rcx, cs:RegHandle; RegHandle
0x18002cf5f  lea     rax, [rbp+0E0h+var_90]
0x18002cf63  mov     [rsp+250h+UserData], rax; UserData
0x18002cf68  xor     r8d, r8d; ActivityId
0x18002cf6b  mov     [rsp+250h+UserDataCount], 4; UserDataCount
0x18002cf73  call    cs:__imp_EventWriteTransfer
0x18002cf79  jmp     loc_18002D3B5
0x18002cf7e  cmp     [rbp+0E0h+FileTime1.dwLowDateTime+8], r13d
0x18002cf82  jnz     loc_18002D06E
0x18002cf88  cmp     [rbp+0E0h+FileTime1.dwHighDateTime], r13d
0x18002cf8c  jnz     loc_18002D06E
0x18002cf92  mov     eax, cs:dword_18004C0F0
0x18002cf98  cmp     eax, 4
0x18002cf9b  jbe     loc_18002D3B5
0x18002cfa1  mov     rcx, cs:qword_18004C108
0x18002cfa8  mov     rbx, 400000000000h
0x18002cfb2  mov     rax, cs:qword_18004C100
0x18002cfb9  test    rbx, rax
0x18002cfbc  jz      loc_18002D3B5
0x18002cfc2  mov     rax, rcx
0x18002cfc5  and     rax, rbx
0x18002cfc8  cmp     rax, rcx
0x18002cfcb  jnz     loc_18002D3B5
0x18002cfd1  mov     rax, [rdi+18h]
0x18002cfd5  mov     rcx, [rax+8]
0x18002cfd9  mov     [rbp+0E0h+HashValue], esi
0x18002cfdc  test    rcx, rcx
0x18002cfdf  jz      short loc_18002D005
0x18002cfe1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002cfe8  nop     dword ptr [rax+rax+00000000h]
0x18002cff0  cmp     [rcx+rax*2+2], r13w
0x18002cff6  lea     rax, [rax+1]
0x18002cffa  jnz     short loc_18002CFF0
0x18002cffc  lea     eax, ds:2[rax*2]
0x18002d003  jmp     short loc_18002D011
0x18002d005  lea     rcx, dword_1800405F4
0x18002d00c  mov     eax, 2
0x18002d011  mov     [rbp+0E0h+var_58], eax
0x18002d017  lea     rax, [rbp+0E0h+HashValue]
0x18002d01b  mov     [rbp+0E0h+var_70], rax
0x18002d01f  movzx   eax, cs:word_180043BE1
0x18002d026  mov     dword ptr [rbp+0E0h+EventDescriptor.Level], eax
0x18002d029  mov     rax, cs:off_18004C0F8
0x18002d030  mov     [rbp+0E0h+var_90.Ptr], rax
0x18002d034  mov     [rbp+0E0h+var_60], rcx
0x18002d03b  mov     [rbp+0E0h+var_54], r13d
0x18002d042  mov     [rbp+0E0h+var_68], 4
0x18002d04a  mov     dword ptr [rbp+0E0h+EventDescriptor.Id], 0B000000h
0x18002d051  mov     [rbp+0E0h+EventDescriptor.Keyword], rbx
0x18002d055  movzx   eax, word ptr [rax]
0x18002d058  mov     [rbp+0E0h+var_90.Size], eax
0x18002d05b  lea     rax, byte_180043BEB
0x18002d062  mov     [rbp+0E0h+var_78], 3Fh ; '?'
0x18002d069  jmp     loc_18002CF29
0x18002d06e  mov     eax, cs:dword_18004C0F0
0x18002d074  mov     rbx, 400000000000h
0x18002d07e  cmp     eax, 4
0x18002d081  jbe     loc_18002D286
0x18002d087  mov     rcx, cs:qword_18004C108
0x18002d08e  mov     rax, cs:qword_18004C100
0x18002d095  test    rbx, rax
0x18002d098  jz      loc_18002D286
0x18002d09e  mov     rax, rcx
0x18002d0a1  and     rax, rbx
0x18002d0a4  cmp     rax, rcx
0x18002d0a7  jnz     loc_18002D286
0x18002d0ad  mov     eax, [rbp+0E0h+FileTime2.dwLowDateTime+8]
0x18002d0b0  mov     [rbp+0E0h+var_110], eax
0x18002d0b3  lea     rax, [rbp+0E0h+var_A8]
0x18002d0b7  mov     [rbp+0E0h+var_E8], rax
0x18002d0bb  mov     rax, qword ptr [rbp+0E0h+FileTime2.dwHighDateTime+8]
0x18002d0bf  mov     [rbp+0E0h+var_E0], rax
0x18002d0c3  mov     rax, qword ptr [rbp+0E0h+FileTime1.dwHighDateTime+8]
0x18002d0c7  mov     [rbp+0E0h+var_D8], rax
0x18002d0cb  mov     rax, [r14+28h]
0x18002d0cf  mov     [rbp+0E0h+var_154], r15w
0x18002d0d4  mov     rcx, [rax+20h]
0x18002d0d8  mov     eax, [rcx]
0x18002d0da  mov     rcx, rdi
0x18002d0dd  mov     [rbp+0E0h+var_138], eax
0x18002d0e0  call    UbpmpMaintenanceTaskIsCritical
0x18002d0e5  mov     rcx, [r14+30h]
0x18002d0e9  mov     [rbp+0E0h+var_15C], al
0x18002d0ec  movzx   eax, byte ptr [rcx+1Ch]
0x18002d0f0  mov     [rbp+0E0h+var_15B], al
0x18002d0f3  movzx   eax, word ptr [rcx+1Ah]
0x18002d0f7  mov     [rbp+0E0h+var_152], ax
0x18002d0fb  movzx   eax, word ptr [rcx+18h]
0x18002d0ff  mov     [rbp+0E0h+var_150], ax
0x18002d103  movzx   eax, word ptr [rcx+16h]
0x18002d107  mov     [rbp+0E0h+var_14E], ax
0x18002d10b  movzx   eax, word ptr [rcx+14h]
0x18002d10f  mov     [rbp+0E0h+var_14C], ax
0x18002d113  movzx   eax, word ptr [rcx+12h]
0x18002d117  mov     [rbp+0E0h+var_14A], ax
0x18002d11b  movzx   eax, word ptr [rcx+10h]
0x18002d11f  mov     [rbp+0E0h+var_148], ax
0x18002d123  movzx   eax, word ptr [rcx+0Eh]
0x18002d127  mov     [rbp+0E0h+var_146], ax
0x18002d12b  movzx   eax, word ptr [rcx+0Ch]
0x18002d12f  mov     [rbp+0E0h+var_144], ax
0x18002d133  movzx   eax, word ptr [rcx+0Ah]
0x18002d137  mov     [rbp+0E0h+var_142], ax
0x18002d13b  movzx   eax, word ptr [rcx+8]
0x18002d13f  mov     [rbp+0E0h+var_140], ax
0x18002d143  movzx   eax, word ptr [rcx+6]
0x18002d147  mov     [rbp+0E0h+var_13E], ax
0x18002d14b  movzx   eax, word ptr [rcx+4]
0x18002d14f  mov     [rbp+0E0h+var_13C], ax
0x18002d153  movzx   eax, word ptr [rcx+2]
0x18002d157  mov     [rbp+0E0h+var_13A], ax
0x18002d15b  movzx   eax, word ptr [rcx]
0x18002d15e  mov     word ptr [rbp+0E0h+var_158], ax
0x18002d162  mov     rax, [r14+8]
0x18002d166  mov     qword ptr [rbp+0E0h+DestinationString.Length], rax
0x18002d16a  lea     rax, [rbp+0E0h+var_110]
0x18002d16e  mov     [rsp+250h+var_170], rax
0x18002d176  lea     rax, [rbp+0E0h+var_E8]
0x18002d17a  mov     [rsp+250h+var_178], rax
0x18002d182  lea     rax, [rbp+0E0h+var_E0]
0x18002d186  mov     [rsp+250h+var_180], rax
0x18002d18e  lea     rax, [rbp+0E0h+var_D8]
0x18002d192  mov     [rsp+250h+var_188], rax
0x18002d19a  lea     rax, [rbp+0E0h+var_154]
0x18002d19e  mov     [rsp+250h+var_190], rax
0x18002d1a6  lea     rax, [rbp+0E0h+var_138]
0x18002d1aa  mov     [rsp+250h+var_198], rax
0x18002d1b2  lea     rax, [rbp+0E0h+var_15C]
0x18002d1b6  mov     [rsp+250h+var_1A0], rax
0x18002d1be  lea     rax, [rbp+0E0h+var_15B]
0x18002d1c2  mov     [rsp+250h+var_1A8], rax
0x18002d1ca  lea     rax, [rbp+0E0h+var_152]
0x18002d1ce  mov     [rsp+250h+var_1B0], rax
0x18002d1d6  lea     rax, [rbp+0E0h+var_150]
0x18002d1da  mov     [rsp+250h+var_1B8], rax
0x18002d1e2  lea     rax, [rbp+0E0h+var_14E]
0x18002d1e6  mov     [rsp+250h+var_1C0], rax
0x18002d1ee  lea     rax, [rbp+0E0h+var_14C]
0x18002d1f2  mov     [rsp+250h+var_1C8], rax
0x18002d1fa  lea     rax, [rbp+0E0h+var_14A]
0x18002d1fe  mov     [rsp+250h+var_1D0], rax
0x18002d206  lea     rax, [rbp+0E0h+var_148]
0x18002d20a  mov     [rsp+250h+var_1D8], rax
0x18002d20f  lea     rax, [rbp+0E0h+var_146]
0x18002d213  mov     [rsp+250h+var_1E0], rax
0x18002d218  mov     word ptr [rbp+0E0h+HashValue], r12w
0x18002d21d  mov     [rbp+0E0h+var_134], esi
0x18002d220  lea     rax, [rbp+0E0h+var_144]
0x18002d224  mov     [rsp+250h+var_1E8], rax
0x18002d229  lea     rdx, byte_1800434C7
0x18002d230  lea     rax, [rbp+0E0h+var_142]
0x18002d234  mov     [rsp+250h+var_1F0], rax
0x18002d239  lea     rax, [rbp+0E0h+var_140]
0x18002d23d  mov     [rsp+250h+var_1F8], rax
0x18002d242  lea     rax, [rbp+0E0h+var_13E]
0x18002d246  mov     [rsp+250h+var_200], rax
0x18002d24b  lea     rax, [rbp+0E0h+var_13C]
0x18002d24f  mov     [rsp+250h+var_208], rax
0x18002d254  lea     rax, [rbp+0E0h+var_13A]
0x18002d258  mov     [rsp+250h+var_210], rax
0x18002d25d  lea     rax, [rbp+0E0h+var_158]
0x18002d261  mov     [rsp+250h+var_218], rax
0x18002d266  lea     rax, [rbp+0E0h+HashValue]
0x18002d26a  mov     [rsp+250h+var_220], rax
0x18002d26f  lea     rax, [rbp+0E0h+DestinationString]
0x18002d273  mov     [rsp+250h+UserData], rax
0x18002d278  lea     rax, [rbp+0E0h+var_134]
0x18002d27c  mov     qword ptr [rsp+250h+UserDataCount], rax
0x18002d281  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$01@@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U3@U?$_tlgWrapperByVal@$00@@U4@U1@U3@U?$_tlgWrapperByVal@$07@@U5@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$01@@55555555555555AEBU?$_tlgWrapperByVal@$00@@635AEBU?$_tlgWrapperByVal@$07@@7AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18002d286  cmp     [rbp+0E0h+var_B0], r13d
0x18002d28a  jz      short loc_18002D2A8
0x18002d28c  cmp     [rbp+0E0h+FileTime2.dwHighDateTime+8], r13d
0x18002d290  jz      short loc_18002D2A8
0x18002d292  lea     rdx, [rbp+0E0h+FileTime2.dwHighDateTime+8]; lpFileTime2
0x18002d296  lea     rcx, [rbp+0E0h+FileTime1.dwHighDateTime]; lpFileTime1
0x18002d29a  call    cs:__imp_CompareFileTime
0x18002d2a0  lea     rcx, [rbp+0E0h+FileTime2.dwHighDateTime+8]
0x18002d2a4  test    eax, eax
0x18002d2a6  js      short loc_18002D2AC
0x18002d2a8  lea     rcx, [rbp+0E0h+FileTime1.dwHighDateTime]; lpFileTime2
0x18002d2ac  mov     r8, [rdi+18h]
0x18002d2b0  lea     rax, [rbp+0E0h+var_130]
0x18002d2b4  lea     r9, [rbp+0E0h+var_108]
0x18002d2b8  mov     qword ptr [rsp+250h+UserDataCount], rax; __int64
0x18002d2bd  lea     rdx, [rbp+0E0h+FileTime1.dwHighDateTime]; lpFileTime
0x18002d2c1  mov     r8, [r8+30h]
0x18002d2c5  call    UbpmpMaintenanceComputeCompletionPeriod
  ... truncated ...
```
