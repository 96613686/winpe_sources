# TpmProtector::Unprotect(void *,std::vector<uchar,wil::secure_allocator<uchar>> &&,uchar *,unsigned __int64,uchar * *,unsigned __int64 *)

- ea: `0x180092a20`
- end: `0x180092bf0`
- name: `?Unprotect@TpmProtector@@UEAAJPEAX$$QEAV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAE_KPEAPEAEPEA_K@Z`
- size: `464`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *, __int64, unsigned __int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18002c420`
- `0x18003f2dc`
- `0x180040278`
- `0x18005388c`
- `0x1800538b0`
- `0x180053fb0`
- `0x180055cf8`
- `0x18006b0b5`
- `0x180092a20`

## import_xrefs

- `ngcutils!NgcSetBioProtectorUpdateNeeded` at `0x180092a65`
- `ngcutils!NgcSetBioProtectorUpdateNeeded` at `0x180092bc0`
- `ngcutils!NgcSetBioProtectorUpdateNeeded` at `0x180092a65`
- `ngcutils!NgcSetBioProtectorUpdateNeeded` at `0x180092bc0`

## string_xrefs

- `0x180092a49`: `onecore\ds\security\biometrics\service\server\dataprotector.cpp`
- `0x180092a94`: `onecore\ds\security\biometrics\service\server\dataprotector.cpp`
- `0x180092afd`: `onecore\ds\security\biometrics\service\server\dataprotector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TpmProtector::Unprotect(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        __int64 a4,
        unsigned __int64 a5,
        _QWORD *a6,
        _QWORD *a7)
{
  unsigned int v7; // ecx
  unsigned int v9; // r10d
  unsigned __int64 v10; // rax
  int v11; // edi
  int updated; // eax
  int v14; // edx
  unsigned int v15; // r8d
  const unsigned __int8 *v16; // rdx
  TpmPolicySession *v17; // rcx
  int v18; // eax
  __int64 v19; // rdx
  void *v20; // rdx
  void *v21; // rax
  void *v22; // rdi
  void *v23; // rdx
  int v24; // eax
  int v25; // [rsp+20h] [rbp-30h]
  int v26; // [rsp+20h] [rbp-30h]
  int v27; // [rsp+20h] [rbp-30h]
  void *Src; // [rsp+30h] [rbp-20h] BYREF
  void **p_Src; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v30[2]; // [rsp+40h] [rbp-10h] BYREF
  char v31; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  size_t size; // [rsp+78h] [rbp+28h] BYREF

  v7 = *(_DWORD *)(a4 + 4);
  v9 = *(_DWORD *)(a4 + 12);
  v10 = v7 + v9;
  if ( (unsigned int)v10 < v7 )
  {
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x4E2,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\dataprotector.cpp",
            (const char *)0xC0000095LL,
            v25);
LABEL_3:
    updated = NgcSetBioProtectorUpdateNeeded();
    if ( updated < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4CE,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\dataprotector.cpp",
        (const char *)(unsigned int)updated,
        v26);
    return (unsigned int)v11;
  }
  if ( v10 > a5 )
  {
    v11 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E6,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\dataprotector.cpp",
      (const char *)0x80070057LL,
      v25);
    goto LABEL_3;
  }
  v14 = a3[2];
  v15 = a4 + v7;
  v16 = (const unsigned __int8 *)(unsigned int)(v14 - *a3);
  v17 = *(TpmPolicySession **)a3;
  p_Src = &Src;
  LODWORD(size) = 0;
  *(_QWORD *)v30 = 0;
  v31 = 1;
  v18 = TpmPolicySession::UnSealWithTpmTicket(
          v17,
          v16,
          v15,
          (const unsigned __int8 *)v9,
          (unsigned int)v30,
          (unsigned __int8 **)&size,
          0);
  v11 = v18;
  if ( v18 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4F2,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\dataprotector.cpp",
      (const char *)(unsigned int)v18,
      v27);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_Src);
  if ( v11 == -2146893779 )
  {
    v11 = -2146860974;
LABEL_13:
    v19 = 1272;
    goto LABEL_14;
  }
  if ( v11 < 0 )
    goto LABEL_13;
  v21 = MIDL_user_allocate((unsigned int)size);
  v22 = v21;
  if ( !v21 )
  {
    v11 = -2147024882;
    v19 = 1275;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\dataprotector.cpp",
      (const char *)(unsigned int)v11,
      v27);
    v20 = Src;
    Src = 0;
    if ( v20 )
      wil::hlocal_secure_deleter::operator()<unsigned char>();
    goto LABEL_3;
  }
  memcpy_0(v21, Src, (unsigned int)size);
  v23 = Src;
  Src = 0;
  *a7 = (unsigned int)size;
  *a6 = v22;
  if ( v23 )
    wil::hlocal_secure_deleter::operator()<unsigned char>();
  v24 = NgcSetBioProtectorUpdateNeeded();
  if ( v24 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4CE,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\dataprotector.cpp",
      (const char *)(unsigned int)v24,
      v27);
  return 0;
}

```

## disassembly

```asm
0x180092a20  mov     [rsp-8+arg_0], rbx
0x180092a25  mov     [rsp-8+arg_8], rdi
0x180092a2a  push    rbp
0x180092a2b  mov     rbp, rsp
0x180092a2e  sub     rsp, 50h
0x180092a32  mov     ecx, [r9+4]
0x180092a36  mov     r11, r8
0x180092a39  mov     r10d, [r9+0Ch]
0x180092a3d  lea     eax, [rcx+r10]
0x180092a41  cmp     eax, ecx
0x180092a43  jnb     short loc_180092A8A
0x180092a45  mov     rcx, [rbp+8]; this
0x180092a49  lea     rbx, aOnecoreDsSecur_42; "onecore\\ds\\security\\biometrics\\serv"...
0x180092a50  mov     r8, rbx; unsigned int
0x180092a53  mov     r9d, 0C0000095h; char *
0x180092a59  mov     edx, 4E2h; void *
0x180092a5e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180092a63  mov     edi, eax
0x180092a65  call    cs:__imp_NgcSetBioProtectorUpdateNeeded
0x180092a6b  test    eax, eax
0x180092a6d  jns     short loc_180092A83
0x180092a6f  mov     rcx, [rbp+8]; this
0x180092a73  mov     r9d, eax; char *
0x180092a76  mov     r8, rbx; unsigned int
0x180092a79  mov     edx, 4CEh; void *
0x180092a7e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180092a83  mov     eax, edi
0x180092a85  jmp     loc_180092BE0
0x180092a8a  cmp     rax, [rbp+arg_20]
0x180092a8e  jbe     short loc_180092AB2
0x180092a90  mov     rcx, [rbp+8]; this
0x180092a94  lea     rbx, aOnecoreDsSecur_42; "onecore\\ds\\security\\biometrics\\serv"...
0x180092a9b  mov     edi, 80070057h
0x180092aa0  mov     r8, rbx; unsigned int
0x180092aa3  mov     r9d, edi; char *
0x180092aa6  mov     edx, 4E6h; void *
0x180092aab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180092ab0  jmp     short loc_180092A65
0x180092ab2  mov     edx, [r11+8]
0x180092ab6  lea     r8, [r9+rcx]; unsigned int
0x180092aba  sub     edx, [r11]; unsigned __int8 *
0x180092abd  lea     rax, [rbp+Src]
0x180092ac1  mov     rcx, [r11]; this
0x180092ac4  mov     r9d, r10d; unsigned __int8 *
0x180092ac7  mov     [rbp+var_18], rax
0x180092acb  lea     rax, [rbp+size]
0x180092acf  mov     [rsp+50h+var_28], rax; unsigned __int8 **
0x180092ad4  lea     rax, [rbp+var_10]
0x180092ad8  mov     qword ptr [rsp+50h+var_30], rax; int
0x180092add  mov     [rbp+Src], 0
0x180092ae5  mov     dword ptr [rbp+size], 0
0x180092aec  mov     qword ptr [rbp+var_10], 0
0x180092af4  mov     [rbp+var_8], 1
0x180092af8  call    ?UnSealWithTpmTicket@TpmPolicySession@@YAJPEBEK0KPEAPEAEPEAK@Z; TpmPolicySession::UnSealWithTpmTicket(uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *)
0x180092afd  lea     rbx, aOnecoreDsSecur_42; "onecore\\ds\\security\\biometrics\\serv"...
0x180092b04  mov     edi, eax
0x180092b06  test    eax, eax
0x180092b08  jns     short loc_180092B1E
0x180092b0a  mov     rcx, [rbp+8]; this
0x180092b0e  mov     r9d, eax; char *
0x180092b11  mov     r8, rbx; unsigned int
0x180092b14  mov     edx, 4F2h; void *
0x180092b19  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180092b1e  lea     rcx, [rbp+var_18]
0x180092b22  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x180092b27  cmp     edi, 8009002Dh
0x180092b2d  jnz     short loc_180092B36
0x180092b2f  mov     edi, 80098052h
0x180092b34  jmp     short loc_180092B3A
0x180092b36  test    edi, edi
0x180092b38  jns     short loc_180092B6D
0x180092b3a  mov     edx, 4F8h; void *
0x180092b3f  mov     rcx, [rbp+8]; this
0x180092b43  mov     r8, rbx; unsigned int
0x180092b46  mov     r9d, edi; char *
0x180092b49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180092b4e  mov     rdx, [rbp+Src]
0x180092b52  mov     [rbp+Src], 0
0x180092b5a  test    rdx, rdx
0x180092b5d  jz      loc_180092A65
0x180092b63  call    ??$?RE@hlocal_secure_deleter@wil@@QEBAXPEAE@Z; wil::hlocal_secure_deleter::operator()<uchar>(uchar *)
0x180092b68  jmp     loc_180092A65
0x180092b6d  mov     ecx, dword ptr [rbp+size]; size
0x180092b70  call    MIDL_user_allocate
0x180092b75  mov     rdi, rax
0x180092b78  test    rax, rax
0x180092b7b  jnz     short loc_180092B89
0x180092b7d  mov     edi, 8007000Eh
0x180092b82  mov     edx, 4FBh
0x180092b87  jmp     short loc_180092B3F
0x180092b89  mov     r8d, dword ptr [rbp+size]; Size
0x180092b8d  mov     rcx, rdi; void *
0x180092b90  mov     rdx, [rbp+Src]; Src
0x180092b94  call    memcpy_0
0x180092b99  mov     rax, [rbp+arg_30]
0x180092b9d  mov     rdx, [rbp+Src]
0x180092ba1  mov     ecx, dword ptr [rbp+size]
0x180092ba4  mov     [rbp+Src], 0
0x180092bac  mov     [rax], rcx
0x180092baf  mov     rax, [rbp+arg_28]
0x180092bb3  mov     [rax], rdi
0x180092bb6  test    rdx, rdx
0x180092bb9  jz      short loc_180092BC0
0x180092bbb  call    ??$?RE@hlocal_secure_deleter@wil@@QEBAXPEAE@Z; wil::hlocal_secure_deleter::operator()<uchar>(uchar *)
0x180092bc0  call    cs:__imp_NgcSetBioProtectorUpdateNeeded
0x180092bc6  test    eax, eax
0x180092bc8  jns     short loc_180092BDE
0x180092bca  mov     rcx, [rbp+8]; this
0x180092bce  mov     r9d, eax; char *
0x180092bd1  mov     r8, rbx; unsigned int
0x180092bd4  mov     edx, 4CEh; void *
0x180092bd9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180092bde  xor     eax, eax
0x180092be0  mov     rbx, [rsp+50h+arg_0]
0x180092be5  mov     rdi, [rsp+50h+arg_8]
0x180092bea  add     rsp, 50h
0x180092bee  pop     rbp
0x180092bef  retn
```
