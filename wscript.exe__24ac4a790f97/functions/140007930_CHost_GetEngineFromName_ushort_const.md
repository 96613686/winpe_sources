# CHost::GetEngineFromName(ushort const *)

- ea: `0x140007930`
- end: `0x140007ac1`
- name: `?GetEngineFromName@CHost@@IEAAJPEBG@Z`
- size: `401`
- prototype: `__int64 __fastcall(CHost *__hidden this, LPCOLESTR lpsz)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000757c`

## callees

- `0x140007930`
- `0x140007f74`
- `0x140008854`
- `0x14000d298`
- `0x140014674`
- `0x140017536`
- `0x1400175a0`
- `0x140018010`

## import_xrefs

- `ole32!CLSIDFromString` at `0x1400079ce`
- `ole32!CLSIDFromString` at `0x1400079ce`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x140007a3e`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x140007a3e`

## pseudocode

```c
__int64 __fastcall CHost::GetEngineFromName(CHost *this, unsigned __int16 *lpsz)
{
  unsigned __int16 *v2; // rdi
  const WCHAR *LastWCharInStr; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 result; // rax
  int IsFeatureEnabledInternal; // eax
  const OLECHAR *v9; // [rsp+20h] [rbp-238h]
  CLSID pclsid; // [rsp+30h] [rbp-228h] BYREF
  unsigned __int16 v11[256]; // [rsp+40h] [rbp-218h] BYREF

  v2 = lpsz;
  if ( !lpsz )
  {
    LastWCharInStr = FindLastWCharInStr(*((const unsigned __int16 **)this + 77), 0x2Eu);
    if ( !LastWCharInStr )
    {
      v5 = (unsigned int)(Global::g_lResourceBase + 21);
      v9 = &Default;
      v6 = 3306;
      return (*(__int64 (__fastcall **)(CHost *, __int64, __int64, _QWORD, const OLECHAR *))(*(_QWORD *)this + 8LL))(
               this,
               v5,
               v6,
               *((_QWORD *)this + 76),
               v9);
    }
    result = mapExtToEngine(LastWCharInStr, v11);
    if ( (int)result < 0 )
      return result;
    v2 = v11;
  }
  pclsid = 0;
  if ( CLSIDFromString(v2, &pclsid) >= 0 )
  {
    if ( !memcmp_0(&pclsid, &CLSID_Chakra, 0x10u) )
      return (*(__int64 (__fastcall **)(CHost *, _QWORD, __int64, const OLECHAR *, const OLECHAR *))(*(_QWORD *)this + 8LL))(
               this,
               (unsigned int)(Global::g_lResourceBase + 20),
               3216,
               &Default,
               &Default);
    if ( !memcmp_0(&pclsid, &CLSID_VBScript, 0x10u) )
    {
      if ( !FCK::FEATURE_VBSCRIPT_DEPRECATION_TOAST )
        goto LABEL_15;
      IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
      if ( IsFeatureEnabledInternal >= 0 )
      {
        dword_1400201F8 = IsFeatureEnabledInternal == 0;
        FCK::FEATURE_VBSCRIPT_DEPRECATION_TOAST = 0;
LABEL_15:
        if ( dword_1400201F8 )
          SendVBScriptToastNotification();
      }
    }
  }
  if ( (int)CScriptingEngine::Create(v2, this, (struct CScriptingEngine **)this + 79) >= 0 )
    return 0;
  v6 = 3201;
  v5 = (unsigned int)(Global::g_lResourceBase + 20);
  v9 = v2;
  return (*(__int64 (__fastcall **)(CHost *, __int64, __int64, _QWORD, const OLECHAR *))(*(_QWORD *)this + 8LL))(
           this,
           v5,
           v6,
           *((_QWORD *)this + 76),
           v9);
}

```

## disassembly

```asm
0x140007930  mov     [rsp+arg_10], rbx
0x140007935  push    rdi
0x140007936  sub     rsp, 250h
0x14000793d  mov     rax, cs:__security_cookie
0x140007944  xor     rax, rsp
0x140007947  mov     [rsp+258h+var_18], rax
0x14000794f  mov     rdi, rdx
0x140007952  mov     rbx, rcx
0x140007955  test    rdx, rdx
0x140007958  jnz     short loc_1400079BE
0x14000795a  mov     rcx, [rcx+268h]; unsigned __int16 *
0x140007961  lea     edx, [rdi+2Eh]; unsigned __int16
0x140007964  call    ?FindLastWCharInStr@@YAPEBGPEBGG@Z; FindLastWCharInStr(ushort const *,ushort)
0x140007969  test    rax, rax
0x14000796c  jnz     short loc_1400079A4
0x14000796e  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x140007974  lea     r9, Default
0x14000797b  add     edx, 15h
0x14000797e  mov     [rsp+258h+var_238], r9
0x140007983  mov     r8d, 0CEAh
0x140007989  mov     r9, [rbx+260h]
0x140007990  mov     rax, [rbx]
0x140007993  mov     rcx, rbx
0x140007996  mov     rax, [rax+8]
0x14000799a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000799f  jmp     loc_140007AA0
0x1400079a4  lea     rdx, [rsp+258h+var_218]; unsigned __int16 *
0x1400079a9  mov     rcx, rax; lpWideCharStr
0x1400079ac  call    mapExtToEngine
0x1400079b1  test    eax, eax
0x1400079b3  js      loc_140007AA0
0x1400079b9  lea     rdi, [rsp+258h+var_218]
0x1400079be  xorps   xmm0, xmm0
0x1400079c1  lea     rdx, [rsp+258h+pclsid]; pclsid
0x1400079c6  mov     rcx, rdi; lpsz
0x1400079c9  movups  xmmword ptr [rsp+258h+pclsid.Data1], xmm0
0x1400079ce  call    cs:__imp_CLSIDFromString
0x1400079d4  test    eax, eax
0x1400079d6  js      loc_140007A6F
0x1400079dc  mov     r8d, 10h; Size
0x1400079e2  lea     rdx, CLSID_Chakra; Buf2
0x1400079e9  lea     rcx, [rsp+258h+pclsid]; Buf1
0x1400079ee  call    memcmp_0
0x1400079f3  test    eax, eax
0x1400079f5  jnz     short loc_140007A17
0x1400079f7  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x1400079fd  lea     r9, Default
0x140007a04  add     edx, 14h
0x140007a07  mov     [rsp+258h+var_238], r9
0x140007a0c  mov     r8d, 0C90h
0x140007a12  jmp     loc_140007990
0x140007a17  mov     r8d, 10h; Size
0x140007a1d  lea     rdx, CLSID_VBScript; Buf2
0x140007a24  lea     rcx, [rsp+258h+pclsid]; Buf1
0x140007a29  call    memcmp_0
0x140007a2e  test    eax, eax
0x140007a30  jnz     short loc_140007A6F
0x140007a32  mov     rcx, cs:?FEATURE_VBSCRIPT_DEPRECATION_TOAST@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_VBSCRIPT_DEPRECATION_TOAST
0x140007a39  test    rcx, rcx
0x140007a3c  jz      short loc_140007A60
0x140007a3e  call    cs:__imp_CoInternetIsFeatureEnabledInternal
0x140007a44  test    eax, eax
0x140007a46  js      short loc_140007A6F
0x140007a48  xor     ecx, ecx
0x140007a4a  test    eax, eax
0x140007a4c  setz    cl
0x140007a4f  mov     cs:dword_1400201F8, ecx
0x140007a55  mov     cs:?FEATURE_VBSCRIPT_DEPRECATION_TOAST@FCK@@3VCFeatureControlKey@@A, 0; CFeatureControlKey FCK::FEATURE_VBSCRIPT_DEPRECATION_TOAST
0x140007a60  mov     eax, cs:dword_1400201F8
0x140007a66  test    eax, eax
0x140007a68  jz      short loc_140007A6F
0x140007a6a  call    SendVBScriptToastNotification
0x140007a6f  lea     r8, [rbx+278h]; struct CScriptingEngine **
0x140007a76  mov     rdx, rbx; struct CHost *
0x140007a79  mov     rcx, rdi; lpsz
0x140007a7c  call    ?Create@CScriptingEngine@@SAJPEBGPEAVCHost@@PEAPEAV1@@Z; CScriptingEngine::Create(ushort const *,CHost *,CScriptingEngine * *)
0x140007a81  test    eax, eax
0x140007a83  jns     short loc_140007A9E
0x140007a85  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x140007a8b  mov     r8d, 0C81h
0x140007a91  add     edx, 14h
0x140007a94  mov     [rsp+258h+var_238], rdi
0x140007a99  jmp     loc_140007989
0x140007a9e  xor     eax, eax
0x140007aa0  mov     rcx, [rsp+258h+var_18]
0x140007aa8  xor     rcx, rsp; StackCookie
0x140007aab  call    __security_check_cookie
0x140007ab0  mov     rbx, [rsp+258h+arg_10]
0x140007ab8  add     rsp, 250h
0x140007abf  pop     rdi
0x140007ac0  retn
```
