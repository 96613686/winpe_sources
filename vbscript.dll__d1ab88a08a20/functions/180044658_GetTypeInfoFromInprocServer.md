# GetTypeInfoFromInprocServer

- ea: `0x180044658`
- end: `0x1800448b2`
- name: `GetTypeInfoFromInprocServer`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006617c`

## callees

- `0x180044658`
- `0x180047098`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `OLEAUT32!__imp_LoadTypeLibEx` at `0x1800447ed`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x1800447ed`
- `KERNEL32!MultiByteToWideChar` at `0x18004478f`
- `KERNEL32!MultiByteToWideChar` at `0x18004478f`
- `ADVAPI32!RegOpenKeyExA` at `0x1800446d4`
- `ADVAPI32!RegOpenKeyExA` at `0x1800446d4`
- `ADVAPI32!RegCloseKey` at `0x180044848`
- `ADVAPI32!RegCloseKey` at `0x180044848`
- `ADVAPI32!RegQueryValueExA` at `0x18004471a`
- `ADVAPI32!RegQueryValueExA` at `0x18004471a`

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
0x180044658  push    rbp
0x18004465a  push    rbx
0x18004465b  push    rsi
0x18004465c  push    rdi
0x18004465d  push    r14
0x18004465f  lea     rbp, [rsp-280h]
0x180044667  sub     rsp, 380h
0x18004466e  mov     rax, cs:__security_cookie
0x180044675  xor     rax, rsp
0x180044678  mov     [rbp+2A0h+var_30], rax
0x18004467f  mov     rsi, r9
0x180044682  mov     qword ptr [r9], 0
0x180044689  mov     edi, r8d
0x18004468c  mov     [rsp+3A0h+hKey], 0
0x180044695  mov     r14, rdx
0x180044698  mov     [rsp+3A0h+cbData], 104h
0x1800446a0  lea     rax, [rsp+3A0h+hKey]
0x1800446a5  mov     [rsp+3A0h+pptlib], 0
0x1800446ae  mov     r9d, 20019h; samDesired
0x1800446b4  mov     [rsp+3A0h+phkResult], rax; phkResult
0x1800446b9  xor     r8d, r8d; ulOptions
0x1800446bc  mov     [rsp+3A0h+var_358], 0
0x1800446c5  lea     rdx, aInprocserver32; "InprocServer32"
0x1800446cc  mov     [rsp+3A0h+Type], 0
0x1800446d4  call    cs:__imp_RegOpenKeyExA
0x1800446db  nop     dword ptr [rax+rax+00h]
0x1800446e0  mov     ebx, eax
0x1800446e2  test    eax, eax
0x1800446e4  jle     short loc_1800446EF
0x1800446e6  movzx   ebx, ax
0x1800446e9  or      ebx, 80070000h
0x1800446ef  test    ebx, ebx
0x1800446f1  js      loc_18004483E
0x1800446f7  mov     rcx, [rsp+3A0h+hKey]; hKey
0x1800446fc  lea     rax, [rsp+3A0h+cbData]
0x180044701  mov     [rsp+3A0h+lpcbData], rax; lpcbData
0x180044706  lea     r9, [rsp+3A0h+Type]; lpType
0x18004470b  lea     rax, [rsp+3A0h+Data]
0x180044710  xor     r8d, r8d; lpReserved
0x180044713  xor     edx, edx; lpValueName
0x180044715  mov     [rsp+3A0h+phkResult], rax; lpData
0x18004471a  call    cs:__imp_RegQueryValueExA
0x180044721  nop     dword ptr [rax+rax+00h]
0x180044726  mov     ebx, eax
0x180044728  test    eax, eax
0x18004472a  jle     short loc_180044735
0x18004472c  movzx   ebx, ax
0x18004472f  or      ebx, 80070000h
0x180044735  test    ebx, ebx
0x180044737  js      loc_18004483E
0x18004473d  cmp     [rsp+3A0h+Type], 1
0x180044742  jnz     loc_180044839
0x180044748  mov     eax, [rsp+3A0h+cbData]
0x18004474c  test    eax, eax
0x18004474e  jz      loc_180044839
0x180044754  cmp     eax, 103h
0x180044759  jnb     loc_180044839
0x18004475f  dec     eax
0x180044761  cmp     eax, 104h
0x180044766  jnb     loc_180044833
0x18004476c  mov     [rsp+rax+3A0h+Data], 0
0x180044771  lea     r8, [rsp+3A0h+Data]; lpMultiByteStr
0x180044776  lea     rax, [rbp+2A0h+WideCharStr]
0x18004477a  mov     dword ptr [rsp+3A0h+lpcbData], 104h; cchWideChar
0x180044782  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180044786  mov     [rsp+3A0h+phkResult], rax; lpWideCharStr
0x18004478b  xor     edx, edx; dwFlags
0x18004478d  xor     ecx, ecx; CodePage
0x18004478f  call    cs:__imp_MultiByteToWideChar
0x180044796  nop     dword ptr [rax+rax+00h]
0x18004479b  mov     edx, eax
0x18004479d  mov     [rsp+3A0h+cbData], edx
0x1800447a1  test    eax, eax
0x1800447a3  jz      loc_180044839
0x1800447a9  cmp     edx, 105h
0x1800447af  jnb     loc_180044839
0x1800447b5  lea     ecx, [rdx-1]
0x1800447b8  add     di, 30h ; '0'
0x1800447bc  mov     eax, 5Ch ; '\'
0x1800447c1  mov     [rbp+rcx*2+2A0h+WideCharStr], ax
0x1800447c6  lea     ecx, [rdx+1]
0x1800447c9  add     rcx, rcx
0x1800447cc  mov     [rbp+rdx*2+2A0h+WideCharStr], di
0x1800447d1  cmp     rcx, 20Ch
0x1800447d8  jnb     short loc_180044833
0x1800447da  xor     eax, eax
0x1800447dc  lea     r8, [rsp+3A0h+pptlib]; pptlib
0x1800447e1  mov     [rbp+rcx+2A0h+WideCharStr], ax
0x1800447e6  lea     rcx, [rbp+2A0h+WideCharStr]; szFile
0x1800447ea  lea     edx, [rax+2]; regkind
0x1800447ed  call    cs:__imp_LoadTypeLibEx
0x1800447f4  nop     dword ptr [rax+rax+00h]
0x1800447f9  mov     ebx, eax
0x1800447fb  test    eax, eax
0x1800447fd  js      short loc_18004483E
0x1800447ff  mov     rcx, [rsp+3A0h+pptlib]
0x180044804  lea     r8, [rsp+3A0h+var_358]
0x180044809  mov     rdx, r14
0x18004480c  mov     rax, [rcx]
0x18004480f  mov     rax, [rax+30h]
0x180044813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044818  mov     ebx, eax
0x18004481a  test    eax, eax
0x18004481c  js      short loc_18004483E
0x18004481e  mov     rax, [rsp+3A0h+var_358]
0x180044823  xor     ebx, ebx
0x180044825  mov     [rsi], rax
0x180044828  mov     [rsp+3A0h+var_358], 0
0x180044831  jmp     short loc_18004483E
0x180044833  call    __report_rangecheckfailure
0x180044839  mov     ebx, 80004005h
0x18004483e  mov     rcx, [rsp+3A0h+hKey]; hKey
0x180044843  test    rcx, rcx
0x180044846  jz      short loc_18004485D
0x180044848  call    cs:__imp_RegCloseKey
0x18004484f  nop     dword ptr [rax+rax+00h]
0x180044854  mov     [rsp+3A0h+hKey], 0
0x18004485d  mov     rcx, [rsp+3A0h+pptlib]
0x180044862  test    rcx, rcx
0x180044865  jz      short loc_18004487C
0x180044867  mov     rax, [rcx]
0x18004486a  mov     rax, [rax+10h]
0x18004486e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044873  mov     [rsp+3A0h+pptlib], 0
0x18004487c  mov     rcx, [rsp+3A0h+var_358]
0x180044881  test    rcx, rcx
0x180044884  jz      short loc_180044892
0x180044886  mov     rax, [rcx]
0x180044889  mov     rax, [rax+10h]
0x18004488d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044892  mov     eax, ebx
0x180044894  mov     rcx, [rbp+2A0h+var_30]
0x18004489b  xor     rcx, rsp; StackCookie
0x18004489e  call    __security_check_cookie
0x1800448a3  add     rsp, 380h
0x1800448aa  pop     r14
0x1800448ac  pop     rdi
0x1800448ad  pop     rsi
0x1800448ae  pop     rbx
0x1800448af  pop     rbp
0x1800448b0  retn
```
