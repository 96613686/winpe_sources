# XmlDocFromResource(uint,IXMLDOMDocument2 * *)

- ea: `0x1800043d0`
- end: `0x18000485f`
- name: `?XmlDocFromResource@@YAXIPEAPEAUIXMLDOMDocument2@@@Z`
- size: `1167`
- prototype: `void __fastcall(unsigned int, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003990`

## callees

- `0x1800043d0`
- `0x180004868`
- `0x1800180cc`
- `0x18001b848`
- `0x18001bb3c`
- `0x18001bb6c`
- `0x18001cba4`
- `0x18001ff00`
- `0x180020d34`
- `0x180025550`
- `0x180025700`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800044ad`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800044ad`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180004495`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180004495`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800044c4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800044c4`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800044d6`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800044d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000446c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000446c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004562`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800045bd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004562`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800045bd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004429`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004429`
- `OLEAUT32!__imp_SysAllocString` at `0x1800045cf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800045cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000464f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000464f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall XmlDocFromResource(unsigned __int16 a1, struct IXMLDOMDocument2 **a2)
{
  HRESULT v4; // eax
  _BYTE *v5; // rdi
  int v6; // ebx
  HMODULE v7; // rsi
  HRSRC Resource; // rax
  HRSRC v9; // r14
  DWORD v10; // r15d
  HGLOBAL v11; // rax
  _BYTE *v12; // rax
  signed int ErrorError; // eax
  char v14; // al
  CHAR *v15; // rdi
  int v16; // eax
  int cchWideChar; // esi
  char *v18; // r14
  unsigned __int64 v19; // rcx
  WCHAR *v20; // rax
  OLECHAR *v21; // rbx
  int v22; // eax
  int v23; // eax
  struct IXMLDOMDocument2 *v24; // rax
  LPVOID v25; // rcx
  size_t v26; // rbx
  int ppv; // [rsp+20h] [rbp-49h]
  int ppva; // [rsp+20h] [rbp-49h]
  int ppvb; // [rsp+20h] [rbp-49h]
  __int16 v30; // [rsp+30h] [rbp-39h] BYREF
  LPVOID v31; // [rsp+38h] [rbp-31h] BYREF
  HMODULE phModule; // [rsp+40h] [rbp-29h] BYREF
  LPWSTR lpWideCharStr; // [rsp+48h] [rbp-21h] BYREF
  void *v34; // [rsp+50h] [rbp-19h]
  __int64 v35; // [rsp+58h] [rbp-11h]
  CHAR MultiByteStr[16]; // [rsp+60h] [rbp-9h] BYREF
  __m128i si128; // [rsp+70h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a2 = 0;
  v31 = 0;
  v4 = CoCreateInstance(
         &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
         0,
         1u,
         &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
         &v31);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  *(_OWORD *)MultiByteStr = 0;
  si128 = 0;
  std::string::_Construct_empty(MultiByteStr);
  phModule = 0;
  if ( !GetModuleHandleExW(6u, (LPCWSTR)XmlDocFromResource, &phModule) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)0x8000FFFFLL,
      ppv);
  v5 = 0;
  v6 = 0;
  v7 = phModule;
  Resource = FindResourceExW(phModule, L"XML", (LPCWSTR)a1, 0);
  v9 = Resource;
  if ( Resource )
  {
    v10 = SizeofResource(v7, Resource);
    if ( v10 && (v11 = LoadResource(v7, v9)) != 0 && (v12 = LockResource(v11)) != 0 )
    {
      v5 = v12;
      v6 = v10;
      ErrorError = 0;
    }
    else
    {
      ErrorError = HRESULTFromLastErrorError();
    }
  }
  else if ( (int)GetLastErrorError() > 0 )
  {
    ErrorError = (unsigned __int16)GetLastErrorError() | 0x80070000;
  }
  else
  {
    ErrorError = GetLastErrorError();
  }
  if ( ErrorError < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)ErrorError,
      ppv);
  if ( v6 > 3 )
  {
    if ( *v5 != 0xEF || v5[1] != 0xBB || v5[2] != 0xBF )
      goto LABEL_11;
    v5 += 3;
    v6 -= 3;
  }
  if ( v6 > 0 )
  {
LABEL_11:
    v14 = 1;
    goto LABEL_12;
  }
  v14 = 0;
LABEL_12:
  if ( !v14 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)0x8000FFFFLL,
      ppv);
  std::string::assign(MultiByteStr, v5, v6);
  if ( si128.m128i_i64[1] > 0xFuLL )
    v15 = *(CHAR **)MultiByteStr;
  else
    v15 = MultiByteStr;
  std::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>(&lpWideCharStr);
  v16 = MultiByteToWideChar(0xFDE9u, 8u, v15, -1, 0, 0);
  cchWideChar = v16;
  if ( v16 <= 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)0x8000FFFFLL,
      ppva);
  v18 = (char *)v34;
  v19 = ((_BYTE *)v34 - (_BYTE *)lpWideCharStr) >> 1;
  if ( v16 < v19 )
  {
    v20 = &lpWideCharStr[v16];
LABEL_18:
    v34 = v20;
    goto LABEL_19;
  }
  if ( v16 > v19 )
  {
    if ( v16 <= (unsigned __int64)((v35 - (__int64)lpWideCharStr) >> 1) )
    {
      v26 = 2 * (v16 - v19);
      memset_0(v34, 0, v26);
      v20 = (WCHAR *)&v18[v26];
      goto LABEL_18;
    }
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&lpWideCharStr, v16);
  }
LABEL_19:
  if ( MultiByteToWideChar(0xFDE9u, 8u, v15, -1, lpWideCharStr, cchWideChar) <= 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x237,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)0x8000FFFFLL,
      ppvb);
  v21 = SysAllocString(lpWideCharStr);
  if ( lpWideCharStr )
    std::_Deallocate<16>(lpWideCharStr, 2 * ((v35 - (__int64)lpWideCharStr) >> 1));
  phModule = (HMODULE)v21;
  v22 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v31 + 504LL))(v31, 0);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v22,
      ppvb);
  v30 = 0;
  v23 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int16 *))(*(_QWORD *)v31 + 520LL))(v31, v21, &v30);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v23,
      ppvb);
  if ( v30 != -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)0x8007000DLL,
      ppvb);
  v24 = (struct IXMLDOMDocument2 *)v31;
  v31 = 0;
  *a2 = v24;
  SysFreeString(v21);
  if ( si128.m128i_i64[1] > 0xFuLL )
    std::_Deallocate<16>(*(_QWORD *)MultiByteStr, si128.m128i_i64[1] + 1);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  MultiByteStr[0] = 0;
  v25 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 16LL))(v25);
  }
}

```

## disassembly

```asm
0x1800043d0  mov     [rsp-8+arg_10], rbx
0x1800043d5  push    rbp
0x1800043d6  push    rsi
0x1800043d7  push    rdi
0x1800043d8  push    r12
0x1800043da  push    r13
0x1800043dc  push    r14
0x1800043de  push    r15
0x1800043e0  lea     rbp, [rsp-27h]
0x1800043e5  sub     rsp, 90h
0x1800043ec  mov     rax, cs:__security_cookie
0x1800043f3  xor     rax, rsp
0x1800043f6  mov     [rbp+57h+var_40], rax
0x1800043fa  mov     r12, rdx
0x1800043fd  mov     r14d, ecx
0x180004400  xor     r13d, r13d
0x180004403  mov     [rdx], r13
0x180004406  mov     [rbp+57h+var_88], r13
0x18000440a  lea     rax, [rbp+57h+var_88]
0x18000440e  mov     [rsp+0C0h+ppv], rax; int
0x180004413  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18000441a  xor     edx, edx; pUnkOuter
0x18000441c  mov     r8d, 1; dwClsContext
0x180004422  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180004429  call    cs:__imp_CoCreateInstance
0x18000442f  mov     rcx, [rbp+5Fh]; this
0x180004433  test    eax, eax
0x180004435  js      loc_180004711
0x18000443b  xorps   xmm0, xmm0
0x18000443e  movups  xmmword ptr [rbp+57h+MultiByteStr], xmm0
0x180004442  xorps   xmm1, xmm1
0x180004445  movdqu  [rbp+57h+var_50], xmm1
0x18000444a  lea     rcx, [rbp+57h+MultiByteStr]
0x18000444e  call    ?_Construct_empty@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Construct_empty(void)
0x180004453  nop
0x180004454  mov     [rbp+57h+phModule], r13
0x180004458  mov     rbx, [rbp+5Fh]
0x18000445c  lea     r8, [rbp+57h+phModule]; phModule
0x180004460  lea     rdx, ?XmlDocFromResource@@YAXIPEAPEAUIXMLDOMDocument2@@@Z; lpModuleName
0x180004467  mov     ecx, 6; dwFlags
0x18000446c  call    cs:__imp_GetModuleHandleExW
0x180004472  test    eax, eax
0x180004474  jz      loc_180004726
0x18000447a  mov     edi, r13d
0x18000447d  mov     ebx, r13d
0x180004480  mov     rsi, [rbp+57h+phModule]
0x180004484  xor     r9d, r9d; wLanguage
0x180004487  movzx   r8d, r14w; lpName
0x18000448b  lea     rdx, Type; "XML"
0x180004492  mov     rcx, rsi; hModule
0x180004495  call    cs:__imp_FindResourceExW
0x18000449b  mov     r14, rax
0x18000449e  test    rax, rax
0x1800044a1  jz      loc_1800046B6
0x1800044a7  mov     rdx, rax; hResInfo
0x1800044aa  mov     rcx, rsi; hModule
0x1800044ad  call    cs:__imp_SizeofResource
0x1800044b3  mov     r15d, eax
0x1800044b6  test    eax, eax
0x1800044b8  jz      loc_1800046CA
0x1800044be  mov     rdx, r14; hResInfo
0x1800044c1  mov     rcx, rsi; hModule
0x1800044c4  call    cs:__imp_LoadResource
0x1800044ca  test    rax, rax
0x1800044cd  jz      loc_1800046CA
0x1800044d3  mov     rcx, rax; hResData
0x1800044d6  call    cs:__imp_LockResource
0x1800044dc  test    rax, rax
0x1800044df  jz      loc_1800046CA
0x1800044e5  mov     rdi, rax
0x1800044e8  mov     ebx, r15d
0x1800044eb  mov     eax, r13d
0x1800044ee  mov     rcx, [rbp+5Fh]; this
0x1800044f2  test    eax, eax
0x1800044f4  js      loc_180004741
0x1800044fa  cmp     ebx, 3
0x1800044fd  jle     loc_1800046D4
0x180004503  cmp     byte ptr [rdi], 0EFh
0x180004506  jz      loc_180004756
0x18000450c  mov     al, 1
0x18000450e  mov     rcx, [rbp+5Fh]; this
0x180004512  test    al, al
0x180004514  jz      loc_180004776
0x18000451a  movsxd  r8, ebx
0x18000451d  mov     rdx, rdi
0x180004520  lea     rcx, [rbp+57h+MultiByteStr]
0x180004524  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x180004529  cmp     qword ptr [rbp+57h+var_50+8], 0Fh
0x18000452e  ja      loc_18000478E
0x180004534  lea     rdi, [rbp+57h+MultiByteStr]
0x180004538  lea     rcx, [rbp+57h+lpWideCharStr]
0x18000453c  call    ??0?$vector@UAppInfoRecord@CAppInfoAggregator@Notifications@Internal@Windows@@V?$allocator@UAppInfoRecord@CAppInfoAggregator@Notifications@Internal@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>::vector<Windows::Internal::Notifications::CAppInfoAggregator::AppInfoRecord>(void)
0x180004541  nop
0x180004542  mov     [rsp+0C0h+cchWideChar], r13d; cchWideChar
0x180004547  mov     [rsp+0C0h+ppv], r13; int
0x18000454c  mov     r15d, 0FFFFFFFFh
0x180004552  mov     r9d, r15d; cbMultiByte
0x180004555  mov     r8, rdi; lpMultiByteStr
0x180004558  mov     edx, 8; dwFlags
0x18000455d  mov     ecx, 0FDE9h; CodePage
0x180004562  call    cs:__imp_MultiByteToWideChar
0x180004568  movsxd  rsi, eax
0x18000456b  mov     rcx, [rbp+5Fh]; this
0x18000456f  test    eax, eax
0x180004571  jle     loc_180004797
0x180004577  mov     rdx, [rbp+57h+lpWideCharStr]
0x18000457b  mov     r14, [rbp+57h+var_70]
0x18000457f  mov     rcx, r14
0x180004582  sub     rcx, rdx
0x180004585  sar     rcx, 1
0x180004588  mov     rbx, rsi
0x18000458b  cmp     rsi, rcx
0x18000458e  jnb     loc_1800047AF
0x180004594  lea     rax, [rdx+rsi*2]
0x180004598  mov     [rbp+57h+var_70], rax
0x18000459c  mov     rbx, [rbp+5Fh]
0x1800045a0  mov     [rsp+0C0h+cchWideChar], esi; cchWideChar
0x1800045a4  mov     rax, [rbp+57h+lpWideCharStr]
0x1800045a8  mov     [rsp+0C0h+ppv], rax; int
0x1800045ad  mov     r9d, r15d; cbMultiByte
0x1800045b0  mov     r8, rdi; lpMultiByteStr
0x1800045b3  mov     edx, 8; dwFlags
0x1800045b8  mov     ecx, 0FDE9h; CodePage
0x1800045bd  call    cs:__imp_MultiByteToWideChar
0x1800045c3  test    eax, eax
0x1800045c5  jle     loc_1800047F1
0x1800045cb  mov     rcx, [rbp+57h+lpWideCharStr]; psz
0x1800045cf  call    cs:__imp_SysAllocString
0x1800045d5  mov     rbx, rax
0x1800045d8  mov     rcx, [rbp+57h+lpWideCharStr]
0x1800045dc  test    rcx, rcx
0x1800045df  jnz     loc_18000480C
0x1800045e5  mov     [rbp+57h+phModule], rbx
0x1800045e9  mov     rcx, [rbp+57h+var_88]
0x1800045ed  mov     rax, [rcx]
0x1800045f0  xor     edx, edx
0x1800045f2  mov     rax, [rax+1F8h]
0x1800045f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045fe  mov     rcx, [rbp+5Fh]; this
0x180004602  test    eax, eax
0x180004604  js      loc_180004823
0x18000460a  mov     [rbp+57h+var_90], r13w
0x18000460f  mov     rcx, [rbp+57h+var_88]
0x180004613  mov     rax, [rcx]
0x180004616  lea     r8, [rbp+57h+var_90]
0x18000461a  mov     rdx, rbx
0x18000461d  mov     rax, [rax+208h]
0x180004624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004629  mov     rcx, [rbp+5Fh]; this
0x18000462d  test    eax, eax
0x18000462f  js      loc_180004838
0x180004635  cmp     r15w, [rbp+57h+var_90]
0x18000463a  jnz     loc_1800046F5
0x180004640  mov     rax, [rbp+57h+var_88]
0x180004644  mov     [rbp+57h+var_88], r13
0x180004648  mov     [r12], rax
0x18000464c  mov     rcx, rbx; bstrString
0x18000464f  call    cs:__imp_SysFreeString
0x180004655  nop
0x180004656  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x18000465a  cmp     rdx, 0Fh
0x18000465e  ja      loc_18000484D
0x180004664  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18000466c  movdqu  [rbp+57h+var_50], xmm0
0x180004671  mov     [rbp+57h+MultiByteStr], 0
0x180004675  mov     rcx, [rbp+57h+var_88]
0x180004679  test    rcx, rcx
0x18000467c  jz      short loc_18000468F
0x18000467e  mov     [rbp+57h+var_88], r13
0x180004682  mov     rax, [rcx]
0x180004685  mov     rax, [rax+10h]
0x180004689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000468e  nop
0x18000468f  mov     rcx, [rbp+57h+var_40]
0x180004693  xor     rcx, rsp; StackCookie
0x180004696  call    __security_check_cookie
0x18000469b  mov     rbx, [rsp+0C0h+arg_10]
0x1800046a3  add     rsp, 90h
0x1800046aa  pop     r15
0x1800046ac  pop     r14
0x1800046ae  pop     r13
0x1800046b0  pop     r12
0x1800046b2  pop     rdi
0x1800046b3  pop     rsi
0x1800046b4  pop     rbp
0x1800046b5  retn
0x1800046b6  call    ?GetLastErrorError@@YAKXZ; GetLastErrorError(void)
0x1800046bb  nop
0x1800046bc  test    eax, eax
0x1800046be  jg      short loc_1800046E3
0x1800046c0  call    ?GetLastErrorError@@YAKXZ; GetLastErrorError(void)
0x1800046c5  jmp     loc_1800044EE
0x1800046ca  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x1800046cf  jmp     loc_1800044EE
0x1800046d4  test    ebx, ebx
0x1800046d6  jg      loc_18000450C
0x1800046dc  xor     al, al
0x1800046de  jmp     loc_18000450E
0x1800046e3  call    ?GetLastErrorError@@YAKXZ; GetLastErrorError(void)
0x1800046e8  movzx   eax, ax
0x1800046eb  or      eax, 80070000h
0x1800046f0  jmp     loc_1800044EE
0x1800046f5  mov     rcx, [rbp+5Fh]; this
0x1800046f9  mov     r9d, 8007000Dh; char *
0x1800046ff  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180004706  mov     edx, 6Fh ; 'o'; void *
0x18000470b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180004711  mov     r9d, eax; char *
0x180004714  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000471b  mov     edx, 5Bh ; '['; void *
0x180004720  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180004726  mov     r9d, 8000FFFFh; char *
0x18000472c  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180004733  mov     edx, 39h ; '9'; void *
0x180004738  mov     rcx, rbx; this
0x18000473b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180004741  mov     r9d, eax; char *
0x180004744  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000474b  mov     edx, 3Dh ; '='; void *
0x180004750  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180004756  cmp     byte ptr [rdi+1], 0BBh
0x18000475a  jnz     loc_18000450C
0x180004760  cmp     byte ptr [rdi+2], 0BFh
0x180004764  jnz     loc_18000450C
0x18000476a  add     rdi, 3
0x18000476e  add     ebx, 0FFFFFFFDh
0x180004771  jmp     loc_1800046D4
0x180004776  mov     r9d, 8000FFFFh; char *
0x18000477c  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180004783  mov     edx, 49h ; 'I'; void *
0x180004788  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000478e  mov     rdi, qword ptr [rbp+57h+MultiByteStr]
0x180004792  jmp     loc_180004538
0x180004797  mov     r9d, 8000FFFFh; char *
0x18000479d  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800047a4  mov     edx, 22Ch; void *
0x1800047a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800047af  jbe     loc_18000459C
0x1800047b5  mov     rax, [rbp+57h+var_68]
0x1800047b9  sub     rax, rdx
0x1800047bc  sar     rax, 1
0x1800047bf  cmp     rbx, rax
0x1800047c2  jbe     short loc_1800047D5
0x1800047c4  mov     rdx, rbx
0x1800047c7  lea     rcx, [rbp+57h+lpWideCharStr]
0x1800047cb  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800047d0  jmp     loc_18000459C
0x1800047d5  sub     rbx, rcx
0x1800047d8  add     rbx, rbx
0x1800047db  mov     r8, rbx; Size
0x1800047de  xor     edx, edx; Val
0x1800047e0  mov     rcx, r14; void *
0x1800047e3  call    memset_0
0x1800047e8  lea     rax, [rbx+r14]
0x1800047ec  jmp     loc_180004598
0x1800047f1  mov     r9d, 8000FFFFh; char *
0x1800047f7  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800047fe  mov     edx, 237h; void *
0x180004803  mov     rcx, rbx; this
0x180004806  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000480c  mov     rdx, [rbp+57h+var_68]
0x180004810  sub     rdx, rcx
0x180004813  sar     rdx, 1
0x180004816  add     rdx, rdx
0x180004819  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000481e  jmp     loc_1800045E5
0x180004823  mov     r9d, eax; char *
0x180004826  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000482d  mov     edx, 63h ; 'c'; void *
0x180004832  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180004838  mov     r9d, eax; char *
0x18000483b  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180004842  mov     edx, 67h ; 'g'; void *
0x180004847  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000484d  inc     rdx
0x180004850  mov     rcx, qword ptr [rbp+57h+MultiByteStr]
0x180004854  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180004859  jmp     loc_180004664
```
