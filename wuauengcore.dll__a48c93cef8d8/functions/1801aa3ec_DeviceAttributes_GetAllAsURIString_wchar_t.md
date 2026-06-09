# DeviceAttributes::GetAllAsURIString(wchar_t * *)

- ea: `0x1801aa3ec`
- end: `0x1801aa6ba`
- name: `?GetAllAsURIString@DeviceAttributes@@AEAAJPEAPEA_W@Z`
- size: `718`
- prototype: `__int64 __fastcall(DeviceAttributes *__hidden this, wchar_t **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801aa084`

## callees

- `0x18000def4`
- `0x180014964`
- `0x18007ac24`
- `0x180110914`
- `0x180113ae8`
- `0x18012b618`
- `0x18012dc08`
- `0x1801aa3ec`
- `0x1801f231c`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aa58f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aa5be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aa58f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aa5be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801aa5a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801aa5d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801aa5a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801aa5d0`
- `OLEAUT32!__imp_SysAllocString` at `0x1801aa63a`
- `OLEAUT32!__imp_SysAllocString` at `0x1801aa657`
- `OLEAUT32!__imp_SysAllocString` at `0x1801aa63a`
- `OLEAUT32!__imp_SysAllocString` at `0x1801aa657`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aa5aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aa5d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aa5aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801aa5d9`

## string_xrefs

- `0x1801aa5f5`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DeviceAttributes::GetAllAsURIString(DeviceAttributes *this, wchar_t **a2)
{
  OLECHAR *v4; // rbx
  int v5; // edi
  __int64 v6; // rdx
  void **v7; // r14
  int v8; // eax
  WUSystemInterfaceHelper *v9; // rcx
  HLOCAL v10; // rsi
  __int64 v11; // r12
  __int64 v12; // rsi
  int WUSystemInterface; // eax
  __int64 v14; // rdx
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // eax
  int v19; // eax
  wchar_t *v20; // rax
  wchar_t *v21; // rax
  int v23; // [rsp+20h] [rbp-50h]
  OLECHAR *psz; // [rsp+30h] [rbp-40h] BYREF
  HLOCAL hMem[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v26; // [rsp+48h] [rbp-28h]
  __int64 v27; // [rsp+50h] [rbp-20h]
  LPVOID pv; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v4 = 0;
  psz = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
    v6 = 235;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\DeviceAttributes\\DeviceAttributes.cpp",
      (const char *)(unsigned int)v5,
      v23);
    goto LABEL_44;
  }
  *a2 = 0;
  v7 = (void **)((char *)this + 80);
  if ( *((_QWORD *)this + 10) )
    goto LABEL_33;
  v27 = 0;
  hMem[0] = 0;
  hMem[1] = 0;
  v26 = 0;
  v8 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::_Concat(hMem, L"E:", 2);
  v5 = v8;
  if ( v8 >= 0 )
  {
    pv = 0;
    v11 = *((_QWORD *)this + 12);
    v12 = *((_QWORD *)this + 11);
    WUSystemInterface = WUSystemInterfaceHelper::LoadWUSystemInterface(v9);
    v5 = WUSystemInterface;
    if ( WUSystemInterface < 0 )
    {
      v14 = 301;
      v15 = (unsigned int)WUSystemInterface;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
        (const char *)v15,
        v23);
      v16 = 251;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\DeviceAttributes\\DeviceAttributes.cpp",
        (const char *)(unsigned int)v5,
        v23);
      v10 = hMem[0];
      goto LABEL_23;
    }
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, LPVOID *))(*(_QWORD *)g_WUSystemInterface + 224LL))(
           g_WUSystemInterface,
           v12,
           v11,
           &pv);
    v15 = (unsigned int)v5;
    if ( v5 < 0 )
    {
      v14 = 303;
      goto LABEL_10;
    }
    if ( pv )
    {
      v17 = -1;
      do
        ++v17;
      while ( *((_WORD *)pv + v17) );
    }
    else
    {
      v17 = 0;
    }
    v5 = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::_Concat(hMem, pv, v17);
    if ( v5 < 0 )
    {
      v16 = 253;
      goto LABEL_18;
    }
    if ( *v7 )
    {
      SusFree(*v7);
      *v7 = 0;
    }
    v10 = hMem[0];
    v18 = DuplicateString<wchar_t const *,wchar_t *>(hMem[0], v7);
    v5 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFE,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\DeviceAttributes\\DeviceAttributes.cpp",
        (const char *)(unsigned int)v18,
        v23);
LABEL_23:
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      goto LABEL_25;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    if ( v10 )
      LocalFree(v10);
    WindowsDeleteString(0);
LABEL_33:
    if ( (unsigned int)AreTestKeysAllowed(1)
      && (v19 = RegQueryStringValue(
                  -2147483646,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                  L"DeviceAttributes",
                  &psz),
          v4 = psz,
          v19 >= 0)
      && psz )
    {
      WUTrace(0, 0, 8, 4, 0, L"Test override for device attributes enabled.");
      v20 = SysAllocString(v4);
      *a2 = v20;
      if ( !v20 )
      {
        v6 = 268;
LABEL_41:
        v5 = -2147024882;
        goto LABEL_42;
      }
    }
    else if ( *v7 )
    {
      v21 = SysAllocString((const OLECHAR *)*v7);
      *a2 = v21;
      if ( !v21 )
      {
        v6 = 277;
        goto LABEL_41;
      }
    }
    v5 = 0;
    goto LABEL_44;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF4,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\DeviceAttributes\\DeviceAttributes.cpp",
    (const char *)(unsigned int)v8,
    v23);
  v10 = hMem[0];
LABEL_25:
  if ( v10 )
    LocalFree(v10);
  WindowsDeleteString(0);
LABEL_44:
  if ( v4 )
    SusFree(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1801aa3ec  mov     [rsp-38h+arg_10], rbx
0x1801aa3f1  push    rbp
0x1801aa3f2  push    rsi
0x1801aa3f3  push    rdi
0x1801aa3f4  push    r12
0x1801aa3f6  push    r13
0x1801aa3f8  push    r14
0x1801aa3fa  push    r15
0x1801aa3fc  mov     rbp, rsp
0x1801aa3ff  sub     rsp, 70h
0x1801aa403  mov     rax, cs:__security_cookie
0x1801aa40a  xor     rax, rsp
0x1801aa40d  mov     [rbp+var_10], rax
0x1801aa411  mov     r15, rdx
0x1801aa414  mov     rsi, rcx
0x1801aa417  xor     r13d, r13d
0x1801aa41a  mov     ebx, r13d
0x1801aa41d  mov     [rbp+psz], rbx
0x1801aa421  test    rdx, rdx
0x1801aa424  jnz     short loc_1801AA435
0x1801aa426  mov     edi, 80004003h
0x1801aa42b  mov     edx, 0EBh
0x1801aa430  jmp     loc_1801AA66F
0x1801aa435  mov     [rdx], r13
0x1801aa438  lea     r14, [rcx+50h]
0x1801aa43c  cmp     [r14], r13
0x1801aa43f  jnz     loc_1801AA5DF
0x1801aa445  mov     [rbp+var_20], r13
0x1801aa449  xorps   xmm0, xmm0
0x1801aa44c  movups  xmmword ptr [rbp+hMem], xmm0
0x1801aa450  mov     [rbp+hMem], r13
0x1801aa454  mov     [rbp+hMem+8], r13
0x1801aa458  mov     [rbp+var_28], r13
0x1801aa45c  mov     r8d, 2
0x1801aa462  lea     rdx, aE_0; "E:"
0x1801aa469  lea     rcx, [rbp+hMem]
0x1801aa46d  call    ?_Concat@?$NativeString@V?$LocalMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAJPEB_W_K@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::_Concat(wchar_t const *,unsigned __int64)
0x1801aa472  mov     edi, eax
0x1801aa474  test    eax, eax
0x1801aa476  jns     short loc_1801AA499
0x1801aa478  mov     rcx, [rbp+38h]; this
0x1801aa47c  mov     r9d, eax; char *
0x1801aa47f  lea     r8, aCW1SSrcClientE_123; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1801aa486  mov     edx, 0F4h; void *
0x1801aa48b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801aa490  mov     rsi, [rbp+hMem]
0x1801aa494  jmp     loc_1801AA599
0x1801aa499  mov     [rbp+pv], r13
0x1801aa49d  mov     r12, [rsi+60h]
0x1801aa4a1  mov     rsi, [rsi+58h]
0x1801aa4a5  call    ?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ; WUSystemInterfaceHelper::LoadWUSystemInterface(void)
0x1801aa4aa  mov     edi, eax
0x1801aa4ac  test    eax, eax
0x1801aa4ae  jns     short loc_1801AA4BA
0x1801aa4b0  mov     edx, 12Dh
0x1801aa4b5  mov     r9d, eax
0x1801aa4b8  jmp     short loc_1801AA4E8
0x1801aa4ba  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x1801aa4c1  mov     rax, [rcx]
0x1801aa4c4  lea     r9, [rbp+pv]
0x1801aa4c8  mov     r8, r12
0x1801aa4cb  mov     rdx, rsi
0x1801aa4ce  mov     rax, [rax+0E0h]
0x1801aa4d5  call    _guard_dispatch_icall
0x1801aa4da  mov     edi, eax
0x1801aa4dc  mov     r9d, eax; char *
0x1801aa4df  test    eax, eax
0x1801aa4e1  jns     short loc_1801AA4FF
0x1801aa4e3  mov     edx, 12Fh; void *
0x1801aa4e8  lea     r8, aCW1SSrcClientL_30; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x1801aa4ef  mov     rcx, [rbp+38h]; this
0x1801aa4f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801aa4f8  mov     edx, 0FBh
0x1801aa4fd  jmp     short loc_1801AA52F
0x1801aa4ff  mov     rdx, [rbp+pv]
0x1801aa503  test    rdx, rdx
0x1801aa506  jz      short loc_1801AA518
0x1801aa508  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801aa50c  inc     r8
0x1801aa50f  cmp     [rdx+r8*2], r13w
0x1801aa514  jnz     short loc_1801AA50C
0x1801aa516  jmp     short loc_1801AA51B
0x1801aa518  mov     r8, r13
0x1801aa51b  lea     rcx, [rbp+hMem]
0x1801aa51f  call    ?_Concat@?$NativeString@V?$LocalMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAJPEB_W_K@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::_Concat(wchar_t const *,unsigned __int64)
0x1801aa524  mov     edi, eax
0x1801aa526  test    eax, eax
0x1801aa528  jns     short loc_1801AA548
0x1801aa52a  mov     edx, 0FDh; void *
0x1801aa52f  mov     rcx, [rbp+38h]; this
0x1801aa533  mov     r9d, edi; char *
0x1801aa536  lea     r8, aCW1SSrcClientE_123; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1801aa53d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801aa542  mov     rsi, [rbp+hMem]
0x1801aa546  jmp     short loc_1801AA586
0x1801aa548  mov     rcx, [r14]; lpMem
0x1801aa54b  test    rcx, rcx
0x1801aa54e  jz      short loc_1801AA558
0x1801aa550  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1801aa555  mov     [r14], r13
0x1801aa558  mov     rdx, r14
0x1801aa55b  mov     rsi, [rbp+hMem]
0x1801aa55f  mov     rcx, rsi
0x1801aa562  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x1801aa567  mov     edi, eax
0x1801aa569  test    eax, eax
0x1801aa56b  jns     short loc_1801AA5B5
0x1801aa56d  mov     rcx, [rbp+38h]; this
0x1801aa571  mov     r9d, eax; char *
0x1801aa574  lea     r8, aCW1SSrcClientE_123; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1801aa57b  mov     edx, 0FEh; void *
0x1801aa580  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801aa585  nop
0x1801aa586  mov     rcx, [rbp+pv]; pv
0x1801aa58a  test    rcx, rcx
0x1801aa58d  jz      short loc_1801AA599
0x1801aa58f  call    cs:__imp_CoTaskMemFree
0x1801aa595  mov     [rbp+pv], r13
0x1801aa599  test    rsi, rsi
0x1801aa59c  jz      short loc_1801AA5A8
0x1801aa59e  mov     rcx, rsi; hMem
0x1801aa5a1  call    cs:__imp_LocalFree
0x1801aa5a7  nop
0x1801aa5a8  xor     ecx, ecx; string
0x1801aa5aa  call    cs:__imp_WindowsDeleteString
0x1801aa5b0  jmp     loc_1801AA687
0x1801aa5b5  mov     rcx, [rbp+pv]; pv
0x1801aa5b9  test    rcx, rcx
0x1801aa5bc  jz      short loc_1801AA5C8
0x1801aa5be  call    cs:__imp_CoTaskMemFree
0x1801aa5c4  mov     [rbp+pv], r13
0x1801aa5c8  test    rsi, rsi
0x1801aa5cb  jz      short loc_1801AA5D7
0x1801aa5cd  mov     rcx, rsi; hMem
0x1801aa5d0  call    cs:__imp_LocalFree
0x1801aa5d6  nop
0x1801aa5d7  xor     ecx, ecx; string
0x1801aa5d9  call    cs:__imp_WindowsDeleteString
0x1801aa5df  mov     cl, 1; bool
0x1801aa5e1  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x1801aa5e6  test    eax, eax
0x1801aa5e8  jz      short loc_1801AA64F
0x1801aa5ea  lea     r9, [rbp+psz]
0x1801aa5ee  lea     r8, aDeviceattribut; "DeviceAttributes"
0x1801aa5f5  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801aa5fc  mov     rcx, 0FFFFFFFF80000002h
0x1801aa603  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEAPEA_WW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,RegistryHiveType)
0x1801aa608  mov     rbx, [rbp+psz]
0x1801aa60c  test    eax, eax
0x1801aa60e  js      short loc_1801AA64F
0x1801aa610  test    rbx, rbx
0x1801aa613  jz      short loc_1801AA64F
0x1801aa615  lea     rax, aTestOverrideFo_1; "Test override for device attributes ena"...
0x1801aa61c  mov     [rsp+70h+var_48], rax
0x1801aa621  mov     [rsp+70h+var_50], r13
0x1801aa626  xor     edx, edx
0x1801aa628  xor     ecx, ecx
0x1801aa62a  lea     r9d, [rdx+4]
0x1801aa62e  lea     r8d, [rdx+8]
0x1801aa632  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801aa637  mov     rcx, rbx; psz
0x1801aa63a  call    cs:__imp_SysAllocString
0x1801aa640  mov     [r15], rax
0x1801aa643  test    rax, rax
0x1801aa646  jnz     short loc_1801AA684
0x1801aa648  mov     edx, 10Ch
0x1801aa64d  jmp     short loc_1801AA66A
0x1801aa64f  mov     rcx, [r14]; psz
0x1801aa652  test    rcx, rcx
0x1801aa655  jz      short loc_1801AA684
0x1801aa657  call    cs:__imp_SysAllocString
0x1801aa65d  mov     [r15], rax
0x1801aa660  test    rax, rax
0x1801aa663  jnz     short loc_1801AA684
0x1801aa665  mov     edx, 115h; void *
0x1801aa66a  mov     edi, 8007000Eh
0x1801aa66f  mov     rcx, [rbp+38h]; this
0x1801aa673  lea     r8, aCW1SSrcClientE_123; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1801aa67a  mov     r9d, edi; char *
0x1801aa67d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801aa682  jmp     short loc_1801AA687
0x1801aa684  mov     edi, r13d
0x1801aa687  test    rbx, rbx
0x1801aa68a  jz      short loc_1801AA694
0x1801aa68c  mov     rcx, rbx; lpMem
0x1801aa68f  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1801aa694  mov     eax, edi
0x1801aa696  mov     rcx, [rbp+var_10]
0x1801aa69a  xor     rcx, rsp; StackCookie
0x1801aa69d  call    __security_check_cookie
0x1801aa6a2  mov     rbx, [rsp+70h+arg_10]
0x1801aa6aa  add     rsp, 70h
0x1801aa6ae  pop     r15
0x1801aa6b0  pop     r14
0x1801aa6b2  pop     r13
0x1801aa6b4  pop     r12
0x1801aa6b6  pop     rdi
0x1801aa6b7  pop     rsi
0x1801aa6b8  pop     rbp
0x1801aa6b9  retn
```
