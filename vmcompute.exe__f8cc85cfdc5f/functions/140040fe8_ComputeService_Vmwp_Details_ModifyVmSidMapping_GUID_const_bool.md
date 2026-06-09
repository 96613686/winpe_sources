# ComputeService::Vmwp::Details::ModifyVmSidMapping(_GUID const &,bool)

- ea: `0x140040fe8`
- end: `0x140041299`
- name: `?ModifyVmSidMapping@Details@Vmwp@ComputeService@@YAXAEBU_GUID@@_N@Z`
- size: `689`
- prototype: `void __fastcall(ComputeService::Vmwp::Details *__hidden this, const struct _GUID *, bool)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14007da0c`
- `0x14007f8e4`
- `0x14007f92c`

## callees

- `0x140017040`
- `0x14001d4d0`
- `0x140040fe8`
- `0x1400421f0`
- `0x140043010`
- `0x1400660b4`
- `0x1400bc8f4`
- `0x1400c4154`
- `0x1400e91a8`
- `0x1401332f0`
- `0x140134048`
- `0x140142dac`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140041123`
- `ntdll!RtlInitUnicodeString` at `0x140041138`
- `ntdll!RtlInitUnicodeString` at `0x140041156`
- `ntdll!RtlInitUnicodeString` at `0x14004116b`
- `ntdll!RtlInitUnicodeString` at `0x140041123`
- `ntdll!RtlInitUnicodeString` at `0x140041138`
- `ntdll!RtlInitUnicodeString` at `0x140041156`
- `ntdll!RtlInitUnicodeString` at `0x14004116b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140041204`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140041236`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140041204`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140041236`
- `api-ms-win-security-lsalookup-l2-1-1!LsaManageSidNameMapping` at `0x14004119e`
- `api-ms-win-security-lsalookup-l2-1-1!LsaManageSidNameMapping` at `0x14004119e`

## string_xrefs

- `0x14004126e`: `onecore\vm\compute\shared\vmwp\lib\vmsid.cpp`
- `0x140041287`: `onecore\vm\compute\shared\vmwp\lib\vmsid.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ComputeService::Vmwp::Details::ModifyVmSidMapping(DWORD *this, const struct _GUID *a2)
{
  int v2; // edi
  HLOCAL **v4; // rax
  const struct _GUID *v5; // rdx
  void *VirtualMachineSid; // rax
  HLOCAL v7; // rbx
  const WCHAR *v8; // rdx
  int v9; // edi
  HLOCAL v10; // rcx
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING v12; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v13; // [rsp+40h] [rbp-C0h]
  HLOCAL v14; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL *v15; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h] BYREF
  char v17; // [rsp+68h] [rbp-98h]
  unsigned __int64 v18; // [rsp+70h] [rbp-90h]
  PCWSTR SourceString[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v20; // [rsp+88h] [rbp-78h]
  HLOCAL hMem; // [rsp+A0h] [rbp-60h] BYREF
  int v22; // [rsp+A8h] [rbp-58h]
  _BYTE v23[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v24[32]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR v25[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v26; // [rsp+100h] [rbp+0h]
  __int128 v27; // [rsp+110h] [rbp+10h]
  __int128 v28; // [rsp+120h] [rbp+20h]
  HLOCAL *v29; // [rsp+130h] [rbp+30h]
  __int16 v30; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v2 = (unsigned __int8)a2;
  DestinationString = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  memset_0(&hMem, 0, 0x50u);
  hMem = 0;
  v22 = 7;
  std::wstring::wstring(v23);
  std::wstring::wstring(v24);
  *(_OWORD *)SourceString = 0;
  v20 = 0;
  std::wstring::_Construct<1,unsigned short const *>(SourceString, L"NT VIRTUAL MACHINE");
  CommonUtilities::GuidToString(&v15);
  v4 = &v15;
  if ( v18 > 7 )
    v4 = (HLOCAL **)v15;
  *(_OWORD *)v25 = *(_OWORD *)v4;
  v26 = *((_OWORD *)v4 + 1);
  v27 = *((_OWORD *)v4 + 2);
  v28 = *((_OWORD *)v4 + 3);
  v29 = v4[8];
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&v15);
  v30 = 0;
  VirtualMachineSid = WpSecurity::AllocateVirtualMachineSid(this, v5);
  Vml::VmSid::Assign((Vml::VmSid *)&hMem, VirtualMachineSid);
  DestinationString = 0;
  v12 = 0;
  v13 = 0;
  v7 = hMem;
  v8 = (const WCHAR *)SourceString;
  if ( (_BYTE)v2 )
  {
    if ( *((_QWORD *)&v20 + 1) > 7u )
      v8 = SourceString[0];
    RtlInitUnicodeString(&DestinationString, v8);
    RtlInitUnicodeString(&v12, v25);
    *(_QWORD *)&v13 = v7;
  }
  else
  {
    if ( *((_QWORD *)&v20 + 1) > 7u )
      v8 = SourceString[0];
    RtlInitUnicodeString(&DestinationString, v8);
    RtlInitUnicodeString(&v12, v25);
  }
  v15 = &v14;
  v16 = 0;
  v17 = 1;
  v9 = LsaManageSidNameMapping(v2 ^ 1u, &DestinationString, &v16);
  if ( v17 )
    wistd::unique_ptr<_LSA_SID_NAME_MAPPING_OPERATION_OUTPUT,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      v15,
      v16);
  if ( v9 < 0 )
  {
    if ( !v14 )
      goto LABEL_24;
    if ( *(_DWORD *)v14 )
    {
      if ( *(_DWORD *)v14 == 2 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x79,
          (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\vmsid.cpp",
          (const char *)0x524,
          *(unsigned int *)&DestinationString.Length);
      if ( *(_DWORD *)v14 != 3 && *(_DWORD *)v14 != 6 )
LABEL_24:
        wil::details::in1diag3::Throw_NtStatus(
          retaddr,
          (void *)0x7D,
          (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\vmsid.cpp",
          (const char *)(unsigned int)v9,
          *(int *)&DestinationString.Length);
    }
  }
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)SourceString);
  if ( v7 )
    LocalFree(v7);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v24);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v23);
  v10 = v14;
  v14 = 0;
  if ( v10 )
    LocalFree(v10);
}

```

## disassembly

```asm
0x140040fe8  mov     [rsp-8+arg_8], rbx
0x140040fed  mov     [rsp-8+arg_10], rdi
0x140040ff2  push    rbp
0x140040ff3  lea     rbp, [rsp-50h]
0x140040ff8  sub     rsp, 150h
0x140040fff  mov     rax, cs:__security_cookie
0x140041006  xor     rax, rsp
0x140041009  mov     [rbp+50h+var_10], rax
0x14004100d  movzx   edi, dl
0x140041010  mov     rbx, rcx
0x140041013  xorps   xmm0, xmm0
0x140041016  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x14004101b  movups  xmmword ptr [rsp+150h+var_120.Length], xmm0
0x140041020  movups  [rsp+150h+var_110], xmm0
0x140041025  mov     [rsp+150h+var_100], 0
0x14004102e  xor     edx, edx; Val
0x140041030  lea     r8d, [rdx+50h]; Size
0x140041034  lea     rcx, [rbp+50h+hMem]; void *
0x140041038  call    memset_0
0x14004103d  mov     [rbp+50h+hMem], 0
0x140041045  mov     [rbp+50h+var_A8], 7
0x14004104c  lea     rcx, [rbp+50h+var_A0]; void *
0x140041050  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140041055  nop
0x140041056  lea     rcx, [rbp+50h+var_80]; void *
0x14004105a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14004105f  nop
0x140041060  xorps   xmm0, xmm0
0x140041063  movups  xmmword ptr [rsp+150h+SourceString], xmm0
0x140041068  xorps   xmm1, xmm1
0x14004106b  movdqu  [rbp+50h+var_C8], xmm1
0x140041070  mov     r8d, 12h
0x140041076  lea     rdx, aNtVirtualMachi; "NT VIRTUAL MACHINE"
0x14004107d  lea     rcx, [rsp+150h+SourceString]
0x140041082  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140041087  nop
0x140041088  mov     rdx, rbx
0x14004108b  lea     rcx, [rsp+150h+var_F8]; void *
0x140041090  call    ?GuidToString@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; CommonUtilities::GuidToString(_GUID const &,bool)
0x140041095  lea     rax, [rsp+150h+var_F8]
0x14004109a  cmp     [rsp+150h+var_E0], 7
0x1400410a0  cmova   rax, [rsp+150h+var_F8]
0x1400410a6  movups  xmm0, xmmword ptr [rax]
0x1400410a9  movaps  xmmword ptr [rbp+50h+var_60], xmm0
0x1400410ad  movups  xmm1, xmmword ptr [rax+10h]
0x1400410b1  movaps  [rbp+50h+var_50], xmm1
0x1400410b5  movups  xmm0, xmmword ptr [rax+20h]
0x1400410b9  movaps  [rbp+50h+var_40], xmm0
0x1400410bd  movups  xmm1, xmmword ptr [rax+30h]
0x1400410c1  movaps  [rbp+50h+var_30], xmm1
0x1400410c5  movsd   xmm0, qword ptr [rax+40h]
0x1400410ca  movsd   [rbp+50h+var_20], xmm0
0x1400410cf  lea     rcx, [rsp+150h+var_F8]; this
0x1400410d4  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400410d9  xor     eax, eax
0x1400410db  mov     [rbp+50h+var_18], ax
0x1400410df  mov     rcx, rbx; this
0x1400410e2  call    ?AllocateVirtualMachineSid@WpSecurity@@YAPEAXAEBU_GUID@@@Z; WpSecurity::AllocateVirtualMachineSid(_GUID const &)
0x1400410e7  mov     rdx, rax; pSourceSid
0x1400410ea  lea     rcx, [rbp+50h+hMem]; this
0x1400410ee  call    ?Assign@VmSid@Vml@@QEAAXPEAX@Z; Vml::VmSid::Assign(void *)
0x1400410f3  xorps   xmm0, xmm0
0x1400410f6  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0; int
0x1400410fb  movups  xmmword ptr [rsp+150h+var_120.Length], xmm0
0x140041100  movups  [rsp+150h+var_110], xmm0
0x140041105  mov     rbx, [rbp+50h+hMem]
0x140041109  lea     rdx, [rsp+150h+SourceString]
0x14004110e  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x140041113  test    dil, dil
0x140041116  jz      short loc_14004114B
0x140041118  cmp     qword ptr [rbp+50h+var_C8+8], 7
0x14004111d  cmova   rdx, [rsp+150h+SourceString]; SourceString
0x140041123  call    cs:__imp_RtlInitUnicodeString
0x14004112a  nop     dword ptr [rax+rax+00h]
0x14004112f  lea     rdx, [rbp+50h+var_60]; SourceString
0x140041133  lea     rcx, [rsp+150h+var_120]; DestinationString
0x140041138  call    cs:__imp_RtlInitUnicodeString
0x14004113f  nop     dword ptr [rax+rax+00h]
0x140041144  mov     qword ptr [rsp+150h+var_110], rbx
0x140041149  jmp     short loc_140041177
0x14004114b  cmp     qword ptr [rbp+50h+var_C8+8], 7
0x140041150  cmova   rdx, [rsp+150h+SourceString]; SourceString
0x140041156  call    cs:__imp_RtlInitUnicodeString
0x14004115d  nop     dword ptr [rax+rax+00h]
0x140041162  lea     rdx, [rbp+50h+var_60]; SourceString
0x140041166  lea     rcx, [rsp+150h+var_120]; DestinationString
0x14004116b  call    cs:__imp_RtlInitUnicodeString
0x140041172  nop     dword ptr [rax+rax+00h]
0x140041177  lea     rax, [rsp+150h+var_100]
0x14004117c  mov     [rsp+150h+var_F8], rax
0x140041181  mov     [rsp+150h+var_F0], 0
0x14004118a  mov     [rsp+150h+var_E8], 1
0x14004118f  mov     ecx, edi
0x140041191  xor     ecx, 1
0x140041194  lea     r8, [rsp+150h+var_F0]
0x140041199  lea     rdx, [rsp+150h+DestinationString]
0x14004119e  call    cs:__imp_LsaManageSidNameMapping
0x1400411a5  nop     dword ptr [rax+rax+00h]
0x1400411aa  mov     edi, eax
0x1400411ac  cmp     [rsp+150h+var_E8], 0
0x1400411b1  jz      short loc_1400411C2
0x1400411b3  mov     rdx, [rsp+150h+var_F0]
0x1400411b8  mov     rcx, [rsp+150h+var_F8]
0x1400411bd  call    ?reset@?$unique_ptr@T_LSA_SID_NAME_MAPPING_OPERATION_OUTPUT@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAT_LSA_SID_NAME_MAPPING_OPERATION_OUTPUT@@@Z; wistd::unique_ptr<_LSA_SID_NAME_MAPPING_OPERATION_OUTPUT,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_LSA_SID_NAME_MAPPING_OPERATION_OUTPUT *)
0x1400411c2  test    edi, edi
0x1400411c4  jns     short loc_1400411F1
0x1400411c6  mov     rcx, [rsp+150h+var_100]
0x1400411cb  test    rcx, rcx
0x1400411ce  jz      loc_140041280
0x1400411d4  mov     edx, [rcx]
0x1400411d6  test    edx, edx
0x1400411d8  jz      short loc_1400411F1
0x1400411da  sub     edx, 2
0x1400411dd  jz      loc_140041264
0x1400411e3  sub     edx, 1
0x1400411e6  jz      short loc_1400411F1
0x1400411e8  cmp     edx, 3
0x1400411eb  jnz     loc_140041280
0x1400411f1  lea     rcx, [rsp+150h+SourceString]; this
0x1400411f6  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400411fb  nop
0x1400411fc  test    rbx, rbx
0x1400411ff  jz      short loc_140041210
0x140041201  mov     rcx, rbx; hMem
0x140041204  call    cs:__imp_LocalFree
0x14004120b  nop     dword ptr [rax+rax+00h]
0x140041210  lea     rcx, [rbp+50h+var_80]; this
0x140041214  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140041219  lea     rcx, [rbp+50h+var_A0]; this
0x14004121d  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140041222  nop
0x140041223  mov     rcx, [rsp+150h+var_100]; hMem
0x140041228  mov     [rsp+150h+var_100], 0
0x140041231  test    rcx, rcx
0x140041234  jz      short loc_140041242
0x140041236  call    cs:__imp_LocalFree
0x14004123d  nop     dword ptr [rax+rax+00h]
0x140041242  mov     rcx, [rbp+50h+var_10]
0x140041246  xor     rcx, rsp; StackCookie
0x140041249  call    __security_check_cookie
0x14004124e  lea     r11, [rsp+150h+var_s0]
0x140041256  mov     rbx, [r11+18h]
0x14004125a  mov     rdi, [r11+20h]
0x14004125e  mov     rsp, r11
0x140041261  pop     rbp
0x140041262  retn
0x140041264  mov     rcx, [rbp+58h]; this
0x140041268  mov     r9d, 524h; char *
0x14004126e  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x140041275  mov     edx, 79h ; 'y'; void *
0x14004127a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140041280  mov     rcx, [rbp+58h]; this
0x140041284  mov     r9d, edi; char *
0x140041287  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x14004128e  mov     edx, 7Dh ; '}'; void *
0x140041293  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
