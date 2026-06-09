# CRequestQueue::CRequestQueue(CEventSem &,IFTEPluginLocator *,wchar_t const *,wchar_t const *,void *)

- ea: `0x1800f510c`
- end: `0x1800f567d`
- name: `??0CRequestQueue@@QEAA@AEAVCEventSem@@PEAUIFTEPluginLocator@@PEB_W2PEAX@Z`
- size: `1393`
- prototype: `CRequestQueue *__usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, struct CEventSem *@<rdx>, struct IFTEPluginLocator *@<r8>, const wchar_t *@<r9>, const wchar_t *, void *)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180169f80`
- `0x180181abc`

## callees

- `0x18002f914`
- `0x180038f08`
- `0x180073578`
- `0x180073748`
- `0x1800740f4`
- `0x180075d8c`
- `0x180075dd0`
- `0x18008e3e0`
- `0x18008efd8`
- `0x18008f020`
- `0x1800f510c`
- `0x1800f5684`
- `0x1800f5814`
- `0x1800f7b50`
- `0x18013effc`
- `0x180147154`
- `0x180153450`
- `0x18015d374`
- `0x18016c024`
- `0x18016c7f0`
- `0x18017504c`
- `0x180188d90`
- `0x180189280`
- `0x180189cce`
- `0x18018e8cb`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f537b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f537b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800f5153`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800f5368`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800f5153`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800f5368`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f538f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f538f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f564d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f564d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f54fd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f54fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
CRequestQueue *__fastcall CRequestQueue::CRequestQueue(
        char *lpCriticalSection,
        struct CEventSem *a2,
        struct IFTEPluginLocator *a3,
        const wchar_t *a4,
        wchar_t *a5,
        void *a6)
{
  const wchar_t *v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rsi
  __int64 v13; // r8
  wchar_t *v14; // rdx
  unsigned int v15; // edx
  bool v16; // al
  wchar_t *v17; // rcx
  const wchar_t *v18; // rax
  __int64 v19; // rdx
  LPWSTR UserStringSid; // rax
  LPWSTR v21; // rbx
  size_t *v22; // r8
  wchar_t *v23; // rsi
  const WCHAR *v24; // r14
  HRESULT v25; // eax
  unsigned int v26; // r11d
  int v27; // eax
  const char *v28; // r9
  int SystemVolumeDriveLetter; // eax
  int v31; // eax
  struct _SECURITY_ATTRIBUTES *const cchToCopya; // [rsp+20h] [rbp-E0h]
  size_t cchToCopy; // [rsp+20h] [rbp-E0h]
  DWORD v34[2]; // [rsp+40h] [rbp-C0h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+48h] [rbp-B8h] BYREF
  size_t cchDest; // [rsp+50h] [rbp-B0h]
  PSECURITY_DESCRIPTOR SecurityDescriptor[3]; // [rsp+58h] [rbp-A8h] BYREF
  void **v38; // [rsp+70h] [rbp-90h] BYREF
  void *Src; // [rsp+78h] [rbp-88h]
  __int64 v40; // [rsp+80h] [rbp-80h]
  wchar_t v41[1028]; // [rsp+88h] [rbp-78h] BYREF
  wchar_t v42[16]; // [rsp+890h] [rbp+790h] BYREF
  wchar_t v43[264]; // [rsp+8B0h] [rbp+7B0h] BYREF
  wchar_t pszSrc[408]; // [rsp+AC0h] [rbp+9C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E48h] [rbp+D48h]

  SecurityDescriptor[1] = lpCriticalSection;
  *((_DWORD *)lpCriticalSection + 10) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  *((_DWORD *)lpCriticalSection + 10) = 1;
  THashSet<CRequestServer *>::THashSet<CRequestServer *>(
    (_DWORD)lpCriticalSection + 48,
    0,
    (unsigned int)CRequestQueue::HashFunc,
    1,
    0);
  *((_QWORD *)lpCriticalSection + 14) = 0;
  XArray<CServerItem>::XArray<CServerItem>(lpCriticalSection + 120, 10);
  *((_QWORD *)lpCriticalSection + 17) = 0;
  *((_QWORD *)lpCriticalSection + 18) = 0;
  *((_QWORD *)lpCriticalSection + 19) = 0;
  *((_QWORD *)lpCriticalSection + 20) = 0;
  *((_DWORD *)lpCriticalSection + 42) = 0;
  *(_QWORD *)(lpCriticalSection + 172) = 30000;
  *((_DWORD *)lpCriticalSection + 45) = 0;
  *((_DWORD *)lpCriticalSection + 46) = 30000;
  *((_QWORD *)lpCriticalSection + 24) = 0;
  *(_QWORD *)v34 = lpCriticalSection + 200;
  *((_QWORD *)lpCriticalSection + 25) = 0;
  *((_QWORD *)lpCriticalSection + 26) = 0;
  *((_DWORD *)lpCriticalSection + 54) = 0;
  *((_DWORD *)lpCriticalSection + 66) = 0;
  *((_OWORD *)lpCriticalSection + 14) = 0;
  *((_OWORD *)lpCriticalSection + 15) = 0;
  *((_QWORD *)lpCriticalSection + 32) = 0;
  *((_DWORD *)lpCriticalSection + 68) = 0;
  *((_QWORD *)lpCriticalSection + 35) = 0;
  *((_QWORD *)lpCriticalSection + 36) = 0;
  *((_DWORD *)lpCriticalSection + 74) = 0;
  *((_QWORD *)lpCriticalSection + 38) = 0;
  *((_QWORD *)lpCriticalSection + 39) = 0;
  *((_DWORD *)lpCriticalSection + 80) = 11;
  *(_QWORD *)(lpCriticalSection + 324) = 1;
  CAutoEventSem::CAutoEventSem((CAutoEventSem *)(lpCriticalSection + 336));
  *((_QWORD *)lpCriticalSection + 43) = 0;
  CEventSem::InternalCreate((CEventSem *)(lpCriticalSection + 344), 1u, 0, v9, cchToCopya);
  *((_QWORD *)lpCriticalSection + 44) = a2;
  *((_QWORD *)lpCriticalSection + 45) = 0;
  *((_QWORD *)lpCriticalSection + 46) = 0;
  *((_DWORD *)lpCriticalSection + 94) = 0;
  std::wstring::wstring(lpCriticalSection + 392, v10);
  *((_QWORD *)lpCriticalSection + 53) = a6;
  lpCriticalSection[432] = 0;
  v12 = -1;
  if ( a5 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a5[v13] );
    std::wstring::_Assign<wchar_t>(v11, a5, v13);
  }
  else
  {
    v34[0] = 520;
    if ( (unsigned int)WSearchRegGetValue(
                         HKEY_LOCAL_MACHINE,
                         L"SOFTWARE\\Microsoft\\Windows Search",
                         L"ServerPipeName",
                         2u,
                         0,
                         v43,
                         v34) )
      StringCchCopyW(v43, 0x104u, L"MsFteWds");
  }
  Src = v41;
  v40 = 1025;
  v41[0] = 0;
  v38 = &TLMString<1024,1024,1048576>::`vftable';
  CLMString::Assign((CLMString *)&v38, L"\\\\.\\pipe\\", 0, 0xFFFFFFFF);
  v14 = v43;
  if ( a5 )
    v14 = a5;
  ((void (__fastcall *)(void ***, wchar_t *, _QWORD, __int64))v38[4])(&v38, v14, HIDWORD(v40), 0xFFFFFFFFLL);
  ((void (__fastcall *)(void ***, const OLECHAR *, _QWORD, __int64))v38[4])(&v38, &psz, HIDWORD(v40), 0xFFFFFFFFLL);
  XArray<wchar_t>::Init(lpCriticalSection + 368, (unsigned int)(HIDWORD(v40) + 1));
  if ( *((_DWORD *)lpCriticalSection + 94) >= (unsigned int)(HIDWORD(v40) + 1) )
    memcpy_0(*((void **)lpCriticalSection + 46), Src, 2LL * (unsigned int)(HIDWORD(v40) + 1));
  *((_QWORD *)lpCriticalSection + 24) = a3;
  (*(void (__fastcall **)(struct IFTEPluginLocator *))(*(_QWORD *)a3 + 8LL))(a3);
  InitializeCriticalSection((LPCRITICAL_SECTION)(lpCriticalSection + 224));
  *((_DWORD *)lpCriticalSection + 66) = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)(lpCriticalSection + 224));
  *(_QWORD *)(lpCriticalSection + 324) = 2;
  LeaveCriticalSection((LPCRITICAL_SECTION)(lpCriticalSection + 224));
  *((_DWORD *)lpCriticalSection + 78) = 1;
  memset_0(*((void **)lpCriticalSection + 15), 0, (unsigned int)(8 * *((_DWORD *)lpCriticalSection + 32)));
  CRequestQueue::UpdatePerfSettings((LPCRITICAL_SECTION)lpCriticalSection, v15);
  v16 = LookupPerVolumeCatalogConfiguration();
  lpCriticalSection[384] = v16;
  if ( v16 )
  {
    SystemVolumeDriveLetter = GetSystemVolumeDriveLetter((wchar_t *)lpCriticalSection + 193);
    if ( SystemVolumeDriveLetter < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1873,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
        (const char *)(unsigned int)SystemVolumeDriveLetter,
        cchToCopy);
  }
  else
  {
    *((_WORD *)lpCriticalSection + 193) = 0;
  }
  v17 = pszSrc;
  v18 = L"O:SYD:(A;;0xC0100000;;;SY)(A;;0x0012019B;;;AU)(A;;0x0012019B;;;BA)(A;;0x0012019B;;;BG)(A;;0x0012019B;;;S-1-15-3-"
         "1024-724741592-1210917904-489960769-637019204-3345707629-3097053430-1727148295-85063603)(A;;0x0012019B;;;S-1-15"
         "-3-128907917-1049808183-3772720920-2589851895-2273257875-2082631859-2896883434)(A;;0x0012019B;;;S-1-15-3-186189"
         "7761-1695161497-2927542615-642690995-327840285-2659745135-2630312742)";
  v19 = 6;
  do
  {
    *(_OWORD *)v17 = *(_OWORD *)v18;
    *((_OWORD *)v17 + 1) = *((_OWORD *)v18 + 1);
    *((_OWORD *)v17 + 2) = *((_OWORD *)v18 + 2);
    *((_OWORD *)v17 + 3) = *((_OWORD *)v18 + 3);
    *((_OWORD *)v17 + 4) = *((_OWORD *)v18 + 4);
    *((_OWORD *)v17 + 5) = *((_OWORD *)v18 + 5);
    *((_OWORD *)v17 + 6) = *((_OWORD *)v18 + 6);
    *((_OWORD *)v17 + 7) = *((_OWORD *)v18 + 7);
    v17 += 64;
    v18 += 64;
    --v19;
  }
  while ( v19 );
  *(_OWORD *)v17 = *(_OWORD *)v18;
  *((_OWORD *)v17 + 1) = *((_OWORD *)v18 + 1);
  *((_QWORD *)v17 + 4) = *((_QWORD *)v18 + 4);
  wcscpy(v42, L"S:(ML;;NW;;;LW)");
  UserStringSid = GetUserStringSid();
  v21 = UserStringSid;
  *(_QWORD *)v34 = UserStringSid;
  pszDest = 0;
  LODWORD(cchDest) = 0;
  if ( !UserStringSid )
  {
    XArray<wchar_t>::Init(&pszDest, 421);
    v23 = pszDest;
    v24 = pszDest;
    if ( (_DWORD)cchDest )
    {
      if ( (unsigned int)cchDest <= 0x7FFFFFFFuLL )
      {
        v25 = StringCopyWorkerW(pszDest, (unsigned int)cchDest, v22, pszSrc, cchToCopy);
        if ( v25 >= 0 )
        {
          v27 = StringCchCatW(v23, v26, v42);
          if ( v27 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1941,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
              (const char *)(unsigned int)v27,
              cchToCopy);
          goto LABEL_18;
        }
LABEL_32:
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x193A,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
          (const char *)(unsigned int)v25,
          cchToCopy);
      }
      *pszDest = 0;
    }
    v25 = -2147024809;
    goto LABEL_32;
  }
  do
    ++v12;
  while ( UserStringSid[v12] );
  XArray<wchar_t>::Init(&pszDest, (unsigned int)(2 * v12 + 403));
  v23 = pszDest;
  v31 = StringCchPrintfW(
          pszDest,
          (unsigned int)cchDest,
          L"O:%sD:(A;;0xC0100000;;;%s)(A;;0xC0100000;;;SY)(A;;0xC0100000;;;BA)(A;;0xC0100000;;;BG)(A;;0xC0100000;;;S-1-15-"
           "3-1024-724741592-1210917904-489960769-637019204-3345707629-3097053430-1727148295-85063603)(A;;0xC0100000;;;S-"
           "1-15-2-128907917-1049808183-3772720920-2589851895-2273257875-2082631859-2896883434)(A;;0xC0100000;;;S-1-15-2-"
           "1861897761-1695161497-2927542615-642690995-327840285-2659745135-2630312742)",
          v21);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x192B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const char *)(unsigned int)v31,
      (int)v21);
  v24 = v23;
LABEL_18:
  SecurityDescriptor[0] = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v24, 1u, SecurityDescriptor, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x194B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      v28);
  *((PSECURITY_DESCRIPTOR *)lpCriticalSection + 45) = SecurityDescriptor[0];
  operator delete(v23);
  if ( v21 )
    LocalFree(v21);
  v38 = &TLMString<1024,1024,1048576>::`vftable';
  CLMString::DeleteBuf((CLMString *)&v38, v41);
  return (CRequestQueue *)lpCriticalSection;
}

```

## disassembly

```asm
0x1800f510c  push    rbp
0x1800f510e  push    rbx
0x1800f510f  push    rsi
0x1800f5110  push    rdi
0x1800f5111  push    r12
0x1800f5113  push    r13
0x1800f5115  push    r14
0x1800f5117  push    r15
0x1800f5119  lea     rbp, [rsp-0D08h]
0x1800f5121  sub     rsp, 0E08h
0x1800f5128  mov     rax, cs:__security_cookie
0x1800f512f  xor     rax, rsp
0x1800f5132  mov     [rbp+0D40h+var_50], rax
0x1800f5139  mov     r13, r8
0x1800f513c  mov     rbx, rdx
0x1800f513f  mov     rdi, rcx
0x1800f5142  mov     r12, [rbp+0D40h+arg_20]
0x1800f5149  mov     [rsp+0E40h+var_DE0], rcx
0x1800f514e  xor     esi, esi
0x1800f5150  mov     [rcx+28h], esi
0x1800f5153  call    cs:__imp_InitializeCriticalSection
0x1800f5159  lea     eax, [rsi+1]
0x1800f515c  mov     [rdi+28h], eax
0x1800f515f  lea     rcx, [rdi+30h]
0x1800f5163  mov     dword ptr [rsp+0E40h+cchToCopy], esi; int
0x1800f5167  mov     r9d, eax
0x1800f516a  lea     r8, ?HashFunc@CRequestQueue@@CAKPEBQEAVCRequestServer@@K@Z; CRequestQueue::HashFunc(CRequestServer * const *,ulong)
0x1800f5171  xor     edx, edx
0x1800f5173  call    ??0?$THashSet@PEAVCRequestServer@@@@QEAA@KP6AKPEBQEAVCRequestServer@@K@ZHH@Z; THashSet<CRequestServer *>::THashSet<CRequestServer *>(ulong,ulong (*)(CRequestServer * const *,ulong),int,int)
0x1800f5178  nop
0x1800f5179  mov     [rdi+70h], rsi
0x1800f517d  lea     rcx, [rdi+78h]
0x1800f5181  lea     edx, [rsi+0Ah]
0x1800f5184  call    ??0?$XArray@VCServerItem@@@@QEAA@I@Z; XArray<CServerItem>::XArray<CServerItem>(uint)
0x1800f5189  nop
0x1800f518a  mov     [rdi+88h], rsi
0x1800f5191  mov     [rdi+90h], rsi
0x1800f5198  mov     [rdi+98h], rsi
0x1800f519f  mov     [rdi+0A0h], rsi
0x1800f51a6  mov     [rdi+0A8h], esi
0x1800f51ac  mov     eax, 7530h
0x1800f51b1  mov     [rdi+0ACh], rax
0x1800f51b8  mov     [rdi+0B4h], esi
0x1800f51be  mov     [rdi+0B8h], eax
0x1800f51c4  mov     [rdi+0C0h], rsi
0x1800f51cb  lea     r14, [rdi+0C8h]
0x1800f51d2  mov     qword ptr [rsp+0E40h+var_E00], r14
0x1800f51d7  mov     [r14], rsi
0x1800f51da  mov     [r14+8], rsi
0x1800f51de  mov     [r14+10h], esi
0x1800f51e2  lea     r15, [r14+18h]
0x1800f51e6  mov     [r15+28h], esi
0x1800f51ea  xorps   xmm0, xmm0
0x1800f51ed  xor     eax, eax
0x1800f51ef  movups  xmmword ptr [r15], xmm0
0x1800f51f3  movups  xmmword ptr [r15+10h], xmm0
0x1800f51f8  mov     [r15+20h], rax
0x1800f51fc  mov     [r14+48h], esi
0x1800f5200  mov     [r14+50h], rsi
0x1800f5204  mov     [r14+58h], rsi
0x1800f5208  mov     [r14+60h], esi
0x1800f520c  mov     [r14+68h], rsi
0x1800f5210  mov     [r14+70h], rsi
0x1800f5214  mov     dword ptr [r14+78h], 0Bh
0x1800f521c  mov     qword ptr [r14+7Ch], 1
0x1800f5224  lea     rcx, [rdi+150h]; this
0x1800f522b  call    ??0CAutoEventSem@@QEAA@XZ; CAutoEventSem::CAutoEventSem(void)
0x1800f5230  nop
0x1800f5231  lea     rcx, [rdi+158h]; this
0x1800f5238  mov     [rcx], rsi
0x1800f523b  xor     r8d, r8d; unsigned int
0x1800f523e  lea     edx, [rsi+1]; unsigned int
0x1800f5241  call    ?InternalCreate@CEventSem@@IEAAXKKPEB_WQEAU_SECURITY_ATTRIBUTES@@@Z; CEventSem::InternalCreate(ulong,ulong,wchar_t const *,_SECURITY_ATTRIBUTES * const)
0x1800f5246  nop
0x1800f5247  mov     [rdi+160h], rbx
0x1800f524e  mov     [rdi+168h], rsi
0x1800f5255  lea     rbx, [rdi+170h]
0x1800f525c  mov     [rbx], rsi
0x1800f525f  mov     [rbx+8], esi
0x1800f5262  lea     rcx, [rdi+188h]
0x1800f5269  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800f526e  nop
0x1800f526f  mov     rax, [rbp+0D40h+arg_28]
0x1800f5276  mov     [rdi+1A8h], rax
0x1800f527d  mov     [rdi+1B0h], sil
0x1800f5284  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800f5288  xor     edx, edx
0x1800f528a  test    r12, r12
0x1800f528d  jz      loc_1802BEC18
0x1800f5293  mov     r8, rsi
0x1800f5296  inc     r8
0x1800f5299  cmp     [r12+r8*2], dx
0x1800f529e  jnz     short loc_1800F5296
0x1800f52a0  mov     rdx, r12
0x1800f52a3  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800f52a8  lea     rax, [rbp+0D40h+var_DB8]
0x1800f52ac  mov     [rsp+0E40h+Src], rax
0x1800f52b1  mov     [rbp+0D40h+var_DC0], 401h
0x1800f52b9  xor     eax, eax
0x1800f52bb  mov     [rbp+0D40h+var_DB8], ax
0x1800f52bf  lea     rax, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x1800f52c6  mov     [rsp+0E40h+var_DD0], rax
0x1800f52cb  or      r9d, 0FFFFFFFFh; unsigned int
0x1800f52cf  xor     r8d, r8d; unsigned int
0x1800f52d2  lea     rdx, aPipe_0; "\\\\.\\pipe\\"
0x1800f52d9  lea     rcx, [rsp+0E40h+var_DD0]; this
0x1800f52de  call    ?Assign@CLMString@@UEAAHPEB_WII@Z; CLMString::Assign(wchar_t const *,uint,uint)
0x1800f52e3  lea     rdx, [rbp+0D40h+var_590]
0x1800f52ea  test    r12, r12
0x1800f52ed  cmovnz  rdx, r12
0x1800f52f1  mov     rax, [rsp+0E40h+var_DD0]
0x1800f52f6  or      r12d, 0FFFFFFFFh
0x1800f52fa  mov     r9d, r12d
0x1800f52fd  mov     r8d, dword ptr [rbp+0D40h+var_DC0+4]
0x1800f5301  lea     rcx, [rsp+0E40h+var_DD0]
0x1800f5306  mov     rax, [rax+20h]
0x1800f530a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f530f  mov     rax, [rsp+0E40h+var_DD0]
0x1800f5314  mov     r9d, r12d
0x1800f5317  mov     r8d, dword ptr [rbp+0D40h+var_DC0+4]
0x1800f531b  lea     rdx, psz
0x1800f5322  lea     rcx, [rsp+0E40h+var_DD0]
0x1800f5327  mov     rax, [rax+20h]
0x1800f532b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5330  mov     edx, dword ptr [rbp+0D40h+var_DC0+4]
0x1800f5333  inc     edx
0x1800f5335  mov     rcx, rbx
0x1800f5338  call    ?Init@?$XArray@_W@@QEAAXI@Z; XArray<wchar_t>::Init(uint)
0x1800f533d  mov     eax, dword ptr [rbp+0D40h+var_DC0+4]
0x1800f5340  inc     eax
0x1800f5342  cmp     [rdi+178h], eax
0x1800f5348  jnb     loc_1800F55E1
0x1800f534e  mov     [rdi+0C0h], r13
0x1800f5355  mov     rax, [r13+0]
0x1800f5359  mov     rcx, r13
0x1800f535c  mov     rax, [rax+8]
0x1800f5360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5365  mov     rcx, r15; lpCriticalSection
0x1800f5368  call    cs:__imp_InitializeCriticalSection
0x1800f536e  mov     r13d, 1
0x1800f5374  mov     [r15+28h], r13d
0x1800f5378  mov     rcx, r15; lpCriticalSection
0x1800f537b  call    cs:__imp_EnterCriticalSection
0x1800f5381  mov     qword ptr [r14+7Ch], 2
0x1800f5389  xor     r12d, r12d
0x1800f538c  mov     rcx, r15; lpCriticalSection
0x1800f538f  call    cs:__imp_LeaveCriticalSection
0x1800f5395  mov     [r14+70h], r13d
0x1800f5399  mov     r8d, [rdi+80h]
0x1800f53a0  shl     r8d, 3; Size
0x1800f53a4  xor     edx, edx; Val
0x1800f53a6  mov     rcx, [rdi+78h]; void *
0x1800f53aa  call    memset_0
0x1800f53af  mov     rcx, rdi; lpCriticalSection
0x1800f53b2  call    ?UpdatePerfSettings@CRequestQueue@@AEAAXK@Z; CRequestQueue::UpdatePerfSettings(ulong)
0x1800f53b7  call    ?LookupPerVolumeCatalogConfiguration@@YA_NXZ; LookupPerVolumeCatalogConfiguration(void)
0x1800f53bc  mov     [rdi+180h], al
0x1800f53c2  test    al, al
0x1800f53c4  jnz     loc_1800F556A
0x1800f53ca  mov     [rdi+182h], r12w
0x1800f53d2  lea     rcx, [rbp+0D40h+pszSrc]
0x1800f53d9  lea     rax, aOSydA0xc010000; "O:SYD:(A;;0xC0100000;;;SY)(A;;0x0012019"...
0x1800f53e0  mov     edx, 6
0x1800f53e5  lea     r8d, [rdx+7Ah]
0x1800f53e9  movups  xmm0, xmmword ptr [rax]
0x1800f53ec  movups  xmmword ptr [rcx], xmm0
0x1800f53ef  movups  xmm1, xmmword ptr [rax+10h]
0x1800f53f3  movups  xmmword ptr [rcx+10h], xmm1
0x1800f53f7  movups  xmm0, xmmword ptr [rax+20h]
0x1800f53fb  movups  xmmword ptr [rcx+20h], xmm0
0x1800f53ff  movups  xmm1, xmmword ptr [rax+30h]
0x1800f5403  movups  xmmword ptr [rcx+30h], xmm1
0x1800f5407  movups  xmm0, xmmword ptr [rax+40h]
0x1800f540b  movups  xmmword ptr [rcx+40h], xmm0
0x1800f540f  movups  xmm1, xmmword ptr [rax+50h]
0x1800f5413  movups  xmmword ptr [rcx+50h], xmm1
0x1800f5417  movups  xmm0, xmmword ptr [rax+60h]
0x1800f541b  movups  xmmword ptr [rcx+60h], xmm0
0x1800f541f  movups  xmm1, xmmword ptr [rax+70h]
0x1800f5423  movups  xmmword ptr [rcx+70h], xmm1
0x1800f5427  add     rcx, r8
0x1800f542a  add     rax, r8
0x1800f542d  sub     rdx, r13
0x1800f5430  jnz     short loc_1800F53E9
0x1800f5432  movups  xmm0, xmmword ptr [rax]
0x1800f5435  movups  xmmword ptr [rcx], xmm0
0x1800f5438  movups  xmm1, xmmword ptr [rax+10h]
0x1800f543c  movups  xmmword ptr [rcx+10h], xmm1
0x1800f5440  mov     rax, [rax+20h]
0x1800f5444  mov     [rcx+20h], rax
0x1800f5448  movups  xmm0, xmmword ptr cs:aSMlNwLw; "S:(ML;;NW;;;LW)"
0x1800f544f  movups  xmmword ptr [rbp+0D40h+var_5B0], xmm0
0x1800f5456  movups  xmm1, xmmword ptr cs:aSMlNwLw+10h; "W;;;LW)"
0x1800f545d  movups  [rbp+0D40h+var_5A0], xmm1
0x1800f5464  call    ?GetUserStringSid@@YAPEA_WXZ; GetUserStringSid(void)
0x1800f5469  mov     rbx, rax
0x1800f546c  mov     qword ptr [rsp+0E40h+var_E00], rax
0x1800f5471  mov     [rsp+0E40h+pszDest], r12
0x1800f5476  mov     dword ptr [rsp+0E40h+cchDest], r12d
0x1800f547b  test    rax, rax
0x1800f547e  jnz     loc_1800F559A
0x1800f5484  mov     edx, 1A5h
0x1800f5489  lea     rcx, [rsp+0E40h+pszDest]
0x1800f548e  call    ?Init@?$XArray@_W@@QEAAXI@Z; XArray<wchar_t>::Init(uint)
0x1800f5493  mov     r11d, dword ptr [rsp+0E40h+cchDest]
0x1800f5498  mov     rsi, [rsp+0E40h+pszDest]
0x1800f549d  mov     r14, rsi
0x1800f54a0  test    r11, r11
0x1800f54a3  jz      loc_1800F565C
0x1800f54a9  cmp     r11, 7FFFFFFFh
0x1800f54b0  ja      loc_1800F5658
0x1800f54b6  lea     r9, [rbp+0D40h+pszSrc]; pszSrc
0x1800f54bd  mov     edx, r11d; cchDest
0x1800f54c0  mov     rcx, rsi; pszDest
0x1800f54c3  call    StringCopyWorkerW
0x1800f54c8  test    eax, eax
0x1800f54ca  js      loc_1800F5661
0x1800f54d0  lea     r8, [rbp+0D40h+var_5B0]; wchar_t *
0x1800f54d7  mov     edx, r11d; unsigned __int64
0x1800f54da  mov     rcx, rsi; wchar_t *
0x1800f54dd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800f54e2  test    eax, eax
0x1800f54e4  js      loc_1800F5615
0x1800f54ea  mov     [rsp+0E40h+SecurityDescriptor], r12
0x1800f54ef  xor     r9d, r9d; SecurityDescriptorSize
0x1800f54f2  lea     r8, [rsp+0E40h+SecurityDescriptor]; SecurityDescriptor
0x1800f54f7  mov     edx, r13d; StringSDRevision
0x1800f54fa  mov     rcx, r14; StringSecurityDescriptor
0x1800f54fd  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800f5503  test    eax, eax
0x1800f5505  jz      loc_1800F5631
0x1800f550b  mov     rax, [rsp+0E40h+SecurityDescriptor]
0x1800f5510  mov     [rdi+168h], rax
0x1800f5517  mov     rcx, rsi; Block
0x1800f551a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f551f  nop
0x1800f5520  test    rbx, rbx
0x1800f5523  jnz     loc_1800F564A
0x1800f5529  lea     rax, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x1800f5530  mov     [rsp+0E40h+var_DD0], rax
0x1800f5535  lea     rdx, [rbp+0D40h+var_DB8]; wchar_t *
0x1800f5539  lea     rcx, [rsp+0E40h+var_DD0]; this
0x1800f553e  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x1800f5543  nop
0x1800f5544  mov     rax, rdi
0x1800f5547  mov     rcx, [rbp+0D40h+var_50]
0x1800f554e  xor     rcx, rsp; StackCookie
0x1800f5551  call    __security_check_cookie
0x1800f5556  add     rsp, 0E08h
0x1800f555d  pop     r15
0x1800f555f  pop     r14
0x1800f5561  pop     r13
0x1800f5563  pop     r12
0x1800f5565  pop     rdi
0x1800f5566  pop     rsi
0x1800f5567  pop     rbx
0x1800f5568  pop     rbp
0x1800f5569  retn
0x1800f556a  lea     rcx, [rdi+182h]; wchar_t *
0x1800f5571  call    ?GetSystemVolumeDriveLetter@@YAJPEA_W@Z; GetSystemVolumeDriveLetter(wchar_t *)
0x1800f5576  mov     rcx, [rbp+0D48h]; this
0x1800f557d  test    eax, eax
0x1800f557f  jns     loc_1800F53D2
0x1800f5585  mov     r9d, eax; char *
0x1800f5588  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f558f  mov     edx, 1873h; void *
0x1800f5594  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f559a  inc     rsi
0x1800f559d  cmp     [rax+rsi*2], r12w
0x1800f55a2  jnz     short loc_1800F559A
0x1800f55a4  lea     edx, ds:193h[rsi*2]
0x1800f55ab  lea     rcx, [rsp+0E40h+pszDest]
0x1800f55b0  call    ?Init@?$XArray@_W@@QEAAXI@Z; XArray<wchar_t>::Init(uint)
0x1800f55b5  mov     edx, dword ptr [rsp+0E40h+cchDest]; unsigned __int64
0x1800f55b9  mov     [rsp+0E40h+cchToCopy], rbx; int
0x1800f55be  mov     r9, rbx
0x1800f55c1  lea     r8, aOSdA0xc0100000; "O:%sD:(A;;0xC0100000;;;%s)(A;;0xC010000"...
0x1800f55c8  mov     rsi, [rsp+0E40h+pszDest]
0x1800f55cd  mov     rcx, rsi; wchar_t *
0x1800f55d0  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800f55d5  test    eax, eax
0x1800f55d7  js      short loc_1800F55F9
0x1800f55d9  mov     r14, rsi
0x1800f55dc  jmp     loc_1800F54EA
0x1800f55e1  mov     r8d, eax
0x1800f55e4  add     r8, r8; Size
0x1800f55e7  mov     rdx, [rsp+0E40h+Src]; Src
0x1800f55ec  mov     rcx, [rbx]; void *
0x1800f55ef  call    memcpy_0
0x1800f55f4  jmp     loc_1800F534E
0x1800f55f9  mov     rcx, [rbp+0D48h]; this
0x1800f5600  mov     r9d, eax; char *
0x1800f5603  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f560a  mov     edx, 192Bh; void *
0x1800f560f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f5615  mov     rcx, [rbp+0D48h]; this
0x1800f561c  mov     r9d, eax; char *
0x1800f561f  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800f5626  mov     edx, 1941h; void *
0x1800f562b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
