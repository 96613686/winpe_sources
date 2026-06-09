# CRequestClient::CRequestClient(wchar_t const *,IDBProperties *,ulong)

- ea: `0x180072edc`
- end: `0x180073527`
- name: `??0CRequestClient@@QEAA@PEB_WPEAUIDBProperties@@K@Z`
- size: `1611`
- prototype: `CRequestClient *(CRequestClient *__hidden this, const wchar_t *, struct IDBProperties *, unsigned int)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180069aec`
- `0x1801af06c`

## callees

- `0x180038f08`
- `0x180072768`
- `0x180072edc`
- `0x180073530`
- `0x180073578`
- `0x1800735a4`
- `0x180073604`
- `0x1800736f8`
- `0x180073748`
- `0x1800737b8`
- `0x180073820`
- `0x180073ca8`
- `0x180073ddc`
- `0x180073e10`
- `0x180073e68`
- `0x180074180`
- `0x180147154`
- `0x180188d90`
- `0x180189280`
- `0x1801895a0`
- `0x1801895b0`
- `0x180189cce`
- `0x18018e8cb`
- `0x1801b9afc`
- `0x1801b9c34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180072fcf`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180072fcf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180072f6a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180072f87`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180072f6a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180072f87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800734c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800734c2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180073045`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180073045`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180072fb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180072fb3`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180072ffa`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180072ffa`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180073079`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180073079`
- `SspiCli!GetUserNameExW` at `0x18007309d`
- `SspiCli!GetUserNameExW` at `0x18007309d`

## string_xrefs

- `0x180073147`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x1800733ce`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x18007342d`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x18007345d`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x1800734b0`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x1802ba42a`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
CRequestClient *__fastcall CRequestClient::CRequestClient(
        CRequestClient *this,
        wchar_t *a2,
        struct IDBProperties *a3,
        int a4)
{
  int v8; // r15d
  const wchar_t *v9; // r9
  wchar_t *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  wchar_t *v14; // r14
  __int64 v15; // rbx
  const wchar_t *v16; // r14
  const wchar_t *v17; // rcx
  wchar_t *v18; // r12
  LSTATUS ValueW; // eax
  struct CDbProperties *v20; // r12
  const char *v21; // r9
  struct CSearchRegistryRedirectHelper *v22; // rax
  struct IUnknown *v23; // rdx
  unsigned int v24; // r14d
  unsigned int v25; // r8d
  int v26; // ebx
  __int64 v27; // r13
  __int64 v28; // rcx
  __int64 v29; // rax
  unsigned int v30; // esi
  _QWORD *v31; // r14
  int v32; // ecx
  __int64 v33; // rbx
  __int64 v34; // r8
  __int64 v35; // r8
  unsigned __int8 *BlobStartAddr; // rax
  unsigned __int8 *v37; // r8
  int v38; // ecx
  int v39; // eax
  int v40; // edx
  __int64 v42; // rax
  wchar_t *v43; // rcx
  wchar_t v44; // dx
  __int64 v45; // rcx
  const char *v46; // r9
  unsigned __int64 v47; // r12
  struct _SECURITY_ATTRIBUTES *pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  LPDWORD pdwTypeb; // [rsp+20h] [rbp-E0h]
  ULONG v51; // [rsp+40h] [rbp-C0h] BYREF
  int v52; // [rsp+44h] [rbp-BCh]
  struct CSearchRegistryRedirectHelper *v53; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD nSize; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v56; // [rsp+58h] [rbp-A8h] BYREF
  void **v57; // [rsp+60h] [rbp-A0h] BYREF
  int v58; // [rsp+68h] [rbp-98h]
  void **v59; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v60; // [rsp+78h] [rbp-88h]
  _BYTE v61[16]; // [rsp+80h] [rbp-80h] BYREF
  int v62; // [rsp+90h] [rbp-70h]
  __int64 v63; // [rsp+98h] [rbp-68h]
  __int64 v64; // [rsp+A0h] [rbp-60h]
  CDbProperties *v65; // [rsp+A8h] [rbp-58h]
  void **v66; // [rsp+B8h] [rbp-48h] BYREF
  int v67; // [rsp+C0h] [rbp-40h]
  void *Block; // [rsp+C8h] [rbp-38h]
  unsigned __int8 *v69; // [rsp+D0h] [rbp-30h]
  unsigned __int8 *v70; // [rsp+D8h] [rbp-28h]
  void **v71; // [rsp+E0h] [rbp-20h] BYREF
  int v72; // [rsp+E8h] [rbp-18h]
  void *v73; // [rsp+F0h] [rbp-10h]
  unsigned __int8 *v74; // [rsp+F8h] [rbp-8h]
  unsigned __int8 *v75; // [rsp+100h] [rbp+0h]
  struct _GUID v76; // [rsp+108h] [rbp+8h] BYREF
  CRequestClient *v77; // [rsp+118h] [rbp+18h]
  struct CDbProperties *v78; // [rsp+120h] [rbp+20h]
  _QWORD *v79; // [rsp+128h] [rbp+28h]
  unsigned int v80; // [rsp+130h] [rbp+30h]
  WCHAR Buffer[20]; // [rsp+138h] [rbp+38h] BYREF
  WCHAR NameBuffer[264]; // [rsp+160h] [rbp+60h] BYREF
  wchar_t pvData[264]; // [rsp+370h] [rbp+270h] BYREF
  wchar_t v84[264]; // [rsp+580h] [rbp+480h] BYREF
  wchar_t v85[264]; // [rsp+790h] [rbp+690h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+9E8h] [rbp+8E8h]

  v65 = (CDbProperties *)a3;
  v77 = this;
  CPipeClient::CPipeClient(this);
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 32) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_DWORD *)this + 36) = 0;
  CAutoEventSem::CAutoEventSem((CRequestClient *)((char *)this + 168));
  CAutoEventSem::CAutoEventSem((CRequestClient *)((char *)this + 176));
  *((_DWORD *)this + 56) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  v8 = 1;
  *((_DWORD *)this + 56) = 1;
  *((_DWORD *)this + 68) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  *((_DWORD *)this + 68) = 1;
  *((_DWORD *)this + 70) = 0;
  *((_QWORD *)this + 36) = 0;
  CEventSem::InternalCreate((CRequestClient *)((char *)this + 288), 1u, 1u, v9, pdwType);
  if ( a4 )
    *((_QWORD *)this + 13) = (unsigned int)(1000 * a4) + GetTickCount64();
  v10 = wcschr(a2, 0x3Au);
  v14 = v10;
  v15 = 260;
  if ( v10 )
  {
    v45 = v10 - a2;
    if ( (unsigned int)v45 >= 0x104 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2ED,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
        (const char *)0x80070057LL,
        pdwTypea);
    v47 = (unsigned int)v45;
    memcpy_0(v84, a2, v47 * 2);
    if ( v47 >= 261 )
      _report_rangecheckfailure();
    v84[v47] = 0;
    a2 = v84;
    v16 = v14 + 1;
  }
  else
  {
    v16 = L"MsFteWds";
  }
  pcbData = 520;
  v53 = 0;
  v18 = (wchar_t *)L"SOFTWARE\\Microsoft\\Windows Search";
  if ( (unsigned __int8)RtlIsStateSeparationEnabled(v12, v11, v13)
    && GetSearchRegistryRedirect(v17, &v53)
    && (int)CSearchRegistryRedirectHelper::MapRegistryKeyPath(
              (const wchar_t *)v53,
              L"SOFTWARE\\Microsoft\\Windows Search",
              v85) >= 0 )
  {
    v18 = v85;
  }
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v18, L"ClientPipeName", 2u, 0, pvData, &pcbData);
  v20 = 0;
  if ( ValueW )
  {
    v42 = 2147483646;
    v43 = pvData;
    while ( v42 )
    {
      v44 = *v16;
      if ( *v16 )
      {
        ++v16;
        *v43++ = v44;
        --v42;
        if ( --v15 )
          continue;
      }
      if ( !v15 )
      {
        *(v43 - 1) = 0;
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x300,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
          (const char *)0x80070057LL,
          (int)pdwTypeb);
      }
      break;
    }
    *v43 = 0;
  }
  CPipeClient::Init(this, a2, pvData);
  nSize = 16;
  if ( !GetComputerNameW(Buffer, &nSize) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x30C,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
      v21);
  v51 = 257;
  if ( !GetUserNameExW((EXTENDED_NAME_FORMAT)65538, NameBuffer, &v51) )
  {
    if ( GetLastError() != 5 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x31F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
        v46);
    NameBuffer[0] = 0;
    v51 = 0;
  }
  v22 = (struct CSearchRegistryRedirectHelper *)CDbProperties::operator new();
  v53 = v22;
  if ( v22 )
    v20 = CDbProperties::CDbProperties(v22, v23);
  v78 = v20;
  if ( !v20 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
      (const char *)0x8007000ELL,
      (int)pdwTypeb);
  TranslateNewPropsToOldProps(v20, (struct CDbProperties *)a3);
  v59 = &CSizeSerStream::`vftable';
  LODWORD(v60) = 0;
  CDbProperties::Marshall(v20, (struct PSerStream *)&v59);
  v24 = (unsigned int)v60;
  v52 = (int)v60;
  v57 = &CSizeSerStream::`vftable';
  v58 = 0;
  v76 = DBPROPSET_ROWSET;
  CDbProperties::Marshall((CDbProperties *)a3, (struct PSerStream *)&v57, v25, &v76);
  v26 = v58;
  LODWORD(v53) = v58;
  LODWORD(pdwTypeb) = v58;
  SearchIndexerDebug::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
    (const wchar_t *)0x342,
    (unsigned int)L"[Proxy] cb old props %d, cb new props: %d\n",
    (const wchar_t *)v24,
    pdwTypeb);
  v27 = -1;
  v28 = -1;
  do
    ++v28;
  while ( Buffer[v28] );
  v29 = -1;
  do
    ++v29;
  while ( NameBuffer[v29] );
  v30 = 2 * (v28 + v29) + 52;
  if ( v24 )
    v30 = ((v24 + 7) & 0xFFFFFFF8) + ((2 * (v28 + v29) + 59) & 0xFFFFFFF8);
  if ( v26 )
    v30 = ((v26 + 7) & 0xFFFFFFF8) + ((v30 + 7) & 0xFFFFFFF8);
  v80 = v30;
  v31 = operator new[](v30);
  v79 = v31;
  memset_0(v31, 0, v30);
  v32 = *((_DWORD *)this + 4);
  *v31 = 200;
  v31[1] = 0;
  *((_DWORD *)v31 + 4) = 67840;
  *((_DWORD *)v31 + 5) = v32;
  *((_DWORD *)v31 + 6) = v52;
  v33 = (unsigned int)v53;
  *((_DWORD *)v31 + 8) = (_DWORD)v53;
  v34 = -1;
  do
    ++v34;
  while ( Buffer[v34] );
  memcpy_0(v31 + 6, Buffer, 2 * v34 + 2);
  v35 = -1;
  do
    ++v35;
  while ( NameBuffer[v35] );
  do
    ++v27;
  while ( *((_WORD *)v31 + v27 + 24) );
  memcpy_0((char *)v31 + 2 * v27 + 50, NameBuffer, 2 * v35 + 2);
  BlobStartAddr = CPMConnectIn::GetBlobStartAddr((CPMConnectIn *)v31);
  v71 = &CMemSerStream::`vftable';
  v72 = 0;
  v73 = BlobStartAddr;
  v74 = BlobStartAddr;
  v75 = &BlobStartAddr[v52];
  CDbProperties::Marshall(v20, (struct PSerStream *)&v71);
  v37 = &CPMConnectIn::GetBlobStartAddr((CPMConnectIn *)v31)[(*((unsigned int *)v31 + 6) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL];
  v66 = &CMemSerStream::`vftable';
  v67 = 0;
  Block = v37;
  v69 = v37;
  v70 = &v37[v33];
  CDbProperties::Marshall(v65, (struct PSerStream *)&v66, (unsigned int)v37, &v76);
  *((_DWORD *)v31 + 2) = CProxyMessage::ComputeCheckSum((CProxyMessage *)v31, v30);
  v56 = 0;
  CRequestClient::DataWriteRead(this, (int *)v31, v30, v61, 0x28u, &v56);
  *((_DWORD *)this + 37) = v62;
  if ( v31[3] == v63 && v31[4] == v64 )
  {
    v40 = 5;
    v63 = 0x100000005LL;
    v39 = 0;
    v64 = 0;
    v38 = 0;
  }
  else
  {
    v38 = HIDWORD(v64);
    v39 = v64;
    v8 = HIDWORD(v63);
    v40 = v63;
  }
  *((_DWORD *)this + 38) = v40;
  *((_DWORD *)this + 39) = v8;
  *((_DWORD *)this + 40) = v39;
  *((_DWORD *)this + 41) = v38;
  v66 = &CMemSerStream::`vftable';
  if ( v67 )
    operator delete(Block);
  v66 = &PSerStream::`vftable';
  v71 = &CMemSerStream::`vftable';
  if ( v72 )
    operator delete(v73);
  v71 = &PSerStream::`vftable';
  operator delete(v31);
  v57 = &PSerStream::`vftable';
  v59 = &PSerStream::`vftable';
  CDbProperties::Release(v20);
  return this;
}

```

## disassembly

```asm
0x180072edc  mov     [rsp-8+arg_18], rbx
0x180072ee1  push    rbp
0x180072ee2  push    rsi
0x180072ee3  push    rdi
0x180072ee4  push    r12
0x180072ee6  push    r13
0x180072ee8  push    r14
0x180072eea  push    r15
0x180072eec  lea     rbp, [rsp-8B0h]
0x180072ef4  sub     rsp, 9B0h
0x180072efb  mov     rax, cs:__security_cookie
0x180072f02  xor     rax, rsp
0x180072f05  mov     [rbp+8E0h+var_40], rax
0x180072f0c  mov     r14d, r9d
0x180072f0f  mov     r13, r8
0x180072f12  mov     [rbp+8E0h+var_938], r8
0x180072f16  mov     rsi, rdx
0x180072f19  mov     rdi, rcx
0x180072f1c  mov     [rbp+8E0h+var_8C8], rcx
0x180072f20  call    ??0CPipeClient@@IEAA@XZ; CPipeClient::CPipeClient(void)
0x180072f25  nop
0x180072f26  xor     r12d, r12d
0x180072f29  mov     [rdi+78h], r12
0x180072f2d  mov     [rdi+80h], r12d
0x180072f34  mov     [rdi+88h], r12
0x180072f3b  mov     [rdi+90h], r12d
0x180072f42  lea     rcx, [rdi+0A8h]; this
0x180072f49  call    ??0CAutoEventSem@@QEAA@XZ; CAutoEventSem::CAutoEventSem(void)
0x180072f4e  nop
0x180072f4f  lea     rcx, [rdi+0B0h]; this
0x180072f56  call    ??0CAutoEventSem@@QEAA@XZ; CAutoEventSem::CAutoEventSem(void)
0x180072f5b  nop
0x180072f5c  lea     rbx, [rdi+0B8h]
0x180072f63  mov     [rbx+28h], r12d
0x180072f67  mov     rcx, rbx; lpCriticalSection
0x180072f6a  call    cs:__imp_InitializeCriticalSection
0x180072f70  lea     r15d, [r12+1]
0x180072f75  mov     [rbx+28h], r15d
0x180072f79  lea     rbx, [rdi+0E8h]
0x180072f80  mov     [rbx+28h], r12d
0x180072f84  mov     rcx, rbx; lpCriticalSection
0x180072f87  call    cs:__imp_InitializeCriticalSection
0x180072f8d  mov     [rbx+28h], r15d
0x180072f91  mov     [rdi+118h], r12d
0x180072f98  lea     rcx, [rdi+120h]; this
0x180072f9f  mov     [rcx], r12
0x180072fa2  mov     r8d, r15d; unsigned int
0x180072fa5  mov     edx, r15d; unsigned int
0x180072fa8  call    ?InternalCreate@CEventSem@@IEAAXKKPEB_WQEAU_SECURITY_ATTRIBUTES@@@Z; CEventSem::InternalCreate(ulong,ulong,wchar_t const *,_SECURITY_ATTRIBUTES * const)
0x180072fad  nop
0x180072fae  test    r14d, r14d
0x180072fb1  jz      short loc_180072FC7
0x180072fb3  call    cs:__imp_GetTickCount64
0x180072fb9  imul    ecx, r14d, 3E8h
0x180072fc0  add     rax, rcx
0x180072fc3  mov     [rdi+68h], rax
0x180072fc7  mov     edx, 3Ah ; ':'; Ch
0x180072fcc  mov     rcx, rsi; Str
0x180072fcf  call    cs:__imp_wcschr
0x180072fd5  mov     r14, rax
0x180072fd8  mov     ebx, 104h
0x180072fdd  test    rax, rax
0x180072fe0  jnz     loc_18007343F
0x180072fe6  lea     r14, aMsftewds; "MsFteWds"
0x180072fed  mov     [rsp+9E0h+var_990], 208h
0x180072ff5  mov     [rsp+9E0h+var_998], r12
0x180072ffa  call    cs:__imp_RtlIsStateSeparationEnabled
0x180073000  lea     r12, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows Search"
0x180073007  test    al, al
0x180073009  jnz     loc_18007346F
0x18007300f  lea     rax, [rsp+9E0h+var_990]
0x180073014  mov     [rsp+9E0h+pcbData], rax; pcbData
0x180073019  lea     rax, [rbp+8E0h+var_670]
0x180073020  mov     [rsp+9E0h+pvData], rax; pvData
0x180073025  mov     [rsp+9E0h+pdwType], 0; int
0x18007302e  mov     r9d, 2; dwFlags
0x180073034  lea     r8, aClientpipename; "ClientPipeName"
0x18007303b  mov     rdx, r12; lpSubKey
0x18007303e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180073045  call    cs:__imp_RegGetValueW
0x18007304b  xor     r12d, r12d
0x18007304e  test    eax, eax
0x180073050  jnz     loc_1800733E0
0x180073056  lea     r8, [rbp+8E0h+var_670]; wchar_t *
0x18007305d  mov     rdx, rsi; wchar_t *
0x180073060  mov     rcx, rdi; this
0x180073063  call    ?Init@CPipeClient@@IEAAXPEB_W0@Z; CPipeClient::Init(wchar_t const *,wchar_t const *)
0x180073068  mov     [rsp+9E0h+nSize], 10h
0x180073070  lea     rdx, [rsp+9E0h+nSize]; nSize
0x180073075  lea     rcx, [rbp+8E0h+Buffer]; lpBuffer
0x180073079  call    cs:__imp_GetComputerNameW
0x18007307f  test    eax, eax
0x180073081  jz      loc_1800734A9
0x180073087  mov     [rsp+9E0h+var_9A0], 101h
0x18007308f  lea     r8, [rsp+9E0h+var_9A0]; nSize
0x180073094  lea     rdx, [rbp+8E0h+NameBuffer]; lpNameBuffer
0x180073098  mov     ecx, 10002h; NameFormat
0x18007309d  call    cs:__imp_GetUserNameExW
0x1800730a3  test    al, al
0x1800730a5  jz      loc_1800734C2
0x1800730ab  call    ??2CDbProperties@@SAPEAX_K@Z; CDbProperties::operator new(unsigned __int64)
0x1800730b0  mov     [rsp+9E0h+var_998], rax
0x1800730b5  test    rax, rax
0x1800730b8  jz      short loc_1800730C5
0x1800730ba  mov     rcx, rax; this
0x1800730bd  call    ??0CDbProperties@@QEAA@PEAUIUnknown@@@Z; CDbProperties::CDbProperties(IUnknown *)
0x1800730c2  mov     r12, rax
0x1800730c5  mov     [rbp+8E0h+var_8C0], r12
0x1800730c9  xor     esi, esi
0x1800730cb  test    r12, r12
0x1800730ce  jz      loc_1800733C1
0x1800730d4  mov     rdx, r13; struct CDbProperties *
0x1800730d7  mov     rcx, r12; struct CDbProperties *
0x1800730da  call    ?TranslateNewPropsToOldProps@@YAXAEAVCDbProperties@@0@Z; TranslateNewPropsToOldProps(CDbProperties &,CDbProperties &)
0x1800730df  lea     rbx, ??_7CSizeSerStream@@6B@; const CSizeSerStream::`vftable'
0x1800730e6  mov     [rsp+9E0h+var_970], rbx
0x1800730eb  mov     dword ptr [rsp+9E0h+var_968], esi
0x1800730ef  lea     rdx, [rsp+9E0h+var_970]; struct PSerStream *
0x1800730f4  mov     rcx, r12; this
0x1800730f7  call    ?Marshall@CDbProperties@@QEBAXAEAVPSerStream@@@Z; CDbProperties::Marshall(PSerStream &)
0x1800730fc  mov     r14d, dword ptr [rsp+9E0h+var_968]
0x180073101  mov     [rsp+9E0h+var_99C], r14d
0x180073106  mov     [rsp+9E0h+var_980], rbx
0x18007310b  mov     [rsp+9E0h+var_978], esi
0x18007310f  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x180073116  movdqu  xmmword ptr [rbp+8E0h+var_8D8.Data1], xmm0
0x18007311b  lea     r9, [rbp+8E0h+var_8D8]; struct _GUID *
0x18007311f  lea     rdx, [rsp+9E0h+var_980]; struct PSerStream *
0x180073124  mov     rcx, r13; this
0x180073127  call    ?Marshall@CDbProperties@@QEBAXAEAVPSerStream@@KPEBU_GUID@@@Z; CDbProperties::Marshall(PSerStream &,ulong,_GUID const *)
0x18007312c  mov     ebx, [rsp+9E0h+var_978]
0x180073130  mov     dword ptr [rsp+9E0h+var_998], ebx
0x180073134  mov     dword ptr [rsp+9E0h+pdwType], ebx
0x180073138  mov     r9d, r14d; wchar_t *
0x18007313b  lea     r8, aProxyCbOldProp; "[Proxy] cb old props %d, cb new props: "...
0x180073142  mov     edx, 342h; wchar_t *
0x180073147  lea     rcx, aOnecoreuapBase_173; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18007314e  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180073153  lea     rax, [rbp+8E0h+Buffer]
0x180073157  or      r13, 0FFFFFFFFFFFFFFFFh
0x18007315b  mov     rcx, r13
0x18007315e  inc     rcx
0x180073161  cmp     [rax+rcx*2], si
0x180073165  jnz     short loc_18007315E
0x180073167  lea     rdx, [rbp+8E0h+NameBuffer]
0x18007316b  mov     rax, r13
0x18007316e  inc     rax
0x180073171  cmp     [rdx+rax*2], si
0x180073175  jnz     short loc_18007316E
0x180073177  add     eax, ecx
0x180073179  lea     esi, ds:34h[rax*2]
0x180073180  mov     edx, 0FFFFFFF8h
0x180073185  test    r14d, r14d
0x180073188  jz      short loc_180073197
0x18007318a  add     esi, 7
0x18007318d  and     esi, edx
0x18007318f  lea     eax, [r14+7]
0x180073193  and     eax, edx
0x180073195  add     esi, eax
0x180073197  test    ebx, ebx
0x180073199  jz      short loc_1800731A7
0x18007319b  add     esi, 7
0x18007319e  and     esi, edx
0x1800731a0  lea     eax, [rbx+7]
0x1800731a3  and     eax, edx
0x1800731a5  add     esi, eax
0x1800731a7  mov     [rbp+8E0h+var_8B0], esi
0x1800731aa  mov     ecx, esi; unsigned __int64
0x1800731ac  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800731b1  mov     r14, rax
0x1800731b4  mov     [rbp+8E0h+var_8B8], rax
0x1800731b8  mov     r8d, esi; Size
0x1800731bb  xor     edx, edx; Val
0x1800731bd  mov     rcx, rax; void *
0x1800731c0  call    memset_0
0x1800731c5  nop
0x1800731c6  mov     ecx, [rdi+10h]
0x1800731c9  mov     qword ptr [r14], 0C8h
0x1800731d0  xor     edx, edx
0x1800731d2  mov     [r14+8], rdx
0x1800731d6  mov     dword ptr [r14+10h], 10900h
0x1800731de  mov     [r14+14h], ecx
0x1800731e2  mov     eax, [rsp+9E0h+var_99C]
0x1800731e6  mov     [r14+18h], eax
0x1800731ea  mov     ebx, dword ptr [rsp+9E0h+var_998]
0x1800731ee  mov     [r14+20h], ebx
0x1800731f2  lea     rax, [rbp+8E0h+Buffer]
0x1800731f6  mov     r8, r13
0x1800731f9  inc     r8
0x1800731fc  cmp     [rax+r8*2], dx
0x180073201  jnz     short loc_1800731F9
0x180073203  lea     rcx, [r14+30h]; void *
0x180073207  lea     r8, ds:2[r8*2]; Size
0x18007320f  lea     rdx, [rbp+8E0h+Buffer]; Src
0x180073213  call    memcpy_0
0x180073218  lea     rcx, [rbp+8E0h+NameBuffer]
0x18007321c  mov     r8, r13
0x18007321f  xor     eax, eax
0x180073221  inc     r8
0x180073224  cmp     [rcx+r8*2], ax
0x180073229  jnz     short loc_180073221
0x18007322b  inc     r13
0x18007322e  cmp     [r14+r13*2+30h], ax
0x180073234  jnz     short loc_18007322B
0x180073236  lea     r8, ds:2[r8*2]; Size
0x18007323e  add     r13, 19h
0x180073242  lea     rcx, [r14+r13*2]; void *
0x180073246  lea     rdx, [rbp+8E0h+NameBuffer]; Src
0x18007324a  call    memcpy_0
0x18007324f  mov     rcx, r14; this
0x180073252  call    ?GetBlobStartAddr@CPMConnectIn@@QEBAPEAEXZ; CPMConnectIn::GetBlobStartAddr(void)
0x180073257  mov     rcx, rax
0x18007325a  lea     rax, ??_7CMemSerStream@@6B@; const CMemSerStream::`vftable'
0x180073261  mov     [rbp+8E0h+var_900], rax
0x180073265  xor     r13d, r13d
0x180073268  mov     [rbp+8E0h+var_8F8], r13d
0x18007326c  mov     [rbp+8E0h+var_8F0], rcx
0x180073270  mov     [rbp+8E0h+var_8E8], rcx
0x180073274  mov     eax, [rsp+9E0h+var_99C]
0x180073278  add     rax, rcx
0x18007327b  mov     [rbp+8E0h+var_8E0], rax
0x18007327f  lea     rdx, [rbp+8E0h+var_900]; struct PSerStream *
0x180073283  mov     rcx, r12; this
0x180073286  call    ?Marshall@CDbProperties@@QEBAXAEAVPSerStream@@@Z; CDbProperties::Marshall(PSerStream &)
0x18007328b  mov     rcx, r14; this
0x18007328e  call    ?GetBlobStartAddr@CPMConnectIn@@QEBAPEAEXZ; CPMConnectIn::GetBlobStartAddr(void)
0x180073293  mov     r8d, [r14+18h]
0x180073297  add     r8, 7
0x18007329b  and     r8, 0FFFFFFFFFFFFFFF8h
0x18007329f  add     r8, rax; unsigned int
0x1800732a2  lea     rax, ??_7CMemSerStream@@6B@; const CMemSerStream::`vftable'
0x1800732a9  mov     [rbp+8E0h+var_928], rax
0x1800732ad  mov     [rbp+8E0h+var_920], r13d
0x1800732b1  mov     [rbp+8E0h+Block], r8
0x1800732b5  mov     [rbp+8E0h+var_910], r8
0x1800732b9  lea     rax, [r8+rbx]
0x1800732bd  mov     [rbp+8E0h+var_908], rax
0x1800732c1  lea     r9, [rbp+8E0h+var_8D8]; struct _GUID *
0x1800732c5  lea     rdx, [rbp+8E0h+var_928]; struct PSerStream *
0x1800732c9  mov     rcx, [rbp+8E0h+var_938]; this
0x1800732cd  call    ?Marshall@CDbProperties@@QEBAXAEAVPSerStream@@KPEBU_GUID@@@Z; CDbProperties::Marshall(PSerStream &,ulong,_GUID const *)
0x1800732d2  mov     edx, esi; unsigned int
0x1800732d4  mov     rcx, r14; this
0x1800732d7  call    ?ComputeCheckSum@CProxyMessage@@AEAAKK@Z; CProxyMessage::ComputeCheckSum(ulong)
0x1800732dc  mov     [r14+8], eax
0x1800732e0  mov     [rsp+9E0h+var_988], r13d
0x1800732e5  lea     rax, [rsp+9E0h+var_988]
0x1800732ea  mov     [rsp+9E0h+pvData], rax; unsigned int *
0x1800732ef  mov     dword ptr [rsp+9E0h+pdwType], 28h ; '('; unsigned int
0x1800732f7  lea     r9, [rbp+8E0h+var_960]; void *
0x1800732fb  mov     r8d, esi; unsigned int
0x1800732fe  mov     rdx, r14; void *
0x180073301  mov     rcx, rdi; this
0x180073304  call    ?DataWriteRead@CRequestClient@@QEAAXPEAXK0KAEAK@Z; CRequestClient::DataWriteRead(void *,ulong,void *,ulong,ulong &)
0x180073309  mov     eax, [rbp+8E0h+var_950]
0x18007330c  mov     [rdi+94h], eax
0x180073312  mov     rax, [rbp+8E0h+var_948]
0x180073316  cmp     [r14+18h], rax
0x18007331a  jz      loc_1800734E0
0x180073320  mov     ecx, dword ptr [rbp+8E0h+var_940+4]
0x180073323  mov     eax, dword ptr [rbp+8E0h+var_940]
0x180073326  mov     r15d, dword ptr [rbp+8E0h+var_948+4]
0x18007332a  mov     edx, dword ptr [rbp+8E0h+var_948]
0x18007332d  mov     [rdi+98h], edx
0x180073333  mov     [rdi+9Ch], r15d
0x18007333a  mov     [rdi+0A0h], eax
0x180073340  mov     [rdi+0A4h], ecx
0x180073346  lea     rsi, ??_7CMemSerStream@@6B@; const CMemSerStream::`vftable'
0x18007334d  mov     [rbp+8E0h+var_928], rsi
0x180073351  cmp     [rbp+8E0h+var_920], r13d
0x180073355  ja      loc_18007350B
0x18007335b  lea     rbx, ??_7PSerStream@@6B@; const PSerStream::`vftable'
0x180073362  mov     [rbp+8E0h+var_928], rbx
0x180073366  mov     [rbp+8E0h+var_900], rsi
0x18007336a  cmp     [rbp+8E0h+var_8F8], r13d
0x18007336e  ja      loc_180073519
0x180073374  mov     [rbp+8E0h+var_900], rbx
0x180073378  mov     rcx, r14; Block
0x18007337b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180073380  nop
0x180073381  mov     [rsp+9E0h+var_980], rbx
0x180073386  mov     [rsp+9E0h+var_970], rbx
0x18007338b  mov     rcx, r12; this
0x18007338e  call    ?Release@CDbProperties@@UEAAKXZ; CDbProperties::Release(void)
0x180073393  nop
0x180073394  mov     rax, rdi
0x180073397  mov     rcx, [rbp+8E0h+var_40]
0x18007339e  xor     rcx, rsp; StackCookie
0x1800733a1  call    __security_check_cookie
0x1800733a6  mov     rbx, [rsp+9E0h+arg_18]
0x1800733ae  add     rsp, 9B0h
0x1800733b5  pop     r15
0x1800733b7  pop     r14
0x1800733b9  pop     r13
0x1800733bb  pop     r12
0x1800733bd  pop     rdi
0x1800733be  pop     rsi
0x1800733bf  pop     rbp
0x1800733c0  retn
0x1800733c1  mov     rcx, [rbp+8E8h]; this
  ... truncated ...
```
