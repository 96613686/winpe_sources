# TdhpCreatePayloadFilter(_GUID const *,_EVENT_DESCRIPTOR const *,uchar,ulong,_PAYLOAD_FILTER_PREDICATE *,_SINGLE_PAYLOAD_FILTER * *)

- ea: `0x180027444`
- end: `0x180027f31`
- name: `?TdhpCreatePayloadFilter@@YAKPEBU_GUID@@PEBU_EVENT_DESCRIPTOR@@EKPEAU_PAYLOAD_FILTER_PREDICATE@@PEAPEAU_SINGLE_PAYLOAD_FILTER@@@Z`
- size: `2797`
- prototype: `TDHSTATUS __fastcall(const struct _GUID *, const struct _EVENT_DESCRIPTOR *, char, unsigned int, struct _PAYLOAD_FILTER_PREDICATE *, struct _SINGLE_PAYLOAD_FILTER **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180023fc0`

## callees

- `0x180003270`
- `0x180012f34`
- `0x180018350`
- `0x1800207c0`
- `0x180021490`
- `0x1800273a8`
- `0x180027444`
- `0x180027f38`
- `0x1800280c8`
- `0x1800280f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002786c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800278a2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002786c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800278a2`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x180027ba7`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x180027bc9`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x180027ba7`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x180027bc9`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x180027b72`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x180027b94`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x180027b72`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x180027b94`
- `ntdll!RtlGUIDFromString` at `0x180027adf`
- `ntdll!RtlGUIDFromString` at `0x180027adf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027580`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027619`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027c46`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027580`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027619`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027c46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027eda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027ef8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027eda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027ef8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027571`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027606`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027c35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027ecc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027eea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027571`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027606`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027c35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027ecc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027eea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
TDHSTATUS __fastcall TdhpCreatePayloadFilter(
        const struct _GUID *a1,
        const struct _EVENT_DESCRIPTOR *a2,
        char a3,
        unsigned int a4,
        struct _PAYLOAD_FILTER_PREDICATE *a5,
        struct _SINGLE_PAYLOAD_FILTER **a6)
{
  struct _PAYLOAD_FILTER_PREDICATE *v6; // r14
  unsigned int v7; // r15d
  unsigned int v10; // r12d
  TDHSTATUS result; // eax
  _BYTE *v12; // r13
  TDHSTATUS EventInformation; // ebx
  EVENT_DESCRIPTOR v14; // xmm1
  ULONG v15; // ebx
  HANDLE ProcessHeap; // rax
  PTRACE_EVENT_INFO v17; // rsi
  HANDLE v18; // rax
  size_t v19; // rbx
  _BYTE *v20; // rax
  unsigned int i; // r12d
  unsigned __int64 v22; // r15
  char *v23; // r14
  char *v24; // rcx
  __int64 v25; // rax
  ULONG v26; // ecx
  ULONG v27; // edx
  PTRACE_EVENT_INFO v28; // rsi
  __int64 v29; // r9
  __int64 v30; // r8
  char *v31; // r10
  __int64 v32; // rax
  char *v33; // r11
  __int64 v34; // rax
  unsigned int v35; // r11d
  _WORD *v36; // r10
  __int64 v37; // rax
  __int64 v38; // rax
  LPWSTR FieldName; // r9
  wchar_t *Value; // rcx
  LPWSTR v41; // rsi
  WCHAR v42; // ax
  __int64 v43; // rdx
  __int64 v44; // rcx
  bool v45; // zf
  _WORD *v46; // rsi
  _WORD *v47; // rax
  bool v48; // r12
  int v49; // r14d
  int v50; // r13d
  int v51; // eax
  int v52; // ecx
  int v53; // eax
  __int64 v54; // rsi
  __int64 v55; // r15
  char v56; // r8
  unsigned int v57; // esi
  int v58; // r8d
  wchar_t *v59; // r10
  int v60; // r8d
  int v61; // r8d
  int v62; // r8d
  int v63; // r8d
  int v64; // r8d
  unsigned __int64 v65; // rax
  unsigned int v66; // eax
  unsigned int v67; // ecx
  unsigned __int64 v68; // rcx
  unsigned __int64 v69; // rcx
  WCHAR *v70; // r10
  NTSTATUS v71; // eax
  unsigned __int64 v72; // rax
  unsigned int v73; // eax
  unsigned int v74; // ecx
  __int64 v75; // rax
  unsigned int v76; // esi
  unsigned int v77; // eax
  unsigned int v78; // r14d
  unsigned int v79; // ecx
  unsigned int v80; // eax
  unsigned int v81; // ebx
  HANDLE v82; // rax
  char *v83; // rax
  unsigned __int16 *v84; // r9
  char v85; // dl
  const struct _EVENT_DESCRIPTOR *v86; // rcx
  UCHAR Version; // al
  unsigned int v88; // ecx
  char v89; // al
  char v90; // dl
  char v91; // al
  __int64 v92; // r9
  __int64 v93; // r9
  __int64 v94; // r9
  unsigned __int16 *v95; // rsi
  __int64 v96; // r9
  __int64 v97; // r9
  unsigned int v98; // ecx
  __int64 v99; // rdx
  __int64 v100; // rax
  unsigned int j; // r10d
  __int64 v102; // rax
  struct _PAYLOAD_FILTER_PREDICATE *v103; // r15
  unsigned __int16 *v104; // r10
  unsigned int k; // r11d
  LPWSTR v106; // rbx
  unsigned int v107; // ecx
  unsigned int v108; // edi
  const struct _EVENT_DESCRIPTOR *v109; // r8
  unsigned int m; // r10d
  unsigned int v111; // r11d
  unsigned int v112; // ebx
  _BYTE *v113; // rcx
  HANDLE v114; // rax
  HANDLE v115; // rax
  unsigned __int16 v116[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v117; // [rsp+34h] [rbp-CCh]
  ULONG PropertyCount; // [rsp+38h] [rbp-C8h]
  char v119; // [rsp+3Ch] [rbp-C4h]
  SIZE_T dwBytes; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v121; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v122; // [rsp+50h] [rbp-B0h] BYREF
  ULONG BufferSize; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE *v124; // [rsp+58h] [rbp-A8h]
  wchar_t *EndPtr; // [rsp+60h] [rbp-A0h] BYREF
  int v126; // [rsp+68h] [rbp-98h]
  unsigned int v127; // [rsp+6Ch] [rbp-94h]
  PTRACE_EVENT_INFO v128; // [rsp+70h] [rbp-90h]
  __int64 v129; // [rsp+78h] [rbp-88h]
  WCHAR *v130; // [rsp+80h] [rbp-80h]
  struct _PAYLOAD_FILTER_PREDICATE *v131; // [rsp+88h] [rbp-78h]
  const struct _EVENT_DESCRIPTOR *v132; // [rsp+90h] [rbp-70h]
  unsigned int v133[4]; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *String; // [rsp+A8h] [rbp-58h]
  _UNICODE_STRING GuidString; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v136; // [rsp+C0h] [rbp-40h]
  __int64 v137; // [rsp+C8h] [rbp-38h]
  const struct _GUID *v138; // [rsp+D0h] [rbp-30h]
  struct _SINGLE_PAYLOAD_FILTER **v139; // [rsp+D8h] [rbp-28h]
  _EVENT_RECORD Event; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v141[256]; // [rsp+150h] [rbp+50h] BYREF

  v6 = a5;
  v7 = 0;
  v119 = a3;
  v132 = a2;
  v10 = a4;
  v138 = a1;
  v127 = a4;
  v131 = a5;
  v139 = a6;
  EndPtr = 0;
  Event.EventHeader.Size = 0;
  memset_0(&Event.EventHeader.HeaderType, 0, 0x6Eu);
  LODWORD(dwBytes) = 0;
  v122 = 0;
  v116[0] = 0;
  BufferSize = 0;
  GuidString = 0;
  *(_OWORD *)v133 = 0;
  if ( v10 > 8 )
    return 87;
  *a6 = 0;
  if ( !v10 )
  {
    v12 = 0;
    v124 = 0;
    v128 = 0;
    EventInformation = 0;
    PropertyCount = 0;
    goto LABEL_38;
  }
  v14 = *a2;
  Event.EventHeader.ProviderId = *a1;
  v133[0] = (unsigned __int16)(24 * v10);
  Event.EventHeader.EventDescriptor = v14;
  result = TdhGetEventInformation(&Event, 0, 0, 0, &BufferSize);
  if ( !result )
    return 13;
  if ( result != 122 )
    return result;
  v15 = BufferSize;
  ProcessHeap = GetProcessHeap();
  v128 = (PTRACE_EVENT_INFO)HeapAlloc(ProcessHeap, 8u, v15);
  v17 = v128;
  if ( !v128 )
    return 8;
  EventInformation = TdhGetEventInformation(&Event, 0, 0, v128, &BufferSize);
  if ( EventInformation )
    goto LABEL_155;
  PropertyCount = v17->PropertyCount;
  v7 = PropertyCount;
  if ( (int)ULongLongToULong(4LL * PropertyCount, &v133[1]) < 0 )
  {
    EventInformation = 534;
    goto LABEL_155;
  }
  if ( (int)ULongLongToULong(24LL * PropertyCount, (unsigned int *)&dwBytes) < 0 )
  {
    EventInformation = 8;
    goto LABEL_155;
  }
  v18 = GetProcessHeap();
  v19 = (unsigned int)dwBytes;
  v20 = HeapAlloc(v18, 8u, (unsigned int)dwBytes);
  v124 = v20;
  v12 = v20;
  if ( !v20 )
  {
    EventInformation = 8;
    goto LABEL_155;
  }
  memset_0(v20, 0, v19);
  EventInformation = 87;
  for ( i = 0; i < v7; ++i )
  {
    v22 = 24LL * i;
    v23 = (char *)v128 + v22;
    if ( !(unsigned __int8)TdhpSetPayloadDecoder(&v12[v22 + 20], &v128->EventPropertyInfoArray[v22 / 0x18]) )
      goto LABEL_153;
    if ( (v12[v22 + 20] & 0xF) == 0 )
      goto LABEL_35;
    if ( (v12[v22 + 20] & 0xF) != 7 )
    {
      if ( (v12[v22 + 20] & 0xF) != 8 && !*(_QWORD *)&v12[24 * i] )
      {
        if ( !*((_DWORD *)v23 + 29) )
          goto LABEL_153;
        v24 = (char *)v128 + *((unsigned int *)v23 + 29);
        *(_QWORD *)&v12[24 * i] = v24;
        v25 = -1;
        do
          ++v25;
        while ( *(_WORD *)&v24[2 * v25] );
        *(_WORD *)&v12[24 * i + 16] = v25;
      }
      goto LABEL_35;
    }
    v26 = *((unsigned __int16 *)v23 + 60);
    v7 = PropertyCount;
    v27 = v26 + *((unsigned __int16 *)v23 + 61);
    if ( v27 > PropertyCount )
      goto LABEL_153;
    if ( v26 < v27 )
    {
      v28 = v128;
      v29 = *((unsigned __int16 *)v23 + 60);
      do
      {
        v30 = 3 * v29;
        v31 = (char *)v28 + *((unsigned int *)v23 + 29);
        v32 = -1;
        *(_QWORD *)&v12[8 * v30] = v31;
        v33 = (char *)v28 + v28->EventPropertyInfoArray[v29].NameOffset;
        *(_QWORD *)&v12[8 * v30 + 8] = v33;
        do
          ++v32;
        while ( *(_WORD *)&v31[2 * v32] );
        *(_WORD *)&v12[24 * v29 + 16] = v32;
        v34 = -1;
        do
          ++v34;
        while ( *(_WORD *)&v33[2 * v34] );
        *(_WORD *)&v12[24 * v29 + 18] = v34;
        ++v26;
        ++v29;
      }
      while ( v26 < v27 );
LABEL_35:
      v7 = PropertyCount;
      continue;
    }
  }
  v10 = v127;
  v6 = v131;
LABEL_38:
  memset_0(v141, 0, sizeof(v141));
  v35 = v133[3];
  v36 = 0;
  v37 = 0;
  v117 = v133[3];
  LODWORD(dwBytes) = v133[2];
  while ( 2 )
  {
    v126 = v37;
    if ( (unsigned int)v37 < v10 )
    {
      v136 = v37;
      v38 = v37;
      FieldName = v6[v38].FieldName;
      v137 = v38 * 3;
      v130 = FieldName;
      if ( !FieldName )
        goto LABEL_115;
      Value = v6[v38].Value;
      v41 = FieldName;
      v42 = *FieldName;
      String = Value;
      while ( v42 && v42 != 46 )
        v42 = *++v41;
      v43 = (unsigned int)v36;
      LODWORD(v121) = (_DWORD)v36;
      v44 = v41 - FieldName;
      v45 = *v41 == 46;
      v129 = v44;
      if ( v45 )
      {
        v46 = v41 + 1;
        v47 = v46;
        if ( *v46 != (_WORD)v36 )
        {
          do
          {
            v43 = (unsigned int)(v43 + 1);
            ++v47;
          }
          while ( *v47 != (_WORD)v36 );
          LODWORD(v121) = v43;
        }
      }
      else
      {
        v46 = v36;
      }
      v48 = (char)v36;
      v49 = (int)v36;
      v50 = (int)v36;
      if ( !v7 )
      {
LABEL_151:
        v12 = v124;
        goto LABEL_152;
      }
      while ( !v48 )
      {
        if ( *(unsigned __int16 *)&v124[24 * v50 + 16] == (_DWORD)v44
          && *(unsigned __int16 *)&v124[24 * v50 + 18] == (_DWORD)v43 )
        {
          v51 = _o__wcsnicmp(*(_QWORD *)&v124[24 * v50], FieldName, (unsigned int)v44);
          v48 = v51 == 0;
          v52 = v50;
          if ( v51 )
            v52 = v49;
          v49 = v52;
          if ( v46 )
          {
            v53 = _o__wcsnicmp(*(_QWORD *)&v124[24 * v50 + 8], v46, (unsigned int)v121);
            LODWORD(v44) = v129;
            v43 = (unsigned int)v121;
            FieldName = v130;
            if ( v53 )
              v48 = 0;
          }
          else
          {
            LODWORD(v44) = v129;
            v43 = (unsigned int)v121;
            FieldName = v130;
          }
        }
        if ( ++v50 >= PropertyCount )
        {
          if ( !v48 )
            goto LABEL_151;
          break;
        }
      }
      v54 = v137;
      v12 = v124;
      v55 = 32 * v136;
      *(_WORD *)&v141[32 * v136] = v49;
      v56 = v12[24 * v49 + 20];
      v6 = v131;
      v57 = *(&v131->CompareOp + 4 * v54);
      *(_WORD *)&v141[v55 + 2] = TdhpCompareOpToInternal((unsigned __int16)v57, v43, v56 & 0xF);
      if ( v57 <= 6 )
      {
        if ( v57 != 6 && v57 >= 4 && v57 - 4 > 1 )
          goto LABEL_152;
LABEL_66:
        if ( (unsigned int)(v58 - 1) > 1 )
          goto LABEL_152;
LABEL_74:
        v59 = String;
        v60 = v58 - 1;
        if ( v60 )
        {
          v61 = v60 - 1;
          if ( v61 )
          {
            v62 = v61 - 1;
            if ( !v62 )
            {
              v72 = -1;
              do
                ++v72;
              while ( String[v72] );
              if ( v72 + 1 < v72 )
                goto LABEL_115;
              v121 = v72 + 1;
              if ( (int)ULongLongMult(v72 + 1, 1u, &v121) < 0 )
                goto LABEL_115;
              if ( (int)ULongLongToULong(v121, &v122) < 0 )
                goto LABEL_115;
              v73 = v117;
              v74 = v122;
              *(_DWORD *)&v141[v55 + 24] = v122;
              v35 = v73 + v74;
              v117 = v73 + v74;
              if ( v73 + v74 < v73 )
                goto LABEL_115;
              goto LABEL_113;
            }
            v63 = v62 - 1;
            if ( v63 )
            {
              v64 = v63 - 1;
              if ( v64 )
              {
                if ( v64 == 1 )
                  goto LABEL_152;
LABEL_111:
                v36 = 0;
              }
              else
              {
                v68 = -1;
                do
                  ++v68;
                while ( String[v68] );
                v121 = v68;
                if ( (int)ULongLongMult(v68, 2u, &v121) < 0 || (int)ULongLongToULong(v121, &v122) < 0 )
                  goto LABEL_115;
                if ( v69 > 0xFFFF )
                {
                  GuidString.Length = -1;
LABEL_115:
                  EventInformation = 87;
                  goto LABEL_152;
                }
                GuidString.Length = v69;
                if ( (int)UShortAdd(v69, 2u, &GuidString.MaximumLength) < 0 )
                  goto LABEL_115;
                GuidString.Buffer = v70;
                v71 = RtlGUIDFromString(&GuidString, (GUID *)&v141[v55 + 8]);
                v36 = 0;
                if ( v71 < 0 )
                  goto LABEL_152;
              }
LABEL_112:
              v35 = v117;
LABEL_113:
              v7 = PropertyCount;
              v37 = (unsigned int)(v126 + 1);
              v10 = v127;
              continue;
            }
LABEL_84:
            v65 = -1;
            do
              ++v65;
            while ( v59[v65] );
            if ( v65 + 1 < v65 )
              goto LABEL_115;
            v121 = v65 + 1;
            if ( (int)ULongLongMult(v65 + 1, 2u, &v121) < 0 )
              goto LABEL_115;
            if ( (int)ULongLongToULong(v121, &v122) < 0 )
              goto LABEL_115;
            v66 = dwBytes;
            v67 = v122;
            *(_DWORD *)&v141[v55 + 24] = v122;
            LODWORD(dwBytes) = v66 + v67;
            if ( v66 + v67 < v66 )
              goto LABEL_115;
            goto LABEL_112;
          }
          *(_QWORD *)&v141[v55 + 8] = _o__wcstoui64(String, &EndPtr, 0);
          if ( (unsigned __int16)(v57 - 6) > 1u )
            goto LABEL_111;
          v75 = _o__wcstoui64(EndPtr, &EndPtr, 0);
        }
        else
        {
          *(_QWORD *)&v141[v55 + 8] = _wcstoi64(String, &EndPtr, 0);
          if ( (unsigned __int16)(v57 - 6) > 1u )
            goto LABEL_111;
          v75 = _wcstoi64(EndPtr, &EndPtr, 0);
        }
        *(_QWORD *)&v141[v55 + 16] = v75;
        goto LABEL_111;
      }
      if ( v57 == 7 || v57 == 8 )
        goto LABEL_66;
      if ( v57 != 20 && v57 != 21 )
      {
        if ( v57 - 30 > 1 || (unsigned int)(v58 - 3) > 2 )
          goto LABEL_152;
        goto LABEL_74;
      }
      if ( v58 == 3 )
        goto LABEL_74;
      if ( v58 != 4 )
        goto LABEL_152;
      v59 = String;
      goto LABEL_84;
    }
    break;
  }
  v76 = v133[0];
  v77 = v133[0] + 40;
  if ( v133[0] >= 0xFFFFFFD8 )
    goto LABEL_115;
  v78 = v133[1];
  v79 = v77 + v133[1];
  if ( v77 + v133[1] < v77 )
    goto LABEL_115;
  v80 = v79 + dwBytes;
  if ( v79 + (unsigned int)dwBytes < v79 )
    goto LABEL_115;
  v81 = v80 + v35;
  if ( v80 + v35 < v80 || (int)ULongToUShort(v81, v116) < 0 )
    goto LABEL_115;
  v82 = GetProcessHeap();
  v83 = (char *)HeapAlloc(v82, 8u, v81);
  EventInformation = 0;
  v84 = (unsigned __int16 *)v83;
  if ( v83 )
  {
    v85 = v83[7];
    v86 = v132;
    *(_WORD *)v83 = 5398;
    *((_WORD *)v83 + 1) = v116[0];
    *(struct _GUID *)(v83 + 8) = *v138;
    *((_WORD *)v83 + 2) = v86->Id;
    Version = v86->Version;
    v88 = dwBytes;
    *((_BYTE *)v84 + 6) = Version;
    v89 = v85;
    v90 = v85 | 1;
    v91 = v89 & 0xFE;
    if ( !v119 )
      v90 = v91;
    *((_BYTE *)v84 + 7) = v90;
    if ( (int)ULongToUShort(v88, v84 + 14) < 0 )
      goto LABEL_115;
    if ( (int)ULongToUShort(v117, (unsigned __int16 *)(v92 + 32)) < 0 )
      goto LABEL_115;
    if ( (int)ULongToUShort(v76, v116) < 0 )
      goto LABEL_115;
    if ( (int)UShortAdd(0x28u, v116[0], (unsigned __int16 *)(v93 + 24)) < 0 )
      goto LABEL_115;
    if ( (int)ULongToUShort(v78, v116) < 0 )
      goto LABEL_115;
    v95 = (unsigned __int16 *)(v94 + 26);
    if ( (int)UShortAdd(*(_WORD *)(v94 + 24), v116[0], (unsigned __int16 *)(v94 + 26)) < 0 )
      goto LABEL_115;
    if ( (int)UShortAdd(*v95, *(_WORD *)(v96 + 28), (unsigned __int16 *)(v96 + 30)) < 0 )
      goto LABEL_115;
    *(_WORD *)(v97 + 34) = v10;
    if ( v7 > 0x7F )
      goto LABEL_115;
    *(_BYTE *)(v97 + 7) &= 1u;
    *(_BYTE *)(v97 + 7) |= 2 * (_BYTE)v7;
    if ( v10 )
    {
      v98 = 0;
      v132 = (const struct _EVENT_DESCRIPTOR *)(v97 + 40);
      v99 = v97 + 40;
      do
      {
        v100 = v98++;
        v100 *= 32;
        *(_OWORD *)v99 = *(_OWORD *)&v141[v100];
        *(_QWORD *)(v99 + 16) = *(_QWORD *)&v141[v100 + 16];
        v99 += 24;
      }
      while ( v98 < v10 );
      for ( j = 0; j < v7; v99 += 4 )
      {
        v102 = j++;
        *(_DWORD *)v99 = *(_DWORD *)&v12[24 * v102 + 20];
      }
      v103 = v131;
      v104 = (unsigned __int16 *)(v97 + 40);
      for ( k = 0; k < v10; ++k )
      {
        if ( (v12[24 * *v104 + 20] & 0xF) == 4 )
        {
          *((_QWORD *)v104 + 1) = (v99 - (unsigned __int64)*v95 - v97) >> 1;
          v106 = v103[k].Value;
          v107 = 0;
          v108 = *(_DWORD *)&v141[32 * k + 24] >> 1;
          if ( v108 )
          {
            do
            {
              ++v107;
              *(_WORD *)v99 = *v106++;
              v99 += 2;
            }
            while ( v107 < v108 );
          }
        }
        v104 += 12;
      }
      v109 = v132;
      for ( m = 0; m < v10; ++m )
      {
        if ( (v12[24 * v109->Id + 20] & 0xF) == 3 )
        {
          v111 = 0;
          v109->Keyword = v99 - *(unsigned __int16 *)(v97 + 30) - v97;
          v112 = *(_DWORD *)&v141[32 * m + 24];
          v113 = v103[m].Value;
          if ( v112 )
          {
            do
            {
              ++v111;
              *(_BYTE *)v99 = *v113;
              v113 += 2;
              ++v99;
            }
            while ( v111 < v112 );
            v12 = v124;
          }
        }
        v109 = (const struct _EVENT_DESCRIPTOR *)((char *)v109 + 24);
      }
      EventInformation = 0;
    }
    *v139 = (struct _SINGLE_PAYLOAD_FILTER *)v97;
  }
  else
  {
    EventInformation = 8;
  }
LABEL_152:
  if ( v12 )
  {
LABEL_153:
    v114 = GetProcessHeap();
    HeapFree(v114, 0, v12);
  }
  v17 = v128;
  if ( v128 )
  {
LABEL_155:
    v115 = GetProcessHeap();
    HeapFree(v115, 0, v17);
  }
  return EventInformation;
}

```

## disassembly

```asm
0x180027444  mov     [rsp-8+arg_10], rbx
0x180027449  push    rbp
0x18002744a  push    rsi
0x18002744b  push    rdi
0x18002744c  push    r12
0x18002744e  push    r13
0x180027450  push    r14
0x180027452  push    r15
0x180027454  lea     rbp, [rsp-160h]
0x18002745c  sub     rsp, 260h
0x180027463  mov     rax, cs:__security_cookie
0x18002746a  xor     rax, rsp
0x18002746d  mov     [rbp+190h+var_40], rax
0x180027474  mov     r14, [rbp+190h+arg_20]
0x18002747b  xor     r15d, r15d
0x18002747e  mov     rdi, [rbp+190h+arg_28]
0x180027485  mov     rbx, rdx
0x180027488  mov     [rsp+290h+var_254], r8b
0x18002748d  mov     rsi, rcx
0x180027490  mov     [rbp+190h+var_200], rdx
0x180027494  mov     r12d, r9d
0x180027497  mov     [rbp+190h+var_1C0], rcx
0x18002749b  lea     r8d, [r15+6Eh]; Size
0x18002749f  xor     edx, edx; Val
0x1800274a1  mov     [rsp+290h+var_224], r9d
0x1800274a6  lea     rcx, [rbp+190h+Event.EventHeader.HeaderType]; void *
0x1800274aa  mov     [rbp+190h+var_208], r14
0x1800274ae  mov     [rbp+190h+var_1B8], rdi
0x1800274b2  mov     [rsp+290h+EndPtr], r15
0x1800274b7  mov     [rbp+190h+Event.EventHeader.Size], r15w
0x1800274bc  call    memset_0
0x1800274c1  lea     r13d, [r15+8]
0x1800274c5  mov     dword ptr [rsp+290h+dwBytes], r15d
0x1800274ca  mov     [rsp+290h+var_240], r15d
0x1800274cf  xorps   xmm0, xmm0
0x1800274d2  mov     [rsp+290h+var_260], r15w
0x1800274d8  xorps   xmm1, xmm1
0x1800274db  mov     [rsp+290h+var_23C], r15d
0x1800274e0  movups  xmmword ptr [rbp+190h+GuidString.Length], xmm0
0x1800274e4  movups  xmmword ptr [rbp+190h+var_1F8], xmm1
0x1800274e8  cmp     r12d, r13d
0x1800274eb  jbe     short loc_1800274F6
0x1800274ed  lea     eax, [r15+57h]
0x1800274f1  jmp     loc_180027F07
0x1800274f6  mov     [rdi], r15
0x1800274f9  mov     edi, 57h ; 'W'
0x1800274fe  test    r12d, r12d
0x180027501  jnz     short loc_18002751C
0x180027503  mov     r13, r15
0x180027506  mov     [rsp+290h+var_238], r15
0x18002750b  mov     [rsp+290h+var_220], r15
0x180027510  xor     ebx, ebx
0x180027512  mov     [rsp+290h+var_258], r15d
0x180027517  jmp     loc_180027775
0x18002751c  movups  xmm0, xmmword ptr [rsi]
0x18002751f  movzx   eax, r12w
0x180027523  xor     r9d, r9d; Buffer
0x180027526  movups  xmm1, xmmword ptr [rbx]
0x180027529  add     ax, ax
0x18002752c  xor     r8d, r8d; TdhContext
0x18002752f  xor     edx, edx; TdhContextCount
0x180027531  movdqu  xmmword ptr [rbp+190h+Event.EventHeader.ProviderId.Data1], xmm0
0x180027536  lea     ecx, [rax+r12]
0x18002753a  shl     cx, 3
0x18002753e  movzx   eax, cx
0x180027541  lea     rcx, [rbp+190h+Event]; Event
0x180027545  mov     [rbp+190h+var_1F8], eax
0x180027548  lea     rax, [rsp+290h+var_23C]
0x18002754d  mov     [rsp+290h+BufferSize], rax; BufferSize
0x180027552  movdqu  xmmword ptr [rbp+190h+Event.EventHeader.EventDescriptor.Id], xmm1
0x180027557  call    TdhGetEventInformation
0x18002755c  test    eax, eax
0x18002755e  jz      loc_180027F02
0x180027564  cmp     eax, 7Ah ; 'z'
0x180027567  jnz     loc_180027F07
0x18002756d  mov     ebx, [rsp+290h+var_23C]
0x180027571  call    cs:__imp_GetProcessHeap
0x180027577  mov     r8d, ebx; dwBytes
0x18002757a  mov     edx, r13d; dwFlags
0x18002757d  mov     rcx, rax; hHeap
0x180027580  call    cs:__imp_HeapAlloc
0x180027586  mov     [rsp+290h+var_220], rax
0x18002758b  mov     rsi, rax
0x18002758e  test    rax, rax
0x180027591  jnz     short loc_18002759B
0x180027593  mov     eax, r13d
0x180027596  jmp     loc_180027F07
0x18002759b  lea     rax, [rsp+290h+var_23C]
0x1800275a0  mov     r9, rsi; Buffer
0x1800275a3  xor     r8d, r8d; TdhContext
0x1800275a6  mov     [rsp+290h+BufferSize], rax; BufferSize
0x1800275ab  xor     edx, edx; TdhContextCount
0x1800275ad  lea     rcx, [rbp+190h+Event]; Event
0x1800275b1  call    TdhGetEventInformation
0x1800275b6  mov     ebx, eax
0x1800275b8  test    eax, eax
0x1800275ba  jnz     loc_180027EEA
0x1800275c0  mov     r15d, [rsi+64h]
0x1800275c4  lea     rdx, [rbp+190h+var_1F8+4]; unsigned int *
0x1800275c8  mov     [rsp+290h+var_258], r15d
0x1800275cd  lea     rcx, ds:0[r15*4]; unsigned __int64
0x1800275d5  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800275da  test    eax, eax
0x1800275dc  jns     short loc_1800275E8
0x1800275de  mov     ebx, 216h
0x1800275e3  jmp     loc_180027EEA
0x1800275e8  lea     rcx, [r15+r15*2]
0x1800275ec  shl     rcx, 3; unsigned __int64
0x1800275f0  lea     rdx, [rsp+290h+dwBytes]; unsigned int *
0x1800275f5  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800275fa  test    eax, eax
0x1800275fc  jns     short loc_180027606
0x1800275fe  mov     ebx, r13d
0x180027601  jmp     loc_180027EEA
0x180027606  call    cs:__imp_GetProcessHeap
0x18002760c  mov     ebx, dword ptr [rsp+290h+dwBytes]
0x180027610  mov     edx, r13d; dwFlags
0x180027613  mov     r8d, ebx; dwBytes
0x180027616  mov     rcx, rax; hHeap
0x180027619  call    cs:__imp_HeapAlloc
0x18002761f  mov     [rsp+290h+var_238], rax
0x180027624  mov     r13, rax
0x180027627  test    rax, rax
0x18002762a  jnz     short loc_180027634
0x18002762c  lea     ebx, [rax+8]
0x18002762f  jmp     loc_180027EEA
0x180027634  mov     r8, rbx; Size
0x180027637  xor     edx, edx; Val
0x180027639  mov     rcx, r13; void *
0x18002763c  call    memset_0
0x180027641  xor     edx, edx
0x180027643  mov     ebx, edi
0x180027645  mov     r12d, edx
0x180027648  cmp     r12d, r15d
0x18002764b  jnb     loc_18002776C
0x180027651  mov     eax, r12d
0x180027654  lea     rcx, [r13+14h]
0x180027658  lea     rsi, [rax+rax*2]
0x18002765c  mov     rax, [rsp+290h+var_220]
0x180027661  lea     r15, ds:0[rsi*8]
0x180027669  add     rcx, r15
0x18002766c  lea     r14, [rax+rsi*8]
0x180027670  lea     rdx, [r14+70h]
0x180027674  call    TdhpSetPayloadDecoder
0x180027679  xor     edx, edx
0x18002767b  test    al, al
0x18002767d  jz      loc_180027ECC
0x180027683  movzx   ecx, byte ptr [r15+r13+14h]
0x180027689  and     ecx, 0Fh
0x18002768c  jz      loc_18002775F
0x180027692  sub     ecx, 7
0x180027695  jz      short loc_1800276DE
0x180027697  cmp     ecx, 1
0x18002769a  jz      loc_18002775F
0x1800276a0  cmp     [r13+rsi*8+0], rdx
0x1800276a5  jnz     loc_18002775F
0x1800276ab  cmp     [r14+74h], edx
0x1800276af  jz      loc_180027ECC
0x1800276b5  mov     eax, [r14+74h]
0x1800276b9  mov     rcx, [rsp+290h+var_220]
0x1800276be  add     rcx, rax
0x1800276c1  mov     [r13+rsi*8+0], rcx
0x1800276c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800276ca  inc     rax
0x1800276cd  cmp     [rcx+rax*2], dx
0x1800276d1  jnz     short loc_1800276CA
0x1800276d3  mov     [r13+rsi*8+10h], ax
0x1800276d9  jmp     loc_18002775F
0x1800276de  movzx   ecx, word ptr [r14+78h]
0x1800276e3  movzx   edx, word ptr [r14+7Ah]
0x1800276e8  mov     r15d, [rsp+290h+var_258]
0x1800276ed  add     edx, ecx
0x1800276ef  cmp     edx, r15d
0x1800276f2  ja      loc_180027ECC
0x1800276f8  cmp     ecx, edx
0x1800276fa  jnb     short loc_180027764
0x1800276fc  mov     rsi, [rsp+290h+var_220]
0x180027701  mov     r9d, ecx
0x180027704  mov     r10d, [r14+74h]
0x180027708  lea     r8, [r9+r9*2]
0x18002770c  add     r10, rsi
0x18002770f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027713  mov     [r13+r8*8+0], r10
0x180027718  mov     r11d, [rsi+r8*8+74h]
0x18002771d  add     r11, rsi
0x180027720  mov     [r13+r8*8+8], r11
0x180027725  xor     r15d, r15d
0x180027728  inc     rax
0x18002772b  cmp     [r10+rax*2], r15w
0x180027730  jnz     short loc_180027728
0x180027732  mov     [r13+r8*8+10h], ax
0x180027738  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002773c  xor     r10d, r10d
0x18002773f  inc     rax
0x180027742  cmp     [r11+rax*2], r10w
0x180027747  jnz     short loc_18002773F
0x180027749  mov     r15d, 1
0x18002774f  mov     [r13+r8*8+12h], ax
0x180027755  add     ecx, r15d
0x180027758  add     r9, r15
0x18002775b  cmp     ecx, edx
0x18002775d  jb      short loc_180027704
0x18002775f  mov     r15d, [rsp+290h+var_258]
0x180027764  inc     r12d
0x180027767  jmp     loc_180027648
0x18002776c  mov     r12d, [rsp+290h+var_224]
0x180027771  mov     r14, [rbp+190h+var_208]
0x180027775  xor     edx, edx; Val
0x180027777  lea     rcx, [rbp+190h+var_140]; void *
0x18002777b  mov     r8d, 100h; Size
0x180027781  call    memset_0
0x180027786  mov     r11d, [rbp+190h+var_1F8+0Ch]
0x18002778a  xor     r10d, r10d
0x18002778d  mov     edx, [rbp+190h+var_1F8+8]
0x180027790  mov     eax, r10d
0x180027793  mov     [rsp+290h+var_25C], r11d
0x180027798  mov     dword ptr [rsp+290h+dwBytes], edx
0x18002779c  mov     [rsp+290h+var_228], eax
0x1800277a0  cmp     eax, r12d
0x1800277a3  jnb     loc_180027BFC
0x1800277a9  mov     [rbp+190h+var_1D0], rax
0x1800277ad  lea     rax, [rax+rax*2]
0x1800277b1  mov     r9, [r14+rax*8]
0x1800277b5  mov     [rbp+190h+var_1C8], rax
0x1800277b9  mov     [rbp+190h+var_210], r9
0x1800277bd  test    r9, r9
0x1800277c0  jz      loc_180027BF5
0x1800277c6  mov     rcx, [r14+rax*8+10h]
0x1800277cb  mov     rsi, r9
0x1800277ce  movzx   eax, word ptr [r9]
0x1800277d2  mov     [rbp+190h+String], rcx
0x1800277d6  jmp     short loc_1800277E5
0x1800277d8  cmp     ax, 2Eh ; '.'
0x1800277dc  jz      short loc_1800277EA
0x1800277de  add     rsi, 2
0x1800277e2  movzx   eax, word ptr [rsi]
0x1800277e5  test    ax, ax
0x1800277e8  jnz     short loc_1800277D8
0x1800277ea  mov     rcx, rsi
0x1800277ed  mov     edx, r10d
0x1800277f0  sub     rcx, r9
0x1800277f3  mov     dword ptr [rsp+290h+var_248], edx
0x1800277f7  sar     rcx, 1
0x1800277fa  cmp     word ptr [rsi], 2Eh ; '.'
0x1800277fe  mov     [rsp+290h+var_218], rcx
0x180027803  jnz     short loc_180027824
0x180027805  add     rsi, 2
0x180027809  mov     rax, rsi
0x18002780c  cmp     [rsi], r10w
0x180027810  jz      short loc_180027827
0x180027812  inc     edx
0x180027814  lea     rax, [rax+2]
0x180027818  cmp     [rax], r10w
0x18002781c  jnz     short loc_180027812
0x18002781e  mov     dword ptr [rsp+290h+var_248], edx
0x180027822  jmp     short loc_180027827
0x180027824  mov     rsi, r10
0x180027827  mov     r12b, r10b
0x18002782a  mov     r14d, r10d
0x18002782d  mov     r13d, r10d
0x180027830  test    r15d, r15d
0x180027833  jz      loc_180027EC2
0x180027839  test    r12b, r12b
0x18002783c  jnz     loc_1800278E5
0x180027842  mov     r10, [rsp+290h+var_238]
0x180027847  mov     eax, r13d
0x18002784a  lea     r15, [rax+rax*2]
0x18002784e  movzx   eax, word ptr [r10+r15*8+10h]
0x180027854  cmp     eax, ecx
0x180027856  jnz     short loc_1800278CE
0x180027858  movzx   eax, word ptr [r10+r15*8+12h]
0x18002785e  cmp     eax, edx
0x180027860  jnz     short loc_1800278CE
0x180027862  mov     r8d, ecx
0x180027865  mov     rdx, r9
0x180027868  mov     rcx, [r10+r15*8]
0x18002786c  call    cs:__imp__o__wcsnicmp
0x180027872  mov     ecx, 1
0x180027877  movzx   r12d, r12b
0x18002787b  test    eax, eax
0x18002787d  cmovz   r12d, ecx
0x180027881  mov     ecx, r13d
0x180027884  cmovnz  ecx, r14d
0x180027888  mov     r14d, ecx
0x18002788b  test    rsi, rsi
0x18002788e  jz      short loc_1800278C1
0x180027890  mov     rcx, [rsp+290h+var_238]
0x180027895  mov     rdx, rsi
0x180027898  mov     r8d, dword ptr [rsp+290h+var_248]
0x18002789d  mov     rcx, [rcx+r15*8+8]
0x1800278a2  call    cs:__imp__o__wcsnicmp
0x1800278a8  mov     rcx, [rsp+290h+var_218]
0x1800278ad  xor     r10d, r10d
0x1800278b0  mov     edx, dword ptr [rsp+290h+var_248]
0x1800278b4  mov     r9, [rbp+190h+var_210]
0x1800278b8  test    eax, eax
0x1800278ba  jz      short loc_1800278CE
0x1800278bc  mov     r12b, r10b
0x1800278bf  jmp     short loc_1800278CE
0x1800278c1  mov     rcx, [rsp+290h+var_218]
  ... truncated ...
```
