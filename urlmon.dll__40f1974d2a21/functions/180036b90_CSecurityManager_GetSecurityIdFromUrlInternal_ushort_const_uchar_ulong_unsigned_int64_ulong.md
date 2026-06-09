# CSecurityManager::GetSecurityIdFromUrlInternal(ushort const *,uchar *,ulong *,unsigned __int64,ulong)

- ea: `0x180036b90`
- end: `0x180036f98`
- name: `?GetSecurityIdFromUrlInternal@CSecurityManager@@UEAAJPEBGPEAEPEAK_KK@Z`
- size: `1032`
- prototype: `int(CSecurityManager *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180036b60`

## callees

- `0x180012410`
- `0x1800128f0`
- `0x180012e20`
- `0x180036b90`
- `0x180037284`
- `0x1800387d0`
- `0x18011c010`

## import_xrefs

- `iertutil!CreateUri` at `0x180036c8e`
- `iertutil!CreateUri` at `0x180036e25`
- `iertutil!CreateUri` at `0x180036c8e`
- `iertutil!CreateUri` at `0x180036e25`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180036ed4`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180036eff`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180036f24`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180036ed4`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180036eff`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180036f24`
- `iertutil!__imp_GetWebPlatformSecurityManagerFactoryCallback` at `0x180036d4f`
- `iertutil!__imp_GetWebPlatformSecurityManagerFactoryCallback` at `0x180036d4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036d27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036d27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036ce9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036ce9`

## pseudocode

```c
__int64 __fastcall CSecurityManager::GetSecurityIdFromUrlInternal(
        CSecurityManager *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  unsigned __int64 v10; // r13
  __int64 v11; // rcx
  __int64 v12; // rbx
  HRESULT ZoneAgnosticSecurityIdFromUrl; // eax
  HRESULT SecurityIdEx2Internal; // edi
  IUri *v15; // rbx
  IUri *v16; // rcx
  struct IUriVtbl *lpVtbl; // rax
  IUri *v18; // rbx
  __int64 v19; // rdi
  unsigned int v20; // r14d
  int BrowserProcess; // eax
  __int64 WebPlatformSecurityManagerFactoryCallback; // rax
  int v23; // eax
  bool v24; // sf
  HRESULT v25; // eax
  IUri *v26; // rbx
  int v28; // edx
  HRESULT v29; // eax
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
      if ( byte_18015E7D8 )
      {
        v19 = qword_18015E7C8;
        if ( qword_18015E7C8 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18015E7C8 + 8LL))(qword_18015E7C8);
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
        WebPlatformSecurityManagerFactoryCallback = GetWebPlatformSecurityManagerFactoryCallback();
        if ( !WebPlatformSecurityManagerFactoryCallback )
          goto LABEL_40;
        v23 = GetAndRegisterWebPlatformPermanantSecurityManager(WebPlatformSecurityManagerFactoryCallback);
        SecurityIdEx2Internal = v23;
        if ( v23 )
        {
          v24 = v23 < 0;
          goto LABEL_29;
        }
        v25 = ObtainPermanentInternetSecurityManagerInternal(&ppURI);
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
            SecurityIdEx2Internal = CSecurityManager::GetSecurityIdEx2Internal(v34, ppURI, a3, a4, v10, v20);
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
            SecurityIdEx2Internal = ((__int64 (__fastcall *)(IUri *, const unsigned __int16 *, unsigned __int8 *, unsigned int *, unsigned __int64, unsigned int))ppURI->lpVtbl->GetPropertyLength)(
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
          SecurityIdEx2Internal = ((__int64 (__fastcall *)(IUri *, const unsigned __int16 *, unsigned __int8 *, unsigned int *, unsigned __int64))v18->lpVtbl->HasProperty)(
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
        dword_180159B48 = IsFeatureEnabledInternal == 0;
        FCK::FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER = 0;
      }
      if ( dword_180159B48 )
        goto LABEL_37;
      goto LABEL_35;
    }
    v11 = *((_QWORD *)this + 9);
    if ( v11 || (v11 = *((_QWORD *)this + 8)) != 0 )
    {
      ZoneAgnosticSecurityIdFromUrl = GetZoneAgnosticSecurityIdFromUrl(v11, (_DWORD)a2, (_DWORD)a3, (_DWORD)a4, a5);
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
      dword_180159B48 = v31 == 0;
      FCK::FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER = 0;
    }
    if ( dword_180159B48 )
    {
LABEL_14:
      ZoneAgnosticSecurityIdFromUrl = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int8 *, unsigned int *, unsigned __int64))(*(_QWORD *)v12 + 48LL))(
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
      dword_180159F88 = v32 == 0;
      FCK::FEATURE_DISABLE_IGNORE_ZONE_FOR_SECURITYID = 0;
    }
    v28 = 0;
    if ( dword_180159F88 )
    {
LABEL_47:
      v29 = ((__int64 (__fastcall *)(IUri *, const unsigned __int16 *, unsigned __int8 *, unsigned int *, unsigned __int64, int))ppURI->lpVtbl->GetPropertyLength)(
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
0x180036b90  mov     [rsp-38h+arg_0], rbx
0x180036b95  push    rbp
0x180036b96  push    rsi
0x180036b97  push    rdi
0x180036b98  push    r12
0x180036b9a  push    r13
0x180036b9c  push    r14
0x180036b9e  push    r15
0x180036ba0  mov     rbp, rsp
0x180036ba3  sub     rsp, 40h
0x180036ba7  xor     edi, edi
0x180036ba9  mov     r12, r9
0x180036bac  mov     r15, r8
0x180036baf  mov     rsi, rdx
0x180036bb2  mov     r14, rcx
0x180036bb5  test    r8, r8
0x180036bb8  jz      short loc_180036BBD
0x180036bba  mov     [r8], dil
0x180036bbd  test    rsi, rsi
0x180036bc0  jz      loc_180036E7C
0x180036bc6  cmp     [rdx], di
0x180036bc9  jz      loc_180036E7C
0x180036bcf  test    r12, r12
0x180036bd2  jz      loc_180036E7C
0x180036bd8  mov     r13, [rbp+arg_20]
0x180036bdc  lea     rax, [rcx-10h]
0x180036be0  mov     [rbp+arg_10], rax
0x180036be4  cmp     [rax+60h], rdi
0x180036be8  jnz     loc_180036C7B
0x180036bee  mov     rcx, [rcx+48h]
0x180036bf2  test    rcx, rcx
0x180036bf5  jnz     loc_180036F49
0x180036bfb  mov     rcx, [r14+40h]
0x180036bff  test    rcx, rcx
0x180036c02  jnz     loc_180036F49
0x180036c08  mov     rbx, [r14+38h]
0x180036c0c  test    rbx, rbx
0x180036c0f  jz      loc_180036CD6
0x180036c15  mov     rcx, cs:?FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER
0x180036c1c  mov     [rbp+ppURI], rdi
0x180036c20  test    rcx, rcx
0x180036c23  jnz     loc_180036EFF
0x180036c29  mov     eax, cs:dword_180159B48
0x180036c2f  test    eax, eax
0x180036c31  jnz     short loc_180036C5A
0x180036c33  mov     rax, [rbx]
0x180036c36  lea     r8, [rbp+ppURI]
0x180036c3a  lea     rdx, _GUID_c90db44a_1902_451e_bdf0_5c89660b528c
0x180036c41  mov     rcx, rbx
0x180036c44  mov     rax, [rax]
0x180036c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c4c  test    eax, eax
0x180036c4e  jnz     short loc_180036C5A
0x180036c50  cmp     [rbp+ppURI], rdi
0x180036c54  jnz     loc_180036E83
0x180036c5a  mov     rax, [rbx]
0x180036c5d  mov     r9, r12
0x180036c60  mov     r8, r15
0x180036c63  mov     [rsp+40h+var_20], r13
0x180036c68  mov     rdx, rsi
0x180036c6b  mov     rcx, rbx
0x180036c6e  mov     rax, [rax+30h]
0x180036c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c77  mov     edi, eax
0x180036c79  jmp     short loc_180036CC8
0x180036c7b  lea     r9, [rbp+ppURI]; ppURI
0x180036c7f  mov     [rbp+ppURI], rdi
0x180036c83  xor     r8d, r8d; dwReserved
0x180036c86  mov     edx, 3002B84h; dwFlags
0x180036c8b  mov     rcx, rsi; pwzURI
0x180036c8e  call    cs:__imp_CreateUri
0x180036c94  mov     edi, eax
0x180036c96  test    eax, eax
0x180036c98  js      short loc_180036CC8
0x180036c9a  mov     rcx, [r14+50h]
0x180036c9e  mov     r9, r12
0x180036ca1  mov     rbx, [rbp+ppURI]
0x180036ca5  mov     r8, r15
0x180036ca8  mov     rdx, rbx
0x180036cab  mov     rax, [rcx]
0x180036cae  mov     rax, [rax+28h]
0x180036cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036cb7  mov     edi, eax
0x180036cb9  mov     rcx, rbx
0x180036cbc  mov     rax, [rbx]
0x180036cbf  mov     rax, [rax+10h]
0x180036cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036cc8  cmp     edi, 800C0011h
0x180036cce  jnz     loc_180036E62
0x180036cd4  xor     edi, edi
0x180036cd6  mov     rbx, rdi
0x180036cd9  lea     rcx, ?g_mxsPermanentISM@@3VCMutexSem@@A; lpCriticalSection
0x180036ce0  mov     [rbp+ppURI], rbx
0x180036ce4  mov     edi, 1
0x180036ce9  call    cs:__imp_EnterCriticalSection
0x180036cef  cmp     cs:byte_18015E7D8, 0
0x180036cf6  jz      short loc_180036D20
0x180036cf8  mov     rdi, cs:qword_18015E7C8
0x180036cff  test    rdi, rdi
0x180036d02  jz      loc_180036F58
0x180036d08  mov     rax, [rdi]
0x180036d0b  mov     rcx, rdi
0x180036d0e  mov     rax, [rax+8]
0x180036d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d17  mov     rbx, rdi
0x180036d1a  xor     edi, edi
0x180036d1c  mov     [rbp+ppURI], rbx
0x180036d20  lea     rcx, ?g_mxsPermanentISM@@3VCMutexSem@@A; lpCriticalSection
0x180036d27  call    cs:__imp_LeaveCriticalSection
0x180036d2d  mov     r14d, [rbp+arg_28]
0x180036d31  cmp     edi, 1
0x180036d34  jnz     short loc_180036D88
0x180036d36  call    GetBrowserProcess
0x180036d3b  lea     ecx, [rax-0Fh]
0x180036d3e  test    ecx, 0FFFFFFF6h
0x180036d44  jnz     short loc_180036D4F
0x180036d46  cmp     eax, 18h
0x180036d49  jnz     loc_180036E0E
0x180036d4f  call    cs:__imp_GetWebPlatformSecurityManagerFactoryCallback
0x180036d55  test    rax, rax
0x180036d58  jz      loc_180036E0E
0x180036d5e  mov     rcx, rax
0x180036d61  call    GetAndRegisterWebPlatformPermanantSecurityManager
0x180036d66  mov     edi, eax
0x180036d68  test    eax, eax
0x180036d6a  jz      short loc_180036D79
0x180036d6c  test    eax, eax
0x180036d6e  js      loc_180036E06
0x180036d74  jmp     loc_180036E0E
0x180036d79  lea     rcx, [rbp+ppURI]
0x180036d7d  call    ObtainPermanentInternetSecurityManagerInternal
0x180036d82  mov     rbx, [rbp+ppURI]
0x180036d86  mov     edi, eax
0x180036d88  test    edi, edi
0x180036d8a  jnz     short loc_180036D6E
0x180036d8c  mov     rcx, cs:?FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER
0x180036d93  mov     [rbp+ppURI], 0
0x180036d9b  test    rcx, rcx
0x180036d9e  jnz     loc_180036ED4
0x180036da4  mov     eax, cs:dword_180159B48
0x180036daa  test    eax, eax
0x180036dac  jnz     short loc_180036DD8
0x180036dae  mov     rax, [rbx]
0x180036db1  lea     r8, [rbp+ppURI]
0x180036db5  lea     rdx, _GUID_c90db44a_1902_451e_bdf0_5c89660b528c
0x180036dbc  mov     rcx, rbx
0x180036dbf  mov     rax, [rax]
0x180036dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036dc7  test    eax, eax
0x180036dc9  jnz     short loc_180036DD8
0x180036dcb  mov     rcx, [rbp+ppURI]
0x180036dcf  test    rcx, rcx
0x180036dd2  jnz     loc_180036F62
0x180036dd8  mov     rax, [rbx]
0x180036ddb  mov     r9, r12
0x180036dde  mov     r8, r15
0x180036de1  mov     [rsp+40h+var_20], r13
0x180036de6  mov     rdx, rsi
0x180036de9  mov     rcx, rbx
0x180036dec  mov     rax, [rax+30h]
0x180036df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036df5  mov     edi, eax
0x180036df7  mov     rax, [rbx]
0x180036dfa  mov     rcx, rbx
0x180036dfd  mov     rax, [rax+10h]
0x180036e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e06  cmp     edi, 800C0011h
0x180036e0c  jnz     short loc_180036E62
0x180036e0e  lea     r9, [rbp+ppURI]; ppURI
0x180036e12  mov     [rbp+ppURI], 0
0x180036e1a  xor     r8d, r8d; dwReserved
0x180036e1d  mov     edx, 3002B84h; dwFlags
0x180036e22  mov     rcx, rsi; pwzURI
0x180036e25  call    cs:__imp_CreateUri
0x180036e2b  mov     edi, eax
0x180036e2d  test    eax, eax
0x180036e2f  js      short loc_180036E62
0x180036e31  mov     rbx, [rbp+ppURI]
0x180036e35  mov     r9, r12; unsigned int *
0x180036e38  mov     rcx, [rbp+arg_10]; this
0x180036e3c  mov     rdx, rbx; struct IUri *
0x180036e3f  mov     [rsp+40h+var_18], r14d; unsigned int
0x180036e44  mov     r8, r15; unsigned __int8 *
0x180036e47  mov     [rsp+40h+var_20], r13; unsigned __int64
0x180036e4c  call    ?GetSecurityIdEx2Internal@CSecurityManager@@AEAAJPEAUIUri@@PEAEPEAK_KK@Z; CSecurityManager::GetSecurityIdEx2Internal(IUri *,uchar *,ulong *,unsigned __int64,ulong)
0x180036e51  mov     edi, eax
0x180036e53  mov     rcx, rbx
0x180036e56  mov     rax, [rbx]
0x180036e59  mov     rax, [rax+10h]
0x180036e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e62  mov     eax, edi
0x180036e64  mov     rbx, [rsp+40h+arg_0]
0x180036e6c  add     rsp, 40h
0x180036e70  pop     r15
0x180036e72  pop     r14
0x180036e74  pop     r13
0x180036e76  pop     r12
0x180036e78  pop     rdi
0x180036e79  pop     rsi
0x180036e7a  pop     rbp
0x180036e7b  retn
0x180036e7c  mov     eax, 80070057h
0x180036e81  jmp     short loc_180036E64
0x180036e83  mov     rcx, cs:?FEATURE_DISABLE_IGNORE_ZONE_FOR_SECURITYID@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_IGNORE_ZONE_FOR_SECURITYID
0x180036e8a  test    rcx, rcx
0x180036e8d  jnz     loc_180036F24
0x180036e93  mov     eax, cs:dword_180159F88
0x180036e99  mov     edx, edi
0x180036e9b  test    eax, eax
0x180036e9d  jnz     short loc_180036EA4
0x180036e9f  mov     edx, 20000000h
0x180036ea4  mov     rcx, [rbp+ppURI]
0x180036ea8  mov     r9, r12
0x180036eab  mov     [rsp+40h+var_18], edx
0x180036eaf  mov     r8, r15
0x180036eb2  mov     rdx, rsi
0x180036eb5  mov     [rsp+40h+var_20], r13
0x180036eba  mov     rax, [rcx]
0x180036ebd  mov     rax, [rax+20h]
0x180036ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ec6  mov     rcx, [rbp+ppURI]
0x180036eca  mov     edi, eax
0x180036ecc  mov     rax, [rcx]
0x180036ecf  jmp     loc_180036CBF
0x180036ed4  call    cs:__imp_CoInternetIsFeatureEnabledInternal
0x180036eda  test    eax, eax
0x180036edc  js      loc_180036DAE
0x180036ee2  xor     ecx, ecx
0x180036ee4  test    eax, eax
0x180036ee6  setz    cl
0x180036ee9  mov     cs:dword_180159B48, ecx
0x180036eef  mov     cs:?FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER@FCK@@3VCFeatureControlKey@@A, 0; CFeatureControlKey FCK::FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER
0x180036efa  jmp     loc_180036DA4
0x180036eff  call    cs:__imp_CoInternetIsFeatureEnabledInternal
0x180036f05  test    eax, eax
0x180036f07  js      loc_180036C33
0x180036f0d  mov     ecx, edi
0x180036f0f  setz    cl
0x180036f12  mov     cs:dword_180159B48, ecx
0x180036f18  mov     cs:?FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER@FCK@@3VCFeatureControlKey@@A, rdi; CFeatureControlKey FCK::FEATURE_DISABLE_INTERNAL_SECURITY_MANAGER
0x180036f1f  jmp     loc_180036C29
0x180036f24  call    cs:__imp_CoInternetIsFeatureEnabledInternal
0x180036f2a  test    eax, eax
0x180036f2c  js      loc_180036E9F
0x180036f32  mov     ecx, edi
0x180036f34  setz    cl
0x180036f37  mov     cs:dword_180159F88, ecx
0x180036f3d  mov     cs:?FEATURE_DISABLE_IGNORE_ZONE_FOR_SECURITYID@FCK@@3VCFeatureControlKey@@A, rdi; CFeatureControlKey FCK::FEATURE_DISABLE_IGNORE_ZONE_FOR_SECURITYID
0x180036f44  jmp     loc_180036E93
0x180036f49  mov     [rsp+40h+var_20], r13
0x180036f4e  call    GetZoneAgnosticSecurityIdFromUrl
0x180036f53  jmp     loc_180036C77
0x180036f58  mov     edi, 8000FFFFh
0x180036f5d  jmp     loc_180036D20
0x180036f62  mov     rax, [rcx]
0x180036f65  mov     r9, r12
0x180036f68  mov     [rsp+40h+var_18], r14d
0x180036f6d  mov     r8, r15
0x180036f70  mov     rdx, rsi
0x180036f73  mov     [rsp+40h+var_20], r13
0x180036f78  mov     rax, [rax+20h]
0x180036f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f81  mov     rcx, [rbp+ppURI]
0x180036f85  mov     edi, eax
0x180036f87  mov     rax, [rcx]
0x180036f8a  mov     rax, [rax+10h]
0x180036f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f93  jmp     loc_180036DF7
```
