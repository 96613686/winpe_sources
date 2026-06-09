# CBioTraceLogging::GetFingerprintEnrollmentDetails(ushort const *,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x18008053c`
- end: `0x1800806cd`
- name: `?GetFingerprintEnrollmentDetails@CBioTraceLogging@@CAJPEBGAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180081e54`

## callees

- `0x18000741c`
- `0x1800119c4`
- `0x180011a34`
- `0x1800530c4`
- `0x18005388c`
- `0x18005e844`
- `0x180068f60`
- `0x180069cc8`
- `0x18007d3f8`
- `0x18007eed0`
- `0x18008053c`
- `0x1800806d4`

## import_xrefs

- `ext-ms-win-biometrics-winbio-l1-2-0!WinBioOpenSession` at `0x1800805a2`
- `ext-ms-win-biometrics-winbio-l1-2-0!WinBioOpenSession` at `0x1800805a2`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioCloseSession` at `0x180080660`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioCloseSession` at `0x180080660`

## string_xrefs

- `0x1800805e3`: `onecore\ds\security\biometrics\service\server\biotracelogging.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBioTraceLogging::GetFingerprintEnrollmentDetails(unsigned __int16 *a1, _QWORD *a2)
{
  int IdentityFromSid; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rdi
  _QWORD *i; // rbx
  _QWORD *v10; // rax
  int UnitCount; // [rsp+20h] [rbp-E0h]
  __int16 v13; // [rsp+40h] [rbp-C0h] BYREF
  char v14[2]; // [rsp+42h] [rbp-BEh] BYREF
  WINBIO_SESSION_HANDLE SessionHandle; // [rsp+44h] [rbp-BCh] BYREF
  int v16; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v17; // [rsp+4Ch] [rbp-B4h] BYREF
  char v18; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v19; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v20[6]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+A0h] [rbp-60h] BYREF
  struct _WINBIO_IDENTITY v22; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  CHardwareManager::Instance();
  CHardwareManager::GetBiometricUnitList(&v19);
  SessionHandle = 0;
  IdentityFromSid = WinBioOpenSession(8u, 1u, 0, 0, 0, (GUID *)1, &SessionHandle);
  v5 = IdentityFromSid;
  if ( IdentityFromSid < 0 )
  {
    v6 = 1249;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\biotracelogging.cpp",
      (const char *)(unsigned int)IdentityFromSid,
      UnitCount);
    goto LABEL_12;
  }
  v16 = 0;
  memset_0(&v22, 0, sizeof(v22));
  IdentityFromSid = CBioTraceLogging::GetIdentityFromSid(a1, &v22);
  v5 = IdentityFromSid;
  if ( IdentityFromSid < 0 )
  {
    v6 = 1252;
    goto LABEL_5;
  }
  v17 = 0;
  v20[0] = &v17;
  v20[1] = a2;
  v20[2] = &SessionHandle;
  v20[3] = &v22;
  v20[4] = &v16;
  v8 = v19;
  for ( i = (_QWORD *)*v19; i != v8; i = (_QWORD *)*i )
  {
    v10 = std::shared_ptr<CBiometricServiceProvider>::shared_ptr<CBiometricServiceProvider>(&v21, i + 2);
    lambda_545ddefb5fa6d6f6e2e1e4e3a22afd11_::operator()_std::shared_ptr_CBiometricUnit___(v20, v10);
  }
  if ( SessionHandle )
    WinBioCloseSession(SessionHandle);
  v13 = v16;
  std::vector<unsigned char>::insert<unsigned char const *,0>(
    (_DWORD)a2,
    (unsigned int)&v18,
    *a2,
    (unsigned int)&v13,
    (__int64)v14);
  v5 = v17;
LABEL_12:
  std::_List_node<std::shared_ptr<CBiometricUnit>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<CBiometricUnit>,void *>>>(
    v7,
    v19);
  std::_Deallocate<16>(v19, 0x20u);
  return v5;
}

```

## disassembly

```asm
0x18008053c  mov     [rsp-8+arg_10], rbx
0x180080541  push    rbp
0x180080542  push    rsi
0x180080543  push    rdi
0x180080544  lea     rbp, [rsp-10h]
0x180080549  sub     rsp, 110h
0x180080550  mov     rax, cs:__security_cookie
0x180080557  xor     rax, rsp
0x18008055a  mov     [rbp+20h+var_20], rax
0x18008055e  mov     rsi, rdx
0x180080561  mov     rdi, rcx
0x180080564  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180080569  lea     rcx, [rsp+120h+var_C8]
0x18008056e  call    ?GetBiometricUnitList@CHardwareManager@@SA?AV?$list@V?$shared_ptr@VCBiometricUnit@@@std@@V?$allocator@V?$shared_ptr@VCBiometricUnit@@@std@@@2@@std@@XZ; CHardwareManager::GetBiometricUnitList(void)
0x180080573  nop
0x180080574  mov     [rsp+120h+var_DC], 0
0x18008057c  lea     rax, [rsp+120h+var_DC]
0x180080581  mov     [rsp+120h+SessionHandle], rax; SessionHandle
0x180080586  mov     edx, 1; PoolType
0x18008058b  mov     [rsp+120h+DatabaseId], rdx; DatabaseId
0x180080590  mov     [rsp+120h+UnitCount], 0; int
0x180080599  xor     r9d, r9d; UnitArray
0x18008059c  xor     r8d, r8d; Flags
0x18008059f  lea     ecx, [rdx+7]; Factor
0x1800805a2  call    cs:__imp_WinBioOpenSession
0x1800805a8  mov     ebx, eax
0x1800805aa  test    eax, eax
0x1800805ac  jns     short loc_1800805B5
0x1800805ae  mov     edx, 4E1h
0x1800805b3  jmp     short loc_1800805E3
0x1800805b5  mov     [rsp+120h+var_D8], 0
0x1800805bd  xor     edx, edx; Val
0x1800805bf  lea     r8d, [rdx+4Ch]; Size
0x1800805c3  lea     rcx, [rbp+20h+var_70]; void *
0x1800805c7  call    memset_0
0x1800805cc  lea     rdx, [rbp+20h+var_70]; struct _WINBIO_IDENTITY *
0x1800805d0  mov     rcx, rdi; unsigned __int16 *
0x1800805d3  call    ?GetIdentityFromSid@CBioTraceLogging@@CAJPEBGPEAU_WINBIO_IDENTITY@@@Z; CBioTraceLogging::GetIdentityFromSid(ushort const *,_WINBIO_IDENTITY *)
0x1800805d8  mov     ebx, eax
0x1800805da  test    eax, eax
0x1800805dc  jns     short loc_1800805FB
0x1800805de  mov     edx, 4E4h; void *
0x1800805e3  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\biometrics\\serv"...
0x1800805ea  mov     r9d, eax; char *
0x1800805ed  mov     rcx, [rbp+28h]; this
0x1800805f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800805f6  jmp     loc_180080693
0x1800805fb  mov     [rsp+120h+var_D4], 0
0x180080603  lea     rax, [rsp+120h+var_D4]
0x180080608  mov     [rsp+120h+var_B0], rax
0x18008060d  mov     [rsp+120h+var_A8], rsi
0x180080612  lea     rax, [rsp+120h+var_DC]
0x180080617  mov     [rbp+20h+var_A0], rax
0x18008061b  lea     rax, [rbp+20h+var_70]
0x18008061f  mov     [rbp+20h+var_98], rax
0x180080623  lea     rax, [rsp+120h+var_D8]
0x180080628  mov     [rbp+20h+var_90], rax
0x18008062c  mov     rdi, [rsp+120h+var_C8]
0x180080631  mov     rbx, [rdi]
0x180080634  cmp     rbx, rdi
0x180080637  jz      short loc_180080658
0x180080639  lea     rdx, [rbx+10h]
0x18008063d  lea     rcx, [rbp+20h+var_80]
0x180080641  call    ??0?$shared_ptr@VCBiometricServiceProvider@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CBiometricServiceProvider>::shared_ptr<CBiometricServiceProvider>(std::shared_ptr<CBiometricServiceProvider> const &)
0x180080646  mov     rdx, rax
0x180080649  lea     rcx, [rsp+120h+var_B0]
0x18008064e  call    _lambda_545ddefb5fa6d6f6e2e1e4e3a22afd11___operator___std__shared_ptr_CBiometricUnit___
0x180080653  mov     rbx, [rbx]
0x180080656  jmp     short loc_180080634
0x180080658  mov     ecx, [rsp+120h+var_DC]; SessionHandle
0x18008065c  test    ecx, ecx
0x18008065e  jz      short loc_180080666
0x180080660  call    cs:__imp_WinBioCloseSession
0x180080666  movzx   eax, word ptr [rsp+120h+var_D8]
0x18008066b  mov     [rsp+120h+var_E0], ax
0x180080670  lea     rax, [rsp+120h+var_DE]
0x180080675  mov     [rsp+120h+UnitCount], rax
0x18008067a  lea     r9, [rsp+120h+var_E0]
0x18008067f  mov     r8, [rsi]
0x180080682  lea     rdx, [rsp+120h+var_D0]
0x180080687  mov     rcx, rsi
0x18008068a  call    ??$insert@PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE1@Z; std::vector<uchar>::insert<uchar const *,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,uchar const *)
0x18008068f  mov     ebx, [rsp+120h+var_D4]
0x180080693  mov     rdx, [rsp+120h+var_C8]
0x180080698  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$shared_ptr@VCBiometricUnit@@@std@@PEAX@std@@@std@@@?$_List_node@V?$shared_ptr@VCBiometricUnit@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@VCBiometricUnit@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::shared_ptr<CBiometricUnit>,void *>::_Free_non_head<std::allocator<std::_List_node<std::shared_ptr<CBiometricUnit>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<CBiometricUnit>,void *>> &,std::_List_node<std::shared_ptr<CBiometricUnit>,void *> *)
0x18008069d  mov     edx, 20h ; ' '
0x1800806a2  mov     rcx, [rsp+120h+var_C8]
0x1800806a7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800806ac  mov     eax, ebx
0x1800806ae  mov     rcx, [rbp+20h+var_20]
0x1800806b2  xor     rcx, rsp; StackCookie
0x1800806b5  call    __security_check_cookie
0x1800806ba  mov     rbx, [rsp+120h+arg_10]
0x1800806c2  add     rsp, 110h
0x1800806c9  pop     rdi
0x1800806ca  pop     rsi
0x1800806cb  pop     rbp
0x1800806cc  retn
```
