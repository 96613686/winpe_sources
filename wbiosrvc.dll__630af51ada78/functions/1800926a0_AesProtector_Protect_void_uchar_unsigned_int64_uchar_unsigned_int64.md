# AesProtector::Protect(void *,uchar *,unsigned __int64,uchar * *,unsigned __int64 *)

- ea: `0x1800926a0`
- end: `0x180092814`
- name: `?Protect@AesProtector@@UEAAJPEAXPEAE_KPEAPEAEPEA_K@Z`
- size: `372`
- prototype: `__int64 __usercall@<rax>(AesProtector *__hidden this@<rcx>, void *@<rdx>, unsigned __int8 *@<r8>, unsigned __int64@<r9>, unsigned __int8 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180054e00`

## callees

- `0x18002da38`
- `0x18003876c`
- `0x18003d460`
- `0x180060dc8`
- `0x1800920f4`
- `0x18009232c`
- `0x1800926a0`
- `0x180092880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009275b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009275b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180092723`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180092723`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800926dd`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800926dd`
- `bcrypt!BCryptDestroyKey` at `0x1800927f4`
- `bcrypt!BCryptDestroyKey` at `0x1800927f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AesProtector::Protect(
        RTL_SRWLOCK *this,
        void *a2,
        unsigned __int8 *a3,
        size_t a4,
        unsigned __int8 **a5,
        unsigned __int64 *a6)
{
  __int64 v10; // rcx
  unsigned __int8 **v11; // r15
  unsigned __int64 *v12; // r12
  AesProtector *v13; // rcx
  int v14; // ebx
  AesProtector *v15; // rcx
  int v16; // eax
  AesProtector *v17; // rcx
  BCRYPT_KEY_HANDLE v18; // rdi
  BCRYPT_KEY_HANDLE hKey; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int8 *v21; // [rsp+90h] [rbp+50h]

  v21 = a3;
  hKey = 0;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  if ( !IsValidSid(a2) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10);
  v11 = a5;
  if ( !a5 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10);
  v12 = a6;
  if ( !a6 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10);
  AcquireSRWLockShared(this + 1);
  a5 = (unsigned __int8 **)&this[1];
  v14 = AesProtector::LoadKey(v13, a2, this[2].Ptr, &hKey);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&a5);
  if ( v14 >= 0 )
  {
    v18 = hKey;
LABEL_24:
    v14 = AesProtector::EncryptData((AesProtector *)this, v18, a2, v21, a4, v11, v12);
    goto LABEL_25;
  }
  if ( v14 != -2147023728 )
    return (unsigned int)v14;
  AcquireSRWLockExclusive(this + 1);
  a5 = (unsigned __int8 **)&this[1];
  v16 = AesProtector::LoadKey(v15, a2, this[2].Ptr, &hKey);
  v14 = v16;
  if ( v16 >= 0 )
    goto LABEL_20;
  if ( v16 != -2147023728 )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&a5);
    return (unsigned int)v14;
  }
  v14 = AesProtector::CreateKey((AesProtector *)this, &hKey);
  if ( v14 < 0 )
  {
LABEL_20:
    v18 = hKey;
  }
  else
  {
    v18 = hKey;
    v14 = AesProtector::StoreKey(v17, a2, hKey);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&a5);
  if ( v14 >= 0 )
    goto LABEL_24;
LABEL_25:
  if ( v18 )
    BCryptDestroyKey(v18);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800926a0  mov     [rsp-38h+arg_8], rbx
0x1800926a5  mov     [rsp-38h+arg_10], r8
0x1800926aa  push    rbp
0x1800926ab  push    rsi
0x1800926ac  push    rdi
0x1800926ad  push    r12
0x1800926af  push    r13
0x1800926b1  push    r14
0x1800926b3  push    r15
0x1800926b5  mov     rbp, rsp
0x1800926b8  sub     rsp, 40h
0x1800926bc  mov     r13, r9
0x1800926bf  mov     rbx, r8
0x1800926c2  mov     rsi, rdx
0x1800926c5  mov     r14, rcx
0x1800926c8  mov     [rbp+hKey], 0
0x1800926d0  test    rdx, rdx
0x1800926d3  jnz     short loc_1800926DA
0x1800926d5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800926da  mov     rcx, rsi; pSid
0x1800926dd  call    cs:__imp_IsValidSid
0x1800926e3  test    eax, eax
0x1800926e5  jnz     short loc_1800926EC
0x1800926e7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800926ec  test    rbx, rbx
0x1800926ef  jnz     short loc_1800926F6
0x1800926f1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800926f6  test    r13, r13
0x1800926f9  jnz     short loc_180092700
0x1800926fb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180092700  mov     r15, [rbp+arg_20]
0x180092704  test    r15, r15
0x180092707  jnz     short loc_18009270E
0x180092709  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009270e  mov     r12, [rbp+arg_28]
0x180092712  test    r12, r12
0x180092715  jnz     short loc_18009271C
0x180092717  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009271c  lea     rdi, [r14+8]
0x180092720  mov     rcx, rdi; SRWLock
0x180092723  call    cs:__imp_AcquireSRWLockShared
0x180092729  mov     [rbp+arg_20], rdi
0x18009272d  lea     r9, [rbp+hKey]; void **
0x180092731  mov     r8, [r14+10h]; void *
0x180092735  mov     rdx, rsi; void *
0x180092738  call    ?LoadKey@AesProtector@@AEAAJPEAX0PEAPEAX@Z; AesProtector::LoadKey(void *,void *,void * *)
0x18009273d  mov     ebx, eax
0x18009273f  lea     rcx, [rbp+arg_20]
0x180092743  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180092748  test    ebx, ebx
0x18009274a  jns     short loc_1800927C5
0x18009274c  cmp     ebx, 80070490h
0x180092752  jnz     loc_1800927FA
0x180092758  mov     rcx, rdi; SRWLock
0x18009275b  call    cs:__imp_AcquireSRWLockExclusive
0x180092761  mov     [rbp+arg_20], rdi
0x180092765  lea     r9, [rbp+hKey]; void **
0x180092769  mov     r8, [r14+10h]; void *
0x18009276d  mov     rdx, rsi; void *
0x180092770  call    ?LoadKey@AesProtector@@AEAAJPEAX0PEAPEAX@Z; AesProtector::LoadKey(void *,void *,void * *)
0x180092775  mov     ebx, eax
0x180092777  test    eax, eax
0x180092779  jns     short loc_1800927B2
0x18009277b  cmp     eax, 80070490h
0x180092780  jz      short loc_18009278D
0x180092782  lea     rcx, [rbp+arg_20]
0x180092786  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18009278b  jmp     short loc_1800927FA
0x18009278d  lea     rdx, [rbp+hKey]; void **
0x180092791  mov     rcx, r14; this
0x180092794  call    ?CreateKey@AesProtector@@AEAAJPEAPEAX@Z; AesProtector::CreateKey(void * *)
0x180092799  mov     ebx, eax
0x18009279b  test    eax, eax
0x18009279d  js      short loc_1800927B2
0x18009279f  mov     rdi, [rbp+hKey]
0x1800927a3  mov     r8, rdi; void *
0x1800927a6  mov     rdx, rsi; void *
0x1800927a9  call    ?StoreKey@AesProtector@@AEAAJPEAX0@Z; AesProtector::StoreKey(void *,void *)
0x1800927ae  mov     ebx, eax
0x1800927b0  jmp     short loc_1800927B6
0x1800927b2  mov     rdi, [rbp+hKey]
0x1800927b6  lea     rcx, [rbp+arg_20]
0x1800927ba  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800927bf  test    ebx, ebx
0x1800927c1  js      short loc_1800927EC
0x1800927c3  jmp     short loc_1800927C9
0x1800927c5  mov     rdi, [rbp+hKey]
0x1800927c9  mov     [rsp+40h+var_10], r12; unsigned __int64 *
0x1800927ce  mov     [rsp+40h+var_18], r15; unsigned __int8 **
0x1800927d3  mov     [rsp+40h+var_20], r13; unsigned __int64
0x1800927d8  mov     r9, [rbp+arg_10]; unsigned __int8 *
0x1800927dc  mov     r8, rsi; void *
0x1800927df  mov     rdx, rdi; void *
0x1800927e2  mov     rcx, r14; this
0x1800927e5  call    ?EncryptData@AesProtector@@AEAAJPEAX0PEAE_KPEAPEAEPEA_K@Z; AesProtector::EncryptData(void *,void *,uchar *,unsigned __int64,uchar * *,unsigned __int64 *)
0x1800927ea  mov     ebx, eax
0x1800927ec  test    rdi, rdi
0x1800927ef  jz      short loc_1800927FA
0x1800927f1  mov     rcx, rdi; hKey
0x1800927f4  call    cs:__imp_BCryptDestroyKey
0x1800927fa  mov     eax, ebx
0x1800927fc  mov     rbx, [rsp+40h+arg_8]
0x180092804  add     rsp, 40h
0x180092808  pop     r15
0x18009280a  pop     r14
0x18009280c  pop     r13
0x18009280e  pop     r12
0x180092810  pop     rdi
0x180092811  pop     rsi
0x180092812  pop     rbp
0x180092813  retn
```
