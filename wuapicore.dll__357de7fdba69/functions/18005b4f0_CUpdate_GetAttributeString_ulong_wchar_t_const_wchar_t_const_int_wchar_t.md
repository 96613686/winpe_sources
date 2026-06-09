# CUpdate::GetAttributeString(ulong,wchar_t const *,wchar_t const *,int,wchar_t * *)

- ea: `0x18005b4f0`
- end: `0x18005b868`
- name: `?GetAttributeString@CUpdate@@UEAAJKPEB_W0HPEAPEA_W@Z`
- size: `888`
- prototype: `__int64 __fastcall(CUpdate *__hidden this, unsigned int, const wchar_t *, const wchar_t *, int, wchar_t **)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x180039e50`
- `0x1800467e8`
- `0x18005b4f0`
- `0x18005ddf8`
- `0x18005e5f4`
- `0x180081a38`
- `0x1800826a0`
- `0x180082720`
- `0x180090bc8`
- `0x180096bb0`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b81b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b81b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005b578`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005b578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b60b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b82a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b60b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b82a`

## string_xrefs

- `0x18005b54e`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18005b75c`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18005b7c0`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18005b6fa`: `* END *   GetAttributeString   returning cached Attribute value = [%ws]`

## pseudocode

```c
__int64 __fastcall CUpdate::GetAttributeString(
        CUpdate *this,
        unsigned int a2,
        const wchar_t *a3,
        const wchar_t *a4,
        int a5,
        wchar_t **a6)
{
  void *v6; // rbx
  __int64 v9; // rdx
  int v10; // r14d
  char *v11; // rsi
  int v12; // eax
  __int64 v13; // rdx
  int v14; // r14d
  int IndexOf; // eax
  unsigned int v16; // ecx
  __int128 v17; // xmm0
  int AttributeString; // eax
  unsigned int v19; // eax
  const wchar_t *v20; // rdi
  __int64 v21; // r9
  int v22; // eax
  void *v23; // rdi
  __int64 v24; // rdx
  int v26; // [rsp+20h] [rbp-69h]
  int v27; // [rsp+20h] [rbp-69h]
  void *lpMem; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v29; // [rsp+48h] [rbp-41h]
  int v30[4]; // [rsp+50h] [rbp-39h] BYREF
  __int128 v31; // [rsp+60h] [rbp-29h] BYREF
  int v32; // [rsp+70h] [rbp-19h]
  LPVOID pv; // [rsp+80h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+4Fh]

  *(_QWORD *)v30 = a3;
  v6 = 0;
  lpMem = 0;
  v29 = a2;
  pv = 0;
  if ( !a4 )
  {
    v9 = 4988;
LABEL_5:
    v10 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)0x80004003LL,
      v26);
    goto LABEL_44;
  }
  if ( !a6 )
  {
    v9 = 4989;
    goto LABEL_5;
  }
  v11 = (char *)this + 1056;
  if ( this != (CUpdate *)-1056LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1064));
  WUTrace(0, 0, 0x10000, 4, 0, L"* START *   GetAttributeString   Attribute name = %ws", a4);
  v12 = DuplicateString<wchar_t const *,wchar_t *>(a4, &lpMem);
  v6 = lpMem;
  v10 = v12;
  if ( v12 < 0 )
  {
    v13 = 4999;
LABEL_26:
    v21 = (unsigned int)v10;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)v21,
      v27);
    goto LABEL_42;
  }
  v14 = 0;
  if ( *((_DWORD *)this + 289) )
  {
    while ( 1 )
    {
      lpMem = v6;
      IndexOf = CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::GetIndexOf(
                  (char *)this + 1136,
                  &lpMem);
      v16 = *((_DWORD *)this + 289);
      if ( IndexOf != v16 )
        break;
      if ( ++v14 >= v16 )
        goto LABEL_13;
    }
    lpMem = v6;
    v19 = CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::GetIndexOf(
            (char *)this + 1136,
            &lpMem);
    if ( !a5 )
    {
      if ( v19 < *((_DWORD *)this + 289) )
      {
        v20 = *(const wchar_t **)(*((_QWORD *)this + 143) + 16LL * v19);
        v10 = SusSysAllocString(v20, a6);
        if ( v10 >= 0 )
        {
          WUTrace(0, 0, 0x10000, 4, 0, L"* END *   GetAttributeString   returning cached Attribute value = [%ws]", v20);
          v10 = 0;
          goto LABEL_42;
        }
        v13 = 5018;
      }
      else
      {
        v10 = -2145124345;
        v13 = 5016;
      }
      goto LABEL_26;
    }
    if ( v19 < *((_DWORD *)this + 289) )
      CSusArrayList<CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::_tagMapEntry,CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::CMapEntryOps>::RemoveArraySection(
        (char *)this + 1136,
        v19,
        v19,
        1);
  }
LABEL_13:
  if ( pv )
    CoTaskMemFree(pv);
  v17 = *(_OWORD *)((char *)this + 648);
  v32 = *((_DWORD *)this + 166);
  v31 = v17;
  v27 = v30[0];
  AttributeString = CSusInternalWrapper::GetAttributeString((char *)this + 32, (char *)this + 896, &v31, v29);
  v10 = AttributeString;
  if ( AttributeString >= 0 )
  {
    if ( !pv )
    {
      v10 = -2145120257;
      v13 = 5038;
      v21 = 2149847039LL;
      goto LABEL_33;
    }
    AttributeString = SusSysAllocString((const wchar_t *)pv, a6);
    v10 = AttributeString;
    if ( AttributeString < 0 )
    {
      v13 = 5041;
      goto LABEL_32;
    }
    lpMem = 0;
    v22 = DuplicateString<wchar_t *,wchar_t *>(pv, &lpMem);
    v23 = lpMem;
    v10 = v22;
    if ( v22 >= 0 )
    {
      *(_QWORD *)v30 = lpMem;
      lpMem = v6;
      v10 = CSusMap<wchar_t *,__int64,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsBasic<__int64>>::Add(
              (char *)this + 1136,
              &lpMem,
              v30);
      if ( v10 >= 0 )
      {
        v6 = 0;
        v23 = 0;
        WUTrace(0, 0, 0x10000, 4, 0, L"* END *   GetAttributeString   Attribute value = [%ws]", pv);
        v10 = 0;
LABEL_40:
        if ( v23 )
          SusFree(v23);
        goto LABEL_42;
      }
      v24 = 5046;
    }
    else
    {
      v24 = 5044;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)(unsigned int)v10,
      v27);
    goto LABEL_40;
  }
  if ( AttributeString != -2147467263 && AttributeString != -2145099769 )
  {
    v13 = 5036;
LABEL_32:
    v21 = (unsigned int)AttributeString;
    goto LABEL_33;
  }
LABEL_42:
  if ( v11 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 8));
LABEL_44:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v6 )
    SusFree(v6);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18005b4f0  push    rbp
0x18005b4f2  push    rbx
0x18005b4f3  push    rsi
0x18005b4f4  push    rdi
0x18005b4f5  push    r12
0x18005b4f7  push    r13
0x18005b4f9  push    r14
0x18005b4fb  push    r15
0x18005b4fd  lea     rbp, [rsp-0Fh]
0x18005b502  sub     rsp, 98h
0x18005b509  mov     rax, cs:__security_cookie
0x18005b510  xor     rax, rsp
0x18005b513  mov     [rbp+47h+var_48], rax
0x18005b517  mov     r12, [rbp+47h+arg_28]
0x18005b51b  xor     edi, edi
0x18005b51d  mov     qword ptr [rbp+47h+var_80], r8
0x18005b521  mov     ebx, edi
0x18005b523  mov     [rbp+47h+lpMem], rbx
0x18005b527  mov     r13, r9
0x18005b52a  mov     [rbp+47h+var_88], edx
0x18005b52d  mov     r15, rcx
0x18005b530  mov     [rbp+47h+pv], rdi
0x18005b534  test    r9, r9
0x18005b537  jnz     short loc_18005B540
0x18005b539  mov     edx, 137Ch
0x18005b53e  jmp     short loc_18005B54A
0x18005b540  test    r12, r12
0x18005b543  jnz     short loc_18005B568
0x18005b545  mov     edx, 137Dh; void *
0x18005b54a  mov     rcx, [rbp+4Fh]; this
0x18005b54e  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18005b555  mov     r14d, 80004003h
0x18005b55b  mov     r9d, r14d; char *
0x18005b55e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b563  jmp     loc_18005B821
0x18005b568  lea     rsi, [rcx+420h]
0x18005b56f  test    rsi, rsi
0x18005b572  jz      short loc_18005B57E
0x18005b574  lea     rcx, [rsi+8]; lpCriticalSection
0x18005b578  call    cs:__imp_EnterCriticalSection
0x18005b57e  xor     edx, edx
0x18005b580  mov     [rsp+0D0h+var_A0], r13
0x18005b585  lea     rax, aStartGetattrib; "* START *   GetAttributeString   Attrib"...
0x18005b58c  xor     ecx, ecx
0x18005b58e  mov     [rsp+0D0h+var_A8], rax
0x18005b593  mov     r8d, 10000h
0x18005b599  mov     qword ptr [rsp+0D0h+var_B0], rdi
0x18005b59e  lea     r9d, [rdx+4]
0x18005b5a2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18005b5a7  lea     rdx, [rbp+47h+lpMem]
0x18005b5ab  mov     rcx, r13
0x18005b5ae  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18005b5b3  mov     rbx, [rbp+47h+lpMem]
0x18005b5b7  mov     r14d, eax
0x18005b5ba  test    eax, eax
0x18005b5bc  jns     short loc_18005B5C8
0x18005b5be  mov     edx, 1387h
0x18005b5c3  jmp     loc_18005B6EE
0x18005b5c8  mov     r14d, edi
0x18005b5cb  cmp     [r15+484h], edi
0x18005b5d2  jbe     short loc_18005B602
0x18005b5d4  lea     rdi, [r15+470h]
0x18005b5db  lea     rdx, [rbp+47h+lpMem]
0x18005b5df  mov     [rbp+47h+lpMem], rbx
0x18005b5e3  mov     rcx, rdi
0x18005b5e6  call    ?GetIndexOf@?$CSusMap@PEA_WPEA_WVCSusSortedArrayListItemOpsLPWSTR@@V1@@@QEBAKAEBQEA_W@Z; CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::GetIndexOf(wchar_t * const &)
0x18005b5eb  mov     ecx, [r15+484h]
0x18005b5f2  cmp     eax, ecx
0x18005b5f4  jnz     loc_18005B681
0x18005b5fa  inc     r14d
0x18005b5fd  cmp     r14d, ecx
0x18005b600  jb      short loc_18005B5DB
0x18005b602  mov     rcx, [rbp+47h+pv]; pv
0x18005b606  test    rcx, rcx
0x18005b609  jz      short loc_18005B611
0x18005b60b  call    cs:__imp_CoTaskMemFree
0x18005b611  mov     eax, [r15+298h]
0x18005b618  lea     rdx, [r15+380h]
0x18005b61f  movups  xmm0, xmmword ptr [r15+288h]
0x18005b627  mov     r9d, [rbp+47h+var_88]
0x18005b62b  lea     r8, [rbp+47h+var_70]
0x18005b62f  mov     [rbp+47h+var_60], eax
0x18005b632  lea     rcx, [r15+20h]
0x18005b636  lea     rax, [rbp+47h+pv]
0x18005b63a  movaps  [rbp+47h+var_70], xmm0
0x18005b63e  mov     [rsp+0D0h+var_A0], rax
0x18005b643  mov     rax, qword ptr [rbp+47h+var_80]
0x18005b647  mov     [rsp+0D0h+var_A8], r13
0x18005b64c  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18005b651  call    ?GetAttributeString@CSusInternalWrapper@@QEAAJAEBU_GUID@@UtagDSGlobalUpdateId@@KPEB_W2PEAPEA_W@Z; CSusInternalWrapper::GetAttributeString(_GUID const &,tagDSGlobalUpdateId,ulong,wchar_t const *,wchar_t const *,wchar_t * *)
0x18005b656  mov     r14d, eax
0x18005b659  test    eax, eax
0x18005b65b  jns     loc_18005B728
0x18005b661  cmp     eax, 80004001h
0x18005b666  jz      loc_18005B812
0x18005b66c  cmp     eax, 80246007h
0x18005b671  jz      loc_18005B812
0x18005b677  mov     edx, 13ACh
0x18005b67c  jmp     loc_18005B755
0x18005b681  lea     rdx, [rbp+47h+lpMem]
0x18005b685  mov     [rbp+47h+lpMem], rbx
0x18005b689  mov     rcx, rdi
0x18005b68c  call    ?GetIndexOf@?$CSusMap@PEA_WPEA_WVCSusSortedArrayListItemOpsLPWSTR@@V1@@@QEBAKAEBQEA_W@Z; CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::GetIndexOf(wchar_t * const &)
0x18005b691  cmp     [rbp+47h+arg_20], 0
0x18005b695  jz      short loc_18005B6B8
0x18005b697  cmp     eax, [rdi+14h]
0x18005b69a  jnb     loc_18005B602
0x18005b6a0  mov     r9d, 1
0x18005b6a6  mov     r8d, eax
0x18005b6a9  mov     edx, eax
0x18005b6ab  mov     rcx, rdi
0x18005b6ae  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEA_WVCSusSortedArrayListItemOpsLPWSTR@@V1@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::_tagMapEntry,CSusMap<wchar_t *,wchar_t *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsLPWSTR>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x18005b6b3  jmp     loc_18005B602
0x18005b6b8  cmp     eax, [rdi+14h]
0x18005b6bb  jb      short loc_18005B6CA
0x18005b6bd  mov     r14d, 80240007h
0x18005b6c3  mov     edx, 1398h
0x18005b6c8  jmp     short loc_18005B6EE
0x18005b6ca  mov     ecx, eax
0x18005b6cc  mov     rdx, r12; wchar_t **
0x18005b6cf  mov     rax, [rdi+8]
0x18005b6d3  add     rcx, rcx
0x18005b6d6  mov     rdi, [rax+rcx*8]
0x18005b6da  mov     rcx, rdi; wchar_t *
0x18005b6dd  call    ?SusSysAllocString@@YAJPEB_WPEAPEA_W@Z; SusSysAllocString(wchar_t const *,wchar_t * *)
0x18005b6e2  mov     r14d, eax
0x18005b6e5  test    eax, eax
0x18005b6e7  jns     short loc_18005B6F3
0x18005b6e9  mov     edx, 139Ah
0x18005b6ee  mov     r9d, r14d
0x18005b6f1  jmp     short loc_18005B758
0x18005b6f3  xor     edx, edx
0x18005b6f5  mov     [rsp+0D0h+var_A0], rdi
0x18005b6fa  lea     rax, aEndGetattribut_1; "* END *   GetAttributeString   returnin"...
0x18005b701  xor     ecx, ecx
0x18005b703  mov     [rsp+0D0h+var_A8], rax
0x18005b708  mov     r8d, 10000h
0x18005b70e  mov     qword ptr [rsp+0D0h+var_B0], 0
0x18005b717  lea     r9d, [rdx+4]
0x18005b71b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18005b720  xor     r14d, r14d
0x18005b723  jmp     loc_18005B812
0x18005b728  mov     rcx, [rbp+47h+pv]; wchar_t *
0x18005b72c  test    rcx, rcx
0x18005b72f  jnz     short loc_18005B741
0x18005b731  mov     r14d, 80240FFFh
0x18005b737  mov     edx, 13AEh
0x18005b73c  mov     r9d, r14d
0x18005b73f  jmp     short loc_18005B758
0x18005b741  mov     rdx, r12; wchar_t **
0x18005b744  call    ?SusSysAllocString@@YAJPEB_WPEAPEA_W@Z; SusSysAllocString(wchar_t const *,wchar_t * *)
0x18005b749  mov     r14d, eax
0x18005b74c  test    eax, eax
0x18005b74e  jns     short loc_18005B76D
0x18005b750  mov     edx, 13B1h; void *
0x18005b755  mov     r9d, eax; char *
0x18005b758  mov     rcx, [rbp+4Fh]; this
0x18005b75c  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18005b763  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b768  jmp     loc_18005B812
0x18005b76d  mov     rcx, [rbp+47h+pv]
0x18005b771  lea     rdx, [rbp+47h+lpMem]
0x18005b775  mov     [rbp+47h+lpMem], 0
0x18005b77d  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18005b782  mov     rdi, [rbp+47h+lpMem]
0x18005b786  mov     r14d, eax
0x18005b789  test    eax, eax
0x18005b78b  jns     short loc_18005B794
0x18005b78d  mov     edx, 13B4h
0x18005b792  jmp     short loc_18005B7BC
0x18005b794  lea     rcx, [r15+470h]
0x18005b79b  mov     qword ptr [rbp+47h+var_80], rdi
0x18005b79f  lea     r8, [rbp+47h+var_80]
0x18005b7a3  mov     [rbp+47h+lpMem], rbx
0x18005b7a7  lea     rdx, [rbp+47h+lpMem]
0x18005b7ab  call    ?Add@?$CSusMap@PEA_W_JVCSusSortedArrayListItemOpsLPWSTR@@V?$CSusSortedArrayListItemOpsBasic@_J@@@@QEAAJAEBQEA_WAEB_J@Z; CSusMap<wchar_t *,__int64,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsBasic<__int64>>::Add(wchar_t * const &,__int64 const &)
0x18005b7b0  mov     r14d, eax
0x18005b7b3  test    eax, eax
0x18005b7b5  jns     short loc_18005B7D1
0x18005b7b7  mov     edx, 13B6h; void *
0x18005b7bc  mov     rcx, [rbp+4Fh]; this
0x18005b7c0  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18005b7c7  mov     r9d, r14d; char *
0x18005b7ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b7cf  jmp     short loc_18005B805
0x18005b7d1  mov     rax, [rbp+47h+pv]
0x18005b7d5  xor     ebx, ebx
0x18005b7d7  mov     [rsp+0D0h+var_A0], rax
0x18005b7dc  xor     edx, edx
0x18005b7de  lea     rax, aEndGetattribut_0; "* END *   GetAttributeString   Attribut"...
0x18005b7e5  xor     ecx, ecx
0x18005b7e7  mov     [rsp+0D0h+var_A8], rax
0x18005b7ec  mov     r8d, 10000h
0x18005b7f2  lea     r9d, [rbx+4]
0x18005b7f6  mov     qword ptr [rsp+0D0h+var_B0], rbx
0x18005b7fb  xor     edi, edi
0x18005b7fd  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18005b802  xor     r14d, r14d
0x18005b805  test    rdi, rdi
0x18005b808  jz      short loc_18005B812
0x18005b80a  mov     rcx, rdi; lpMem
0x18005b80d  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005b812  test    rsi, rsi
0x18005b815  jz      short loc_18005B821
0x18005b817  lea     rcx, [rsi+8]; lpCriticalSection
0x18005b81b  call    cs:__imp_LeaveCriticalSection
0x18005b821  mov     rcx, [rbp+47h+pv]; pv
0x18005b825  test    rcx, rcx
0x18005b828  jz      short loc_18005B838
0x18005b82a  call    cs:__imp_CoTaskMemFree
0x18005b830  mov     [rbp+47h+pv], 0
0x18005b838  test    rbx, rbx
0x18005b83b  jz      short loc_18005B845
0x18005b83d  mov     rcx, rbx; lpMem
0x18005b840  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005b845  mov     eax, r14d
0x18005b848  mov     rcx, [rbp+47h+var_48]
0x18005b84c  xor     rcx, rsp; StackCookie
0x18005b84f  call    __security_check_cookie
0x18005b854  add     rsp, 98h
0x18005b85b  pop     r15
0x18005b85d  pop     r14
0x18005b85f  pop     r13
0x18005b861  pop     r12
0x18005b863  pop     rdi
0x18005b864  pop     rsi
0x18005b865  pop     rbx
0x18005b866  pop     rbp
0x18005b867  retn
```
