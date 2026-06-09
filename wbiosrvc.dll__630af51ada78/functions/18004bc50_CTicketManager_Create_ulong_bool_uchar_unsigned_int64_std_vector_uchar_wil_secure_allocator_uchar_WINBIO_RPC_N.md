# CTicketManager::Create(ulong,bool,uchar *,unsigned __int64,std::vector<uchar,wil::secure_allocator<uchar>> &&,_WINBIO_RPC_NGC_AUTHORIZATION *,_WINBIO_GESTURE_METADATA,unsigned __int64 *)

- ea: `0x18004bc50`
- end: `0x18004c065`
- name: `?Create@CTicketManager@@SAJK_NPEAE_K$$QEAV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAU_WINBIO_RPC_NGC_AUTHORIZATION@@U_WINBIO_GESTURE_METADATA@@PEA_K@Z`
- size: `1045`
- prototype: `__int64 __fastcall(unsigned int, char, void *, unsigned __int64, __int64, char *, __int64, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180049970`
- `0x18004a2f0`
- `0x1800907a0`

## callees

- `0x1800024b4`
- `0x18000255c`
- `0x18000394c`
- `0x180004728`
- `0x18000b760`
- `0x180023d88`
- `0x180028af0`
- `0x18002b7c0`
- `0x180038dd0`
- `0x18003f848`
- `0x180041b7c`
- `0x180044b1c`
- `0x18004b950`
- `0x18004bc50`
- `0x180055878`
- `0x1800559c8`
- `0x18005da30`
- `0x180060680`
- `0x180068f60`
- `0x180069330`
- `0x18006963c`
- `0x180093700`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004bcd8`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004bcd8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004bce9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004bce9`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CTicketManager::Create(
        unsigned int a1,
        char a2,
        void *a3,
        unsigned __int64 a4,
        __int64 a5,
        char *a6,
        __int64 a7,
        unsigned __int64 *a8)
{
  __int64 v11; // r15
  unsigned __int64 *v12; // r13
  int v13; // esi
  char *v14; // r14
  struct CTicketManager *v15; // rax
  __int64 **v16; // rbx
  __int64 **v17; // rax
  unsigned __int64 v18; // rdx
  int v19; // edi
  __int64 **v20; // rcx
  bool IsFocusProcess; // al
  int v22; // r8d
  int v23; // r9d
  int v24; // ecx
  struct CTicketManager *v25; // rax
  void *v26; // rsi
  char *v27; // rbx
  struct CTicketManager *v28; // r14
  __int64 v29; // r8
  void *v30; // rcx
  unsigned __int64 v31; // rbx
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  bool v36; // [rsp+40h] [rbp-298h] BYREF
  char v37[7]; // [rsp+41h] [rbp-297h] BYREF
  char *v38; // [rsp+48h] [rbp-290h] BYREF
  void *v39; // [rsp+50h] [rbp-288h] BYREF
  unsigned __int64 v40; // [rsp+58h] [rbp-280h] BYREF
  char *v41; // [rsp+60h] [rbp-278h] BYREF
  __int64 v42; // [rsp+68h] [rbp-270h] BYREF
  char v43[8]; // [rsp+70h] [rbp-268h] BYREF
  char v44[8]; // [rsp+78h] [rbp-260h] BYREF
  std::_Ref_count_base *v45; // [rsp+80h] [rbp-258h]
  _BYTE v46[528]; // [rsp+90h] [rbp-248h] BYREF
  unsigned int v47; // [rsp+2E0h] [rbp+8h] BYREF

  v47 = a1;
  v39 = a3;
  v42 = a5;
  v11 = a7;
  v12 = a8;
  v13 = 0;
  v14 = a6;
  v41 = a6;
  if ( !a4 )
    goto LABEL_36;
  if ( !a3 || !a8 )
  {
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v41);
    return 2147500035LL;
  }
  if ( IsValidSid(a3) && GetLengthSid(a3) <= a4 )
  {
    if ( v14 && *((_DWORD *)v14 + 1) )
      *(_DWORD *)(v11 + 16) = 2;
    *v12 = 0;
    v15 = CTicketManager::Instance();
    winbio::lockable_object::lock_exclusive(v15, v43);
    v40 = 0;
    v16 = (__int64 **)*((_QWORD *)CTicketManager::Instance() + 2);
    v17 = (__int64 **)*((_QWORD *)CTicketManager::Instance() + 2);
    v18 = 0;
    while ( 1 )
    {
      v17 = (__int64 **)*v17;
      if ( v17 == v16 )
        break;
      if ( *((_DWORD *)v17[2] + 2) == v47 )
        ++v18;
    }
    if ( v18 < 0x14 )
    {
      while ( 2 )
      {
        v19 = CTicketManager::GenerateTicketId(&v40);
        if ( v19 >= 0 )
        {
          v20 = (__int64 **)*((_QWORD *)CTicketManager::Instance() + 2);
          do
          {
            v20 = (__int64 **)*v20;
            if ( v20 == v16 )
            {
              if ( __eh34_try(-1, 0) )
              {
                __eh34_scope_strut(0);
                IsFocusProcess = CFocusMonitor::IsFocusProcess(v47);
                LOBYTE(v24) = IsFocusProcess;
                if ( a2 && IsFocusProcess )
                {
                  v41 = 0;
                  v38 = v14;
                  std::make_shared<CProtectionTicket,unsigned __int64 &,unsigned long &,unsigned char * &,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,_WINBIO_RPC_NGC_AUTHORIZATION *>(
                    (int)v44,
                    (int)&v40,
                    (int)&v47,
                    (int)&v39,
                    v42,
                    (__int64)&v38);
                  v25 = CTicketManager::Instance();
                  std::list<std::shared_ptr<CProtectionTicket>>::push_back((char *)v25 + 16, v44);
                  CEtwEvent::CEtwEvent((CEtwEvent *)v46);
                  v26 = v39;
                  CEtwEvent::CaptureSidInfo((CEtwEvent *)v46, v39);
                  CEtwEvent::Write(v46, 1605, 1);
                  v27 = (char *)operator new(0x20u);
                  *(_QWORD *)v27 = v40;
                  *(_OWORD *)(v27 + 8) = *(_OWORD *)v11;
                  *((_QWORD *)v27 + 3) = *(_QWORD *)(v11 + 16);
                  v38 = v27;
                  v28 = CTicketManager::Instance();
                  v29 = *((_QWORD *)CTicketManager::Instance() + 14);
                  v38 = 0;
                  v30 = (void *)*((_QWORD *)v28 + v29 + 4);
                  *((_QWORD *)v28 + v29 + 4) = v27;
                  if ( v30 )
                    operator delete(v30, 0x20u);
                  v31 = (*((_QWORD *)CTicketManager::Instance() + 14) + 1LL) % 0xAuLL;
                  *((_QWORD *)CTicketManager::Instance() + 14) = v31;
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors>::GetImpl'::`2'::impl)
                    && (unsigned int)dword_18010F170 > 5
                    && (unsigned __int8)tlgKeywordOn(&dword_18010F170, 0x400000000000LL) )
                  {
                    v42 = 50331648;
                    v39 = v26;
                    v36 = *(_DWORD *)(v11 + 16) == 2;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapSid<_SID>,_tlgWrapperByVal<8>>(
                      v32,
                      (int)byte_1800EFBF1,
                      v33,
                      v34,
                      (__int64)&v36,
                      (__int64)&v39,
                      (__int64)&v42);
                  }
                  std::unique_ptr<GestureMetadata>::~unique_ptr<GestureMetadata>(&v38);
                  CEtwEvent::~CEtwEvent((CEtwEvent *)v46);
                  if ( v45 )
                    std::_Ref_count_base::_Decref(v45);
                }
                else if ( (unsigned int)dword_18010F170 > 3 )
                {
                  v36 = IsFocusProcess;
                  v37[0] = a2;
                  LODWORD(v39) = v47;
                  LODWORD(v38) = 0;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
                    v24,
                    (int)word_1800EFB8A,
                    v22,
                    v23,
                    (__int64)&v38,
                    (__int64)&v39,
                    (__int64)v37,
                    (__int64)&v36);
                }
                *v12 = v40;
              }
              if ( __eh34_catch(0) )
              {
                if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
                {
                  v19 = -2147024882;
                  __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18004BFFA);
                }
              }
              goto LABEL_34;
            }
          }
          while ( *v20[2] != v40 );
          if ( ++v13 < 3 )
            continue;
          v19 = -2147023537;
        }
        break;
      }
    }
    else
    {
      v19 = -2146860987;
    }
LABEL_34:
    Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v43);
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v41);
    return (unsigned int)v19;
  }
  else
  {
LABEL_36:
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(&v41);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18004bc50  mov     [rsp+arg_8], rbx
0x18004bc55  mov     [rsp+arg_18], rsi
0x18004bc5a  mov     [rsp+arg_0], ecx
0x18004bc5e  push    rdi
0x18004bc5f  push    r12
0x18004bc61  push    r13
0x18004bc63  push    r14
0x18004bc65  push    r15
0x18004bc67  sub     rsp, 2B0h
0x18004bc6e  mov     rax, cs:__security_cookie
0x18004bc75  xor     rax, rsp
0x18004bc78  mov     [rsp+2D8h+var_38], rax
0x18004bc80  mov     rdi, r9
0x18004bc83  mov     rbx, r8
0x18004bc86  mov     r12b, dl
0x18004bc89  mov     [rsp+2D8h+var_288], rbx
0x18004bc8e  mov     rax, [rsp+2D8h+arg_20]
0x18004bc96  mov     [rsp+2D8h+var_270], rax
0x18004bc9b  mov     r15, [rsp+2D8h+arg_30]
0x18004bca3  mov     r13, [rsp+2D8h+arg_38]
0x18004bcab  xor     esi, esi
0x18004bcad  mov     r14, [rsp+2D8h+arg_28]
0x18004bcb5  mov     [rsp+2D8h+var_278], r14
0x18004bcba  test    r9, r9
0x18004bcbd  jz      loc_18004C029
0x18004bcc3  test    rbx, rbx
0x18004bcc6  jz      loc_18004C018
0x18004bccc  test    r13, r13
0x18004bccf  jz      loc_18004C018
0x18004bcd5  mov     rcx, rbx; pSid
0x18004bcd8  call    cs:__imp_IsValidSid
0x18004bcde  test    eax, eax
0x18004bce0  jz      loc_18004C029
0x18004bce6  mov     rcx, rbx; pSid
0x18004bce9  call    cs:__imp_GetLengthSid
0x18004bcef  mov     eax, eax
0x18004bcf1  cmp     rax, rdi
0x18004bcf4  ja      loc_18004C029
0x18004bcfa  test    r14, r14
0x18004bcfd  jz      short loc_18004BD0D
0x18004bcff  cmp     [r14+4], esi
0x18004bd03  jbe     short loc_18004BD0D
0x18004bd05  mov     dword ptr [r15+10h], 2
0x18004bd0d  mov     [r13+0], rsi
0x18004bd11  call    ?Instance@CTicketManager@@SAAEAV1@XZ; CTicketManager::Instance(void)
0x18004bd16  lea     rdx, [rsp+2D8h+var_268]
0x18004bd1b  mov     rcx, rax
0x18004bd1e  call    ?lock_exclusive@lockable_object@winbio@@QEBA?AVSyncLockExclusive@Details@Wrappers@WRL@Microsoft@@XZ; winbio::lockable_object::lock_exclusive(void)
0x18004bd23  nop
0x18004bd24  mov     [rsp+2D8h+var_280], rsi
0x18004bd29  call    ?Instance@CTicketManager@@SAAEAV1@XZ; CTicketManager::Instance(void)
0x18004bd2e  mov     rbx, [rax+10h]
0x18004bd32  call    ?Instance@CTicketManager@@SAAEAV1@XZ; CTicketManager::Instance(void)
0x18004bd37  mov     rax, [rax+10h]
0x18004bd3b  mov     rdx, rsi
0x18004bd3e  mov     r8d, [rsp+2D8h+arg_0]
0x18004bd46  mov     rax, [rax]
0x18004bd49  cmp     rax, rbx
0x18004bd4c  jz      short loc_18004BD5D
0x18004bd4e  mov     rcx, [rax+10h]
0x18004bd52  cmp     [rcx+8], r8d
0x18004bd56  jnz     short loc_18004BD46
0x18004bd58  inc     rdx
0x18004bd5b  jmp     short loc_18004BD46
0x18004bd5d  cmp     rdx, 14h
0x18004bd61  jb      short loc_18004BD6D
0x18004bd63  mov     edi, 80098045h
0x18004bd68  jmp     loc_18004BFFF
0x18004bd6d  lea     rcx, [rsp+2D8h+var_280]; unsigned __int64 *
0x18004bd72  call    ?GenerateTicketId@CTicketManager@@CAJPEA_K@Z; CTicketManager::GenerateTicketId(unsigned __int64 *)
0x18004bd77  mov     edi, eax
0x18004bd79  test    eax, eax
0x18004bd7b  js      loc_18004BFFF
0x18004bd81  call    ?Instance@CTicketManager@@SAAEAV1@XZ; CTicketManager::Instance(void)
0x18004bd86  mov     rcx, [rax+10h]
0x18004bd8a  mov     rdx, [rsp+2D8h+var_280]
0x18004bd8f  mov     rcx, [rcx]
0x18004bd92  cmp     rcx, rbx
0x18004bd95  jz      short loc_18004BDB1
0x18004bd97  mov     rax, [rcx+10h]
0x18004bd9b  cmp     [rax], rdx
0x18004bd9e  jnz     short loc_18004BD8F
0x18004bda0  inc     esi
0x18004bda2  cmp     esi, 3
0x18004bda5  jl      short loc_18004BD6D
0x18004bda7  mov     edi, 8007054Fh
0x18004bdac  jmp     loc_18004BFFF
0x18004bdb1  mov     ecx, [rsp+2D8h+arg_0]; unsigned int
0x18004bdb8  call    ?IsFocusProcess@CFocusMonitor@@SA_NK@Z; CFocusMonitor::IsFocusProcess(ulong)
0x18004bdbd  mov     cl, al
0x18004bdbf  test    r12b, r12b
0x18004bdc2  jz      loc_18004BF94
0x18004bdc8  test    al, al
0x18004bdca  jz      loc_18004BF94
0x18004bdd0  mov     [rsp+2D8h+var_278], 0
0x18004bdd9  mov     [rsp+2D8h+var_290], r14
0x18004bdde  lea     rax, [rsp+2D8h+var_290]
0x18004bde3  mov     [rsp+2D8h+var_2B0], rax
0x18004bde8  mov     rax, [rsp+2D8h+var_270]
0x18004bded  mov     [rsp+2D8h+var_2B8], rax
0x18004bdf2  lea     r9, [rsp+2D8h+var_288]
0x18004bdf7  lea     r8, [rsp+2D8h+arg_0]
0x18004bdff  lea     rdx, [rsp+2D8h+var_280]
0x18004be04  lea     rcx, [rsp+2D8h+var_260]
0x18004be09  call    ??$make_shared@VCProtectionTicket@@AEA_KAEAKAEAPEAEV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAU_WINBIO_RPC_NGC_AUTHORIZATION@@@std@@YA?AV?$shared_ptr@VCProtectionTicket@@@0@AEA_KAEAKAEAPEAE$$QEAV?$vector@EU?$secure_allocator@E@wil@@@0@$$QEAPEAU_WINBIO_RPC_NGC_AUTHORIZATION@@@Z; std::make_shared<CProtectionTicket,unsigned __int64 &,ulong &,uchar * &,std::vector<uchar,wil::secure_allocator<uchar>>,_WINBIO_RPC_NGC_AUTHORIZATION *>(unsigned __int64 &,ulong &,uchar * &,std::vector<uchar,wil::secure_allocator<uchar>> &&,_WINBIO_RPC_NGC_AUTHORIZATION * &&)
0x18004be0e  nop
0x18004be0f  call    ?Instance@CTicketManager@@SAAEAV1@XZ; CTicketManager::Instance(void)
0x18004be14  lea     rcx, [rax+10h]
0x18004be18  lea     rdx, [rsp+2D8h+var_260]
0x18004be1d  call    ?push_back@?$list@V?$shared_ptr@VCProtectionTicket@@@std@@V?$allocator@V?$shared_ptr@VCProtectionTicket@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VCProtectionTicket@@@2@@Z; std::list<std::shared_ptr<CProtectionTicket>>::push_back(std::shared_ptr<CProtectionTicket> &&)
0x18004be22  lea     rcx, [rsp+2D8h+var_248]; this
0x18004be2a  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x18004be2f  nop
0x18004be30  mov     rsi, [rsp+2D8h+var_288]
0x18004be35  mov     rdx, rsi; void *
0x18004be38  lea     rcx, [rsp+2D8h+var_248]; this
0x18004be40  call    ?CaptureSidInfo@CEtwEvent@@QEAAXPEAX@Z; CEtwEvent::CaptureSidInfo(void *)
0x18004be45  mov     edx, 645h
0x18004be4a  mov     r8d, 1
0x18004be50  lea     rcx, [rsp+2D8h+var_248]
0x18004be58  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x18004be5d  mov     r12d, 20h ; ' '
0x18004be63  mov     ecx, r12d; Size
0x18004be66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004be6b  mov     rbx, rax
0x18004be6e  mov     rcx, [rsp+2D8h+var_280]
0x18004be73  mov     [rax], rcx
0x18004be76  movups  xmm0, xmmword ptr [r15]
0x18004be7a  movups  xmmword ptr [rax+8], xmm0
0x18004be7e  movsd   xmm1, qword ptr [r15+10h]
0x18004be84  movsd   qword ptr [rax+18h], xmm1
0x18004be89  mov     [rsp+2D8h+var_290], rax
0x18004be8e  call    ?Instance@CTicketManager@@SAAEAV1@XZ; CTicketManager::Instance(void)
0x18004be93  mov     r14, rax
0x18004be96  call    ?Instance@CTicketManager@@SAAEAV1@XZ; CTicketManager::Instance(void)
0x18004be9b  mov     r8, [rax+70h]
0x18004be9f  mov     [rsp+2D8h+var_290], 0
0x18004bea8  mov     rcx, [r14+r8*8+20h]; void *
0x18004bead  mov     [r14+r8*8+20h], rbx
0x18004beb2  test    rcx, rcx
0x18004beb5  jz      short loc_18004BEBF
0x18004beb7  mov     edx, r12d; unsigned __int64
0x18004beba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004bebf  call    ?Instance@CTicketManager@@SAAEAV1@XZ; CTicketManager::Instance(void)
0x18004bec4  mov     rbx, [rax+70h]
0x18004bec8  inc     rbx
0x18004becb  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18004bed5  mul     rbx
0x18004bed8  shr     rdx, 3
0x18004bedc  lea     rax, [rdx+rdx*4]
0x18004bee0  add     rax, rax
0x18004bee3  sub     rbx, rax
0x18004bee6  call    ?Instance@CTicketManager@@SAAEAV1@XZ; CTicketManager::Instance(void)
0x18004beeb  mov     [rax+70h], rbx
0x18004beef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors> `wil::Feature<__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors>::GetImpl(void)'::`2'::impl
0x18004bef6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddLoggingForFaceAuthErrors>::__private_IsEnabled(void)
0x18004befb  test    al, al
0x18004befd  jz      short loc_18004BF67
0x18004beff  mov     eax, cs:dword_18010F170
0x18004bf05  cmp     eax, 5
0x18004bf08  jbe     short loc_18004BF67
0x18004bf0a  mov     rdx, 400000000000h
0x18004bf14  lea     rcx, dword_18010F170
0x18004bf1b  call    _tlgKeywordOn
0x18004bf20  test    al, al
0x18004bf22  jz      short loc_18004BF67
0x18004bf24  mov     [rsp+2D8h+var_270], 3000000h
0x18004bf2d  mov     [rsp+2D8h+var_288], rsi
0x18004bf32  cmp     dword ptr [r15+10h], 2
0x18004bf37  setz    [rsp+2D8h+var_298]
0x18004bf3c  lea     rax, [rsp+2D8h+var_270]
0x18004bf41  mov     [rsp+2D8h+var_2A8], rax
0x18004bf46  lea     rax, [rsp+2D8h+var_288]
0x18004bf4b  mov     [rsp+2D8h+var_2B0], rax
0x18004bf50  lea     rax, [rsp+2D8h+var_298]
0x18004bf55  mov     [rsp+2D8h+var_2B8], rax
0x18004bf5a  lea     rdx, byte_1800EFBF1
0x18004bf61  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapSid<_SID>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapSid<_SID> const &,_tlgWrapperByVal<8> const &)
0x18004bf66  nop
0x18004bf67  lea     rcx, [rsp+2D8h+var_290]; void *
0x18004bf6c  call    ??1?$unique_ptr@VGestureMetadata@@U?$default_delete@VGestureMetadata@@@std@@@std@@QEAA@XZ; std::unique_ptr<GestureMetadata>::~unique_ptr<GestureMetadata>(void)
0x18004bf71  nop
0x18004bf72  lea     rcx, [rsp+2D8h+var_248]; this
0x18004bf7a  call    ??1CEtwEvent@@QEAA@XZ; CEtwEvent::~CEtwEvent(void)
0x18004bf7f  nop
0x18004bf80  mov     rcx, [rsp+2D8h+var_258]; this
0x18004bf88  test    rcx, rcx
0x18004bf8b  jz      short loc_18004BFEF
0x18004bf8d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004bf92  jmp     short loc_18004BFEF
0x18004bf94  mov     eax, cs:dword_18010F170
0x18004bf9a  cmp     eax, 3
0x18004bf9d  jbe     short loc_18004BFEF
0x18004bf9f  mov     [rsp+2D8h+var_298], cl
0x18004bfa3  mov     [rsp+2D8h+var_297], r12b
0x18004bfa8  mov     eax, [rsp+2D8h+arg_0]
0x18004bfaf  mov     dword ptr [rsp+2D8h+var_288], eax
0x18004bfb3  mov     dword ptr [rsp+2D8h+var_290], 0
0x18004bfbb  lea     rax, [rsp+2D8h+var_298]
0x18004bfc0  mov     [rsp+2D8h+var_2A0], rax
0x18004bfc5  lea     rax, [rsp+2D8h+var_297]
0x18004bfca  mov     [rsp+2D8h+var_2A8], rax
0x18004bfcf  lea     rax, [rsp+2D8h+var_288]
0x18004bfd4  mov     [rsp+2D8h+var_2B0], rax
0x18004bfd9  lea     rax, [rsp+2D8h+var_290]
0x18004bfde  mov     [rsp+2D8h+var_2B8], rax
0x18004bfe3  lea     rdx, word_1800EFB8A
0x18004bfea  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x18004bfef  mov     rax, [rsp+2D8h+var_280]
0x18004bff4  mov     [r13+0], rax
0x18004bff8  jmp     short loc_18004BFFF
0x18004bffa  mov     edi, 8007000Eh
0x18004bfff  lea     rcx, [rsp+2D8h+var_268]; this
0x18004c004  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x18004c009  nop
0x18004c00a  lea     rcx, [rsp+2D8h+var_278]
0x18004c00f  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x18004c014  mov     eax, edi
0x18004c016  jmp     short loc_18004C038
0x18004c018  lea     rcx, [rsp+2D8h+var_278]
0x18004c01d  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x18004c022  mov     eax, 80004003h
0x18004c027  jmp     short loc_18004C038
0x18004c029  lea     rcx, [rsp+2D8h+var_278]
0x18004c02e  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x18004c033  mov     eax, 80070057h
0x18004c038  mov     rcx, [rsp+2D8h+var_38]
0x18004c040  xor     rcx, rsp; StackCookie
0x18004c043  call    __security_check_cookie
0x18004c048  lea     r11, [rsp+2D8h+var_28]
0x18004c050  mov     rbx, [r11+38h]
0x18004c054  mov     rsi, [r11+48h]
0x18004c058  mov     rsp, r11
0x18004c05b  pop     r15
0x18004c05d  pop     r14
0x18004c05f  pop     r13
0x18004c061  pop     r12
0x18004c063  pop     rdi
0x18004c064  retn
```
