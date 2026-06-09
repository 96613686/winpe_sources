# CBiometricUnit::OpenHmacKey(void)

- ea: `0x180026288`
- end: `0x18002648c`
- name: `?OpenHmacKey@CBiometricUnit@@QEAAJXZ`
- size: `516`
- prototype: `int(CBiometricUnit *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180046b70`
- `0x180049970`

## callees

- `0x180026288`
- `0x180026494`
- `0x180027af8`
- `0x18003878c`
- `0x18003f2dc`
- `0x1800533f8`
- `0x18005388c`
- `0x180058ec0`
- `0x180061ee0`
- `0x1800787a0`
- `0x18007a62c`

## import_xrefs

- `ngcutils!NgcSetBioProtectorUpdateNeeded` at `0x1800263e3`
- `ngcutils!NgcSetBioProtectorUpdateNeeded` at `0x180026459`
- `ngcutils!NgcSetBioProtectorUpdateNeeded` at `0x1800263e3`
- `ngcutils!NgcSetBioProtectorUpdateNeeded` at `0x180026459`

## string_xrefs

- `0x1800262b7`: `onecore\ds\security\biometrics\service\server\biometricunit.cpp`
- `0x180026332`: `onecore\ds\security\biometrics\service\server\biometricunit.cpp`
- `0x180026374`: `onecore\ds\security\biometrics\service\server\biometricunit.cpp`
- `0x1800263bb`: `onecore\ds\security\biometrics\service\server\biometricunit.cpp`
- `0x180026407`: `onecore\ds\security\biometrics\service\server\biometricunit.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBiometricUnit::OpenHmacKey(AuthValue **this, __int64 a2, __int64 a3, const char *a4)
{
  int v5; // eax
  unsigned int v6; // edi
  __int64 result; // rax
  AuthValue *v8; // rcx
  AuthValue *v9; // rcx
  __int64 *v10; // rsi
  int v11; // eax
  int v12; // edi
  int v13; // eax
  unsigned int v14; // edi
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v19; // [rsp+30h] [rbp+8h] BYREF

  try
  {
    if ( !this[359] )
    {
      v5 = CBiometricUnit::ProvisionAuthValue((CBiometricUnit *)this);
      v6 = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x341,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biometricunit.cpp",
          (const char *)(unsigned int)v5,
          v17);
        return v6;
      }
    }
    v8 = this[359];
    if ( !v8 )
      return 0;
    if ( !AuthValue::Provisioned(v8) )
      return 0;
    if ( !AuthValue::HeldInTpm(v9) )
      return 0;
    v10 = (__int64 *)(this + 361);
    if ( this[361] )
      return 0;
    v19 = 0;
    v11 = AuthValue::OpenTpmHmacKey(this[359], &v19);
    v12 = v11;
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x34C,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biometricunit.cpp",
        (const char *)(unsigned int)v11,
        v17);
    if ( v12 == -2146893802 )
    {
      v13 = AuthValue::Provision(this[359], (struct _WINBIO_PIPELINE *)((char *)this[338] + 16));
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x351,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biometricunit.cpp",
          (const char *)(unsigned int)v13,
          v17);
        if ( v19 )
          std::default_delete<TpmHmacKey>::operator()();
        return v14;
      }
      v15 = AuthValue::OpenTpmHmacKey(this[359], &v19);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x352,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biometricunit.cpp",
          (const char *)(unsigned int)v15,
          v17);
        if ( v19 )
          std::default_delete<TpmHmacKey>::operator()();
        return v16;
      }
      NgcSetBioProtectorUpdateNeeded();
      goto LABEL_27;
    }
    if ( v12 == -2146893771 || v12 == -2146893776 )
    {
      AuthValue::DeleteKeys(this[359]);
      NgcSetBioProtectorUpdateNeeded();
      if ( v19 )
        std::default_delete<TpmHmacKey>::operator()();
      result = 0;
    }
    else
    {
      if ( v12 >= 0 )
      {
LABEL_27:
        std::unique_ptr<TpmHmacKey>::operator=<std::default_delete<TpmHmacKey>,0>(v10, &v19);
        if ( v19 )
          std::default_delete<TpmHmacKey>::operator()();
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35F,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biometricunit.cpp",
        (const char *)(unsigned int)v12,
        v17);
      if ( v19 )
        std::default_delete<TpmHmacKey>::operator()();
      result = (unsigned int)v12;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x366,
                           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biometricunit.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x180026288  mov     [rsp+arg_8], rbx
0x18002628d  mov     [rsp+arg_10], rsi
0x180026292  push    rdi; int
0x180026293  sub     rsp, 20h
0x180026297  mov     rbx, rcx
0x18002629a  cmp     qword ptr [rcx+0B38h], 0
0x1800262a2  jnz     short loc_1800262CF
0x1800262a4  call    ?ProvisionAuthValue@CBiometricUnit@@QEAAJXZ; CBiometricUnit::ProvisionAuthValue(void)
0x1800262a9  mov     edi, eax
0x1800262ab  test    eax, eax
0x1800262ad  jns     short loc_1800262CF
0x1800262af  mov     rcx, [rsp+28h]; this
0x1800262b4  mov     r9d, eax; char *
0x1800262b7  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\biometrics\\serv"...
0x1800262be  mov     edx, 341h; void *
0x1800262c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800262c8  mov     eax, edi
0x1800262ca  jmp     loc_18002647B
0x1800262cf  mov     rcx, [rbx+0B38h]; this
0x1800262d6  test    rcx, rcx
0x1800262d9  jz      loc_180026473
0x1800262df  call    ?Provisioned@AuthValue@@QEBA_NXZ; AuthValue::Provisioned(void)
0x1800262e4  test    al, al
0x1800262e6  jz      loc_180026473
0x1800262ec  call    ?HeldInTpm@AuthValue@@QEBA_NXZ; AuthValue::HeldInTpm(void)
0x1800262f1  test    al, al
0x1800262f3  jz      loc_180026473
0x1800262f9  lea     rsi, [rbx+0B48h]
0x180026300  cmp     qword ptr [rsi], 0
0x180026304  jnz     loc_180026473
0x18002630a  mov     [rsp+28h+arg_0], 0
0x180026313  lea     rdx, [rsp+28h+arg_0]
0x180026318  mov     rcx, [rbx+0B38h]
0x18002631f  call    ?OpenTpmHmacKey@AuthValue@@QEBAJPEAV?$unique_ptr@VTpmHmacKey@@U?$default_delete@VTpmHmacKey@@@std@@@std@@@Z; AuthValue::OpenTpmHmacKey(std::unique_ptr<TpmHmacKey> *)
0x180026324  mov     edi, eax
0x180026326  mov     rcx, [rsp+28h]; this
0x18002632b  test    eax, eax
0x18002632d  jns     short loc_180026343
0x18002632f  mov     r9d, eax; char *
0x180026332  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\biometrics\\serv"...
0x180026339  mov     edx, 34Ch; void *
0x18002633e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026343  cmp     edi, 80090016h
0x180026349  jnz     loc_1800263EB
0x18002634f  mov     rdx, [rbx+0A90h]
0x180026356  add     rdx, 10h; struct _WINBIO_PIPELINE *
0x18002635a  mov     rcx, [rbx+0B38h]; this
0x180026361  call    ?Provision@AuthValue@@QEAAJPEAU_WINBIO_PIPELINE@@@Z; AuthValue::Provision(_WINBIO_PIPELINE *)
0x180026366  mov     edi, eax
0x180026368  test    eax, eax
0x18002636a  jns     short loc_18002639C
0x18002636c  mov     rcx, [rsp+28h]; this
0x180026371  mov     r9d, eax; char *
0x180026374  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\biometrics\\serv"...
0x18002637b  mov     edx, 351h; void *
0x180026380  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026385  nop
0x180026386  mov     rdx, [rsp+28h+arg_0]
0x18002638b  test    rdx, rdx
0x18002638e  jz      short loc_180026395
0x180026390  call    ??R?$default_delete@VTpmHmacKey@@@std@@QEBAXPEAVTpmHmacKey@@@Z; std::default_delete<TpmHmacKey>::operator()(TpmHmacKey *)
0x180026395  mov     eax, edi
0x180026397  jmp     loc_18002647B
0x18002639c  lea     rdx, [rsp+28h+arg_0]
0x1800263a1  mov     rcx, [rbx+0B38h]
0x1800263a8  call    ?OpenTpmHmacKey@AuthValue@@QEBAJPEAV?$unique_ptr@VTpmHmacKey@@U?$default_delete@VTpmHmacKey@@@std@@@std@@@Z; AuthValue::OpenTpmHmacKey(std::unique_ptr<TpmHmacKey> *)
0x1800263ad  mov     ebx, eax
0x1800263af  test    eax, eax
0x1800263b1  jns     short loc_1800263E3
0x1800263b3  mov     rcx, [rsp+28h]; this
0x1800263b8  mov     r9d, eax; char *
0x1800263bb  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\biometrics\\serv"...
0x1800263c2  mov     edx, 352h; void *
0x1800263c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800263cc  nop
0x1800263cd  mov     rdx, [rsp+28h+arg_0]
0x1800263d2  test    rdx, rdx
0x1800263d5  jz      short loc_1800263DC
0x1800263d7  call    ??R?$default_delete@VTpmHmacKey@@@std@@QEBAXPEAVTpmHmacKey@@@Z; std::default_delete<TpmHmacKey>::operator()(TpmHmacKey *)
0x1800263dc  mov     eax, ebx
0x1800263de  jmp     loc_18002647B
0x1800263e3  call    cs:__imp_NgcSetBioProtectorUpdateNeeded
0x1800263e9  jmp     short loc_18002642C
0x1800263eb  cmp     edi, 80090035h
0x1800263f1  jz      short loc_18002644D
0x1800263f3  cmp     edi, 80090030h
0x1800263f9  jz      short loc_18002644D
0x1800263fb  test    edi, edi
0x1800263fd  jns     short loc_18002642C
0x1800263ff  mov     rcx, [rsp+28h]; this
0x180026404  mov     r9d, edi; char *
0x180026407  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\biometrics\\serv"...
0x18002640e  mov     edx, 35Fh; void *
0x180026413  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026418  nop
0x180026419  mov     rdx, [rsp+28h+arg_0]
0x18002641e  test    rdx, rdx
0x180026421  jz      short loc_180026428
0x180026423  call    ??R?$default_delete@VTpmHmacKey@@@std@@QEBAXPEAVTpmHmacKey@@@Z; std::default_delete<TpmHmacKey>::operator()(TpmHmacKey *)
0x180026428  mov     eax, edi
0x18002642a  jmp     short loc_18002647B
0x18002642c  lea     rdx, [rsp+28h+arg_0]
0x180026431  mov     rcx, rsi
0x180026434  call    ??$?4U?$default_delete@VTpmHmacKey@@@std@@$0A@@?$unique_ptr@VTpmHmacKey@@U?$default_delete@VTpmHmacKey@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<TpmHmacKey>::operator=<std::default_delete<TpmHmacKey>,0>(std::unique_ptr<TpmHmacKey> &&)
0x180026439  nop
0x18002643a  mov     rdx, [rsp+28h+arg_0]
0x18002643f  test    rdx, rdx
0x180026442  jz      short loc_180026449
0x180026444  call    ??R?$default_delete@VTpmHmacKey@@@std@@QEBAXPEAVTpmHmacKey@@@Z; std::default_delete<TpmHmacKey>::operator()(TpmHmacKey *)
0x180026449  xor     eax, eax
0x18002644b  jmp     short loc_18002647B
0x18002644d  mov     rcx, [rbx+0B38h]; this
0x180026454  call    ?DeleteKeys@AuthValue@@QEAAJXZ; AuthValue::DeleteKeys(void)
0x180026459  call    cs:__imp_NgcSetBioProtectorUpdateNeeded
0x18002645f  nop
0x180026460  mov     rdx, [rsp+28h+arg_0]
0x180026465  test    rdx, rdx
0x180026468  jz      short loc_18002646F
0x18002646a  call    ??R?$default_delete@VTpmHmacKey@@@std@@QEBAXPEAVTpmHmacKey@@@Z; std::default_delete<TpmHmacKey>::operator()(TpmHmacKey *)
0x18002646f  xor     eax, eax
0x180026471  jmp     short loc_18002647B
0x180026473  xor     eax, eax
0x180026475  jmp     short loc_18002647B
0x180026477  mov     eax, dword ptr [rsp+28h+arg_0]
0x18002647b  mov     rbx, [rsp+28h+arg_8]
0x180026480  mov     rsi, [rsp+28h+arg_10]
0x180026485  add     rsp, 20h
0x180026489  pop     rdi
0x18002648a  retn
```
