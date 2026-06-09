# CSecurityManager::GetSecurityIdFromUrlInternal(ushort const *,uchar *,ulong *,unsigned __int64,ulong)

- ea: `0x180040a60`
- end: `0x180040e99`
- name: `?GetSecurityIdFromUrlInternal@CSecurityManager@@UEAAJPEBGPEAEPEAK_KK@Z`
- size: `1081`
- prototype: `__int64 __fastcall(CSecurityManager *this, const unsigned __int16 *, unsigned __int8 *, unsigned int *, const WCHAR *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180040a30`

## callees

- `0x18001a710`
- `0x18001acb0`
- `0x18001b230`
- `0x180040a60`
- `0x180041188`
- `0x180042850`
- `0x180129010`

## import_xrefs

- `iertutil!CreateUri` at `0x180040b5e`
- `iertutil!CreateUri` at `0x180040d0d`
- `iertutil!CreateUri` at `0x180040b5e`
- `iertutil!CreateUri` at `0x180040d0d`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180040dc3`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180040df4`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180040e1f`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180040dc3`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180040df4`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180040e1f`
- `iertutil!__imp_GetWebPlatformSecurityManagerFactoryCallback` at `0x180040c31`
- `iertutil!__imp_GetWebPlatformSecurityManagerFactoryCallback` at `0x180040c31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040c03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040c03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040bbf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040bbf`

## pseudocode

```c
__int64 __fastcall CSecurityManager::GetSecurityIdFromUrlInternal(
        CSecurityManager *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int *a4,
        const WCHAR *a5,
        unsigned int a6)
{
  const WCHAR *v10; // r13
  __int64 v11; // rcx
  __int64 v12; // rbx
  int ZoneAgnosticSecurityIdFromUrl; // eax
  int SecurityIdEx2Internal; // edi
  IUri *v15; // rbx
  IUri *v16; // rcx
  struct IUriVtbl *lpVtbl; // rax
  IUri *v18; // rbx
  __int64 v19; // rdi
  unsigned int v20; // r14d
  int BrowserProcess; // eax
  __int64 (__fastcall *WebPlatformSecurityManagerFactoryCallback)(struct IWebPlatformPermanentSecurityManager **); // rax
  int v23; // eax
  bool v24; // sf
  int v25; // eax
  IUri *v26; // rbx
  int v28; // edx
  int v29; // eax
  int IsFeatureEnabledInternal; // eax
  int v31; // eax
  int v32; // eax
  IUri *ppURI; // [rsp+88h] [rbp+48h] BYREF
  CSecurityManager *v34; // [rsp+90h] [rbp+50h]

  if ( a3 )
    *a3 = 0;
  if ( a2 && *a2 && a4 )
  {
    v10 = a5;
    v34 = (CSecurityManager *)((char *)this - 16);
    if ( *((_QWORD *)this + 10) )
    {
      ppURI = 0;
      SecurityIdEx2Internal = CreateUri(a2, 0x3002B84u, 0, &ppURI);
      if ( SecurityIdEx2Internal < 0 )
        goto LABEL_19;
      v15 = ppURI;
      SecurityIdEx2Internal = (*(__int64 (__fastcall **)(_QWORD, IUri *, unsigned __int8 *, unsigned int *))(**((_QWORD **)this + 10) + 40LL))(
                                *((_QWORD *)this + 10),
                                ppURI,
                                a3,
                                a4);
      v16 = v15;
      lpVtbl = v15->lpVtbl;
LABEL_18:
      ((void (__fastcall *)(IUri *))lpVtbl->Release)(v16);
LABEL_19:
      if ( SecurityIdEx2Internal != -2146697199 )
        return (unsigned int)SecurityIdEx2Internal;
LABEL_20:
      v18 = 0;
      ppURI = 0;
      SecurityIdEx2Internal = 1;
      EnterCriticalSection(&g_mxsPermanentISM);
      if ( byte_18016B8D0 )
      {
        v19 = qword_18016B8C0;
        if ( qword_18016B8C0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18016B8C0 + 8LL))(qword_18016B8C0);
          v18 = (IUri *)v19;
          SecurityIdEx2Internal = 0;
          ppURI = v18;
        }
        else
        {
          SecurityIdEx2Internal = -2147418113;
        }
      }
      LeaveCriticalSection(&g_mxsPermanentISM);
      v20 = a6;
      if ( SecurityIdEx2Internal == 1 )
      {
        BrowserProcess = GetBrowserProcess();
        if ( ((BrowserProcess - 15) & 0xFFFFFFF6) == 0 && BrowserProcess != 24 )
          goto LABEL_40;
        WebPlatformSecurityManagerFactoryCallback = (__int64 (__fastcall *)(struct IWebPlatformPermanentSecurityManager **))GetWebPlatformSecurityManagerFactoryCallback();
        if ( !WebPlatformSecurityManagerFactoryCallback )
          goto LABEL_40;
        v23 = GetAndRegisterWebPlatformPermanantSecurityManager(WebPlatformSecurityManagerFactoryCallback);
        SecurityIdEx2Internal = v23;
        if ( v23 )
        {
          v24 = v23 < 0;
          goto LABEL_29;
        }
        v25 = ObtainPermanentInternetSecurityManagerInternal((__int64 *)&ppURI);
        v18 = ppURI;
        SecurityIdEx2Internal = v25;
      }
      v24 = SecurityIdEx2Internal < 0;
      if ( SecurityIdEx2Internal )
      {
LABEL_29:
        if ( !v24 )
        {
LABEL_40:
          ppURI = 0;
          SecurityIdEx2Internal = CreateUri(a2, 0x3002B84u, 0, &ppURI);
          if ( SecurityIdEx2Internal >= 0 )
          {
            v26 = ppURI;
            SecurityIdEx2Internal = CSecurityManager::GetSecurityIdEx2Internal(
                                      (const WCHAR *)v34,
                                      ppURI,
                                      a3,
                                      a4,
                                      v10,
                                      v20);
            ((void (__fastcall *)(IUri *))v26->lpVtbl->Release)(v26);
          }
          return (unsigned int)SecurityIdEx2Internal;
        }
        goto LABEL_39;
      }
      ppURI = 0;
      if ( FCK::FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER )
      {
        IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
        if ( IsFeatureEnabledInternal < 0 )
        {
LABEL_35:
          if ( !((unsigned __int64 (__fastcall *)(IUri *, GUID *, IUri **))v18->lpVtbl->QueryInterface)(
                  v18,
                  &GUID_c90db44a_1902_451e_bdf0_5c89660b528c,
                  &ppURI)
            && ppURI )
          {
            SecurityIdEx2Internal = ((__int64 (__fastcall *)(IUri *, const unsigned __int16 *, unsigned __int8 *, unsigned int *, const WCHAR *, unsigned int))ppURI->lpVtbl->GetPropertyLength)(
                                      ppURI,
                                      a2,
                                      a3,
                                      a4,
                                      v10,
                                      v20);
            ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
            goto LABEL_38;
          }
LABEL_37:
          SecurityIdEx2Internal = ((__int64 (__fastcall *)(IUri *, const unsigned __int16 *, unsigned __int8 *, unsigned int *, const WCHAR *))v18->lpVtbl->HasProperty)(
                                    v18,
                                    a2,
                                    a3,
                                    a4,
                                    v10);
LABEL_38:
          ((void (__fastcall *)(IUri *))v18->lpVtbl->Release)(v18);
LABEL_39:
          if ( SecurityIdEx2Internal == -2146697199 )
            goto LABEL_40;
          return (unsigned int)SecurityIdEx2Internal;
        }
        dword_180166B48 = IsFeatureEnabledInternal == 0;
        FCK::FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER = 0;
      }
      if ( dword_180166B48 )
        goto LABEL_37;
      goto LABEL_35;
    }
    v11 = *((_QWORD *)this + 9);
    if ( v11 || (v11 = *((_QWORD *)this + 8)) != 0 )
    {
      ZoneAgnosticSecurityIdFromUrl = GetZoneAgnosticSecurityIdFromUrl(
                                        v11,
                                        (__int64)a2,
                                        (__int64)a3,
                                        (__int64)a4,
                                        (__int64)a5);
      goto LABEL_15;
    }
    v12 = *((_QWORD *)this + 7);
    if ( !v12 )
      goto LABEL_20;
    ppURI = 0;
    if ( FCK::FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER )
    {
      v31 = CoInternetIsFeatureEnabledInternal();
      if ( v31 < 0 )
        goto LABEL_12;
      dword_180166B48 = v31 == 0;
      FCK::FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER = 0;
    }
    if ( dword_180166B48 )
    {
LABEL_14:
      ZoneAgnosticSecurityIdFromUrl = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int8 *, unsigned int *, const WCHAR *))(*(_QWORD *)v12 + 48LL))(
                                        v12,
                                        a2,
                                        a3,
                                        a4,
                                        v10);
LABEL_15:
      SecurityIdEx2Internal = ZoneAgnosticSecurityIdFromUrl;
      goto LABEL_19;
    }
LABEL_12:
    if ( (**(unsigned int (__fastcall ***)(__int64, GUID *, IUri **))v12)(
           v12,
           &GUID_c90db44a_1902_451e_bdf0_5c89660b528c,
           &ppURI)
      || !ppURI )
    {
      goto LABEL_14;
    }
    if ( FCK::FEATURE_DISABLE_IGNORE_ZONE_FOR_SECURITYID )
    {
      v32 = CoInternetIsFeatureEnabledInternal();
      if ( v32 < 0 )
        goto LABEL_46;
      dword_180166F88 = v32 == 0;
      FCK::FEATURE_DISABLE_IGNORE_ZONE_FOR_SECURITYID = 0;
    }
    v28 = 0;
    if ( dword_180166F88 )
    {
LABEL_47:
      v29 = ((__int64 (__fastcall *)(IUri *, const unsigned __int16 *, unsigned __int8 *, unsigned int *, const WCHAR *, int))ppURI->lpVtbl->GetPropertyLength)(
              ppURI,
              a2,
              a3,
              a4,
              v10,
              v28);
      v16 = ppURI;
      SecurityIdEx2Internal = v29;
      lpVtbl = ppURI->lpVtbl;
      goto LABEL_18;
    }
LABEL_46:
    v28 = 0x20000000;
    goto LABEL_47;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180040a60  mov     [rsp-38h+arg_0], rbx
0x180040a65  push    rbp
0x180040a66  push    rsi
0x180040a67  push    rdi
0x180040a68  push    r12
0x180040a6a  push    r13
0x180040a6c  push    r14
0x180040a6e  push    r15
0x180040a70  mov     rbp, rsp
0x180040a73  sub     rsp, 40h
0x180040a77  xor     edi, edi
0x180040a79  mov     r12, r9
0x180040a7c  mov     r15, r8
0x180040a7f  mov     rsi, rdx
0x180040a82  mov     r14, rcx
0x180040a85  test    r8, r8
0x180040a88  jz      short loc_180040A8D
0x180040a8a  mov     [r8], dil
0x180040a8d  test    rsi, rsi
0x180040a90  jz      loc_180040D6B
0x180040a96  cmp     [rdx], di
0x180040a99  jz      loc_180040D6B
0x180040a9f  test    r12, r12
0x180040aa2  jz      loc_180040D6B
0x180040aa8  mov     r13, [rbp+arg_20]
0x180040aac  lea     rax, [rcx-10h]
0x180040ab0  mov     [rbp+arg_10], rax
0x180040ab4  cmp     [rax+60h], rdi
0x180040ab8  jnz     loc_180040B4B
0x180040abe  mov     rcx, [rcx+48h]
0x180040ac2  test    rcx, rcx
0x180040ac5  jnz     loc_180040E4A
0x180040acb  mov     rcx, [r14+40h]
0x180040acf  test    rcx, rcx
0x180040ad2  jnz     loc_180040E4A
0x180040ad8  mov     rbx, [r14+38h]
0x180040adc  test    rbx, rbx
0x180040adf  jz      loc_180040BAC
0x180040ae5  mov     rcx, cs:?FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER
0x180040aec  mov     [rbp+ppURI], rdi
0x180040af0  test    rcx, rcx
0x180040af3  jnz     loc_180040DF4
0x180040af9  mov     eax, cs:dword_180166B48
0x180040aff  test    eax, eax
0x180040b01  jnz     short loc_180040B2A
0x180040b03  mov     rax, [rbx]
0x180040b06  lea     r8, [rbp+ppURI]
0x180040b0a  lea     rdx, _GUID_c90db44a_1902_451e_bdf0_5c89660b528c
0x180040b11  mov     rcx, rbx
0x180040b14  mov     rax, [rax]
0x180040b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b1c  test    eax, eax
0x180040b1e  jnz     short loc_180040B2A
0x180040b20  cmp     [rbp+ppURI], rdi
0x180040b24  jnz     loc_180040D72
0x180040b2a  mov     rax, [rbx]
0x180040b2d  mov     r9, r12
0x180040b30  mov     r8, r15
0x180040b33  mov     [rsp+40h+var_20], r13
0x180040b38  mov     rdx, rsi
0x180040b3b  mov     rcx, rbx
0x180040b3e  mov     rax, [rax+30h]
0x180040b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b47  mov     edi, eax
0x180040b49  jmp     short loc_180040B9E
0x180040b4b  lea     r9, [rbp+ppURI]; ppURI
0x180040b4f  mov     [rbp+ppURI], rdi
0x180040b53  xor     r8d, r8d; dwReserved
0x180040b56  mov     edx, 3002B84h; dwFlags
0x180040b5b  mov     rcx, rsi; pwzURI
0x180040b5e  call    cs:__imp_CreateUri
0x180040b65  nop     dword ptr [rax+rax+00h]
0x180040b6a  mov     edi, eax
0x180040b6c  test    eax, eax
0x180040b6e  js      short loc_180040B9E
0x180040b70  mov     rcx, [r14+50h]
0x180040b74  mov     r9, r12
0x180040b77  mov     rbx, [rbp+ppURI]
0x180040b7b  mov     r8, r15
0x180040b7e  mov     rdx, rbx
0x180040b81  mov     rax, [rcx]
0x180040b84  mov     rax, [rax+28h]
0x180040b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b8d  mov     edi, eax
0x180040b8f  mov     rcx, rbx
0x180040b92  mov     rax, [rbx]
0x180040b95  mov     rax, [rax+10h]
0x180040b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b9e  cmp     edi, 800C0011h
0x180040ba4  jnz     loc_180040D50
0x180040baa  xor     edi, edi
0x180040bac  mov     rbx, rdi
0x180040baf  lea     rcx, ?g_mxsPermanentISM@@3VCMutexSem@@A; lpCriticalSection
0x180040bb6  mov     [rbp+ppURI], rbx
0x180040bba  mov     edi, 1
0x180040bbf  call    cs:__imp_EnterCriticalSection
0x180040bc6  nop     dword ptr [rax+rax+00h]
0x180040bcb  cmp     cs:byte_18016B8D0, 0
0x180040bd2  jz      short loc_180040BFC
0x180040bd4  mov     rdi, cs:qword_18016B8C0
0x180040bdb  test    rdi, rdi
0x180040bde  jz      loc_180040E59
0x180040be4  mov     rax, [rdi]
0x180040be7  mov     rcx, rdi
0x180040bea  mov     rax, [rax+8]
0x180040bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040bf3  mov     rbx, rdi
0x180040bf6  xor     edi, edi
0x180040bf8  mov     [rbp+ppURI], rbx
0x180040bfc  lea     rcx, ?g_mxsPermanentISM@@3VCMutexSem@@A; lpCriticalSection
0x180040c03  call    cs:__imp_LeaveCriticalSection
0x180040c0a  nop     dword ptr [rax+rax+00h]
0x180040c0f  mov     r14d, [rbp+arg_28]
0x180040c13  cmp     edi, 1
0x180040c16  jnz     short loc_180040C70
0x180040c18  call    GetBrowserProcess
0x180040c1d  lea     ecx, [rax-0Fh]
0x180040c20  test    ecx, 0FFFFFFF6h
0x180040c26  jnz     short loc_180040C31
0x180040c28  cmp     eax, 18h
0x180040c2b  jnz     loc_180040CF6
0x180040c31  call    cs:__imp_GetWebPlatformSecurityManagerFactoryCallback
0x180040c38  nop     dword ptr [rax+rax+00h]
0x180040c3d  test    rax, rax
0x180040c40  jz      loc_180040CF6
0x180040c46  mov     rcx, rax
0x180040c49  call    GetAndRegisterWebPlatformPermanantSecurityManager
0x180040c4e  mov     edi, eax
0x180040c50  test    eax, eax
0x180040c52  jz      short loc_180040C61
0x180040c54  test    eax, eax
0x180040c56  js      loc_180040CEE
0x180040c5c  jmp     loc_180040CF6
0x180040c61  lea     rcx, [rbp+ppURI]
0x180040c65  call    ObtainPermanentInternetSecurityManagerInternal
0x180040c6a  mov     rbx, [rbp+ppURI]
0x180040c6e  mov     edi, eax
0x180040c70  test    edi, edi
0x180040c72  jnz     short loc_180040C56
0x180040c74  mov     rcx, cs:?FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER
0x180040c7b  mov     [rbp+ppURI], 0
0x180040c83  test    rcx, rcx
0x180040c86  jnz     loc_180040DC3
0x180040c8c  mov     eax, cs:dword_180166B48
0x180040c92  test    eax, eax
0x180040c94  jnz     short loc_180040CC0
0x180040c96  mov     rax, [rbx]
0x180040c99  lea     r8, [rbp+ppURI]
0x180040c9d  lea     rdx, _GUID_c90db44a_1902_451e_bdf0_5c89660b528c
0x180040ca4  mov     rcx, rbx
0x180040ca7  mov     rax, [rax]
0x180040caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040caf  test    eax, eax
0x180040cb1  jnz     short loc_180040CC0
0x180040cb3  mov     rcx, [rbp+ppURI]
0x180040cb7  test    rcx, rcx
0x180040cba  jnz     loc_180040E63
0x180040cc0  mov     rax, [rbx]
0x180040cc3  mov     r9, r12
0x180040cc6  mov     r8, r15
0x180040cc9  mov     [rsp+40h+var_20], r13
0x180040cce  mov     rdx, rsi
0x180040cd1  mov     rcx, rbx
0x180040cd4  mov     rax, [rax+30h]
0x180040cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cdd  mov     edi, eax
0x180040cdf  mov     rax, [rbx]
0x180040ce2  mov     rcx, rbx
0x180040ce5  mov     rax, [rax+10h]
0x180040ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cee  cmp     edi, 800C0011h
0x180040cf4  jnz     short loc_180040D50
0x180040cf6  lea     r9, [rbp+ppURI]; ppURI
0x180040cfa  mov     [rbp+ppURI], 0
0x180040d02  xor     r8d, r8d; dwReserved
0x180040d05  mov     edx, 3002B84h; dwFlags
0x180040d0a  mov     rcx, rsi; pwzURI
0x180040d0d  call    cs:__imp_CreateUri
0x180040d14  nop     dword ptr [rax+rax+00h]
0x180040d19  mov     edi, eax
0x180040d1b  test    eax, eax
0x180040d1d  js      short loc_180040D50
0x180040d1f  mov     rbx, [rbp+ppURI]
0x180040d23  mov     r9, r12; unsigned int *
0x180040d26  mov     rcx, [rbp+arg_10]; this
0x180040d2a  mov     rdx, rbx; struct IUri *
0x180040d2d  mov     [rsp+40h+var_18], r14d; unsigned int
0x180040d32  mov     r8, r15; unsigned __int8 *
0x180040d35  mov     [rsp+40h+var_20], r13; unsigned __int64
0x180040d3a  call    ?GetSecurityIdEx2Internal@CSecurityManager@@AEAAJPEAUIUri@@PEAEPEAK_KK@Z; CSecurityManager::GetSecurityIdEx2Internal(IUri *,uchar *,ulong *,unsigned __int64,ulong)
0x180040d3f  mov     edi, eax
0x180040d41  mov     rcx, rbx
0x180040d44  mov     rax, [rbx]
0x180040d47  mov     rax, [rax+10h]
0x180040d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d50  mov     eax, edi
0x180040d52  mov     rbx, [rsp+40h+arg_0]
0x180040d5a  add     rsp, 40h
0x180040d5e  pop     r15
0x180040d60  pop     r14
0x180040d62  pop     r13
0x180040d64  pop     r12
0x180040d66  pop     rdi
0x180040d67  pop     rsi
0x180040d68  pop     rbp
0x180040d69  retn
0x180040d6b  mov     eax, 80070057h
0x180040d70  jmp     short loc_180040D52
0x180040d72  mov     rcx, cs:?FEATURE_DISABLE_IGNORE_ZONE_FOR_SECURITYID@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_IGNORE_ZONE_FOR_SECURITYID
0x180040d79  test    rcx, rcx
0x180040d7c  jnz     loc_180040E1F
0x180040d82  mov     eax, cs:dword_180166F88
0x180040d88  mov     edx, edi
0x180040d8a  test    eax, eax
0x180040d8c  jnz     short loc_180040D93
0x180040d8e  mov     edx, 20000000h
0x180040d93  mov     rcx, [rbp+ppURI]
0x180040d97  mov     r9, r12
0x180040d9a  mov     [rsp+40h+var_18], edx
0x180040d9e  mov     r8, r15
0x180040da1  mov     rdx, rsi
0x180040da4  mov     [rsp+40h+var_20], r13
0x180040da9  mov     rax, [rcx]
0x180040dac  mov     rax, [rax+20h]
0x180040db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040db5  mov     rcx, [rbp+ppURI]
0x180040db9  mov     edi, eax
0x180040dbb  mov     rax, [rcx]
0x180040dbe  jmp     loc_180040B95
0x180040dc3  call    cs:__imp_CoInternetIsFeatureEnabledInternal
0x180040dca  nop     dword ptr [rax+rax+00h]
0x180040dcf  test    eax, eax
0x180040dd1  js      loc_180040C96
0x180040dd7  xor     ecx, ecx
0x180040dd9  test    eax, eax
0x180040ddb  setz    cl
0x180040dde  mov     cs:dword_180166B48, ecx
0x180040de4  mov     cs:?FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER@FCK@@3VCFeatureControlKey@@A, 0; CFeatureControlKey FCK::FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER
0x180040def  jmp     loc_180040C8C
0x180040df4  call    cs:__imp_CoInternetIsFeatureEnabledInternal
0x180040dfb  nop     dword ptr [rax+rax+00h]
0x180040e00  test    eax, eax
0x180040e02  js      loc_180040B03
0x180040e08  mov     ecx, edi
0x180040e0a  setz    cl
0x180040e0d  mov     cs:dword_180166B48, ecx
0x180040e13  mov     cs:?FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER@FCK@@3VCFeatureControlKey@@A, rdi; CFeatureControlKey FCK::FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER
0x180040e1a  jmp     loc_180040AF9
0x180040e1f  call    cs:__imp_CoInternetIsFeatureEnabledInternal
0x180040e26  nop     dword ptr [rax+rax+00h]
0x180040e2b  test    eax, eax
0x180040e2d  js      loc_180040D8E
0x180040e33  mov     ecx, edi
0x180040e35  setz    cl
0x180040e38  mov     cs:dword_180166F88, ecx
0x180040e3e  mov     cs:?FEATURE_DISABLE_IGNORE_ZONE_FOR_SECURITYID@FCK@@3VCFeatureControlKey@@A, rdi; CFeatureControlKey FCK::FEATURE_DISABLE_IGNORE_ZONE_FOR_SECURITYID
0x180040e45  jmp     loc_180040D82
0x180040e4a  mov     [rsp+40h+var_20], r13
0x180040e4f  call    GetZoneAgnosticSecurityIdFromUrl
0x180040e54  jmp     loc_180040B47
0x180040e59  mov     edi, 8000FFFFh
0x180040e5e  jmp     loc_180040BFC
0x180040e63  mov     rax, [rcx]
0x180040e66  mov     r9, r12
0x180040e69  mov     [rsp+40h+var_18], r14d
0x180040e6e  mov     r8, r15
0x180040e71  mov     rdx, rsi
0x180040e74  mov     [rsp+40h+var_20], r13
0x180040e79  mov     rax, [rax+20h]
0x180040e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e82  mov     rcx, [rbp+ppURI]
0x180040e86  mov     edi, eax
0x180040e88  mov     rax, [rcx]
0x180040e8b  mov     rax, [rax+10h]
0x180040e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e94  jmp     loc_180040CDF
```
