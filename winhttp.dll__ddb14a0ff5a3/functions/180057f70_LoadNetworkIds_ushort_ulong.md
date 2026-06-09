# LoadNetworkIds(ushort * * *,ulong *)

- ea: `0x180057f70`
- end: `0x180058783`
- name: `?LoadNetworkIds@@YAJPEAPEAPEAGPEAK@Z`
- size: `2067`
- prototype: `__int64 __fastcall(unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180057dd4`

## callees

- `0x18000bfd0`
- `0x1800191c0`
- `0x18001b480`
- `0x180041eb0`
- `0x180057f70`
- `0x18005878c`
- `0x180058a08`
- `0x180058f80`
- `0x180058fc4`
- `0x1800597ec`
- `0x180059844`
- `0x180059ab4`
- `0x18005ad90`
- `0x18005af10`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800a3da8`
- `0x1800cf008`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005803f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005803f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800585a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800585a8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005825d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005825d`
- `ntdll!RtlNtStatusToDosError` at `0x18005864f`
- `ntdll!RtlNtStatusToDosError` at `0x18005864f`
- `ntdll!RtlGUIDFromString` at `0x1800582b5`
- `ntdll!RtlGUIDFromString` at `0x1800582b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800585f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800585f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005848d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005848d`
- `NSI!NsiFreeTable` at `0x18005818a`
- `NSI!NsiFreeTable` at `0x1800583cd`
- `NSI!NsiFreeTable` at `0x18005818a`
- `NSI!NsiFreeTable` at `0x1800583cd`
- `NSI!NsiAllocateAndGetTable` at `0x180058112`
- `NSI!NsiAllocateAndGetTable` at `0x180058112`

## pseudocode

```c
__int64 __fastcall LoadNetworkIds(unsigned __int16 ***a1, unsigned int *a2)
{
  GatewayIdList *v2; // rbx
  unsigned __int16 *v5; // rsi
  STRSAFE_LPWSTR v6; // rdi
  GatewayIdList *v7; // rax
  unsigned int v8; // edx
  unsigned int v9; // r14d
  int v10; // eax
  signed int v11; // r15d
  int AdaptersAddresses; // eax
  NTSTATUS Table; // eax
  __int64 v14; // r12
  ULONG v15; // eax
  bool v16; // sf
  struct _IP_ADAPTER_ADDRESSES_LH *v17; // r13
  unsigned int v18; // eax
  struct _NDIS_NSI_INTERFACE_ENUM_ROD *v19; // r15
  NTSTATUS v20; // eax
  int v21; // eax
  int GatewayIdList; // eax
  unsigned __int16 **v23; // r14
  unsigned int v24; // edx
  bool v25; // zf
  STRSAFE_LPWSTR v26; // rsi
  _QWORD *v27; // rdx
  __int64 v28; // r13
  unsigned int v30; // r13d
  __int64 j; // r14
  void *v32; // rcx
  _QWORD *v33; // r12
  int v34; // eax
  STRSAFE_LPWSTR v35; // r10
  HRESULT v36; // eax
  signed int LastError; // eax
  unsigned int v38; // r13d
  SIZE_T v39; // r12
  unsigned __int16 **v40; // rax
  unsigned __int16 **v41; // r8
  unsigned int i; // edx
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rax
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-E0h]
  STRSAFE_LPWSTR pszDest[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v48; // [rsp+90h] [rbp-70h]
  unsigned int v49; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v50; // [rsp+9Ch] [rbp-64h]
  LPVOID pv; // [rsp+A0h] [rbp-60h]
  unsigned __int16 **v52; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v53; // [rsp+B0h] [rbp-50h]
  struct _NDIS_NSI_INTERFACE_ENUM_ROS *v54; // [rsp+B8h] [rbp-48h]
  int v55; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v56; // [rsp+C8h] [rbp-38h]
  STRSAFE_LPWSTR v57; // [rsp+D0h] [rbp-30h]
  void *v58; // [rsp+D8h] [rbp-28h] BYREF
  int v59; // [rsp+E4h] [rbp-1Ch]
  STRSAFE_LPWSTR v60; // [rsp+E8h] [rbp-18h] BYREF
  struct _NDIS_NSI_INTERFACE_ENUM_ROD *v61; // [rsp+F0h] [rbp-10h]
  unsigned __int16 ***v62; // [rsp+F8h] [rbp-8h]
  unsigned int *v63; // [rsp+100h] [rbp+0h]
  __int64 v64; // [rsp+108h] [rbp+8h] BYREF
  __int64 v65; // [rsp+110h] [rbp+10h]
  __int64 v66; // [rsp+118h] [rbp+18h]
  struct _UNICODE_STRING GuidString; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v68; // [rsp+130h] [rbp+30h]
  GUID Guid; // [rsp+140h] [rbp+40h] BYREF
  WCHAR WideCharStr[40]; // [rsp+150h] [rbp+50h] BYREF

  v2 = 0;
  v63 = a2;
  v62 = a1;
  HIDWORD(pszDest[0]) = 0;
  v57 = 0;
  v58 = 0;
  v60 = 0;
  v5 = 0;
  v6 = 0;
  memset_0(WideCharStr, 0, 0x4Eu);
  v48 = 0;
  pv = 0;
  v52 = 0;
  GuidString = 0;
  v50 = 0;
  Guid = 0;
  v49 = 0;
  v55 = 0;
  v56 = 0;
  v53 = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_(1029, 31, WPP_862cb32ccfe33916531e6ec8d1ca0818_Traceguids);
  if ( a2 )
    *a2 = 0;
  if ( a1 )
    *a1 = 0;
  if ( !a2 )
  {
    v11 = -2147024809;
    HIDWORD(pszDest[0]) = 1005;
    goto LABEL_48;
  }
  if ( !a1 )
  {
    v11 = -2147024809;
    HIDWORD(pszDest[0]) = 1006;
    goto LABEL_48;
  }
  v7 = (GatewayIdList *)HeapAlloc(g_hWxProcessHeap, 0, 0x30u);
  v9 = 0;
  v2 = v7;
  if ( !v7 )
  {
    HIDWORD(pszDest[0]) = 1010;
    v2 = 0;
    v11 = -2147024882;
    goto LABEL_48;
  }
  *((_QWORD *)v7 + 3) = 0;
  *((_QWORD *)v7 + 4) = 0;
  *((_QWORD *)v7 + 5) = 0;
  *(_QWORD *)v7 = 0;
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  v10 = GatewayIdList::Initialize(v7, v8);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 < 0 )
  {
    HIDWORD(pszDest[0]) = 1012;
    goto LABEL_48;
  }
  pszDest[0] = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v68 = 0;
  v60 = 0;
  AdaptersAddresses = WxGetAdaptersAddresses(0x88Eu, (struct _IP_ADAPTER_ADDRESSES_LH **)pszDest);
  if ( AdaptersAddresses < 0 )
  {
    v15 = WX_WIN32_FROM_HR((unsigned int)AdaptersAddresses);
  }
  else
  {
    LODWORD(lpWideCharStr) = 8;
    Table = NsiAllocateAndGetTable(1, &NPI_MS_NDIS_MODULEID, 1, &v64);
    if ( Table >= 0 )
    {
      v11 = 0;
      v6 = pszDest[0];
      v14 = v64;
      v9 = v68;
      v56 = v65;
      v53 = v66;
      v64 = 0;
      v65 = 0;
      v66 = 0;
      v68 = 0;
      v60 = pszDest[0];
      v48 = v14;
      goto LABEL_23;
    }
    v15 = RtlNtStatusToDosError(Table);
  }
  v11 = v15;
  v48 = 0;
  v56 = 0;
  v53 = 0;
  if ( v64 || v65 || v66 )
  {
    NsiFreeTable(v64, 0, v65, v66);
    v64 = 0;
    v65 = 0;
    v66 = 0;
  }
  if ( pszDest[0] )
    WxFreeHeapEx(pszDest);
  v14 = 0;
  v16 = v11 < 0;
  if ( v11 <= 0 )
    goto LABEL_24;
  v11 = (unsigned __int16)v11 | 0x80070000;
LABEL_23:
  v16 = v11 < 0;
LABEL_24:
  if ( v16 )
  {
    HIDWORD(pszDest[0]) = 1022;
    goto LABEL_48;
  }
  v17 = (struct _IP_ADAPTER_ADDRESSES_LH *)v6;
  while ( 1 )
  {
    if ( !v17 )
    {
      GatewayIdList = GatewayIdList::GetGatewayIdList(v2, &v52, &v49, &v55);
      v11 = GatewayIdList;
      if ( GatewayIdList > 0 )
        v11 = (unsigned __int16)GatewayIdList | 0x80070000;
      if ( v11 < 0 )
      {
        pv = v52;
        v50 = v49;
        HIDWORD(pszDest[0]) = 1113;
        goto LABEL_48;
      }
      if ( !v55 )
      {
        v11 = -2147024637;
        pv = v52;
        v50 = v49;
        HIDWORD(pszDest[0]) = 1116;
        goto LABEL_48;
      }
      v11 = 0;
      if ( v5 )
      {
        v38 = v49;
        v59 = 0;
        v50 = v49;
        v39 = 8 * v49 + 8;
        v40 = (unsigned __int16 **)CoTaskMemAlloc(v39);
        v23 = v40;
        if ( !v40 )
        {
          v11 = -2147024882;
          v59 = 76;
          pv = v52;
          HIDWORD(pszDest[0]) = 1138;
          goto LABEL_48;
        }
        memset_0(v40, 0, v39);
        v41 = v52;
        pv = v52;
        for ( i = 0; i < v38; v41[v44] = 0 )
        {
          v43 = i++;
          v44 = v43;
          v23[v44] = v41[v43];
        }
        v45 = i;
        v24 = i + 1;
        v57 = 0;
        v58 = 0;
        v23[v45] = v5;
      }
      else
      {
        v23 = v52;
        v24 = v49;
        pv = 0;
      }
      v50 = 0;
      *v62 = v23;
      *v63 = v24;
      goto LABEL_48;
    }
    memset_0(WideCharStr, 0, 0x4Eu);
    v18 = 0;
    v61 = 0;
    GuidString = 0;
    v19 = 0;
    v54 = 0;
    Guid = 0;
    LODWORD(pszDest[0]) = 0;
    while ( v18 < v9 )
    {
      if ( *(_QWORD *)(v14 + 8LL * v18) == v17->Luid.Value )
      {
        v19 = (struct _NDIS_NSI_INTERFACE_ENUM_ROD *)(v56 + 656LL * v18);
        v61 = v19;
        v54 = (struct _NDIS_NSI_INTERFACE_ENUM_ROS *)(v53 + 568LL * v18);
        break;
      }
      ++v18;
    }
    if ( !MultiByteToWideChar(0, 0, v17->AdapterName, 39, WideCharStr, 39) )
      break;
    IsAdapterFiltered(v17, v19, v54, (int *)pszDest);
    if ( LODWORD(pszDest[0]) )
    {
      v17 = v17->Next;
    }
    else if ( (unsigned int)IsMediaWwan(WideCharStr) )
    {
      if ( v5 )
      {
        v17 = v17->Next;
      }
      else
      {
        HIDWORD(v54) = 0;
        pszDest[0] = 0;
        v5 = 0;
        v57 = 0;
        v58 = 0;
        v34 = WxAllocZero<unsigned short,WxCoTaskAllocator>(0x58u, pszDest);
        v35 = pszDest[0];
        v11 = v34;
        if ( v34 < 0 )
        {
          HIDWORD(v54) = 544;
          goto LABEL_84;
        }
        v36 = StringCchCopyW(pszDest[0], 0x2Cu, L"{WWAN-D00AA0AC-5A6E-4001-B586-E4B72BECDC19}");
        v11 = v36;
        if ( v36 < 0 )
        {
          HIDWORD(v54) = 548;
LABEL_84:
          if ( v35 )
            WxCoTaskAllocator::Free((void **)pszDest);
          if ( v11 < 0 )
          {
            HIDWORD(pszDest[0]) = 1089;
            goto LABEL_48;
          }
          goto LABEL_40;
        }
        v17 = v17->Next;
        v5 = v35;
        v57 = v35;
        v58 = v35;
        LODWORD(pszDest[0]) = v36;
      }
    }
    else
    {
      *(_DWORD *)&GuidString.Length = 5111884;
      GuidString.Buffer = WideCharStr;
      v20 = RtlGUIDFromString(&GuidString, &Guid);
      v11 = HRESULT_FROM_NTSTATUS(v20);
      if ( v11 < 0 )
      {
        HIDWORD(pszDest[0]) = 1097;
        goto LABEL_48;
      }
      *(GUID *)pszDest = Guid;
      v21 = GatewayIdList::AddGatewayIdsForAdapter(v2, (struct _GUID *)pszDest, v61, v54);
      v11 = v21;
      if ( v21 > 0 )
        v11 = (unsigned __int16)v21 | 0x80070000;
      if ( v11 < 0 )
      {
        HIDWORD(pszDest[0]) = 1105;
        goto LABEL_48;
      }
LABEL_40:
      v17 = v17->Next;
    }
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  HIDWORD(pszDest[0]) = 1065;
  if ( v11 >= 0 )
    v11 = -2147418113;
LABEL_48:
  v25 = (xmmword_180107A60 & 0x20) == 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    WPP_SF_(1029, 16, WPP_927dd49ceab235c34f59e6ea3b7830f7_Traceguids);
    v25 = (xmmword_180107A60 & 0x20) == 0;
  }
  v26 = v57;
  if ( !v25 )
    WPP_SF_(1029, 17, WPP_927dd49ceab235c34f59e6ea3b7830f7_Traceguids);
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_(1029, 16, WPP_927dd49ceab235c34f59e6ea3b7830f7_Traceguids);
  v27 = pv;
  if ( pv )
  {
    v30 = v50;
    for ( j = 0; (unsigned int)j < v30; j = (unsigned int)(j + 1) )
    {
      v32 = (void *)v27[j];
      v33 = &v27[j];
      if ( v32 )
      {
        CoTaskMemFree(v32);
        v27 = pv;
        *v33 = 0;
      }
    }
    CoTaskMemFree(v27);
  }
  v28 = v48;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_(1029, 17, WPP_927dd49ceab235c34f59e6ea3b7830f7_Traceguids);
  if ( v28 || v56 || v53 )
    NsiFreeTable(v28, 0, v56, v53);
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 32, WPP_862cb32ccfe33916531e6ec8d1ca0818_Traceguids, (unsigned int)v11, lpWideCharStr);
  if ( v2 )
  {
    GatewayIdList::Uninitialize(v2);
    operator delete(v2);
  }
  if ( v6 )
    WxFreeHeapEx(&v60);
  if ( v26 )
    WxCoTaskAllocator::Free(&v58);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180057f70  mov     [rsp-8+arg_10], rbx
0x180057f75  push    rbp
0x180057f76  push    rsi
0x180057f77  push    rdi
0x180057f78  push    r12
0x180057f7a  push    r13
0x180057f7c  push    r14
0x180057f7e  push    r15
0x180057f80  lea     rbp, [rsp-0B0h]
0x180057f88  sub     rsp, 1B0h
0x180057f8f  mov     rax, cs:__security_cookie
0x180057f96  xor     rax, rsp
0x180057f99  mov     [rbp+0E0h+var_40], rax
0x180057fa0  xor     ebx, ebx
0x180057fa2  mov     [rbp+0E0h+var_E0], rdx
0x180057fa6  mov     r15, rdx
0x180057fa9  mov     [rbp+0E0h+var_E8], rcx
0x180057fad  mov     r14, rcx
0x180057fb0  mov     dword ptr [rbp+0E0h+pszDest+4], ebx
0x180057fb3  xor     edx, edx; Val
0x180057fb5  mov     [rbp+0E0h+var_110], rbx
0x180057fb9  lea     rcx, [rbp+0E0h+WideCharStr]; void *
0x180057fbd  mov     [rbp+0E0h+var_108], rbx
0x180057fc1  mov     r8d, 4Eh ; 'N'; Size
0x180057fc7  mov     [rbp+0E0h+var_F8], rbx
0x180057fcb  mov     esi, ebx
0x180057fcd  mov     edi, ebx
0x180057fcf  call    memset_0
0x180057fd4  xor     eax, eax
0x180057fd6  mov     [rbp+0E0h+var_150], rbx
0x180057fda  xorps   xmm0, xmm0
0x180057fdd  mov     [rbp+0E0h+pv], rax
0x180057fe1  xorps   xmm1, xmm1
0x180057fe4  mov     [rbp+0E0h+var_138], rax
0x180057fe8  movups  xmmword ptr [rbp+0E0h+GuidString.Length], xmm0
0x180057fec  mov     [rbp+0E0h+var_144], eax
0x180057fef  movups  xmmword ptr [rbp+0E0h+Guid.Data1], xmm1
0x180057ff3  mov     [rbp+0E0h+var_148], eax
0x180057ff6  mov     [rbp+0E0h+var_120], eax
0x180057ff9  mov     [rbp+0E0h+var_118], rbx
0x180057ffd  mov     [rbp+0E0h+var_130], rbx
0x180058001  test    byte ptr cs:xmmword_180107A60, 20h
0x180058008  jnz     loc_180058624
0x18005800e  test    r15, r15
0x180058011  jz      short loc_180058016
0x180058013  mov     [r15], eax
0x180058016  test    r14, r14
0x180058019  jz      short loc_18005801E
0x18005801b  mov     [r14], rax
0x18005801e  test    r15, r15
0x180058021  jz      loc_180058445
0x180058027  test    r14, r14
0x18005802a  jz      loc_180058498
0x180058030  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180058037  xor     edx, edx; dwFlags
0x180058039  mov     r8d, 30h ; '0'; dwBytes
0x18005803f  call    cs:__imp_HeapAlloc
0x180058045  xor     r14d, r14d
0x180058048  mov     rbx, rax
0x18005804b  test    rax, rax
0x18005804e  jz      loc_1800584AA
0x180058054  mov     [rax+18h], r14
0x180058058  mov     rcx, rax; this
0x18005805b  mov     [rax+20h], r14
0x18005805f  mov     [rax+28h], r14
0x180058063  mov     [rax], r14
0x180058066  mov     [rax+8], r14
0x18005806a  mov     [rax+10h], r14
0x18005806e  call    ?Initialize@GatewayIdList@@QEAAKK@Z; GatewayIdList::Initialize(ulong)
0x180058073  mov     r15d, eax
0x180058076  test    eax, eax
0x180058078  jle     short loc_180058085
0x18005807a  movzx   r15d, ax
0x18005807e  or      r15d, 80070000h
0x180058085  test    r15d, r15d
0x180058088  js      loc_180058641
0x18005808e  lea     rdx, [rbp+0E0h+pszDest]; struct _IP_ADAPTER_ADDRESSES_LH **
0x180058092  mov     [rbp+0E0h+pszDest], r14
0x180058096  mov     ecx, 88Eh; Flags
0x18005809b  mov     [rbp+0E0h+var_D8], r14
0x18005809f  mov     [rbp+0E0h+var_D0], r14
0x1800580a3  mov     [rbp+0E0h+var_C8], r14
0x1800580a7  mov     [rbp+0E0h+var_B0], r14d
0x1800580ab  mov     [rbp+0E0h+var_F8], r14
0x1800580af  call    ?WxGetAdaptersAddresses@@YAJKPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z; WxGetAdaptersAddresses(ulong,_IP_ADAPTER_ADDRESSES_LH * *)
0x1800580b4  test    eax, eax
0x1800580b6  js      loc_18005815D
0x1800580bc  mov     [rsp+1E0h+var_180], sil
0x1800580c1  lea     rax, [rbp+0E0h+var_B0]
0x1800580c5  mov     [rsp+1E0h+var_188], rax
0x1800580ca  lea     r9, [rbp+0E0h+var_D8]
0x1800580ce  mov     [rsp+1E0h+var_190], 238h
0x1800580d6  lea     rax, [rbp+0E0h+var_C8]
0x1800580da  mov     [rsp+1E0h+var_198], rax
0x1800580df  lea     rdx, NPI_MS_NDIS_MODULEID
0x1800580e6  mov     [rsp+1E0h+var_1A0], 290h
0x1800580ee  lea     rax, [rbp+0E0h+var_D0]
0x1800580f2  mov     [rsp+1E0h+var_1A8], rax
0x1800580f7  mov     r8d, 1
0x1800580fd  mov     [rsp+1E0h+var_1B0], r14d
0x180058102  mov     ecx, r8d
0x180058105  mov     qword ptr [rsp+1E0h+cchWideChar], r14
0x18005810a  mov     dword ptr [rsp+1E0h+lpWideCharStr], 8
0x180058112  call    cs:__imp_NsiAllocateAndGetTable
0x180058118  test    eax, eax
0x18005811a  js      loc_18005864D
0x180058120  mov     rax, [rbp+0E0h+var_D0]
0x180058124  mov     r15d, r14d
0x180058127  mov     r13, [rbp+0E0h+var_D8]
0x18005812b  mov     rdi, [rbp+0E0h+pszDest]
0x18005812f  mov     r12, r13
0x180058132  mov     r14d, [rbp+0E0h+var_B0]
0x180058136  mov     [rbp+0E0h+var_118], rax
0x18005813a  mov     rax, [rbp+0E0h+var_C8]
0x18005813e  mov     [rbp+0E0h+var_130], rax
0x180058142  xor     eax, eax
0x180058144  mov     [rbp+0E0h+var_D8], rax
0x180058148  mov     [rbp+0E0h+var_D0], rax
0x18005814c  mov     [rbp+0E0h+var_C8], rax
0x180058150  mov     [rbp+0E0h+var_B0], eax
0x180058153  mov     [rbp+0E0h+var_F8], rdi
0x180058157  mov     [rbp+0E0h+var_150], r13
0x18005815b  jmp     short loc_1800581C0
0x18005815d  mov     ecx, eax
0x18005815f  call    WX_WIN32_FROM_HR
0x180058164  mov     r15d, eax
0x180058167  mov     rcx, [rbp+0E0h+var_D8]
0x18005816b  mov     r8, [rbp+0E0h+var_D0]
0x18005816f  mov     r9, [rbp+0E0h+var_C8]
0x180058173  mov     [rbp+0E0h+var_150], r14
0x180058177  mov     [rbp+0E0h+var_118], r14
0x18005817b  mov     [rbp+0E0h+var_130], r14
0x18005817f  test    rcx, rcx
0x180058182  jz      loc_18005865A
0x180058188  xor     edx, edx
0x18005818a  call    cs:__imp_NsiFreeTable
0x180058190  xor     eax, eax
0x180058192  mov     [rbp+0E0h+var_D8], rax
0x180058196  mov     [rbp+0E0h+var_D0], rax
0x18005819a  mov     [rbp+0E0h+var_C8], rax
0x18005819e  cmp     [rbp+0E0h+pszDest], rsi
0x1800581a2  jz      short loc_1800581AD
0x1800581a4  lea     rcx, [rbp+0E0h+pszDest]
0x1800581a8  call    WxFreeHeapEx
0x1800581ad  mov     r12, r14
0x1800581b0  test    r15d, r15d
0x1800581b3  jle     short loc_1800581C3
0x1800581b5  movzx   r15d, r15w
0x1800581b9  or      r15d, 80070000h
0x1800581c0  test    r15d, r15d
0x1800581c3  js      loc_180058593
0x1800581c9  mov     r13, rdi
0x1800581cc  nop     dword ptr [rax+00h]
0x1800581d0  test    r13, r13
0x1800581d3  jz      loc_18005830E
0x1800581d9  xor     edx, edx; Val
0x1800581db  lea     rcx, [rbp+0E0h+WideCharStr]; void *
0x1800581df  mov     r8d, 4Eh ; 'N'; Size
0x1800581e5  call    memset_0
0x1800581ea  xor     eax, eax
0x1800581ec  xorps   xmm0, xmm0
0x1800581ef  xorps   xmm1, xmm1
0x1800581f2  mov     [rbp+0E0h+var_F0], rax
0x1800581f6  movups  xmmword ptr [rbp+0E0h+GuidString.Length], xmm0
0x1800581fa  mov     r15d, eax
0x1800581fd  mov     [rbp+0E0h+var_128], rax
0x180058201  movups  xmmword ptr [rbp+0E0h+Guid.Data1], xmm1
0x180058205  mov     dword ptr [rbp+0E0h+pszDest], eax
0x180058208  cmp     eax, r14d
0x18005820b  jnb     short loc_18005823E
0x18005820d  mov     rcx, [r13+0E0h]
0x180058214  mov     edx, eax
0x180058216  cmp     [r12+rdx*8], rcx
0x18005821a  jz      short loc_180058220
0x18005821c  inc     eax
0x18005821e  jmp     short loc_180058208
0x180058220  imul    r15, rdx, 290h
0x180058227  imul    rax, rdx, 238h
0x18005822e  add     r15, [rbp+0E0h+var_118]
0x180058232  mov     [rbp+0E0h+var_F0], r15
0x180058236  add     rax, [rbp+0E0h+var_130]
0x18005823a  mov     [rbp+0E0h+var_128], rax
0x18005823e  mov     r8, [r13+10h]; lpMultiByteStr
0x180058242  lea     rax, [rbp+0E0h+WideCharStr]
0x180058246  mov     [rsp+1E0h+cchWideChar], 27h ; '''; cchWideChar
0x18005824e  mov     r9d, 27h ; '''; cbMultiByte
0x180058254  xor     edx, edx; dwFlags
0x180058256  mov     [rsp+1E0h+lpWideCharStr], rax; lpWideCharStr
0x18005825b  xor     ecx, ecx; CodePage
0x18005825d  call    cs:__imp_MultiByteToWideChar
0x180058263  test    eax, eax
0x180058265  jz      loc_1800585A8
0x18005826b  mov     r8, [rbp+0E0h+var_128]; struct _NDIS_NSI_INTERFACE_ENUM_ROS *
0x18005826f  lea     r9, [rbp+0E0h+pszDest]; int *
0x180058273  mov     rdx, r15; struct _NDIS_NSI_INTERFACE_ENUM_ROD *
0x180058276  mov     rcx, r13; struct _IP_ADAPTER_ADDRESSES_LH *
0x180058279  call    ?IsAdapterFiltered@@YAKPEAU_IP_ADAPTER_ADDRESSES_LH@@PEAU_NDIS_NSI_INTERFACE_ENUM_ROD@@PEAU_NDIS_NSI_INTERFACE_ENUM_ROS@@PEAH@Z; IsAdapterFiltered(_IP_ADAPTER_ADDRESSES_LH *,_NDIS_NSI_INTERFACE_ENUM_ROD *,_NDIS_NSI_INTERFACE_ENUM_ROS *,int *)
0x18005827e  cmp     dword ptr [rbp+0E0h+pszDest], 0
0x180058282  jz      short loc_18005828D
0x180058284  mov     r13, [r13+8]
0x180058288  jmp     loc_1800581D0
0x18005828d  lea     rcx, [rbp+0E0h+WideCharStr]; unsigned __int16 *
0x180058291  call    ?IsMediaWwan@@YAHPEBG@Z; IsMediaWwan(ushort const *)
0x180058296  test    eax, eax
0x180058298  jnz     loc_1800584BF
0x18005829e  lea     rax, [rbp+0E0h+WideCharStr]
0x1800582a2  mov     dword ptr [rbp+0E0h+GuidString.Length], 4E004Ch
0x1800582a9  lea     rdx, [rbp+0E0h+Guid]; Guid
0x1800582ad  mov     [rbp+0E0h+GuidString.Buffer], rax
0x1800582b1  lea     rcx, [rbp+0E0h+GuidString]; GuidString
0x1800582b5  call    cs:__imp_RtlGUIDFromString
0x1800582bb  mov     ecx, eax; int
0x1800582bd  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x1800582c2  mov     r15d, eax
0x1800582c5  test    eax, eax
0x1800582c7  js      loc_18005867D
0x1800582cd  movaps  xmm0, xmmword ptr [rbp+0E0h+Guid.Data1]
0x1800582d1  lea     rdx, [rbp+0E0h+pszDest]; struct _GUID
0x1800582d5  mov     r9, [rbp+0E0h+var_128]; struct _NDIS_NSI_INTERFACE_ENUM_ROS *
0x1800582d9  mov     rcx, rbx; this
0x1800582dc  mov     r8, [rbp+0E0h+var_F0]; struct _NDIS_NSI_INTERFACE_ENUM_ROD *
0x1800582e0  movdqa  xmmword ptr [rbp+0E0h+pszDest], xmm0
0x1800582e5  call    ?AddGatewayIdsForAdapter@GatewayIdList@@QEAAKU_GUID@@PEAU_NDIS_NSI_INTERFACE_ENUM_ROD@@PEAU_NDIS_NSI_INTERFACE_ENUM_ROS@@@Z; GatewayIdList::AddGatewayIdsForAdapter(_GUID,_NDIS_NSI_INTERFACE_ENUM_ROD *,_NDIS_NSI_INTERFACE_ENUM_ROS *)
0x1800582ea  mov     r15d, eax
0x1800582ed  test    eax, eax
0x1800582ef  jle     short loc_1800582FC
0x1800582f1  movzx   r15d, ax
0x1800582f5  or      r15d, 80070000h
0x1800582fc  test    r15d, r15d
0x1800582ff  js      loc_180058671
0x180058305  mov     r13, [r13+8]
0x180058309  jmp     loc_1800581D0
0x18005830e  lea     r9, [rbp+0E0h+var_120]; int *
0x180058312  mov     rcx, rbx; this
0x180058315  lea     r8, [rbp+0E0h+var_148]; unsigned int *
0x180058319  lea     rdx, [rbp+0E0h+var_138]; unsigned __int16 ***
0x18005831d  call    ?GetGatewayIdList@GatewayIdList@@QEAAKPEAPEAPEAGPEAKPEAH@Z; GatewayIdList::GetGatewayIdList(ushort * * *,ulong *,int *)
0x180058322  mov     r15d, eax
0x180058325  test    eax, eax
0x180058327  jle     short loc_180058334
0x180058329  movzx   r15d, ax
0x18005832d  or      r15d, 80070000h
0x180058334  test    r15d, r15d
0x180058337  js      loc_18005854F
0x18005833d  cmp     [rbp+0E0h+var_120], 0
0x180058341  jz      loc_18005852F
0x180058347  xor     r9d, r9d
0x18005834a  mov     r15d, r9d
0x18005834d  test    rsi, rsi
0x180058350  jnz     loc_1800585D8
0x180058356  mov     r14, [rbp+0E0h+var_138]
0x18005835a  mov     edx, [rbp+0E0h+var_148]
0x18005835d  mov     [rbp+0E0h+pv], r9
0x180058361  mov     rax, [rbp+0E0h+var_E8]
0x180058365  mov     [rbp+0E0h+var_144], r9d
0x180058369  mov     [rax], r14
0x18005836c  mov     rax, [rbp+0E0h+var_E0]
0x180058370  mov     [rax], edx
0x180058372  test    byte ptr cs:xmmword_180107A60, 20h
0x180058379  jnz     loc_1800586DB
0x18005837f  mov     rsi, [rbp+0E0h+var_110]
0x180058383  jnz     loc_1800586FD
0x180058389  test    byte ptr cs:xmmword_180107A60, 20h
0x180058390  jnz     loc_180058718
0x180058396  mov     rdx, [rbp+0E0h+pv]
0x18005839a  test    rdx, rdx
0x18005839d  jnz     loc_180058457
0x1800583a3  test    byte ptr cs:xmmword_180107A60, 20h
0x1800583aa  mov     r13, [rbp+0E0h+var_150]
0x1800583ae  jnz     loc_180058733
0x1800583b4  mov     rax, [rbp+0E0h+var_118]
0x1800583b8  mov     r9, [rbp+0E0h+var_130]
0x1800583bc  test    r13, r13
0x1800583bf  jz      loc_18005874E
0x1800583c5  mov     r8, rax
0x1800583c8  xor     edx, edx
0x1800583ca  mov     rcx, r13
0x1800583cd  call    cs:__imp_NsiFreeTable
0x1800583d3  test    byte ptr cs:xmmword_180107A60, 20h
0x1800583da  jnz     loc_180058765
0x1800583e0  test    rbx, rbx
0x1800583e3  jz      short loc_1800583FA
0x1800583e5  mov     rcx, rbx; this
0x1800583e8  call    ?Uninitialize@GatewayIdList@@QEAAXXZ; GatewayIdList::Uninitialize(void)
0x1800583ed  mov     edx, 30h ; '0'; unsigned __int64
0x1800583f2  mov     rcx, rbx; void *
0x1800583f5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800583fa  test    rdi, rdi
0x1800583fd  jnz     short loc_18005843A
0x1800583ff  test    rsi, rsi
0x180058402  jz      short loc_18005840D
0x180058404  lea     rcx, [rbp+0E0h+var_108]; void **
0x180058408  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x18005840d  mov     eax, r15d
0x180058410  mov     rcx, [rbp+0E0h+var_40]
0x180058417  xor     rcx, rsp; StackCookie
0x18005841a  call    __security_check_cookie
0x18005841f  mov     rbx, [rsp+1E0h+arg_10]
0x180058427  add     rsp, 1B0h
0x18005842e  pop     r15
  ... truncated ...
```
