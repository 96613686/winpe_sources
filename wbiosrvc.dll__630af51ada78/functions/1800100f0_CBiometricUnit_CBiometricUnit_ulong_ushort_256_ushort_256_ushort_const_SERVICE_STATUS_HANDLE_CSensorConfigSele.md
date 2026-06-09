# CBiometricUnit::CBiometricUnit(ulong,ushort (*)[256],ushort (*)[256],ushort const *,SERVICE_STATUS_HANDLE__ *,CSensorConfigSelector *)

- ea: `0x1800100f0`
- end: `0x1800104ac`
- name: `??0CBiometricUnit@@QEAA@KPEAY0BAA@G0PEBGPEAUSERVICE_STATUS_HANDLE__@@PEAVCSensorConfigSelector@@@Z`
- size: `956`
- prototype: `CBiometricUnit *__fastcall(CBiometricUnit *this, int, unsigned __int16 (*)[256], unsigned __int16 (*)[256], const unsigned __int16 *, struct SERVICE_STATUS_HANDLE__ *, struct CSensorConfigSelector *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001119c`

## callees

- `0x18000367c`
- `0x1800052fc`
- `0x1800100f0`
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
- `0x180069cc8`
- `0x180078b58`
- `0x180079674`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010200`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001021b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010232`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010283`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010200`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001021b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010232`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010283`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001043b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001043b`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800101d2`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800101e9`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800101d2`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800101e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CBiometricUnit *__fastcall CBiometricUnit::CBiometricUnit(
        CBiometricUnit *this,
        int a2,
        unsigned __int16 (*a3)[256],
        unsigned __int16 (*a4)[256],
        const unsigned __int16 *a5,
        struct SERVICE_STATUS_HANDLE__ *a6,
        struct CSensorConfigSelector *a7)
{
  const unsigned __int16 *v10; // rbx
  _OWORD *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  _OWORD *v14; // rax
  __int64 v15; // rax
  int v17; // [rsp+30h] [rbp-61h] BYREF
  _QWORD v18[2]; // [rsp+38h] [rbp-59h] BYREF
  CPipeline *v19; // [rsp+48h] [rbp-49h]
  _BYTE v20[24]; // [rsp+50h] [rbp-41h] BYREF
  __int128 v21; // [rsp+68h] [rbp-29h] BYREF
  __int64 v22; // [rsp+78h] [rbp-19h]
  __int64 v23; // [rsp+80h] [rbp-11h]
  char v24[46]; // [rsp+88h] [rbp-9h] BYREF
  int v25; // [rsp+E8h] [rbp+57h] BYREF

  v25 = a2;
  v18[1] = this;
  v10 = a5;
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
  std::wstring::wstring((char *)this + 2672, v10);
  *((_QWORD *)this + 338) = 0;
  *((_BYTE *)this + 2712) = 0;
  *(_QWORD *)((char *)this + 2716) = 0;
  *((_DWORD *)this + 681) = 0;
  *((_QWORD *)this + 341) = 0;
  *((_BYTE *)this + 2736) = 0;
  *((_QWORD *)this + 343) = 0;
  *((_QWORD *)this + 344) = a7;
  *((_QWORD *)this + 345) = a6;
  *((_QWORD *)this + 346) = 0;
  *((_QWORD *)this + 347) = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
  *((_QWORD *)this + 348) = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
  *((_QWORD *)this + 349) = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 350) = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 351) = CreateEventW(0, 0, 0, 0);
  *((_DWORD *)this + 704) = 0;
  *((_QWORD *)this + 353) = 0;
  *((_QWORD *)this + 354) = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (char *)this + 2832,
    1);
  v18[0] = (char *)this + 2840;
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
  *((_DWORD *)this + 746) = 0;
  v17 = 0;
  strcpy(v24, "CBiometricUnit::CBiometricUnit");
  _lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_::_lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_(
    (_lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_ *)v20,
    (const char (*)[46])v24,
    (enum _WppTraceIndentType *)&v17,
    (struct CBiometricUnit *)&v25);
  lambda_5084c5583e093bacbd11a551e31a909d_::operator()(v20);
  v17 = 1;
  _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(v18, v20);
  v19 = (CPipeline *)operator new(0x8B0u);
  *((_QWORD *)this + 338) = CPipeline::CPipeline(v19, this);
  memset_0((char *)this + 84, 0, 0xA18u);
  *((_DWORD *)this + 20) = v25;
  *((_DWORD *)this + 21) = 0;
  *((_DWORD *)this + 745) = 0;
  v11 = (_OWORD *)((char *)this + 612);
  v12 = 4;
  v13 = 4;
  do
  {
    *v11 = *(_OWORD *)a3;
    v11[1] = *(_OWORD *)&(*a3)[8];
    v11[2] = *(_OWORD *)&(*a3)[16];
    v11[3] = *(_OWORD *)&(*a3)[24];
    v11[4] = *(_OWORD *)&(*a3)[32];
    v11[5] = *(_OWORD *)&(*a3)[40];
    v11[6] = *(_OWORD *)&(*a3)[48];
    v11[7] = *(_OWORD *)&(*a3)[56];
    v11 += 8;
    a3 = (unsigned __int16 (*)[256])((char *)a3 + 128);
    --v13;
  }
  while ( v13 );
  v14 = (_OWORD *)((char *)this + 100);
  do
  {
    *v14 = *(_OWORD *)a4;
    v14[1] = *(_OWORD *)&(*a4)[8];
    v14[2] = *(_OWORD *)&(*a4)[16];
    v14[3] = *(_OWORD *)&(*a4)[24];
    v14[4] = *(_OWORD *)&(*a4)[32];
    v14[5] = *(_OWORD *)&(*a4)[40];
    v14[6] = *(_OWORD *)&(*a4)[48];
    v14[7] = *(_OWORD *)&(*a4)[56];
    v14 += 8;
    a4 = (unsigned __int16 (*)[256])((char *)a4 + 128);
    --v12;
  }
  while ( v12 );
  SetEvent(*((HANDLE *)this + 350));
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v15 = std::_WChar_traits<unsigned short>::length((char *)this + 100);
  std::wstring::_Construct<1,unsigned short const *>(&v21, (char *)this + 100, v15);
  CBioTraceLogging::OnBiometricUnitCreate(&v21);
  std::wstring::_Tidy_deallocate(&v21);
  WppTraceUnwinder__lambda_5084c5583e093bacbd11a551e31a909d____::_WppTraceUnwinder__lambda_5084c5583e093bacbd11a551e31a909d____(v18);
  return this;
}

```

## disassembly

```asm
0x1800100f0  mov     [rsp-8+arg_10], rbx
0x1800100f5  mov     [rsp-8+arg_8], edx
0x1800100f9  push    rbp
0x1800100fa  push    rsi
0x1800100fb  push    rdi
0x1800100fc  push    r14
0x1800100fe  push    r15
0x180010100  lea     rbp, [rsp-1Fh]
0x180010105  sub     rsp, 0B0h
0x18001010c  mov     rax, cs:__security_cookie
0x180010113  xor     rax, rsp
0x180010116  mov     qword ptr [rbp+3Fh+var_48+20h], rax
0x18001011a  mov     rdi, r9
0x18001011d  mov     rsi, r8
0x180010120  mov     r14, rcx
0x180010123  mov     [rbp+3Fh+var_90], rcx
0x180010127  mov     rbx, [rbp+3Fh+arg_20]
0x18001012b  call    ??0lockable_object@winbio@@QEAA@XZ; winbio::lockable_object::lockable_object(void)
0x180010130  nop
0x180010131  xor     r15d, r15d
0x180010134  mov     [r14+18h], r15
0x180010138  mov     [r14+20h], r15
0x18001013c  lea     rax, ??_7CBiometricUnit@@6Blockable_object@winbio@@@; const CBiometricUnit::`vftable'{for `winbio::lockable_object'}
0x180010143  mov     [r14], rax
0x180010146  lea     rax, ??_7CBiometricUnit@@6BBindingHelper@@@; const CBiometricUnit::`vftable'{for `BindingHelper'}
0x18001014d  mov     [r14+10h], rax
0x180010151  mov     [r14+28h], r15d
0x180010155  mov     [r14+30h], r15
0x180010159  mov     [r14+38h], r15
0x18001015d  mov     [r14+40h], r15
0x180010161  mov     [r14+48h], r15
0x180010165  lea     rcx, [r14+0A70h]
0x18001016c  mov     rdx, rbx
0x18001016f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180010174  nop
0x180010175  mov     [r14+0A90h], r15
0x18001017c  mov     [r14+0A98h], r15b
0x180010183  mov     [r14+0A9Ch], r15
0x18001018a  mov     [r14+0AA4h], r15d
0x180010191  mov     [r14+0AA8h], r15
0x180010198  mov     [r14+0AB0h], r15b
0x18001019f  mov     [r14+0AB8h], r15
0x1800101a6  mov     rax, [rbp+3Fh+arg_30]
0x1800101aa  mov     [r14+0AC0h], rax
0x1800101b1  mov     rax, [rbp+3Fh+arg_28]
0x1800101b5  mov     [r14+0AC8h], rax
0x1800101bc  mov     [r14+0AD0h], r15
0x1800101c3  xor     r9d, r9d; lpName
0x1800101c6  mov     ebx, 7FFFFFFFh
0x1800101cb  mov     r8d, ebx; lMaximumCount
0x1800101ce  xor     edx, edx; lInitialCount
0x1800101d0  xor     ecx, ecx; lpSemaphoreAttributes
0x1800101d2  call    cs:__imp_CreateSemaphoreW
0x1800101d8  mov     [r14+0AD8h], rax
0x1800101df  xor     r9d, r9d; lpName
0x1800101e2  mov     r8d, ebx; lMaximumCount
0x1800101e5  xor     edx, edx; lInitialCount
0x1800101e7  xor     ecx, ecx; lpSemaphoreAttributes
0x1800101e9  call    cs:__imp_CreateSemaphoreW
0x1800101ef  mov     [r14+0AE0h], rax
0x1800101f6  xor     r9d, r9d; lpName
0x1800101f9  xor     r8d, r8d; bInitialState
0x1800101fc  xor     edx, edx; bManualReset
0x1800101fe  xor     ecx, ecx; lpEventAttributes
0x180010200  call    cs:__imp_CreateEventW
0x180010206  mov     [r14+0AE8h], rax
0x18001020d  xor     r9d, r9d; lpName
0x180010210  xor     r8d, r8d; bInitialState
0x180010213  lea     ebx, [r15+1]
0x180010217  mov     edx, ebx; bManualReset
0x180010219  xor     ecx, ecx; lpEventAttributes
0x18001021b  call    cs:__imp_CreateEventW
0x180010221  mov     [r14+0AF0h], rax
0x180010228  xor     r9d, r9d; lpName
0x18001022b  xor     r8d, r8d; bInitialState
0x18001022e  xor     edx, edx; bManualReset
0x180010230  xor     ecx, ecx; lpEventAttributes
0x180010232  call    cs:__imp_CreateEventW
0x180010238  mov     [r14+0AF8h], rax
0x18001023f  mov     [r14+0B00h], r15d
0x180010246  mov     [r14+0B08h], r15
0x18001024d  lea     rcx, [r14+0B10h]
0x180010254  mov     [rbp+3Fh+var_98], rcx
0x180010258  mov     [rcx], r15
0x18001025b  mov     edx, ebx
0x18001025d  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180010262  nop
0x180010263  lea     rcx, [r14+0B18h]
0x18001026a  mov     [rbp+3Fh+var_98], rcx
0x18001026e  mov     [rcx], r15
0x180010271  mov     edx, ebx
0x180010273  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180010278  nop
0x180010279  xor     r9d, r9d; lpName
0x18001027c  xor     r8d, r8d; bInitialState
0x18001027f  xor     edx, edx; bManualReset
0x180010281  xor     ecx, ecx; lpEventAttributes
0x180010283  call    cs:__imp_CreateEventW
0x180010289  mov     [r14+0B20h], rax
0x180010290  mov     dword ptr [r14+0B28h], 80004005h
0x18001029b  mov     [r14+0B30h], r15
0x1800102a2  mov     [r14+0B38h], r15
0x1800102a9  mov     [r14+0B40h], r15
0x1800102b0  mov     [r14+0B48h], r15
0x1800102b7  lea     rcx, [r14+0B50h]
0x1800102be  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1800102c3  nop
0x1800102c4  mov     [r14+0B68h], r15
0x1800102cb  mov     [r14+0B70h], r15
0x1800102d2  lea     rcx, [r14+0B78h]
0x1800102d9  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1800102de  nop
0x1800102df  xor     eax, eax
0x1800102e1  mov     [r14+0B90h], rax
0x1800102e8  mov     [r14+0B98h], rax
0x1800102ef  mov     [r14+0BA0h], r15d
0x1800102f6  mov     [r14+0BA8h], r15d
0x1800102fd  mov     [rbp+3Fh+var_A0], r15d
0x180010301  movups  xmm0, xmmword ptr cs:aCbiometricunit_8; "CBiometricUnit::CBiometricUnit"
0x180010308  movups  xmmword ptr [rbp+3Fh+var_48], xmm0
0x18001030c  movups  xmm1, xmmword ptr cs:aCbiometricunit_8+0Fh; ":CBiometricUnit"
0x180010313  movups  xmmword ptr [rbp+3Fh+var_48+0Fh], xmm1
0x180010317  lea     r9, [rbp+3Fh+arg_8]; struct CBiometricUnit *
0x18001031b  lea     r8, [rbp+3Fh+var_A0]; enum _WppTraceIndentType *
0x18001031f  lea     rdx, [rbp+3Fh+var_48]; char (*)[46]
0x180010323  lea     rcx, [rbp+3Fh+var_80]; this
0x180010327  call    ??0_lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_@@QEAA@AEAY0CO@$$CBDAEAW4_WppTraceIndentType@@PEAVCBiometricUnit@@@Z; _lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_::_lambda_f3ea3dba11ac062fb299e6b9fa99ba2c_(char const (&)[46],_WppTraceIndentType &,CBiometricUnit *)
0x18001032c  lea     rcx, [rbp+3Fh+var_80]
0x180010330  call    _lambda_5084c5583e093bacbd11a551e31a909d___operator__
0x180010335  mov     [rbp+3Fh+var_A0], ebx
0x180010338  lea     rdx, [rbp+3Fh+var_80]
0x18001033c  lea     rcx, [rbp+3Fh+var_98]
0x180010340  call    ??0_lambda_1d8e544947e376896bbe6f02de9fb8f9_@@QEAA@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@Z; _lambda_1d8e544947e376896bbe6f02de9fb8f9_::_lambda_1d8e544947e376896bbe6f02de9fb8f9_(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *)
0x180010345  nop
0x180010346  mov     ecx, 8B0h; Size
0x18001034b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010350  mov     [rbp+3Fh+var_88], rax
0x180010354  mov     rdx, r14; struct CBiometricUnit *
0x180010357  mov     rcx, rax; this
0x18001035a  call    ??0CPipeline@@QEAA@PEAVCBiometricUnit@@@Z; CPipeline::CPipeline(CBiometricUnit *)
0x18001035f  mov     [r14+0A90h], rax
0x180010366  lea     rcx, [r14+54h]; void *
0x18001036a  xor     edx, edx; Val
0x18001036c  mov     r8d, 0A18h; Size
0x180010372  call    memset_0
0x180010377  mov     eax, [rbp+3Fh+arg_8]
0x18001037a  mov     [r14+50h], eax
0x18001037e  mov     [r14+54h], r15d
0x180010382  mov     [r14+0BA4h], r15d
0x180010389  lea     rax, [r14+264h]
0x180010390  lea     ecx, [rbx+3]
0x180010393  mov     edx, ecx
0x180010395  lea     r8d, [rbx+7Fh]
0x180010399  movups  xmm0, xmmword ptr [rsi]
0x18001039c  movups  xmmword ptr [rax], xmm0
0x18001039f  movups  xmm1, xmmword ptr [rsi+10h]
0x1800103a3  movups  xmmword ptr [rax+10h], xmm1
0x1800103a7  movups  xmm0, xmmword ptr [rsi+20h]
0x1800103ab  movups  xmmword ptr [rax+20h], xmm0
0x1800103af  movups  xmm1, xmmword ptr [rsi+30h]
0x1800103b3  movups  xmmword ptr [rax+30h], xmm1
0x1800103b7  movups  xmm0, xmmword ptr [rsi+40h]
0x1800103bb  movups  xmmword ptr [rax+40h], xmm0
0x1800103bf  movups  xmm1, xmmword ptr [rsi+50h]
0x1800103c3  movups  xmmword ptr [rax+50h], xmm1
0x1800103c7  movups  xmm0, xmmword ptr [rsi+60h]
0x1800103cb  movups  xmmword ptr [rax+60h], xmm0
0x1800103cf  movups  xmm1, xmmword ptr [rsi+70h]
0x1800103d3  movups  xmmword ptr [rax+70h], xmm1
0x1800103d7  add     rax, r8
0x1800103da  add     rsi, r8
0x1800103dd  sub     rdx, 1
0x1800103e1  jnz     short loc_180010399
0x1800103e3  lea     rbx, [r14+64h]
0x1800103e7  mov     rax, rbx
0x1800103ea  movups  xmm0, xmmword ptr [rdi]
0x1800103ed  movups  xmmword ptr [rax], xmm0
0x1800103f0  movups  xmm1, xmmword ptr [rdi+10h]
0x1800103f4  movups  xmmword ptr [rax+10h], xmm1
0x1800103f8  movups  xmm0, xmmword ptr [rdi+20h]
0x1800103fc  movups  xmmword ptr [rax+20h], xmm0
0x180010400  movups  xmm1, xmmword ptr [rdi+30h]
0x180010404  movups  xmmword ptr [rax+30h], xmm1
0x180010408  movups  xmm0, xmmword ptr [rdi+40h]
0x18001040c  movups  xmmword ptr [rax+40h], xmm0
0x180010410  movups  xmm1, xmmword ptr [rdi+50h]
0x180010414  movups  xmmword ptr [rax+50h], xmm1
0x180010418  movups  xmm0, xmmword ptr [rdi+60h]
0x18001041c  movups  xmmword ptr [rax+60h], xmm0
0x180010420  movups  xmm1, xmmword ptr [rdi+70h]
0x180010424  movups  xmmword ptr [rax+70h], xmm1
0x180010428  add     rax, r8
0x18001042b  add     rdi, r8
0x18001042e  sub     rcx, 1
0x180010432  jnz     short loc_1800103EA
0x180010434  mov     rcx, [r14+0AF0h]; hEvent
0x18001043b  call    cs:__imp_SetEvent
0x180010441  xorps   xmm0, xmm0
0x180010444  movups  [rbp+3Fh+var_68], xmm0
0x180010448  mov     [rbp+3Fh+var_58], r15
0x18001044c  mov     [rbp+3Fh+var_50], r15
0x180010450  mov     rcx, rbx
0x180010453  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180010458  mov     r8, rax
0x18001045b  mov     rdx, rbx
0x18001045e  lea     rcx, [rbp+3Fh+var_68]
0x180010462  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180010467  nop
0x180010468  lea     rcx, [rbp+3Fh+var_68]
0x18001046c  call    ?OnBiometricUnitCreate@CBioTraceLogging@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CBioTraceLogging::OnBiometricUnitCreate(std::wstring const &)
0x180010471  nop
0x180010472  lea     rcx, [rbp+3Fh+var_68]
0x180010476  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001047b  nop
0x18001047c  lea     rcx, [rbp+3Fh+var_98]
0x180010480  call    WppTraceUnwinder__lambda_5084c5583e093bacbd11a551e31a909d_______WppTraceUnwinder__lambda_5084c5583e093bacbd11a551e31a909d____
0x180010485  nop
0x180010486  mov     rax, r14
0x180010489  mov     rcx, qword ptr [rbp+3Fh+var_48+20h]
0x18001048d  xor     rcx, rsp; StackCookie
0x180010490  call    __security_check_cookie
0x180010495  mov     rbx, [rsp+0D0h+arg_10]
0x18001049d  add     rsp, 0B0h
0x1800104a4  pop     r15
0x1800104a6  pop     r14
0x1800104a8  pop     rdi
0x1800104a9  pop     rsi
0x1800104aa  pop     rbp
0x1800104ab  retn
```
