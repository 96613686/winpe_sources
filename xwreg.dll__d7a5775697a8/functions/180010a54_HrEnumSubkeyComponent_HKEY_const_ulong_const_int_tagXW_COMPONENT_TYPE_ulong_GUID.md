# HrEnumSubkeyComponent(HKEY__ * const,ulong * const,int,tagXW_COMPONENT_TYPE,ulong,_GUID *)

- ea: `0x180010a54`
- end: `0x180010dc3`
- name: `?HrEnumSubkeyComponent@@YAJQEAUHKEY__@@QEAKHW4tagXW_COMPONENT_TYPE@@KPEAU_GUID@@@Z`
- size: `879`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010dcc`

## callees

- `0x180007820`
- `0x18000abbc`
- `0x180010a54`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180010d1d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180010d1d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010b53`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010b53`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180010b21`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180010b21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010b99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010b99`

## pseudocode

```c
__int64 __fastcall HrEnumSubkeyComponent(HKEY a1, _DWORD *a2, int a3, __int64 a4, __int64 a5, CLSID *pclsid)
{
  unsigned int v9; // ebx
  int v10; // r15d
  DWORD v11; // edx
  int v12; // r14d
  DWORD v13; // edi
  int v14; // esi
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  DWORD v18; // eax
  PVOID *v19; // rcx
  int v20; // edx
  HRESULT v21; // eax
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  int v25; // [rsp+48h] [rbp-B8h]
  DWORD cbData; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD v27; // [rsp+50h] [rbp-B0h]
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v30; // [rsp+68h] [rbp-98h]
  WCHAR Name[40]; // [rsp+70h] [rbp-90h] BYREF
  char v32[80]; // [rsp+C0h] [rbp-40h] BYREF

  v25 = a3;
  v30 = a2;
  memset_0(Name, 0, sizeof(Name));
  memset_0(v32, 0, sizeof(v32));
  v9 = 0;
  ftLastWriteTime = 0;
  v10 = 1;
  if ( *a2 )
    v10 = *a2;
  v11 = 0;
  if ( !a3 )
    v11 = v10 - 1;
  v27 = v11;
LABEL_6:
  v12 = 0;
  v13 = v11;
  v14 = 0;
  while ( 1 )
  {
    cchName = 40;
    v15 = RegEnumKeyExW(a1, v13, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
    if ( v15 )
    {
      if ( v15 == 259 )
      {
        v9 = 1;
        v19 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            (unsigned int)WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids,
            (unsigned int)Name,
            1);
          v19 = (PVOID *)WPP_GLOBAL_Control;
        }
LABEL_44:
        v11 = v27;
        if ( v12 )
          goto LABEL_6;
        goto LABEL_52;
      }
      if ( v15 > 0 )
        v9 = (unsigned __int16)v15 | 0x80070000;
      else
        v9 = v15;
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v20 = 14;
LABEL_34:
        WPP_SF_SD(
          (unsigned int)v19[2],
          v20,
          (unsigned int)WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids,
          (unsigned int)Name,
          v9);
LABEL_35:
        v19 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    else
    {
      phkResult = 0;
      v16 = RegOpenKeyExW(a1, Name, 0, 0x20019u, &phkResult);
      if ( !v16 )
      {
        *(_DWORD *)Data = 0;
        cbData = 4;
        if ( v25 )
        {
          v17 = RegQueryValueExW(phkResult, L"Ordinal", 0, 0, Data, &cbData);
          v9 = v17;
          if ( v17 > 0 )
            v9 = (unsigned __int16)v17 | 0x80070000;
          v18 = *(_DWORD *)Data;
        }
        else
        {
          v18 = v13 + 1;
          *(_DWORD *)Data = v13 + 1;
        }
        if ( (v9 & 0x80000000) != 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              (unsigned int)WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids,
              (unsigned int)Name,
              v9);
        }
        else if ( v18 == v10 )
        {
          v12 = 1;
          v14 = 1;
        }
        RegCloseKey(phkResult);
        goto LABEL_35;
      }
      if ( v16 > 0 )
        v9 = (unsigned __int16)v16 | 0x80070000;
      else
        v9 = v16;
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v20 = 12;
        goto LABEL_34;
      }
    }
    if ( v9 )
    {
      if ( v9 != 1 )
        goto LABEL_52;
      goto LABEL_44;
    }
    if ( v14 )
      break;
    ++v13;
  }
  *v30 = v10 + 1;
  if ( pclsid && (v21 = CLSIDFromString(Name, pclsid), v9 = v21, v21 < 0) )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids,
        (unsigned int)Name,
        v21);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_52:
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 0x10) != 0 )
    WPP_SF_D(v19[2], 16, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180010a54  mov     [rsp-8+arg_10], rbx
0x180010a59  push    rbp
0x180010a5a  push    rsi
0x180010a5b  push    rdi
0x180010a5c  push    r12
0x180010a5e  push    r13
0x180010a60  push    r14
0x180010a62  push    r15
0x180010a64  lea     rbp, [rsp-20h]
0x180010a69  sub     rsp, 120h
0x180010a70  mov     rax, cs:__security_cookie
0x180010a77  xor     rax, rsp
0x180010a7a  mov     [rbp+50h+var_40], rax
0x180010a7e  mov     r12, [rbp+50h+pclsid]
0x180010a85  mov     esi, r8d
0x180010a88  mov     [rsp+150h+var_108], r8d
0x180010a8d  mov     rdi, rdx
0x180010a90  mov     [rsp+150h+var_E8], rdx
0x180010a95  mov     r13, rcx
0x180010a98  mov     ebx, 50h ; 'P'
0x180010a9d  lea     rcx, [rsp+150h+Name]; void *
0x180010aa2  mov     r8d, ebx; Size
0x180010aa5  xor     edx, edx; Val
0x180010aa7  call    memset_0
0x180010aac  mov     r8d, ebx; Size
0x180010aaf  lea     rcx, [rbp+50h+var_90]; void *
0x180010ab3  xor     edx, edx; Val
0x180010ab5  call    memset_0
0x180010aba  xor     ebx, ebx
0x180010abc  mov     qword ptr [rsp+150h+ftLastWriteTime.dwLowDateTime], 0
0x180010ac5  cmp     [rdi], ebx
0x180010ac7  lea     r15d, [rbx+1]
0x180010acb  cmovnz  r15d, [rdi]
0x180010acf  xor     edx, edx
0x180010ad1  test    esi, esi
0x180010ad3  lea     eax, [r15-1]
0x180010ad7  cmovz   edx, eax
0x180010ada  mov     [rsp+150h+var_100], edx
0x180010ade  xor     r14d, r14d
0x180010ae1  mov     edi, edx
0x180010ae3  xor     esi, esi
0x180010ae5  lea     rax, [rsp+150h+ftLastWriteTime]
0x180010aea  mov     [rsp+150h+cchName], 28h ; '('
0x180010af2  mov     [rsp+150h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180010af7  lea     r9, [rsp+150h+cchName]; lpcchName
0x180010afc  mov     [rsp+150h+lpcchClass], 0; lpcchClass
0x180010b05  lea     r8, [rsp+150h+Name]; lpName
0x180010b0a  mov     [rsp+150h+lpClass], 0; lpClass
0x180010b13  mov     edx, edi; dwIndex
0x180010b15  mov     rcx, r13; hKey
0x180010b18  mov     [rsp+150h+lpReserved], 0; lpReserved
0x180010b21  call    cs:__imp_RegEnumKeyExW
0x180010b27  test    eax, eax
0x180010b29  jnz     loc_180010C43
0x180010b2f  lea     rax, [rsp+150h+phkResult]
0x180010b34  mov     [rsp+150h+phkResult], 0
0x180010b3d  mov     r9d, 20019h; samDesired
0x180010b43  mov     [rsp+150h+lpReserved], rax; phkResult
0x180010b48  xor     r8d, r8d; ulOptions
0x180010b4b  lea     rdx, [rsp+150h+Name]; lpSubKey
0x180010b50  mov     rcx, r13; hKey
0x180010b53  call    cs:__imp_RegOpenKeyExW
0x180010b59  test    eax, eax
0x180010b5b  jnz     loc_180010C14
0x180010b61  mov     dword ptr [rsp+150h+Data], eax
0x180010b65  mov     [rsp+150h+cbData], 4
0x180010b6d  cmp     [rsp+150h+var_108], eax
0x180010b71  jz      short loc_180010BB4
0x180010b73  mov     rcx, [rsp+150h+phkResult]; hKey
0x180010b78  lea     rax, [rsp+150h+cbData]
0x180010b7d  mov     [rsp+150h+lpClass], rax; lpcbData
0x180010b82  lea     rdx, aOrdinal_0; "Ordinal"
0x180010b89  lea     rax, [rsp+150h+Data]
0x180010b8e  xor     r9d, r9d; lpType
0x180010b91  xor     r8d, r8d; lpReserved
0x180010b94  mov     [rsp+150h+lpReserved], rax; lpData
0x180010b99  call    cs:__imp_RegQueryValueExW
0x180010b9f  mov     ebx, eax
0x180010ba1  test    eax, eax
0x180010ba3  jle     short loc_180010BAE
0x180010ba5  movzx   ebx, ax
0x180010ba8  or      ebx, 80070000h
0x180010bae  mov     eax, dword ptr [rsp+150h+Data]
0x180010bb2  jmp     short loc_180010BBB
0x180010bb4  lea     eax, [rdi+1]
0x180010bb7  mov     dword ptr [rsp+150h+Data], eax
0x180010bbb  test    ebx, ebx
0x180010bbd  js      short loc_180010BD0
0x180010bbf  cmp     eax, r15d
0x180010bc2  jnz     short loc_180010C07
0x180010bc4  mov     eax, 1
0x180010bc9  mov     r14d, eax
0x180010bcc  mov     esi, eax
0x180010bce  jmp     short loc_180010C07
0x180010bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180010bd7  lea     rax, WPP_GLOBAL_Control
0x180010bde  cmp     rcx, rax
0x180010be1  jz      short loc_180010C07
0x180010be3  test    byte ptr [rcx+1Ch], 4
0x180010be7  jz      short loc_180010C07
0x180010be9  mov     rcx, [rcx+10h]
0x180010bed  lea     r9, [rsp+150h+Name]
0x180010bf2  mov     edx, 0Bh
0x180010bf7  mov     dword ptr [rsp+150h+lpReserved], ebx
0x180010bfb  lea     r8, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids
0x180010c02  call    WPP_SF_SD
0x180010c07  mov     rcx, [rsp+150h+phkResult]; hKey
0x180010c0c  call    cs:__imp_RegCloseKey
0x180010c12  jmp     short loc_180010C92
0x180010c14  jg      short loc_180010C1A
0x180010c16  mov     ebx, eax
0x180010c18  jmp     short loc_180010C23
0x180010c1a  movzx   ebx, ax
0x180010c1d  or      ebx, 80070000h
0x180010c23  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c2a  lea     rax, WPP_GLOBAL_Control
0x180010c31  cmp     rcx, rax
0x180010c34  jz      short loc_180010C99
0x180010c36  test    byte ptr [rcx+1Ch], 4
0x180010c3a  jz      short loc_180010C99
0x180010c3c  mov     edx, 0Ch
0x180010c41  jmp     short loc_180010C79
0x180010c43  cmp     eax, 103h
0x180010c48  jz      short loc_180010CB3
0x180010c4a  test    eax, eax
0x180010c4c  jg      short loc_180010C52
0x180010c4e  mov     ebx, eax
0x180010c50  jmp     short loc_180010C5B
0x180010c52  movzx   ebx, ax
0x180010c55  or      ebx, 80070000h
0x180010c5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c62  lea     rax, WPP_GLOBAL_Control
0x180010c69  cmp     rcx, rax
0x180010c6c  jz      short loc_180010C99
0x180010c6e  test    byte ptr [rcx+1Ch], 4
0x180010c72  jz      short loc_180010C99
0x180010c74  mov     edx, 0Eh
0x180010c79  mov     rcx, [rcx+10h]
0x180010c7d  lea     r9, [rsp+150h+Name]
0x180010c82  lea     r8, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids
0x180010c89  mov     dword ptr [rsp+150h+lpReserved], ebx
0x180010c8d  call    WPP_SF_SD
0x180010c92  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c99  test    ebx, ebx
0x180010c9b  jnz     short loc_180010CA8
0x180010c9d  test    esi, esi
0x180010c9f  jnz     short loc_180010D05
0x180010ca1  inc     edi
0x180010ca3  jmp     loc_180010AE5
0x180010ca8  cmp     ebx, 1
0x180010cab  jnz     loc_180010D70
0x180010cb1  jmp     short loc_180010CF4
0x180010cb3  mov     ebx, 1
0x180010cb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cbf  lea     rax, WPP_GLOBAL_Control
0x180010cc6  cmp     rcx, rax
0x180010cc9  jz      short loc_180010CF4
0x180010ccb  test    byte ptr [rcx+1Ch], 10h
0x180010ccf  jz      short loc_180010CF4
0x180010cd1  mov     rcx, [rcx+10h]
0x180010cd5  lea     edx, [rbx+0Ch]
0x180010cd8  lea     r9, [rsp+150h+Name]
0x180010cdd  mov     dword ptr [rsp+150h+lpReserved], ebx
0x180010ce1  lea     r8, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids
0x180010ce8  call    WPP_SF_SD
0x180010ced  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cf4  mov     edx, [rsp+150h+var_100]
0x180010cf8  test    r14d, r14d
0x180010cfb  jnz     loc_180010ADE
0x180010d01  test    ebx, ebx
0x180010d03  jnz     short loc_180010D70
0x180010d05  mov     rcx, [rsp+150h+var_E8]
0x180010d0a  lea     eax, [r15+1]
0x180010d0e  mov     [rcx], eax
0x180010d10  test    r12, r12
0x180010d13  jz      short loc_180010D69
0x180010d15  mov     rdx, r12; pclsid
0x180010d18  lea     rcx, [rsp+150h+Name]; lpsz
0x180010d1d  call    cs:__imp_CLSIDFromString
0x180010d23  mov     ebx, eax
0x180010d25  test    eax, eax
0x180010d27  jns     short loc_180010D69
0x180010d29  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d30  lea     rdi, WPP_GLOBAL_Control
0x180010d37  cmp     rcx, rdi
0x180010d3a  jz      short loc_180010D9A
0x180010d3c  test    byte ptr [rcx+1Ch], 4
0x180010d40  jz      short loc_180010D77
0x180010d42  mov     rcx, [rcx+10h]
0x180010d46  lea     r9, [rsp+150h+Name]
0x180010d4b  mov     edx, 0Fh
0x180010d50  mov     dword ptr [rsp+150h+lpReserved], eax
0x180010d54  lea     r8, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids
0x180010d5b  call    WPP_SF_SD
0x180010d60  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d67  jmp     short loc_180010D77
0x180010d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d70  lea     rdi, WPP_GLOBAL_Control
0x180010d77  cmp     rcx, rdi
0x180010d7a  jz      short loc_180010D9A
0x180010d7c  test    byte ptr [rcx+1Ch], 10h
0x180010d80  jz      short loc_180010D9A
0x180010d82  mov     rcx, [rcx+10h]
0x180010d86  lea     r8, WPP_1683c08f278a3fd7da6c53cfa055de44_Traceguids
0x180010d8d  mov     edx, 10h
0x180010d92  mov     r9d, ebx
0x180010d95  call    WPP_SF_D
0x180010d9a  mov     eax, ebx
0x180010d9c  mov     rcx, [rbp+50h+var_40]
0x180010da0  xor     rcx, rsp; StackCookie
0x180010da3  call    __security_check_cookie
0x180010da8  mov     rbx, [rsp+150h+arg_10]
0x180010db0  add     rsp, 120h
0x180010db7  pop     r15
0x180010db9  pop     r14
0x180010dbb  pop     r13
0x180010dbd  pop     r12
0x180010dbf  pop     rdi
0x180010dc0  pop     rsi
0x180010dc1  pop     rbp
0x180010dc2  retn
```
