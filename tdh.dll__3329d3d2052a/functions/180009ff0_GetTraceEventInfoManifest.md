# GetTraceEventInfoManifest

- ea: `0x180009ff0`
- end: `0x18000ade9`
- name: `GetTraceEventInfoManifest`
- size: `3577`
- prototype: `signed int __fastcall(__int64, PublisherManifestResource *, __int16 *, const void *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task`

## callers

- `0x180009c7c`

## callees

- `0x180009ff0`
- `0x18000adf0`
- `0x18000b030`
- `0x18000b0a8`
- `0x18000b120`
- `0x18000b390`
- `0x18000b41c`
- `0x18000b9d0`
- `0x18000bf6c`
- `0x18000c274`
- `0x18000c300`
- `0x18000cfd0`
- `0x180011a80`
- `0x180012f34`
- `0x180013b44`
- `0x18001ebcc`
- `0x180023b05`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a145`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a6c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000abbd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a145`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a6c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000abbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a134`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a6b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000abac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a134`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a6b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000abac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a46e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a46e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a557`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a466`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a54f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a466`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a54f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall GetTraceEventInfoManifest(
        __int64 a1,
        PublisherManifestResource *a2,
        __int16 *a3,
        const void *a4,
        __int64 a5,
        unsigned int *a6)
{
  const struct TemplateResource *v7; // rdx
  unsigned int v10; // r12d
  const struct _GUID *v11; // rax
  __int64 v12; // r14
  const wchar_t *v13; // rax
  va_list *nSize; // r10
  const wchar_t *v15; // rbx
  _DWORD *v16; // rsi
  int v17; // edi
  __int64 v18; // rax
  const wchar_t *v19; // rcx
  SIZE_T v20; // r15
  HANDLE ProcessHeap; // rax
  wchar_t *v22; // rax
  signed int result; // eax
  unsigned int v24; // esi
  __int64 v25; // rdx
  HINSTANCE v26; // r15
  __int64 v27; // rdx
  DWORD v28; // r10d
  __int64 v29; // rdx
  unsigned int v30; // r8d
  _DWORD *v31; // r8
  __int64 v32; // r9
  const wchar_t *v33; // r8
  unsigned int v34; // ecx
  unsigned int v35; // ebx
  unsigned int v36; // eax
  const struct TaskResource *v37; // rdx
  HINSTANCE v38; // r15
  __int64 v39; // rdx
  DWORD v40; // r8d
  DWORD v41; // r15d
  PublisherManifestResource *v42; // r9
  DWORD v43; // r8d
  __int64 v44; // rax
  const wchar_t *v45; // r8
  char v46; // cl
  va_list *v47; // r11
  __int16 v48; // dx
  wchar_t *v49; // r12
  DWORD v50; // r13d
  unsigned int v51; // ebx
  const struct EventAttribsResource *v52; // rdi
  int v53; // ecx
  int v54; // ecx
  int EventAttribsResource; // eax
  __int64 v56; // rax
  DWORD v57; // ebx
  DWORD LastError; // eax
  va_list *v59; // rax
  __int64 v60; // rdx
  unsigned int v61; // ecx
  int v62; // eax
  DWORD v63; // ebx
  va_list *v64; // rax
  __int64 v65; // rdx
  unsigned int v66; // ecx
  unsigned int v67; // ecx
  unsigned int v68; // eax
  unsigned int v69; // ecx
  unsigned int v70; // r15d
  unsigned int v71; // ebx
  HANDLE v72; // rax
  LPVOID v73; // rax
  PublisherManifestResource *v74; // r12
  unsigned int i; // edi
  __int64 v76; // r15
  __int128 v77; // xmm0
  unsigned __int64 v78; // r13
  __m128i v79; // xmm2
  __m128i v80; // xmm3
  struct QueryStruct *v81; // xmm4_8
  _WORD *v82; // rax
  __int64 v83; // rbx
  unsigned __int64 v84; // rcx
  unsigned __int64 j; // r12
  unsigned __int64 v86; // r12
  int v87; // eax
  const wchar_t *v88; // r11
  char *v89; // rax
  unsigned __int64 v90; // rcx
  __int64 v91; // rax
  __int64 v92; // rcx
  int v93; // eax
  unsigned int v94; // ecx
  DWORD v95; // eax
  unsigned int v96; // edx
  unsigned int v97; // ecx
  DWORD v98; // eax
  unsigned int v99; // edx
  unsigned int v100; // ecx
  unsigned int v101; // r13d
  unsigned int v102; // r8d
  __int64 v103; // rcx
  unsigned int v104; // eax
  unsigned int v105; // ecx
  unsigned __int64 v106; // rax
  unsigned int v107; // eax
  unsigned int v108; // ecx
  unsigned int v109; // edi
  HANDLE v110; // rax
  LPVOID v111; // rax
  __int64 v112; // r12
  const struct EventAttribsResource *v113; // rdi
  DWORD v114; // r13d
  __int64 v115; // r15
  __int64 v116; // rcx
  unsigned int v117; // ecx
  struct _GUID v118; // xmm0
  int v119; // eax
  unsigned int v120; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v121; // [rsp+48h] [rbp-B8h]
  unsigned int v122; // [rsp+50h] [rbp-B0h]
  __int64 v123; // [rsp+58h] [rbp-A8h]
  va_list *v124; // [rsp+60h] [rbp-A0h]
  wchar_t *v125[2]; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwMessageId[2]; // [rsp+78h] [rbp-88h]
  __int128 v127; // [rsp+80h] [rbp-80h]
  void *Src[2]; // [rsp+90h] [rbp-70h] BYREF
  DWORD v129[2]; // [rsp+A0h] [rbp-60h]
  wchar_t *v130[2]; // [rsp+A8h] [rbp-58h] BYREF
  DWORD v131[4]; // [rsp+B8h] [rbp-48h]
  __int128 v132; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v133; // [rsp+D8h] [rbp-28h]
  __int128 v134; // [rsp+E8h] [rbp-18h]
  __int64 v135; // [rsp+F8h] [rbp-8h]
  __m128i v136; // [rsp+100h] [rbp+0h] BYREF
  __int128 v137; // [rsp+110h] [rbp+10h]
  __m128i v138; // [rsp+120h] [rbp+20h]
  struct QueryStruct *v139; // [rsp+130h] [rbp+30h]
  __int128 v140; // [rsp+138h] [rbp+38h] BYREF
  wchar_t *v141[2]; // [rsp+148h] [rbp+48h]
  DWORD v142[14]; // [rsp+158h] [rbp+58h]
  va_list *Buffer; // [rsp+1B0h] [rbp+B0h] BYREF
  LPCVOID lpSource; // [rsp+1B8h] [rbp+B8h]

  lpSource = a4;
  *(_QWORD *)v129 = 0;
  *(_QWORD *)dwMessageId = 0;
  v120 = 0;
  v7 = (const struct TemplateResource *)*((_QWORD *)a3 + 3);
  *(_QWORD *)v142 = 0;
  *(_QWORD *)v131 = 0;
  v10 = 136;
  v135 = 0;
  v139 = 0;
  *(_OWORD *)Src = 0;
  *(_OWORD *)v125 = 0;
  v140 = 0;
  *(_OWORD *)v141 = 0;
  *(_OWORD *)v130 = 0;
  v132 = 0;
  v133 = 0;
  v134 = 0;
  v136 = 0;
  v137 = 0;
  v138 = 0;
  if ( v7 )
  {
    result = PublisherManifestResource::GetTemplateResource(a2, v7, (struct TemplateResourceData *)&v132);
    if ( result )
      return result;
    v122 = v133;
    if ( (_DWORD)v133 )
    {
      v106 = 24LL * (unsigned int)(v133 - 1);
      if ( v106 > 0xFFFFFFFF )
        return 534;
      v107 = v106 + 136;
      if ( v107 < 0x88 )
        return 534;
      v10 = v107;
    }
  }
  else
  {
    v122 = 0;
  }
  v11 = PublisherManifestResource::ProviderControlGuid(a2);
  v12 = a5;
  if ( v11 )
  {
    v118 = *v11;
    *(_BYTE *)(a5 + 964) = 1;
    *(struct _GUID *)(v12 + 968) = v118;
  }
  v13 = PublisherManifestResource::ProviderName(a2);
  nSize = 0;
  v15 = v13;
  if ( !v13 )
    v15 = *(const wchar_t **)(a1 + 8);
  if ( !v12 )
    return 87;
  v16 = (_DWORD *)(v12 + 592);
  if ( v12 == -592 )
    return 87;
  v17 = 87;
  if ( !v15 )
  {
    *(_BYTE *)(v12 + 892) = 0;
    goto LABEL_19;
  }
  v18 = 0x7FFFFFFF;
  v19 = v15;
  do
  {
    if ( !*v19 )
      break;
    ++v19;
    --v18;
  }
  while ( v18 );
  if ( !v18 )
  {
    result = 87;
LABEL_18:
    if ( result )
      return result;
    goto LABEL_19;
  }
  v20 = (-(__int64)(v18 != 0) & (2 * (0x7FFFFFFF - v18))) + 2;
  if ( v20 > 0xFFFFFFFF )
  {
    *v16 = -1;
    return 534;
  }
  *v16 = v20;
  ProcessHeap = GetProcessHeap();
  v22 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, v20);
  *(_QWORD *)v12 = v22;
  if ( !v22 )
    return 8;
  *(_BYTE *)(v12 + 892) = 2;
  result = StringCbCopyW(v22, v20, v15);
  if ( result < 0 )
  {
    result = (unsigned __int16)result;
    goto LABEL_18;
  }
LABEL_19:
  v24 = v10 + *v16;
  LODWORD(Buffer) = v24;
  if ( v24 < v10 )
    return 534;
  v25 = *((_QWORD *)a3 + 5);
  if ( v25 )
  {
    v98 = *(_DWORD *)(v25 + 4);
    v99 = *(_DWORD *)(v25 + 8);
    v129[0] = v98;
    result = PublisherManifestResource::GetResourceString(a2, v99, (const wchar_t **)&Src[1]);
    if ( result )
      return result;
    v26 = (HINSTANCE)lpSource;
    result = TdhpGetResourceName(
               (HINSTANCE)lpSource,
               v129[0],
               (const wchar_t *)Src[1],
               (wchar_t **)(v12 + 8),
               (unsigned int *)(v12 + 596),
               (unsigned __int8 *)(v12 + 893));
    nSize = 0;
    if ( result )
      return result;
    v100 = v24 + *(_DWORD *)(v12 + 596);
    if ( v100 < v24 )
      return 534;
    v24 += *(_DWORD *)(v12 + 596);
    LODWORD(Buffer) = v100;
  }
  else
  {
    v26 = (HINSTANCE)lpSource;
  }
  v27 = *((_QWORD *)a3 + 9);
  if ( v27 )
  {
    v28 = *(_DWORD *)(v27 + 12);
    v29 = *(unsigned int *)(v27 + 4);
    if ( (_DWORD)v29 )
    {
      v30 = *((_DWORD *)a2 + 34) - *((_DWORD *)a2 + 30);
      if ( (unsigned int)v29 < v30 )
        return 13;
      if ( (int)v29 + 4 < (unsigned int)v29 )
        return 13;
      if ( (int)v29 + 4 > v30 + *(_DWORD *)(*((_QWORD *)a2 + 17) + 4LL) )
        return 13;
      v31 = (_DWORD *)(v29 + *((_QWORD *)a2 + 15));
      if ( *v31 <= 6u )
        return 13;
      v32 = (unsigned int)*v31;
      if ( v32 + (unsigned __int64)(unsigned int)v29 >= *((unsigned int *)a2 + 36)
        || *((_WORD *)v31 + ((unsigned __int64)(v32 - 4) >> 1) + 1) )
      {
        return 13;
      }
      v33 = (const wchar_t *)(v31 + 1);
    }
    else
    {
      v33 = 0;
    }
    result = TdhpGetResourceName(
               v26,
               v28,
               v33,
               (wchar_t **)(v12 + 16),
               (unsigned int *)(v12 + 600),
               (unsigned __int8 *)(v12 + 894));
    nSize = 0;
    if ( result )
      return result;
    v34 = v24 + *(_DWORD *)(v12 + 600);
    if ( v34 < v24 )
      return 534;
    v24 += *(_DWORD *)(v12 + 600);
    LODWORD(Buffer) = v34;
  }
  v35 = (unsigned int)nSize;
  *(_DWORD *)(v12 + 860) = *((_DWORD *)a3 + 14);
  while ( 1 )
  {
    v36 = *(_DWORD *)(v12 + 860);
    if ( v35 >= v36 )
      break;
    result = PublisherManifestResource::GetKeywordResource(
               a2,
               (const struct KeywordResourceIndex *)(*((_QWORD *)a3 + 8) + 4LL * v35),
               (struct KeywordResourceData *)v125);
    if ( result )
      return result;
    result = TdhpGetResourceName(
               (HINSTANCE)lpSource,
               dwMessageId[0],
               v125[1],
               (wchar_t **)(v12 + 24 + 8LL * v35),
               &v120,
               (unsigned __int8 *)(v35 + v12 + 895));
    nSize = 0;
    if ( result )
      return result;
    v68 = v120;
    *(_DWORD *)(v12 + 4LL * v35 + 604) = v120;
    v69 = v24 + v68;
    if ( v24 + v68 < v24 )
      return 534;
    v24 += v68;
    LODWORD(Buffer) = v69;
    ++v35;
  }
  if ( v36 )
  {
    v104 = v24 + 2;
    if ( v24 + 2 < v24 )
      return 534;
    v24 += 2;
    LODWORD(Buffer) = v104;
  }
  v37 = (const struct TaskResource *)*((_QWORD *)a3 + 6);
  if ( v37 )
  {
    result = PublisherManifestResource::GetTaskResource(a2, v37, (struct TaskResourceData *)&v140);
    if ( result )
      return result;
    v38 = (HINSTANCE)lpSource;
    result = TdhpGetResourceName(
               (HINSTANCE)lpSource,
               v142[0],
               v141[1],
               (wchar_t **)(v12 + 536),
               (unsigned int *)(v12 + 864),
               (unsigned __int8 *)(v12 + 959));
    nSize = 0;
    if ( result )
      return result;
    v105 = v24 + *(_DWORD *)(v12 + 864);
    if ( v105 < v24 )
      return 534;
    v24 += *(_DWORD *)(v12 + 864);
    LODWORD(Buffer) = v105;
  }
  else
  {
    v38 = (HINSTANCE)lpSource;
  }
  v39 = *((_QWORD *)a3 + 4);
  if ( v39 )
  {
    v95 = *(_DWORD *)(v39 + 4);
    v96 = *(_DWORD *)(v39 + 8);
    v131[0] = v95;
    result = PublisherManifestResource::GetResourceString(a2, v96, (const wchar_t **)&v130[1]);
    if ( result )
      return result;
    result = TdhpGetResourceName(
               v38,
               v131[0],
               v130[1],
               (wchar_t **)(v12 + 544),
               (unsigned int *)(v12 + 868),
               (unsigned __int8 *)(v12 + 960));
    nSize = 0;
    if ( result )
      return result;
    v97 = v24 + *(_DWORD *)(v12 + 868);
    if ( v97 < v24 )
      return 534;
    v24 += *(_DWORD *)(v12 + 868);
    LODWORD(Buffer) = v97;
  }
  v40 = *((_DWORD *)a3 + 4);
  v41 = -1;
  if ( v40 != -1 )
  {
    Buffer = nSize;
    if ( v12 == -552 || v12 == -872 )
      return v17;
    if ( lpSource )
    {
      v63 = FormatMessageW(0xBFFu, lpSource, v40, 0, (LPWSTR)&Buffer, (DWORD)nSize, nSize);
      result = GetLastError();
      nSize = 0;
      if ( !v63 )
        goto LABEL_82;
      v64 = Buffer;
      *(_QWORD *)(v12 + 552) = Buffer;
      *(_BYTE *)(v12 + 961) = 1;
      if ( v64 )
      {
        v65 = 0x7FFFFFFF;
        do
        {
          if ( !*(_WORD *)v64 )
            break;
          v64 = (va_list *)((char *)v64 + 2);
          --v65;
        }
        while ( v65 );
        v66 = v65 == 0 ? 0x80070057 : 0;
        if ( v65 )
        {
          result = ULongLongToULong(((2 * (0x7FFFFFFF - v65)) & -(__int64)(v65 != 0)) + 2, (unsigned int *)(v12 + 872));
          if ( result < 0 )
          {
            result = (unsigned __int16)result;
            goto LABEL_82;
          }
LABEL_83:
          v67 = v24 + *(_DWORD *)(v12 + 872);
          if ( v67 < v24 )
            return 534;
          v24 += *(_DWORD *)(v12 + 872);
          LODWORD(Buffer) = v67;
          v41 = -1;
          goto LABEL_43;
        }
      }
      else
      {
        LOWORD(v66) = 87;
      }
      result = (unsigned __int16)v66;
LABEL_82:
      if ( result )
        return result;
      goto LABEL_83;
    }
    *(_BYTE *)(v12 + 961) = (_BYTE)nSize;
    goto LABEL_83;
  }
LABEL_43:
  v42 = a2;
  v43 = *(_DWORD *)(*((_QWORD *)a2 + 17) + 8LL);
  if ( v43 == -1 )
    goto LABEL_44;
  Buffer = nSize;
  if ( v12 == -560 || v12 == -876 )
    return v17;
  if ( !lpSource )
  {
    *(_BYTE *)(v12 + 962) = (_BYTE)nSize;
    goto LABEL_154;
  }
  v57 = FormatMessageW(0xBFFu, lpSource, v43, 0, (LPWSTR)&Buffer, (DWORD)nSize, nSize);
  LastError = GetLastError();
  nSize = 0;
  v17 = LastError;
  if ( !v57 )
    goto LABEL_69;
  v59 = Buffer;
  *(_QWORD *)(v12 + 560) = Buffer;
  *(_BYTE *)(v12 + 962) = 1;
  if ( !v59 )
  {
    LOWORD(v61) = 87;
LABEL_183:
    v17 = (unsigned __int16)v61;
LABEL_69:
    if ( v17 )
      return v17;
    goto LABEL_153;
  }
  v60 = 0x7FFFFFFF;
  do
  {
    if ( !*(_WORD *)v59 )
      break;
    v59 = (va_list *)((char *)v59 + 2);
    --v60;
  }
  while ( v60 );
  v61 = v60 == 0 ? 0x80070057 : 0;
  if ( !v60 )
    goto LABEL_183;
  v62 = ULongLongToULong(((2 * (0x7FFFFFFF - v60)) & -(__int64)(v60 != 0)) + 2, (unsigned int *)(v12 + 876));
  if ( v62 < 0 )
  {
    v17 = (unsigned __int16)v62;
    goto LABEL_69;
  }
LABEL_153:
  v42 = a2;
LABEL_154:
  v108 = v24 + *(_DWORD *)(v12 + 876);
  if ( v108 < v24 )
    return 534;
  v24 += *(_DWORD *)(v12 + 876);
  LODWORD(Buffer) = v108;
  v41 = -1;
LABEL_44:
  if ( *((va_list **)a3 + 3) != nSize )
  {
    *(_QWORD *)(v12 + 568) = v132;
    v93 = DWORD2(v132);
    *(_DWORD *)(v12 + 880) = DWORD2(v132);
    v94 = v93 + v24;
    if ( v93 + v24 < v24 || v94 + 1 < v94 )
      return 534;
    v24 = (v94 + 1) & 0xFFFFFFFE;
    LODWORD(Buffer) = v24;
  }
  v44 = *((_QWORD *)v42 + 11);
  v45 = (const wchar_t *)nSize;
  v46 = *((_BYTE *)a3 + 2);
  v47 = nSize;
  v48 = *a3;
  v123 = (__int64)nSize;
  v124 = nSize;
  LOBYTE(v120) = 18;
  BYTE1(v120) = v46;
  HIWORD(v120) = v48;
  if ( v44 )
  {
    v101 = *(_DWORD *)(v44 + 8);
    v49 = (wchar_t *)(v44 + 12);
    LOBYTE(v121) = 17;
    BYTE1(v121) = v46;
    v102 = v101;
    HIWORD(v121) = v48;
    if ( v101 )
    {
      do
      {
        v103 = v102 >> 1;
        if ( *(_DWORD *)&v49[4 * v103] >= v121 )
        {
          v102 >>= 1;
        }
        else
        {
          v49 += 4 * (unsigned int)(v103 + 1);
          v102 += -1 - (v102 >> 1);
        }
      }
      while ( v102 );
      v42 = a2;
    }
    v125[1] = v49;
    v45 = (const wchar_t *)nSize;
    v50 = v101 - (((__int64)v49 - v44 - 12) >> 3);
    dwMessageId[0] = v50;
    nSize = 0;
  }
  else
  {
    v49 = (wchar_t *)nSize;
    v125[1] = (wchar_t *)nSize;
    v50 = (unsigned int)nSize;
    dwMessageId[0] = (unsigned int)nSize;
  }
  v51 = v120;
  v127 = 0;
  v52 = 0;
  dwMessageId[1] = -1;
  while ( ++v41 < v50 )
  {
    dwMessageId[1] = v41;
    if ( v41 )
    {
      v52 = (const struct EventAttribsResource *)((char *)v52 + 8);
      *(_QWORD *)&v127 = v52;
    }
    else
    {
      v52 = (const struct EventAttribsResource *)v49;
      *(_QWORD *)&v127 = v49;
    }
    if ( *(_DWORD *)v52 > v51 )
      goto LABEL_90;
    v53 = *(unsigned __int8 *)v52;
    *(_OWORD *)Src = 0;
    v54 = v53 - 17;
    if ( v54 )
    {
      if ( v54 == 1 )
      {
        EventAttribsResource = PublisherManifestResource::GetEventAttribsResource(
                                 v42,
                                 v52,
                                 (struct EventAttribsResourceData *)Src);
        v47 = v124;
        nSize = 0;
        v45 = (const wchar_t *)v123;
        v42 = a2;
        if ( !EventAttribsResource )
        {
          v56 = -1;
          do
            ++v56;
          while ( *((_WORD *)Src[1] + v56) );
          v47 = (va_list *)((char *)v124 + v56 + 1);
          v124 = v47;
LABEL_187:
          v42 = a2;
        }
      }
    }
    else
    {
      v119 = PublisherManifestResource::GetEventAttribsResource(v42, v52, (struct EventAttribsResourceData *)Src);
      v47 = v124;
      nSize = 0;
      v45 = (const wchar_t *)v123;
      v42 = a2;
      if ( !v119 )
      {
        v45 = (const wchar_t *)Src[1];
        v123 = (__int64)Src[1];
        goto LABEL_187;
      }
    }
  }
  *(_QWORD *)&v127 = nSize;
LABEL_90:
  if ( !v45 )
  {
LABEL_91:
    if ( !v47 )
      goto LABEL_92;
    v109 = 2 * (_DWORD)v47;
    *(_DWORD *)(v12 + 888) = 2 * (_DWORD)v47;
    v110 = GetProcessHeap();
    v111 = HeapAlloc(v110, 8u, v109);
    *(_QWORD *)(v12 + 584) = v111;
    if ( v111 )
    {
      v112 = 0;
      PublisherManifestResource::EventAttribsLowerBound(a2, v51, v125);
      v113 = (const struct EventAttribsResource *)v127;
      v114 = dwMessageId[1];
      while ( ++v114 < dwMessageId[0] )
      {
        if ( v114 )
          v113 = (const struct EventAttribsResource *)((char *)v113 + 8);
        else
          v113 = (const struct EventAttribsResource *)v125[1];
        if ( *(_DWORD *)v113 > v51 )
          break;
        *(_OWORD *)Src = 0;
        if ( !(unsigned int)PublisherManifestResource::GetEventAttribsResource(
                              a2,
                              v113,
                              (struct EventAttribsResourceData *)Src) )
        {
          v115 = -1;
          do
            ++v115;
          while ( *((_WORD *)Src[1] + v115) );
          memcpy_0((void *)(*(_QWORD *)(v12 + 584) + 2 * v112), Src[1], 2 * v115);
          v116 = v115 + v112;
          v112 += v115 + 1;
          *(_WORD *)(*(_QWORD *)(v12 + 584) + 2 * v116) = 59;
        }
      }
      *(_WORD *)(*(_QWORD *)(v12 + 584) + 2 * v112 - 2) = 0;
      if ( (int)Buffer + *(_DWORD *)(v12 + 888) < (unsigned int)Buffer )
        return 534;
      v24 = (_DWORD)Buffer + *(_DWORD *)(v12 + 888);
LABEL_92:
      v70 = v122;
      if ( 88 * (unsigned __int64)v122 > 0xFFFFFFFF )
        return 534;
      v71 = 88 * v122;
      v72 = GetProcessHeap();
      v73 = HeapAlloc(v72, 8u, v71);
      *(_QWORD *)(v12 + 1064) = v73;
      if ( v73 )
      {
        v74 = a2;
        for ( i = 0; ; ++i )
        {
          if ( i >= v70 )
          {
            *a6 = v24;
            return 0;
          }
          v123 = 5LL * i;
          result = PublisherManifestResource::GetTypeResource(
                     v74,
                     (const struct TemplateResourceData *)&v132,
                     (const struct TypeResource *)(*((_QWORD *)&v133 + 1) + 20LL * i),
                     (struct TypeResourceData *)&v136);
          if ( result )
            return result;
          v76 = *(_QWORD *)(v12 + 1064);
          v77 = v137;
          LODWORD(v78) = 0;
          Buffer = 0;
          v79 = v138;
          v80 = v136;
          v81 = v139;
          v82 = (_WORD *)v138.m128i_i64[0];
          v83 = 88LL * i;
          *(_OWORD *)v130 = 0;
          *(__m128i *)(v83 + v76) = v136;
          *(_OWORD *)(v83 + v76 + 16) = v77;
          *(__m128i *)(v83 + v76 + 32) = v79;
          *(_QWORD *)(v83 + v76 + 48) = v81;
          *(_OWORD *)v125 = 0;
          if ( !v82 )
          {
            LOWORD(result) = 87;
LABEL_120:
            result = (unsigned __int16)result;
            if ( (_WORD)result )
              return result;
            goto LABEL_121;
          }
          v84 = (unsigned __int64)*((unsigned int *)a2 + 36) >> 1;
          for ( j = v84; v84; --v84 )
          {
            if ( !*v82 )
              break;
            ++v82;
          }
          result = v84 == 0 ? 0x80070057 : 0;
          if ( v84 )
            v86 = j - v84;
          else
            v86 = 0;
          if ( !v84 )
          {
LABEL_191:
            v74 = a2;
            goto LABEL_120;
          }
          if ( (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v80, 2)) )
            break;
          v87 = _mm_cvtsi128_si32(_mm_srli_si128(v79, 12));
          if ( !v87 )
            break;
          if ( v87 == 1 )
          {
            result = PublisherManifestResource::GetMapStruct(a2, v81, (struct MapStructData *)v125);
            if ( result )
              return result;
            v88 = v125[0];
          }
          else
          {
            if ( v87 != 2 )
              break;
            result = PublisherManifestResource::GetQueryStruct(a2, v81, (struct QueryStructData *)v130);
            if ( result )
              return result;
            v88 = v130[0];
          }
          if ( !v88 )
            goto LABEL_108;
          result = StringCbLengthW(v88, *((unsigned int *)a2 + 36), (unsigned __int64 *)&Buffer);
          if ( result < 0 )
            goto LABEL_191;
          v89 = (char *)Buffer + 2;
LABEL_109:
          v90 = 2 * v86 + 2;
          v78 = (unsigned __int64)&v89[v90];
          if ( (unsigned __int64)&v89[v90] < v90 || v78 > 0xFFFFFFFF )
            return 534;
          v74 = a2;
          *(_QWORD *)(v83 + v76 + 64) = v89;
          v91 = *((_QWORD *)&v133 + 1);
          *(_QWORD *)(v83 + v76 + 72) = v90;
          v92 = v123;
          *(_QWORD *)(v83 + v76 + 56) = v88;
          *(_WORD *)(v83 + v76 + 80) = *(_WORD *)(v91 + 4 * v92 + 4);
LABEL_121:
          if ( v24 + (unsigned int)v78 < v24 )
            return 534;
          v70 = v122;
          v24 += v78;
        }
        v88 = 0;
LABEL_108:
        v89 = 0;
        goto LABEL_109;
      }
    }
    return 8;
  }
  result = TdhpGetResourceName(
             (HINSTANCE)lpSource,
             0xFFFFFFFF,
             v45,
             (wchar_t **)(v12 + 576),
             (unsigned int *)(v12 + 884),
             (unsigned __int8 *)(v12 + 963));
  if ( !result )
  {
    v117 = v24 + *(_DWORD *)(v12 + 884);
    if ( v117 >= v24 )
    {
      v47 = v124;
      v24 += *(_DWORD *)(v12 + 884);
      LODWORD(Buffer) = v117;
      goto LABEL_91;
    }
    return 534;
  }
  return result;
}

```

## disassembly

```asm
0x180009ff0  mov     [rsp-8+arg_0], rbx
0x180009ff5  mov     [rsp-8+lpSource], r9
0x180009ffa  mov     [rsp-8+arg_8], rdx
0x180009fff  push    rbp
0x18000a000  push    rsi
0x18000a001  push    rdi
0x18000a002  push    r12
0x18000a004  push    r13
0x18000a006  push    r14
0x18000a008  push    r15
0x18000a00a  lea     rbp, [rsp-60h]
0x18000a00f  sub     rsp, 160h
0x18000a016  xor     eax, eax
0x18000a018  xorps   xmm0, xmm0
0x18000a01b  xorps   xmm1, xmm1
0x18000a01e  mov     qword ptr [rbp+90h+var_F0], rax
0x18000a022  xor     r15d, r15d
0x18000a025  mov     qword ptr [rsp+190h+dwMessageId], rax
0x18000a02a  mov     rbx, rdx
0x18000a02d  mov     [rsp+190h+var_150], r15d
0x18000a032  mov     rdx, [r8+18h]; struct TemplateResource *
0x18000a036  mov     r13, r8
0x18000a039  mov     qword ptr [rbp+90h+var_38], rax
0x18000a03d  mov     rdi, rcx
0x18000a040  mov     qword ptr [rbp+90h+var_D8], rax
0x18000a044  mov     r12d, 88h
0x18000a04a  mov     [rbp+90h+var_98], rax
0x18000a04e  mov     r14d, 0FFFFFFFFh
0x18000a054  mov     [rbp+90h+var_60], rax
0x18000a058  movups  xmmword ptr [rbp+90h+Src], xmm0
0x18000a05c  movups  xmmword ptr [rsp+190h+var_128], xmm1
0x18000a061  movups  [rbp+90h+var_58], xmm0
0x18000a065  movups  xmmword ptr [rbp+90h+var_48], xmm0
0x18000a069  movups  xmmword ptr [rbp+90h+var_E8], xmm0
0x18000a06d  movups  [rbp+90h+var_C8], xmm1
0x18000a071  movups  [rbp+90h+var_B8], xmm1
0x18000a075  movups  [rbp+90h+var_A8], xmm1
0x18000a079  movups  [rbp+90h+var_90], xmm0
0x18000a07d  movups  [rbp+90h+var_80], xmm0
0x18000a081  movups  [rbp+90h+var_70], xmm0
0x18000a085  test    rdx, rdx
0x18000a088  jnz     loc_18000AAFA
0x18000a08e  mov     [rsp+190h+var_140], r15d
0x18000a093  mov     rcx, rbx; this
0x18000a096  call    ?ProviderControlGuid@PublisherManifestResource@@QEBAPEBU_GUID@@XZ; PublisherManifestResource::ProviderControlGuid(void)
0x18000a09b  mov     r14, [rbp+90h+arg_20]
0x18000a0a2  test    rax, rax
0x18000a0a5  jnz     loc_18000ACCC
0x18000a0ab  mov     rcx, rbx; this
0x18000a0ae  call    ?ProviderName@PublisherManifestResource@@QEBAPEB_WXZ; PublisherManifestResource::ProviderName(void)
0x18000a0b3  xor     r10d, r10d
0x18000a0b6  mov     rbx, rax
0x18000a0b9  test    rax, rax
0x18000a0bc  jz      loc_18000ACE5
0x18000a0c2  test    r14, r14
0x18000a0c5  jz      loc_18000ACEE
0x18000a0cb  lea     rsi, [r14+250h]
0x18000a0d2  test    rsi, rsi
0x18000a0d5  jz      loc_18000ACEE
0x18000a0db  mov     edi, 57h ; 'W'
0x18000a0e0  mov     edx, 7FFFFFFFh
0x18000a0e5  test    rbx, rbx
0x18000a0e8  jz      loc_18000AD06
0x18000a0ee  mov     eax, edx
0x18000a0f0  mov     rcx, rbx
0x18000a0f3  cmp     [rcx], r10w
0x18000a0f7  jz      short loc_18000A103
0x18000a0f9  add     rcx, 2
0x18000a0fd  sub     rax, 1
0x18000a101  jnz     short loc_18000A0F3
0x18000a103  test    rax, rax
0x18000a106  jz      loc_18000ACF8
0x18000a10c  mov     rcx, rdx
0x18000a10f  sub     rcx, rax
0x18000a112  neg     rax
0x18000a115  sbb     rax, rax
0x18000a118  lea     r15, [rcx+rcx]
0x18000a11c  and     r15, rax
0x18000a11f  mov     eax, 0FFFFFFFFh
0x18000a124  add     r15, 2
0x18000a128  cmp     r15, rax
0x18000a12b  ja      loc_18000AB45
0x18000a131  mov     [rsi], r15d
0x18000a134  call    cs:__imp_GetProcessHeap
0x18000a13a  mov     r8, r15; dwBytes
0x18000a13d  mov     edx, 8; dwFlags
0x18000a142  mov     rcx, rax; hHeap
0x18000a145  call    cs:__imp_HeapAlloc
0x18000a14b  xor     r10d, r10d
0x18000a14e  mov     [r14], rax
0x18000a151  test    rax, rax
0x18000a154  jz      loc_18000ADC9
0x18000a15a  mov     r8, rbx; wchar_t *
0x18000a15d  mov     byte ptr [r14+37Ch], 2
0x18000a165  mov     rdx, r15; unsigned __int64
0x18000a168  mov     rcx, rax; wchar_t *
0x18000a16b  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000a170  test    eax, eax
0x18000a172  jns     short loc_18000A17B
0x18000a174  movzx   eax, ax
0x18000a177  test    eax, eax
0x18000a179  jnz     short loc_18000A190
0x18000a17b  mov     esi, [rsi]
0x18000a17d  add     esi, r12d
0x18000a180  mov     dword ptr [rbp+90h+Buffer], esi
0x18000a186  cmp     esi, r12d
0x18000a189  jnb     short loc_18000A1AB
0x18000a18b  mov     eax, 216h
0x18000a190  mov     rbx, [rsp+190h+arg_0]
0x18000a198  add     rsp, 160h
0x18000a19f  pop     r15
0x18000a1a1  pop     r14
0x18000a1a3  pop     r13
0x18000a1a5  pop     r12
0x18000a1a7  pop     rdi
0x18000a1a8  pop     rsi
0x18000a1a9  pop     rbp
0x18000a1aa  retn
0x18000a1ab  mov     rdx, [r13+28h]
0x18000a1af  mov     r12, [rbp+90h+arg_8]
0x18000a1b6  test    rdx, rdx
0x18000a1b9  jnz     loc_18000A91A
0x18000a1bf  mov     r15, [rbp+90h+lpSource]
0x18000a1c6  mov     rdx, [r13+48h]
0x18000a1ca  test    rdx, rdx
0x18000a1cd  jz      loc_18000A2A7
0x18000a1d3  mov     r10d, [rdx+0Ch]
0x18000a1d7  xor     r11d, r11d
0x18000a1da  mov     edx, [rdx+4]
0x18000a1dd  test    edx, edx
0x18000a1df  jz      loc_18000AD12
0x18000a1e5  mov     r8d, [r12+88h]
0x18000a1ed  sub     r8d, [r12+78h]
0x18000a1f2  cmp     edx, r8d
0x18000a1f5  jb      loc_18000A87C
0x18000a1fb  lea     r9d, [rdx+4]
0x18000a1ff  cmp     r9d, edx
0x18000a202  jb      loc_18000A87C
0x18000a208  mov     rax, [r12+88h]
0x18000a210  mov     eax, [rax+4]
0x18000a213  add     eax, r8d
0x18000a216  cmp     r9d, eax
0x18000a219  ja      loc_18000A87C
0x18000a21f  mov     r8, [r12+78h]
0x18000a224  mov     ecx, edx
0x18000a226  add     r8, rdx
0x18000a229  cmp     dword ptr [r8], 6
0x18000a22d  jbe     loc_18000A87C
0x18000a233  mov     r9d, [r8]
0x18000a236  mov     eax, [r12+90h]
0x18000a23e  add     rcx, r9
0x18000a241  cmp     rcx, rax
0x18000a244  jnb     loc_18000A87C
0x18000a24a  lea     rax, [r9-4]
0x18000a24e  shr     rax, 1
0x18000a251  cmp     [r8+rax*2+2], r11w
0x18000a257  jnz     loc_18000A87C
0x18000a25d  add     r8, 4; wchar_t *
0x18000a261  lea     rax, [r14+37Eh]
0x18000a268  mov     edx, r10d; dwMessageId
0x18000a26b  mov     qword ptr [rsp+190h+nSize], rax; unsigned __int8 *
0x18000a270  lea     rbx, [r14+258h]
0x18000a277  lea     r9, [r14+10h]; wchar_t **
0x18000a27b  mov     [rsp+190h+lpBuffer], rbx; unsigned int *
0x18000a280  mov     rcx, r15; lpSource
0x18000a283  call    ?TdhpGetResourceName@@YAKPEAUHINSTANCE__@@KPEB_WPEAPEA_WPEAKPEAE@Z; TdhpGetResourceName(HINSTANCE__ *,ulong,wchar_t const *,wchar_t * *,ulong *,uchar *)
0x18000a288  xor     r10d, r10d
0x18000a28b  test    eax, eax
0x18000a28d  jnz     loc_18000A190
0x18000a293  mov     ecx, [rbx]
0x18000a295  add     ecx, esi
0x18000a297  cmp     ecx, esi
0x18000a299  jb      loc_18000A18B
0x18000a29f  mov     esi, ecx
0x18000a2a1  mov     dword ptr [rbp+90h+Buffer], ecx
0x18000a2a7  mov     eax, [r13+38h]
0x18000a2ab  mov     ebx, r10d
0x18000a2ae  mov     [r14+35Ch], eax
0x18000a2b5  mov     eax, [r14+35Ch]
0x18000a2bc  cmp     ebx, eax
0x18000a2be  jb      loc_18000A5FF
0x18000a2c4  test    eax, eax
0x18000a2c6  jnz     loc_18000AA0E
0x18000a2cc  mov     rdx, [r13+30h]; struct TaskResource *
0x18000a2d0  test    rdx, rdx
0x18000a2d3  jnz     loc_18000AA26
0x18000a2d9  mov     r15, [rbp+90h+lpSource]
0x18000a2e0  mov     rdx, [r13+20h]
0x18000a2e4  test    rdx, rdx
0x18000a2e7  jnz     loc_18000A886
0x18000a2ed  mov     r8d, [r13+10h]; dwMessageId
0x18000a2f1  mov     r15d, 0FFFFFFFFh
0x18000a2f7  cmp     r8d, r15d
0x18000a2fa  jnz     loc_18000A4FF
0x18000a300  mov     r9, [rbp+90h+arg_8]
0x18000a307  mov     rax, [r9+88h]
0x18000a30e  mov     r8d, [rax+8]; dwMessageId
0x18000a312  cmp     r8d, r15d
0x18000a315  jnz     loc_18000A40E
0x18000a31b  cmp     [r13+18h], r10
0x18000a31f  jnz     loc_18000A843
0x18000a325  mov     rax, [r9+58h]
0x18000a329  mov     r8, r10; wchar_t *
0x18000a32c  mov     cl, [r13+2]
0x18000a330  mov     r11, r10
0x18000a333  movzx   edx, word ptr [r13+0]
0x18000a338  mov     [rsp+190h+var_138], r10
0x18000a33d  mov     [rsp+190h+var_130], r10
0x18000a342  mov     byte ptr [rsp+190h+var_150], 12h
0x18000a347  mov     byte ptr [rsp+190h+var_150+1], cl
0x18000a34b  mov     word ptr [rsp+190h+var_150+2], dx
0x18000a350  test    rax, rax
0x18000a353  jnz     loc_18000A98D
0x18000a359  mov     r12, r10
0x18000a35c  mov     [rsp+190h+var_128+8], r10
0x18000a361  mov     r13d, r10d
0x18000a364  mov     [rsp+190h+dwMessageId], r10d
0x18000a369  mov     ebx, [rsp+190h+var_150]
0x18000a36d  xorps   xmm0, xmm0
0x18000a370  movdqu  [rbp+90h+var_110], xmm0
0x18000a375  mov     rdi, qword ptr [rbp+90h+var_110]
0x18000a379  mov     [rsp+190h+dwMessageId+4], r15d
0x18000a37e  inc     r15d
0x18000a381  cmp     r15d, r13d
0x18000a384  jnb     loc_18000A686
0x18000a38a  mov     [rsp+190h+dwMessageId+4], r15d
0x18000a38f  test    r15d, r15d
0x18000a392  jz      loc_18000AA02
0x18000a398  add     rdi, 8
0x18000a39c  mov     qword ptr [rbp+90h+var_110], rdi
0x18000a3a0  cmp     [rdi], ebx
0x18000a3a2  ja      loc_18000A68A
0x18000a3a8  movzx   ecx, byte ptr [rdi]
0x18000a3ab  xorps   xmm0, xmm0
0x18000a3ae  movups  xmmword ptr [rbp+90h+Src], xmm0
0x18000a3b2  sub     ecx, 11h
0x18000a3b5  jz      loc_18000AD4C
0x18000a3bb  cmp     ecx, 1
0x18000a3be  jnz     short loc_18000A37E
0x18000a3c0  lea     r8, [rbp+90h+Src]; struct EventAttribsResourceData *
0x18000a3c4  mov     rdx, rdi; struct EventAttribsResource *
0x18000a3c7  mov     rcx, r9; this
0x18000a3ca  call    ?GetEventAttribsResource@PublisherManifestResource@@QEBAKPEBUEventAttribsResource@@AEAUEventAttribsResourceData@@@Z; PublisherManifestResource::GetEventAttribsResource(EventAttribsResource const *,EventAttribsResourceData &)
0x18000a3cf  mov     r11, [rsp+190h+var_130]
0x18000a3d4  xor     r10d, r10d
0x18000a3d7  mov     r8, [rsp+190h+var_138]
0x18000a3dc  mov     r9, [rbp+90h+arg_8]
0x18000a3e3  test    eax, eax
0x18000a3e5  jnz     short loc_18000A37E
0x18000a3e7  mov     rcx, [rbp+90h+Src+8]
0x18000a3eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a3ef  inc     rax
0x18000a3f2  cmp     [rcx+rax*2], r10w
0x18000a3f7  jnz     short loc_18000A3EF
0x18000a3f9  mov     r11, [rsp+190h+var_130]
0x18000a3fe  inc     r11
0x18000a401  add     r11, rax
0x18000a404  mov     [rsp+190h+var_130], r11
0x18000a409  jmp     loc_18000AD80
0x18000a40e  lea     r15, [r14+230h]
0x18000a415  mov     [rbp+90h+Buffer], r10
0x18000a41c  test    r15, r15
0x18000a41f  jz      loc_18000A4F8
0x18000a425  lea     r12, [r14+36Ch]
0x18000a42c  test    r12, r12
0x18000a42f  jz      loc_18000A4F8
0x18000a435  mov     rax, [rbp+90h+lpSource]
0x18000a43c  test    rax, rax
0x18000a43f  jz      loc_18000AD40
0x18000a445  mov     [rsp+190h+Arguments], r10; Arguments
0x18000a44a  lea     rdx, [rbp+90h+Buffer]
0x18000a451  mov     [rsp+190h+nSize], r10d; nSize
0x18000a456  xor     r9d, r9d; dwLanguageId
0x18000a459  mov     [rsp+190h+lpBuffer], rdx; lpBuffer
0x18000a45e  mov     ecx, 0BFFh; dwFlags
0x18000a463  mov     rdx, rax; lpSource
0x18000a466  call    cs:__imp_FormatMessageW
0x18000a46c  mov     ebx, eax
0x18000a46e  call    cs:__imp_GetLastError
0x18000a474  xor     r10d, r10d
0x18000a477  mov     edi, eax
0x18000a479  test    ebx, ebx
0x18000a47b  jz      short loc_18000A4F0
0x18000a47d  mov     rax, [rbp+90h+Buffer]
0x18000a484  mov     [r15], rax
0x18000a487  mov     byte ptr [r14+3C2h], 1
0x18000a48f  test    rax, rax
0x18000a492  jz      loc_18000AD33
0x18000a498  mov     r8d, 7FFFFFFFh
0x18000a49e  mov     edx, r8d
0x18000a4a1  cmp     [rax], r10w
0x18000a4a5  jz      short loc_18000A4B1
0x18000a4a7  add     rax, 2
0x18000a4ab  sub     rdx, 1
0x18000a4af  jnz     short loc_18000A4A1
0x18000a4b1  mov     rax, rdx
0x18000a4b4  neg     rax
0x18000a4b7  sbb     ecx, ecx
0x18000a4b9  not     ecx
0x18000a4bb  and     ecx, 80070057h
  ... truncated ...
```
