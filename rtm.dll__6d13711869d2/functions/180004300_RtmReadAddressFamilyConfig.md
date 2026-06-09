# RtmReadAddressFamilyConfig

- ea: `0x180004300`
- end: `0x180004914`
- name: `RtmReadAddressFamilyConfig`
- size: `1556`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009118`

## callees

- `0x180002cb0`
- `0x180004300`
- `0x180005768`
- `0x180007a34`
- `0x180009d14`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18000444a`
- `ADVAPI32!RegOpenKeyExA` at `0x18000444a`
- `ADVAPI32!RegCloseKey` at `0x1800047ac`
- `ADVAPI32!RegCloseKey` at `0x1800048c0`
- `ADVAPI32!RegCloseKey` at `0x1800047ac`
- `ADVAPI32!RegCloseKey` at `0x1800048c0`
- `ADVAPI32!RegQueryValueExA` at `0x180004540`
- `ADVAPI32!RegQueryValueExA` at `0x180004619`
- `ADVAPI32!RegQueryValueExA` at `0x180004682`
- `ADVAPI32!RegQueryValueExA` at `0x1800046d6`
- `ADVAPI32!RegQueryValueExA` at `0x180004730`
- `ADVAPI32!RegQueryValueExA` at `0x180004780`
- `ADVAPI32!RegQueryValueExA` at `0x180004540`
- `ADVAPI32!RegQueryValueExA` at `0x180004619`
- `ADVAPI32!RegQueryValueExA` at `0x180004682`
- `ADVAPI32!RegQueryValueExA` at `0x1800046d6`
- `ADVAPI32!RegQueryValueExA` at `0x180004730`
- `ADVAPI32!RegQueryValueExA` at `0x180004780`

## string_xrefs

- `0x1800043dd`: `Entered: RtmReadAddressFamilyConfig `
- `0x18000446d`: `Address Family Config: Error %d opening address family key`
- `0x1800044dd`: `Leaving: RtmReadAddressFamilyConfig `
- `0x18000456a`: `Address Family Config: Error %d reading address size key. Using default...`
- `0x1800045de`: `Address Family Config: Address Size %d out of bounds`
- `0x180004646`: `Address Family Config: No supported views`
- `0x18000482f`: `Address Family Config: # notifications out of range`
- `0x180004841`: `Address Family Config: # opaque ptrs out of range`
- `0x180004853`: `Address Family Config: # nexthops out of range`
- `0x180004865`: `Address Family Config: # handles returned in enum`
- `0x1800047cd`: `Leaving: RtmReadAddressFamilyConfig`
- `0x1800048e1`: `Leaving: RtmReadAddressFamilyConfig`

## pseudocode

```c
void __fastcall RtmReadAddressFamilyConfig(unsigned __int16 a1, unsigned __int16 a2, unsigned int *a3)
{
  int v3; // esi
  int v6; // eax
  __int64 v7; // rdi
  __int128 *v8; // r9
  unsigned int v9; // eax
  char v10; // cl
  __int128 *v11; // r9
  __int128 *v12; // r9
  unsigned int v13; // eax
  unsigned int v14; // esi
  unsigned int v15; // ecx
  __int128 *v16; // r9
  __int64 v17; // r8
  const wchar_t *v18; // rdx
  LSTATUS v19; // eax
  const wchar_t *v20; // r8
  LSTATUS v21; // eax
  LSTATUS v22; // eax
  LSTATUS v23; // eax
  LSTATUS v24; // eax
  __int128 *v25; // r9
  __int128 *v26; // r9
  __int128 *v27; // r9
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  ULONG uliInst[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v33; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v35; // [rsp+64h] [rbp-9Ch]
  __int128 v36; // [rsp+74h] [rbp-8Ch]
  int v37; // [rsp+84h] [rbp-7Ch]
  int v38; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v39[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v3 = a2;
  hKey = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  *(_QWORD *)uliInst = 0;
  v38 = 0;
  memset_0(v39, 0, sizeof(v39));
  v34 = 0;
  v35 = 0;
  v37 = 0;
  v36 = 0;
  v33 = 0;
  if ( !(_DWORD)qword_18002BD00 && (unsigned int)RtmApiStartup() )
    return;
  GetInstance((LPSPropValue)a1, 0, (ULONG)uliInst);
  if ( v6 )
    return;
  v7 = *(_QWORD *)uliInst;
  if ( (byte_18002BD1A & 8) != 0 )
  {
    LOWORD(v34) = 0;
    v8 = &v33;
    if ( *(_QWORD *)uliInst != -48 )
      LODWORD(v8) = uliInst[0] + 48;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
      (unsigned int)L"Entered: RtmReadAddressFamilyConfig ",
      (_DWORD)v8,
      0,
      (__int64)&v34);
  }
  StringCchPrintfA((STRSAFE_LPSTR)lpSubKey + 66, 0xC2u, "\\Instance %05d\\AddressFamily %05d", 0, v3);
  v9 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  if ( v9 )
  {
    v10 = byte_18002BD1A;
    if ( (byte_18002BD1A & 0x10) != 0 )
    {
      LOWORD(v38) = 0;
      LOWORD(v34) = 0;
      FormatRRASErrorString(&v38, L"Address Family Config: Error %d opening address family key", v9);
      v10 = byte_18002BD1A;
      if ( (byte_18002BD1A & 0x10) != 0 )
      {
        v11 = &v33;
        if ( v7 != -48 )
          LODWORD(v11) = v7 + 48;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RRAS_RTM_PARAM_TRACE_ERROR,
          (unsigned int)&v38,
          (_DWORD)v11,
          0,
          (__int64)&v34);
        v10 = byte_18002BD1A;
      }
    }
    if ( (v10 & 8) != 0 )
    {
      LOWORD(v34) = 0;
      v12 = &v33;
      if ( v7 != -48 )
        LODWORD(v12) = v7 + 48;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
        (unsigned int)L"Leaving: RtmReadAddressFamilyConfig ",
        (_DWORD)v12,
        0,
        (__int64)&v34);
    }
    return;
  }
  cbData = 4;
  v13 = RegQueryValueExA(hKey, "AddressSize", 0, &Type, Data, &cbData);
  v14 = v13;
  if ( v13 || Type != 4 )
  {
    if ( (byte_18002BD1A & 0x10) != 0 )
    {
      LOWORD(v38) = 0;
      LOWORD(v34) = 0;
      FormatRRASErrorString(&v38, L"Address Family Config: Error %d reading address size key. Using default...", v13);
      if ( (byte_18002BD1A & 0x10) != 0 )
      {
        v16 = &v33;
        if ( v7 != -48 )
          LODWORD(v16) = v7 + 48;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RRAS_RTM_PARAM_TRACE_ERROR,
          (unsigned int)&v38,
          (_DWORD)v16,
          0,
          (__int64)&v34);
      }
    }
    v15 = 4;
    *(_DWORD *)Data = 4;
    if ( v14 )
      goto LABEL_31;
  }
  else
  {
    v15 = *(_DWORD *)Data;
  }
  if ( v15 - 1 > 0xF )
  {
    if ( (byte_18002BD1A & 8) == 0 )
      goto LABEL_66;
    v17 = v15;
    v18 = L"Address Family Config: Address Size %d out of bounds";
LABEL_61:
    LOWORD(v38) = 0;
    LOWORD(v34) = 0;
    FormatRRASErrorString(&v38, v18, v17);
    if ( (byte_18002BD1A & 8) != 0 )
    {
      v20 = (const wchar_t *)&v38;
      goto LABEL_63;
    }
    goto LABEL_66;
  }
LABEL_31:
  *a3 = v15;
  cbData = 4;
  v19 = RegQueryValueExA(hKey, "ViewsSupported", 0, &Type, Data, &cbData);
  a3[1] = 3;
  if ( !v19 )
  {
    if ( !*(_DWORD *)Data )
    {
      if ( (byte_18002BD1A & 8) != 0 )
      {
        LOWORD(v34) = 0;
        v20 = L"Address Family Config: No supported views";
LABEL_63:
        v26 = &v33;
        if ( v7 != -48 )
          LODWORD(v26) = v7 + 48;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
          (_DWORD)v20,
          (_DWORD)v26,
          0,
          (__int64)&v34);
      }
LABEL_66:
      RegCloseKey(hKey);
      if ( (byte_18002BD1A & 8) != 0 )
      {
        LOWORD(v34) = 0;
        v27 = &v33;
        if ( v7 != -48 )
          LODWORD(v27) = v7 + 48;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
          (unsigned int)L"Leaving: RtmReadAddressFamilyConfig",
          (_DWORD)v27,
          0,
          (__int64)&v34);
      }
      return;
    }
    a3[1] = *(_DWORD *)Data;
  }
  cbData = 4;
  v21 = RegQueryValueExA(hKey, "MaxChangeNotifyRegistrations", 0, &Type, Data, &cbData);
  a3[5] = 16;
  if ( !v21 )
  {
    v17 = *(unsigned int *)Data;
    if ( (unsigned int)(*(_DWORD *)Data - 1) > 0x1F )
    {
      if ( (byte_18002BD1A & 8) == 0 )
        goto LABEL_66;
      v18 = L"Address Family Config: # notifications out of range";
      goto LABEL_61;
    }
    a3[5] = *(_DWORD *)Data;
  }
  cbData = 4;
  v22 = RegQueryValueExA(hKey, "MaxOpaqueInfoPointers", 0, &Type, Data, &cbData);
  a3[2] = 5;
  if ( !v22 )
  {
    v17 = *(unsigned int *)Data;
    if ( *(_DWORD *)Data > 0xAu )
    {
      if ( (byte_18002BD1A & 8) == 0 )
        goto LABEL_66;
      v18 = L"Address Family Config: # opaque ptrs out of range";
      goto LABEL_61;
    }
    a3[2] = *(_DWORD *)Data;
  }
  cbData = 4;
  v23 = RegQueryValueExA(hKey, "MaxNextHopsInRoute", 0, &Type, Data, &cbData);
  a3[3] = 3;
  if ( !v23 )
  {
    v17 = *(unsigned int *)Data;
    if ( (unsigned int)(*(_DWORD *)Data - 1) > 9 )
    {
      if ( (byte_18002BD1A & 8) == 0 )
        goto LABEL_66;
      v18 = L"Address Family Config: # nexthops out of range";
      goto LABEL_61;
    }
    a3[3] = *(_DWORD *)Data;
  }
  cbData = 4;
  v24 = RegQueryValueExA(hKey, "MaxHandlesReturnedInEnum", 0, &Type, Data, &cbData);
  a3[4] = 25;
  if ( !v24 )
  {
    v17 = *(unsigned int *)Data;
    if ( (unsigned int)(*(_DWORD *)Data - 1) > 0x63 )
    {
      if ( (byte_18002BD1A & 8) == 0 )
        goto LABEL_66;
      v18 = L"Address Family Config: # handles returned in enum";
      goto LABEL_61;
    }
    a3[4] = *(_DWORD *)Data;
  }
  RegCloseKey(hKey);
  if ( (byte_18002BD1A & 8) != 0 )
  {
    LOWORD(v34) = 0;
    v25 = &v33;
    if ( v7 != -48 )
      LODWORD(v25) = v7 + 48;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RRAS_RTM_PARAM_TRACE_INFO,
      (unsigned int)L"Leaving: RtmReadAddressFamilyConfig",
      (_DWORD)v25,
      0,
      (__int64)&v34);
  }
}

```

## disassembly

```asm
0x180004300  mov     [rsp-8+arg_18], rbx
0x180004305  push    rbp
0x180004306  push    rsi
0x180004307  push    rdi
0x180004308  push    r12
0x18000430a  push    r13
0x18000430c  push    r14
0x18000430e  push    r15
0x180004310  lea     rbp, [rsp-7A0h]
0x180004318  sub     rsp, 8A0h
0x18000431f  mov     rax, cs:__security_cookie
0x180004326  xor     rax, rsp
0x180004329  mov     [rbp+7D0h+var_40], rax
0x180004330  xor     r14d, r14d
0x180004333  movzx   esi, dx
0x180004336  mov     rbx, r8
0x180004339  mov     [rsp+8D0h+hKey], r14
0x18000433e  movzx   edi, cx
0x180004341  mov     [rsp+8D0h+cbData], r14d
0x180004346  xor     edx, edx; Val
0x180004348  mov     dword ptr [rsp+8D0h+Data], r14d
0x18000434d  mov     r8d, 7FCh; Size
0x180004353  mov     [rsp+8D0h+Type], r14d
0x180004358  lea     rcx, [rbp+7D0h+var_83C]; void *
0x18000435c  mov     qword ptr [rsp+8D0h+uliInst], r14
0x180004361  mov     [rbp+7D0h+var_840], r14d
0x180004365  call    memset_0
0x18000436a  xorps   xmm0, xmm0
0x18000436d  mov     [rsp+8D0h+var_870], r14d
0x180004372  xor     eax, eax
0x180004374  cmp     dword ptr cs:qword_18002BD00, r14d
0x18000437b  movups  [rsp+8D0h+var_86C], xmm0
0x180004380  mov     [rbp+7D0h+var_84C], eax
0x180004383  movups  [rsp+8D0h+var_85C], xmm0
0x180004388  movups  [rsp+8D0h+var_880], xmm0
0x18000438d  jnz     short loc_18000439C
0x18000438f  call    RtmApiStartup
0x180004394  test    eax, eax
0x180004396  jnz     loc_1800047F8
0x18000439c  lea     r8, [rsp+8D0h+uliInst]; uliInst
0x1800043a1  xor     edx, edx; lpPropSv
0x1800043a3  movzx   ecx, di; lpPropMv
0x1800043a6  call    GetInstance
0x1800043ab  test    eax, eax
0x1800043ad  jnz     loc_1800047F8
0x1800043b3  mov     rdi, qword ptr [rsp+8D0h+uliInst]
0x1800043b8  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800043bf  mov     r15b, 8
0x1800043c2  test    cs:byte_18002BD1A, r15b
0x1800043c9  jz      short loc_180004406
0x1800043cb  lea     rax, [rdi+30h]
0x1800043cf  mov     word ptr [rsp+8D0h+var_870], r14w
0x1800043d5  test    rax, rax
0x1800043d8  lea     r9, [rsp+8D0h+var_880]
0x1800043dd  lea     r8, aEnteredRtmread; "Entered: RtmReadAddressFamilyConfig "
0x1800043e4  mov     rcx, r12
0x1800043e7  cmovnz  r9, rax
0x1800043eb  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x1800043f2  lea     rax, [rsp+8D0h+var_870]
0x1800043f7  mov     [rsp+8D0h+lpcbData], rax
0x1800043fc  mov     [rsp+8D0h+phkResult], r14
0x180004401  call    McTemplateU0zjzz_EventWriteTransfer
0x180004406  mov     rcx, cs:lpSubKey
0x18000440d  lea     r8, pszFormat; "\\Instance %05d\\AddressFamily %05d"
0x180004414  add     rcx, 42h ; 'B'; pszDest
0x180004418  mov     dword ptr [rsp+8D0h+phkResult], esi
0x18000441c  xor     r9d, r9d
0x18000441f  mov     edx, 0C2h; cchDest
0x180004424  call    StringCchPrintfA
0x180004429  mov     rdx, cs:lpSubKey; lpSubKey
0x180004430  lea     rax, [rsp+8D0h+hKey]
0x180004435  mov     r9d, 20019h; samDesired
0x18000443b  mov     [rsp+8D0h+phkResult], rax; phkResult
0x180004440  xor     r8d, r8d; ulOptions
0x180004443  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000444a  call    cs:__imp_RegOpenKeyExA
0x180004450  mov     esi, eax
0x180004452  test    eax, eax
0x180004454  jz      loc_18000450D
0x18000445a  mov     cl, cs:byte_18002BD1A
0x180004460  test    cl, 10h
0x180004463  jz      short loc_1800044C6
0x180004465  mov     r8d, eax
0x180004468  mov     word ptr [rbp+7D0h+var_840], r14w
0x18000446d  lea     rdx, aAddressFamilyC_7; "Address Family Config: Error %d opening"...
0x180004474  mov     word ptr [rsp+8D0h+var_870], r14w
0x18000447a  lea     rcx, [rbp+7D0h+var_840]
0x18000447e  call    FormatRRASErrorString
0x180004483  mov     cl, cs:byte_18002BD1A
0x180004489  test    cl, 10h
0x18000448c  jz      short loc_1800044C6
0x18000448e  lea     rax, [rdi+30h]
0x180004492  mov     rcx, r12
0x180004495  test    rax, rax
0x180004498  lea     r9, [rsp+8D0h+var_880]
0x18000449d  lea     r8, [rbp+7D0h+var_840]
0x1800044a1  cmovnz  r9, rax
0x1800044a5  lea     rdx, RRAS_RTM_PARAM_TRACE_ERROR
0x1800044ac  lea     rax, [rsp+8D0h+var_870]
0x1800044b1  mov     [rsp+8D0h+lpcbData], rax
0x1800044b6  mov     [rsp+8D0h+phkResult], r14
0x1800044bb  call    McTemplateU0zjzz_EventWriteTransfer
0x1800044c0  mov     cl, cs:byte_18002BD1A
0x1800044c6  test    r15b, cl
0x1800044c9  jz      short loc_180004506
0x1800044cb  lea     rax, [rdi+30h]
0x1800044cf  mov     word ptr [rsp+8D0h+var_870], r14w
0x1800044d5  test    rax, rax
0x1800044d8  lea     r9, [rsp+8D0h+var_880]
0x1800044dd  lea     r8, aLeavingRtmread_0; "Leaving: RtmReadAddressFamilyConfig "
0x1800044e4  mov     rcx, r12
0x1800044e7  cmovnz  r9, rax
0x1800044eb  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x1800044f2  lea     rax, [rsp+8D0h+var_870]
0x1800044f7  mov     [rsp+8D0h+lpcbData], rax
0x1800044fc  mov     [rsp+8D0h+phkResult], r14
0x180004501  call    McTemplateU0zjzz_EventWriteTransfer
0x180004506  mov     eax, esi
0x180004508  jmp     loc_1800047F8
0x18000450d  mov     rcx, [rsp+8D0h+hKey]; hKey
0x180004512  lea     rax, [rsp+8D0h+cbData]
0x180004517  mov     [rsp+8D0h+lpcbData], rax; lpcbData
0x18000451c  lea     r9, [rsp+8D0h+Type]; lpType
0x180004521  lea     rax, [rsp+8D0h+Data]
0x180004526  mov     r13d, 4
0x18000452c  xor     r8d, r8d; lpReserved
0x18000452f  mov     [rsp+8D0h+phkResult], rax; lpData
0x180004534  lea     rdx, ValueName; "AddressSize"
0x18000453b  mov     [rsp+8D0h+cbData], r13d
0x180004540  call    cs:__imp_RegQueryValueExA
0x180004546  mov     esi, eax
0x180004548  test    eax, eax
0x18000454a  jnz     short loc_180004559
0x18000454c  cmp     [rsp+8D0h+Type], r13d
0x180004551  jnz     short loc_180004559
0x180004553  mov     ecx, dword ptr [rsp+8D0h+Data]
0x180004557  jmp     short loc_1800045C6
0x180004559  test    cs:byte_18002BD1A, 10h
0x180004560  jz      short loc_1800045BB
0x180004562  mov     r8d, esi
0x180004565  mov     word ptr [rbp+7D0h+var_840], r14w
0x18000456a  lea     rdx, aAddressFamilyC_1; "Address Family Config: Error %d reading"...
0x180004571  mov     word ptr [rsp+8D0h+var_870], r14w
0x180004577  lea     rcx, [rbp+7D0h+var_840]
0x18000457b  call    FormatRRASErrorString
0x180004580  test    cs:byte_18002BD1A, 10h
0x180004587  jz      short loc_1800045BB
0x180004589  lea     rax, [rdi+30h]
0x18000458d  mov     rcx, r12
0x180004590  test    rax, rax
0x180004593  lea     r9, [rsp+8D0h+var_880]
0x180004598  lea     r8, [rbp+7D0h+var_840]
0x18000459c  cmovnz  r9, rax
0x1800045a0  lea     rdx, RRAS_RTM_PARAM_TRACE_ERROR
0x1800045a7  lea     rax, [rsp+8D0h+var_870]
0x1800045ac  mov     [rsp+8D0h+lpcbData], rax
0x1800045b1  mov     [rsp+8D0h+phkResult], r14
0x1800045b6  call    McTemplateU0zjzz_EventWriteTransfer
0x1800045bb  mov     ecx, r13d
0x1800045be  mov     dword ptr [rsp+8D0h+Data], ecx
0x1800045c2  test    esi, esi
0x1800045c4  jnz     short loc_1800045EA
0x1800045c6  lea     eax, [rcx-1]
0x1800045c9  cmp     eax, 0Fh
0x1800045cc  jbe     short loc_1800045EA
0x1800045ce  test    cs:byte_18002BD1A, r15b
0x1800045d5  jz      loc_1800048BB
0x1800045db  mov     r8d, ecx
0x1800045de  lea     rdx, aAddressFamilyC_3; "Address Family Config: Address Size %d "...
0x1800045e5  jmp     loc_18000486C
0x1800045ea  lea     rax, [rsp+8D0h+cbData]
0x1800045ef  mov     [rbx], ecx
0x1800045f1  mov     rcx, [rsp+8D0h+hKey]; hKey
0x1800045f6  lea     r9, [rsp+8D0h+Type]; lpType
0x1800045fb  mov     [rsp+8D0h+lpcbData], rax; lpcbData
0x180004600  lea     rdx, aViewssupported; "ViewsSupported"
0x180004607  lea     rax, [rsp+8D0h+Data]
0x18000460c  mov     [rsp+8D0h+cbData], r13d
0x180004611  xor     r8d, r8d; lpReserved
0x180004614  mov     [rsp+8D0h+phkResult], rax; lpData
0x180004619  call    cs:__imp_RegQueryValueExA
0x18000461f  mov     esi, 3
0x180004624  mov     [rbx+4], esi
0x180004627  test    eax, eax
0x180004629  jnz     short loc_180004655
0x18000462b  mov     eax, dword ptr [rsp+8D0h+Data]
0x18000462f  test    eax, eax
0x180004631  jnz     short loc_180004652
0x180004633  test    cs:byte_18002BD1A, r15b
0x18000463a  jz      loc_1800048BB
0x180004640  mov     word ptr [rsp+8D0h+var_870], r14w
0x180004646  lea     r8, aAddressFamilyC_0; "Address Family Config: No supported vie"...
0x18000464d  jmp     loc_18000488D
0x180004652  mov     [rbx+4], eax
0x180004655  mov     rcx, [rsp+8D0h+hKey]; hKey
0x18000465a  lea     rax, [rsp+8D0h+cbData]
0x18000465f  mov     [rsp+8D0h+lpcbData], rax; lpcbData
0x180004664  lea     r9, [rsp+8D0h+Type]; lpType
0x180004669  lea     rax, [rsp+8D0h+Data]
0x18000466e  mov     [rsp+8D0h+cbData], r13d
0x180004673  xor     r8d, r8d; lpReserved
0x180004676  mov     [rsp+8D0h+phkResult], rax; lpData
0x18000467b  lea     rdx, aMaxchangenotif; "MaxChangeNotifyRegistrations"
0x180004682  call    cs:__imp_RegQueryValueExA
0x180004688  mov     dword ptr [rbx+14h], 10h
0x18000468f  test    eax, eax
0x180004691  jnz     short loc_1800046A9
0x180004693  mov     r8d, dword ptr [rsp+8D0h+Data]
0x180004698  lea     eax, [r8-1]
0x18000469c  cmp     eax, 1Fh
0x18000469f  ja      loc_180004822
0x1800046a5  mov     [rbx+14h], r8d
0x1800046a9  mov     rcx, [rsp+8D0h+hKey]; hKey
0x1800046ae  lea     rax, [rsp+8D0h+cbData]
0x1800046b3  mov     [rsp+8D0h+lpcbData], rax; lpcbData
0x1800046b8  lea     r9, [rsp+8D0h+Type]; lpType
0x1800046bd  lea     rax, [rsp+8D0h+Data]
0x1800046c2  mov     [rsp+8D0h+cbData], r13d
0x1800046c7  xor     r8d, r8d; lpReserved
0x1800046ca  mov     [rsp+8D0h+phkResult], rax; lpData
0x1800046cf  lea     rdx, aMaxopaqueinfop; "MaxOpaqueInfoPointers"
0x1800046d6  call    cs:__imp_RegQueryValueExA
0x1800046dc  mov     dword ptr [rbx+8], 5
0x1800046e3  test    eax, eax
0x1800046e5  jnz     short loc_180004703
0x1800046e7  mov     r8d, dword ptr [rsp+8D0h+Data]
0x1800046ec  test    r8d, r8d
0x1800046ef  js      loc_180004838
0x1800046f5  cmp     r8d, 0Ah
0x1800046f9  ja      loc_180004838
0x1800046ff  mov     [rbx+8], r8d
0x180004703  mov     rcx, [rsp+8D0h+hKey]; hKey
0x180004708  lea     rax, [rsp+8D0h+cbData]
0x18000470d  mov     [rsp+8D0h+lpcbData], rax; lpcbData
0x180004712  lea     r9, [rsp+8D0h+Type]; lpType
0x180004717  lea     rax, [rsp+8D0h+Data]
0x18000471c  mov     [rsp+8D0h+cbData], r13d
0x180004721  xor     r8d, r8d; lpReserved
0x180004724  mov     [rsp+8D0h+phkResult], rax; lpData
0x180004729  lea     rdx, aMaxnexthopsinr; "MaxNextHopsInRoute"
0x180004730  call    cs:__imp_RegQueryValueExA
0x180004736  mov     [rbx+0Ch], esi
0x180004739  test    eax, eax
0x18000473b  jnz     short loc_180004753
0x18000473d  mov     r8d, dword ptr [rsp+8D0h+Data]
0x180004742  lea     eax, [r8-1]
0x180004746  cmp     eax, 9
0x180004749  ja      loc_18000484A
0x18000474f  mov     [rbx+0Ch], r8d
0x180004753  mov     rcx, [rsp+8D0h+hKey]; hKey
0x180004758  lea     rax, [rsp+8D0h+cbData]
0x18000475d  mov     [rsp+8D0h+lpcbData], rax; lpcbData
0x180004762  lea     r9, [rsp+8D0h+Type]; lpType
0x180004767  lea     rax, [rsp+8D0h+Data]
0x18000476c  mov     [rsp+8D0h+cbData], r13d
0x180004771  xor     r8d, r8d; lpReserved
0x180004774  mov     [rsp+8D0h+phkResult], rax; lpData
0x180004779  lea     rdx, aMaxhandlesretu; "MaxHandlesReturnedInEnum"
0x180004780  call    cs:__imp_RegQueryValueExA
0x180004786  mov     dword ptr [rbx+10h], 19h
0x18000478d  test    eax, eax
0x18000478f  jnz     short loc_1800047A7
0x180004791  mov     r8d, dword ptr [rsp+8D0h+Data]
0x180004796  lea     eax, [r8-1]
0x18000479a  cmp     eax, 63h ; 'c'
0x18000479d  ja      loc_18000485C
0x1800047a3  mov     [rbx+10h], r8d
0x1800047a7  mov     rcx, [rsp+8D0h+hKey]; hKey
0x1800047ac  call    cs:__imp_RegCloseKey
0x1800047b2  test    cs:byte_18002BD1A, r15b
0x1800047b9  jz      short loc_1800047F6
0x1800047bb  lea     rax, [rdi+30h]
0x1800047bf  mov     word ptr [rsp+8D0h+var_870], r14w
0x1800047c5  test    rax, rax
0x1800047c8  lea     r9, [rsp+8D0h+var_880]
0x1800047cd  lea     r8, aLeavingRtmread_1; "Leaving: RtmReadAddressFamilyConfig"
0x1800047d4  mov     rcx, r12
0x1800047d7  cmovnz  r9, rax
0x1800047db  lea     rdx, RRAS_RTM_PARAM_TRACE_INFO
0x1800047e2  lea     rax, [rsp+8D0h+var_870]
0x1800047e7  mov     [rsp+8D0h+lpcbData], rax
0x1800047ec  mov     [rsp+8D0h+phkResult], r14
0x1800047f1  call    McTemplateU0zjzz_EventWriteTransfer
0x1800047f6  xor     eax, eax
0x1800047f8  mov     rcx, [rbp+7D0h+var_40]
0x1800047ff  xor     rcx, rsp; StackCookie
0x180004802  call    __security_check_cookie
0x180004807  mov     rbx, [rsp+8D0h+arg_18]
0x18000480f  add     rsp, 8A0h
0x180004816  pop     r15
0x180004818  pop     r14
0x18000481a  pop     r13
0x18000481c  pop     r12
0x18000481e  pop     rdi
0x18000481f  pop     rsi
0x180004820  pop     rbp
0x180004821  retn
0x180004822  test    cs:byte_18002BD1A, r15b
0x180004829  jz      loc_1800048BB
0x18000482f  lea     rdx, aAddressFamilyC_4; "Address Family Config: # notifications "...
  ... truncated ...
```
