# GetTypeLibraryFromTypeLibKey

- ea: `0x180044180`
- end: `0x1800444a5`
- name: `GetTypeLibraryFromTypeLibKey`
- size: `805`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800662f0`

## callees

- `0x180044180`
- `0x180047098`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `msvcrt!atoi` at `0x180044369`
- `msvcrt!atoi` at `0x180044384`
- `msvcrt!atoi` at `0x180044369`
- `msvcrt!atoi` at `0x180044384`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800443f8`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800443f8`
- `KERNEL32!MultiByteToWideChar` at `0x1800443b1`
- `KERNEL32!MultiByteToWideChar` at `0x1800443b1`
- `OLE32!CLSIDFromString` at `0x1800443ca`
- `OLE32!CLSIDFromString` at `0x1800443ca`
- `ADVAPI32!RegOpenKeyExA` at `0x18004420a`
- `ADVAPI32!RegOpenKeyExA` at `0x1800442bd`
- `ADVAPI32!RegOpenKeyExA` at `0x18004420a`
- `ADVAPI32!RegOpenKeyExA` at `0x1800442bd`
- `ADVAPI32!RegCloseKey` at `0x180044434`
- `ADVAPI32!RegCloseKey` at `0x180044453`
- `ADVAPI32!RegCloseKey` at `0x180044434`
- `ADVAPI32!RegCloseKey` at `0x180044453`
- `ADVAPI32!RegQueryValueExA` at `0x180044251`
- `ADVAPI32!RegQueryValueExA` at `0x1800442ff`
- `ADVAPI32!RegQueryValueExA` at `0x180044251`
- `ADVAPI32!RegQueryValueExA` at `0x1800442ff`

## pseudocode

```c
__int64 __fastcall GetTypeLibraryFromTypeLibKey(HKEY hKey, ITypeLib **a2)
{
  LSTATUS v4; // eax
  int v5; // ebx
  LSTATUS v6; // eax
  __int64 v7; // rax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  const char *v10; // rdi
  __int64 i; // rbx
  WORD v12; // si
  WORD v13; // di
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD lpcbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  ITypeLib *pptlib; // [rsp+50h] [rbp-B0h] BYREF
  CLSID pclsid; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v22[16]; // [rsp+68h] [rbp-98h] BYREF
  CHAR Data[56]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR WideCharStr[48]; // [rsp+B0h] [rbp-50h] BYREF

  *a2 = 0;
  hKeya = 0;
  phkResult = 0;
  cbData = 48;
  lpcbData = 10;
  pclsid = 0;
  Type = 0;
  pptlib = 0;
  v4 = RegOpenKeyExA(hKey, "TypeLib", 0, 0x20019u, &hKeya);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    v6 = RegQueryValueExA(hKeya, 0, 0, &Type, (LPBYTE)Data, &cbData);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v5 >= 0 )
    {
      if ( Type != 1 )
        goto LABEL_32;
      if ( !cbData )
        goto LABEL_32;
      v7 = cbData - 1;
      if ( (unsigned int)v7 >= 0x2F )
        goto LABEL_32;
      Data[v7] = 0;
      v8 = RegOpenKeyExA(hKey, "Version", 0, 0x20019u, &phkResult);
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      if ( v5 >= 0 )
      {
        v9 = RegQueryValueExA(phkResult, 0, 0, &Type, v22, &lpcbData);
        v5 = v9;
        if ( v9 > 0 )
          v5 = (unsigned __int16)v9 | 0x80070000;
        if ( v5 >= 0 )
        {
          if ( Type == 1 && lpcbData )
          {
            v10 = 0;
            for ( i = 0; (unsigned int)i < lpcbData; i = (unsigned int)(i + 1) )
            {
              if ( v22[i] == 46 )
              {
                if ( (unsigned int)i >= 0xAuLL )
                  _report_rangecheckfailure();
                v22[i] = 0;
                v10 = (const char *)&v22[(unsigned int)(i + 1)];
                break;
              }
            }
            v12 = atoi((const char *)v22);
            v13 = (_DWORD)i == lpcbData ? 0 : atoi(v10);
            if ( MultiByteToWideChar(0, 0, Data, -1, WideCharStr, 48) )
            {
              v5 = CLSIDFromString(WideCharStr, &pclsid);
              if ( v5 >= 0 )
              {
                v5 = LoadRegTypeLib(&pclsid, v12, v13, 0x400u, &pptlib);
                if ( v5 >= 0 )
                {
                  v5 = 0;
                  *a2 = pptlib;
                  pptlib = 0;
                }
              }
              goto LABEL_33;
            }
          }
LABEL_32:
          v5 = -2147467259;
        }
      }
    }
  }
LABEL_33:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( pptlib )
    ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180044180  mov     [rsp-8+arg_10], rbx
0x180044185  mov     [rsp-8+arg_18], rsi
0x18004418a  push    rbp
0x18004418b  push    rdi
0x18004418c  push    r14
0x18004418e  lea     rbp, [rsp-20h]
0x180044193  sub     rsp, 120h
0x18004419a  mov     rax, cs:__security_cookie
0x1800441a1  xor     rax, rsp
0x1800441a4  mov     [rbp+30h+var_20], rax
0x1800441a8  mov     r14, rdx
0x1800441ab  mov     qword ptr [rdx], 0
0x1800441b2  xorps   xmm0, xmm0
0x1800441b5  mov     [rsp+130h+hKey], 0
0x1800441be  lea     rax, [rsp+130h+hKey]
0x1800441c3  mov     [rsp+130h+var_E8], 0
0x1800441cc  lea     rdx, aTypelib; "TypeLib"
0x1800441d3  mov     [rsp+130h+phkResult], rax; phkResult
0x1800441d8  mov     r9d, 20019h; samDesired
0x1800441de  mov     [rsp+130h+cbData], 30h ; '0'
0x1800441e6  xor     r8d, r8d; ulOptions
0x1800441e9  mov     [rsp+130h+var_FC], 0Ah
0x1800441f1  movups  xmmword ptr [rsp+130h+pclsid.Data1], xmm0
0x1800441f6  mov     rdi, rcx
0x1800441f9  mov     [rsp+130h+Type], 0
0x180044201  mov     [rsp+130h+pptlib], 0
0x18004420a  call    cs:__imp_RegOpenKeyExA
0x180044211  nop     dword ptr [rax+rax+00h]
0x180044216  mov     ebx, eax
0x180044218  mov     esi, 80070000h
0x18004421d  test    eax, eax
0x18004421f  jle     short loc_180044226
0x180044221  movzx   ebx, ax
0x180044224  or      ebx, esi
0x180044226  test    ebx, ebx
0x180044228  js      loc_18004442A
0x18004422e  mov     rcx, [rsp+130h+hKey]; hKey
0x180044233  lea     rax, [rsp+130h+cbData]
0x180044238  mov     [rsp+130h+lpcbData], rax; lpcbData
0x18004423d  lea     r9, [rsp+130h+Type]; lpType
0x180044242  lea     rax, [rsp+130h+Data]
0x180044247  xor     r8d, r8d; lpReserved
0x18004424a  xor     edx, edx; lpValueName
0x18004424c  mov     [rsp+130h+phkResult], rax; lpData
0x180044251  call    cs:__imp_RegQueryValueExA
0x180044258  nop     dword ptr [rax+rax+00h]
0x18004425d  mov     ebx, eax
0x18004425f  test    eax, eax
0x180044261  jle     short loc_180044268
0x180044263  movzx   ebx, ax
0x180044266  or      ebx, esi
0x180044268  test    ebx, ebx
0x18004426a  js      loc_18004442A
0x180044270  cmp     [rsp+130h+Type], 1
0x180044275  jnz     loc_180044425
0x18004427b  mov     eax, [rsp+130h+cbData]
0x18004427f  test    eax, eax
0x180044281  jz      loc_180044425
0x180044287  dec     eax
0x180044289  cmp     eax, 2Fh ; '/'
0x18004428c  jnb     loc_180044425
0x180044292  cmp     eax, 30h ; '0'
0x180044295  jnb     loc_18004441F
0x18004429b  mov     [rsp+rax+130h+Data], 0
0x1800442a0  lea     rdx, aVersion; "Version"
0x1800442a7  lea     rax, [rsp+130h+var_E8]
0x1800442ac  mov     r9d, 20019h; samDesired
0x1800442b2  xor     r8d, r8d; ulOptions
0x1800442b5  mov     [rsp+130h+phkResult], rax; phkResult
0x1800442ba  mov     rcx, rdi; hKey
0x1800442bd  call    cs:__imp_RegOpenKeyExA
0x1800442c4  nop     dword ptr [rax+rax+00h]
0x1800442c9  mov     ebx, eax
0x1800442cb  test    eax, eax
0x1800442cd  jle     short loc_1800442D4
0x1800442cf  movzx   ebx, ax
0x1800442d2  or      ebx, esi
0x1800442d4  test    ebx, ebx
0x1800442d6  js      loc_18004442A
0x1800442dc  mov     rcx, [rsp+130h+var_E8]; hKey
0x1800442e1  lea     rax, [rsp+130h+var_FC]
0x1800442e6  mov     [rsp+130h+lpcbData], rax; lpcbData
0x1800442eb  lea     r9, [rsp+130h+Type]; lpType
0x1800442f0  lea     rax, [rsp+130h+var_C8]
0x1800442f5  xor     r8d, r8d; lpReserved
0x1800442f8  xor     edx, edx; lpValueName
0x1800442fa  mov     [rsp+130h+phkResult], rax; lpData
0x1800442ff  call    cs:__imp_RegQueryValueExA
0x180044306  nop     dword ptr [rax+rax+00h]
0x18004430b  mov     ebx, eax
0x18004430d  test    eax, eax
0x18004430f  jle     short loc_180044316
0x180044311  movzx   ebx, ax
0x180044314  or      ebx, esi
0x180044316  test    ebx, ebx
0x180044318  js      loc_18004442A
0x18004431e  cmp     [rsp+130h+Type], 1
0x180044323  jnz     loc_180044425
0x180044329  mov     ecx, [rsp+130h+var_FC]
0x18004432d  test    ecx, ecx
0x18004432f  jz      loc_180044425
0x180044335  xor     edi, edi
0x180044337  xor     ebx, ebx
0x180044339  cmp     ebx, ecx
0x18004433b  jnb     short loc_180044364
0x18004433d  cmp     [rsp+rbx+130h+var_C8], 2Eh ; '.'
0x180044342  mov     eax, ebx
0x180044344  jz      short loc_18004434A
0x180044346  inc     ebx
0x180044348  jmp     short loc_180044339
0x18004434a  cmp     rax, 0Ah
0x18004434e  jnb     loc_18004441F
0x180044354  mov     [rsp+rbx+130h+var_C8], dil
0x180044359  lea     ecx, [rbx+1]
0x18004435c  lea     rdi, [rsp+130h+var_C8]
0x180044361  add     rdi, rcx
0x180044364  lea     rcx, [rsp+130h+var_C8]; String
0x180044369  call    cs:__imp_atoi
0x180044370  nop     dword ptr [rax+rax+00h]
0x180044375  mov     esi, eax
0x180044377  cmp     ebx, [rsp+130h+var_FC]
0x18004437b  jnz     short loc_180044381
0x18004437d  xor     edi, edi
0x18004437f  jmp     short loc_180044393
0x180044381  mov     rcx, rdi; String
0x180044384  call    cs:__imp_atoi
0x18004438b  nop     dword ptr [rax+rax+00h]
0x180044390  movzx   edi, ax
0x180044393  lea     rax, [rbp+30h+WideCharStr]
0x180044397  mov     dword ptr [rsp+130h+lpcbData], 30h ; '0'; cchWideChar
0x18004439f  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800443a3  mov     [rsp+130h+phkResult], rax; lpWideCharStr
0x1800443a8  lea     r8, [rsp+130h+Data]; lpMultiByteStr
0x1800443ad  xor     edx, edx; dwFlags
0x1800443af  xor     ecx, ecx; CodePage
0x1800443b1  call    cs:__imp_MultiByteToWideChar
0x1800443b8  nop     dword ptr [rax+rax+00h]
0x1800443bd  test    eax, eax
0x1800443bf  jz      short loc_180044425
0x1800443c1  lea     rdx, [rsp+130h+pclsid]; pclsid
0x1800443c6  lea     rcx, [rbp+30h+WideCharStr]; lpsz
0x1800443ca  call    cs:__imp_CLSIDFromString
0x1800443d1  nop     dword ptr [rax+rax+00h]
0x1800443d6  mov     ebx, eax
0x1800443d8  test    eax, eax
0x1800443da  js      short loc_18004442A
0x1800443dc  lea     rax, [rsp+130h+pptlib]
0x1800443e1  movzx   edx, si; wVerMajor
0x1800443e4  mov     r9d, 400h; lcid
0x1800443ea  mov     [rsp+130h+phkResult], rax; pptlib
0x1800443ef  movzx   r8d, di; wVerMinor
0x1800443f3  lea     rcx, [rsp+130h+pclsid]; rguid
0x1800443f8  call    cs:__imp_LoadRegTypeLib
0x1800443ff  nop     dword ptr [rax+rax+00h]
0x180044404  mov     ebx, eax
0x180044406  test    eax, eax
0x180044408  js      short loc_18004442A
0x18004440a  mov     rax, [rsp+130h+pptlib]
0x18004440f  xor     ebx, ebx
0x180044411  mov     [r14], rax
0x180044414  mov     [rsp+130h+pptlib], 0
0x18004441d  jmp     short loc_18004442A
0x18004441f  call    __report_rangecheckfailure
0x180044425  mov     ebx, 80004005h
0x18004442a  mov     rcx, [rsp+130h+hKey]; hKey
0x18004442f  test    rcx, rcx
0x180044432  jz      short loc_180044449
0x180044434  call    cs:__imp_RegCloseKey
0x18004443b  nop     dword ptr [rax+rax+00h]
0x180044440  mov     [rsp+130h+hKey], 0
0x180044449  mov     rcx, [rsp+130h+var_E8]; hKey
0x18004444e  test    rcx, rcx
0x180044451  jz      short loc_180044468
0x180044453  call    cs:__imp_RegCloseKey
0x18004445a  nop     dword ptr [rax+rax+00h]
0x18004445f  mov     [rsp+130h+var_E8], 0
0x180044468  mov     rcx, [rsp+130h+pptlib]
0x18004446d  test    rcx, rcx
0x180044470  jz      short loc_18004447E
0x180044472  mov     rax, [rcx]
0x180044475  mov     rax, [rax+10h]
0x180044479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004447e  mov     eax, ebx
0x180044480  mov     rcx, [rbp+30h+var_20]
0x180044484  xor     rcx, rsp; StackCookie
0x180044487  call    __security_check_cookie
0x18004448c  lea     r11, [rsp+130h+var_10]
0x180044494  mov     rbx, [r11+30h]
0x180044498  mov     rsi, [r11+38h]
0x18004449c  mov     rsp, r11
0x18004449f  pop     r14
0x1800444a1  pop     rdi
0x1800444a2  pop     rbp
0x1800444a3  retn
```
