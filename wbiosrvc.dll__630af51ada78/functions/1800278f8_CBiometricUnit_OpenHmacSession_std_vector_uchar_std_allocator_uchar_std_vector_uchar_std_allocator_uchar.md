# CBiometricUnit::OpenHmacSession(std::vector<uchar,std::allocator<uchar>> *,std::vector<uchar,std::allocator<uchar>> *)

- ea: `0x1800278f8`
- end: `0x180027af0`
- name: `?OpenHmacSession@CBiometricUnit@@QEAAJPEAV?$vector@EV?$allocator@E@std@@@std@@0@Z`
- size: `504`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007978`
- `0x18004ac70`

## callees

- `0x1800278f8`
- `0x180027af8`
- `0x180027b50`
- `0x180046aa8`
- `0x18005388c`
- `0x1800538b0`
- `0x180057b58`
- `0x180058ec0`
- `0x1800601a8`
- `0x180063c6c`
- `0x180069cc8`
- `0x180072da0`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x180027aa9`
- `bcrypt!BCryptGenRandom` at `0x180027aa9`

## string_xrefs

- `0x1800279ba`: `onecore\ds\security\biometrics\service\server\biometricunit.cpp`
- `0x1800279e5`: `onecore\ds\security\biometrics\service\server\biometricunit.cpp`
- `0x180027abb`: `onecore\ds\security\biometrics\service\server\biometricunit.cpp`
- `0x18002793c`: `onecore\ds\security\biometrics\service\server\AuthValue.h`
- `0x180027971`: `onecore\ds\security\biometrics\service\server\AuthValue.h`

## pseudocode

```c
int __fastcall CBiometricUnit::OpenHmacSession(__int64 a1, _QWORD *a2, __int64 a3, const char *a4)
{
  AuthValue *v6; // rcx
  AuthValue *v7; // rcx
  AuthValue *v8; // rcx
  __int64 v9; // r9
  __int64 v10; // r11
  __int64 v11; // r8
  __int64 v12; // r9
  TpmHmacKey *v13; // rcx
  int result; // eax
  int v15; // eax
  int v16; // edi
  __int64 v17; // rax
  _QWORD *v18; // rax
  __int64 v19; // rbx
  PUCHAR v20; // rdx
  __int64 v21; // r14
  unsigned __int64 v22; // rcx
  PUCHAR v23; // rax
  unsigned __int64 v24; // rdi
  NTSTATUS v25; // eax
  int v26; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  try
  {
    v6 = *(AuthValue **)(a1 + 2872);
    if ( v6 && AuthValue::Provisioned(v6) )
    {
      if ( !AuthValue::Provisioned(v7) )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x92,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\AuthValue.h",
          (const char *)0x8007139FLL,
          v26);
      if ( *((_QWORD *)v8 + 8) != *((_QWORD *)v8 + 9) )
      {
        if ( !AuthValue::Provisioned(v8) )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x6A,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\AuthValue.h",
            (const char *)0x8007139FLL,
            v26);
        std::vector<unsigned char>::operator=(v10, v9);
      }
      if ( AuthValue::HeldInTpm(*(AuthValue **)(a1 + 2872)) )
      {
        v13 = *(TpmHmacKey **)(a1 + 2888);
        if ( !v13 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x37C,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biometricunit.cpp",
            (const char *)0x80004003LL,
            v26);
          return -2147467261;
        }
        v15 = TpmHmacKey::OpenSession(v13);
        v16 = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x37D,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biometricunit.cpp",
            (const char *)(unsigned int)v15,
            v26);
          return v16;
        }
        v17 = *(_QWORD *)(a1 + 2896);
        if ( v17 != *(_QWORD *)(a1 + 2904) )
          *(_QWORD *)(a1 + 2904) = v17;
        v18 = (_QWORD *)TpmHmacKey::NonceTpm(*(_QWORD *)(a1 + 2888));
        if ( a2 != v18 )
          std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(a2, *v18, v18[1] - *v18);
        return 0;
      }
      v19 = a1 + 2896;
      v20 = *(PUCHAR *)v19;
      v21 = *(_QWORD *)(v19 + 8);
      v22 = v21 - *(_QWORD *)v19;
      if ( v22 > 0x20 )
      {
        v23 = v20 + 32;
LABEL_25:
        *(_QWORD *)(v19 + 8) = v23;
        goto LABEL_26;
      }
      if ( v22 < 0x20 )
      {
        if ( *(_QWORD *)(v19 + 16) - (_QWORD)v20 >= 0x20u )
        {
          v24 = 32 - v22;
          memset_0(*(void **)(v19 + 8), 0, 32 - v22);
          v23 = (PUCHAR)(v24 + v21);
          goto LABEL_25;
        }
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v19, 32, v11, v12);
      }
LABEL_26:
      v25 = BCryptGenRandom(0, *(PUCHAR *)v19, *(_DWORD *)(v19 + 8) - *(_DWORD *)v19, 2u);
      if ( v25 < 0 )
        return wil::details::in1diag3::Return_NtStatus(
                 retaddr,
                 (void *)0x389,
                 (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biometricunit.cpp",
                 (const char *)(unsigned int)v25,
                 v26);
      std::vector<unsigned char>::operator=(a2, v19);
      return 0;
    }
    result = 0;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x38F,
             (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biometricunit.cpp",
             a4);
  }
  return result;
}

```

## disassembly

```asm
0x1800278f8  push    rbx
0x1800278fa  push    rsi
0x1800278fb  push    rdi
0x1800278fc  push    r14
0x1800278fe  sub     rsp, 28h
0x180027902  mov     r11, r8
0x180027905  mov     rsi, rdx
0x180027908  mov     rbx, rcx
0x18002790b  mov     rcx, [rcx+0B38h]; this
0x180027912  test    rcx, rcx
0x180027915  jz      loc_180027ADD
0x18002791b  call    ?Provisioned@AuthValue@@QEBA_NXZ; AuthValue::Provisioned(void)
0x180027920  test    al, al
0x180027922  jz      loc_180027ADD
0x180027928  call    ?Provisioned@AuthValue@@QEBA_NXZ; AuthValue::Provisioned(void)
0x18002792d  mov     r10, [rsp+48h]
0x180027932  test    al, al
0x180027934  jnz     short loc_180027950
0x180027936  mov     r9d, 8007139Fh; char *
0x18002793c  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\biometrics\\serv"...
0x180027943  mov     edx, 92h; void *
0x180027948  mov     rcx, r10; this
0x18002794b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180027950  lea     r9, [rcx+40h]
0x180027954  mov     rax, [r9+8]
0x180027958  cmp     [r9], rax
0x18002795b  jz      short loc_18002798D
0x18002795d  call    ?Provisioned@AuthValue@@QEBA_NXZ; AuthValue::Provisioned(void)
0x180027962  mov     rcx, [rsp+48h]; this
0x180027967  test    al, al
0x180027969  jnz     short loc_180027982
0x18002796b  mov     r9d, 8007139Fh; char *
0x180027971  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\biometrics\\serv"...
0x180027978  mov     edx, 6Ah ; 'j'; void *
0x18002797d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180027982  mov     rdx, r9
0x180027985  mov     rcx, r11
0x180027988  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x18002798d  mov     rcx, [rbx+0B38h]; this
0x180027994  call    ?HeldInTpm@AuthValue@@QEBA_NXZ; AuthValue::HeldInTpm(void)
0x180027999  test    al, al
0x18002799b  jz      loc_180027A40
0x1800279a1  mov     rcx, [rbx+0B48h]; this
0x1800279a8  test    rcx, rcx
0x1800279ab  jnz     short loc_1800279D2
0x1800279ad  mov     rcx, [rsp+48h]; this
0x1800279b2  mov     ebx, 80004003h
0x1800279b7  mov     r9d, ebx; char *
0x1800279ba  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\biometrics\\serv"...
0x1800279c1  mov     edx, 37Ch; void *
0x1800279c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800279cb  mov     eax, ebx
0x1800279cd  jmp     loc_180027AE5
0x1800279d2  call    ?OpenSession@TpmHmacKey@@QEAAJXZ; TpmHmacKey::OpenSession(void)
0x1800279d7  mov     edi, eax
0x1800279d9  test    eax, eax
0x1800279db  jns     short loc_1800279FD
0x1800279dd  mov     rcx, [rsp+48h]; this
0x1800279e2  mov     r9d, eax; char *
0x1800279e5  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\biometrics\\serv"...
0x1800279ec  mov     edx, 37Dh; void *
0x1800279f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800279f6  mov     eax, edi
0x1800279f8  jmp     loc_180027AE5
0x1800279fd  mov     rax, [rbx+0B50h]
0x180027a04  cmp     rax, [rbx+0B58h]
0x180027a0b  jz      short loc_180027A14
0x180027a0d  mov     [rbx+0B58h], rax
0x180027a14  mov     rcx, [rbx+0B48h]
0x180027a1b  call    ?NonceTpm@TpmHmacKey@@QEBAAEBV?$vector@EV?$allocator@E@std@@@std@@XZ; TpmHmacKey::NonceTpm(void)
0x180027a20  cmp     rsi, rax
0x180027a23  jz      loc_180027AD9
0x180027a29  mov     r8, [rax+8]
0x180027a2d  sub     r8, [rax]
0x180027a30  mov     rdx, [rax]
0x180027a33  mov     rcx, rsi
0x180027a36  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x180027a3b  jmp     loc_180027AD9
0x180027a40  add     rbx, 0B50h
0x180027a47  mov     rdx, [rbx]
0x180027a4a  mov     r14, [rbx+8]
0x180027a4e  mov     rcx, r14
0x180027a51  sub     rcx, rdx
0x180027a54  mov     edi, 20h ; ' '
0x180027a59  cmp     rcx, rdi
0x180027a5c  jbe     short loc_180027A64
0x180027a5e  lea     rax, [rdx+20h]
0x180027a62  jmp     short loc_180027A93
0x180027a64  jnb     short loc_180027A97
0x180027a66  mov     rax, [rbx+10h]
0x180027a6a  sub     rax, rdx
0x180027a6d  cmp     rax, rdi
0x180027a70  jnb     short loc_180027A7F
0x180027a72  mov     rdx, rdi
0x180027a75  mov     rcx, rbx
0x180027a78  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180027a7d  jmp     short loc_180027A97
0x180027a7f  sub     rdi, rcx
0x180027a82  mov     r8, rdi; Size
0x180027a85  xor     edx, edx; Val
0x180027a87  mov     rcx, r14; void *
0x180027a8a  call    memset_0
0x180027a8f  lea     rax, [rdi+r14]
0x180027a93  mov     [rbx+8], rax
0x180027a97  mov     r8d, [rbx+8]
0x180027a9b  sub     r8d, [rbx]; cbBuffer
0x180027a9e  mov     r9d, 2; dwFlags
0x180027aa4  mov     rdx, [rbx]; pbBuffer
0x180027aa7  xor     ecx, ecx; hAlgorithm
0x180027aa9  call    cs:__imp_BCryptGenRandom
0x180027aaf  test    eax, eax
0x180027ab1  jns     short loc_180027ACE
0x180027ab3  mov     rcx, [rsp+48h]; this
0x180027ab8  mov     r9d, eax; char *
0x180027abb  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\biometrics\\serv"...
0x180027ac2  mov     edx, 389h; void *
0x180027ac7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180027acc  jmp     short loc_180027AE5
0x180027ace  mov     rdx, rbx
0x180027ad1  mov     rcx, rsi
0x180027ad4  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x180027ad9  xor     eax, eax
0x180027adb  jmp     short loc_180027AE5
0x180027add  xor     eax, eax
0x180027adf  jmp     short loc_180027AE5
0x180027ae1  mov     eax, [rsp+48h+arg_0]
0x180027ae5  add     rsp, 28h
0x180027ae9  pop     r14
0x180027aeb  pop     rdi
0x180027aec  pop     rsi
0x180027aed  pop     rbx
0x180027aee  retn
```
