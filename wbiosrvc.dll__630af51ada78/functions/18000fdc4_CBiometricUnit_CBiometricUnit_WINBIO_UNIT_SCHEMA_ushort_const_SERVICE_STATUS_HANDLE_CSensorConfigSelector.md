# CBiometricUnit::CBiometricUnit(_WINBIO_UNIT_SCHEMA &,ushort const *,SERVICE_STATUS_HANDLE__ *,CSensorConfigSelector *)

- ea: `0x18000fdc4`
- end: `0x1800100aa`
- name: `??0CBiometricUnit@@QEAA@AEAU_WINBIO_UNIT_SCHEMA@@PEBGPEAUSERVICE_STATUS_HANDLE__@@PEAVCSensorConfigSelector@@@Z`
- size: `742`
- prototype: `CBiometricUnit *__fastcall(CBiometricUnit *this, struct _WINBIO_UNIT_SCHEMA *, const unsigned __int16 *, struct SERVICE_STATUS_HANDLE__ *, struct CSensorConfigSelector *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010944`

## callees

- `0x18000367c`
- `0x1800052fc`
- `0x1800128c0`
- `0x18001434c`
- `0x180014854`
- `0x1800148b4`
- `0x180014938`
- `0x18003eb6c`
- `0x180048d54`
- `0x180055928`
- `0x1800559b0`
- `0x180068f60`
- `0x18006963c`
- `0x18006b0b5`
- `0x180078a68`
- `0x180079184`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fec4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fedf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fef6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ff40`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fec4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fedf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fef6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ff40`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010038`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010038`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18000fe96`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18000fead`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18000fe96`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18000fead`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
CBiometricUnit *__fastcall CBiometricUnit::CBiometricUnit(
        CBiometricUnit *this,
        struct _WINBIO_UNIT_SCHEMA *a2,
        const unsigned __int16 *a3,
        struct SERVICE_STATUS_HANDLE__ *a4,
        struct CSensorConfigSelector *a5)
{
  __int64 v9; // rax
  __int64 v10; // rcx
  int v12; // [rsp+30h] [rbp-51h] BYREF
  _QWORD v13[2]; // [rsp+38h] [rbp-49h] BYREF
  CPipeline *v14; // [rsp+48h] [rbp-39h]
  _BYTE v15[24]; // [rsp+50h] [rbp-31h] BYREF
  __int128 v16; // [rsp+68h] [rbp-19h] BYREF
  __int64 v17; // [rsp+78h] [rbp-9h]
  __int64 v18; // [rsp+80h] [rbp-1h]
  char v19[46]; // [rsp+88h] [rbp+7h] BYREF

  v13[1] = this;
  winbio::lockable_object::lockable_object(this);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *(_QWORD *)this = &CBiometricUnit::`vftable'{for `winbio::lockable_object'};
  *((_QWORD *)this + 2) = &CBiometricUnit::`vftable'{for `BindingHelper'};
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  std::wstring::wstring((char *)this + 2672, a3);
  *((_QWORD *)this + 338) = 0;
  *((_BYTE *)this + 2712) = 0;
  *(_QWORD *)((char *)this + 2716) = 0;
  *((_DWORD *)this + 681) = 0;
  *((_BYTE *)this + 2736) = 0;
  *((_QWORD *)this + 343) = 0;
  *((_QWORD *)this + 344) = a5;
  *((_QWORD *)this + 345) = a4;
  *((_QWORD *)this + 346) = 0;
  *((_QWORD *)this + 347) = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
  *((_QWORD *)this + 348) = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
  *((_QWORD *)this + 349) = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 350) = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 351) = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 353) = 0;
  *((_QWORD *)this + 354) = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (char *)this + 2832,
    1);
  v13[0] = (char *)this + 2840;
  *((_QWORD *)this + 355) = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (char *)this + 2840,
    1);
  *((_QWORD *)this + 356) = CreateEventW(0, 0, 0, 0);
  *((_DWORD *)this + 714) = -2147467259;
  *((_QWORD *)this + 358) = 0;
  *((_QWORD *)this + 359) = 0;
  *((_QWORD *)this + 360) = 0;
  *((_QWORD *)this + 361) = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>((char *)this + 2896);
  *((_QWORD *)this + 365) = 0;
  *((_QWORD *)this + 366) = 0;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>((char *)this + 2936);
  *((_QWORD *)this + 370) = 0;
  *((_QWORD *)this + 371) = 0;
  *((_DWORD *)this + 744) = 0;
  v12 = 0;
  strcpy(v19, "CBiometricUnit::CBiometricUnit");
  _lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_::_lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_(
    (_lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_ *)v15,
    (const char (*)[46])v19,
    (enum _WppTraceIndentType *)&v12,
    (struct CBiometricUnit *)a2);
  lambda_301296fb6d6e4680e4f6722f41dc0aee_::operator()(v15);
  v12 = 1;
  _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(v13, v15);
  v14 = (CPipeline *)operator new(0x8B0u);
  *((_QWORD *)this + 338) = CPipeline::CPipeline(v14, this);
  memcpy_0((char *)this + 80, a2, 0xA1Cu);
  *((_DWORD *)this + 21) = 0;
  SetEvent(*((HANDLE *)this + 350));
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v9 = std::_WChar_traits<unsigned short>::length(a2->DeviceInstanceId);
  std::wstring::_Construct<1,unsigned short const *>(&v16, v10, v9);
  CBioTraceLogging::OnBiometricUnitCreate(&v16);
  std::wstring::_Tidy_deallocate(&v16);
  WppTraceUnwinder__lambda_301296fb6d6e4680e4f6722f41dc0aee____::_WppTraceUnwinder__lambda_301296fb6d6e4680e4f6722f41dc0aee____(v13);
  return this;
}

```

## disassembly

```asm
0x18000fdc4  mov     [rsp-8+arg_18], rbx
0x18000fdc9  push    rbp
0x18000fdca  push    rsi
0x18000fdcb  push    rdi
0x18000fdcc  push    r14
0x18000fdce  push    r15
0x18000fdd0  lea     rbp, [rsp-2Fh]
0x18000fdd5  sub     rsp, 0B0h
0x18000fddc  mov     rax, cs:__security_cookie
0x18000fde3  xor     rax, rsp
0x18000fde6  mov     qword ptr [rbp+4Fh+var_48+20h], rax
0x18000fdea  mov     rdi, r9
0x18000fded  mov     rbx, r8
0x18000fdf0  mov     rsi, rdx
0x18000fdf3  mov     r14, rcx
0x18000fdf6  mov     [rbp+4Fh+var_90], rcx
0x18000fdfa  call    ??0lockable_object@winbio@@QEAA@XZ; winbio::lockable_object::lockable_object(void)
0x18000fdff  nop
0x18000fe00  xor     r15d, r15d
0x18000fe03  mov     [r14+18h], r15
0x18000fe07  mov     [r14+20h], r15
0x18000fe0b  lea     rax, ??_7CBiometricUnit@@6Blockable_object@winbio@@@; const CBiometricUnit::`vftable'{for `winbio::lockable_object'}
0x18000fe12  mov     [r14], rax
0x18000fe15  lea     rax, ??_7CBiometricUnit@@6BBindingHelper@@@; const CBiometricUnit::`vftable'{for `BindingHelper'}
0x18000fe1c  mov     [r14+10h], rax
0x18000fe20  mov     [r14+28h], r15d
0x18000fe24  mov     [r14+30h], r15
0x18000fe28  mov     [r14+38h], r15
0x18000fe2c  mov     [r14+40h], r15
0x18000fe30  mov     [r14+48h], r15
0x18000fe34  lea     rcx, [r14+0A70h]
0x18000fe3b  mov     rdx, rbx
0x18000fe3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000fe43  nop
0x18000fe44  mov     [r14+0A90h], r15
0x18000fe4b  mov     [r14+0A98h], r15b
0x18000fe52  mov     [r14+0A9Ch], r15
0x18000fe59  mov     [r14+0AA4h], r15d
0x18000fe60  mov     [r14+0AB0h], r15b
0x18000fe67  mov     [r14+0AB8h], r15
0x18000fe6e  mov     rax, [rbp+4Fh+arg_20]
0x18000fe72  mov     [r14+0AC0h], rax
0x18000fe79  mov     [r14+0AC8h], rdi
0x18000fe80  mov     [r14+0AD0h], r15
0x18000fe87  xor     r9d, r9d; lpName
0x18000fe8a  mov     ebx, 7FFFFFFFh
0x18000fe8f  mov     r8d, ebx; lMaximumCount
0x18000fe92  xor     edx, edx; lInitialCount
0x18000fe94  xor     ecx, ecx; lpSemaphoreAttributes
0x18000fe96  call    cs:__imp_CreateSemaphoreW
0x18000fe9c  mov     [r14+0AD8h], rax
0x18000fea3  xor     r9d, r9d; lpName
0x18000fea6  mov     r8d, ebx; lMaximumCount
0x18000fea9  xor     edx, edx; lInitialCount
0x18000feab  xor     ecx, ecx; lpSemaphoreAttributes
0x18000fead  call    cs:__imp_CreateSemaphoreW
0x18000feb3  mov     [r14+0AE0h], rax
0x18000feba  xor     r9d, r9d; lpName
0x18000febd  xor     r8d, r8d; bInitialState
0x18000fec0  xor     edx, edx; bManualReset
0x18000fec2  xor     ecx, ecx; lpEventAttributes
0x18000fec4  call    cs:__imp_CreateEventW
0x18000feca  mov     [r14+0AE8h], rax
0x18000fed1  xor     r9d, r9d; lpName
0x18000fed4  xor     r8d, r8d; bInitialState
0x18000fed7  lea     ebx, [r15+1]
0x18000fedb  mov     edx, ebx; bManualReset
0x18000fedd  xor     ecx, ecx; lpEventAttributes
0x18000fedf  call    cs:__imp_CreateEventW
0x18000fee5  mov     [r14+0AF0h], rax
0x18000feec  xor     r9d, r9d; lpName
0x18000feef  xor     r8d, r8d; bInitialState
0x18000fef2  xor     edx, edx; bManualReset
0x18000fef4  xor     ecx, ecx; lpEventAttributes
0x18000fef6  call    cs:__imp_CreateEventW
0x18000fefc  mov     [r14+0AF8h], rax
0x18000ff03  mov     [r14+0B08h], r15
0x18000ff0a  lea     rcx, [r14+0B10h]
0x18000ff11  mov     [rbp+4Fh+var_98], rcx
0x18000ff15  mov     [rcx], r15
0x18000ff18  mov     edx, ebx
0x18000ff1a  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000ff1f  nop
0x18000ff20  lea     rcx, [r14+0B18h]
0x18000ff27  mov     [rbp+4Fh+var_98], rcx
0x18000ff2b  mov     [rcx], r15
0x18000ff2e  mov     edx, ebx
0x18000ff30  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000ff35  nop
0x18000ff36  xor     r9d, r9d; lpName
0x18000ff39  xor     r8d, r8d; bInitialState
0x18000ff3c  xor     edx, edx; bManualReset
0x18000ff3e  xor     ecx, ecx; lpEventAttributes
0x18000ff40  call    cs:__imp_CreateEventW
0x18000ff46  mov     [r14+0B20h], rax
0x18000ff4d  mov     dword ptr [r14+0B28h], 80004005h
0x18000ff58  mov     [r14+0B30h], r15
0x18000ff5f  mov     [r14+0B38h], r15
0x18000ff66  mov     [r14+0B40h], r15
0x18000ff6d  mov     [r14+0B48h], r15
0x18000ff74  lea     rcx, [r14+0B50h]
0x18000ff7b  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18000ff80  nop
0x18000ff81  mov     [r14+0B68h], r15
0x18000ff88  mov     [r14+0B70h], r15
0x18000ff8f  lea     rcx, [r14+0B78h]
0x18000ff96  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18000ff9b  nop
0x18000ff9c  xor     eax, eax
0x18000ff9e  mov     [r14+0B90h], rax
0x18000ffa5  mov     [r14+0B98h], rax
0x18000ffac  mov     [r14+0BA0h], r15d
0x18000ffb3  mov     [rbp+4Fh+var_A0], r15d
0x18000ffb7  movups  xmm0, xmmword ptr cs:aCbiometricunit_8; "CBiometricUnit::CBiometricUnit"
0x18000ffbe  movups  xmmword ptr [rbp+4Fh+var_48], xmm0
0x18000ffc2  movups  xmm1, xmmword ptr cs:aCbiometricunit_8+0Fh; ":CBiometricUnit"
0x18000ffc9  movups  xmmword ptr [rbp+4Fh+var_48+0Fh], xmm1
0x18000ffcd  mov     r9, rsi; struct CBiometricUnit *
0x18000ffd0  lea     r8, [rbp+4Fh+var_A0]; enum _WppTraceIndentType *
0x18000ffd4  lea     rdx, [rbp+4Fh+var_48]; char (*)[46]
0x18000ffd8  lea     rcx, [rbp+4Fh+var_80]; this
0x18000ffdc  call    ??0_lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_@@QEAA@AEAY0CO@$$CBDAEAW4_WppTraceIndentType@@PEAVCBiometricUnit@@@Z; _lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_::_lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_(char const (&)[46],_WppTraceIndentType &,CBiometricUnit *)
0x18000ffe1  lea     rcx, [rbp+4Fh+var_80]
0x18000ffe5  call    _lambda_301296fb6d6e4680e4f6722f41dc0aee___operator__
0x18000ffea  mov     [rbp+4Fh+var_A0], ebx
0x18000ffed  lea     rdx, [rbp+4Fh+var_80]
0x18000fff1  lea     rcx, [rbp+4Fh+var_98]
0x18000fff5  call    ??0_lambda_1d8e544947e376896bbe6f02de9fb8f9_@@QEAA@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@Z; _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *)
0x18000fffa  nop
0x18000fffb  mov     ecx, 8B0h; Size
0x180010000  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010005  mov     [rbp+4Fh+var_88], rax
0x180010009  mov     rdx, r14; struct CBiometricUnit *
0x18001000c  mov     rcx, rax; this
0x18001000f  call    ??0CPipeline@@QEAA@PEAVCBiometricUnit@@@Z; CPipeline::CPipeline(CBiometricUnit *)
0x180010014  mov     [r14+0A90h], rax
0x18001001b  lea     rcx, [r14+50h]; void *
0x18001001f  mov     rdx, rsi; Src
0x180010022  mov     r8d, 0A1Ch; Size
0x180010028  call    memcpy_0
0x18001002d  mov     [r14+54h], r15d
0x180010031  mov     rcx, [r14+0AF0h]; hEvent
0x180010038  call    cs:__imp_SetEvent
0x18001003e  lea     rcx, [rsi+14h]
0x180010042  xorps   xmm0, xmm0
0x180010045  movups  [rbp+4Fh+var_68], xmm0
0x180010049  mov     [rbp+4Fh+var_58], r15
0x18001004d  mov     [rbp+4Fh+var_50], r15
0x180010051  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180010056  mov     r8, rax
0x180010059  mov     rdx, rcx
0x18001005c  lea     rcx, [rbp+4Fh+var_68]
0x180010060  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180010065  nop
0x180010066  lea     rcx, [rbp+4Fh+var_68]
0x18001006a  call    ?OnBiometricUnitCreate@CBioTraceLogging@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CBioTraceLogging::OnBiometricUnitCreate(std::wstring const &)
0x18001006f  nop
0x180010070  lea     rcx, [rbp+4Fh+var_68]
0x180010074  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010079  nop
0x18001007a  lea     rcx, [rbp+4Fh+var_98]
0x18001007e  call    WppTraceUnwinder__lambda_301296fb6d6e4680e4f6722f41dc0aee_______WppTraceUnwinder__lambda_301296fb6d6e4680e4f6722f41dc0aee____
0x180010083  nop
0x180010084  mov     rax, r14
0x180010087  mov     rcx, qword ptr [rbp+4Fh+var_48+20h]
0x18001008b  xor     rcx, rsp; StackCookie
0x18001008e  call    __security_check_cookie
0x180010093  mov     rbx, [rsp+0D0h+arg_18]
0x18001009b  add     rsp, 0B0h
0x1800100a2  pop     r15
0x1800100a4  pop     r14
0x1800100a6  pop     rdi
0x1800100a7  pop     rsi
0x1800100a8  pop     rbp
0x1800100a9  retn
```
