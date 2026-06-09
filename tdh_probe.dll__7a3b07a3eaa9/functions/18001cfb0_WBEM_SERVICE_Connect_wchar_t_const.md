# WBEM_SERVICE::Connect(wchar_t const *)

- ea: `0x18001cfb0`
- end: `0x18001d1c9`
- name: `?Connect@WBEM_SERVICE@@QEAAKPEB_W@Z`
- size: `537`
- prototype: `__int64 __fastcall(WBEM_SERVICE *this, const wchar_t *)`
- caller_count: `8`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180014ff4`
- `0x1800172a0`
- `0x18001cdcc`
- `0x1800245f4`
- `0x1800247d0`
- `0x18002b2c0`
- `0x18002b380`
- `0x18002b4e0`

## callees

- `0x180012fd0`
- `0x1800159ac`
- `0x18001cfb0`
- `0x18001d1d0`
- `0x18001eb98`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001cfea`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001cfea`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d053`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d053`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001d008`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001d008`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001d16b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001d16b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001d06d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001d06d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d0dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d0dd`

## pseudocode

```c
__int64 __fastcall WBEM_SERVICE::Connect(WBEM_SERVICE *this, const wchar_t *a2)
{
  size_t v4; // rax
  unsigned int v5; // ebx
  int v6; // r14d
  wchar_t *v7; // rax
  BSTR v8; // rbx
  HRESULT Instance; // edi
  HRESULT v10; // eax
  char v11; // al
  __int64 v12; // rcx
  LPVOID ppv[4]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v15; // [rsp+98h] [rbp+28h] BYREF
  BSTR v16; // [rsp+A0h] [rbp+30h] BYREF

  v15 = 0;
  v16 = 0;
  if ( !a2 )
  {
    v8 = SysAllocString(L"root\\wmi");
    v16 = v8;
    if ( v8 )
    {
LABEL_8:
      v10 = CoInitializeEx(0, 0);
      Instance = v10;
      if ( v10 == -2147417850 )
      {
        v11 = 0;
LABEL_13:
        *((_BYTE *)this + 8) = v11;
        ppv[0] = 0;
        ppv[1] = &v15;
        v12 = v15;
        v15 = 0;
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        Instance = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, ppv);
        utl::out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>::~out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>(ppv);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, WBEM_SERVICE *))(*(_QWORD *)v15 + 24LL))(
                       v15,
                       v8,
                       0,
                       0,
                       0,
                       0,
                       0,
                       0,
                       this);
          if ( Instance >= 0 )
          {
            Instance = CoSetProxyBlanket(
                         *(IUnknown **)this,
                         0xFFFFFFFF,
                         0xFFFFFFFF,
                         (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                         4u,
                         3u,
                         0,
                         0x40u);
            if ( Instance == -2147467262 )
              Instance = 0;
          }
        }
        goto LABEL_19;
      }
      if ( v10 >= 0 )
      {
        v11 = 1;
        goto LABEL_13;
      }
      *((_BYTE *)this + 8) = 0;
LABEL_19:
      utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v16);
      std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v15);
      return (Instance >> 31) & 0x1070;
    }
LABEL_20:
    v5 = 8;
    goto LABEL_21;
  }
  v4 = wcsnlen(a2, 0x7FFFFFF4u);
  if ( v4 != 2147483636 )
  {
    v6 = v4 + 11;
    v7 = SysAllocStringLen(0, (int)v4 + 11);
    v8 = v7;
    v16 = v7;
    if ( v7 )
    {
      Instance = StringCchPrintfW(v7, (unsigned int)(v6 + 1), L"\\\\%ls\\%ls", a2, L"root\\wmi");
      if ( Instance < 0 )
        goto LABEL_19;
      goto LABEL_8;
    }
    goto LABEL_20;
  }
  v5 = 87;
LABEL_21:
  utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v16);
  std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v15);
  return v5;
}

```

## disassembly

```asm
0x18001cfb0  mov     [rsp-18h+arg_0], rbx
0x18001cfb5  mov     [rsp-18h+arg_18], rsi
0x18001cfba  push    rbp
0x18001cfbb  push    rdi
0x18001cfbc  push    r14
0x18001cfbe  mov     rbp, rsp
0x18001cfc1  sub     rsp, 70h
0x18001cfc5  mov     rdi, rdx
0x18001cfc8  mov     rsi, rcx
0x18001cfcb  mov     [rbp+arg_8], 0
0x18001cfd3  mov     [rbp+arg_10], 0
0x18001cfdb  test    rdx, rdx
0x18001cfde  jz      short loc_18001D04C
0x18001cfe0  mov     ebx, 7FFFFFF4h
0x18001cfe5  mov     edx, ebx; MaxCount
0x18001cfe7  mov     rcx, rdi; Source
0x18001cfea  call    cs:__imp_wcsnlen
0x18001cff0  cmp     rax, rbx
0x18001cff3  jnz     short loc_18001CFFF
0x18001cff5  mov     ebx, 57h ; 'W'
0x18001cffa  jmp     loc_18001D1A0
0x18001cfff  lea     r14d, [rax+0Bh]
0x18001d003  mov     edx, r14d; ui
0x18001d006  xor     ecx, ecx; strIn
0x18001d008  call    cs:__imp_SysAllocStringLen
0x18001d00e  mov     rbx, rax
0x18001d011  mov     [rbp+arg_10], rax
0x18001d015  test    rax, rax
0x18001d018  jz      loc_18001D19B
0x18001d01e  lea     edx, [r14+1]; unsigned __int64
0x18001d022  lea     rcx, aRootWmi; "root\\wmi"
0x18001d029  mov     [rsp+70h+ppv], rcx
0x18001d02e  mov     r9, rdi
0x18001d031  lea     r8, aLsLs; "\\\\%ls\\%ls"
0x18001d038  mov     rcx, rax; wchar_t *
0x18001d03b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001d040  mov     edi, eax
0x18001d042  test    eax, eax
0x18001d044  js      loc_18001D17C
0x18001d04a  jmp     short loc_18001D069
0x18001d04c  lea     rcx, aRootWmi; "root\\wmi"
0x18001d053  call    cs:__imp_SysAllocString
0x18001d059  mov     rbx, rax
0x18001d05c  mov     [rbp+arg_10], rax
0x18001d060  test    rax, rax
0x18001d063  jz      loc_18001D19B
0x18001d069  xor     edx, edx; dwCoInit
0x18001d06b  xor     ecx, ecx; pvReserved
0x18001d06d  call    cs:__imp_CoInitializeEx
0x18001d073  mov     edi, eax
0x18001d075  cmp     eax, 80010106h
0x18001d07a  jnz     short loc_18001D080
0x18001d07c  xor     al, al
0x18001d07e  jmp     short loc_18001D08F
0x18001d080  test    eax, eax
0x18001d082  jns     short loc_18001D08D
0x18001d084  mov     byte ptr [rsi+8], 0
0x18001d088  jmp     loc_18001D17C
0x18001d08d  mov     al, 1
0x18001d08f  mov     [rsi+8], al
0x18001d092  mov     [rbp+var_20], 0
0x18001d09a  lea     rax, [rbp+arg_8]
0x18001d09e  mov     [rbp+var_18], rax
0x18001d0a2  mov     rcx, [rbp+arg_8]
0x18001d0a6  mov     [rbp+arg_8], 0
0x18001d0ae  test    rcx, rcx
0x18001d0b1  jz      short loc_18001D0C0
0x18001d0b3  mov     rax, [rcx]
0x18001d0b6  mov     rax, [rax+10h]
0x18001d0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0bf  nop
0x18001d0c0  lea     rax, [rbp+var_20]
0x18001d0c4  mov     [rsp+70h+ppv], rax; ppv
0x18001d0c9  lea     r9, IID_IWbemLocator; riid
0x18001d0d0  xor     edx, edx; pUnkOuter
0x18001d0d2  lea     r8d, [rdx+1]; dwClsContext
0x18001d0d6  lea     rcx, CLSID_WbemLocator; rclsid
0x18001d0dd  call    cs:__imp_CoCreateInstance
0x18001d0e3  mov     edi, eax
0x18001d0e5  lea     rcx, [rbp+var_20]
0x18001d0e9  call    ??1?$out_ptr_t@V?$unique_ptr@UIWbemQualifierSet@@Urelease_delete@tlx@@@utl@@PEAUIWbemQualifierSet@@$$V@utl@@QEAA@XZ; utl::out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>::~out_ptr_t<utl::unique_ptr<IWbemQualifierSet,tlx::release_delete>,IWbemQualifierSet *,>(void)
0x18001d0ee  test    edi, edi
0x18001d0f0  js      loc_18001D17C
0x18001d0f6  mov     rcx, [rbp+arg_8]
0x18001d0fa  mov     rax, [rcx]
0x18001d0fd  mov     [rsp+70h+var_30], rsi
0x18001d102  mov     qword ptr [rsp+70h+dwCapabilities], 0
0x18001d10b  mov     [rsp+70h+pAuthInfo], 0
0x18001d114  mov     [rsp+70h+dwImpLevel], 0
0x18001d11c  mov     [rsp+70h+ppv], 0
0x18001d125  xor     r9d, r9d
0x18001d128  xor     r8d, r8d
0x18001d12b  mov     rdx, rbx
0x18001d12e  mov     rax, [rax+18h]
0x18001d132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d137  mov     edi, eax
0x18001d139  test    eax, eax
0x18001d13b  js      short loc_18001D17C
0x18001d13d  mov     [rsp+70h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18001d145  mov     [rsp+70h+pAuthInfo], 0; pAuthInfo
0x18001d14e  mov     [rsp+70h+dwImpLevel], 3; dwImpLevel
0x18001d156  mov     dword ptr [rsp+70h+ppv], 4; dwAuthnLevel
0x18001d15e  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001d162  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001d165  mov     r8d, edx; dwAuthzSvc
0x18001d168  mov     rcx, [rsi]; pProxy
0x18001d16b  call    cs:__imp_CoSetProxyBlanket
0x18001d171  mov     edi, eax
0x18001d173  cmp     eax, 80004002h
0x18001d178  jnz     short loc_18001D17C
0x18001d17a  xor     edi, edi
0x18001d17c  sar     edi, 1Fh
0x18001d17f  and     edi, 1070h
0x18001d185  lea     rcx, [rbp+arg_10]
0x18001d189  call    ??1?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x18001d18e  lea     rcx, [rbp+arg_8]
0x18001d192  call    ??1?$unique_ptr@UIUnknown@@UReleaseDelete@XmlReader@@@std@@QEAA@XZ; std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(void)
0x18001d197  mov     eax, edi
0x18001d199  jmp     short loc_18001D1B4
0x18001d19b  mov     ebx, 8
0x18001d1a0  lea     rcx, [rbp+arg_10]
0x18001d1a4  call    ??1?$unique_ptr@$$BY0A@_WUsysfreestring_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(void)
0x18001d1a9  lea     rcx, [rbp+arg_8]
0x18001d1ad  call    ??1?$unique_ptr@UIUnknown@@UReleaseDelete@XmlReader@@@std@@QEAA@XZ; std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(void)
0x18001d1b2  mov     eax, ebx
0x18001d1b4  lea     r11, [rsp+70h+var_s0]
0x18001d1b9  mov     rbx, [r11+20h]
0x18001d1bd  mov     rsi, [r11+38h]
0x18001d1c1  mov     rsp, r11
0x18001d1c4  pop     r14
0x18001d1c6  pop     rdi
0x18001d1c7  pop     rbp
0x18001d1c8  retn
```
