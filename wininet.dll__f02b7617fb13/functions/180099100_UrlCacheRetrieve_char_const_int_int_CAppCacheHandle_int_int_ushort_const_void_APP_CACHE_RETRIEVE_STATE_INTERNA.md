# UrlCacheRetrieve(char const *,int,int,CAppCacheHandle *,int,int,ushort const *,void * *,_APP_CACHE_RETRIEVE_STATE *,_INTERNAL_CACHE_ENTRY_INFOEX * *,uchar * *,ulong *,ulong *,unsigned __int64 *)

- ea: `0x180099100`
- end: `0x180099703`
- name: `?UrlCacheRetrieve@@YAKPEBDHHPEAVCAppCacheHandle@@HHPEBGPEAPEAXPEAU_APP_CACHE_RETRIEVE_STATE@@PEAPEAU_INTERNAL_CACHE_ENTRY_INFOEX@@PEAPEAEPEAK7PEA_K@Z`
- size: `1539`
- prototype: `unsigned int __usercall@<eax>(LPCCH lpMultiByteStr@<rcx>, int@<edx>, int@<r8d>, struct CAppCacheHandle *@<r9>, int, int, const unsigned __int16 *, void **, struct _APP_CACHE_RETRIEVE_STATE *, struct _INTERNAL_CACHE_ENTRY_INFOEX **, unsigned __int8 **, unsigned int *, unsigned int *, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800cf67c`
- `0x18012fa90`
- `0x180146628`
- `0x18017b25c`

## callees

- `0x1800701d0`
- `0x180099100`
- `0x18009970c`
- `0x18009a424`
- `0x18009aac8`
- `0x1800a0ef8`
- `0x1800d168c`
- `0x1800f2c40`
- `0x18014a7a0`
- `0x1801a0e74`
- `0x1801e0330`
- `0x1801e1790`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800994bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800994bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099365`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180099365`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180099497`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180099497`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800994af`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800994af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009926f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009926f`
- `ntdll!RtlNtStatusToDosError` at `0x1800996ac`
- `ntdll!RtlNtStatusToDosError` at `0x1800996e0`
- `ntdll!RtlNtStatusToDosError` at `0x1800996ac`
- `ntdll!RtlNtStatusToDosError` at `0x1800996e0`

## pseudocode

```c
__int64 __fastcall UrlCacheRetrieve(
        LPCCH lpMultiByteStr,
        __int64 a2,
        int a3,
        struct CAppCacheHandle *a4,
        int a5,
        int a6,
        unsigned __int16 *a7,
        void **a8,
        struct _APP_CACHE_RETRIEVE_STATE *a9,
        struct _INTERNAL_CACHE_ENTRY_INFOEX **a10,
        unsigned __int8 **a11,
        unsigned int *a12,
        unsigned int *a13,
        unsigned __int64 *a14)
{
  int v14; // r15d
  void *v17; // r14
  struct CCacheClientEntry *v18; // rbx
  int v19; // ecx
  int v20; // eax
  signed int CanProcessImpersonate; // esi
  void **v22; // r15
  __int64 v23; // rdx
  ULONG v24; // eax
  unsigned int v25; // edi
  void **v27; // rcx
  unsigned int v28; // r8d
  int v29; // eax
  void *v30; // rcx
  HANDLE CurrentThread; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  int LastError; // eax
  unsigned int v35; // eax
  ULONG v36; // eax
  signed __int32 v37[8]; // [rsp+0h] [rbp-F9h] BYREF
  unsigned int *v38; // [rsp+20h] [rbp-D9h]
  int v39; // [rsp+80h] [rbp-79h] BYREF
  int v40; // [rsp+84h] [rbp-75h]
  int v41; // [rsp+88h] [rbp-71h] BYREF
  void *v42; // [rsp+90h] [rbp-69h] BYREF
  LPVOID lpMem; // [rsp+98h] [rbp-61h] BYREF
  struct _APP_CACHE_RETRIEVE_STATE *v44; // [rsp+A0h] [rbp-59h]
  struct CCacheClientEntry *v45; // [rsp+A8h] [rbp-51h] BYREF
  struct _INTERNAL_CACHE_ENTRY_INFOEX **v46; // [rsp+B0h] [rbp-49h]
  unsigned int *v47; // [rsp+B8h] [rbp-41h]
  unsigned __int8 **v48; // [rsp+C0h] [rbp-39h]
  void **v49; // [rsp+C8h] [rbp-31h]
  unsigned __int64 *v50; // [rsp+D0h] [rbp-29h]
  unsigned __int16 *v51; // [rsp+D8h] [rbp-21h]
  struct CAppCacheHandle *v52; // [rsp+E0h] [rbp-19h]
  HANDLE hObject; // [rsp+E8h] [rbp-11h] BYREF

  v14 = 0;
  v17 = 0;
  v50 = a14;
  v18 = 0;
  v52 = a4;
  v45 = 0;
  v51 = a7;
  v49 = a8;
  v44 = a9;
  v46 = a10;
  v48 = a11;
  v47 = a12;
  v40 = 0;
  lpMem = 0;
  v42 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_sllqllSqqqqq(
      (_DWORD)a11,
      (_DWORD)a12,
      (_DWORD)a9,
      (_DWORD)lpMultiByteStr,
      (_DWORD)v38,
      a3,
      (__int64)a4,
      a5,
      a6,
      (__int64)a7,
      (__int64)a8,
      (__int64)a9,
      (__int64)a10,
      (__int64)a11,
      (__int64)a12);
  if ( a13 )
    *a13 = 11;
  if ( !lpMultiByteStr )
  {
    CanProcessImpersonate = -2147024809;
    v40 = 265;
    goto LABEL_37;
  }
  if ( a13 )
    *a13 = 12;
  v40 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
    WPP_SF_d(1038, 17, WPP_1f863943467533a4b627fcbad4e97ae1_Traceguids, 2);
  v19 = 0;
  v40 = 0;
  hObject = 0;
  v41 = 0;
  v39 = 0;
  if ( g_fCanProcessImpersonateCached )
  {
    _InterlockedOr(v37, 0);
    v20 = g_fCanProcessImpersonate;
  }
  else
  {
    CanProcessImpersonate = WxCanProcessImpersonate(&v41, &v39);
    if ( CanProcessImpersonate < 0 )
    {
      v40 = 885;
      goto LABEL_14;
    }
    v20 = v41;
    if ( v41 )
      g_fCanProcessImpersonate = 1;
    _InterlockedOr(v37, 0);
    v19 = v39;
    g_fCanProcessImpersonateCached = 1;
  }
  if ( !v20 )
  {
LABEL_13:
    CanProcessImpersonate = 1;
    goto LABEL_14;
  }
  if ( v19 || (CurrentThread = GetCurrentThread(), OpenThreadToken(CurrentThread, 0x20008u, 1, &hObject)) )
  {
    CanProcessImpersonate = 0;
  }
  else
  {
    if ( GetLastError() == 1008 )
      goto LABEL_13;
    LastError = WxGetLastError(v33, v32);
    CanProcessImpersonate = LastError;
    if ( LastError > 0 )
      CanProcessImpersonate = (unsigned __int16)LastError | 0x80070000;
    v40 = 914;
    if ( CanProcessImpersonate >= 0 )
      CanProcessImpersonate = -2147418113;
  }
LABEL_14:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( CanProcessImpersonate < 0 )
  {
    v40 = 248;
    v14 = CanProcessImpersonate;
  }
  else if ( CanProcessImpersonate == 1 )
  {
    CanProcessImpersonate = 0;
  }
  else
  {
    CanProcessImpersonate = -2147024894;
    v40 = 249;
    v14 = -2147024894;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
    WPP_SF_d(1038, 18, WPP_1f863943467533a4b627fcbad4e97ae1_Traceguids, (unsigned int)CanProcessImpersonate);
  if ( v14 < 0 )
  {
    v40 = 272;
  }
  else
  {
    if ( a13 )
      *a13 = 5;
    v22 = v49;
    if ( v49 )
      *v49 = 0;
    if ( v48 )
      *v48 = 0;
    if ( v47 )
      *v47 = 0;
    if ( v44 )
      *(_OWORD *)v44 = 0;
    *v46 = 0;
    if ( a3 )
    {
      LODWORD(v17) = 20;
      if ( a6 )
        LODWORD(v17) = 16;
      if ( a5 )
        LODWORD(v17) = (unsigned int)v17 | 0x20;
    }
    v23 = -1;
    do
      ++v23;
    while ( lpMultiByteStr[v23] );
    CanProcessImpersonate = ConvertCacheCharToWChar(lpMultiByteStr, v23, 0xFDE9u, (unsigned __int16 **)&lpMem, 0);
    if ( CanProcessImpersonate < 0 )
    {
      v17 = lpMem;
      v40 = 328;
      goto LABEL_37;
    }
    v27 = &v42;
    v28 = (unsigned int)v17;
    v17 = lpMem;
    if ( !v22 )
      v27 = 0;
    v29 = RetrieveUrlCacheEntryStreamHelper((const unsigned __int16 *)lpMem, v52, v28, 0, v51, v27, v44, &v45, a13, v50);
    v18 = v45;
    CanProcessImpersonate = v29;
    if ( v29 < 0 )
    {
      v30 = v42;
      v40 = 347;
      goto LABEL_56;
    }
    CanProcessImpersonate = ConvertInternalCacheEntryInfo((struct CCacheClientEntry *)((char *)v45 + 8), v46);
    if ( CanProcessImpersonate >= 0 )
    {
      if ( v22 )
      {
        v30 = 0;
        *v22 = v42;
      }
      else
      {
        v30 = v42;
      }
      if ( *((_QWORD *)v18 + 19) )
      {
        v35 = *((_DWORD *)v18 + 20);
        if ( v35 )
        {
          if ( v47 )
            *v47 = v35;
          if ( v48 )
          {
            *v48 = (unsigned __int8 *)*((_QWORD *)v18 + 19);
            *((_QWORD *)v18 + 19) = 0;
            *((_DWORD *)v18 + 20) = 0;
          }
        }
      }
LABEL_56:
      if ( !v30 )
        goto LABEL_37;
      goto LABEL_57;
    }
    v30 = v42;
    v40 = 355;
    if ( v42 )
    {
LABEL_57:
      UnlockUrlCacheEntryStreamHelper(v30);
      goto LABEL_37;
    }
    UnlockUrlCacheEntryFileHelper(*((const unsigned __int16 **)v18 + 13));
  }
LABEL_37:
  if ( v17 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v17);
    else
      HeapFree(g_hWxProcessHeap, 0, v17);
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
  {
    if ( (CanProcessImpersonate & 0x1FFF0000) == 0xC0000 )
    {
      v24 = (unsigned __int16)CanProcessImpersonate;
    }
    else if ( CanProcessImpersonate < 0 )
    {
      if ( (CanProcessImpersonate & 0x1FFF0000) == 0x70000 )
      {
        v24 = (unsigned __int16)CanProcessImpersonate;
        if ( !(_WORD)CanProcessImpersonate )
          v24 = 317;
      }
      else if ( (CanProcessImpersonate & 0x10000000) != 0 )
      {
        v24 = RtlNtStatusToDosError(CanProcessImpersonate & 0xEFFFFFFF);
        if ( v24 )
        {
          if ( v24 == 317 )
            v24 = CanProcessImpersonate;
        }
        else
        {
          v24 = CanProcessImpersonate;
        }
      }
      else
      {
        v24 = CanProcessImpersonate;
      }
    }
    else
    {
      v24 = 0;
    }
    WPP_SF_d(1036, 15, WPP_29d8921fdfbf3b8597c2d9971819ee4e_Traceguids, v24);
  }
  if ( (CanProcessImpersonate & 0x1FFF0000) == 0xC0000 )
  {
    v25 = (unsigned __int16)CanProcessImpersonate;
  }
  else if ( CanProcessImpersonate < 0 )
  {
    if ( (CanProcessImpersonate & 0x1FFF0000) == 0x70000 )
    {
      v25 = (unsigned __int16)CanProcessImpersonate;
      if ( !(_WORD)CanProcessImpersonate )
        v25 = 317;
    }
    else if ( (CanProcessImpersonate & 0x10000000) != 0 )
    {
      v36 = RtlNtStatusToDosError(CanProcessImpersonate & 0xEFFFFFFF);
      v25 = v36;
      if ( v36 )
      {
        if ( v36 == 317 )
          v25 = CanProcessImpersonate;
      }
      else
      {
        v25 = CanProcessImpersonate;
      }
    }
    else
    {
      v25 = CanProcessImpersonate;
    }
  }
  else
  {
    v25 = 0;
  }
  if ( v18 )
    CCacheClientEntry::Release(v18);
  return v25;
}

```

## disassembly

```asm
0x180099100  mov     [rsp-8+arg_8], rbx
0x180099105  push    rbp
0x180099106  push    rsi
0x180099107  push    rdi
0x180099108  push    r12
0x18009910a  push    r13
0x18009910c  push    r14
0x18009910e  push    r15
0x180099110  lea     rbp, [rsp-7]
0x180099115  sub     rsp, 100h
0x18009911c  mov     rax, cs:__security_cookie
0x180099123  xor     rax, rsp
0x180099126  mov     [rbp+37h+var_40], rax
0x18009912a  mov     rbx, [rbp+37h+arg_68]
0x180099131  xor     r15d, r15d
0x180099134  mov     r11, [rbp+37h+arg_30]
0x180099138  mov     r10, r9
0x18009913b  mov     rax, [rbp+37h+arg_38]
0x18009913f  mov     r13d, r8d
0x180099142  mov     r8, [rbp+37h+arg_40]
0x180099149  mov     rdi, rcx
0x18009914c  mov     rcx, [rbp+37h+arg_50]
0x180099153  mov     r14d, r15d
0x180099156  mov     rdx, [rbp+37h+arg_58]
0x18009915d  mov     r12, [rbp+37h+arg_60]
0x180099164  mov     [rbp+37h+var_60], rbx
0x180099168  mov     ebx, r15d
0x18009916b  mov     [rbp+37h+var_50], r9
0x18009916f  mov     r9, [rbp+37h+arg_48]
0x180099176  mov     [rbp+37h+var_88], rbx
0x18009917a  mov     [rbp+37h+var_58], r11
0x18009917e  mov     [rbp+37h+var_68], rax
0x180099182  mov     [rbp+37h+var_90], r8
0x180099186  mov     [rbp+37h+var_80], r9
0x18009918a  mov     [rbp+37h+var_70], rcx
0x18009918e  mov     [rbp+37h+var_78], rdx
0x180099192  mov     [rbp+37h+var_AC], r15d
0x180099196  mov     [rbp+37h+lpMem], r15
0x18009919a  mov     [rbp+37h+var_A0], r15
0x18009919e  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800991a5  jz      short loc_1800991E5
0x1800991a7  mov     [rsp+130h+var_C0], rdx
0x1800991ac  mov     [rsp+130h+var_C8], rcx
0x1800991b1  mov     [rsp+130h+var_D0], r9
0x1800991b6  mov     r9, rdi
0x1800991b9  mov     [rsp+130h+var_D8], r8
0x1800991be  mov     [rsp+130h+var_E0], rax
0x1800991c3  mov     eax, [rbp+37h+arg_28]
0x1800991c6  mov     [rsp+130h+var_E8], r11
0x1800991cb  mov     dword ptr [rsp+130h+var_F0], eax
0x1800991cf  mov     eax, [rbp+37h+arg_20]
0x1800991d2  mov     dword ptr [rsp+130h+var_F8], eax
0x1800991d6  mov     [rsp+130h+var_100], r10
0x1800991db  mov     dword ptr [rsp+130h+var_108], r13d
0x1800991e0  call    WPP_SF_sllqllSqqqqq
0x1800991e5  test    r12, r12
0x1800991e8  jz      short loc_1800991F2
0x1800991ea  mov     dword ptr [r12], 0Bh
0x1800991f2  test    rdi, rdi
0x1800991f5  jz      loc_180099651
0x1800991fb  test    r12, r12
0x1800991fe  jz      short loc_180099208
0x180099200  mov     dword ptr [r12], 0Ch
0x180099208  mov     [rbp+37h+var_AC], r15d
0x18009920c  test    byte ptr cs:xmmword_180266B60+1, 40h
0x180099213  jz      short loc_180099231
0x180099215  mov     edx, 11h
0x18009921a  lea     r8, WPP_1f863943467533a4b627fcbad4e97ae1_Traceguids
0x180099221  mov     ecx, 40Eh
0x180099226  mov     r9d, 2
0x18009922c  call    WPP_SF_d
0x180099231  mov     ecx, r15d
0x180099234  mov     [rbp+37h+var_AC], r15d
0x180099238  cmp     cs:?g_fCanProcessImpersonateCached@@3HA, ecx; int g_fCanProcessImpersonateCached
0x18009923e  mov     [rbp+37h+hObject], r15
0x180099242  mov     [rbp+37h+var_A8], r15d
0x180099246  mov     [rbp+37h+var_B0], ecx
0x180099249  jz      loc_1800995ED
0x18009924f  lock or [rsp+130h+var_130], ecx
0x180099253  mov     eax, cs:?g_fCanProcessImpersonate@@3HA; int g_fCanProcessImpersonate
0x180099259  test    eax, eax
0x18009925b  jnz     loc_18009948F
0x180099261  mov     esi, 1
0x180099266  mov     rcx, [rbp+37h+hObject]; hObject
0x18009926a  test    rcx, rcx
0x18009926d  jz      short loc_180099279
0x18009926f  call    cs:__imp_CloseHandle
0x180099275  mov     [rbp+37h+hObject], r15
0x180099279  test    esi, esi
0x18009927b  js      loc_180099403
0x180099281  cmp     esi, 1
0x180099284  jnz     loc_180099625
0x18009928a  mov     esi, r15d
0x18009928d  test    byte ptr cs:xmmword_180266B60+1, 40h
0x180099294  jz      short loc_1800992AF
0x180099296  mov     edx, 12h
0x18009929b  lea     r8, WPP_1f863943467533a4b627fcbad4e97ae1_Traceguids
0x1800992a2  mov     ecx, 40Eh
0x1800992a7  mov     r9d, esi
0x1800992aa  call    WPP_SF_d
0x1800992af  test    r15d, r15d
0x1800992b2  js      loc_18009966B
0x1800992b8  xor     ecx, ecx
0x1800992ba  test    r12, r12
0x1800992bd  jz      short loc_1800992C7
0x1800992bf  mov     dword ptr [r12], 5
0x1800992c7  mov     r15, [rbp+37h+var_68]
0x1800992cb  test    r15, r15
0x1800992ce  jz      short loc_1800992D3
0x1800992d0  mov     [r15], rcx
0x1800992d3  mov     rax, [rbp+37h+var_70]
0x1800992d7  test    rax, rax
0x1800992da  jz      short loc_1800992DF
0x1800992dc  mov     [rax], rcx
0x1800992df  mov     rax, [rbp+37h+var_78]
0x1800992e3  test    rax, rax
0x1800992e6  jz      short loc_1800992EA
0x1800992e8  mov     [rax], ecx
0x1800992ea  mov     rax, [rbp+37h+var_90]
0x1800992ee  test    rax, rax
0x1800992f1  jz      short loc_1800992F9
0x1800992f3  xorps   xmm0, xmm0
0x1800992f6  movups  xmmword ptr [rax], xmm0
0x1800992f9  mov     rax, [rbp+37h+var_80]
0x1800992fd  mov     [rax], rcx
0x180099300  test    r13d, r13d
0x180099303  jnz     loc_1800995C9
0x180099309  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180099310  inc     rdx; cbMultiByte
0x180099313  cmp     [rdi+rdx], cl
0x180099316  jnz     short loc_180099310
0x180099318  mov     [rsp+130h+var_110], rcx; unsigned int *
0x18009931d  lea     r9, [rbp+37h+lpMem]; unsigned __int16 **
0x180099321  mov     rcx, rdi; lpMultiByteStr
0x180099324  mov     r8d, 0FDE9h; CodePage
0x18009932a  call    ?ConvertCacheCharToWChar@@YAJPEBDKKPEAPEAGPEAK@Z; ConvertCacheCharToWChar(char const *,ulong,ulong,ushort * *,ulong *)
0x18009932f  mov     esi, eax
0x180099331  test    eax, eax
0x180099333  jns     loc_180099412
0x180099339  mov     r14, [rbp+37h+lpMem]
0x18009933d  mov     [rbp+37h+var_AC], 148h
0x180099344  xor     r15d, r15d
0x180099347  test    r14, r14
0x18009934a  jz      short loc_18009936B
0x18009934c  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x180099353  jnz     loc_180099511
0x180099359  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180099360  mov     r8, r14; lpMem
0x180099363  xor     edx, edx; dwFlags
0x180099365  call    cs:__imp_HeapFree
0x18009936b  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180099372  mov     r14d, 13Dh
0x180099378  jz      short loc_1800993B0
0x18009937a  mov     eax, esi
0x18009937c  and     eax, 1FFF0000h
0x180099381  cmp     eax, 0C0000h
0x180099386  jz      loc_1800995C1
0x18009938c  test    esi, esi
0x18009938e  js      loc_180099525
0x180099394  mov     eax, r15d
0x180099397  mov     edx, 0Fh
0x18009939c  lea     r8, WPP_29d8921fdfbf3b8597c2d9971819ee4e_Traceguids
0x1800993a3  mov     ecx, 40Ch
0x1800993a8  mov     r9d, eax
0x1800993ab  call    WPP_SF_d
0x1800993b0  mov     eax, esi
0x1800993b2  and     eax, 1FFF0000h
0x1800993b7  cmp     eax, 0C0000h
0x1800993bc  jz      loc_18009953E
0x1800993c2  test    esi, esi
0x1800993c4  js      loc_1800994F8
0x1800993ca  mov     edi, r15d
0x1800993cd  test    rbx, rbx
0x1800993d0  jz      short loc_1800993DA
0x1800993d2  mov     rcx, rbx; this
0x1800993d5  call    ?Release@CCacheClientEntry@@QEAAKXZ; CCacheClientEntry::Release(void)
0x1800993da  mov     eax, edi
0x1800993dc  mov     rcx, [rbp+37h+var_40]
0x1800993e0  xor     rcx, rsp; StackCookie
0x1800993e3  call    __security_check_cookie
0x1800993e8  mov     rbx, [rsp+130h+arg_8]
0x1800993f0  add     rsp, 100h
0x1800993f7  pop     r15
0x1800993f9  pop     r14
0x1800993fb  pop     r13
0x1800993fd  pop     r12
0x1800993ff  pop     rdi
0x180099400  pop     rsi
0x180099401  pop     rbp
0x180099402  retn
0x180099403  mov     [rbp+37h+var_AC], 0F8h
0x18009940a  mov     r15d, esi
0x18009940d  jmp     loc_18009928D
0x180099412  mov     rdx, [rbp+37h+var_50]; struct CAppCacheHandle *
0x180099416  lea     rcx, [rbp+37h+var_A0]
0x18009941a  xor     eax, eax
0x18009941c  mov     r8d, r14d; unsigned int
0x18009941f  mov     r14, [rbp+37h+lpMem]
0x180099423  test    r15, r15
0x180099426  cmovz   rcx, rax
0x18009942a  mov     rax, [rbp+37h+var_60]
0x18009942e  mov     [rsp+130h+var_E8], rax; unsigned __int64 *
0x180099433  xor     r9d, r9d; int
0x180099436  mov     [rsp+130h+var_F0], r12; unsigned int *
0x18009943b  lea     rax, [rbp+37h+var_88]
0x18009943f  mov     [rsp+130h+var_F8], rax; struct CCacheClientEntry **
0x180099444  mov     rax, [rbp+37h+var_90]
0x180099448  mov     [rsp+130h+var_100], rax; struct _APP_CACHE_RETRIEVE_STATE *
0x18009944d  mov     rax, [rbp+37h+var_58]
0x180099451  mov     [rsp+130h+var_108], rcx; void **
0x180099456  mov     rcx, r14; unsigned __int16 *
0x180099459  mov     [rsp+130h+var_110], rax; unsigned __int16 *
0x18009945e  call    ?RetrieveUrlCacheEntryStreamHelper@@YAJPEBGPEAVCAppCacheHandle@@KH0PEAPEAXPEAU_APP_CACHE_RETRIEVE_STATE@@PEAPEAVCCacheClientEntry@@PEAKPEA_K@Z; RetrieveUrlCacheEntryStreamHelper(ushort const *,CAppCacheHandle *,ulong,int,ushort const *,void * *,_APP_CACHE_RETRIEVE_STATE *,CCacheClientEntry * *,ulong *,unsigned __int64 *)
0x180099463  mov     rbx, [rbp+37h+var_88]
0x180099467  mov     esi, eax
0x180099469  test    eax, eax
0x18009946b  jns     loc_180099546
0x180099471  mov     rcx, [rbp+37h+var_A0]; void *
0x180099475  mov     [rbp+37h+var_AC], 15Bh
0x18009947c  test    rcx, rcx
0x18009947f  jz      loc_180099344
0x180099485  call    ?UnlockUrlCacheEntryStreamHelper@@YAJPEAX@Z; UnlockUrlCacheEntryStreamHelper(void *)
0x18009948a  jmp     loc_180099344
0x18009948f  test    ecx, ecx
0x180099491  jnz     loc_18009961D
0x180099497  call    cs:__imp_GetCurrentThread
0x18009949d  lea     r9, [rbp+37h+hObject]; TokenHandle
0x1800994a1  mov     edx, 20008h; DesiredAccess
0x1800994a6  mov     rcx, rax; ThreadHandle
0x1800994a9  mov     r8d, 1; OpenAsSelf
0x1800994af  call    cs:__imp_OpenThreadToken
0x1800994b5  test    eax, eax
0x1800994b7  jnz     loc_18009961D
0x1800994bd  call    cs:__imp_GetLastError
0x1800994c3  cmp     eax, 3F0h
0x1800994c8  jz      loc_180099261
0x1800994ce  call    WxGetLastError
0x1800994d3  mov     esi, eax
0x1800994d5  test    eax, eax
0x1800994d7  jle     short loc_1800994E2
0x1800994d9  movzx   esi, ax
0x1800994dc  or      esi, 80070000h
0x1800994e2  test    esi, esi
0x1800994e4  mov     [rbp+37h+var_AC], 392h
0x1800994eb  mov     eax, 8000FFFFh
0x1800994f0  cmovns  esi, eax
0x1800994f3  jmp     loc_180099266
0x1800994f8  cmp     eax, 70000h
0x1800994fd  jnz     loc_1800996CD
0x180099503  movzx   edi, si
0x180099506  test    edi, edi
0x180099508  cmovz   edi, r14d
0x18009950c  jmp     loc_1800993CD
0x180099511  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x180099518  mov     rcx, r14
0x18009951b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099520  jmp     loc_18009936B
0x180099525  cmp     eax, 70000h
0x18009952a  jnz     loc_180099699
0x180099530  movzx   eax, si
0x180099533  test    eax, eax
0x180099535  cmovz   eax, r14d
0x180099539  jmp     loc_180099397
0x18009953e  movzx   edi, si
0x180099541  jmp     loc_1800993CD
0x180099546  mov     rdx, [rbp+37h+var_80]; struct _INTERNAL_CACHE_ENTRY_INFOEX **
0x18009954a  lea     rcx, [rbx+8]; struct _URLCACHE_ENTRY *
0x18009954e  call    ?ConvertInternalCacheEntryInfo@@YAJPEBU_URLCACHE_ENTRY@@PEAPEAU_INTERNAL_CACHE_ENTRY_INFOEX@@@Z; ConvertInternalCacheEntryInfo(_URLCACHE_ENTRY const *,_INTERNAL_CACHE_ENTRY_INFOEX * *)
0x180099553  mov     esi, eax
0x180099555  test    eax, eax
0x180099557  js      loc_180099677
0x18009955d  test    r15, r15
0x180099560  jz      loc_180099662
0x180099566  mov     rax, [rbp+37h+var_A0]
0x18009956a  xor     ecx, ecx
0x18009956c  mov     [r15], rax
0x18009956f  cmp     qword ptr [rbx+98h], 0
0x180099577  jz      loc_18009947C
0x18009957d  mov     eax, [rbx+50h]
0x180099580  test    eax, eax
0x180099582  jz      loc_18009947C
0x180099588  mov     rdx, [rbp+37h+var_78]
0x18009958c  test    rdx, rdx
0x18009958f  jz      short loc_180099593
0x180099591  mov     [rdx], eax
0x180099593  mov     rdx, [rbp+37h+var_70]
0x180099597  test    rdx, rdx
0x18009959a  jz      loc_18009947C
0x1800995a0  mov     rax, [rbx+98h]
0x1800995a7  mov     [rdx], rax
0x1800995aa  mov     qword ptr [rbx+98h], 0
0x1800995b5  mov     dword ptr [rbx+50h], 0
0x1800995bc  jmp     loc_18009947C
0x1800995c1  movzx   eax, si
0x1800995c4  jmp     loc_180099397
0x1800995c9  cmp     [rbp+37h+arg_28], ecx
0x1800995cc  mov     eax, 10h
0x1800995d1  mov     r14d, 14h
0x1800995d7  cmovnz  r14d, eax
0x1800995db  mov     eax, r14d
  ... truncated ...
```
