# RegWow64Helpers::DeleteTree(HKEY__ * const,ushort const * const)

- ea: `0x1800272bc`
- end: `0x18002750c`
- name: `?DeleteTree@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG@Z`
- size: `592`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026b20`
- `0x1800272bc`
- `0x18002a30c`
- `0x18002a36c`
- `0x180056e11`

## callees

- `0x180009e38`
- `0x18000a230`
- `0x18000e5ac`
- `0x18001a718`
- `0x1800272bc`
- `0x180029c94`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002732b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800273e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002732b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800273e6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180027467`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180027467`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180027441`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180027441`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180027386`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180027386`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800274a2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800274a2`

## string_xrefs

- `0x180027349`: `onecore\base\flighting\common\inc\RegWow64Helpers.h`
- `0x180027404`: `onecore\base\flighting\common\inc\RegWow64Helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall RegWow64Helpers::DeleteTree(HKEY a1, const unsigned __int16 *a2)
{
  unsigned int v4; // r8d
  signed int v5; // ebx
  char v6; // r12
  HKEY v7; // r14
  WCHAR *v8; // rbx
  LSTATUS v9; // eax
  signed int v10; // edi
  int v11; // edi
  WCHAR *v13; // rbx
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  int lpReserved; // [rsp+20h] [rbp-38h]
  int lpReserveda; // [rsp+20h] [rbp-38h]
  _QWORD v19[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  DWORD cchName; // [rsp+A0h] [rbp+48h] BYREF
  DWORD cchValueName; // [rsp+A8h] [rbp+50h] BYREF
  WCHAR *v23; // [rsp+B0h] [rbp+58h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+60h] BYREF

  hKey = 0;
  if ( a2 && *a2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v5 = RegWow64Helpers::OpenKey(a1, a2, v4, 0xF003Fu, &hKey);
    if ( v5 < 0 )
    {
LABEL_31:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return (unsigned int)v5;
    }
    v6 = 1;
    v7 = hKey;
  }
  else
  {
    v7 = a1;
    v6 = 0;
  }
  v8 = (WCHAR *)CoTaskMemAlloc(0x200u);
  v23 = v8;
  if ( !v8 )
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\RegWow64Helpers.h",
      (const char *)0x8007000ELL,
      lpReserved);
LABEL_30:
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v23);
    goto LABEL_31;
  }
  while ( 1 )
  {
    cchName = 256;
    v9 = RegEnumKeyExW(v7, 0, v8, &cchName, 0, 0, 0, 0);
    v10 = v9;
    if ( v9 == 259 )
      break;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    if ( v10 < 0 )
    {
LABEL_14:
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v23);
      v5 = v10;
      goto LABEL_31;
    }
    v11 = RegWow64Helpers::DeleteTree(v7, v8);
    if ( v11 < 0 )
    {
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v23);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return (unsigned int)v11;
    }
  }
  v13 = (WCHAR *)CoTaskMemAlloc(0x7FFFu);
  v19[0] = v13;
  if ( !v13 )
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\RegWow64Helpers.h",
      (const char *)0x8007000ELL,
      lpReserveda);
LABEL_29:
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(v19);
    goto LABEL_30;
  }
  while ( 1 )
  {
    cchValueName = 0x3FFF;
    v14 = RegEnumValueW(v7, 0, v13, &cchValueName, 0, 0, 0, 0);
    v10 = v14;
    if ( v14 == 259 )
      break;
    if ( v14 > 0 )
      v10 = (unsigned __int16)v14 | 0x80070000;
    if ( v10 >= 0 )
    {
      v15 = RegDeleteValueW(v7, v13);
      v10 = v15;
      if ( v15 > 0 )
        v10 = (unsigned __int16)v15 | 0x80070000;
      if ( v10 >= 0 )
        continue;
    }
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(v19);
    goto LABEL_14;
  }
  if ( v6 )
  {
    v16 = RegDeleteKeyExW(a1, a2, 0x100u, 0);
    v5 = v16;
    if ( v16 > 0 )
      v5 = (unsigned __int16)v16 | 0x80070000;
    if ( v5 < 0 )
      goto LABEL_29;
  }
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(v19);
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v23);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x1800272bc  push    rbp
0x1800272be  push    rbx
0x1800272bf  push    rsi
0x1800272c0  push    rdi
0x1800272c1  push    r12
0x1800272c3  push    r13
0x1800272c5  push    r14
0x1800272c7  push    r15
0x1800272c9  mov     rbp, rsp
0x1800272cc  sub     rsp, 58h
0x1800272d0  mov     rsi, rdx
0x1800272d3  mov     r15, rcx
0x1800272d6  xor     r13d, r13d
0x1800272d9  mov     [rbp+hKey], r13
0x1800272dd  test    rdx, rdx
0x1800272e0  jz      short loc_180027320
0x1800272e2  cmp     [rdx], r13w
0x1800272e6  jz      short loc_180027320
0x1800272e8  xor     edx, edx
0x1800272ea  lea     rcx, [rbp+hKey]
0x1800272ee  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800272f3  lea     rax, [rbp+hKey]
0x1800272f7  mov     [rsp+58h+lpReserved], rax; PHKEY
0x1800272fc  mov     r9d, 0F003Fh; unsigned int
0x180027302  mov     rdx, rsi; unsigned __int16 *
0x180027305  mov     rcx, r15; HKEY
0x180027308  call    ?OpenKey@RegWow64Helpers@@SAJQEAUHKEY__@@QEBGKKPEAPEAU2@@Z; RegWow64Helpers::OpenKey(HKEY__ * const,ushort const * const,ulong,ulong,HKEY__ * *)
0x18002730d  mov     ebx, eax
0x18002730f  test    eax, eax
0x180027311  js      loc_1800274CF
0x180027317  mov     r12b, 1
0x18002731a  mov     r14, [rbp+hKey]
0x18002731e  jmp     short loc_180027326
0x180027320  mov     r14, r15
0x180027323  mov     r12b, r13b
0x180027326  mov     ecx, 200h; cb
0x18002732b  call    cs:__imp_CoTaskMemAlloc
0x180027331  mov     rbx, rax
0x180027334  mov     [rbp+arg_10], rax
0x180027338  test    rax, rax
0x18002733b  jnz     short loc_18002735F
0x18002733d  mov     rcx, [rbp+40h]; this
0x180027341  mov     ebx, 8007000Eh
0x180027346  mov     r9d, ebx; char *
0x180027349  lea     r8, aOnecoreBaseFli_11; "onecore\\base\\flighting\\common\\inc\\"...
0x180027350  mov     edx, 232h; void *
0x180027355  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002735a  jmp     loc_1800274C5
0x18002735f  mov     [rbp+cchName], 100h
0x180027366  mov     [rsp+58h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18002736b  mov     [rsp+58h+lpcchClass], r13; lpcchClass
0x180027370  mov     [rsp+58h+lpClass], r13; lpClass
0x180027375  mov     [rsp+58h+lpReserved], r13; int
0x18002737a  lea     r9, [rbp+cchName]; lpcchName
0x18002737e  mov     r8, rbx; lpName
0x180027381  xor     edx, edx; dwIndex
0x180027383  mov     rcx, r14; hKey
0x180027386  call    cs:__imp_RegEnumKeyExW
0x18002738c  mov     edi, eax
0x18002738e  cmp     eax, 103h
0x180027393  jz      short loc_1800273E1
0x180027395  test    eax, eax
0x180027397  jle     short loc_1800273A2
0x180027399  movzx   edi, ax
0x18002739c  or      edi, 80070000h
0x1800273a2  test    edi, edi
0x1800273a4  js      short loc_1800273D1
0x1800273a6  mov     rdx, rbx; unsigned __int16 *
0x1800273a9  mov     rcx, r14; HKEY
0x1800273ac  call    ?DeleteTree@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG@Z; RegWow64Helpers::DeleteTree(HKEY__ * const,ushort const * const)
0x1800273b1  mov     edi, eax
0x1800273b3  test    eax, eax
0x1800273b5  jns     short loc_18002735F
0x1800273b7  lea     rcx, [rbp+arg_10]
0x1800273bb  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800273c0  nop
0x1800273c1  lea     rcx, [rbp+hKey]
0x1800273c5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800273ca  mov     eax, edi
0x1800273cc  jmp     loc_1800274FB
0x1800273d1  lea     rcx, [rbp+arg_10]
0x1800273d5  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800273da  mov     ebx, edi
0x1800273dc  jmp     loc_1800274CF
0x1800273e1  mov     ecx, 7FFFh; cb
0x1800273e6  call    cs:__imp_CoTaskMemAlloc
0x1800273ec  mov     rbx, rax
0x1800273ef  mov     [rbp+var_18], rax
0x1800273f3  test    rax, rax
0x1800273f6  jnz     short loc_18002741A
0x1800273f8  mov     rcx, [rbp+40h]; this
0x1800273fc  mov     ebx, 8007000Eh
0x180027401  mov     r9d, ebx; char *
0x180027404  lea     r8, aOnecoreBaseFli_11; "onecore\\base\\flighting\\common\\inc\\"...
0x18002740b  mov     edx, 255h; void *
0x180027410  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027415  jmp     loc_1800274BB
0x18002741a  mov     [rbp+cchValueName], 3FFFh
0x180027421  mov     [rsp+58h+lpftLastWriteTime], r13; lpcbData
0x180027426  mov     [rsp+58h+lpcchClass], r13; lpData
0x18002742b  mov     [rsp+58h+lpClass], r13; lpType
0x180027430  mov     [rsp+58h+lpReserved], r13; lpReserved
0x180027435  lea     r9, [rbp+cchValueName]; lpcchValueName
0x180027439  mov     r8, rbx; lpValueName
0x18002743c  xor     edx, edx; dwIndex
0x18002743e  mov     rcx, r14; hKey
0x180027441  call    cs:__imp_RegEnumValueW
0x180027447  mov     edi, eax
0x180027449  cmp     eax, 103h
0x18002744e  jz      short loc_18002748E
0x180027450  test    eax, eax
0x180027452  jle     short loc_18002745D
0x180027454  movzx   edi, ax
0x180027457  or      edi, 80070000h
0x18002745d  test    edi, edi
0x18002745f  js      short loc_180027480
0x180027461  mov     rdx, rbx; lpValueName
0x180027464  mov     rcx, r14; hKey
0x180027467  call    cs:__imp_RegDeleteValueW
0x18002746d  mov     edi, eax
0x18002746f  test    eax, eax
0x180027471  jle     short loc_18002747C
0x180027473  movzx   edi, ax
0x180027476  or      edi, 80070000h
0x18002747c  test    edi, edi
0x18002747e  jns     short loc_18002741A
0x180027480  lea     rcx, [rbp+var_18]
0x180027484  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180027489  jmp     loc_1800273D1
0x18002748e  test    r12b, r12b
0x180027491  jz      short loc_1800274DC
0x180027493  xor     r9d, r9d; Reserved
0x180027496  mov     r8d, 100h; samDesired
0x18002749c  mov     rdx, rsi; lpSubKey
0x18002749f  mov     rcx, r15; hKey
0x1800274a2  call    cs:__imp_RegDeleteKeyExW
0x1800274a8  mov     ebx, eax
0x1800274aa  test    eax, eax
0x1800274ac  jle     short loc_1800274B7
0x1800274ae  movzx   ebx, ax
0x1800274b1  or      ebx, 80070000h
0x1800274b7  test    ebx, ebx
0x1800274b9  jns     short loc_1800274DC
0x1800274bb  lea     rcx, [rbp+var_18]
0x1800274bf  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800274c4  nop
0x1800274c5  lea     rcx, [rbp+arg_10]
0x1800274c9  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800274ce  nop
0x1800274cf  lea     rcx, [rbp+hKey]
0x1800274d3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800274d8  mov     eax, ebx
0x1800274da  jmp     short loc_1800274FB
0x1800274dc  lea     rcx, [rbp+var_18]
0x1800274e0  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800274e5  nop
0x1800274e6  lea     rcx, [rbp+arg_10]
0x1800274ea  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800274ef  nop
0x1800274f0  lea     rcx, [rbp+hKey]
0x1800274f4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800274f9  xor     eax, eax
0x1800274fb  add     rsp, 58h
0x1800274ff  pop     r15
0x180027501  pop     r14
0x180027503  pop     r13
0x180027505  pop     r12
0x180027507  pop     rdi
0x180027508  pop     rsi
0x180027509  pop     rbx
0x18002750a  pop     rbp
0x18002750b  retn
```
