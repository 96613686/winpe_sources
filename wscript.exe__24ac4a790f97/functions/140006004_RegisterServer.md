# RegisterServer

- ea: `0x140006004`
- end: `0x14000673d`
- name: `RegisterServer`
- size: `1849`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140006c88`

## callees

- `0x140001008`
- `0x140001048`
- `0x140001338`
- `0x140006004`
- `0x140006744`
- `0x1400175a0`
- `0x140018010`

## import_xrefs

- `msvcrt!sprintf_s` at `0x140006301`
- `msvcrt!sprintf_s` at `0x14000642d`
- `msvcrt!sprintf_s` at `0x140006301`
- `msvcrt!sprintf_s` at `0x14000642d`
- `OLEAUT32!__imp_SysFreeString` at `0x14000617d`
- `OLEAUT32!__imp_SysFreeString` at `0x1400063c5`
- `OLEAUT32!__imp_SysFreeString` at `0x14000617d`
- `OLEAUT32!__imp_SysFreeString` at `0x1400063c5`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x14000623b`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x14000623b`
- `KERNEL32!GetLastError` at `0x1400060aa`
- `KERNEL32!GetLastError` at `0x140006713`
- `KERNEL32!GetLastError` at `0x1400060aa`
- `KERNEL32!GetLastError` at `0x140006713`
- `KERNEL32!GetModuleFileNameA` at `0x14000609c`
- `KERNEL32!GetModuleFileNameA` at `0x14000609c`
- `KERNEL32!MultiByteToWideChar` at `0x1400061e7`
- `KERNEL32!MultiByteToWideChar` at `0x1400061e7`
- `KERNEL32!WideCharToMultiByte` at `0x14000647f`
- `KERNEL32!WideCharToMultiByte` at `0x1400064ba`
- `KERNEL32!WideCharToMultiByte` at `0x14000647f`
- `KERNEL32!WideCharToMultiByte` at `0x1400064ba`
- `ole32!CoGetMalloc` at `0x14000607b`
- `ole32!CoGetMalloc` at `0x14000607b`
- `ole32!StringFromCLSID` at `0x1400062a2`
- `ole32!StringFromCLSID` at `0x140006409`
- `ole32!StringFromCLSID` at `0x1400062a2`
- `ole32!StringFromCLSID` at `0x140006409`
- `ADVAPI32!RegCreateKeyA` at `0x1400064ea`
- `ADVAPI32!RegCreateKeyA` at `0x140006529`
- `ADVAPI32!RegCreateKeyA` at `0x1400066a6`
- `ADVAPI32!RegCreateKeyA` at `0x1400064ea`
- `ADVAPI32!RegCreateKeyA` at `0x140006529`
- `ADVAPI32!RegCreateKeyA` at `0x1400066a6`
- `ADVAPI32!RegCloseKey` at `0x140006143`
- `ADVAPI32!RegCloseKey` at `0x140006153`
- `ADVAPI32!RegCloseKey` at `0x140006163`
- `ADVAPI32!RegCloseKey` at `0x140006172`
- `ADVAPI32!RegCloseKey` at `0x1400064d2`
- `ADVAPI32!RegCloseKey` at `0x14000650d`
- `ADVAPI32!RegCloseKey` at `0x14000668c`
- `ADVAPI32!RegCloseKey` at `0x140006143`
- `ADVAPI32!RegCloseKey` at `0x140006153`
- `ADVAPI32!RegCloseKey` at `0x140006163`
- `ADVAPI32!RegCloseKey` at `0x140006172`
- `ADVAPI32!RegCloseKey` at `0x1400064d2`
- `ADVAPI32!RegCloseKey` at `0x14000650d`
- `ADVAPI32!RegCloseKey` at `0x14000668c`
- `ADVAPI32!RegOpenKeyA` at `0x14000627c`
- `ADVAPI32!RegOpenKeyA` at `0x14000627c`
- `ADVAPI32!RegSetValueA` at `0x140006565`
- `ADVAPI32!RegSetValueA` at `0x1400065a8`
- `ADVAPI32!RegSetValueA` at `0x1400065eb`
- `ADVAPI32!RegSetValueA` at `0x14000662b`
- `ADVAPI32!RegSetValueA` at `0x140006669`
- `ADVAPI32!RegSetValueA` at `0x1400066e9`
- `ADVAPI32!RegSetValueA` at `0x140006565`
- `ADVAPI32!RegSetValueA` at `0x1400065a8`
- `ADVAPI32!RegSetValueA` at `0x1400065eb`
- `ADVAPI32!RegSetValueA` at `0x14000662b`
- `ADVAPI32!RegSetValueA` at `0x140006669`
- `ADVAPI32!RegSetValueA` at `0x1400066e9`

## string_xrefs

- `0x140006275`: `CLSID`
- `0x1400066e2`: `CLSID`

## pseudocode

```c
__int64 RegisterServer()
{
  CHAR *v0; // rsi
  int Malloc; // ebx
  signed int LastError; // eax
  ITypeLib *v3; // rcx
  __int64 v4; // rcx
  int v6; // eax
  LSTATUS v7; // eax
  unsigned int v8; // r15d
  unsigned int i; // r14d
  __int64 v10; // rcx
  const WCHAR *v11; // r8
  int v12; // ebx
  CHAR *v13; // rax
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  __int64 v16; // rax
  LSTATUS v17; // eax
  __int64 v18; // rax
  LSTATUS v19; // eax
  __int64 v20; // rax
  LSTATUS v21; // eax
  __int64 v22; // rax
  LSTATUS v23; // eax
  __int64 v24; // rax
  LSTATUS v25; // eax
  LSTATUS v26; // eax
  __int64 v27; // rax
  LSTATUS v28; // eax
  signed int v29; // eax
  HKEY v30; // [rsp+40h] [rbp-C0h] BYREF
  ITypeLib *pptlib; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  IID *v34; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  HKEY v36; // [rsp+70h] [rbp-90h] BYREF
  LPMALLOC ppMalloc; // [rsp+78h] [rbp-88h] BYREF
  IID *rclsid; // [rsp+80h] [rbp-80h] BYREF
  LPOLESTR lpsz; // [rsp+88h] [rbp-78h] BYREF
  LPOLESTR v40; // [rsp+90h] [rbp-70h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp-68h] BYREF
  CHAR Buffer[32]; // [rsp+A0h] [rbp-60h] BYREF
  CHAR SubKey[48]; // [rsp+C0h] [rbp-40h] BYREF
  CHAR Data[48]; // [rsp+F0h] [rbp-10h] BYREF
  CHAR Filename[260]; // [rsp+120h] [rbp+20h] BYREF
  char v46; // [rsp+224h] [rbp+124h]
  WCHAR WideCharStr[264]; // [rsp+230h] [rbp+130h] BYREF

  lpsz = 0;
  v0 = 0;
  v40 = 0;
  bstrString = 0;
  ppMalloc = 0;
  pptlib = 0;
  v32 = 0;
  rclsid = 0;
  v34 = 0;
  phkResult = 0;
  v30 = 0;
  hKey = 0;
  v36 = 0;
  Malloc = CoGetMalloc(1u, &ppMalloc);
  if ( Malloc < 0 )
    goto LABEL_5;
  v46 = 0;
  if ( !GetModuleFileNameA(0, Filename, 0x105u) )
    goto LABEL_3;
  if ( v46 )
  {
    Malloc = -2147024774;
    goto LABEL_5;
  }
  v6 = MultiByteToWideChar(0, 0, Filename, -1, WideCharStr, 261);
  if ( !v6 )
  {
LABEL_3:
    LastError = GetLastError();
    Malloc = LastError;
    if ( LastError > 0 )
      Malloc = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_5;
  }
  WideCharStr[v6 - 1] = 92;
  WideCharStr[v6] = 50;
  if ( 2 * (unsigned __int64)(unsigned int)(v6 + 1) >= 0x210 )
    _report_rangecheckfailure();
  WideCharStr[v6 + 1] = 0;
  Malloc = LoadTypeLibEx(WideCharStr, REGKIND_REGISTER, &pptlib);
  if ( Malloc >= 0 )
  {
    Malloc = ((__int64 (__fastcall *)(ITypeLib *, IID **))pptlib->lpVtbl->GetLibAttr)(pptlib, &rclsid);
    if ( Malloc >= 0 )
    {
      v7 = RegOpenKeyA(HKEY_CLASSES_ROOT, "CLSID", &phkResult);
      Malloc = v7;
      if ( v7 > 0 )
        Malloc = (unsigned __int16)v7 | 0x80070000;
      if ( Malloc >= 0 )
      {
        Malloc = StringFromCLSID(rclsid, &lpsz);
        if ( Malloc >= 0 )
        {
          StringCchPrintfA(Data, 0x30u, "%S", lpsz);
          ((void (__fastcall *)(LPMALLOC, LPOLESTR))ppMalloc->lpVtbl->Free)(ppMalloc, lpsz);
          sprintf_s(
            Buffer,
            0x20u,
            "%d.%d",
            *(unsigned __int16 *)rclsid[1].Data4,
            *(unsigned __int16 *)&rclsid[1].Data4[2]);
          v8 = ((__int64 (__fastcall *)(ITypeLib *))pptlib->lpVtbl->GetTypeInfoCount)(pptlib);
          for ( i = 0; i < v8; ++i )
          {
            v10 = v32;
            if ( v32 )
            {
              if ( v34 )
              {
                (*(void (**)(void))(*(_QWORD *)v32 + 152LL))();
                v10 = v32;
                v34 = 0;
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
              v32 = 0;
            }
            Malloc = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, __int64 *))pptlib->lpVtbl->GetTypeInfo)(
                       pptlib,
                       i,
                       &v32);
            if ( Malloc >= 0 )
            {
              Malloc = (*(__int64 (__fastcall **)(__int64, IID **))(*(_QWORD *)v32 + 24LL))(v32, &v34);
              if ( Malloc >= 0 && *(_DWORD *)&v34[2].Data4[4] == 5 && (v34[3].Data4[2] & 2) != 0 )
              {
                SysFreeString(bstrString);
                bstrString = 0;
                Malloc = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))pptlib->lpVtbl->GetDocumentation)(
                           pptlib,
                           i,
                           &bstrString,
                           0,
                           0,
                           0);
                if ( Malloc >= 0 )
                {
                  Malloc = StringFromCLSID(v34, &v40);
                  if ( Malloc < 0 )
                    break;
                  sprintf_s(SubKey, 0x30u, "%S", v40);
                  ((void (__fastcall *)(LPMALLOC, LPOLESTR))ppMalloc->lpVtbl->Free)(ppMalloc, v40);
                  v11 = bstrString;
                  if ( bstrString )
                  {
                    if ( v0 )
                    {
                      operator delete(v0);
                      v11 = bstrString;
                    }
                    v12 = WideCharToMultiByte(0, 0, v11, -1, 0, 0, 0, 0);
                    v13 = (CHAR *)operator new((unsigned int)(v12 + 1));
                    v0 = v13;
                    if ( !v13 )
                    {
                      Malloc = -2147024882;
                      break;
                    }
                    if ( !WideCharToMultiByte(0, 0, bstrString, -1, v13, v12, 0, 0) )
                    {
                      v29 = GetLastError();
                      Malloc = v29;
                      if ( v29 > 0 )
                        Malloc = (unsigned __int16)v29 | 0x80070000;
                      break;
                    }
                  }
                  if ( v30 )
                  {
                    RegCloseKey(v30);
                    v30 = 0;
                  }
                  v14 = RegCreateKeyA(phkResult, SubKey, &v30);
                  Malloc = v14;
                  if ( v14 > 0 )
                    Malloc = (unsigned __int16)v14 | 0x80070000;
                  if ( Malloc < 0 )
                    break;
                  if ( v36 )
                  {
                    RegCloseKey(v36);
                    v36 = 0;
                  }
                  v15 = RegCreateKeyA(v30, "LocalServer32", &v36);
                  Malloc = v15;
                  if ( v15 > 0 )
                    Malloc = (unsigned __int16)v15 | 0x80070000;
                  if ( Malloc < 0 )
                    break;
                  v16 = -1;
                  do
                    ++v16;
                  while ( Filename[v16] );
                  v17 = RegSetValueA(v36, 0, 1u, Filename, v16);
                  Malloc = v17;
                  if ( v17 > 0 )
                    Malloc = (unsigned __int16)v17 | 0x80070000;
                  if ( Malloc < 0 )
                    break;
                  v18 = -1;
                  do
                    ++v18;
                  while ( Data[v18] );
                  v19 = RegSetValueA(v30, "TypeLib", 1u, Data, v18);
                  Malloc = v19;
                  if ( v19 > 0 )
                    Malloc = (unsigned __int16)v19 | 0x80070000;
                  if ( Malloc < 0 )
                    break;
                  v20 = -1;
                  do
                    ++v20;
                  while ( Buffer[v20] );
                  v21 = RegSetValueA(v30, "Version", 1u, Buffer, v20);
                  Malloc = v21;
                  if ( v21 > 0 )
                    Malloc = (unsigned __int16)v21 | 0x80070000;
                  if ( Malloc < 0 )
                    break;
                  if ( v0 )
                  {
                    v22 = -1;
                    do
                      ++v22;
                    while ( v0[v22] );
                    v23 = RegSetValueA(v30, 0, 1u, v0, v22);
                    Malloc = v23;
                    if ( v23 > 0 )
                      Malloc = (unsigned __int16)v23 | 0x80070000;
                    if ( Malloc < 0 )
                      break;
                    v24 = -1;
                    do
                      ++v24;
                    while ( v0[v24] );
                    v25 = RegSetValueA(v30, "ProgID", 1u, v0, v24);
                    Malloc = v25;
                    if ( v25 > 0 )
                      Malloc = (unsigned __int16)v25 | 0x80070000;
                    if ( Malloc < 0 )
                      break;
                    if ( hKey )
                    {
                      RegCloseKey(hKey);
                      hKey = 0;
                    }
                    v26 = RegCreateKeyA(HKEY_CLASSES_ROOT, v0, &hKey);
                    Malloc = v26;
                    if ( v26 > 0 )
                      Malloc = (unsigned __int16)v26 | 0x80070000;
                    if ( Malloc < 0 )
                      break;
                    v27 = -1;
                    do
                      ++v27;
                    while ( SubKey[v27] );
                    v28 = RegSetValueA(hKey, "CLSID", 1u, SubKey, v27);
                    Malloc = v28;
                    if ( v28 > 0 )
                      Malloc = (unsigned __int16)v28 | 0x80070000;
                    if ( Malloc < 0 )
                      break;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_5:
  if ( ppMalloc )
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  v3 = pptlib;
  if ( pptlib )
  {
    if ( rclsid )
    {
      ((void (*)(void))pptlib->lpVtbl->ReleaseTLibAttr)();
      v3 = pptlib;
    }
    ((void (__fastcall *)(ITypeLib *))v3->lpVtbl->Release)(v3);
  }
  v4 = v32;
  if ( v32 )
  {
    if ( v34 )
    {
      (*(void (**)(void))(*(_QWORD *)v32 + 152LL))();
      v4 = v32;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v36 )
    RegCloseKey(v36);
  if ( v30 )
    RegCloseKey(v30);
  if ( phkResult )
    RegCloseKey(phkResult);
  SysFreeString(bstrString);
  if ( v0 )
    operator delete(v0);
  return (unsigned int)Malloc;
}

```

## disassembly

```asm
0x140006004  push    rbp
0x140006006  push    rbx
0x140006007  push    rsi
0x140006008  push    rdi
0x140006009  push    r12
0x14000600b  push    r13
0x14000600d  push    r14
0x14000600f  push    r15
0x140006011  lea     rbp, [rsp-358h]
0x140006019  sub     rsp, 458h
0x140006020  mov     rax, cs:__security_cookie
0x140006027  xor     rax, rsp
0x14000602a  mov     [rbp+390h+var_50], rax
0x140006031  xor     r12d, r12d
0x140006034  lea     rdx, [rsp+490h+ppMalloc]; ppMalloc
0x140006039  mov     [rbp+390h+lpsz], r12
0x14000603d  mov     esi, r12d
0x140006040  mov     [rbp+390h+var_400], r12
0x140006044  mov     [rsp+490h+bstrString], r12
0x140006049  lea     edi, [r12+1]
0x14000604e  mov     [rsp+490h+ppMalloc], r12
0x140006053  mov     ecx, edi; dwMemContext
0x140006055  mov     [rsp+490h+pptlib], r12
0x14000605a  mov     [rsp+490h+var_440], r12
0x14000605f  mov     [rbp+390h+rclsid], r12
0x140006063  mov     [rsp+490h+var_430], r12
0x140006068  mov     [rbp+390h+phkResult], r12
0x14000606c  mov     [rsp+490h+var_450], r12
0x140006071  mov     [rsp+490h+hKey], r12
0x140006076  mov     [rsp+490h+var_420], r12
0x14000607b  call    cs:__imp_CoGetMalloc
0x140006081  mov     ebx, eax
0x140006083  test    eax, eax
0x140006085  js      short loc_1400060BF
0x140006087  mov     ebx, 105h
0x14000608c  mov     [rbp+390h+var_26C], r12b
0x140006093  mov     r8d, ebx; nSize
0x140006096  lea     rdx, [rbp+390h+Filename]; lpFilename
0x14000609a  xor     ecx, ecx; hModule
0x14000609c  call    cs:__imp_GetModuleFileNameA
0x1400060a2  test    eax, eax
0x1400060a4  jnz     loc_1400061B5
0x1400060aa  call    cs:__imp_GetLastError
0x1400060b0  mov     ebx, eax
0x1400060b2  test    eax, eax
0x1400060b4  jle     short loc_1400060BF
0x1400060b6  movzx   ebx, ax
0x1400060b9  or      ebx, 80070000h
0x1400060bf  mov     rcx, [rsp+490h+ppMalloc]
0x1400060c4  test    rcx, rcx
0x1400060c7  jz      short loc_1400060D5
0x1400060c9  mov     rax, [rcx]
0x1400060cc  mov     rax, [rax+10h]
0x1400060d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060d5  mov     rcx, [rsp+490h+pptlib]
0x1400060da  test    rcx, rcx
0x1400060dd  jz      short loc_140006105
0x1400060df  mov     rdx, [rbp+390h+rclsid]
0x1400060e3  test    rdx, rdx
0x1400060e6  jz      short loc_1400060F9
0x1400060e8  mov     rax, [rcx]
0x1400060eb  mov     rax, [rax+60h]
0x1400060ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060f4  mov     rcx, [rsp+490h+pptlib]
0x1400060f9  mov     rax, [rcx]
0x1400060fc  mov     rax, [rax+10h]
0x140006100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006105  mov     rcx, [rsp+490h+var_440]
0x14000610a  test    rcx, rcx
0x14000610d  jz      short loc_140006139
0x14000610f  mov     rdx, [rsp+490h+var_430]
0x140006114  test    rdx, rdx
0x140006117  jz      short loc_14000612D
0x140006119  mov     rax, [rcx]
0x14000611c  mov     rax, [rax+98h]
0x140006123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006128  mov     rcx, [rsp+490h+var_440]
0x14000612d  mov     rax, [rcx]
0x140006130  mov     rax, [rax+10h]
0x140006134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006139  mov     rcx, [rsp+490h+hKey]; hKey
0x14000613e  test    rcx, rcx
0x140006141  jz      short loc_140006149
0x140006143  call    cs:__imp_RegCloseKey
0x140006149  mov     rcx, [rsp+490h+var_420]; hKey
0x14000614e  test    rcx, rcx
0x140006151  jz      short loc_140006159
0x140006153  call    cs:__imp_RegCloseKey
0x140006159  mov     rcx, [rsp+490h+var_450]; hKey
0x14000615e  test    rcx, rcx
0x140006161  jz      short loc_140006169
0x140006163  call    cs:__imp_RegCloseKey
0x140006169  mov     rcx, [rbp+390h+phkResult]; hKey
0x14000616d  test    rcx, rcx
0x140006170  jz      short loc_140006178
0x140006172  call    cs:__imp_RegCloseKey
0x140006178  mov     rcx, [rsp+490h+bstrString]; bstrString
0x14000617d  call    cs:__imp_SysFreeString
0x140006183  test    rsi, rsi
0x140006186  jz      short loc_140006190
0x140006188  mov     rcx, rsi; Block
0x14000618b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140006190  mov     eax, ebx
0x140006192  mov     rcx, [rbp+390h+var_50]
0x140006199  xor     rcx, rsp; StackCookie
0x14000619c  call    __security_check_cookie
0x1400061a1  add     rsp, 458h
0x1400061a8  pop     r15
0x1400061aa  pop     r14
0x1400061ac  pop     r13
0x1400061ae  pop     r12
0x1400061b0  pop     rdi
0x1400061b1  pop     rsi
0x1400061b2  pop     rbx
0x1400061b3  pop     rbp
0x1400061b4  retn
0x1400061b5  cmp     [rbp+390h+var_26C], r12b
0x1400061bc  jz      short loc_1400061C8
0x1400061be  mov     ebx, 8007007Ah
0x1400061c3  jmp     loc_1400060BF
0x1400061c8  lea     rax, [rbp+390h+WideCharStr]
0x1400061cf  mov     [rsp+490h+cchWideChar], ebx; cchWideChar
0x1400061d3  or      r13, 0FFFFFFFFFFFFFFFFh
0x1400061d7  mov     [rsp+490h+lpWideCharStr], rax; lpWideCharStr
0x1400061dc  mov     r9d, r13d; cbMultiByte
0x1400061df  lea     r8, [rbp+390h+Filename]; lpMultiByteStr
0x1400061e3  xor     edx, edx; dwFlags
0x1400061e5  xor     ecx, ecx; CodePage
0x1400061e7  call    cs:__imp_MultiByteToWideChar
0x1400061ed  mov     edx, eax
0x1400061ef  test    eax, eax
0x1400061f1  jz      loc_1400060AA
0x1400061f7  lea     ecx, [rdx-1]
0x1400061fa  lea     eax, [r13+5Dh]
0x1400061fe  mov     [rbp+rcx*2+390h+WideCharStr], ax
0x140006206  lea     ecx, [rax-2Ah]
0x140006209  mov     [rbp+rdx*2+390h+WideCharStr], cx
0x140006211  lea     ecx, [rdx+1]
0x140006214  add     rcx, rcx
0x140006217  cmp     rcx, 210h
0x14000621e  jnb     loc_140006737
0x140006224  mov     [rbp+rcx+390h+WideCharStr], r12w
0x14000622d  lea     r8, [rsp+490h+pptlib]; pptlib
0x140006232  lea     rcx, [rbp+390h+WideCharStr]; szFile
0x140006239  mov     edx, edi; regkind
0x14000623b  call    cs:__imp_LoadTypeLibEx
0x140006241  mov     ebx, eax
0x140006243  test    eax, eax
0x140006245  js      loc_1400060BF
0x14000624b  mov     rcx, [rsp+490h+pptlib]
0x140006250  lea     rdx, [rbp+390h+rclsid]
0x140006254  mov     rax, [rcx]
0x140006257  mov     rax, [rax+38h]
0x14000625b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006260  mov     ebx, eax
0x140006262  test    eax, eax
0x140006264  js      loc_1400060BF
0x14000626a  lea     r8, [rbp+390h+phkResult]; phkResult
0x14000626e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140006275  lea     rdx, SubKey; "CLSID"
0x14000627c  call    cs:__imp_RegOpenKeyA
0x140006282  mov     ebx, eax
0x140006284  mov     edi, 80070000h
0x140006289  test    eax, eax
0x14000628b  jle     short loc_140006292
0x14000628d  movzx   ebx, ax
0x140006290  or      ebx, edi
0x140006292  test    ebx, ebx
0x140006294  js      loc_1400060BF
0x14000629a  mov     rcx, [rbp+390h+rclsid]; rclsid
0x14000629e  lea     rdx, [rbp+390h+lpsz]; lplpsz
0x1400062a2  call    cs:__imp_StringFromCLSID
0x1400062a8  mov     ebx, eax
0x1400062aa  test    eax, eax
0x1400062ac  js      loc_1400060BF
0x1400062b2  mov     r9, [rbp+390h+lpsz]
0x1400062b6  lea     r8, aS_0; "%S"
0x1400062bd  mov     edx, 30h ; '0'; unsigned __int64
0x1400062c2  lea     rcx, [rbp+390h+Data]; char *
0x1400062c6  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1400062cb  mov     rcx, [rsp+490h+ppMalloc]
0x1400062d0  mov     rdx, [rbp+390h+lpsz]
0x1400062d4  mov     rax, [rcx]
0x1400062d7  mov     rax, [rax+28h]
0x1400062db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062e0  mov     rax, [rbp+390h+rclsid]
0x1400062e4  lea     r8, Format; "%d.%d"
0x1400062eb  mov     edx, 20h ; ' '; BufferCount
0x1400062f0  movzx   ecx, word ptr [rax+1Ah]
0x1400062f4  movzx   r9d, word ptr [rax+18h]
0x1400062f9  mov     dword ptr [rsp+490h+lpWideCharStr], ecx
0x1400062fd  lea     rcx, [rbp+390h+Buffer]; Buffer
0x140006301  call    cs:__imp_sprintf_s
0x140006307  mov     rcx, [rsp+490h+pptlib]
0x14000630c  mov     rax, [rcx]
0x14000630f  mov     rax, [rax+18h]
0x140006313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006318  mov     r15d, eax
0x14000631b  mov     r14d, r12d
0x14000631e  test    eax, eax
0x140006320  jz      loc_1400060BF
0x140006326  mov     rcx, [rsp+490h+var_440]
0x14000632b  test    rcx, rcx
0x14000632e  jz      short loc_140006364
0x140006330  mov     rdx, [rsp+490h+var_430]
0x140006335  test    rdx, rdx
0x140006338  jz      short loc_140006353
0x14000633a  mov     rax, [rcx]
0x14000633d  mov     rax, [rax+98h]
0x140006344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006349  mov     rcx, [rsp+490h+var_440]
0x14000634e  mov     [rsp+490h+var_430], r12
0x140006353  mov     rax, [rcx]
0x140006356  mov     rax, [rax+10h]
0x14000635a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000635f  mov     [rsp+490h+var_440], r12
0x140006364  mov     rcx, [rsp+490h+pptlib]
0x140006369  lea     r8, [rsp+490h+var_440]
0x14000636e  mov     edx, r14d
0x140006371  mov     rax, [rcx]
0x140006374  mov     rax, [rax+20h]
0x140006378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000637d  mov     ebx, eax
0x14000637f  test    eax, eax
0x140006381  js      loc_140006702
0x140006387  mov     rcx, [rsp+490h+var_440]
0x14000638c  lea     rdx, [rsp+490h+var_430]
0x140006391  mov     rax, [rcx]
0x140006394  mov     rax, [rax+18h]
0x140006398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000639d  mov     ebx, eax
0x14000639f  test    eax, eax
0x1400063a1  js      loc_140006702
0x1400063a7  mov     rdx, [rsp+490h+var_430]
0x1400063ac  cmp     dword ptr [rdx+2Ch], 5
0x1400063b0  jnz     loc_140006702
0x1400063b6  test    byte ptr [rdx+3Ah], 2
0x1400063ba  jz      loc_140006702
0x1400063c0  mov     rcx, [rsp+490h+bstrString]; bstrString
0x1400063c5  call    cs:__imp_SysFreeString
0x1400063cb  mov     rcx, [rsp+490h+pptlib]
0x1400063d0  lea     r8, [rsp+490h+bstrString]
0x1400063d5  mov     [rsp+490h+bstrString], r12
0x1400063da  xor     r9d, r9d
0x1400063dd  mov     qword ptr [rsp+490h+cchWideChar], r12
0x1400063e2  mov     edx, r14d
0x1400063e5  mov     [rsp+490h+lpWideCharStr], r12
0x1400063ea  mov     rax, [rcx]
0x1400063ed  mov     rax, [rax+48h]
0x1400063f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400063f6  mov     ebx, eax
0x1400063f8  test    eax, eax
0x1400063fa  js      loc_140006702
0x140006400  mov     rcx, [rsp+490h+var_430]; rclsid
0x140006405  lea     rdx, [rbp+390h+var_400]; lplpsz
0x140006409  call    cs:__imp_StringFromCLSID
0x14000640f  mov     ebx, eax
0x140006411  test    eax, eax
0x140006413  js      loc_1400060BF
0x140006419  mov     r9, [rbp+390h+var_400]
0x14000641d  lea     r8, aS_0; "%S"
0x140006424  mov     edx, 30h ; '0'; BufferCount
0x140006429  lea     rcx, [rbp+390h+SubKey]; Buffer
0x14000642d  call    cs:__imp_sprintf_s
0x140006433  mov     rcx, [rsp+490h+ppMalloc]
0x140006438  mov     rdx, [rbp+390h+var_400]
0x14000643c  mov     rax, [rcx]
0x14000643f  mov     rax, [rax+28h]
0x140006443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006448  mov     r8, [rsp+490h+bstrString]
0x14000644d  test    r8, r8
0x140006450  jz      short loc_1400064C8
0x140006452  test    rsi, rsi
0x140006455  jz      short loc_140006464
0x140006457  mov     rcx, rsi; Block
0x14000645a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000645f  mov     r8, [rsp+490h+bstrString]; lpWideCharStr
0x140006464  mov     [rsp+490h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x140006469  mov     r9d, r13d; cchWideChar
0x14000646c  mov     [rsp+490h+lpDefaultChar], r12; lpDefaultChar
0x140006471  xor     edx, edx; dwFlags
0x140006473  mov     [rsp+490h+cchWideChar], r12d; cbMultiByte
0x140006478  xor     ecx, ecx; CodePage
0x14000647a  mov     [rsp+490h+lpWideCharStr], r12; lpMultiByteStr
0x14000647f  call    cs:__imp_WideCharToMultiByte
0x140006485  mov     ebx, eax
0x140006487  lea     ecx, [rax+1]; Size
0x14000648a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000648f  mov     rsi, rax
0x140006492  test    rax, rax
0x140006495  jz      loc_14000672D
0x14000649b  mov     r8, [rsp+490h+bstrString]; lpWideCharStr
0x1400064a0  mov     r9d, r13d; cchWideChar
0x1400064a3  mov     [rsp+490h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x1400064a8  xor     edx, edx; dwFlags
0x1400064aa  mov     [rsp+490h+lpDefaultChar], r12; lpDefaultChar
0x1400064af  xor     ecx, ecx; CodePage
0x1400064b1  mov     [rsp+490h+cchWideChar], ebx; cbMultiByte
0x1400064b5  mov     [rsp+490h+lpWideCharStr], rax; lpMultiByteStr
0x1400064ba  call    cs:__imp_WideCharToMultiByte
  ... truncated ...
```
