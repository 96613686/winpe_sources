# CWnpConnector::StartTlsAuthenticate(void)

- ea: `0x18005cef8`
- end: `0x18005d50f`
- name: `?StartTlsAuthenticate@CWnpConnector@@AEAAJXZ`
- size: `1559`
- prototype: `__int64 __fastcall(CWnpConnector *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005a938`

## callees

- `0x180007440`
- `0x180008294`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x18002f27c`
- `0x18002f2d8`
- `0x18002f808`
- `0x18002fc80`
- `0x18004f050`
- `0x18004ff8c`
- `0x180051298`
- `0x180056ce0`
- `0x180059018`
- `0x1800591bc`
- `0x180059d24`
- `0x18005c2d0`
- `0x18005cef8`
- `0x18005ff78`
- `0x1800852d4`
- `0x180096010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005d301`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005d301`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d0ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d0ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18005d003`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18005d003`

## string_xrefs

- `0x18005d203`: `Microsoft Unified Security Protocol Provider`

## pseudocode

```c
__int64 __fastcall CWnpConnector::StartTlsAuthenticate(CWnpConnector *this)
{
  PVOID v2; // rcx
  int v3; // ebx
  __int64 v4; // rcx
  unsigned int v5; // eax
  __int64 v6; // r9
  PVOID *v7; // rcx
  _QWORD *v8; // rsi
  int v9; // eax
  INITIALIZE_SECURITY_CONTEXT_FN_W InitializeSecurityContextW; // rbx
  _QWORD *v11; // rax
  void *v12; // rcx
  int v13; // eax
  int v14; // ecx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  __int64 v18; // [rsp+28h] [rbp-D8h]
  char *v19; // [rsp+38h] [rbp-C8h]
  bool v20[4]; // [rsp+70h] [rbp-90h] BYREF
  int v21; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v22; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v23; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  size_t Size; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 *Src; // [rsp+98h] [rbp-68h]
  __int128 v28; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v29[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v30[28]; // [rsp+B4h] [rbp-4Ch] BYREF
  _DWORD v31[18]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v32; // [rsp+118h] [rbp+18h]
  void *Block; // [rsp+120h] [rbp+20h] BYREF
  char v34; // [rsp+128h] [rbp+28h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_dddc(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      151,
      *((unsigned int *)this + 27),
      *((unsigned int *)this + 16),
      *((_DWORD *)this + 27),
      *((_DWORD *)this + 22),
      (*((_DWORD *)this + 27) & 8) != 0);
  }
  v3 = 0;
  v21 = 0;
  if ( *((_QWORD *)this + 10) == -1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
  CWnpConnector::ChangeConnectorState(this, 6);
  if ( (byte_1800AFD83 & 0x20) != 0 )
    McTemplateU0q_EventWriteTransfer(v4, WPNPRV_TRANS_TLS_NEGOTIATION_START, (*((_BYTE *)this + 108) & 8) != 0);
  CWnpConnector::LogTlsNegotiationStart(this);
  memset_0(v31, 0, 0x50u);
  v31[0] = 4;
  v31[14] = 10880;
  v32 = 2097200;
  hKey = 0;
  v5 = RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "Software\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
         0,
         1u,
         &hKey);
  if ( !v5 )
  {
    v22 = 0;
    v23 = 0;
    if ( (int)WpnRegLoadDWord(hKey, L"DisableTLSCertCheck", &v22) >= 0 && v22 )
    {
      v32 = v32 & 0xFFFFFFD7 | 8;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids);
    }
    if ( (int)WpnRegLoadDWord(hKey, L"DisableSendAuxRecord", &v23) >= 0 && v23 )
    {
      v32 &= ~0x200000u;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids);
    }
    RegCloseKey(hKey);
    goto LABEL_29;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids, v5);
LABEL_29:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)this + 54)
    || (v8 = (_QWORD *)((char *)this + 320), *((_QWORD *)this + 40) == -1)
    || *((_QWORD *)this + 41) == -1 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 5u )
    {
      LOBYTE(v6) = (*((_BYTE *)this + 108) & 8) != 0;
      WPP_SF_c(v7[2], 155, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids, v6);
    }
    v24 = 0;
    v8 = (_QWORD *)((char *)this + 320);
    if ( *((_QWORD *)this + 40) != -1 && *((_QWORD *)this + 41) != -1 )
    {
      ((void (__fastcall *)(char *))CWnpConnector::s_pSSPI->FreeCredentialsHandle)((char *)this + 320);
      *((_QWORD *)this + 41) = -1;
      *v8 = -1;
    }
    v19 = (char *)this + 320;
    HIDWORD(v18) = 0;
    phkResult = (PHKEY)v31;
    v9 = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, __int64))CWnpConnector::s_pSSPI->AcquireCredentialsHandleW)(
           0,
           L"Microsoft Unified Security Protocol Provider",
           2);
    v3 = v9;
    v21 = v9;
    if ( v9 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        156,
        &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
        (unsigned int)v9);
    }
  }
  else if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 5u )
  {
    LOBYTE(v6) = (*((_BYTE *)this + 108) & 8) != 0;
    WPP_SF_c(v7[2], 157, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids, v6);
  }
  v28 = 0;
  if ( v3 >= 0 )
  {
    *((_DWORD *)this + 88) = 49436;
    Size = 0x200000000LL;
    Src = 0;
    DWORD1(v28) = 1;
    *((_QWORD *)&v28 + 1) = &Size;
    InitializeSecurityContextW = CWnpConnector::s_pSSPI->InitializeSecurityContextW;
    v11 = (_QWORD *)ATL::CA2WEX<128>::CA2WEX<128>(&Block, *((_QWORD *)this + 12));
    LODWORD(v19) = 0;
    LODWORD(v18) = 0;
    LODWORD(phkResult) = 0;
    v3 = ((__int64 (__fastcall *)(_QWORD *, _QWORD, _QWORD, __int64, PHKEY, __int64, _QWORD, char *, char *, __int128 *, char *, _QWORD))InitializeSecurityContextW)(
           v8,
           0,
           *v11,
           49436,
           phkResult,
           v18,
           0,
           v19,
           (char *)this + 336,
           &v28,
           (char *)this + 356,
           0);
    v21 = v3;
    v12 = Block;
    if ( Block != &v34 )
      free(Block);
    if ( (byte_1800AFD84 & 1) != 0 )
      McTemplateU0qq_EventWriteTransfer(
        v12,
        WPNPRV_TRANS_INITIALIZE_SECURITY_CONTEXT,
        (*((_BYTE *)this + 108) & 8) != 0,
        (unsigned int)v3);
    if ( v3 >= 0 )
    {
      if ( v3 == 590610 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids);
        }
        if ( (_DWORD)Size && Src )
        {
          v13 = CWnpConnector::SendSocket(this, Src, (unsigned int)Size);
          v3 = v13;
          v21 = v13;
          if ( v13 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              160,
              &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
              (unsigned int)v13);
          }
          ((void (__fastcall *)(unsigned __int8 *))CWnpConnector::s_pSSPI->FreeContextBuffer)(Src);
          Src = 0;
          LODWORD(Size) = 0;
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        158,
        &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
        (unsigned int)v3);
    }
  }
  CWnpConnector::GetPrecommandRetryProperties(this, v29);
  v23 = *((_DWORD *)this + 132);
  v20[0] = *((_QWORD *)this + 10) == -1;
  v14 = *((_DWORD *)this + 27);
  v22 = (v14 & 8) != 0;
  LODWORD(v24) = v14;
  WpnconTelemetry::StartTlsAuthenticate<int &,unsigned long,enum CWnpConnector::WnpConnectorStates &,int,bool,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0008,int &,_GUID &,long &>(
    (_DWORD)this + 64,
    (unsigned int)&v24,
    (_DWORD)this + 88,
    (unsigned int)&v22,
    (__int64)v20,
    (__int64)&v23,
    (__int64)v29,
    (__int64)v30,
    (__int64)&v21);
  if ( v3 < 0 )
  {
    CWnpConnector::OnError(this, (unsigned int)v3);
    CWnpConnector::LogTlsNegotiationEnd(this, v3);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(phkResulta) = (*((_BYTE *)this + 108) & 8) != 0;
    WPP_SF_dcd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      161,
      &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
      *((unsigned int *)this + 16),
      phkResulta,
      v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18005cef8  push    rbp
0x18005cefa  push    rbx
0x18005cefb  push    rsi
0x18005cefc  push    rdi
0x18005cefd  push    r13
0x18005ceff  push    r15
0x18005cf01  lea     rbp, [rsp-148h]
0x18005cf09  sub     rsp, 248h
0x18005cf10  mov     rax, cs:__security_cookie
0x18005cf17  xor     rax, rsp
0x18005cf1a  mov     [rbp+170h+var_40], rax
0x18005cf21  mov     rdi, rcx
0x18005cf24  lea     r13, WPP_GLOBAL_Control
0x18005cf2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cf32  cmp     rcx, r13
0x18005cf35  jz      short loc_18005CF70
0x18005cf37  test    byte ptr [rcx+1Ch], 4
0x18005cf3b  jz      short loc_18005CF70
0x18005cf3d  cmp     byte ptr [rcx+19h], 6
0x18005cf41  jb      short loc_18005CF70
0x18005cf43  mov     r8d, [rdi+6Ch]
0x18005cf47  test    r8b, 8
0x18005cf4b  setnbe  al
0x18005cf4e  mov     edx, 97h
0x18005cf53  mov     byte ptr [rsp+270h+var_240], al
0x18005cf57  mov     eax, [rdi+58h]
0x18005cf5a  mov     dword ptr [rsp+270h+var_248], eax
0x18005cf5e  mov     dword ptr [rsp+270h+phkResult], r8d
0x18005cf63  mov     r9d, [rdi+40h]
0x18005cf67  mov     rcx, [rcx+10h]
0x18005cf6b  call    WPP_SF_dddc
0x18005cf70  xor     r15d, r15d
0x18005cf73  mov     ebx, r15d
0x18005cf76  mov     [rsp+270h+var_1FC], ebx
0x18005cf7a  cmp     qword ptr [rdi+50h], 0FFFFFFFFFFFFFFFFh
0x18005cf7f  jnz     short loc_18005CF86
0x18005cf81  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005cf86  mov     edx, 6
0x18005cf8b  mov     rcx, rdi
0x18005cf8e  call    ?ChangeConnectorState@CWnpConnector@@AEAAXW4WnpConnectorStates@1@@Z; CWnpConnector::ChangeConnectorState(CWnpConnector::WnpConnectorStates)
0x18005cf93  test    cs:byte_1800AFD83, 20h
0x18005cf9a  jz      short loc_18005CFB3
0x18005cf9c  test    byte ptr [rdi+6Ch], 8
0x18005cfa0  mov     r8d, r15d
0x18005cfa3  setnbe  r8b
0x18005cfa7  lea     rdx, WPNPRV_TRANS_TLS_NEGOTIATION_START
0x18005cfae  call    McTemplateU0q_EventWriteTransfer
0x18005cfb3  mov     rcx, rdi; this
0x18005cfb6  call    ?LogTlsNegotiationStart@CWnpConnector@@AEAAXXZ; CWnpConnector::LogTlsNegotiationStart(void)
0x18005cfbb  xor     edx, edx; Val
0x18005cfbd  lea     r8d, [rdx+50h]; Size
0x18005cfc1  lea     rcx, [rbp+170h+var_1A0]; void *
0x18005cfc5  call    memset_0
0x18005cfca  mov     [rbp+170h+var_1A0], 4
0x18005cfd1  mov     [rbp+170h+var_168], 2A80h
0x18005cfd8  mov     [rbp+170h+var_158], 200030h
0x18005cfdf  mov     [rbp+170h+hKey], r15
0x18005cfe3  lea     rax, [rbp+170h+hKey]
0x18005cfe7  mov     [rsp+270h+phkResult], rax; phkResult
0x18005cfec  mov     r9d, 1; samDesired
0x18005cff2  xor     r8d, r8d; ulOptions
0x18005cff5  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005cffc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005d003  call    cs:__imp_RegOpenKeyExA
0x18005d009  test    eax, eax
0x18005d00b  jnz     loc_18005D0D6
0x18005d011  mov     [rsp+270h+var_1F8], r15d
0x18005d016  mov     [rsp+270h+var_1F4], r15d
0x18005d01b  lea     r8, [rsp+270h+var_1F8]; unsigned int *
0x18005d020  lea     rdx, aDisabletlscert; "DisableTLSCertCheck"
0x18005d027  mov     rcx, [rbp+170h+hKey]; hKey
0x18005d02b  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18005d030  test    eax, eax
0x18005d032  js      short loc_18005D049
0x18005d034  cmp     [rsp+270h+var_1F8], r15d
0x18005d039  jz      short loc_18005D049
0x18005d03b  mov     eax, [rbp+170h+var_158]
0x18005d03e  and     eax, 0FFFFFFDFh
0x18005d041  or      eax, 8
0x18005d044  mov     [rbp+170h+var_158], eax
0x18005d047  jmp     short loc_18005D076
0x18005d049  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d050  cmp     rcx, r13
0x18005d053  jz      short loc_18005D076
0x18005d055  test    byte ptr [rcx+1Ch], 4
0x18005d059  jz      short loc_18005D076
0x18005d05b  cmp     byte ptr [rcx+19h], 3
0x18005d05f  jb      short loc_18005D076
0x18005d061  mov     edx, 98h
0x18005d066  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005d06d  mov     rcx, [rcx+10h]
0x18005d071  call    WPP_SF_
0x18005d076  lea     r8, [rsp+270h+var_1F4]; unsigned int *
0x18005d07b  lea     rdx, aDisablesendaux; "DisableSendAuxRecord"
0x18005d082  mov     rcx, [rbp+170h+hKey]; hKey
0x18005d086  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18005d08b  test    eax, eax
0x18005d08d  js      short loc_18005D09D
0x18005d08f  cmp     [rsp+270h+var_1F4], r15d
0x18005d094  jz      short loc_18005D09D
0x18005d096  btr     [rbp+170h+var_158], 15h
0x18005d09b  jmp     short loc_18005D0CA
0x18005d09d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d0a4  cmp     rcx, r13
0x18005d0a7  jz      short loc_18005D0CA
0x18005d0a9  test    byte ptr [rcx+1Ch], 4
0x18005d0ad  jz      short loc_18005D0CA
0x18005d0af  cmp     byte ptr [rcx+19h], 3
0x18005d0b3  jb      short loc_18005D0CA
0x18005d0b5  mov     edx, 99h
0x18005d0ba  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005d0c1  mov     rcx, [rcx+10h]
0x18005d0c5  call    WPP_SF_
0x18005d0ca  mov     rcx, [rbp+170h+hKey]; hKey
0x18005d0ce  call    cs:__imp_RegCloseKey
0x18005d0d4  jmp     short loc_18005D106
0x18005d0d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d0dd  cmp     rcx, r13
0x18005d0e0  jz      short loc_18005D10D
0x18005d0e2  test    byte ptr [rcx+1Ch], 4
0x18005d0e6  jz      short loc_18005D10D
0x18005d0e8  cmp     byte ptr [rcx+19h], 3
0x18005d0ec  jb      short loc_18005D10D
0x18005d0ee  mov     edx, 9Ah
0x18005d0f3  mov     r9d, eax
0x18005d0f6  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005d0fd  mov     rcx, [rcx+10h]
0x18005d101  call    WPP_SF_d
0x18005d106  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d10d  cmp     [rdi+0D8h], r15d
0x18005d114  jz      short loc_18005D16C
0x18005d116  lea     rsi, [rdi+140h]
0x18005d11d  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18005d121  jz      short loc_18005D16C
0x18005d123  cmp     qword ptr [rdi+148h], 0FFFFFFFFFFFFFFFFh
0x18005d12b  jz      short loc_18005D16C
0x18005d12d  cmp     rcx, r13
0x18005d130  jz      loc_18005D24F
0x18005d136  test    byte ptr [rcx+1Ch], 4
0x18005d13a  jz      loc_18005D24F
0x18005d140  cmp     byte ptr [rcx+19h], 5
0x18005d144  jb      loc_18005D24F
0x18005d14a  test    byte ptr [rdi+6Ch], 8
0x18005d14e  setnbe  r9b
0x18005d152  mov     edx, 9Dh
0x18005d157  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005d15e  mov     rcx, [rcx+10h]
0x18005d162  call    WPP_SF_c
0x18005d167  jmp     loc_18005D24F
0x18005d16c  cmp     rcx, r13
0x18005d16f  jz      short loc_18005D19A
0x18005d171  test    byte ptr [rcx+1Ch], 4
0x18005d175  jz      short loc_18005D19A
0x18005d177  cmp     byte ptr [rcx+19h], 5
0x18005d17b  jb      short loc_18005D19A
0x18005d17d  test    byte ptr [rdi+6Ch], 8
0x18005d181  setnbe  r9b
0x18005d185  mov     edx, 9Bh
0x18005d18a  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005d191  mov     rcx, [rcx+10h]
0x18005d195  call    WPP_SF_c
0x18005d19a  mov     [rbp+170h+var_1F0], r15
0x18005d19e  lea     rsi, [rdi+140h]
0x18005d1a5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005d1a9  cmp     [rsi], rbx
0x18005d1ac  jz      short loc_18005D1D4
0x18005d1ae  cmp     [rdi+148h], rbx
0x18005d1b5  jz      short loc_18005D1D4
0x18005d1b7  mov     rax, cs:?s_pSSPI@CWnpConnector@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * CWnpConnector::s_pSSPI
0x18005d1be  mov     rcx, rsi
0x18005d1c1  mov     rax, [rax+20h]
0x18005d1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d1ca  mov     [rdi+148h], rbx
0x18005d1d1  mov     [rsi], rbx
0x18005d1d4  mov     rax, cs:?s_pSSPI@CWnpConnector@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * CWnpConnector::s_pSSPI
0x18005d1db  lea     rcx, [rbp+170h+var_1F0]
0x18005d1df  mov     [rsp+270h+var_230], rcx
0x18005d1e4  mov     [rsp+270h+var_238], rsi
0x18005d1e9  mov     [rsp+270h+var_240], r15
0x18005d1ee  mov     [rsp+270h+var_248], r15
0x18005d1f3  lea     rcx, [rbp+170h+var_1A0]
0x18005d1f7  mov     [rsp+270h+phkResult], rcx
0x18005d1fc  xor     r9d, r9d
0x18005d1ff  lea     r8d, [r9+2]
0x18005d203  lea     rdx, aMicrosoftUnifi; "Microsoft Unified Security Protocol Pro"...
0x18005d20a  xor     ecx, ecx
0x18005d20c  mov     rax, [rax+18h]
0x18005d210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d215  mov     ebx, eax
0x18005d217  mov     [rsp+270h+var_1FC], eax
0x18005d21b  test    eax, eax
0x18005d21d  jns     short loc_18005D24F
0x18005d21f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d226  cmp     rcx, r13
0x18005d229  jz      short loc_18005D24F
0x18005d22b  test    byte ptr [rcx+1Ch], 4
0x18005d22f  jz      short loc_18005D24F
0x18005d231  cmp     byte ptr [rcx+19h], 2
0x18005d235  jb      short loc_18005D24F
0x18005d237  mov     edx, 9Ch
0x18005d23c  mov     r9d, eax
0x18005d23f  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005d246  mov     rcx, [rcx+10h]
0x18005d24a  call    WPP_SF_d
0x18005d24f  xorps   xmm0, xmm0
0x18005d252  movups  [rbp+170h+var_1D0], xmm0
0x18005d256  test    ebx, ebx
0x18005d258  js      loc_18005D41B
0x18005d25e  mov     dword ptr [rdi+160h], 0C11Ch
0x18005d268  mov     dword ptr [rbp+170h+Size], r15d
0x18005d26c  mov     dword ptr [rbp+170h+Size+4], 2
0x18005d273  mov     [rbp+170h+Src], r15
0x18005d277  mov     dword ptr [rbp+170h+var_1D0+4], 1
0x18005d27e  lea     rax, [rbp+170h+Size]
0x18005d282  mov     qword ptr [rbp+170h+var_1D0+8], rax
0x18005d286  mov     rax, cs:?s_pSSPI@CWnpConnector@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * CWnpConnector::s_pSSPI
0x18005d28d  mov     rbx, [rax+30h]
0x18005d291  mov     rdx, [rdi+60h]
0x18005d295  lea     rcx, [rbp+170h+Block]
0x18005d299  call    ??0?$CA2WEX@$0IA@@ATL@@QEAA@PEBD@Z; ATL::CA2WEX<128>::CA2WEX<128>(char const *)
0x18005d29e  mov     r8, [rax]
0x18005d2a1  lea     rax, [rdi+164h]
0x18005d2a8  lea     rdx, [rdi+150h]
0x18005d2af  mov     [rsp+270h+var_218], r15
0x18005d2b4  mov     [rsp+270h+var_220], rax
0x18005d2b9  lea     rax, [rbp+170h+var_1D0]
0x18005d2bd  mov     [rsp+270h+var_228], rax
0x18005d2c2  mov     [rsp+270h+var_230], rdx
0x18005d2c7  mov     dword ptr [rsp+270h+var_238], r15d
0x18005d2cc  mov     [rsp+270h+var_240], r15
0x18005d2d1  mov     dword ptr [rsp+270h+var_248], r15d
0x18005d2d6  mov     dword ptr [rsp+270h+phkResult], r15d
0x18005d2db  xor     edx, edx
0x18005d2dd  mov     r9d, 0C11Ch
0x18005d2e3  mov     rcx, rsi
0x18005d2e6  mov     rax, rbx
0x18005d2e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d2ee  mov     ebx, eax
0x18005d2f0  mov     [rsp+270h+var_1FC], eax
0x18005d2f4  mov     rcx, [rbp+170h+Block]; Block
0x18005d2f8  lea     rax, [rbp+170h+var_148]
0x18005d2fc  cmp     rcx, rax
0x18005d2ff  jz      short loc_18005D307
0x18005d301  call    cs:__imp_free
0x18005d307  test    cs:byte_1800AFD84, 1
0x18005d30e  jz      short loc_18005D32A
0x18005d310  test    byte ptr [rdi+6Ch], 8
0x18005d314  mov     r8d, r15d
0x18005d317  setnbe  r8b
0x18005d31b  mov     r9d, ebx
0x18005d31e  lea     rdx, WPNPRV_TRANS_INITIALIZE_SECURITY_CONTEXT
0x18005d325  call    McTemplateU0qq_EventWriteTransfer
0x18005d32a  test    ebx, ebx
0x18005d32c  jns     short loc_18005D36F
0x18005d32e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d335  cmp     rcx, r13
0x18005d338  jz      loc_18005D41B
0x18005d33e  test    byte ptr [rcx+1Ch], 4
0x18005d342  jz      loc_18005D41B
0x18005d348  cmp     byte ptr [rcx+19h], 2
0x18005d34c  jb      loc_18005D41B
0x18005d352  mov     edx, 9Eh
0x18005d357  mov     r9d, ebx
0x18005d35a  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005d361  mov     rcx, [rcx+10h]
0x18005d365  call    WPP_SF_d
0x18005d36a  jmp     loc_18005D41B
0x18005d36f  cmp     ebx, 90312h
0x18005d375  jnz     loc_18005D41B
0x18005d37b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d382  cmp     rcx, r13
0x18005d385  jz      short loc_18005D3A8
0x18005d387  test    byte ptr [rcx+1Ch], 4
0x18005d38b  jz      short loc_18005D3A8
0x18005d38d  cmp     byte ptr [rcx+19h], 5
0x18005d391  jb      short loc_18005D3A8
0x18005d393  mov     edx, 9Fh
0x18005d398  lea     r8, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x18005d39f  mov     rcx, [rcx+10h]
0x18005d3a3  call    WPP_SF_
0x18005d3a8  mov     r8d, dword ptr [rbp+170h+Size]; Size
0x18005d3ac  test    r8d, r8d
0x18005d3af  jz      short loc_18005D41B
0x18005d3b1  mov     rdx, [rbp+170h+Src]; Src
0x18005d3b5  test    rdx, rdx
0x18005d3b8  jz      short loc_18005D41B
0x18005d3ba  mov     rcx, rdi; this
0x18005d3bd  call    ?SendSocket@CWnpConnector@@AEAAJPEBEK@Z; CWnpConnector::SendSocket(uchar const *,ulong)
0x18005d3c2  mov     ebx, eax
0x18005d3c4  mov     [rsp+270h+var_1FC], eax
0x18005d3c8  test    eax, eax
0x18005d3ca  jns     short loc_18005D3FC
0x18005d3cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d3d3  cmp     rcx, r13
0x18005d3d6  jz      short loc_18005D3FC
0x18005d3d8  test    byte ptr [rcx+1Ch], 4
0x18005d3dc  jz      short loc_18005D3FC
0x18005d3de  cmp     byte ptr [rcx+19h], 2
0x18005d3e2  jb      short loc_18005D3FC
0x18005d3e4  mov     edx, 0A0h
  ... truncated ...
```
