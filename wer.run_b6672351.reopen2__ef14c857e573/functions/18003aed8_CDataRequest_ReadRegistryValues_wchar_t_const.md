# CDataRequest::ReadRegistryValues(wchar_t const *)

- ea: `0x18003aed8`
- end: `0x18003b179`
- name: `?ReadRegistryValues@CDataRequest@@IEAAXPEB_W@Z`
- size: `673`
- prototype: `void __fastcall(CDataRequest *__hidden this, LPCWSTR lpSubKey)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18007cc74`
- `0x18008799c`
- `0x180088b88`
- `0x180088c50`
- `0x18008eabc`

## callees

- `0x180004c64`
- `0x18001cb20`
- `0x18001e0d0`
- `0x18001f3a0`
- `0x1800201f0`
- `0x18003aed8`
- `0x18003b180`
- `0x18008e78c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003b06f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003b06f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003af3c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003af3c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003afe8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003afe8`

## pseudocode

```c
void __fastcall CDataRequest::ReadRegistryValues(CDataRequest *this, LPCWSTR lpSubKey)
{
  HKEY *phkResult; // rax
  __int64 unique_for; // rax
  LPWSTR v6; // rbx
  __int64 v7; // rax
  LPBYTE v8; // rdi
  wchar_t *v9; // rcx
  __int64 v10; // rdx
  DWORD i; // r14d
  DWORD cValues; // [rsp+60h] [rbp+7h] BYREF
  DWORD Type; // [rsp+64h] [rbp+Bh] BYREF
  HKEY hKey; // [rsp+68h] [rbp+Fh] BYREF
  LPBYTE lpData; // [rsp+70h] [rbp+17h] BYREF
  LPWSTR lpValueName; // [rsp+78h] [rbp+1Fh] BYREF
  _BYTE v17[16]; // [rsp+80h] [rbp+27h] BYREF
  DWORD cchValueName; // [rsp+D0h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+D8h] [rbp+7Fh] BYREF

  hKey = 0;
  cValues = 0;
  lpValueName = 0;
  lpData = 0;
  cchValueName = 0;
  cbData = 0;
  Type = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, phkResult) )
  {
    unique_for = utl::make_unique_for_overwrite<wchar_t [0],0>(v17, 260);
    utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(&lpValueName, unique_for);
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(v17);
    v6 = lpValueName;
    if ( lpValueName )
    {
      v7 = utl::make_unique_for_overwrite<wchar_t [0],0>(v17, 2048);
      utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(&lpData, v7);
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(v17);
      v8 = lpData;
      if ( lpData )
      {
        if ( RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0) )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v10 = 18;
LABEL_26:
            WPP_SF_(*((_QWORD *)v9 + 2), v10, WPP_df4f1aef4ed33107df8087e7e060b469_Traceguids);
          }
        }
        else
        {
          for ( i = 0; i < cValues; ++i )
          {
            cchValueName = 260;
            cbData = 4096;
            if ( !RegEnumValueW(hKey, i, v6, &cchValueName, 0, &Type, v8, &cbData) )
            {
              if ( Type == 1 && cchValueName <= 0x104 && cbData <= 0x1000 )
              {
                if ( *v6 )
                {
                  v6[259] = 0;
                  *((_WORD *)v8 + 2047) = 0;
                  CDataRequest::AddRequest(this, v6, (const wchar_t *)v8);
                }
              }
              else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_df4f1aef4ed33107df8087e7e060b469_Traceguids);
              }
            }
          }
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v10 = 17;
          goto LABEL_26;
        }
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v10 = 16;
        goto LABEL_26;
      }
    }
  }
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&lpData);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&lpValueName);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
}

```

## disassembly

```asm
0x18003aed8  mov     [rsp-8+arg_0], rbx
0x18003aedd  mov     [rsp-8+arg_8], rsi
0x18003aee2  push    rbp
0x18003aee3  push    rdi
0x18003aee4  push    r12
0x18003aee6  push    r14
0x18003aee8  push    r15
0x18003aeea  lea     rbp, [rsp-37h]
0x18003aeef  sub     rsp, 90h
0x18003aef6  xor     r12d, r12d
0x18003aef9  mov     r15, rcx
0x18003aefc  lea     rcx, [rbp+57h+hKey]
0x18003af00  mov     [rbp+57h+hKey], r12
0x18003af04  mov     [rbp+57h+cValues], r12d
0x18003af08  mov     rbx, rdx
0x18003af0b  mov     [rbp+57h+lpValueName], r12
0x18003af0f  mov     [rbp+57h+lpData], r12
0x18003af13  mov     [rbp+57h+cchValueName], r12d
0x18003af17  mov     [rbp+57h+cbData], r12d
0x18003af1b  mov     [rbp+57h+Type], r12d
0x18003af1f  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18003af24  mov     r9d, 20119h; samDesired
0x18003af2a  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18003af2f  xor     r8d, r8d; ulOptions
0x18003af32  mov     rdx, rbx; lpSubKey
0x18003af35  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003af3c  call    cs:__imp_RegOpenKeyExW
0x18003af43  nop     dword ptr [rax+rax+00h]
0x18003af48  test    eax, eax
0x18003af4a  jnz     loc_18003B141
0x18003af50  mov     edx, 104h
0x18003af55  lea     rcx, [rbp+57h+var_30]
0x18003af59  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x18003af5e  mov     rdx, rax
0x18003af61  lea     rcx, [rbp+57h+lpValueName]
0x18003af65  call    ??4?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&)
0x18003af6a  lea     rcx, [rbp+57h+var_30]; void *
0x18003af6e  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18003af73  mov     rbx, [rbp+57h+lpValueName]
0x18003af77  test    rbx, rbx
0x18003af7a  jz      loc_18003B113
0x18003af80  mov     edx, 800h
0x18003af85  lea     rcx, [rbp+57h+var_30]
0x18003af89  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x18003af8e  mov     rdx, rax
0x18003af91  lea     rcx, [rbp+57h+lpData]
0x18003af95  call    ??4?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&)
0x18003af9a  lea     rcx, [rbp+57h+var_30]; void *
0x18003af9e  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18003afa3  mov     rdi, [rbp+57h+lpData]
0x18003afa7  test    rdi, rdi
0x18003afaa  jz      loc_18003B0F3
0x18003afb0  mov     rcx, [rbp+57h+hKey]; hKey
0x18003afb4  lea     rax, [rbp+57h+cValues]
0x18003afb8  mov     [rsp+0B0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18003afbd  xor     r9d, r9d; lpReserved
0x18003afc0  mov     [rsp+0B0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18003afc5  xor     r8d, r8d; lpcchClass
0x18003afc8  mov     [rsp+0B0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18003afcd  xor     edx, edx; lpClass
0x18003afcf  mov     [rsp+0B0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18003afd4  mov     [rsp+0B0h+lpcValues], rax; lpcValues
0x18003afd9  mov     [rsp+0B0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18003afde  mov     [rsp+0B0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18003afe3  mov     [rsp+0B0h+phkResult], r12; lpcSubKeys
0x18003afe8  call    cs:__imp_RegQueryInfoKeyW
0x18003afef  nop     dword ptr [rax+rax+00h]
0x18003aff4  test    eax, eax
0x18003aff6  jz      short loc_18003B023
0x18003aff8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003afff  lea     rsi, WPP_GLOBAL_Control
0x18003b006  cmp     rcx, rsi
0x18003b009  jz      loc_18003B141
0x18003b00f  test    byte ptr [rcx+1Ch], 1
0x18003b013  jz      loc_18003B141
0x18003b019  lea     edx, [r12+12h]
0x18003b01e  jmp     loc_18003B131
0x18003b023  mov     r14d, r12d
0x18003b026  cmp     [rbp+57h+cValues], r12d
0x18003b02a  jbe     loc_18003B141
0x18003b030  lea     rsi, WPP_GLOBAL_Control
0x18003b037  mov     rcx, [rbp+57h+hKey]; hKey
0x18003b03b  lea     rax, [rbp+57h+cbData]
0x18003b03f  mov     [rsp+0B0h+lpcValues], rax; lpcbData
0x18003b044  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18003b048  lea     rax, [rbp+57h+Type]
0x18003b04c  mov     [rsp+0B0h+lpcbMaxClassLen], rdi; lpData
0x18003b051  mov     [rsp+0B0h+lpcbMaxSubKeyLen], rax; lpType
0x18003b056  mov     r8, rbx; lpValueName
0x18003b059  mov     edx, r14d; dwIndex
0x18003b05c  mov     [rsp+0B0h+phkResult], r12; lpReserved
0x18003b061  mov     [rbp+57h+cchValueName], 104h
0x18003b068  mov     [rbp+57h+cbData], 1000h
0x18003b06f  call    cs:__imp_RegEnumValueW
0x18003b076  nop     dword ptr [rax+rax+00h]
0x18003b07b  test    eax, eax
0x18003b07d  jnz     short loc_18003B0E4
0x18003b07f  cmp     [rbp+57h+Type], 1
0x18003b083  jnz     short loc_18003B0BD
0x18003b085  cmp     [rbp+57h+cchValueName], 104h
0x18003b08c  ja      short loc_18003B0BD
0x18003b08e  cmp     [rbp+57h+cbData], 1000h
0x18003b095  ja      short loc_18003B0BD
0x18003b097  cmp     [rbx], r12w
0x18003b09b  jz      short loc_18003B0E4
0x18003b09d  mov     [rbx+206h], r12w
0x18003b0a5  mov     r8, rdi; wchar_t *
0x18003b0a8  mov     rdx, rbx; wchar_t *
0x18003b0ab  mov     [rdi+0FFEh], r12w
0x18003b0b3  mov     rcx, r15; this
0x18003b0b6  call    ?AddRequest@CDataRequest@@QEAAJPEB_W0@Z; CDataRequest::AddRequest(wchar_t const *,wchar_t const *)
0x18003b0bb  jmp     short loc_18003B0E4
0x18003b0bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b0c4  cmp     rcx, rsi
0x18003b0c7  jz      short loc_18003B0E4
0x18003b0c9  test    byte ptr [rcx+1Ch], 1
0x18003b0cd  jz      short loc_18003B0E4
0x18003b0cf  mov     rcx, [rcx+10h]
0x18003b0d3  lea     r8, WPP_df4f1aef4ed33107df8087e7e060b469_Traceguids
0x18003b0da  mov     edx, 13h
0x18003b0df  call    WPP_SF_
0x18003b0e4  inc     r14d
0x18003b0e7  cmp     r14d, [rbp+57h+cValues]
0x18003b0eb  jb      loc_18003B037
0x18003b0f1  jmp     short loc_18003B141
0x18003b0f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b0fa  lea     rsi, WPP_GLOBAL_Control
0x18003b101  cmp     rcx, rsi
0x18003b104  jz      short loc_18003B141
0x18003b106  test    byte ptr [rcx+1Ch], 1
0x18003b10a  jz      short loc_18003B141
0x18003b10c  mov     edx, 11h
0x18003b111  jmp     short loc_18003B131
0x18003b113  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b11a  lea     rsi, WPP_GLOBAL_Control
0x18003b121  cmp     rcx, rsi
0x18003b124  jz      short loc_18003B141
0x18003b126  test    byte ptr [rcx+1Ch], 1
0x18003b12a  jz      short loc_18003B141
0x18003b12c  mov     edx, 10h
0x18003b131  mov     rcx, [rcx+10h]
0x18003b135  lea     r8, WPP_df4f1aef4ed33107df8087e7e060b469_Traceguids
0x18003b13c  call    WPP_SF_
0x18003b141  lea     rcx, [rbp+57h+lpData]; void *
0x18003b145  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18003b14a  lea     rcx, [rbp+57h+lpValueName]; void *
0x18003b14e  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18003b153  lea     rcx, [rbp+57h+hKey]
0x18003b157  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18003b15c  lea     r11, [rsp+0B0h+var_20]
0x18003b164  mov     rbx, [r11+30h]
0x18003b168  mov     rsi, [r11+38h]
0x18003b16c  mov     rsp, r11
0x18003b16f  pop     r15
0x18003b171  pop     r14
0x18003b173  pop     r12
0x18003b175  pop     rdi
0x18003b176  pop     rbp
0x18003b177  retn
```
