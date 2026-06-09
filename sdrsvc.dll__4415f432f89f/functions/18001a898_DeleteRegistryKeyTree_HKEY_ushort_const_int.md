# DeleteRegistryKeyTree(HKEY__ *,ushort const *,int)

- ea: `0x18001a898`
- end: `0x18001acdb`
- name: `?DeleteRegistryKeyTree@@YAJPEAUHKEY__@@PEBGH@Z`
- size: `1091`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b770`

## callees

- `0x180014f70`
- `0x18001586c`
- `0x180015974`
- `0x18001a898`
- `0x18001f5b4`
- `0x18001f624`
- `0x18001fc28`
- `0x180020488`
- `0x18002170a`
- `0x180021740`

## import_xrefs

- `msvcrt!wcschr` at `0x18001a93d`
- `msvcrt!wcschr` at `0x18001a93d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ab1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ac77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ab1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ac77`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001aa82`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001aa82`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001aa35`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001ab0d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001aa35`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001ab0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a9e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a9e1`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001ab8d`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001ab8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001aac1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001aac1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aaad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ac99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aaad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ac99`

## string_xrefs

- `0x18001a936`: `Security`
- `0x18001a95b`: `Security`
- `0x18001a8c8`: `DeleteRegistryKeyTree`

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
  unsigned __int16 v15; // dx
  unsigned int v16; // eax
  __int16 v17; // ax
  __int16 v18; // ax
  unsigned int v19; // ebx
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+78h] [rbp-88h] BYREF
  __int16 v25; // [rsp+7Ch] [rbp-84h]
  __int16 v26; // [rsp+7Eh] [rbp-82h]
  LPCWSTR lpSubKey; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v28; // [rsp+B8h] [rbp-48h]
  WCHAR Name[264]; // [rsp+C0h] [rbp-40h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v24, "DeleteRegistryKeyTree", 486, 2);
  lpSubKey = (LPCWSTR)qword_180028260;
  hKeya = 0;
  v28 = 0;
  cbMaxSubKeyLen = 0;
  v3 = 0;
  memset_0(Name, 0, 0x208u);
  cchName = 0;
  if ( hKey )
  {
    v24 = 0;
    v25 = 501;
    v4 = wcschr(L"Security", 0x5Cu) == 0;
    v5 = 502;
    if ( v4 )
    {
      v24 = 0;
      v25 = 502;
      v24 = CBsString::Append((CBsString *)&lpSubKey, L"Security");
      v5 = 504;
      if ( v24 >= 0 )
      {
        v6 = Name;
        v7 = 260;
        do
        {
          v25 = v5;
          v8 = lpSubKey;
          while ( 1 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_955fb8e851b1303fac6deb5ef5879a46_Traceguids, v8);
            }
            v9 = RegOpenKeyExW(hKey, v8, 0, 0x2001Fu, &hKeya);
            if ( v9 == 2 )
            {
              v24 = 1;
              v18 = 517;
              goto LABEL_41;
            }
            if ( v9 > 0 )
              v9 = (unsigned __int16)v9 | 0x80070000;
            v24 = v9;
            if ( v9 < 0 )
            {
              v26 = 519;
              goto LABEL_44;
            }
            v25 = 519;
            cchName = v7;
            v10 = RegEnumKeyExW(hKeya, 0, v6, &cchName, 0, 0, 0, 0);
            if ( v10 == 234 )
            {
              v11 = RegQueryInfoKeyW(hKeya, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
              if ( v11 > 0 )
                v11 = (unsigned __int16)v11 | 0x80070000;
              v24 = v11;
              v12 = v11 < 0;
              v5 = 529;
              if ( v12 )
                goto LABEL_43;
              v25 = 529;
              CoTaskMemFree(v3);
              v7 = cbMaxSubKeyLen + 1;
              v3 = CoTaskMemAlloc(2LL * (cbMaxSubKeyLen + 1));
              v5 = 537;
              if ( !v3 )
              {
                v24 = -2147024882;
                goto LABEL_43;
              }
              v6 = (WCHAR *)v3;
              v24 = 0;
              v25 = 537;
              cchName = v7;
              v10 = RegEnumKeyExW(hKeya, 0, (LPWSTR)v3, &cchName, 0, 0, 0, 0);
            }
            v13 = RegCloseKey(hKeya);
            if ( v13 > 0 )
              v13 = (unsigned __int16)v13 | 0x80070000;
            v24 = v13;
            v12 = v13 < 0;
            v5 = 548;
            if ( v12 )
              goto LABEL_43;
            v25 = 548;
            hKeya = 0;
            if ( v10 != 259 )
              break;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_955fb8e851b1303fac6deb5ef5879a46_Traceguids, v8);
            }
            v14 = RegDeleteKeyW(hKey, v8);
            if ( v14 > 0 )
              v14 = (unsigned __int16)v14 | 0x80070000;
            v24 = v14;
            v12 = v14 < 0;
            v5 = 555;
            if ( v12 )
              goto LABEL_43;
            v25 = 555;
            v16 = CBsString::ReverseFind((CBsString *)&lpSubKey, v15);
            if ( v16 == -1 )
            {
              v24 = 0;
              v18 = 561;
LABEL_41:
              v25 = v18;
              goto LABEL_44;
            }
            if ( v16 < (unsigned int)v28 )
            {
              LODWORD(v28) = v16;
              v8[v16] = 0;
            }
          }
          if ( v10 > 0 )
            v10 = (unsigned __int16)v10 | 0x80070000;
          v24 = v10;
          v17 = 568;
          if ( v10 < 0 )
            goto LABEL_47;
          v25 = 568;
          v24 = CBsString::Append((CBsString *)&lpSubKey, L"\\", v6);
          v5 = 571;
        }
        while ( v24 >= 0 );
      }
    }
    else
    {
      v24 = -2147024809;
    }
LABEL_43:
    v26 = v5;
LABEL_44:
    if ( hKeya )
    {
      RegCloseKey(hKeya);
      hKeya = 0;
    }
  }
  else
  {
    v24 = -2147024809;
    v17 = 499;
LABEL_47:
    v26 = v17;
  }
  CoTaskMemFree(v3);
  v19 = v24;
  CBsString::_Release((LPVOID *)&lpSubKey);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v24);
  return v19;
}

```

## disassembly

```asm
0x18001a898  push    rbp
0x18001a89a  push    rbx
0x18001a89b  push    rsi
0x18001a89c  push    rdi
0x18001a89d  push    r12
0x18001a89f  push    r13
0x18001a8a1  push    r14
0x18001a8a3  push    r15
0x18001a8a5  lea     rbp, [rsp-1E8h]
0x18001a8ad  sub     rsp, 2E8h
0x18001a8b4  mov     rax, cs:__security_cookie
0x18001a8bb  xor     rax, rsp
0x18001a8be  mov     [rbp+220h+var_50], rax
0x18001a8c5  mov     r12, rcx
0x18001a8c8  lea     rdx, aDeleteregistry; "DeleteRegistryKeyTree"
0x18001a8cf  lea     rcx, [rsp+320h+var_2A8]; this
0x18001a8d4  mov     r9d, 2; unsigned __int16
0x18001a8da  mov     r8d, 1E6h; unsigned __int16
0x18001a8e0  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001a8e5  xor     r13d, r13d
0x18001a8e8  lea     rax, qword_180028260
0x18001a8ef  xor     edx, edx; Val
0x18001a8f1  mov     [rbp+220h+lpSubKey], rax
0x18001a8f5  mov     r8d, 208h; Size
0x18001a8fb  mov     [rsp+320h+hKey], r13
0x18001a900  lea     rcx, [rbp+220h+Name]; void *
0x18001a904  mov     [rbp+220h+var_268], r13
0x18001a908  mov     [rsp+320h+cbMaxSubKeyLen], r13d
0x18001a90d  mov     esi, r13d
0x18001a910  call    memset_0
0x18001a915  mov     [rsp+320h+cchName], r13d
0x18001a91a  test    r12, r12
0x18001a91d  jz      loc_18001AC84
0x18001a923  mov     eax, 1F5h
0x18001a928  mov     [rsp+320h+var_2A8], r13d
0x18001a92d  lea     edx, [r13+5Ch]; Ch
0x18001a931  mov     [rsp+320h+var_2A4], ax
0x18001a936  lea     rcx, c_wszSafedocsCredentialsKey; "Security"
0x18001a93d  call    cs:__imp_wcschr
0x18001a943  test    rax, rax
0x18001a946  mov     eax, 1F6h
0x18001a94b  jnz     loc_18001AC60
0x18001a951  mov     [rsp+320h+var_2A8], r13d
0x18001a956  mov     [rsp+320h+var_2A4], ax
0x18001a95b  lea     rdx, c_wszSafedocsCredentialsKey; "Security"
0x18001a962  lea     rcx, [rbp+220h+lpSubKey]; this
0x18001a966  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18001a96b  mov     [rsp+320h+var_2A8], eax
0x18001a96f  test    eax, eax
0x18001a971  mov     eax, 1F8h
0x18001a976  js      loc_18001AC68
0x18001a97c  lea     r15, [rbp+220h+Name]
0x18001a980  mov     r14d, 104h
0x18001a986  mov     ebx, 207h
0x18001a98b  mov     [rsp+320h+var_2A4], ax
0x18001a990  mov     rdi, [rbp+220h+lpSubKey]
0x18001a994  lea     rdx, WPP_GLOBAL_Control
0x18001a99b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9a2  cmp     rcx, rdx
0x18001a9a5  jz      short loc_18001A9C8
0x18001a9a7  test    dword ptr [rcx+1Ch], 800000h
0x18001a9ae  jz      short loc_18001A9C8
0x18001a9b0  mov     rcx, [rcx+10h]
0x18001a9b4  lea     r8, WPP_955fb8e851b1303fac6deb5ef5879a46_Traceguids
0x18001a9bb  mov     edx, 0Ah
0x18001a9c0  mov     r9, rdi
0x18001a9c3  call    WPP_SF_S
0x18001a9c8  lea     rax, [rsp+320h+hKey]
0x18001a9cd  mov     r9d, 2001Fh; samDesired
0x18001a9d3  xor     r8d, r8d; ulOptions
0x18001a9d6  mov     [rsp+320h+phkResult], rax; phkResult
0x18001a9db  mov     rdx, rdi; lpSubKey
0x18001a9de  mov     rcx, r12; hKey
0x18001a9e1  call    cs:__imp_RegOpenKeyExW
0x18001a9e7  cmp     eax, 2
0x18001a9ea  jz      loc_18001AC4C
0x18001a9f0  test    eax, eax
0x18001a9f2  jle     short loc_18001A9FC
0x18001a9f4  movzx   eax, ax
0x18001a9f7  or      eax, 80070000h
0x18001a9fc  mov     [rsp+320h+var_2A8], eax
0x18001aa00  test    eax, eax
0x18001aa02  js      loc_18001AC45
0x18001aa08  mov     rcx, [rsp+320h+hKey]; hKey
0x18001aa0d  lea     r9, [rsp+320h+cchName]; lpcchName
0x18001aa12  mov     [rsp+320h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18001aa17  mov     r8, r15; lpName
0x18001aa1a  mov     [rsp+320h+lpcchClass], r13; lpcchClass
0x18001aa1f  xor     edx, edx; dwIndex
0x18001aa21  mov     [rsp+320h+lpClass], r13; lpClass
0x18001aa26  mov     [rsp+320h+phkResult], r13; lpReserved
0x18001aa2b  mov     [rsp+320h+var_2A4], bx
0x18001aa30  mov     [rsp+320h+cchName], r14d
0x18001aa35  call    cs:__imp_RegEnumKeyExW
0x18001aa3b  mov     ebx, eax
0x18001aa3d  cmp     eax, 0EAh
0x18001aa42  jnz     loc_18001AB15
0x18001aa48  mov     rcx, [rsp+320h+hKey]; hKey
0x18001aa4d  lea     rax, [rsp+320h+cbMaxSubKeyLen]
0x18001aa52  mov     [rsp+320h+var_2C8], r13; lpftLastWriteTime
0x18001aa57  xor     r9d, r9d; lpReserved
0x18001aa5a  mov     [rsp+320h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18001aa5f  xor     r8d, r8d; lpcchClass
0x18001aa62  mov     [rsp+320h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18001aa67  xor     edx, edx; lpClass
0x18001aa69  mov     [rsp+320h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18001aa6e  mov     [rsp+320h+lpftLastWriteTime], r13; lpcValues
0x18001aa73  mov     [rsp+320h+lpcchClass], r13; lpcbMaxClassLen
0x18001aa78  mov     [rsp+320h+lpClass], rax; lpcbMaxSubKeyLen
0x18001aa7d  mov     [rsp+320h+phkResult], r13; lpcSubKeys
0x18001aa82  call    cs:__imp_RegQueryInfoKeyW
0x18001aa88  test    eax, eax
0x18001aa8a  jle     short loc_18001AA94
0x18001aa8c  movzx   eax, ax
0x18001aa8f  or      eax, 80070000h
0x18001aa94  mov     [rsp+320h+var_2A8], eax
0x18001aa98  test    eax, eax
0x18001aa9a  mov     eax, 211h
0x18001aa9f  js      loc_18001AC68
0x18001aaa5  mov     rcx, rsi; pv
0x18001aaa8  mov     [rsp+320h+var_2A4], ax
0x18001aaad  call    cs:__imp_CoTaskMemFree
0x18001aab3  mov     r14d, [rsp+320h+cbMaxSubKeyLen]
0x18001aab8  inc     r14d
0x18001aabb  mov     ecx, r14d
0x18001aabe  add     rcx, rcx; cb
0x18001aac1  call    cs:__imp_CoTaskMemAlloc
0x18001aac7  mov     rsi, rax
0x18001aaca  test    rax, rax
0x18001aacd  mov     eax, 219h
0x18001aad2  jz      loc_18001AC2F
0x18001aad8  mov     rcx, [rsp+320h+hKey]; hKey
0x18001aadd  lea     r9, [rsp+320h+cchName]; lpcchName
0x18001aae2  mov     [rsp+320h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18001aae7  mov     r8, rsi; lpName
0x18001aaea  mov     [rsp+320h+lpcchClass], r13; lpcchClass
0x18001aaef  xor     edx, edx; dwIndex
0x18001aaf1  mov     [rsp+320h+lpClass], r13; lpClass
0x18001aaf6  mov     r15, rsi
0x18001aaf9  mov     [rsp+320h+phkResult], r13; lpReserved
0x18001aafe  mov     [rsp+320h+var_2A8], r13d
0x18001ab03  mov     [rsp+320h+var_2A4], ax
0x18001ab08  mov     [rsp+320h+cchName], r14d
0x18001ab0d  call    cs:__imp_RegEnumKeyExW
0x18001ab13  mov     ebx, eax
0x18001ab15  mov     rcx, [rsp+320h+hKey]; hKey
0x18001ab1a  call    cs:__imp_RegCloseKey
0x18001ab20  test    eax, eax
0x18001ab22  jle     short loc_18001AB2C
0x18001ab24  movzx   eax, ax
0x18001ab27  or      eax, 80070000h
0x18001ab2c  mov     [rsp+320h+var_2A8], eax
0x18001ab30  test    eax, eax
0x18001ab32  mov     eax, 224h
0x18001ab37  js      loc_18001AC68
0x18001ab3d  mov     [rsp+320h+var_2A4], ax
0x18001ab42  mov     [rsp+320h+hKey], r13
0x18001ab47  cmp     ebx, 103h
0x18001ab4d  jnz     loc_18001ABE7
0x18001ab53  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab5a  lea     rax, WPP_GLOBAL_Control
0x18001ab61  cmp     rcx, rax
0x18001ab64  jz      short loc_18001AB87
0x18001ab66  test    dword ptr [rcx+1Ch], 800000h
0x18001ab6d  jz      short loc_18001AB87
0x18001ab6f  mov     rcx, [rcx+10h]
0x18001ab73  lea     r8, WPP_955fb8e851b1303fac6deb5ef5879a46_Traceguids
0x18001ab7a  mov     edx, 0Bh
0x18001ab7f  mov     r9, rdi
0x18001ab82  call    WPP_SF_S
0x18001ab87  mov     rdx, rdi; lpSubKey
0x18001ab8a  mov     rcx, r12; hKey
0x18001ab8d  call    cs:__imp_RegDeleteKeyW
0x18001ab93  test    eax, eax
0x18001ab95  jle     short loc_18001AB9F
0x18001ab97  movzx   eax, ax
0x18001ab9a  or      eax, 80070000h
0x18001ab9f  mov     [rsp+320h+var_2A8], eax
0x18001aba3  test    eax, eax
0x18001aba5  mov     eax, 22Bh
0x18001abaa  js      loc_18001AC68
0x18001abb0  lea     rcx, [rbp+220h+lpSubKey]; this
0x18001abb4  mov     [rsp+320h+var_2A4], ax
0x18001abb9  call    ?ReverseFind@CBsString@@QEBAJG@Z; CBsString::ReverseFind(ushort)
0x18001abbe  cmp     eax, 0FFFFFFFFh
0x18001abc1  jz      short loc_18001AC39
0x18001abc3  lea     rdx, WPP_GLOBAL_Control
0x18001abca  mov     ebx, 207h
0x18001abcf  cmp     eax, dword ptr [rbp+220h+var_268]
0x18001abd2  jnb     loc_18001A99B
0x18001abd8  mov     ecx, eax
0x18001abda  mov     dword ptr [rbp+220h+var_268], eax
0x18001abdd  mov     [rdi+rcx*2], r13w
0x18001abe2  jmp     loc_18001A994
0x18001abe7  test    ebx, ebx
0x18001abe9  jle     short loc_18001ABF4
0x18001abeb  movzx   ebx, bx
0x18001abee  or      ebx, 80070000h
0x18001abf4  mov     [rsp+320h+var_2A8], ebx
0x18001abf8  mov     eax, 238h
0x18001abfd  test    ebx, ebx
0x18001abff  js      loc_18001AC91
0x18001ac05  mov     r8, r15; unsigned __int16 *
0x18001ac08  mov     [rsp+320h+var_2A4], ax
0x18001ac0d  lea     rdx, asc_180024680; "\\"
0x18001ac14  lea     rcx, [rbp+220h+lpSubKey]; this
0x18001ac18  call    ?Append@CBsString@@QEAAJPEBG0@Z; CBsString::Append(ushort const *,ushort const *)
0x18001ac1d  mov     [rsp+320h+var_2A8], eax
0x18001ac21  test    eax, eax
0x18001ac23  mov     eax, 23Bh
0x18001ac28  js      short loc_18001AC68
0x18001ac2a  jmp     loc_18001A986
0x18001ac2f  mov     [rsp+320h+var_2A8], 8007000Eh
0x18001ac37  jmp     short loc_18001AC68
0x18001ac39  mov     [rsp+320h+var_2A8], r13d
0x18001ac3e  mov     eax, 231h
0x18001ac43  jmp     short loc_18001AC59
0x18001ac45  mov     [rsp+320h+var_2A2], bx
0x18001ac4a  jmp     short loc_18001AC6D
0x18001ac4c  mov     [rsp+320h+var_2A8], 1
0x18001ac54  mov     eax, 205h
0x18001ac59  mov     [rsp+320h+var_2A4], ax
0x18001ac5e  jmp     short loc_18001AC6D
0x18001ac60  mov     [rsp+320h+var_2A8], 80070057h
0x18001ac68  mov     [rsp+320h+var_2A2], ax
0x18001ac6d  mov     rcx, [rsp+320h+hKey]; hKey
0x18001ac72  test    rcx, rcx
0x18001ac75  jz      short loc_18001AC96
0x18001ac77  call    cs:__imp_RegCloseKey
0x18001ac7d  mov     [rsp+320h+hKey], r13
0x18001ac82  jmp     short loc_18001AC96
0x18001ac84  mov     [rsp+320h+var_2A8], 80070057h
0x18001ac8c  mov     eax, 1F3h
0x18001ac91  mov     [rsp+320h+var_2A2], ax
0x18001ac96  mov     rcx, rsi; pv
0x18001ac99  call    cs:__imp_CoTaskMemFree
0x18001ac9f  mov     ebx, [rsp+320h+var_2A8]
0x18001aca3  lea     rcx, [rbp+220h+lpSubKey]; this
0x18001aca7  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001acac  lea     rcx, [rsp+320h+var_2A8]; this
0x18001acb1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001acb6  mov     eax, ebx
0x18001acb8  mov     rcx, [rbp+220h+var_50]
0x18001acbf  xor     rcx, rsp; StackCookie
0x18001acc2  call    __security_check_cookie
0x18001acc7  add     rsp, 2E8h
0x18001acce  pop     r15
0x18001acd0  pop     r14
0x18001acd2  pop     r13
0x18001acd4  pop     r12
0x18001acd6  pop     rdi
0x18001acd7  pop     rsi
0x18001acd8  pop     rbx
0x18001acd9  pop     rbp
0x18001acda  retn
```
