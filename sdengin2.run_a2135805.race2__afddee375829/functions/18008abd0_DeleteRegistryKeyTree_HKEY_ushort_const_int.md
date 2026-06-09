# DeleteRegistryKeyTree(HKEY__ *,ushort const *,int)

- ea: `0x18008abd0`
- end: `0x18008b043`
- name: `?DeleteRegistryKeyTree@@YAJPEAUHKEY__@@PEBGH@Z`
- size: `1139`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18005cb48`

## callees

- `0x1800083e4`
- `0x180072e08`
- `0x180072f14`
- `0x18008abd0`
- `0x18009dd0c`
- `0x18009e718`
- `0x18009e904`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `msvcrt!wcschr` at `0x18008ac75`
- `msvcrt!wcschr` at `0x18008ac75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ae73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008afd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ae73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008afd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008ad1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008ad1f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008ad70`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008ae60`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008ad70`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008ae60`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008adc3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008adc3`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18008aeec`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18008aeec`
- `ole32!CoTaskMemFree` at `0x18008adf4`
- `ole32!CoTaskMemFree` at `0x18008affa`
- `ole32!CoTaskMemFree` at `0x18008adf4`
- `ole32!CoTaskMemFree` at `0x18008affa`
- `ole32!CoTaskMemAlloc` at `0x18008ae0e`
- `ole32!CoTaskMemAlloc` at `0x18008ae0e`

## string_xrefs

- `0x18008ac00`: `DeleteRegistryKeyTree`

## pseudocode

```c
__int64 __fastcall DeleteRegistryKeyTree(HKEY hKey, const unsigned __int16 *a2)
{
  void *v3; // rsi
  bool v4; // zf
  __int16 v5; // ax
  WCHAR *v6; // r15
  DWORD v7; // r14d
  const WCHAR *v8; // rdi
  int v9; // eax
  int v10; // ebx
  int v11; // eax
  bool v12; // sf
  int v13; // eax
  int v14; // eax
  unsigned int v15; // eax
  __int16 v16; // ax
  unsigned int v17; // ebx
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+78h] [rbp-88h] BYREF
  __int16 v23; // [rsp+7Ch] [rbp-84h]
  __int16 v24; // [rsp+7Eh] [rbp-82h]
  LPCWSTR lpSubKey; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v26; // [rsp+B8h] [rbp-48h]
  WCHAR Name[264]; // [rsp+C0h] [rbp-40h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v22, "DeleteRegistryKeyTree", 0x1E6u, 2u);
  lpSubKey = (LPCWSTR)qword_1800EE510;
  hKeya = 0;
  v26 = 0;
  cbMaxSubKeyLen = 0;
  v3 = 0;
  memset_0(Name, 0, 0x208u);
  cchName = 0;
  if ( !hKey )
  {
    v22 = -2147024809;
    v16 = 499;
LABEL_44:
    v24 = v16;
    goto LABEL_45;
  }
  v22 = 0;
  v23 = 501;
  v4 = wcschr(L"ScheduleParams", 0x5Cu) == 0;
  v5 = 502;
  if ( v4 )
  {
    v22 = 0;
    v23 = 502;
    v22 = CBsString::Set((CBsString *)&lpSubKey, L"ScheduleParams");
    v5 = 504;
    if ( v22 >= 0 )
    {
      v6 = Name;
      v7 = 260;
      do
      {
        v23 = v5;
        v8 = lpSubKey;
        while ( 1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_955fb8e851b1303fac6deb5ef5879a46_Traceguids, v8);
          v9 = RegOpenKeyExW(hKey, v8, 0, 0x2001Fu, &hKeya);
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
          v22 = v9;
          if ( v9 < 0 )
          {
            v24 = 519;
            goto LABEL_41;
          }
          v23 = 519;
          cchName = v7;
          v10 = RegEnumKeyExW(hKeya, 0, v6, &cchName, 0, 0, 0, 0);
          if ( v10 == 234 )
          {
            v11 = RegQueryInfoKeyW(hKeya, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
            if ( v11 > 0 )
              v11 = (unsigned __int16)v11 | 0x80070000;
            v22 = v11;
            v12 = v11 < 0;
            v5 = 529;
            if ( v12 )
              goto LABEL_40;
            v23 = 529;
            CoTaskMemFree(v3);
            v7 = cbMaxSubKeyLen + 1;
            v3 = CoTaskMemAlloc(2LL * (cbMaxSubKeyLen + 1));
            v5 = 537;
            if ( !v3 )
            {
              v22 = -2147024882;
              goto LABEL_40;
            }
            v6 = (WCHAR *)v3;
            v22 = 0;
            v23 = 537;
            cchName = v7;
            v10 = RegEnumKeyExW(hKeya, 0, (LPWSTR)v3, &cchName, 0, 0, 0, 0);
          }
          v13 = RegCloseKey(hKeya);
          if ( v13 > 0 )
            v13 = (unsigned __int16)v13 | 0x80070000;
          v22 = v13;
          v12 = v13 < 0;
          v5 = 548;
          if ( v12 )
            goto LABEL_40;
          v23 = 548;
          hKeya = 0;
          if ( v10 != 259 )
            break;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_955fb8e851b1303fac6deb5ef5879a46_Traceguids, v8);
          v14 = RegDeleteKeyW(hKey, v8);
          if ( v14 > 0 )
            v14 = (unsigned __int16)v14 | 0x80070000;
          v22 = v14;
          v12 = v14 < 0;
          v5 = 555;
          if ( v12 )
            goto LABEL_40;
          v23 = 555;
          v15 = CBsString::ReverseFind((CBsString *)&lpSubKey, 0x5Cu);
          if ( v15 == -1 )
          {
            v22 = 0;
            v23 = 561;
            goto LABEL_41;
          }
          if ( v15 < (unsigned int)v26 )
          {
            LODWORD(v26) = v15;
            v8[v15] = 0;
          }
        }
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        v22 = v10;
        v16 = 568;
        if ( v10 < 0 )
          goto LABEL_44;
        v23 = 568;
        v22 = CBsString::Append((CBsString *)&lpSubKey, L"\\", v6);
        v5 = 571;
      }
      while ( v22 >= 0 );
    }
  }
  else
  {
    v22 = -2147024809;
  }
LABEL_40:
  v24 = v5;
LABEL_41:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
LABEL_45:
  CoTaskMemFree(v3);
  v17 = v22;
  CBsString::_Release((CBsString *)&lpSubKey);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v22);
  return v17;
}

```

## disassembly

```asm
0x18008abd0  push    rbp
0x18008abd2  push    rbx
0x18008abd3  push    rsi
0x18008abd4  push    rdi
0x18008abd5  push    r12
0x18008abd7  push    r13
0x18008abd9  push    r14
0x18008abdb  push    r15
0x18008abdd  lea     rbp, [rsp-1E8h]
0x18008abe5  sub     rsp, 2E8h
0x18008abec  mov     rax, cs:__security_cookie
0x18008abf3  xor     rax, rsp
0x18008abf6  mov     [rbp+220h+var_50], rax
0x18008abfd  mov     r12, rcx
0x18008ac00  lea     rdx, aDeleteregistry; "DeleteRegistryKeyTree"
0x18008ac07  lea     rcx, [rsp+320h+var_2A8]; this
0x18008ac0c  mov     r9d, 2; unsigned __int16
0x18008ac12  mov     r8d, 1E6h; unsigned __int16
0x18008ac18  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008ac1d  xor     r13d, r13d
0x18008ac20  lea     rax, qword_1800EE510
0x18008ac27  xor     edx, edx; Val
0x18008ac29  mov     [rbp+220h+lpSubKey], rax
0x18008ac2d  mov     r8d, 208h; Size
0x18008ac33  mov     [rsp+320h+hKey], r13
0x18008ac38  lea     rcx, [rbp+220h+Name]; void *
0x18008ac3c  mov     [rbp+220h+var_268], r13
0x18008ac40  mov     [rsp+320h+cbMaxSubKeyLen], r13d
0x18008ac45  mov     esi, r13d
0x18008ac48  call    memset_0
0x18008ac4d  mov     [rsp+320h+cchName], r13d
0x18008ac52  test    r12, r12
0x18008ac55  jz      loc_18008AFE5
0x18008ac5b  mov     eax, 1F5h
0x18008ac60  mov     [rsp+320h+var_2A8], r13d
0x18008ac65  lea     edx, [r13+5Ch]; Ch
0x18008ac69  mov     [rsp+320h+var_2A4], ax
0x18008ac6e  lea     rcx, c_wszSafedocsSchedulingKeyName; "ScheduleParams"
0x18008ac75  call    cs:__imp_wcschr
0x18008ac7c  nop     dword ptr [rax+rax+00h]
0x18008ac81  test    rax, rax
0x18008ac84  mov     eax, 1F6h
0x18008ac89  jnz     loc_18008AFBB
0x18008ac8f  lea     rdx, c_wszSafedocsSchedulingKeyName; "ScheduleParams"
0x18008ac96  mov     [rsp+320h+var_2A8], r13d
0x18008ac9b  lea     rcx, [rbp+220h+lpSubKey]; this
0x18008ac9f  mov     [rsp+320h+var_2A4], ax
0x18008aca4  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18008aca9  mov     [rsp+320h+var_2A8], eax
0x18008acad  test    eax, eax
0x18008acaf  mov     eax, 1F8h
0x18008acb4  js      loc_18008AFC3
0x18008acba  lea     r15, [rbp+220h+Name]
0x18008acbe  mov     r14d, 104h
0x18008acc4  mov     ebx, 207h
0x18008acc9  mov     [rsp+320h+var_2A4], ax
0x18008acce  mov     rdi, [rbp+220h+lpSubKey]
0x18008acd2  lea     rdx, WPP_GLOBAL_Control
0x18008acd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ace0  cmp     rcx, rdx
0x18008ace3  jz      short loc_18008AD06
0x18008ace5  test    dword ptr [rcx+1Ch], 800000h
0x18008acec  jz      short loc_18008AD06
0x18008acee  mov     rcx, [rcx+10h]
0x18008acf2  lea     r8, WPP_955fb8e851b1303fac6deb5ef5879a46_Traceguids
0x18008acf9  mov     edx, 0Ah
0x18008acfe  mov     r9, rdi
0x18008ad01  call    WPP_SF_S
0x18008ad06  lea     rax, [rsp+320h+hKey]
0x18008ad0b  mov     r9d, 2001Fh; samDesired
0x18008ad11  xor     r8d, r8d; ulOptions
0x18008ad14  mov     [rsp+320h+phkResult], rax; phkResult
0x18008ad19  mov     rdx, rdi; lpSubKey
0x18008ad1c  mov     rcx, r12; hKey
0x18008ad1f  call    cs:__imp_RegOpenKeyExW
0x18008ad26  nop     dword ptr [rax+rax+00h]
0x18008ad2b  test    eax, eax
0x18008ad2d  jle     short loc_18008AD37
0x18008ad2f  movzx   eax, ax
0x18008ad32  or      eax, 80070000h
0x18008ad37  mov     [rsp+320h+var_2A8], eax
0x18008ad3b  test    eax, eax
0x18008ad3d  js      loc_18008AFB4
0x18008ad43  mov     rcx, [rsp+320h+hKey]; hKey
0x18008ad48  lea     r9, [rsp+320h+cchName]; lpcchName
0x18008ad4d  mov     [rsp+320h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18008ad52  mov     r8, r15; lpName
0x18008ad55  mov     [rsp+320h+lpcchClass], r13; lpcchClass
0x18008ad5a  xor     edx, edx; dwIndex
0x18008ad5c  mov     [rsp+320h+lpClass], r13; lpClass
0x18008ad61  mov     [rsp+320h+phkResult], r13; lpReserved
0x18008ad66  mov     [rsp+320h+var_2A4], bx
0x18008ad6b  mov     [rsp+320h+cchName], r14d
0x18008ad70  call    cs:__imp_RegEnumKeyExW
0x18008ad77  nop     dword ptr [rax+rax+00h]
0x18008ad7c  mov     ebx, eax
0x18008ad7e  cmp     eax, 0EAh
0x18008ad83  jnz     loc_18008AE6E
0x18008ad89  mov     rcx, [rsp+320h+hKey]; hKey
0x18008ad8e  lea     rax, [rsp+320h+cbMaxSubKeyLen]
0x18008ad93  mov     [rsp+320h+var_2C8], r13; lpftLastWriteTime
0x18008ad98  xor     r9d, r9d; lpReserved
0x18008ad9b  mov     [rsp+320h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18008ada0  xor     r8d, r8d; lpcchClass
0x18008ada3  mov     [rsp+320h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18008ada8  xor     edx, edx; lpClass
0x18008adaa  mov     [rsp+320h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18008adaf  mov     [rsp+320h+lpftLastWriteTime], r13; lpcValues
0x18008adb4  mov     [rsp+320h+lpcchClass], r13; lpcbMaxClassLen
0x18008adb9  mov     [rsp+320h+lpClass], rax; lpcbMaxSubKeyLen
0x18008adbe  mov     [rsp+320h+phkResult], r13; lpcSubKeys
0x18008adc3  call    cs:__imp_RegQueryInfoKeyW
0x18008adca  nop     dword ptr [rax+rax+00h]
0x18008adcf  test    eax, eax
0x18008add1  jle     short loc_18008ADDB
0x18008add3  movzx   eax, ax
0x18008add6  or      eax, 80070000h
0x18008addb  mov     [rsp+320h+var_2A8], eax
0x18008addf  test    eax, eax
0x18008ade1  mov     eax, 211h
0x18008ade6  js      loc_18008AFC3
0x18008adec  mov     rcx, rsi; pv
0x18008adef  mov     [rsp+320h+var_2A4], ax
0x18008adf4  call    cs:__imp_CoTaskMemFree
0x18008adfb  nop     dword ptr [rax+rax+00h]
0x18008ae00  mov     r14d, [rsp+320h+cbMaxSubKeyLen]
0x18008ae05  inc     r14d
0x18008ae08  mov     ecx, r14d
0x18008ae0b  add     rcx, rcx; cb
0x18008ae0e  call    cs:__imp_CoTaskMemAlloc
0x18008ae15  nop     dword ptr [rax+rax+00h]
0x18008ae1a  mov     rsi, rax
0x18008ae1d  test    rax, rax
0x18008ae20  mov     eax, 219h
0x18008ae25  jz      loc_18008AF99
0x18008ae2b  mov     rcx, [rsp+320h+hKey]; hKey
0x18008ae30  lea     r9, [rsp+320h+cchName]; lpcchName
0x18008ae35  mov     [rsp+320h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18008ae3a  mov     r8, rsi; lpName
0x18008ae3d  mov     [rsp+320h+lpcchClass], r13; lpcchClass
0x18008ae42  xor     edx, edx; dwIndex
0x18008ae44  mov     [rsp+320h+lpClass], r13; lpClass
0x18008ae49  mov     r15, rsi
0x18008ae4c  mov     [rsp+320h+phkResult], r13; lpReserved
0x18008ae51  mov     [rsp+320h+var_2A8], r13d
0x18008ae56  mov     [rsp+320h+var_2A4], ax
0x18008ae5b  mov     [rsp+320h+cchName], r14d
0x18008ae60  call    cs:__imp_RegEnumKeyExW
0x18008ae67  nop     dword ptr [rax+rax+00h]
0x18008ae6c  mov     ebx, eax
0x18008ae6e  mov     rcx, [rsp+320h+hKey]; hKey
0x18008ae73  call    cs:__imp_RegCloseKey
0x18008ae7a  nop     dword ptr [rax+rax+00h]
0x18008ae7f  test    eax, eax
0x18008ae81  jle     short loc_18008AE8B
0x18008ae83  movzx   eax, ax
0x18008ae86  or      eax, 80070000h
0x18008ae8b  mov     [rsp+320h+var_2A8], eax
0x18008ae8f  test    eax, eax
0x18008ae91  mov     eax, 224h
0x18008ae96  js      loc_18008AFC3
0x18008ae9c  mov     [rsp+320h+var_2A4], ax
0x18008aea1  mov     [rsp+320h+hKey], r13
0x18008aea6  cmp     ebx, 103h
0x18008aeac  jnz     loc_18008AF51
0x18008aeb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008aeb9  lea     rax, WPP_GLOBAL_Control
0x18008aec0  cmp     rcx, rax
0x18008aec3  jz      short loc_18008AEE6
0x18008aec5  test    dword ptr [rcx+1Ch], 800000h
0x18008aecc  jz      short loc_18008AEE6
0x18008aece  mov     rcx, [rcx+10h]
0x18008aed2  lea     r8, WPP_955fb8e851b1303fac6deb5ef5879a46_Traceguids
0x18008aed9  mov     edx, 0Bh
0x18008aede  mov     r9, rdi
0x18008aee1  call    WPP_SF_S
0x18008aee6  mov     rdx, rdi; lpSubKey
0x18008aee9  mov     rcx, r12; hKey
0x18008aeec  call    cs:__imp_RegDeleteKeyW
0x18008aef3  nop     dword ptr [rax+rax+00h]
0x18008aef8  test    eax, eax
0x18008aefa  jle     short loc_18008AF04
0x18008aefc  movzx   eax, ax
0x18008aeff  or      eax, 80070000h
0x18008af04  mov     [rsp+320h+var_2A8], eax
0x18008af08  test    eax, eax
0x18008af0a  mov     eax, 22Bh
0x18008af0f  js      loc_18008AFC3
0x18008af15  mov     edx, 5Ch ; '\'; unsigned __int16
0x18008af1a  mov     [rsp+320h+var_2A4], ax
0x18008af1f  lea     rcx, [rbp+220h+lpSubKey]; this
0x18008af23  call    ?ReverseFind@CBsString@@QEBAJG@Z; CBsString::ReverseFind(ushort)
0x18008af28  cmp     eax, 0FFFFFFFFh
0x18008af2b  jz      short loc_18008AFA3
0x18008af2d  lea     rdx, WPP_GLOBAL_Control
0x18008af34  mov     ebx, 207h
0x18008af39  cmp     eax, dword ptr [rbp+220h+var_268]
0x18008af3c  jnb     loc_18008ACD9
0x18008af42  mov     ecx, eax
0x18008af44  mov     dword ptr [rbp+220h+var_268], eax
0x18008af47  mov     [rdi+rcx*2], r13w
0x18008af4c  jmp     loc_18008ACD2
0x18008af51  test    ebx, ebx
0x18008af53  jle     short loc_18008AF5E
0x18008af55  movzx   ebx, bx
0x18008af58  or      ebx, 80070000h
0x18008af5e  mov     [rsp+320h+var_2A8], ebx
0x18008af62  mov     eax, 238h
0x18008af67  test    ebx, ebx
0x18008af69  js      loc_18008AFF2
0x18008af6f  mov     r8, r15; unsigned __int16 *
0x18008af72  mov     [rsp+320h+var_2A4], ax
0x18008af77  lea     rdx, Str; "\\"
0x18008af7e  lea     rcx, [rbp+220h+lpSubKey]; this
0x18008af82  call    ?Append@CBsString@@QEAAJPEBG0@Z; CBsString::Append(ushort const *,ushort const *)
0x18008af87  mov     [rsp+320h+var_2A8], eax
0x18008af8b  test    eax, eax
0x18008af8d  mov     eax, 23Bh
0x18008af92  js      short loc_18008AFC3
0x18008af94  jmp     loc_18008ACC4
0x18008af99  mov     [rsp+320h+var_2A8], 8007000Eh
0x18008afa1  jmp     short loc_18008AFC3
0x18008afa3  mov     eax, 231h
0x18008afa8  mov     [rsp+320h+var_2A8], r13d
0x18008afad  mov     [rsp+320h+var_2A4], ax
0x18008afb2  jmp     short loc_18008AFC8
0x18008afb4  mov     [rsp+320h+var_2A2], bx
0x18008afb9  jmp     short loc_18008AFC8
0x18008afbb  mov     [rsp+320h+var_2A8], 80070057h
0x18008afc3  mov     [rsp+320h+var_2A2], ax
0x18008afc8  mov     rcx, [rsp+320h+hKey]; hKey
0x18008afcd  test    rcx, rcx
0x18008afd0  jz      short loc_18008AFF7
0x18008afd2  call    cs:__imp_RegCloseKey
0x18008afd9  nop     dword ptr [rax+rax+00h]
0x18008afde  mov     [rsp+320h+hKey], r13
0x18008afe3  jmp     short loc_18008AFF7
0x18008afe5  mov     [rsp+320h+var_2A8], 80070057h
0x18008afed  mov     eax, 1F3h
0x18008aff2  mov     [rsp+320h+var_2A2], ax
0x18008aff7  mov     rcx, rsi; pv
0x18008affa  call    cs:__imp_CoTaskMemFree
0x18008b001  nop     dword ptr [rax+rax+00h]
0x18008b006  mov     ebx, [rsp+320h+var_2A8]
0x18008b00a  lea     rcx, [rbp+220h+lpSubKey]; this
0x18008b00e  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18008b013  lea     rcx, [rsp+320h+var_2A8]; this
0x18008b018  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008b01d  mov     eax, ebx
0x18008b01f  mov     rcx, [rbp+220h+var_50]
0x18008b026  xor     rcx, rsp; StackCookie
0x18008b029  call    __security_check_cookie
0x18008b02e  add     rsp, 2E8h
0x18008b035  pop     r15
0x18008b037  pop     r14
0x18008b039  pop     r13
0x18008b03b  pop     r12
0x18008b03d  pop     rdi
0x18008b03e  pop     rsi
0x18008b03f  pop     rbx
0x18008b040  pop     rbp
0x18008b041  retn
```
