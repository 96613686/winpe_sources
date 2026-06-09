# RtmWriteAddressFamilyConfig

- ea: `0x180004b50`
- end: `0x1800052c8`
- name: `RtmWriteAddressFamilyConfig`
- size: `1912`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800052d0`

## callees

- `0x180002c5c`
- `0x180004b50`
- `0x180005768`
- `0x180007a34`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x180004c49`
- `ADVAPI32!RegOpenKeyExA` at `0x180004c49`
- `ADVAPI32!RegCloseKey` at `0x180004d59`
- `ADVAPI32!RegCloseKey` at `0x180004fd7`
- `ADVAPI32!RegCloseKey` at `0x18000521e`
- `ADVAPI32!RegCloseKey` at `0x180004d59`
- `ADVAPI32!RegCloseKey` at `0x180004fd7`
- `ADVAPI32!RegCloseKey` at `0x18000521e`
- `ADVAPI32!RegCreateKeyExA` at `0x180004d4c`
- `ADVAPI32!RegCreateKeyExA` at `0x180004d4c`
- `ADVAPI32!RegDeleteKeyA` at `0x180005256`
- `ADVAPI32!RegDeleteKeyA` at `0x180005256`
- `ADVAPI32!RegSetValueExA` at `0x180004e42`
- `ADVAPI32!RegSetValueExA` at `0x180004ea4`
- `ADVAPI32!RegSetValueExA` at `0x180004eea`
- `ADVAPI32!RegSetValueExA` at `0x180004f36`
- `ADVAPI32!RegSetValueExA` at `0x180004f7c`
- `ADVAPI32!RegSetValueExA` at `0x180004fc2`
- `ADVAPI32!RegSetValueExA` at `0x180004e42`
- `ADVAPI32!RegSetValueExA` at `0x180004ea4`
- `ADVAPI32!RegSetValueExA` at `0x180004eea`
- `ADVAPI32!RegSetValueExA` at `0x180004f36`
- `ADVAPI32!RegSetValueExA` at `0x180004f7c`
- `ADVAPI32!RegSetValueExA` at `0x180004fc2`

## string_xrefs

- `0x180005139`: `Address Family Config: Address Size %d out of bounds`
- `0x180004e6b`: `Address Family Config: No supported views`
- `0x1800050b9`: `Address Family Config: # opaque ptrs out of range`
- `0x180005074`: `Address Family Config: # nexthops out of range`
- `0x18000502f`: `Address Family Config: # handles returned in enum`
- `0x180004bd5`: `Entered: RtmWriteAddressFamilyConfig `
- `0x180004c71`: `Address Family Config: Error %d opening instance key`
- `0x180004ce4`: `Leaving: RtmWriteAddressFamilyConfig `
- `0x180004df5`: `Leaving: RtmWriteAddressFamilyConfig `
- `0x180004d7f`: `Address Family Config: Error %d creating address family key`
- `0x1800050fb`: `Address Family Config: # Change notify regs out of range`
- `0x180004fe6`: `Leaving: RtmWriteAddressFamilyConfig`
- `0x180005265`: `Leaving: RtmWriteAddressFamilyConfig`
- `0x1800051b8`: `Address Family Config: Error %d writing address family params`

## pseudocode

```c
__int64 __fastcall RtmWriteAddressFamilyConfig(__int64 a1, unsigned __int16 a2, _DWORD *a3)
{
  int v3; // ebx
  __int64 v5; // r8
  __int64 result; // rax
  unsigned int v7; // eax
  __int64 v8; // r8
  unsigned int v9; // esi
  char v10; // cl
  __int64 v11; // rbx
  const wchar_t *v12; // rax
  int v13; // r15d
  char v14; // cl
  __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // r8
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v22; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[16]; // [rsp+68h] [rbp-98h] BYREF
  const wchar_t *v25; // [rsp+78h] [rbp-88h]
  __int64 v26; // [rsp+80h] [rbp-80h]
  int v27; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v28[2044]; // [rsp+94h] [rbp-6Ch] BYREF
  char pszDest[272]; // [rsp+890h] [rbp+790h] BYREF

  v3 = a2;
  hKey = 0;
  v22 = 0;
  *(_DWORD *)Data = 0;
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  if ( !(_DWORD)qword_18002BD00 )
  {
    result = RtmApiStartup();
    if ( (_DWORD)result )
      return result;
  }
  if ( (byte_18002BD1A & 8) != 0 )
  {
    v26 = 76;
    v25 = L"Entered: RtmWriteAddressFamilyConfig ";
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RRAS_RTM_TRACE_INFO, v5, 2, v24);
  }
  StringCchPrintfA((STRSAFE_LPSTR)lpSubKey + 66, 0xC2u, "\\Instance %05d", 0);
  v7 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  v9 = v7;
  if ( v7 )
  {
    v10 = byte_18002BD1A;
    if ( (byte_18002BD1A & 4) != 0 )
    {
      LOWORD(v27) = 0;
      FormatRRASErrorString(&v27, L"Address Family Config: Error %d opening instance key", v7);
      v10 = byte_18002BD1A;
      if ( (byte_18002BD1A & 4) != 0 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&v28[2 * v11 - 4] );
        v26 = (unsigned int)(2 * v11 + 2);
        v25 = (const wchar_t *)&v27;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RRAS_RTM_TRACE_ERROR, v8, 2, v24);
        v10 = byte_18002BD1A;
      }
    }
    if ( (v10 & 8) == 0 )
      return v9;
    v12 = L"Leaving: RtmWriteAddressFamilyConfig ";
    v26 = 76;
LABEL_71:
    v25 = v12;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RRAS_RTM_TRACE_INFO, v8, 2, v24);
    return v9;
  }
  v13 = v3;
  StringCchPrintfA(pszDest, 0x104u, "AddressFamily %05d", v3);
  v9 = RegCreateKeyExA(hKey, pszDest, 0, 0, 0, 0x20006u, 0, &v22, 0);
  RegCloseKey(hKey);
  if ( v9 )
  {
    v14 = byte_18002BD1A;
    if ( (byte_18002BD1A & 4) != 0 )
    {
      LOWORD(v27) = 0;
      FormatRRASErrorString(&v27, L"Address Family Config: Error %d creating address family key", v9);
      v14 = byte_18002BD1A;
      if ( (byte_18002BD1A & 4) != 0 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v28[2 * v15 - 4] );
        v26 = (unsigned int)(2 * v15 + 2);
        v25 = (const wchar_t *)&v27;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RRAS_RTM_TRACE_ERROR, v8, 2, v24);
        v14 = byte_18002BD1A;
      }
    }
    if ( (v14 & 8) == 0 )
      return v9;
    v12 = L"Leaving: RtmWriteAddressFamilyConfig ";
    v26 = 76;
    goto LABEL_71;
  }
  v16 = -1;
  *(_DWORD *)Data = *a3;
  if ( (unsigned int)(*(_DWORD *)Data - 1) > 0xF )
  {
    if ( (byte_18002BD1A & 8) == 0 )
      goto LABEL_64;
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"Address Family Config: Address Size %d out of bounds");
    if ( (byte_18002BD1A & 8) == 0 )
      goto LABEL_64;
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)&v28[2 * v19 - 4] );
LABEL_62:
    v25 = (const wchar_t *)&v27;
    v26 = (unsigned int)(2 * v19 + 2);
    goto LABEL_63;
  }
  v9 = RegSetValueExA(v22, "AddressSize", 0, 4u, Data, 4u);
  if ( v9 )
    goto LABEL_65;
  *(_DWORD *)Data = a3[1];
  if ( !*(_DWORD *)Data )
  {
    if ( (byte_18002BD1A & 8) == 0 )
    {
LABEL_64:
      v9 = 87;
LABEL_65:
      if ( (byte_18002BD1A & 4) != 0 )
      {
        LOWORD(v27) = 0;
        FormatRRASErrorString(&v27, L"Address Family Config: Error %d writing address family params", v9);
        if ( (byte_18002BD1A & 4) != 0 )
        {
          do
            ++v16;
          while ( *(_WORD *)&v28[2 * v16 - 4] );
          v26 = (unsigned int)(2 * v16 + 2);
          v25 = (const wchar_t *)&v27;
          McGenEventWrite_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RRAS_RTM_TRACE_ERROR,
            v20,
            2,
            v24);
        }
      }
      RegCloseKey(v22);
      StringCchPrintfA((STRSAFE_LPSTR)lpSubKey + 66, 0xC2u, "\\Instance %05d\\AddressFamily %05d", 0, v13);
      RegDeleteKeyA(HKEY_LOCAL_MACHINE, lpSubKey);
      if ( (byte_18002BD1A & 8) == 0 )
        return v9;
      v12 = L"Leaving: RtmWriteAddressFamilyConfig";
      v26 = 74;
      goto LABEL_71;
    }
    v26 = 84;
    v25 = L"Address Family Config: No supported views";
LABEL_63:
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RRAS_RTM_TRACE_INFO, v17, 2, v24);
    goto LABEL_64;
  }
  v9 = RegSetValueExA(v22, "ViewsSupported", 0, 4u, Data, 4u);
  if ( v9 )
    goto LABEL_65;
  *(_DWORD *)Data = a3[5];
  if ( (unsigned int)(*(_DWORD *)Data - 1) > 0x1F )
  {
    if ( (byte_18002BD1A & 8) == 0 )
      goto LABEL_64;
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"Address Family Config: # Change notify regs out of range");
    if ( (byte_18002BD1A & 8) == 0 )
      goto LABEL_64;
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)&v28[2 * v19 - 4] );
    goto LABEL_62;
  }
  v9 = RegSetValueExA(v22, "MaxChangeNotifyRegistrations", 0, 4u, Data, 4u);
  if ( v9 )
    goto LABEL_65;
  *(_DWORD *)Data = a3[2];
  if ( *(_DWORD *)Data > 0xAu )
  {
    if ( (byte_18002BD1A & 8) == 0 )
      goto LABEL_64;
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"Address Family Config: # opaque ptrs out of range");
    if ( (byte_18002BD1A & 8) == 0 )
      goto LABEL_64;
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)&v28[2 * v19 - 4] );
    goto LABEL_62;
  }
  v9 = RegSetValueExA(v22, "MaxOpaqueInfoPointers", 0, 4u, Data, 4u);
  if ( v9 )
    goto LABEL_65;
  *(_DWORD *)Data = a3[3];
  if ( (unsigned int)(*(_DWORD *)Data - 1) > 9 )
  {
    if ( (byte_18002BD1A & 8) == 0 )
      goto LABEL_64;
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"Address Family Config: # nexthops out of range");
    if ( (byte_18002BD1A & 8) == 0 )
      goto LABEL_64;
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)&v28[2 * v19 - 4] );
    goto LABEL_62;
  }
  v9 = RegSetValueExA(v22, "MaxNextHopsInRoute", 0, 4u, Data, 4u);
  if ( v9 )
    goto LABEL_65;
  *(_DWORD *)Data = a3[4];
  if ( (unsigned int)(*(_DWORD *)Data - 1) > 0x63 )
  {
    if ( (byte_18002BD1A & 8) == 0 )
      goto LABEL_64;
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v27, L"Address Family Config: # handles returned in enum");
    if ( (byte_18002BD1A & 8) == 0 )
      goto LABEL_64;
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)&v28[2 * v19 - 4] );
    goto LABEL_62;
  }
  v9 = RegSetValueExA(v22, "MaxHandlesReturnedInEnum", 0, 4u, Data, 4u);
  if ( v9 )
    goto LABEL_65;
  RegCloseKey(v22);
  if ( (byte_18002BD1A & 8) != 0 )
  {
    v26 = 74;
    v25 = L"Leaving: RtmWriteAddressFamilyConfig";
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RRAS_RTM_TRACE_INFO, v18, v9 + 2, v24);
  }
  return 0;
}

```

## disassembly

```asm
0x180004b50  mov     [rsp-8+arg_0], rbx
0x180004b55  push    rbp
0x180004b56  push    rsi
0x180004b57  push    rdi
0x180004b58  push    r12
0x180004b5a  push    r13
0x180004b5c  push    r14
0x180004b5e  push    r15
0x180004b60  lea     rbp, [rsp-8B0h]
0x180004b68  sub     rsp, 9B0h
0x180004b6f  mov     rax, cs:__security_cookie
0x180004b76  xor     rax, rsp
0x180004b79  mov     [rbp+8E0h+var_40], rax
0x180004b80  xor     r12d, r12d
0x180004b83  movzx   ebx, dx
0x180004b86  mov     r14, r8
0x180004b89  mov     [rsp+9E0h+hKey], r12
0x180004b8e  xor     edx, edx; Val
0x180004b90  mov     [rsp+9E0h+var_988], r12
0x180004b95  mov     r8d, 7FCh; Size
0x180004b9b  mov     dword ptr [rsp+9E0h+Data], r12d
0x180004ba0  lea     rcx, [rbp+8E0h+var_94C]; void *
0x180004ba4  mov     [rbp+8E0h+var_950], r12d
0x180004ba8  call    memset_0
0x180004bad  cmp     dword ptr cs:qword_18002BD00, r12d
0x180004bb4  jnz     short loc_180004BC3
0x180004bb6  call    RtmApiStartup
0x180004bbb  test    eax, eax
0x180004bbd  jnz     loc_18000529E
0x180004bc3  mov     r13b, 8
0x180004bc6  mov     r15d, 2
0x180004bcc  test    cs:byte_18002BD1A, r13b
0x180004bd3  jz      short loc_180004C09
0x180004bd5  lea     rax, aEnteredRtmwrit_1; "Entered: RtmWriteAddressFamilyConfig "
0x180004bdc  mov     [rbp+8E0h+var_960], 4Ch ; 'L'
0x180004be4  mov     [rsp+9E0h+var_968], rax
0x180004be9  lea     rdx, RRAS_RTM_TRACE_INFO
0x180004bf0  lea     rax, [rsp+9E0h+var_978]
0x180004bf5  mov     r9d, r15d
0x180004bf8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004bff  mov     [rsp+9E0h+phkResult], rax
0x180004c04  call    McGenEventWrite_EventWriteTransfer
0x180004c09  mov     rcx, cs:lpSubKey
0x180004c10  lea     r8, aInstance05d; "\\Instance %05d"
0x180004c17  add     rcx, 42h ; 'B'; pszDest
0x180004c1b  xor     r9d, r9d
0x180004c1e  mov     edx, 0C2h; cchDest
0x180004c23  call    StringCchPrintfA
0x180004c28  mov     rdx, cs:lpSubKey; lpSubKey
0x180004c2f  lea     rax, [rsp+9E0h+hKey]
0x180004c34  mov     r9d, 20019h; samDesired
0x180004c3a  mov     [rsp+9E0h+phkResult], rax; phkResult
0x180004c3f  xor     r8d, r8d; ulOptions
0x180004c42  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004c49  call    cs:__imp_RegOpenKeyExA
0x180004c4f  mov     esi, eax
0x180004c51  test    eax, eax
0x180004c53  jz      loc_180004CFB
0x180004c59  mov     cl, cs:byte_18002BD1A
0x180004c5f  mov     edi, 4
0x180004c64  test    dil, cl
0x180004c67  jz      short loc_180004CDB
0x180004c69  mov     r8d, eax
0x180004c6c  mov     word ptr [rbp+8E0h+var_950], r12w
0x180004c71  lea     rdx, aAddressFamilyC_6; "Address Family Config: Error %d opening"...
0x180004c78  lea     rcx, [rbp+8E0h+var_950]
0x180004c7c  call    FormatRRASErrorString
0x180004c81  mov     cl, cs:byte_18002BD1A
0x180004c87  test    dil, cl
0x180004c8a  jz      short loc_180004CDB
0x180004c8c  lea     rax, [rbp+8E0h+var_950]
0x180004c90  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004c94  inc     rbx
0x180004c97  cmp     [rax+rbx*2], r12w
0x180004c9c  jnz     short loc_180004C94
0x180004c9e  lea     eax, ds:2[rbx*2]
0x180004ca5  mov     dword ptr [rbp+8E0h+var_960+4], r12d
0x180004ca9  lea     rcx, [rbp+8E0h+var_950]
0x180004cad  mov     dword ptr [rbp+8E0h+var_960], eax
0x180004cb0  lea     rax, [rsp+9E0h+var_978]
0x180004cb5  mov     [rsp+9E0h+var_968], rcx
0x180004cba  mov     r9d, r15d
0x180004cbd  mov     [rsp+9E0h+phkResult], rax
0x180004cc2  lea     rdx, RRAS_RTM_TRACE_ERROR
0x180004cc9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004cd0  call    McGenEventWrite_EventWriteTransfer
0x180004cd5  mov     cl, cs:byte_18002BD1A
0x180004cdb  test    r13b, cl
0x180004cde  jz      loc_18000529C
0x180004ce4  lea     rax, aLeavingRtmwrit_1; "Leaving: RtmWriteAddressFamilyConfig "
0x180004ceb  mov     [rbp+8E0h+var_960], 4Ch ; 'L'
0x180004cf3  mov     r9d, r15d
0x180004cf6  jmp     loc_18000527A
0x180004cfb  mov     r9d, ebx
0x180004cfe  lea     r8, aAddressfamily0; "AddressFamily %05d"
0x180004d05  mov     edx, 104h; cchDest
0x180004d0a  lea     rcx, [rbp+8E0h+pszDest]; pszDest
0x180004d11  mov     r15d, ebx
0x180004d14  call    StringCchPrintfA
0x180004d19  mov     rcx, [rsp+9E0h+hKey]; hKey
0x180004d1e  lea     rax, [rsp+9E0h+var_988]
0x180004d23  mov     [rsp+9E0h+lpdwDisposition], r12; lpdwDisposition
0x180004d28  lea     rdx, [rbp+8E0h+pszDest]; lpSubKey
0x180004d2f  mov     [rsp+9E0h+var_9A8], rax; phkResult
0x180004d34  xor     r9d, r9d; lpClass
0x180004d37  mov     [rsp+9E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180004d3c  xor     r8d, r8d; Reserved
0x180004d3f  mov     [rsp+9E0h+samDesired], 20006h; samDesired
0x180004d47  mov     dword ptr [rsp+9E0h+phkResult], r12d; dwOptions
0x180004d4c  call    cs:__imp_RegCreateKeyExA
0x180004d52  mov     rcx, [rsp+9E0h+hKey]; hKey
0x180004d57  mov     esi, eax
0x180004d59  call    cs:__imp_RegCloseKey
0x180004d5f  mov     edi, 4
0x180004d64  test    esi, esi
0x180004d66  jz      loc_180004E09
0x180004d6c  mov     cl, cs:byte_18002BD1A
0x180004d72  test    dil, cl
0x180004d75  jz      short loc_180004DEC
0x180004d77  mov     r8d, esi
0x180004d7a  mov     word ptr [rbp+8E0h+var_950], r12w
0x180004d7f  lea     rdx, aAddressFamilyC; "Address Family Config: Error %d creatin"...
0x180004d86  lea     rcx, [rbp+8E0h+var_950]
0x180004d8a  call    FormatRRASErrorString
0x180004d8f  mov     cl, cs:byte_18002BD1A
0x180004d95  test    dil, cl
0x180004d98  jz      short loc_180004DEC
0x180004d9a  lea     rax, [rbp+8E0h+var_950]
0x180004d9e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004da2  inc     rbx
0x180004da5  cmp     [rax+rbx*2], r12w
0x180004daa  jnz     short loc_180004DA2
0x180004dac  lea     eax, ds:2[rbx*2]
0x180004db3  mov     dword ptr [rbp+8E0h+var_960+4], r12d
0x180004db7  lea     rcx, [rbp+8E0h+var_950]
0x180004dbb  mov     dword ptr [rbp+8E0h+var_960], eax
0x180004dbe  lea     rax, [rsp+9E0h+var_978]
0x180004dc3  mov     [rsp+9E0h+var_968], rcx
0x180004dc8  mov     r9d, 2
0x180004dce  mov     [rsp+9E0h+phkResult], rax
0x180004dd3  lea     rdx, RRAS_RTM_TRACE_ERROR
0x180004dda  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004de1  call    McGenEventWrite_EventWriteTransfer
0x180004de6  mov     cl, cs:byte_18002BD1A
0x180004dec  test    r13b, cl
0x180004def  jz      loc_18000529C
0x180004df5  lea     rax, aLeavingRtmwrit_1; "Leaving: RtmWriteAddressFamilyConfig "
0x180004dfc  mov     [rbp+8E0h+var_960], 4Ch ; 'L'
0x180004e04  jmp     loc_180005274
0x180004e09  mov     r8d, [r14]
0x180004e0c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004e10  mov     dword ptr [rsp+9E0h+Data], r8d
0x180004e15  lea     eax, [r8-1]
0x180004e19  cmp     eax, 0Fh
0x180004e1c  ja      loc_180005130
0x180004e22  mov     rcx, [rsp+9E0h+var_988]; hKey
0x180004e27  lea     rax, [rsp+9E0h+Data]
0x180004e2c  mov     [rsp+9E0h+samDesired], edi; cbData
0x180004e30  lea     rdx, ValueName; "AddressSize"
0x180004e37  mov     r9d, edi; dwType
0x180004e3a  mov     [rsp+9E0h+phkResult], rax; lpData
0x180004e3f  xor     r8d, r8d; Reserved
0x180004e42  call    cs:__imp_RegSetValueExA
0x180004e48  mov     esi, eax
0x180004e4a  test    eax, eax
0x180004e4c  jnz     loc_1800051A7
0x180004e52  mov     eax, [r14+4]
0x180004e56  mov     dword ptr [rsp+9E0h+Data], eax
0x180004e5a  test    eax, eax
0x180004e5c  jnz     short loc_180004E84
0x180004e5e  test    cs:byte_18002BD1A, r13b
0x180004e65  jz      loc_1800051A2
0x180004e6b  lea     rax, aAddressFamilyC_0; "Address Family Config: No supported vie"...
0x180004e72  mov     [rbp+8E0h+var_960], 54h ; 'T'
0x180004e7a  mov     [rsp+9E0h+var_968], rax
0x180004e7f  jmp     loc_18000517F
0x180004e84  mov     rcx, [rsp+9E0h+var_988]; hKey
0x180004e89  lea     rax, [rsp+9E0h+Data]
0x180004e8e  mov     [rsp+9E0h+samDesired], edi; cbData
0x180004e92  lea     rdx, aViewssupported; "ViewsSupported"
0x180004e99  mov     r9d, edi; dwType
0x180004e9c  mov     [rsp+9E0h+phkResult], rax; lpData
0x180004ea1  xor     r8d, r8d; Reserved
0x180004ea4  call    cs:__imp_RegSetValueExA
0x180004eaa  mov     esi, eax
0x180004eac  test    eax, eax
0x180004eae  jnz     loc_1800051A7
0x180004eb4  mov     r8d, [r14+14h]
0x180004eb8  mov     dword ptr [rsp+9E0h+Data], r8d
0x180004ebd  lea     eax, [r8-1]
0x180004ec1  cmp     eax, 1Fh
0x180004ec4  ja      loc_1800050EE
0x180004eca  mov     rcx, [rsp+9E0h+var_988]; hKey
0x180004ecf  lea     rax, [rsp+9E0h+Data]
0x180004ed4  mov     [rsp+9E0h+samDesired], edi; cbData
0x180004ed8  lea     rdx, aMaxchangenotif; "MaxChangeNotifyRegistrations"
0x180004edf  mov     r9d, edi; dwType
0x180004ee2  mov     [rsp+9E0h+phkResult], rax; lpData
0x180004ee7  xor     r8d, r8d; Reserved
0x180004eea  call    cs:__imp_RegSetValueExA
0x180004ef0  mov     esi, eax
0x180004ef2  test    eax, eax
0x180004ef4  jnz     loc_1800051A7
0x180004efa  mov     r8d, [r14+8]
0x180004efe  mov     dword ptr [rsp+9E0h+Data], r8d
0x180004f03  test    r8d, r8d
0x180004f06  js      loc_1800050AC
0x180004f0c  cmp     r8d, 0Ah
0x180004f10  ja      loc_1800050AC
0x180004f16  mov     rcx, [rsp+9E0h+var_988]; hKey
0x180004f1b  lea     rax, [rsp+9E0h+Data]
0x180004f20  mov     [rsp+9E0h+samDesired], edi; cbData
0x180004f24  lea     rdx, aMaxopaqueinfop; "MaxOpaqueInfoPointers"
0x180004f2b  mov     r9d, edi; dwType
0x180004f2e  mov     [rsp+9E0h+phkResult], rax; lpData
0x180004f33  xor     r8d, r8d; Reserved
0x180004f36  call    cs:__imp_RegSetValueExA
0x180004f3c  mov     esi, eax
0x180004f3e  test    eax, eax
0x180004f40  jnz     loc_1800051A7
0x180004f46  mov     r8d, [r14+0Ch]
0x180004f4a  mov     dword ptr [rsp+9E0h+Data], r8d
0x180004f4f  lea     eax, [r8-1]
0x180004f53  cmp     eax, 9
0x180004f56  ja      loc_180005067
0x180004f5c  mov     rcx, [rsp+9E0h+var_988]; hKey
0x180004f61  lea     rax, [rsp+9E0h+Data]
0x180004f66  mov     [rsp+9E0h+samDesired], edi; cbData
0x180004f6a  lea     rdx, aMaxnexthopsinr; "MaxNextHopsInRoute"
0x180004f71  mov     r9d, edi; dwType
0x180004f74  mov     [rsp+9E0h+phkResult], rax; lpData
0x180004f79  xor     r8d, r8d; Reserved
0x180004f7c  call    cs:__imp_RegSetValueExA
0x180004f82  mov     esi, eax
0x180004f84  test    eax, eax
0x180004f86  jnz     loc_1800051A7
0x180004f8c  mov     r8d, [r14+10h]
0x180004f90  mov     dword ptr [rsp+9E0h+Data], r8d
0x180004f95  lea     eax, [r8-1]
0x180004f99  cmp     eax, 63h ; 'c'
0x180004f9c  ja      loc_180005022
0x180004fa2  mov     rcx, [rsp+9E0h+var_988]; hKey
0x180004fa7  lea     rax, [rsp+9E0h+Data]
0x180004fac  mov     [rsp+9E0h+samDesired], edi; cbData
0x180004fb0  lea     rdx, aMaxhandlesretu; "MaxHandlesReturnedInEnum"
0x180004fb7  mov     r9d, edi; dwType
0x180004fba  mov     [rsp+9E0h+phkResult], rax; lpData
0x180004fbf  xor     r8d, r8d; Reserved
0x180004fc2  call    cs:__imp_RegSetValueExA
0x180004fc8  mov     esi, eax
0x180004fca  test    eax, eax
0x180004fcc  jnz     loc_1800051A7
0x180004fd2  mov     rcx, [rsp+9E0h+var_988]; hKey
0x180004fd7  call    cs:__imp_RegCloseKey
0x180004fdd  test    cs:byte_18002BD1A, r13b
0x180004fe4  jz      short loc_18000501B
0x180004fe6  lea     rax, aLeavingRtmwrit_2; "Leaving: RtmWriteAddressFamilyConfig"
0x180004fed  mov     [rbp+8E0h+var_960], 4Ah ; 'J'
0x180004ff5  mov     [rsp+9E0h+var_968], rax
0x180004ffa  lea     r9d, [rsi+2]
0x180004ffe  lea     rax, [rsp+9E0h+var_978]
0x180005003  lea     rdx, RRAS_RTM_TRACE_INFO
0x18000500a  mov     [rsp+9E0h+phkResult], rax
0x18000500f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005016  call    McGenEventWrite_EventWriteTransfer
0x18000501b  xor     eax, eax
0x18000501d  jmp     loc_18000529E
0x180005022  test    cs:byte_18002BD1A, r13b
0x180005029  jz      loc_1800051A2
0x18000502f  lea     rdx, aAddressFamilyC_2; "Address Family Config: # handles return"...
0x180005036  mov     word ptr [rbp+8E0h+var_950], r12w
0x18000503b  lea     rcx, [rbp+8E0h+var_950]
0x18000503f  call    FormatRRASErrorString
0x180005044  test    cs:byte_18002BD1A, r13b
0x18000504b  jz      loc_1800051A2
0x180005051  lea     rcx, [rbp+8E0h+var_950]
0x180005055  mov     rax, rbx
0x180005058  inc     rax
0x18000505b  cmp     [rcx+rax*2], r12w
0x180005060  jnz     short loc_180005058
0x180005062  jmp     loc_180005168
0x180005067  test    cs:byte_18002BD1A, r13b
0x18000506e  jz      loc_1800051A2
0x180005074  lea     rdx, aAddressFamilyC_5; "Address Family Config: # nexthops out o"...
0x18000507b  mov     word ptr [rbp+8E0h+var_950], r12w
0x180005080  lea     rcx, [rbp+8E0h+var_950]
0x180005084  call    FormatRRASErrorString
0x180005089  test    cs:byte_18002BD1A, r13b
0x180005090  jz      loc_1800051A2
0x180005096  lea     rcx, [rbp+8E0h+var_950]
0x18000509a  mov     rax, rbx
0x18000509d  inc     rax
0x1800050a0  cmp     [rcx+rax*2], r12w
0x1800050a5  jnz     short loc_18000509D
0x1800050a7  jmp     loc_180005168
0x1800050ac  test    cs:byte_18002BD1A, r13b
0x1800050b3  jz      loc_1800051A2
0x1800050b9  lea     rdx, aAddressFamilyC_9; "Address Family Config: # opaque ptrs ou"...
0x1800050c0  mov     word ptr [rbp+8E0h+var_950], r12w
0x1800050c5  lea     rcx, [rbp+8E0h+var_950]
  ... truncated ...
```
