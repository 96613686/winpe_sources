# GetTypeInfoFromInprocServer

- ea: `0x180043468`
- end: `0x18004369f`
- name: `GetTypeInfoFromInprocServer`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800643ac`

## callees

- `0x180043468`
- `0x180045ca8`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `OLEAUT32!__imp_LoadTypeLibEx` at `0x1800435e7`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x1800435e7`
- `KERNEL32!MultiByteToWideChar` at `0x180043593`
- `KERNEL32!MultiByteToWideChar` at `0x180043593`
- `ADVAPI32!RegOpenKeyExA` at `0x1800434e4`
- `ADVAPI32!RegOpenKeyExA` at `0x1800434e4`
- `ADVAPI32!RegCloseKey` at `0x18004363c`
- `ADVAPI32!RegCloseKey` at `0x18004363c`
- `ADVAPI32!RegQueryValueExA` at `0x180043524`
- `ADVAPI32!RegQueryValueExA` at `0x180043524`

## pseudocode

```c
__int64 __fastcall GetTypeInfoFromInprocServer(HKEY a1, __int64 a2, __int16 a3, _QWORD *a4)
{
  LSTATUS v7; // eax
  int v8; // ebx
  LSTATUS v9; // eax
  __int64 v10; // rax
  DWORD v11; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  ITypeLib *pptlib; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  CHAR Data[272]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+160h] [rbp+60h] BYREF

  *a4 = 0;
  hKey = 0;
  cbData = 260;
  pptlib = 0;
  v17 = 0;
  Type = 0;
  v7 = RegOpenKeyExA(a1, "InprocServer32", 0, 0x20019u, &hKey);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
  {
    v9 = RegQueryValueExA(hKey, 0, 0, &Type, (LPBYTE)Data, &cbData);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v8 >= 0 )
    {
      if ( Type == 1 && cbData && cbData < 0x103 )
      {
        v10 = cbData - 1;
        if ( (unsigned int)v10 >= 0x104 )
          goto LABEL_17;
        Data[v10] = 0;
        v11 = MultiByteToWideChar(0, 0, Data, -1, WideCharStr, 260);
        cbData = v11;
        if ( v11 && v11 < 0x105 )
        {
          WideCharStr[v11 - 1] = 92;
          WideCharStr[v11] = a3 + 48;
          if ( 2 * (unsigned __int64)(v11 + 1) < 0x20C )
          {
            WideCharStr[v11 + 1] = 0;
            v8 = LoadTypeLibEx(WideCharStr, REGKIND_NONE, &pptlib);
            if ( v8 >= 0 )
            {
              v8 = ((__int64 (__fastcall *)(ITypeLib *, __int64, __int64 *))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                     pptlib,
                     a2,
                     &v17);
              if ( v8 >= 0 )
              {
                v8 = 0;
                *a4 = v17;
                v17 = 0;
              }
            }
            goto LABEL_19;
          }
LABEL_17:
          _report_rangecheckfailure();
        }
      }
      v8 = -2147467259;
    }
  }
LABEL_19:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( pptlib )
  {
    ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
    pptlib = 0;
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180043468  push    rbp
0x18004346a  push    rbx
0x18004346b  push    rsi
0x18004346c  push    rdi
0x18004346d  push    r14
0x18004346f  lea     rbp, [rsp-280h]
0x180043477  sub     rsp, 380h
0x18004347e  mov     rax, cs:__security_cookie
0x180043485  xor     rax, rsp
0x180043488  mov     [rbp+2A0h+var_30], rax
0x18004348f  mov     rsi, r9
0x180043492  mov     qword ptr [r9], 0
0x180043499  mov     edi, r8d
0x18004349c  mov     [rsp+3A0h+hKey], 0
0x1800434a5  mov     r14, rdx
0x1800434a8  mov     [rsp+3A0h+cbData], 104h
0x1800434b0  lea     rax, [rsp+3A0h+hKey]
0x1800434b5  mov     [rsp+3A0h+pptlib], 0
0x1800434be  mov     r9d, 20019h; samDesired
0x1800434c4  mov     [rsp+3A0h+phkResult], rax; phkResult
0x1800434c9  xor     r8d, r8d; ulOptions
0x1800434cc  mov     [rsp+3A0h+var_358], 0
0x1800434d5  lea     rdx, aInprocserver32; "InprocServer32"
0x1800434dc  mov     [rsp+3A0h+Type], 0
0x1800434e4  call    cs:__imp_RegOpenKeyExA
0x1800434ea  mov     ebx, eax
0x1800434ec  test    eax, eax
0x1800434ee  jle     short loc_1800434F9
0x1800434f0  movzx   ebx, ax
0x1800434f3  or      ebx, 80070000h
0x1800434f9  test    ebx, ebx
0x1800434fb  js      loc_180043632
0x180043501  mov     rcx, [rsp+3A0h+hKey]; hKey
0x180043506  lea     rax, [rsp+3A0h+cbData]
0x18004350b  mov     [rsp+3A0h+lpcbData], rax; lpcbData
0x180043510  lea     r9, [rsp+3A0h+Type]; lpType
0x180043515  lea     rax, [rsp+3A0h+Data]
0x18004351a  xor     r8d, r8d; lpReserved
0x18004351d  xor     edx, edx; lpValueName
0x18004351f  mov     [rsp+3A0h+phkResult], rax; lpData
0x180043524  call    cs:__imp_RegQueryValueExA
0x18004352a  mov     ebx, eax
0x18004352c  test    eax, eax
0x18004352e  jle     short loc_180043539
0x180043530  movzx   ebx, ax
0x180043533  or      ebx, 80070000h
0x180043539  test    ebx, ebx
0x18004353b  js      loc_180043632
0x180043541  cmp     [rsp+3A0h+Type], 1
0x180043546  jnz     loc_18004362D
0x18004354c  mov     eax, [rsp+3A0h+cbData]
0x180043550  test    eax, eax
0x180043552  jz      loc_18004362D
0x180043558  cmp     eax, 103h
0x18004355d  jnb     loc_18004362D
0x180043563  dec     eax
0x180043565  cmp     eax, 104h
0x18004356a  jnb     loc_180043627
0x180043570  mov     [rsp+rax+3A0h+Data], 0
0x180043575  lea     r8, [rsp+3A0h+Data]; lpMultiByteStr
0x18004357a  lea     rax, [rbp+2A0h+WideCharStr]
0x18004357e  mov     dword ptr [rsp+3A0h+lpcbData], 104h; cchWideChar
0x180043586  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18004358a  mov     [rsp+3A0h+phkResult], rax; lpWideCharStr
0x18004358f  xor     edx, edx; dwFlags
0x180043591  xor     ecx, ecx; CodePage
0x180043593  call    cs:__imp_MultiByteToWideChar
0x180043599  mov     edx, eax
0x18004359b  mov     [rsp+3A0h+cbData], edx
0x18004359f  test    eax, eax
0x1800435a1  jz      loc_18004362D
0x1800435a7  cmp     edx, 105h
0x1800435ad  jnb     short loc_18004362D
0x1800435af  lea     ecx, [rdx-1]
0x1800435b2  add     di, 30h ; '0'
0x1800435b6  mov     eax, 5Ch ; '\'
0x1800435bb  mov     [rbp+rcx*2+2A0h+WideCharStr], ax
0x1800435c0  lea     ecx, [rdx+1]
0x1800435c3  add     rcx, rcx
0x1800435c6  mov     [rbp+rdx*2+2A0h+WideCharStr], di
0x1800435cb  cmp     rcx, 20Ch
0x1800435d2  jnb     short loc_180043627
0x1800435d4  xor     eax, eax
0x1800435d6  lea     r8, [rsp+3A0h+pptlib]; pptlib
0x1800435db  mov     [rbp+rcx+2A0h+WideCharStr], ax
0x1800435e0  lea     rcx, [rbp+2A0h+WideCharStr]; szFile
0x1800435e4  lea     edx, [rax+2]; regkind
0x1800435e7  call    cs:__imp_LoadTypeLibEx
0x1800435ed  mov     ebx, eax
0x1800435ef  test    eax, eax
0x1800435f1  js      short loc_180043632
0x1800435f3  mov     rcx, [rsp+3A0h+pptlib]
0x1800435f8  lea     r8, [rsp+3A0h+var_358]
0x1800435fd  mov     rdx, r14
0x180043600  mov     rax, [rcx]
0x180043603  mov     rax, [rax+30h]
0x180043607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004360c  mov     ebx, eax
0x18004360e  test    eax, eax
0x180043610  js      short loc_180043632
0x180043612  mov     rax, [rsp+3A0h+var_358]
0x180043617  xor     ebx, ebx
0x180043619  mov     [rsi], rax
0x18004361c  mov     [rsp+3A0h+var_358], 0
0x180043625  jmp     short loc_180043632
0x180043627  call    __report_rangecheckfailure
0x18004362d  mov     ebx, 80004005h
0x180043632  mov     rcx, [rsp+3A0h+hKey]; hKey
0x180043637  test    rcx, rcx
0x18004363a  jz      short loc_18004364B
0x18004363c  call    cs:__imp_RegCloseKey
0x180043642  mov     [rsp+3A0h+hKey], 0
0x18004364b  mov     rcx, [rsp+3A0h+pptlib]
0x180043650  test    rcx, rcx
0x180043653  jz      short loc_18004366A
0x180043655  mov     rax, [rcx]
0x180043658  mov     rax, [rax+10h]
0x18004365c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043661  mov     [rsp+3A0h+pptlib], 0
0x18004366a  mov     rcx, [rsp+3A0h+var_358]
0x18004366f  test    rcx, rcx
0x180043672  jz      short loc_180043680
0x180043674  mov     rax, [rcx]
0x180043677  mov     rax, [rax+10h]
0x18004367b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043680  mov     eax, ebx
0x180043682  mov     rcx, [rbp+2A0h+var_30]
0x180043689  xor     rcx, rsp; StackCookie
0x18004368c  call    __security_check_cookie
0x180043691  add     rsp, 380h
0x180043698  pop     r14
0x18004369a  pop     rdi
0x18004369b  pop     rsi
0x18004369c  pop     rbx
0x18004369d  pop     rbp
0x18004369e  retn
```
