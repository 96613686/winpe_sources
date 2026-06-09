# ComputeService::Vmwp::ProcessAttributes::AttributeList::AttributeList(ComputeService::Vmwp::ProcessAttributes::AttributeListOptions &)

- ea: `0x1400b7604`
- end: `0x1400b7c48`
- name: `??0AttributeList@ProcessAttributes@Vmwp@ComputeService@@QEAA@AEAUAttributeListOptions@123@@Z`
- size: `1604`
- prototype: `__int64 __fastcall(ComputeService::Vmwp::ProcessAttributes::AttributeList *__hidden this, struct ComputeService::Vmwp::ProcessAttributes::AttributeListOptions *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400b6a4c`

## callees

- `0x14001bce0`
- `0x14005be10`
- `0x140080180`
- `0x1400b7604`
- `0x1400c4154`
- `0x1400ef5dc`
- `0x1400f26c8`
- `0x1400f3924`
- `0x14010580c`
- `0x14010685c`
- `0x140106a68`
- `0x140106acc`
- `0x140106af8`
- `0x1401332f0`
- `0x14023ab8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b7b35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b7b35`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1400b7b25`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1400b7bbc`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1400b7b25`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1400b7bbc`

## string_xrefs

- `0x1400b7b59`: `onecore\vm\compute\shared\vmwp\lib\vmprocattributes.cpp`
- `0x1400b7bea`: `onecore\vm\compute\shared\vmwp\lib\vmprocattributes.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ComputeService::Vmwp::ProcessAttributes::AttributeList *__fastcall ComputeService::Vmwp::ProcessAttributes::AttributeList::AttributeList(
        ComputeService::Vmwp::ProcessAttributes::AttributeList *this,
        struct ComputeService::Vmwp::ProcessAttributes::AttributeListOptions *a2)
{
  __int64 v2; // rax
  unsigned int v3; // eax
  const char *v4; // r9
  unsigned int v6; // [rsp+20h] [rbp-2B8h]
  DWORD dwAttributeCount; // [rsp+50h] [rbp-288h]
  bool v8; // [rsp+54h] [rbp-284h]
  DWORD LastError; // [rsp+60h] [rbp-278h]
  bool v10; // [rsp+6Ch] [rbp-26Ch]
  struct _PROC_THREAD_ATTRIBUTE_LIST *lpAttributeList; // [rsp+78h] [rbp-260h]
  int *v12; // [rsp+80h] [rbp-258h]
  int *v13; // [rsp+88h] [rbp-250h]
  __int64 v14; // [rsp+B0h] [rbp-228h]
  __int64 v15; // [rsp+B8h] [rbp-220h]
  __int64 v16; // [rsp+C0h] [rbp-218h]
  __int64 v17; // [rsp+D0h] [rbp-208h]
  __int64 v18; // [rsp+D8h] [rbp-200h]
  int v19; // [rsp+E0h] [rbp-1F8h]
  int v20; // [rsp+E8h] [rbp-1F0h]
  int v21; // [rsp+F0h] [rbp-1E8h]
  _BYTE v22[24]; // [rsp+100h] [rbp-1D8h] BYREF
  _BYTE v23[24]; // [rsp+118h] [rbp-1C0h] BYREF
  _BYTE v24[24]; // [rsp+130h] [rbp-1A8h] BYREF
  _BYTE v25[24]; // [rsp+148h] [rbp-190h] BYREF
  _BYTE v26[24]; // [rsp+160h] [rbp-178h] BYREF
  _BYTE v27[24]; // [rsp+178h] [rbp-160h] BYREF
  _BYTE v28[24]; // [rsp+190h] [rbp-148h] BYREF
  _BYTE v29[24]; // [rsp+1A8h] [rbp-130h] BYREF
  bool v30; // [rsp+1C0h] [rbp-118h] BYREF
  char v31; // [rsp+1C1h] [rbp-117h] BYREF
  bool v32; // [rsp+1C2h] [rbp-116h] BYREF
  char has_value; // [rsp+1C3h] [rbp-115h] BYREF
  bool v34; // [rsp+1C4h] [rbp-114h] BYREF
  bool v35; // [rsp+1C5h] [rbp-113h] BYREF
  bool v36; // [rsp+1C6h] [rbp-112h] BYREF
  bool v37; // [rsp+1C7h] [rbp-111h] BYREF
  int v38; // [rsp+1C8h] [rbp-110h] BYREF
  ULONG_PTR Size; // [rsp+1D0h] [rbp-108h] BYREF
  int v40; // [rsp+1D8h] [rbp-100h] BYREF
  int v41; // [rsp+1DCh] [rbp-FCh] BYREF
  int v42; // [rsp+1E0h] [rbp-F8h] BYREF
  int v43; // [rsp+1E4h] [rbp-F4h] BYREF
  int v44; // [rsp+1E8h] [rbp-F0h] BYREF
  int v45; // [rsp+1ECh] [rbp-ECh] BYREF
  int v46; // [rsp+1F0h] [rbp-E8h] BYREF
  int v47; // [rsp+1F4h] [rbp-E4h] BYREF
  int v48; // [rsp+1F8h] [rbp-E0h] BYREF
  _BYTE v49[192]; // [rsp+200h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(this);
  *((_QWORD *)this + 3) = 0;
  v44 = 0;
  v42 = 0;
  if ( (unsigned __int8)std::optional<unsigned long>::has_value((char *)a2 + 56) )
    v13 = (int *)std::optional<unsigned long>::value((char *)a2 + 56);
  else
    v13 = &v44;
  if ( (unsigned __int8)std::optional<unsigned long>::has_value((char *)a2 + 72) )
    v12 = (int *)std::optional<unsigned long>::value((char *)a2 + 72);
  else
    v12 = &v42;
  v37 = *((_QWORD *)a2 + 5) != 0;
  v30 = *((_QWORD *)a2 + 6) != 0;
  v10 = *(_QWORD *)a2 || *((_QWORD *)a2 + 1);
  v36 = v10;
  v8 = *((_QWORD *)a2 + 2) || *((_QWORD *)a2 + 3);
  v35 = v8;
  v34 = *((_DWORD *)a2 + 8) != 0;
  has_value = std::optional<unsigned long>::has_value((char *)a2 + 56);
  v32 = (unsigned __int8)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&long FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>>::operator bool((char *)a2 + 64) != 0;
  v31 = std::optional<unsigned long>::has_value((char *)a2 + 72);
  v45 = 131074;
  v46 = 131085;
  v47 = 131079;
  v48 = 131096;
  v43 = 131086;
  v38 = 131083;
  v40 = 131081;
  v41 = 131087;
  v16 = std::forward_as_tuple<bool &,unsigned long &,int &>(v23, &v31, v12, &v41);
  v2 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&long FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>>::get((char *)a2 + 64);
  v15 = std::forward_as_tuple<bool &,unsigned long &,int &>(v24, &v32, v2, &v40);
  v14 = std::forward_as_tuple<bool &,unsigned long &,int &>(v22, &has_value, v13, &v38);
  v17 = std::forward_as_tuple<bool &,unsigned long &,int &>(v25, &v34, (char *)a2 + 32, &v43);
  v18 = std::forward_as_tuple<bool &,unsigned long &,int &>(v26, &v35, (char *)a2 + 16, &v48);
  v19 = std::forward_as_tuple<bool &,unsigned long &,int &>(v27, &v36, a2, &v47);
  v20 = std::forward_as_tuple<bool &,unsigned long &,int &>(v28, &v30, (char *)a2 + 48, &v46);
  v21 = std::forward_as_tuple<bool &,unsigned long &,int &>(v29, &v37, (char *)a2 + 40, &v45);
  std::make_tuple<std::tuple<bool &,void * &,int &>,std::tuple<bool &,void * &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,unsigned long &,int &>,std::tuple<bool &,unsigned long &,int &>,std::tuple<bool &,_SECURITY_CAPABILITIES &,int &>,std::tuple<bool &,unsigned long &,int &>>(
    (unsigned int)v49,
    v21,
    v20,
    v19,
    v18,
    v17,
    v14,
    v15,
    v16);
  dwAttributeCount = ComputeService::Vmwp::ProcessAttributes::details::SumAttributes<0,std::tuple<bool &,void * &,int &>,std::tuple<bool &,void * &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,unsigned long &,int &>,std::tuple<bool &,unsigned long &,int &>,std::tuple<bool &,_SECURITY_CAPABILITIES &,int &>,std::tuple<bool &,unsigned long &,int &>>(v49);
  if ( dwAttributeCount )
  {
    Size = 0;
    if ( !InitializeProcThreadAttributeList(0, dwAttributeCount, 0, &Size) )
    {
      LastError = GetLastError();
      if ( LastError != 122 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xE2,
          (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\vmprocattributes.cpp",
          (const char *)LastError,
          v6);
    }
    std::vector<enum gsl::byte>::resize(this, Size);
    lpAttributeList = (struct _PROC_THREAD_ATTRIBUTE_LIST *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&long FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>>::get(this);
    v3 = InitializeProcThreadAttributeList(lpAttributeList, dwAttributeCount, 0, &Size);
    if ( !(unsigned int)wil::verify_BOOL<int>(v3) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xED,
        (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\vmprocattributes.cpp",
        v4);
    ComputeService::Vmwp::ProcessAttributes::details::UpdateAttributes<0,std::tuple<bool &,void * &,int &>,std::tuple<bool &,void * &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,unsigned long &,int &>,std::tuple<bool &,unsigned long &,int &>,std::tuple<bool &,_SECURITY_CAPABILITIES &,int &>,std::tuple<bool &,unsigned long &,int &>>(
      lpAttributeList,
      v49);
    *((_QWORD *)this + 3) = lpAttributeList;
  }
  return this;
}

```

## disassembly

```asm
0x1400b7604  mov     [rsp+arg_8], rdx
0x1400b7609  mov     [rsp+arg_0], rcx
0x1400b760e  sub     rsp, 2D8h
0x1400b7615  mov     rax, cs:__security_cookie
0x1400b761c  xor     rax, rsp
0x1400b761f  mov     [rsp+2D8h+var_18], rax
0x1400b7627  mov     rax, [rsp+2D8h+arg_0]
0x1400b762f  mov     rcx, rax
0x1400b7632  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x1400b7637  nop
0x1400b7638  mov     rax, [rsp+2D8h+arg_0]
0x1400b7640  mov     qword ptr [rax+18h], 0
0x1400b7648  mov     [rsp+2D8h+var_F0], 0
0x1400b7653  mov     [rsp+2D8h+var_F8], 0
0x1400b765e  mov     rax, [rsp+2D8h+arg_8]
0x1400b7666  add     rax, 38h ; '8'
0x1400b766a  mov     rcx, rax
0x1400b766d  call    ?has_value@?$optional@K@std@@QEBA_NXZ; std::optional<ulong>::has_value(void)
0x1400b7672  movzx   eax, al
0x1400b7675  test    eax, eax
0x1400b7677  jz      short loc_1400B7697
0x1400b7679  mov     rax, [rsp+2D8h+arg_8]
0x1400b7681  add     rax, 38h ; '8'
0x1400b7685  mov     rcx, rax
0x1400b7688  call    ?value@?$optional@K@std@@QEGAAAEAKXZ; std::optional<ulong>::value(void)
0x1400b768d  mov     [rsp+2D8h+var_250], rax
0x1400b7695  jmp     short loc_1400B76A7
0x1400b7697  lea     rax, [rsp+2D8h+var_F0]
0x1400b769f  mov     [rsp+2D8h+var_250], rax
0x1400b76a7  mov     rax, [rsp+2D8h+var_250]
0x1400b76af  mov     [rsp+2D8h+var_238], rax
0x1400b76b7  mov     rax, [rsp+2D8h+var_238]
0x1400b76bf  mov     [rsp+2D8h+var_210], rax
0x1400b76c7  mov     rax, [rsp+2D8h+arg_8]
0x1400b76cf  add     rax, 48h ; 'H'
0x1400b76d3  mov     rcx, rax
0x1400b76d6  call    ?has_value@?$optional@K@std@@QEBA_NXZ; std::optional<ulong>::has_value(void)
0x1400b76db  movzx   eax, al
0x1400b76de  test    eax, eax
0x1400b76e0  jz      short loc_1400B7700
0x1400b76e2  mov     rax, [rsp+2D8h+arg_8]
0x1400b76ea  add     rax, 48h ; 'H'
0x1400b76ee  mov     rcx, rax
0x1400b76f1  call    ?value@?$optional@K@std@@QEGAAAEAKXZ; std::optional<ulong>::value(void)
0x1400b76f6  mov     [rsp+2D8h+var_258], rax
0x1400b76fe  jmp     short loc_1400B7710
0x1400b7700  lea     rax, [rsp+2D8h+var_F8]
0x1400b7708  mov     [rsp+2D8h+var_258], rax
0x1400b7710  mov     rax, [rsp+2D8h+var_258]
0x1400b7718  mov     [rsp+2D8h+var_248], rax
0x1400b7720  mov     rax, [rsp+2D8h+var_248]
0x1400b7728  mov     [rsp+2D8h+var_240], rax
0x1400b7730  mov     rax, [rsp+2D8h+arg_8]
0x1400b7738  cmp     qword ptr [rax+28h], 0
0x1400b773d  jz      short loc_1400B7749
0x1400b773f  mov     dword ptr [rsp+2D8h+var_278+4], 1
0x1400b7747  jmp     short loc_1400B7751
0x1400b7749  mov     dword ptr [rsp+2D8h+var_278+4], 0
0x1400b7751  mov     al, byte ptr [rsp+2D8h+var_278+4]
0x1400b7755  mov     [rsp+2D8h+var_111], al
0x1400b775c  mov     rax, [rsp+2D8h+arg_8]
0x1400b7764  cmp     qword ptr [rax+30h], 0
0x1400b7769  jz      short loc_1400B7775
0x1400b776b  mov     [rsp+2D8h+var_270], 1
0x1400b7773  jmp     short loc_1400B777D
0x1400b7775  mov     [rsp+2D8h+var_270], 0
0x1400b777d  mov     al, byte ptr [rsp+2D8h+var_270]
0x1400b7781  mov     [rsp+2D8h+var_118], al
0x1400b7788  mov     rax, [rsp+2D8h+arg_8]
0x1400b7790  cmp     qword ptr [rax], 0
0x1400b7794  jnz     short loc_1400B77AF
0x1400b7796  mov     rax, [rsp+2D8h+arg_8]
0x1400b779e  cmp     qword ptr [rax+8], 0
0x1400b77a3  jnz     short loc_1400B77AF
0x1400b77a5  mov     [rsp+2D8h+var_26C], 0
0x1400b77ad  jmp     short loc_1400B77B7
0x1400b77af  mov     [rsp+2D8h+var_26C], 1
0x1400b77b7  mov     al, byte ptr [rsp+2D8h+var_26C]
0x1400b77bb  mov     [rsp+2D8h+var_112], al
0x1400b77c2  mov     rax, [rsp+2D8h+arg_8]
0x1400b77ca  cmp     qword ptr [rax+10h], 0
0x1400b77cf  jnz     short loc_1400B77EA
0x1400b77d1  mov     rax, [rsp+2D8h+arg_8]
0x1400b77d9  cmp     qword ptr [rax+18h], 0
0x1400b77de  jnz     short loc_1400B77EA
0x1400b77e0  mov     [rsp+2D8h+var_284], 0
0x1400b77e8  jmp     short loc_1400B77F2
0x1400b77ea  mov     [rsp+2D8h+var_284], 1
0x1400b77f2  mov     al, byte ptr [rsp+2D8h+var_284]
0x1400b77f6  mov     [rsp+2D8h+var_113], al
0x1400b77fd  mov     rax, [rsp+2D8h+arg_8]
0x1400b7805  cmp     dword ptr [rax+20h], 0
0x1400b7809  jz      short loc_1400B7815
0x1400b780b  mov     [rsp+2D8h+var_280], 1
0x1400b7813  jmp     short loc_1400B781D
0x1400b7815  mov     [rsp+2D8h+var_280], 0
0x1400b781d  mov     al, byte ptr [rsp+2D8h+var_280]
0x1400b7821  mov     [rsp+2D8h+var_114], al
0x1400b7828  mov     rax, [rsp+2D8h+arg_8]
0x1400b7830  add     rax, 38h ; '8'
0x1400b7834  mov     rcx, rax
0x1400b7837  call    ?has_value@?$optional@K@std@@QEBA_NXZ; std::optional<ulong>::has_value(void)
0x1400b783c  mov     [rsp+2D8h+var_115], al
0x1400b7843  mov     rax, [rsp+2D8h+arg_8]
0x1400b784b  add     rax, 40h ; '@'
0x1400b784f  mov     rcx, rax
0x1400b7852  call    ??B?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@P6AJPEAU1@@Z$1?FreeWorkerProcessCapabilities@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBA_NXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>>::operator bool(void)
0x1400b7857  movzx   eax, al
0x1400b785a  test    eax, eax
0x1400b785c  jz      short loc_1400B7868
0x1400b785e  mov     [rsp+2D8h+var_27C], 1
0x1400b7866  jmp     short loc_1400B7870
0x1400b7868  mov     [rsp+2D8h+var_27C], 0
0x1400b7870  mov     al, byte ptr [rsp+2D8h+var_27C]
0x1400b7874  mov     [rsp+2D8h+var_116], al
0x1400b787b  mov     rax, [rsp+2D8h+arg_8]
0x1400b7883  add     rax, 48h ; 'H'
0x1400b7887  mov     rcx, rax
0x1400b788a  call    ?has_value@?$optional@K@std@@QEBA_NXZ; std::optional<ulong>::has_value(void)
0x1400b788f  mov     [rsp+2D8h+var_117], al
0x1400b7896  mov     [rsp+2D8h+var_EC], 20002h
0x1400b78a1  mov     [rsp+2D8h+var_E8], 2000Dh
0x1400b78ac  mov     [rsp+2D8h+var_E4], 20007h
0x1400b78b7  mov     [rsp+2D8h+var_E0], 20018h
0x1400b78c2  mov     [rsp+2D8h+var_F4], 2000Eh
0x1400b78cd  mov     [rsp+2D8h+var_110], 2000Bh
0x1400b78d8  mov     [rsp+2D8h+var_100], 20009h
0x1400b78e3  mov     [rsp+2D8h+var_FC], 2000Fh
0x1400b78ee  lea     r9, [rsp+2D8h+var_FC]
0x1400b78f6  mov     r8, [rsp+2D8h+var_240]
0x1400b78fe  lea     rdx, [rsp+2D8h+var_117]
0x1400b7906  lea     rcx, [rsp+2D8h+var_1C0]
0x1400b790e  call    ??$forward_as_tuple@AEA_NAEAKAEAH@std@@YA?AV?$tuple@AEA_NAEAKAEAH@0@AEA_NAEAKAEAH@Z; std::forward_as_tuple<bool &,ulong &,int &>(bool &,ulong &,int &)
0x1400b7913  mov     [rsp+2D8h+var_218], rax
0x1400b791b  mov     rax, [rsp+2D8h+arg_8]
0x1400b7923  add     rax, 40h ; '@'
0x1400b7927  mov     rcx, rax
0x1400b792a  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@P6AJPEAU1@@Z$1?FreeWorkerProcessCapabilities@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAU_SECURITY_CAPABILITIES@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>>::get(void)
0x1400b792f  lea     r9, [rsp+2D8h+var_100]
0x1400b7937  mov     r8, rax
0x1400b793a  lea     rdx, [rsp+2D8h+var_116]
0x1400b7942  lea     rcx, [rsp+2D8h+var_1A8]
0x1400b794a  call    ??$forward_as_tuple@AEA_NAEAKAEAH@std@@YA?AV?$tuple@AEA_NAEAKAEAH@0@AEA_NAEAKAEAH@Z; std::forward_as_tuple<bool &,ulong &,int &>(bool &,ulong &,int &)
0x1400b794f  mov     [rsp+2D8h+var_220], rax
0x1400b7957  lea     r9, [rsp+2D8h+var_110]
0x1400b795f  mov     r8, [rsp+2D8h+var_210]
0x1400b7967  lea     rdx, [rsp+2D8h+var_115]
0x1400b796f  lea     rcx, [rsp+2D8h+var_1D8]
0x1400b7977  call    ??$forward_as_tuple@AEA_NAEAKAEAH@std@@YA?AV?$tuple@AEA_NAEAKAEAH@0@AEA_NAEAKAEAH@Z; std::forward_as_tuple<bool &,ulong &,int &>(bool &,ulong &,int &)
0x1400b797c  mov     [rsp+2D8h+var_228], rax
0x1400b7984  mov     rax, [rsp+2D8h+arg_8]
0x1400b798c  add     rax, 20h ; ' '
0x1400b7990  lea     r9, [rsp+2D8h+var_F4]
0x1400b7998  mov     r8, rax
0x1400b799b  lea     rdx, [rsp+2D8h+var_114]
0x1400b79a3  lea     rcx, [rsp+2D8h+var_190]
0x1400b79ab  call    ??$forward_as_tuple@AEA_NAEAKAEAH@std@@YA?AV?$tuple@AEA_NAEAKAEAH@0@AEA_NAEAKAEAH@Z; std::forward_as_tuple<bool &,ulong &,int &>(bool &,ulong &,int &)
0x1400b79b0  mov     [rsp+2D8h+var_208], rax
0x1400b79b8  mov     rax, [rsp+2D8h+arg_8]
0x1400b79c0  add     rax, 10h
0x1400b79c4  lea     r9, [rsp+2D8h+var_E0]
0x1400b79cc  mov     r8, rax
0x1400b79cf  lea     rdx, [rsp+2D8h+var_113]
0x1400b79d7  lea     rcx, [rsp+2D8h+var_178]
0x1400b79df  call    ??$forward_as_tuple@AEA_NAEAKAEAH@std@@YA?AV?$tuple@AEA_NAEAKAEAH@0@AEA_NAEAKAEAH@Z; std::forward_as_tuple<bool &,ulong &,int &>(bool &,ulong &,int &)
0x1400b79e4  mov     qword ptr [rsp+2D8h+var_200], rax
0x1400b79ec  mov     rax, [rsp+2D8h+arg_8]
0x1400b79f4  lea     r9, [rsp+2D8h+var_E4]
0x1400b79fc  mov     r8, rax
0x1400b79ff  lea     rdx, [rsp+2D8h+var_112]
0x1400b7a07  lea     rcx, [rsp+2D8h+var_160]
0x1400b7a0f  call    ??$forward_as_tuple@AEA_NAEAKAEAH@std@@YA?AV?$tuple@AEA_NAEAKAEAH@0@AEA_NAEAKAEAH@Z; std::forward_as_tuple<bool &,ulong &,int &>(bool &,ulong &,int &)
0x1400b7a14  mov     [rsp+2D8h+var_1F8], rax
0x1400b7a1c  mov     rax, [rsp+2D8h+arg_8]
0x1400b7a24  add     rax, 30h ; '0'
0x1400b7a28  lea     r9, [rsp+2D8h+var_E8]
0x1400b7a30  mov     r8, rax
0x1400b7a33  lea     rdx, [rsp+2D8h+var_118]
0x1400b7a3b  lea     rcx, [rsp+2D8h+var_148]
0x1400b7a43  call    ??$forward_as_tuple@AEA_NAEAKAEAH@std@@YA?AV?$tuple@AEA_NAEAKAEAH@0@AEA_NAEAKAEAH@Z; std::forward_as_tuple<bool &,ulong &,int &>(bool &,ulong &,int &)
0x1400b7a48  mov     [rsp+2D8h+var_1F0], rax
0x1400b7a50  mov     rax, [rsp+2D8h+arg_8]
0x1400b7a58  add     rax, 28h ; '('
0x1400b7a5c  lea     r9, [rsp+2D8h+var_EC]
0x1400b7a64  mov     r8, rax
0x1400b7a67  lea     rdx, [rsp+2D8h+var_111]
0x1400b7a6f  lea     rcx, [rsp+2D8h+var_130]
0x1400b7a77  call    ??$forward_as_tuple@AEA_NAEAKAEAH@std@@YA?AV?$tuple@AEA_NAEAKAEAH@0@AEA_NAEAKAEAH@Z; std::forward_as_tuple<bool &,ulong &,int &>(bool &,ulong &,int &)
0x1400b7a7c  mov     [rsp+2D8h+var_1E8], rax
0x1400b7a84  mov     rax, [rsp+2D8h+var_218]
0x1400b7a8c  mov     [rsp+2D8h+var_298], rax
0x1400b7a91  mov     rax, [rsp+2D8h+var_220]
0x1400b7a99  mov     [rsp+2D8h+var_2A0], rax
0x1400b7a9e  mov     rax, [rsp+2D8h+var_228]
0x1400b7aa6  mov     [rsp+2D8h+var_2A8], rax
0x1400b7aab  mov     rax, [rsp+2D8h+var_208]
0x1400b7ab3  mov     [rsp+2D8h+var_2B0], rax
0x1400b7ab8  mov     rax, qword ptr [rsp+2D8h+var_200]
0x1400b7ac0  mov     qword ptr [rsp+2D8h+var_2B8], rax; unsigned int
0x1400b7ac5  mov     r9, [rsp+2D8h+var_1F8]
0x1400b7acd  mov     r8, [rsp+2D8h+var_1F0]
0x1400b7ad5  mov     rdx, [rsp+2D8h+var_1E8]
0x1400b7add  lea     rcx, [rsp+2D8h+var_D8]
0x1400b7ae5  call    ??$make_tuple@V?$tuple@AEA_NAEAPEAXAEAH@std@@V12@V?$tuple@AEA_NAEAUSECURITY_MITIGATION_POLICIES@ProcessAttributes@Vmwp@ComputeService@@AEAH@2@V32@V?$tuple@AEA_NAEAKAEAH@2@V42@V?$tuple@AEA_NAEAU_SECURITY_CAPABILITIES@@AEAH@2@V42@@std@@YA?AV?$tuple@V?$tuple@AEA_NAEAPEAXAEAH@std@@V12@V?$tuple@AEA_NAEAUSECURITY_MITIGATION_POLICIES@ProcessAttributes@Vmwp@ComputeService@@AEAH@2@V32@V?$tuple@AEA_NAEAKAEAH@2@V42@V?$tuple@AEA_NAEAU_SECURITY_CAPABILITIES@@AEAH@2@V42@@0@$$QEAV?$tuple@AEA_NAEAPEAXAEAH@0@0$$QEAV?$tuple@AEA_NAEAUSECURITY_MITIGATION_POLICIES@ProcessAttributes@Vmwp@ComputeService@@AEAH@0@1$$QEAV?$tuple@AEA_NAEAKAEAH@0@2$$QEAV?$tuple@AEA_NAEAU_SECURITY_CAPABILITIES@@AEAH@0@2@Z; std::make_tuple<std::tuple<bool &,void * &,int &>,std::tuple<bool &,void * &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,ulong &,int &>,std::tuple<bool &,ulong &,int &>,std::tuple<bool &,_SECURITY_CAPABILITIES &,int &>,std::tuple<bool &,ulong &,int &>>(std::tuple<bool &,void * &,int &> &&,std::tuple<bool &,void * &,int &> &&,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &> &&,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &> &&,std::tuple<bool &,ulong &,int &> &&,std::tuple<bool &,ulong &,int &> &&,std::tuple<bool &,_SECURITY_CAPABILITIES &,int &> &&,std::tuple<bool &,ulong &,int &> &&)
0x1400b7aea  nop
0x1400b7aeb  lea     rcx, [rsp+2D8h+var_D8]
0x1400b7af3  call    ??$SumAttributes@$0A@V?$tuple@AEA_NAEAPEAXAEAH@std@@V12@V?$tuple@AEA_NAEAUSECURITY_MITIGATION_POLICIES@ProcessAttributes@Vmwp@ComputeService@@AEAH@2@V32@V?$tuple@AEA_NAEAKAEAH@2@V42@V?$tuple@AEA_NAEAU_SECURITY_CAPABILITIES@@AEAH@2@V42@@details@ProcessAttributes@Vmwp@ComputeService@@YAHAEAV?$tuple@V?$tuple@AEA_NAEAPEAXAEAH@std@@V12@V?$tuple@AEA_NAEAUSECURITY_MITIGATION_POLICIES@ProcessAttributes@Vmwp@ComputeService@@AEAH@2@V32@V?$tuple@AEA_NAEAKAEAH@2@V42@V?$tuple@AEA_NAEAU_SECURITY_CAPABILITIES@@AEAH@2@V42@@std@@@Z; ComputeService::Vmwp::ProcessAttributes::details::SumAttributes<0,std::tuple<bool &,void * &,int &>,std::tuple<bool &,void * &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,ulong &,int &>,std::tuple<bool &,ulong &,int &>,std::tuple<bool &,_SECURITY_CAPABILITIES &,int &>,std::tuple<bool &,ulong &,int &>>(std::tuple<std::tuple<bool &,void * &,int &>,std::tuple<bool &,void * &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,ulong &,int &>,std::tuple<bool &,ulong &,int &>,std::tuple<bool &,_SECURITY_CAPABILITIES &,int &>,std::tuple<bool &,ulong &,int &>> &)
0x1400b7af8  mov     [rsp+2D8h+dwAttributeCount], eax
0x1400b7afc  cmp     [rsp+2D8h+dwAttributeCount], 0
0x1400b7b01  jnz     short loc_1400B7B08
0x1400b7b03  jmp     loc_1400B7C27
0x1400b7b08  mov     [rsp+2D8h+Size], 0
0x1400b7b14  lea     r9, [rsp+2D8h+Size]; lpSize
0x1400b7b1c  xor     r8d, r8d; dwFlags
0x1400b7b1f  mov     edx, [rsp+2D8h+dwAttributeCount]; dwAttributeCount
0x1400b7b23  xor     ecx, ecx; lpAttributeList
0x1400b7b25  call    cs:__imp_InitializeProcThreadAttributeList
0x1400b7b2c  nop     dword ptr [rax+rax+00h]
0x1400b7b31  test    eax, eax
0x1400b7b33  jnz     short loc_1400B7B6E
0x1400b7b35  call    cs:__imp_GetLastError
0x1400b7b3c  nop     dword ptr [rax+rax+00h]
0x1400b7b41  mov     dword ptr [rsp+2D8h+var_278], eax
0x1400b7b45  cmp     dword ptr [rsp+2D8h+var_278], 7Ah ; 'z'
0x1400b7b4a  jz      short loc_1400B7B6E
0x1400b7b4c  mov     rax, [rsp+2D8h]
0x1400b7b54  mov     r9d, dword ptr [rsp+2D8h+var_278]; char *
0x1400b7b59  lea     r8, aOnecoreVmCompu_33; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x1400b7b60  mov     edx, 0E2h; void *
0x1400b7b65  mov     rcx, rax; this
0x1400b7b68  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b7b6e  mov     rax, [rsp+2D8h+arg_0]
0x1400b7b76  mov     [rsp+2D8h+var_1E0], rax
0x1400b7b7e  mov     rdx, [rsp+2D8h+Size]
0x1400b7b86  mov     rcx, [rsp+2D8h+var_1E0]
0x1400b7b8e  call    ?resize@?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAAX_K@Z; std::vector<gsl::byte>::resize(unsigned __int64)
0x1400b7b93  mov     rax, [rsp+2D8h+arg_0]
0x1400b7b9b  mov     rcx, rax
0x1400b7b9e  call    ?get@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@P6AJPEAU1@@Z$1?FreeWorkerProcessCapabilities@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBAPEAU_SECURITY_CAPABILITIES@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>>::get(void)
0x1400b7ba3  mov     [rsp+2D8h+lpAttributeList], rax
0x1400b7ba8  lea     r9, [rsp+2D8h+Size]; lpSize
0x1400b7bb0  xor     r8d, r8d; dwFlags
0x1400b7bb3  mov     edx, [rsp+2D8h+dwAttributeCount]; dwAttributeCount
0x1400b7bb7  mov     rcx, [rsp+2D8h+lpAttributeList]; lpAttributeList
0x1400b7bbc  call    cs:__imp_InitializeProcThreadAttributeList
0x1400b7bc3  nop     dword ptr [rax+rax+00h]
0x1400b7bc8  mov     ecx, eax
0x1400b7bca  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x1400b7bcf  mov     [rsp+2D8h+var_268], eax
0x1400b7bd3  mov     rax, [rsp+2D8h]
0x1400b7bdb  mov     [rsp+2D8h+var_230], rax
0x1400b7be3  cmp     [rsp+2D8h+var_268], 0
0x1400b7be8  jnz     short loc_1400B7C04
0x1400b7bea  lea     r8, aOnecoreVmCompu_33; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x1400b7bf1  mov     edx, 0EDh; void *
0x1400b7bf6  mov     rcx, [rsp+2D8h+var_230]; this
0x1400b7bfe  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b7c04  lea     rdx, [rsp+2D8h+var_D8]
0x1400b7c0c  mov     rcx, [rsp+2D8h+lpAttributeList]
0x1400b7c11  call    ??$UpdateAttributes@$0A@V?$tuple@AEA_NAEAPEAXAEAH@std@@V12@V?$tuple@AEA_NAEAUSECURITY_MITIGATION_POLICIES@ProcessAttributes@Vmwp@ComputeService@@AEAH@2@V32@V?$tuple@AEA_NAEAKAEAH@2@V42@V?$tuple@AEA_NAEAU_SECURITY_CAPABILITIES@@AEAH@2@V42@@details@ProcessAttributes@Vmwp@ComputeService@@YAXPEAU_PROC_THREAD_ATTRIBUTE_LIST@@AEAV?$tuple@V?$tuple@AEA_NAEAPEAXAEAH@std@@V12@V?$tuple@AEA_NAEAUSECURITY_MITIGATION_POLICIES@ProcessAttributes@Vmwp@ComputeService@@AEAH@2@V32@V?$tuple@AEA_NAEAKAEAH@2@V42@V?$tuple@AEA_NAEAU_SECURITY_CAPABILITIES@@AEAH@2@V42@@std@@@Z; ComputeService::Vmwp::ProcessAttributes::details::UpdateAttributes<0,std::tuple<bool &,void * &,int &>,std::tuple<bool &,void * &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,ulong &,int &>,std::tuple<bool &,ulong &,int &>,std::tuple<bool &,_SECURITY_CAPABILITIES &,int &>,std::tuple<bool &,ulong &,int &>>(_PROC_THREAD_ATTRIBUTE_LIST *,std::tuple<std::tuple<bool &,void * &,int &>,std::tuple<bool &,void * &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,ComputeService::Vmwp::ProcessAttributes::SECURITY_MITIGATION_POLICIES &,int &>,std::tuple<bool &,ulong &,int &>,std::tuple<bool &,ulong &,int &>,std::tuple<bool &,_SECURITY_CAPABILITIES &,int &>,std::tuple<bool &,ulong &,int &>> &)
0x1400b7c16  mov     rax, [rsp+2D8h+arg_0]
0x1400b7c1e  mov     rcx, [rsp+2D8h+lpAttributeList]
0x1400b7c23  mov     [rax+18h], rcx
0x1400b7c27  mov     rax, [rsp+2D8h+arg_0]
0x1400b7c2f  mov     rcx, [rsp+2D8h+var_18]
0x1400b7c37  xor     rcx, rsp; StackCookie
0x1400b7c3a  call    __security_check_cookie
0x1400b7c3f  add     rsp, 2D8h
0x1400b7c46  retn
```
