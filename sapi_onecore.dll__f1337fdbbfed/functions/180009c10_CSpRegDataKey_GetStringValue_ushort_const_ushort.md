# CSpRegDataKey::GetStringValue(ushort const *,ushort * *)

- ea: `0x180009c10`
- end: `0x18000a1e7`
- name: `?GetStringValue@CSpRegDataKey@@UEAAJPEBGPEAPEAG@Z`
- size: `1495`
- prototype: `int(CSpRegDataKey *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009c10`
- `0x18000a1f0`
- `0x18000a420`
- `0x180026508`
- `0x180079e30`
- `0x18007aae4`
- `0x18007d7b1`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180009e82`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180009fd5`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180009e82`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180009fd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009fc7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009fc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a01f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a040`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a050`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a0a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a01f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a040`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a050`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a0a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a1cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a060`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009eb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a00f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009eb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a00f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009e08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009efc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009f52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009e08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009efc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009f52`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009d4b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009d4b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009d90`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009d90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a1a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a1a0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009f8b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009f8b`

## string_xrefs

- `0x18000a0f7`: `onecoreuap\enduser\NUI\OneCore\sapi\sapi\SharedLib\RegistryIsolator.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSpRegDataKey::GetStringValue(
        CSpRegDataKey *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 v5; // rbx
  __int64 v6; // rax
  HKEY v8; // r15
  _WORD *v9; // rsi
  HKEY v10; // r14
  unsigned __int64 i; // rdx
  __int64 v12; // r10
  int v13; // eax
  bool v14; // sf
  int v15; // r14d
  DWORD v16; // eax
  __int64 v17; // r12
  SIZE_T v18; // rcx
  __int64 v19; // rbx
  bool v20; // zf
  HANDLE v21; // rax
  SIZE_T v22; // rax
  unsigned __int64 v23; // rax
  _WORD *v24; // rdi
  __int64 j; // rcx
  SIZE_T v26; // rcx
  DWORD v27; // edx
  SIZE_T v28; // rcx
  __int64 v29; // rdi
  _WORD *v30; // rbx
  DWORD v31; // ecx
  unsigned __int16 *v32; // rax
  HANDLE ProcessHeap; // rax
  SIZE_T v34; // rax
  SIZE_T v35; // rax
  __int64 v36; // rcx
  _WORD *v37; // rdi
  signed int LastError; // eax
  _WORD *v39; // rcx
  __int16 *v40; // rdx
  unsigned int v41; // r8d
  __int16 v42; // ax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  _WORD *v47; // [rsp+60h] [rbp-A0h]
  struct CSpRegistryIsolator *v48; // [rsp+68h] [rbp-98h] BYREF
  _WORD Data[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v5 = -1;
  if ( a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    if ( (unsigned __int64)(v6 + 1) > 0xFFFFF )
      return 2147942487LL;
  }
  if ( !a3 )
    return 2147500035LL;
  v8 = (HKEY)*((_QWORD *)this + 8);
  v9 = 0;
  v47 = 0;
  cbData = 260;
  Type = 0;
  hKey = v8;
  v48 = 0;
  if ( (int)CSpRegistryIsolator::GetInitializedSingleton(&v48, 0) < 0 )
  {
LABEL_79:
    v15 = 12;
    cbData = (2 * cbData) >> 1;
  }
  else if ( v48 )
  {
    v10 = v8;
    hKey = v8;
    for ( i = 0; i < *((_QWORD *)v48 + 1); ++i )
    {
      v12 = *(_QWORD *)v48 + 16 * i;
      if ( v8 == *(HKEY *)(v12 + 8) )
      {
        v13 = RegCreateKeyExW(*((HKEY *)v48 + 3), *(LPCWSTR *)v12, 0, 0, 1u, 0xF003Fu, 0, &hKey, 0);
        v14 = v13 < 0;
        if ( v13 > 0 )
        {
          v13 = (unsigned __int16)v13 | 0x80070000;
          v14 = v13 < 0;
        }
        if ( v14 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5F,
            (unsigned int)"onecoreuap\\enduser\\NUI\\OneCore\\sapi\\sapi\\SharedLib\\RegistryIsolator.h",
            (const char *)(unsigned int)v13,
            dwOptions);
          goto LABEL_79;
        }
        v10 = hKey;
        break;
      }
    }
    cbData *= 2;
    v15 = RegQueryValueExW(v10, a2, 0, &Type, (LPBYTE)Data, &cbData);
    v16 = cbData >> 1;
    cbData >>= 1;
    if ( !v15 && Type == 7 && v16 )
    {
      v39 = Data;
      v40 = Data;
      v41 = v16 - 1;
      if ( v16 != 1 )
      {
        do
        {
          v42 = *v40;
          if ( !*v40 )
            v42 = *++v40;
          *v39++ = v42;
          ++v40;
        }
        while ( (unsigned int)(v40 - Data) < v41 );
      }
      if ( (unsigned int)(v40 - Data) < cbData )
        *v39 = *v40;
      cbData = v39 - Data + 1;
    }
  }
  else
  {
    v15 = 14;
    cbData = (2 * cbData) >> 1;
  }
  if ( hKey != v8 && hKey )
    RegCloseKey(hKey);
  *a3 = 0;
  v17 = 8;
  if ( !v15 )
  {
    v15 = 0;
    do
      ++v5;
    while ( Data[v5] );
    if ( (unsigned int)v5 >= 0x4FFFFFFF || (v26 = 2LL * (unsigned int)(v5 + 1), v26 <= (unsigned int)v5) )
    {
      SetLastError(0x216u);
    }
    else
    {
      v9 = CoTaskMemAlloc(v26);
      if ( v9 )
      {
        v9[(unsigned int)v5] = 0;
        memcpy_0(v9, Data, 2 * v5);
      }
      else
      {
        SetLastError(0xEu);
      }
    }
    goto LABEL_45;
  }
  if ( v15 != 2 )
  {
    if ( v15 != 234 )
      goto LABEL_27;
    if ( cbData >= 0x4FFFFFFF || (v18 = 2LL * (cbData + 1), v19 = cbData, v18 <= cbData) )
    {
      SetLastError(0x216u);
    }
    else
    {
      v9 = CoTaskMemAlloc(v18);
      v47 = v9;
      if ( v9 )
      {
        v9[v19] = 0;
        memset_0(v9, 0, 2 * v19);
        v15 = SpRegQueryStringValueW(v8, a2, (LPBYTE)v9, &cbData);
LABEL_27:
        v20 = v15 == 0;
        if ( v15 <= 0 )
          goto LABEL_28;
        goto LABEL_76;
      }
      SetLastError(0xEu);
    }
LABEL_76:
    v15 = (unsigned __int16)v15 | 0x80070000;
    v20 = v15 == 0;
LABEL_28:
    if ( !v20 )
      goto LABEL_29;
LABEL_45:
    v27 = cbData + 260;
    if ( cbData + 260 >= 0x4FFFFFFF || (v28 = 2LL * (cbData + 261), v29 = v27, v28 <= v27) )
    {
      SetLastError(0x216u);
      v30 = 0;
    }
    else
    {
      v30 = CoTaskMemAlloc(v28);
      if ( v30 )
      {
        v30[v29] = 0;
        memset_0(v30, 0, 2 * v29);
        v31 = ExpandEnvironmentStringsW(v9, v30, cbData + 260);
        if ( v31 )
        {
          if ( v31 > cbData + 260 )
          {
            v15 = -2147467259;
          }
          else
          {
            v32 = v30;
            v30 = 0;
            *a3 = v32;
          }
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v15 = -2147467259;
          if ( LastError < 0 )
            v15 = LastError;
        }
LABEL_51:
        if ( !*a3 )
          v15 = -2147024882;
        if ( !v30 )
          goto LABEL_29;
        ProcessHeap = GetProcessHeap();
        v34 = HeapSize(ProcessHeap, 0, v30);
        if ( v34 - 3 > 0xFFFFFFFFFFFFFFFBuLL )
          goto LABEL_60;
        v35 = v34 >> 1;
        v36 = v35 - 1;
        if ( v35 - 1 < 8 )
        {
          if ( v35 == 1 )
          {
LABEL_60:
            CoTaskMemFree(v30);
LABEL_29:
            if ( v15 == -2147024894 )
              v15 = -2147200966;
            goto LABEL_31;
          }
        }
        else
        {
          v36 = 8;
        }
        v37 = v30;
        while ( v36 )
        {
          *v37++ = -8531;
          --v36;
        }
        goto LABEL_60;
      }
      SetLastError(0xEu);
    }
    v15 = -2147024882;
    goto LABEL_51;
  }
  v15 = -2147200966;
LABEL_31:
  if ( v9 )
  {
    v21 = GetProcessHeap();
    v22 = HeapSize(v21, 0, v9);
    if ( v22 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v23 = (v22 >> 1) - 1;
      if ( v23 >= 8 || (v17 = v23) != 0 )
      {
        v24 = v9;
        for ( j = v17; j; --j )
          *v24++ = -8531;
      }
    }
    CoTaskMemFree(v9);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180009c10  mov     [rsp-8+arg_18], rbx
0x180009c15  push    rbp
0x180009c16  push    rsi
0x180009c17  push    rdi
0x180009c18  push    r12
0x180009c1a  push    r13
0x180009c1c  push    r14
0x180009c1e  push    r15
0x180009c20  lea     rbp, [rsp-190h]
0x180009c28  sub     rsp, 290h
0x180009c2f  mov     rax, cs:__security_cookie
0x180009c36  xor     rax, rsp
0x180009c39  mov     [rbp+1C0h+var_40], rax
0x180009c40  mov     r13, r8
0x180009c43  mov     rdi, rdx
0x180009c46  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180009c4d  test    rdx, rdx
0x180009c50  jz      short loc_180009C99
0x180009c52  mov     rax, rbx
0x180009c55  inc     rax
0x180009c58  cmp     word ptr [rdx+rax*2], 0
0x180009c5d  jnz     short loc_180009C55
0x180009c5f  inc     rax
0x180009c62  cmp     rax, 0FFFFFh
0x180009c68  jbe     short loc_180009C99
0x180009c6a  mov     eax, 80070057h
0x180009c6f  mov     rcx, [rbp+1C0h+var_40]
0x180009c76  xor     rcx, rsp; StackCookie
0x180009c79  call    __security_check_cookie
0x180009c7e  mov     rbx, [rsp+2C0h+arg_18]
0x180009c86  add     rsp, 290h
0x180009c8d  pop     r15
0x180009c8f  pop     r14
0x180009c91  pop     r13
0x180009c93  pop     r12
0x180009c95  pop     rdi
0x180009c96  pop     rsi
0x180009c97  pop     rbp
0x180009c98  retn
0x180009c99  test    r13, r13
0x180009c9c  jz      loc_18000A1DD
0x180009ca2  mov     r15, [rcx+40h]
0x180009ca6  xor     r12d, r12d
0x180009ca9  mov     esi, r12d
0x180009cac  mov     [rsp+2C0h+var_260], r12
0x180009cb1  mov     [rsp+2C0h+cbData], 104h
0x180009cb9  mov     [rsp+2C0h+Type], r12d
0x180009cbe  mov     [rsp+2C0h+hKey], r15
0x180009cc3  mov     [rsp+2C0h+var_258], r12
0x180009cc8  xor     edx, edx; unsigned __int16 *
0x180009cca  lea     rcx, [rsp+2C0h+var_258]; struct CSpRegistryIsolator **
0x180009ccf  call    ?GetInitializedSingleton@CSpRegistryIsolator@@SAJPEAPEAV1@PEAG@Z; CSpRegistryIsolator::GetInitializedSingleton(CSpRegistryIsolator * *,ushort *)
0x180009cd4  test    eax, eax
0x180009cd6  js      loc_18000A108
0x180009cdc  mov     r11, [rsp+2C0h+var_258]
0x180009ce1  test    r11, r11
0x180009ce4  jz      loc_18000A0D6
0x180009cea  mov     r14, r15
0x180009ced  mov     [rsp+2C0h+hKey], r15
0x180009cf2  mov     edx, r12d
0x180009cf5  mov     r8, [r11+8]
0x180009cf9  nop     dword ptr [rax+00000000h]
0x180009d00  cmp     rdx, r8
0x180009d03  jnb     short loc_180009D64
0x180009d05  mov     r10, rdx
0x180009d08  shl     r10, 4
0x180009d0c  add     r10, [r11]
0x180009d0f  cmp     r15, [r10+8]
0x180009d13  jz      short loc_180009D1A
0x180009d15  inc     rdx
0x180009d18  jmp     short loc_180009D00
0x180009d1a  mov     [rsp+2C0h+lpdwDisposition], r12; lpdwDisposition
0x180009d1f  lea     rax, [rsp+2C0h+hKey]
0x180009d24  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180009d29  mov     [rsp+2C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180009d2e  mov     [rsp+2C0h+samDesired], 0F003Fh; samDesired
0x180009d36  mov     [rsp+2C0h+dwOptions], 1; int
0x180009d3e  xor     r9d, r9d; lpClass
0x180009d41  xor     r8d, r8d; Reserved
0x180009d44  mov     rdx, [r10]; lpSubKey
0x180009d47  mov     rcx, [r11+18h]; hKey
0x180009d4b  call    cs:__imp_RegCreateKeyExW
0x180009d51  test    eax, eax
0x180009d53  jg      loc_18000A0C7
0x180009d59  js      loc_18000A0ED
0x180009d5f  mov     r14, [rsp+2C0h+hKey]
0x180009d64  mov     eax, [rsp+2C0h+cbData]
0x180009d68  add     eax, eax
0x180009d6a  mov     [rsp+2C0h+cbData], eax
0x180009d6e  lea     rax, [rsp+2C0h+cbData]
0x180009d73  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x180009d78  lea     rax, [rsp+2C0h+Data]
0x180009d7d  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x180009d82  lea     r9, [rsp+2C0h+Type]; lpType
0x180009d87  xor     r8d, r8d; lpReserved
0x180009d8a  mov     rdx, rdi; lpValueName
0x180009d8d  mov     rcx, r14; hKey
0x180009d90  call    cs:__imp_RegQueryValueExW
0x180009d96  mov     r14d, eax
0x180009d99  mov     eax, [rsp+2C0h+cbData]
0x180009d9d  shr     eax, 1
0x180009d9f  mov     [rsp+2C0h+cbData], eax
0x180009da3  test    r14d, r14d
0x180009da6  jnz     short loc_180009DB3
0x180009da8  cmp     [rsp+2C0h+Type], 7
0x180009dad  jz      loc_18000A11F
0x180009db3  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180009db8  cmp     rcx, r15
0x180009dbb  jnz     loc_18000A197
0x180009dc1  mov     [r13+0], r12
0x180009dc5  mov     r12d, 8
0x180009dcb  test    r14d, r14d
0x180009dce  jz      loc_180009ECD
0x180009dd4  cmp     r14d, 2
0x180009dd8  jz      loc_18000A08C
0x180009dde  cmp     r14d, 0EAh
0x180009de5  jnz     short loc_180009E4A
0x180009de7  mov     edx, [rsp+2C0h+cbData]
0x180009deb  cmp     edx, 4FFFFFFFh
0x180009df1  jnb     loc_18000A09F
0x180009df7  lea     ecx, [rdx+1]
0x180009dfa  add     rcx, rcx; cb
0x180009dfd  mov     ebx, edx
0x180009dff  cmp     rcx, rdx
0x180009e02  jbe     loc_18000A09F
0x180009e08  call    cs:__imp_CoTaskMemAlloc
0x180009e0e  mov     rsi, rax
0x180009e11  mov     [rsp+2C0h+var_260], rax
0x180009e16  test    rax, rax
0x180009e19  jz      loc_18000A1AB
0x180009e1f  lea     r8, [rbx+rbx]; Size
0x180009e23  xor     eax, eax
0x180009e25  mov     [r8+rsi], ax
0x180009e2a  xor     edx, edx; Val
0x180009e2c  mov     rcx, rsi; void *
0x180009e2f  call    memset_0
0x180009e34  lea     r9, [rsp+2C0h+cbData]; lpcbData
0x180009e39  mov     r8, rsi; lpData
0x180009e3c  mov     rdx, rdi; lpValueName
0x180009e3f  mov     rcx, r15; hKey
0x180009e42  call    ?SpRegQueryStringValueW@@YAJPEAUHKEY__@@PEBGPEAGPEAK@Z; SpRegQueryStringValueW(HKEY__ *,ushort const *,ushort *,ulong *)
0x180009e47  mov     r14d, eax
0x180009e4a  test    r14d, r14d
0x180009e4d  jg      loc_18000A0AA
0x180009e53  jz      loc_180009F25
0x180009e59  mov     r15d, 0DEADh
0x180009e5f  mov     ebx, 8004503Ah
0x180009e64  cmp     r14d, 80070002h
0x180009e6b  cmovz   r14d, ebx
0x180009e6f  test    rsi, rsi
0x180009e72  jz      short loc_180009EB8
0x180009e74  call    cs:__imp_GetProcessHeap
0x180009e7a  mov     r8, rsi; lpMem
0x180009e7d  xor     edx, edx; dwFlags
0x180009e7f  mov     rcx, rax; hHeap
0x180009e82  call    cs:__imp_HeapSize
0x180009e88  lea     rcx, [rax-3]
0x180009e8c  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x180009e90  ja      short loc_180009EAF
0x180009e92  shr     rax, 1
0x180009e95  dec     rax
0x180009e98  cmp     rax, 8
0x180009e9c  jb      loc_18000A02A
0x180009ea2  movzx   eax, r15w
0x180009ea6  mov     rdi, rsi
0x180009ea9  mov     rcx, r12
0x180009eac  rep stosw
0x180009eaf  mov     rcx, rsi; pv
0x180009eb2  call    cs:__imp_CoTaskMemFree
0x180009eb8  cmp     r14d, 80070002h
0x180009ebf  jz      loc_18000A1D6
0x180009ec5  mov     eax, r14d
0x180009ec8  jmp     loc_180009C6F
0x180009ecd  xor     r14d, r14d
0x180009ed0  lea     rax, [rsp+2C0h+Data]
0x180009ed5  inc     rbx
0x180009ed8  cmp     [rax+rbx*2], r14w
0x180009edd  jnz     short loc_180009ED5
0x180009edf  cmp     ebx, 4FFFFFFFh
0x180009ee5  jnb     loc_18000A03B
0x180009eeb  lea     ecx, [rbx+1]
0x180009eee  add     rcx, rcx; cb
0x180009ef1  mov     edi, ebx
0x180009ef3  cmp     rcx, rdi
0x180009ef6  jbe     loc_18000A03B
0x180009efc  call    cs:__imp_CoTaskMemAlloc
0x180009f02  mov     rsi, rax
0x180009f05  test    rax, rax
0x180009f08  jz      loc_18000A01A
0x180009f0e  xor     eax, eax
0x180009f10  mov     [rsi+rdi*2], ax
0x180009f14  lea     r8, [rbx+rbx]; Size
0x180009f18  lea     rdx, [rsp+2C0h+Data]; Src
0x180009f1d  mov     rcx, rsi; void *
0x180009f20  call    memcpy_0
0x180009f25  mov     edx, [rsp+2C0h+cbData]
0x180009f29  add     edx, 104h
0x180009f2f  mov     r15d, 8007000Eh
0x180009f35  cmp     edx, 4FFFFFFFh
0x180009f3b  jnb     loc_18000A04B
0x180009f41  lea     ecx, [rdx+1]
0x180009f44  add     rcx, rcx; cb
0x180009f47  mov     edi, edx
0x180009f49  cmp     rcx, rdi
0x180009f4c  jbe     loc_18000A04B
0x180009f52  call    cs:__imp_CoTaskMemAlloc
0x180009f58  mov     rbx, rax
0x180009f5b  test    rax, rax
0x180009f5e  jz      loc_18000A1C6
0x180009f64  lea     r8, [rdi+rdi]; Size
0x180009f68  xor     eax, eax
0x180009f6a  mov     [r8+rbx], ax
0x180009f6f  xor     edx, edx; Val
0x180009f71  mov     rcx, rbx; void *
0x180009f74  call    memset_0
0x180009f79  mov     r8d, [rsp+2C0h+cbData]
0x180009f7e  add     r8d, 104h; nSize
0x180009f85  mov     rdx, rbx; lpDst
0x180009f88  mov     rcx, rsi; lpSrc
0x180009f8b  call    cs:__imp_ExpandEnvironmentStringsW
0x180009f91  mov     ecx, eax
0x180009f93  test    eax, eax
0x180009f95  jz      loc_18000A060
0x180009f9b  mov     eax, [rsp+2C0h+cbData]
0x180009f9f  add     eax, 104h
0x180009fa4  cmp     ecx, eax
0x180009fa6  ja      loc_18000A1BB
0x180009fac  mov     rax, rbx
0x180009faf  xor     ebx, ebx
0x180009fb1  mov     [r13+0], rax
0x180009fb5  cmp     qword ptr [r13+0], 0
0x180009fba  cmovz   r14d, r15d
0x180009fbe  test    rbx, rbx
0x180009fc1  jz      loc_180009E59
0x180009fc7  call    cs:__imp_GetProcessHeap
0x180009fcd  mov     r8, rbx; lpMem
0x180009fd0  xor     edx, edx; dwFlags
0x180009fd2  mov     rcx, rax; hHeap
0x180009fd5  call    cs:__imp_HeapSize
0x180009fdb  lea     rcx, [rax-3]
0x180009fdf  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x180009fe3  ja      loc_18000A084
0x180009fe9  shr     rax, 1
0x180009fec  lea     rcx, [rax-1]
0x180009ff0  cmp     rcx, r12
0x180009ff3  jb      loc_18000A07B
0x180009ff9  mov     rcx, r12
0x180009ffc  mov     r15d, 0DEADh
0x18000a002  movzx   eax, r15w
0x18000a006  mov     rdi, rbx
0x18000a009  rep stosw
0x18000a00c  mov     rcx, rbx; pv
0x18000a00f  call    cs:__imp_CoTaskMemFree
0x18000a015  jmp     loc_180009E5F
0x18000a01a  mov     ecx, 0Eh; dwErrCode
0x18000a01f  call    cs:__imp_SetLastError
0x18000a025  jmp     loc_180009F25
0x18000a02a  mov     r12, rax
0x18000a02d  test    rax, rax
0x18000a030  jz      loc_180009EAF
0x18000a036  jmp     loc_180009EA2
0x18000a03b  mov     ecx, 216h; dwErrCode
0x18000a040  call    cs:__imp_SetLastError
0x18000a046  jmp     loc_180009F25
0x18000a04b  mov     ecx, 216h; dwErrCode
0x18000a050  call    cs:__imp_SetLastError
0x18000a056  xor     ebx, ebx
0x18000a058  mov     r14d, r15d
0x18000a05b  jmp     loc_180009FB5
0x18000a060  call    cs:__imp_GetLastError
0x18000a066  test    eax, eax
0x18000a068  jg      short loc_18000A0BD
0x18000a06a  mov     r14d, 80004005h
0x18000a070  test    eax, eax
0x18000a072  cmovs   r14d, eax
0x18000a076  jmp     loc_180009FB5
0x18000a07b  test    rcx, rcx
0x18000a07e  jnz     loc_180009FFC
0x18000a084  mov     r15d, 0DEADh
0x18000a08a  jmp     short loc_18000A00C
0x18000a08c  mov     ebx, 8004503Ah
0x18000a091  mov     r14d, ebx
0x18000a094  mov     r15d, 0DEADh
0x18000a09a  jmp     loc_180009E6F
0x18000a09f  mov     ecx, 216h; dwErrCode
0x18000a0a4  call    cs:__imp_SetLastError
0x18000a0aa  movzx   r14d, r14w
0x18000a0ae  or      r14d, 80070000h
0x18000a0b5  test    r14d, r14d
0x18000a0b8  jmp     loc_180009E53
0x18000a0bd  movzx   eax, ax
0x18000a0c0  or      eax, 80070000h
0x18000a0c5  jmp     short loc_18000A06A
0x18000a0c7  movzx   eax, ax
0x18000a0ca  or      eax, 80070000h
0x18000a0cf  test    eax, eax
0x18000a0d1  jmp     loc_180009D59
0x18000a0d6  mov     r14d, 0Eh
0x18000a0dc  mov     eax, [rsp+2C0h+cbData]
0x18000a0e0  add     eax, eax
  ... truncated ...
```
