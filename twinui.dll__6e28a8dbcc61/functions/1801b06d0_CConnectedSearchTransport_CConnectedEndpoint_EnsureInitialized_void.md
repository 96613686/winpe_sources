# CConnectedSearchTransport::CConnectedEndpoint::_EnsureInitialized(void)

- ea: `0x1801b06d0`
- end: `0x1801b0a64`
- name: `?_EnsureInitialized@CConnectedEndpoint@CConnectedSearchTransport@@AEAAJXZ`
- size: `916`
- prototype: `__int64 __fastcall(CConnectedSearchTransport::CConnectedEndpoint *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801b016c`
- `0x1801b0b8c`

## callees

- `0x180027ee4`
- `0x180036250`
- `0x180038274`
- `0x180047224`
- `0x180073390`
- `0x180074b74`
- `0x180151970`
- `0x1801a8cd4`
- `0x1801b06d0`
- `0x1801b1118`
- `0x1801b1374`
- `0x1801b14e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b0961`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b0990`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b09b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b0961`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b0990`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b09b7`
- `WININET!InternetSetOptionW` at `0x1801b08ce`
- `WININET!InternetSetOptionW` at `0x1801b08ce`
- `WININET!InternetCloseHandle` at `0x1801b0927`
- `WININET!InternetCloseHandle` at `0x1801b0927`
- `WININET!InternetOpenW` at `0x1801b0899`
- `WININET!InternetOpenW` at `0x1801b0899`
- `WININET!InternetConnectW` at `0x1801b090b`
- `WININET!InternetConnectW` at `0x1801b090b`

## pseudocode

```c
__int64 __fastcall CConnectedSearchTransport::CConnectedEndpoint::_EnsureInitialized(
        CConnectedSearchTransport::CConnectedEndpoint *this)
{
  int UrlParts; // edi
  __int64 v3; // r9
  __int64 v4; // r9
  __int64 v5; // rdx
  const WCHAR *v6; // r15
  int v7; // eax
  INTERNET_PORT v8; // r14
  LPCWSTR v9; // r13
  void *v10; // rsi
  LPCWSTR v11; // r12
  HINTERNET v12; // r14
  void *v13; // rcx
  unsigned __int16 *v14; // rsi
  void *v15; // rcx
  void *v16; // rcx
  unsigned int v17; // eax
  LPCWSTR lpszServerName; // [rsp+40h] [rbp-69h] BYREF
  __int64 v20; // [rsp+48h] [rbp-61h]
  __int64 v21; // [rsp+50h] [rbp-59h]
  LPCWSTR pwzURI; // [rsp+58h] [rbp-51h] BYREF
  __int64 v23; // [rsp+60h] [rbp-49h]
  __int64 v24; // [rsp+68h] [rbp-41h]
  unsigned __int16 *v25; // [rsp+70h] [rbp-39h] BYREF
  __int64 v26; // [rsp+78h] [rbp-31h]
  __int64 v27; // [rsp+80h] [rbp-29h]
  LPCWSTR lpszAgent; // [rsp+88h] [rbp-21h] BYREF
  __int64 v29; // [rsp+90h] [rbp-19h]
  __int64 v30; // [rsp+98h] [rbp-11h]
  _QWORD v31[12]; // [rsp+A0h] [rbp-9h] BYREF
  unsigned int v32; // [rsp+110h] [rbp+67h] BYREF
  int Buffer; // [rsp+118h] [rbp+6Fh] BYREF
  char v34; // [rsp+120h] [rbp+77h] BYREF
  char v35; // [rsp+128h] [rbp+7Fh] BYREF

  UrlParts = 0;
  wil::AcquireSRWLockExclusive(&v35, (char *)this + 16);
  if ( !*((_BYTE *)this + 24) )
  {
    v3 = 200LL * *(unsigned int *)this;
    memset(v31, 0, 24);
    pwzURI = 0;
    v4 = *(__int64 *)((char *)&CConnectedSearchTransport::s_rgEndpointRegMap + v3 + 32);
    v23 = 0;
    v24 = 0;
    if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                v31,
                -2147483646,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\ConnectedSearch",
                v4) < 0 )
      v5 = (__int64)*(&CConnectedSearchTransport::s_rgEndpointRegMap + 25 * *(unsigned int *)this);
    else
      v5 = v31[0];
    UrlParts = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                 &pwzURI,
                 v5,
                 -1);
    if ( UrlParts < 0 )
      goto LABEL_34;
    lpszServerName = 0;
    v20 = 0;
    v21 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpszServerName);
    v6 = pwzURI;
    v20 = -1;
    v21 = -1;
    if ( CConnectedSearchTransport::CConnectedEndpoint::_UpdateDomain(
           this,
           pwzURI,
           (unsigned __int16 **)&lpszServerName) >= 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pwzURI);
      v23 = -1;
      v24 = -1;
      v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CopyTo(
             &lpszServerName,
             &pwzURI);
      v6 = pwzURI;
      UrlParts = v7;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpszServerName);
    if ( UrlParts < 0 )
      goto LABEL_34;
    lpszServerName = 0;
    v20 = 0;
    v21 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v32 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v25);
    v26 = -1;
    v27 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpszServerName);
    v20 = -1;
    v21 = -1;
    UrlParts = CConnectedSearchTransport::CConnectedEndpoint::s_GetUrlParts(
                 v6,
                 &v32,
                 (unsigned __int16 **)&lpszServerName,
                 &v25);
    if ( UrlParts < 0 )
    {
LABEL_33:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v25);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpszServerName);
LABEL_34:
      *((_BYTE *)this + 24) = UrlParts >= 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pwzURI);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v31);
      goto LABEL_35;
    }
    v8 = 443;
    if ( v32 != 11 )
      v8 = 80;
    lpszAgent = 0;
    v29 = 0;
    v30 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpszAgent);
    v29 = -1;
    v30 = -1;
    UrlParts = CConnectedSearchTransport::s_GetUserAgentString((unsigned __int16 **)&lpszAgent);
    if ( UrlParts < 0
      || (v9 = lpszAgent, (v10 = InternetOpenW(lpszAgent, 0, 0, 0, 0)) == 0)
      && (UrlParts = ResultFromKnownLastError(), UrlParts < 0) )
    {
LABEL_32:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpszAgent);
      goto LABEL_33;
    }
    Buffer = 1;
    if ( InternetSetOptionW(v10, 0x41u, &Buffer, 4u) || (UrlParts = ResultFromKnownLastError(), UrlParts >= 0) )
    {
      v11 = lpszServerName;
      v12 = InternetConnectW(v10, lpszServerName, v8, 0, 0, 3u, 0, 0);
      if ( v12 )
      {
        UrlParts = 0;
      }
      else
      {
        UrlParts = ResultFromKnownLastError();
        if ( UrlParts < 0 )
          goto LABEL_19;
      }
      wil::AcquireSRWLockExclusive(&v34, (char *)this + 32);
      *((_QWORD *)this + 5) = v12;
      *((_QWORD *)this + 1) = v10;
      v13 = (void *)*((_QWORD *)this + 7);
      pwzURI = 0;
      v24 = 0;
      v23 = 0;
      if ( v13 )
        CoTaskMemFree(v13);
      v14 = v25;
      *((_QWORD *)this + 7) = v6;
      *((_QWORD *)this + 9) = -1;
      *((_QWORD *)this + 8) = -1;
      v15 = (void *)*((_QWORD *)this + 10);
      v25 = 0;
      v27 = 0;
      v26 = 0;
      if ( v15 )
        CoTaskMemFree(v15);
      *((_QWORD *)this + 10) = v14;
      *((_QWORD *)this + 12) = -1;
      *((_QWORD *)this + 11) = -1;
      v16 = (void *)*((_QWORD *)this + 13);
      lpszServerName = 0;
      v21 = 0;
      v20 = 0;
      if ( v16 )
        CoTaskMemFree(v16);
      v17 = v32;
      *((_QWORD *)this + 13) = v11;
      *((_QWORD *)this + 15) = -1;
      *((_QWORD *)this + 14) = -1;
      *((_DWORD *)this + 32) = v17;
      if ( v17 == 11 )
        *((_DWORD *)this + 12) |= 0x800000u;
      if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
        McTemplateU0qzzz_EventWriteTransfer(
          (_DWORD)v16,
          (unsigned int)ConnectedSearch_ConnectionEstablished,
          *(_DWORD *)this,
          0,
          *((_QWORD *)this + 10),
          (__int64)v9);
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v34);
      goto LABEL_32;
    }
LABEL_19:
    InternetCloseHandle(v10);
    goto LABEL_32;
  }
LABEL_35:
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v35);
  return (unsigned int)UrlParts;
}

```

## disassembly

```asm
0x1801b06d0  push    rbp
0x1801b06d2  push    rbx
0x1801b06d3  push    rsi
0x1801b06d4  push    rdi
0x1801b06d5  push    r12
0x1801b06d7  push    r13
0x1801b06d9  push    r14
0x1801b06db  push    r15
0x1801b06dd  lea     rbp, [rsp-1Fh]
0x1801b06e2  sub     rsp, 0C8h
0x1801b06e9  mov     rbx, rcx
0x1801b06ec  lea     rdx, [rcx+10h]
0x1801b06f0  xor     r12d, r12d
0x1801b06f3  lea     rcx, [rbp+57h+arg_18]
0x1801b06f7  mov     edi, r12d
0x1801b06fa  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1801b06ff  cmp     [rbx+18h], r12b
0x1801b0703  jnz     loc_1801B0A45
0x1801b0709  mov     eax, [rbx]
0x1801b070b  lea     rdi, ?s_rgEndpointRegMap@CConnectedSearchTransport@@0PAUHTTP_ENDPOINT_REGISTRATION@1@A; CConnectedSearchTransport::HTTP_ENDPOINT_REGISTRATION near * CConnectedSearchTransport::s_rgEndpointRegMap
0x1801b0712  imul    r9, rax, 0C8h
0x1801b0719  lea     r8, aSoftwareMicros_80; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801b0720  mov     [rbp+57h+var_60], r12
0x1801b0724  mov     rdx, 0FFFFFFFF80000002h
0x1801b072b  mov     [rbp+57h+var_58], r12
0x1801b072f  lea     rcx, [rbp+57h+var_60]
0x1801b0733  mov     [rbp+57h+var_50], r12
0x1801b0737  mov     [rbp+57h+pwzURI], r12
0x1801b073b  mov     r9, [r9+rdi+20h]
0x1801b0740  mov     [rbp+57h+var_A0], r12
0x1801b0744  mov     [rbp+57h+var_98], r12
0x1801b0748  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x1801b074d  test    eax, eax
0x1801b074f  js      short loc_1801B0757
0x1801b0751  mov     rdx, [rbp+57h+var_60]
0x1801b0755  jmp     short loc_1801B0764
0x1801b0757  mov     eax, [rbx]
0x1801b0759  imul    rcx, rax, 0C8h
0x1801b0760  mov     rdx, [rcx+rdi]
0x1801b0764  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801b0768  lea     rcx, [rbp+57h+pwzURI]
0x1801b076c  mov     r8, rsi
0x1801b076f  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1801b0774  mov     edi, eax
0x1801b0776  test    eax, eax
0x1801b0778  js      loc_1801B0A29
0x1801b077e  lea     rcx, [rbp+57h+lpszServerName]
0x1801b0782  mov     [rbp+57h+lpszServerName], r12
0x1801b0786  mov     [rbp+57h+var_B8], r12
0x1801b078a  mov     [rbp+57h+var_B0], r12
0x1801b078e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b0793  mov     r15, [rbp+57h+pwzURI]
0x1801b0797  lea     r8, [rbp+57h+lpszServerName]; unsigned __int16 **
0x1801b079b  mov     rdx, r15; unsigned __int16 *
0x1801b079e  mov     [rbp+57h+var_B8], rsi
0x1801b07a2  mov     rcx, rbx; this
0x1801b07a5  mov     [rbp+57h+var_B0], rsi
0x1801b07a9  call    ?_UpdateDomain@CConnectedEndpoint@CConnectedSearchTransport@@AEAAJPEBGPEAPEAG@Z; CConnectedSearchTransport::CConnectedEndpoint::_UpdateDomain(ushort const *,ushort * *)
0x1801b07ae  test    eax, eax
0x1801b07b0  js      short loc_1801B07D6
0x1801b07b2  lea     rcx, [rbp+57h+pwzURI]
0x1801b07b6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b07bb  lea     rdx, [rbp+57h+pwzURI]
0x1801b07bf  mov     [rbp+57h+var_A0], rsi
0x1801b07c3  lea     rcx, [rbp+57h+lpszServerName]
0x1801b07c7  mov     [rbp+57h+var_98], rsi
0x1801b07cb  call    ?CopyTo@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CopyTo(ushort * *)
0x1801b07d0  mov     r15, [rbp+57h+pwzURI]
0x1801b07d4  mov     edi, eax
0x1801b07d6  lea     rcx, [rbp+57h+lpszServerName]
0x1801b07da  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b07df  test    edi, edi
0x1801b07e1  js      loc_1801B0A29
0x1801b07e7  lea     rcx, [rbp+57h+var_90]
0x1801b07eb  mov     [rbp+57h+lpszServerName], r12
0x1801b07ef  mov     [rbp+57h+var_B8], r12
0x1801b07f3  mov     [rbp+57h+var_B0], r12
0x1801b07f7  mov     [rbp+57h+var_90], r12
0x1801b07fb  mov     [rbp+57h+var_88], r12
0x1801b07ff  mov     [rbp+57h+var_80], r12
0x1801b0803  mov     [rbp+57h+arg_0], r12d
0x1801b0807  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b080c  lea     rcx, [rbp+57h+lpszServerName]
0x1801b0810  mov     [rbp+57h+var_88], rsi
0x1801b0814  mov     [rbp+57h+var_80], rsi
0x1801b0818  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b081d  lea     r9, [rbp+57h+var_90]; unsigned __int16 **
0x1801b0821  mov     [rbp+57h+var_B8], rsi
0x1801b0825  lea     r8, [rbp+57h+lpszServerName]; unsigned __int16 **
0x1801b0829  mov     [rbp+57h+var_B0], rsi
0x1801b082d  lea     rdx, [rbp+57h+arg_0]; unsigned int *
0x1801b0831  mov     rcx, r15; pwzURI
0x1801b0834  call    ?s_GetUrlParts@CConnectedEndpoint@CConnectedSearchTransport@@CAJPEBGPEAKPEAPEAG2@Z; CConnectedSearchTransport::CConnectedEndpoint::s_GetUrlParts(ushort const *,ulong *,ushort * *,ushort * *)
0x1801b0839  mov     edi, eax
0x1801b083b  test    eax, eax
0x1801b083d  js      loc_1801B0A17
0x1801b0843  cmp     [rbp+57h+arg_0], 0Bh
0x1801b0847  mov     r14d, 1BBh
0x1801b084d  jz      short loc_1801B0855
0x1801b084f  mov     r14d, 50h ; 'P'
0x1801b0855  lea     rcx, [rbp+57h+lpszAgent]
0x1801b0859  mov     [rbp+57h+lpszAgent], r12
0x1801b085d  mov     [rbp+57h+var_70], r12
0x1801b0861  mov     [rbp+57h+var_68], r12
0x1801b0865  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b086a  lea     rcx, [rbp+57h+lpszAgent]; unsigned __int16 **
0x1801b086e  mov     [rbp+57h+var_70], rsi
0x1801b0872  mov     [rbp+57h+var_68], rsi
0x1801b0876  call    ?s_GetUserAgentString@CConnectedSearchTransport@@SAJPEAPEAG@Z; CConnectedSearchTransport::s_GetUserAgentString(ushort * *)
0x1801b087b  mov     edi, eax
0x1801b087d  test    eax, eax
0x1801b087f  js      loc_1801B0A0E
0x1801b0885  mov     r13, [rbp+57h+lpszAgent]
0x1801b0889  xor     r9d, r9d; lpszProxyBypass
0x1801b088c  mov     rcx, r13; lpszAgent
0x1801b088f  mov     [rsp+100h+dwFlags], r12d; dwFlags
0x1801b0894  xor     r8d, r8d; lpszProxy
0x1801b0897  xor     edx, edx; dwAccessType
0x1801b0899  call    cs:__imp_InternetOpenW
0x1801b089f  mov     rsi, rax
0x1801b08a2  test    rax, rax
0x1801b08a5  jnz     short loc_1801B08B6
0x1801b08a7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801b08ac  mov     edi, eax
0x1801b08ae  test    eax, eax
0x1801b08b0  js      loc_1801B0A0E
0x1801b08b6  mov     r9d, 4; dwBufferLength
0x1801b08bc  mov     [rbp+57h+Buffer], 1
0x1801b08c3  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1801b08c7  mov     rcx, rsi; hInternet
0x1801b08ca  lea     edx, [r9+3Dh]; dwOption
0x1801b08ce  call    cs:__imp_InternetSetOptionW
0x1801b08d4  test    eax, eax
0x1801b08d6  jnz     short loc_1801B08E3
0x1801b08d8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801b08dd  mov     edi, eax
0x1801b08df  test    eax, eax
0x1801b08e1  js      short loc_1801B0924
0x1801b08e3  mov     [rsp+100h+dwContext], r12; dwContext
0x1801b08e8  xor     r9d, r9d; lpszUserName
0x1801b08eb  mov     [rsp+100h+var_D0], r12d; dwFlags
0x1801b08f0  movzx   r8d, r14w; nServerPort
0x1801b08f4  mov     [rsp+100h+dwService], 3; dwService
0x1801b08fc  mov     rcx, rsi; hInternet
0x1801b08ff  mov     qword ptr [rsp+100h+dwFlags], r12; lpszPassword
0x1801b0904  mov     r12, [rbp+57h+lpszServerName]
0x1801b0908  mov     rdx, r12; lpszServerName
0x1801b090b  call    cs:__imp_InternetConnectW
0x1801b0911  mov     r14, rax
0x1801b0914  test    rax, rax
0x1801b0917  jnz     short loc_1801B0932
0x1801b0919  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801b091e  mov     edi, eax
0x1801b0920  test    eax, eax
0x1801b0922  jns     short loc_1801B0934
0x1801b0924  mov     rcx, rsi; hInternet
0x1801b0927  call    cs:__imp_InternetCloseHandle
0x1801b092d  jmp     loc_1801B0A0E
0x1801b0932  xor     edi, edi
0x1801b0934  lea     rdx, [rbx+20h]
0x1801b0938  lea     rcx, [rbp+57h+arg_10]
0x1801b093c  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1801b0941  mov     [rbx+28h], r14
0x1801b0945  xor     r14d, r14d
0x1801b0948  mov     [rbx+8], rsi
0x1801b094c  mov     rcx, [rbx+38h]; pv
0x1801b0950  mov     [rbp+57h+pwzURI], r14
0x1801b0954  mov     [rbp+57h+var_98], r14
0x1801b0958  mov     [rbp+57h+var_A0], r14
0x1801b095c  test    rcx, rcx
0x1801b095f  jz      short loc_1801B0967
0x1801b0961  call    cs:__imp_CoTaskMemFree
0x1801b0967  mov     rsi, [rbp+57h+var_90]
0x1801b096b  mov     [rbx+38h], r15
0x1801b096f  or      r15, 0FFFFFFFFFFFFFFFFh
0x1801b0973  mov     [rbx+48h], r15
0x1801b0977  mov     [rbx+40h], r15
0x1801b097b  mov     rcx, [rbx+50h]; pv
0x1801b097f  mov     [rbp+57h+var_90], r14
0x1801b0983  mov     [rbp+57h+var_80], r14
0x1801b0987  mov     [rbp+57h+var_88], r14
0x1801b098b  test    rcx, rcx
0x1801b098e  jz      short loc_1801B0996
0x1801b0990  call    cs:__imp_CoTaskMemFree
0x1801b0996  mov     [rbx+50h], rsi
0x1801b099a  mov     [rbx+60h], r15
0x1801b099e  mov     [rbx+58h], r15
0x1801b09a2  mov     rcx, [rbx+68h]; pv
0x1801b09a6  mov     [rbp+57h+lpszServerName], r14
0x1801b09aa  mov     [rbp+57h+var_B0], r14
0x1801b09ae  mov     [rbp+57h+var_B8], r14
0x1801b09b2  test    rcx, rcx
0x1801b09b5  jz      short loc_1801B09BD
0x1801b09b7  call    cs:__imp_CoTaskMemFree
0x1801b09bd  mov     eax, [rbp+57h+arg_0]
0x1801b09c0  mov     [rbx+68h], r12
0x1801b09c4  mov     [rbx+78h], r15
0x1801b09c8  mov     [rbx+70h], r15
0x1801b09cc  mov     [rbx+80h], eax
0x1801b09d2  cmp     eax, 0Bh
0x1801b09d5  jnz     short loc_1801B09DC
0x1801b09d7  bts     dword ptr [rbx+30h], 17h
0x1801b09dc  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x1801b09e3  jz      short loc_1801B0A05
0x1801b09e5  mov     rax, [rbx+50h]
0x1801b09e9  lea     rdx, ConnectedSearch_ConnectionEstablished
0x1801b09f0  mov     r8d, [rbx]
0x1801b09f3  xor     r9d, r9d
0x1801b09f6  mov     qword ptr [rsp+100h+dwService], r13
0x1801b09fb  mov     qword ptr [rsp+100h+dwFlags], rax
0x1801b0a00  call    McTemplateU0qzzz_EventWriteTransfer
0x1801b0a05  lea     rcx, [rbp+57h+arg_10]; this
0x1801b0a09  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1801b0a0e  lea     rcx, [rbp+57h+lpszAgent]
0x1801b0a12  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b0a17  lea     rcx, [rbp+57h+var_90]
0x1801b0a1b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b0a20  lea     rcx, [rbp+57h+lpszServerName]
0x1801b0a24  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b0a29  mov     eax, edi
0x1801b0a2b  lea     rcx, [rbp+57h+pwzURI]
0x1801b0a2f  shr     eax, 1Fh
0x1801b0a32  xor     al, 1
0x1801b0a34  mov     [rbx+18h], al
0x1801b0a37  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b0a3c  lea     rcx, [rbp+57h+var_60]
0x1801b0a40  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801b0a45  lea     rcx, [rbp+57h+arg_18]; this
0x1801b0a49  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1801b0a4e  mov     eax, edi
0x1801b0a50  add     rsp, 0C8h
0x1801b0a57  pop     r15
0x1801b0a59  pop     r14
0x1801b0a5b  pop     r13
0x1801b0a5d  pop     r12
0x1801b0a5f  pop     rdi
0x1801b0a60  pop     rsi
0x1801b0a61  pop     rbx
0x1801b0a62  pop     rbp
0x1801b0a63  retn
```
