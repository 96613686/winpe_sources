# ComputeService::VmCommonHelpers::VirtualGpu::GpuDetails::AddGpu(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ComputeService::VmCommonHelpers::VirtualGpu::GpuEnvironment &)

- ea: `0x140048974`
- end: `0x140048f33`
- name: `?AddGpu@GpuDetails@VirtualGpu@VmCommonHelpers@ComputeService@@YA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UDisplayDevice@VirtualGpu@VmCommonHelpers@ComputeService@@@std@@@std@@@std@@@std@@_N@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@AEAUGpuEnvironment@234@@Z`
- size: `1471`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140048514`
- `0x1401ef080`

## callees

- `0x1400142a0`
- `0x140017040`
- `0x14001bce0`
- `0x14001d4d0`
- `0x140024030`
- `0x1400421f0`
- `0x1400451a0`
- `0x140048974`
- `0x140048f3c`
- `0x14004a24c`
- `0x140068b1c`
- `0x140080180`
- `0x1400ac560`
- `0x1400c4154`
- `0x1400cdba8`
- `0x1400e3608`
- `0x14011e5c4`
- `0x1401332f0`
- `0x140134048`
- `0x14017b76c`
- `0x1401eec08`
- `0x1401eed44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x140048a79`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x140048a79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048c90`
- `RPCRT4!UuidCreate` at `0x140048e79`
- `RPCRT4!UuidCreate` at `0x140048e79`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140048ba2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140048ba2`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140048db9`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140048db9`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x140048da2`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x140048da2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140048c80`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140048c80`

## string_xrefs

- `0x140048cc6`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualgpu.cpp`
- `0x140048dd3`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualgpu.cpp`
- `0x140048f21`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualgpu.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ComputeService::VmCommonHelpers::VirtualGpu::GpuDetails::AddGpu(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int128 *v6; // rcx
  char *v7; // r8
  char *v8; // rdx
  _QWORD *v9; // rcx
  wint_t *v10; // rbx
  wint_t *v11; // r14
  __int64 v12; // rcx
  wint_t *v13; // rax
  char *i; // r13
  __int16 v15; // di
  _QWORD *v16; // rax
  const WCHAR *v18; // rcx
  wint_t *FileW; // rbx
  const char *v20; // r9
  DWORD j; // ecx
  char *v22; // r13
  char *v23; // rax
  size_t v24; // r14
  DWORD LastError; // eax
  _QWORD *v26; // r13
  __int16 v27; // r14
  __int64 v28; // r14
  __int64 v29; // rcx
  CONFIGRET v30; // eax
  DWORD v31; // eax
  __int64 *v32; // rcx
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  wint_t *v34; // [rsp+40h] [rbp-C0h] BYREF
  UUID Uuid; // [rsp+48h] [rbp-B8h] BYREF
  char *v36; // [rsp+58h] [rbp-A8h]
  wint_t *v37; // [rsp+60h] [rbp-A0h]
  char v38[16]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v39; // [rsp+78h] [rbp-88h]
  _QWORD *v40; // [rsp+80h] [rbp-80h]
  _DWORD v41[4]; // [rsp+90h] [rbp-70h] BYREF
  wint_t *v42; // [rsp+A0h] [rbp-60h]
  DWORD nOutBufferSize; // [rsp+230h] [rbp+130h] BYREF
  __int64 v44; // [rsp+238h] [rbp+138h] BYREF
  void *lpOutBuffer[2]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v46; // [rsp+250h] [rbp+150h]
  __int128 v47; // [rsp+258h] [rbp+158h] BYREF
  __int64 v48[3]; // [rsp+268h] [rbp+168h]
  _BYTE v49[32]; // [rsp+280h] [rbp+180h] BYREF
  __int64 v50; // [rsp+2A0h] [rbp+1A0h] BYREF
  UUID v51; // [rsp+2A8h] [rbp+1A8h]
  __int128 v52; // [rsp+2B8h] [rbp+1B8h]
  __int128 v53; // [rsp+2C8h] [rbp+1C8h]
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  v40 = a2;
  v47 = 0;
  *(_OWORD *)v48 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v47, L"GPUPARAV");
  v6 = &v47;
  if ( v48[1] > 7uLL )
    v6 = (__int128 *)v47;
  v7 = (char *)v6 + 2 * v48[0];
  v36 = v7;
  v8 = (char *)&v47;
  if ( v48[1] > 7uLL )
    v8 = (char *)v47;
  *(_QWORD *)&Uuid.Data1 = v8;
  if ( a2[3] <= 7u )
    v9 = a2;
  else
    v9 = (_QWORD *)*a2;
  v10 = (wint_t *)v9 + a2[2];
  if ( a2[3] <= 7u )
    v11 = (wint_t *)a2;
  else
    v11 = (wint_t *)*a2;
  v12 = (v7 - v8) >> 1;
  if ( v10 - v11 >= v12 )
  {
    v37 = &v10[-v12];
LABEL_13:
    v13 = v11;
    for ( i = v8; ; i += 2 )
    {
      v34 = v13;
      if ( i == v7 )
        break;
      v15 = *(_WORD *)i;
      if ( towupper(*v13) != v15 )
      {
        if ( v11 == v37 )
          goto LABEL_20;
        ++v11;
        v8 = *(char **)&Uuid.Data1;
        v7 = v36;
        goto LABEL_13;
      }
      v13 = v34 + 1;
      v7 = v36;
    }
    v10 = v11;
  }
LABEL_20:
  if ( a2[3] <= 7u )
    v16 = a2;
  else
    v16 = (_QWORD *)*a2;
  if ( v10 == (wint_t *)((char *)v16 + 2 * a2[2]) )
  {
    *(_QWORD *)a1 = *(_QWORD *)a3;
    *(_BYTE *)(a1 + 8) = 0;
    goto LABEL_25;
  }
  std::wstring::_Replace<unsigned short>(a2, v48[0]);
  if ( a2[3] <= 7u )
    v18 = (const WCHAR *)a2;
  else
    v18 = (const WCHAR *)*a2;
  FileW = (wint_t *)CreateFileW(v18, 1u, 1u, 0, 3u, 0x80u, 0);
  v34 = FileW;
  if ( (unsigned __int64)FileW - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualgpu.cpp",
      v20);
  *(_OWORD *)lpOutBuffer = 0;
  v46 = 0;
  std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(lpOutBuffer);
  for ( j = 52; ; j = 2 * *(_DWORD *)lpOutBuffer[0] + 20 )
  {
    nOutBufferSize = j;
    v22 = (char *)lpOutBuffer[1];
    if ( (void *)j >= (void *)((char *)lpOutBuffer[1] - (char *)lpOutBuffer[0]) )
    {
      if ( (void *)j <= (void *)((char *)lpOutBuffer[1] - (char *)lpOutBuffer[0]) )
        goto LABEL_38;
      if ( j > v46 - (unsigned __int64)lpOutBuffer[0] )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(lpOutBuffer, j);
        goto LABEL_38;
      }
      v24 = j - (unsigned __int64)((char *)lpOutBuffer[1] - (char *)lpOutBuffer[0]);
      memset_0(lpOutBuffer[1], 0, v24);
      v23 = &v22[v24];
    }
    else
    {
      v23 = (char *)lpOutBuffer[0] + j;
    }
    lpOutBuffer[1] = v23;
LABEL_38:
    if ( DeviceIoControl(FileW, 0x226444u, 0, 0, lpOutBuffer[0], nOutBufferSize, &nOutBufferSize, 0) )
      break;
    LastError = GetLastError();
    if ( LastError != 234 && LastError )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualgpu.cpp",
        (const char *)LastError,
        dwCreationDisposition);
  }
  v26 = lpOutBuffer[0];
  if ( *(_DWORD *)(a3 + 40) != 1 || (*((_BYTE *)lpOutBuffer[0] + 16) & 1) != 0 )
  {
    v27 = -1;
    if ( *(_DWORD *)(a3 + 40) == 2 )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,Schema::Responses::System::NetworkProperty,std::less<void>,std::allocator<std::pair<std::wstring const,Schema::Responses::System::NetworkProperty>>,0>>::_Find_lower_bound<std::wstring>(
        a3 + 48,
        v38,
        a2);
      v28 = v39;
      if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>,std::less<void>,std::allocator<std::pair<std::wstring const,Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>>>,0>>::_Lower_bound_duplicate<std::wstring>(
                               v29,
                               v39,
                               a2)
        || v28 == *(_QWORD *)(a3 + 48) )
      {
        goto LABEL_45;
      }
      v27 = *(_WORD *)(v28 + 64);
    }
    v44 = 0;
    memset_0(v41, 0, 0x1A0u);
    v41[0] = 416;
    v41[2] = 1;
    v42 = FileW;
    wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(
      &v44,
      0);
    v30 = CM_Register_Notification(
            v41,
            a3,
            &ComputeService::VmCommonHelpers::VirtualGpu::GpuDetails::GpuPnPListener,
            &v44);
    if ( v30 )
    {
      v31 = CM_MapCrToWin32Err(v30, 0x1Fu);
      if ( v31 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xB8,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualgpu.cpp",
          (const char *)v31,
          dwCreationDisposition);
    }
    v32 = (__int64 *)(*(_QWORD *)std::map<std::wstring,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>>,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>>>>>::_Try_emplace<std::wstring const &,>(
                                   a3 + 16,
                                   &Uuid,
                                   a2)
                    + 64LL);
    if ( v32 != &v44 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(
        v32,
        v44);
      v44 = 0;
    }
    std::wstring::wstring(v49);
    v50 = -1;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    std::wstring::operator=(v49, a2);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      &v50,
      &v34);
    Uuid = 0;
    UuidCreate(&Uuid);
    v51 = Uuid;
    v52 = *(_OWORD *)v26;
    *(_QWORD *)&v53 = v26[2];
    WORD4(v53) = v27;
    WORD5(v53) = *(_WORD *)(a3 + 64);
    BYTE12(v53) = *(_BYTE *)(a3 + 66);
    std::map<std::wstring,ComputeService::VmCommonHelpers::VirtualGpu::DisplayDevice,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,ComputeService::VmCommonHelpers::VirtualGpu::DisplayDevice>>>::_Try_emplace<std::wstring,ComputeService::VmCommonHelpers::VirtualGpu::DisplayDevice>(
      a3,
      &Uuid,
      a2,
      v49);
    *(_QWORD *)a1 = *(_QWORD *)&Uuid.Data1;
    *(_BYTE *)(a1 + 8) = Uuid.Data4[0];
    ComputeService::VmCommonHelpers::VirtualGpu::DisplayDevice::~DisplayDevice((ComputeService::VmCommonHelpers::VirtualGpu::DisplayDevice *)v49);
    wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>(&v44);
  }
  else
  {
LABEL_45:
    *(_QWORD *)a1 = *(_QWORD *)a3;
    *(_BYTE *)(a1 + 8) = 0;
  }
  std::vector<unsigned char>::_Tidy(lpOutBuffer);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v34);
LABEL_25:
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&v47);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)a2);
  return a1;
}

```

## disassembly

```asm
0x140048974  mov     [rsp-8+arg_18], rbx
0x140048979  push    rbp
0x14004897a  push    rsi
0x14004897b  push    rdi
0x14004897c  push    r12
0x14004897e  push    r13
0x140048980  push    r14
0x140048982  push    r15
0x140048984  lea     rbp, [rsp-1F0h]
0x14004898c  sub     rsp, 2F0h
0x140048993  mov     rax, cs:__security_cookie
0x14004899a  xor     rax, rsp
0x14004899d  mov     [rbp+220h+var_40], rax
0x1400489a4  mov     r12, r8
0x1400489a7  mov     rsi, rdx
0x1400489aa  mov     r15, rcx
0x1400489ad  mov     [rbp+220h+var_2A0], rdx
0x1400489b1  xorps   xmm0, xmm0
0x1400489b4  movups  [rbp+220h+var_C8], xmm0
0x1400489bb  xorps   xmm1, xmm1
0x1400489be  movdqu  xmmword ptr [rbp+220h+var_B8], xmm1
0x1400489c6  mov     r8d, 8
0x1400489cc  lea     rdx, aGpuparav; "GPUPARAV"
0x1400489d3  lea     rcx, [rbp+220h+var_C8]
0x1400489da  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400489df  nop
0x1400489e0  lea     rcx, [rbp+220h+var_C8]
0x1400489e7  mov     r10, qword ptr [rbp+220h+var_C8]
0x1400489ee  cmp     [rbp+220h+var_B8+8], 7
0x1400489f6  cmova   rcx, r10
0x1400489fa  mov     rax, [rbp+220h+var_B8]
0x140048a01  lea     r8, [rcx+rax*2]
0x140048a05  mov     [rsp+320h+var_2C8], r8
0x140048a0a  lea     rdx, [rbp+220h+var_C8]
0x140048a11  cmova   rdx, r10
0x140048a15  mov     qword ptr [rsp+320h+Uuid.Data1], rdx
0x140048a1a  cmp     qword ptr [rsi+18h], 7
0x140048a1f  jbe     short loc_140048A26
0x140048a21  mov     rcx, [rsi]
0x140048a24  jmp     short loc_140048A29
0x140048a26  mov     rcx, rsi
0x140048a29  mov     rax, [rsi+10h]
0x140048a2d  lea     rbx, [rcx+rax*2]
0x140048a31  jbe     short loc_140048A38
0x140048a33  mov     r14, [rsi]
0x140048a36  jmp     short loc_140048A3B
0x140048a38  mov     r14, rsi
0x140048a3b  mov     rcx, r8
0x140048a3e  sub     rcx, rdx
0x140048a41  sar     rcx, 1
0x140048a44  mov     rax, rbx
0x140048a47  sub     rax, r14
0x140048a4a  sar     rax, 1
0x140048a4d  cmp     rax, rcx
0x140048a50  jl      short loc_140048ABF
0x140048a52  lea     rax, [rcx+rcx]
0x140048a56  mov     rcx, rbx
0x140048a59  sub     rcx, rax
0x140048a5c  mov     [rsp+320h+var_2C0], rcx
0x140048a61  mov     rax, r14
0x140048a64  mov     r13, rdx
0x140048a67  mov     [rsp+320h+var_2E0], rax
0x140048a6c  cmp     r13, r8
0x140048a6f  jz      short loc_140048AB5
0x140048a71  movzx   edi, word ptr [r13+0]
0x140048a76  movzx   ecx, word ptr [rax]; C
0x140048a79  call    cs:__imp_towupper
0x140048a80  nop     dword ptr [rax+rax+00h]
0x140048a85  cmp     ax, di
0x140048a88  jnz     short loc_140048A9E
0x140048a8a  mov     rax, [rsp+320h+var_2E0]
0x140048a8f  add     rax, 2
0x140048a93  add     r13, 2
0x140048a97  mov     r8, [rsp+320h+var_2C8]
0x140048a9c  jmp     short loc_140048A67
0x140048a9e  cmp     r14, [rsp+320h+var_2C0]
0x140048aa3  jz      short loc_140048AB8
0x140048aa5  add     r14, 2
0x140048aa9  mov     rdx, qword ptr [rsp+320h+Uuid.Data1]
0x140048aae  mov     r8, [rsp+320h+var_2C8]
0x140048ab3  jmp     short loc_140048A61
0x140048ab5  mov     rbx, r14
0x140048ab8  mov     r10, qword ptr [rbp+220h+var_C8]
0x140048abf  cmp     qword ptr [rsi+18h], 7
0x140048ac4  jbe     short loc_140048ACB
0x140048ac6  mov     rax, [rsi]
0x140048ac9  jmp     short loc_140048ACE
0x140048acb  mov     rax, rsi
0x140048ace  mov     rdx, [rsi+10h]
0x140048ad2  lea     r8, [rax+rdx*2]
0x140048ad6  cmp     rbx, r8
0x140048ad9  jnz     short loc_140048B2B
0x140048adb  mov     rdx, [r12]
0x140048adf  mov     [r15], rdx
0x140048ae2  xor     edi, edi
0x140048ae4  mov     [r15+8], dil
0x140048ae8  lea     rcx, [rbp+220h+var_C8]; this
0x140048aef  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140048af4  nop
0x140048af5  mov     rcx, rsi; this
0x140048af8  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140048afd  mov     rax, r15
0x140048b00  mov     rcx, [rbp+220h+var_40]
0x140048b07  xor     rcx, rsp; StackCookie
0x140048b0a  call    __security_check_cookie
0x140048b0f  mov     rbx, [rsp+320h+arg_18]
0x140048b17  add     rsp, 2F0h
0x140048b1e  pop     r15
0x140048b20  pop     r14
0x140048b22  pop     r13
0x140048b24  pop     r12
0x140048b26  pop     rdi
0x140048b27  pop     rsi
0x140048b28  pop     rbp
0x140048b29  retn
0x140048b2b  mov     rcx, [rbp+220h+var_B8]
0x140048b32  lea     r8, [rcx+rcx]
0x140048b36  sar     r8, 1
0x140048b39  cmp     qword ptr [rsi+18h], 7
0x140048b3e  jbe     short loc_140048B45
0x140048b40  mov     rax, [rsi]
0x140048b43  jmp     short loc_140048B48
0x140048b45  mov     rax, rsi
0x140048b48  sub     rbx, rax
0x140048b4b  sar     rbx, 1
0x140048b4e  lea     r9, [rbp+220h+var_C8]
0x140048b55  cmp     [rbp+220h+var_B8+8], 7
0x140048b5d  cmova   r9, r10
0x140048b61  mov     qword ptr [rsp+320h+dwCreationDisposition], rcx; __int64
0x140048b66  mov     rdx, rbx
0x140048b69  mov     rcx, rsi; Src
0x140048b6c  call    ??$_Replace@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_K_KQEBG0@Z; std::wstring::_Replace<ushort>(unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x140048b71  cmp     qword ptr [rsi+18h], 7
0x140048b76  jbe     short loc_140048B7D
0x140048b78  mov     rcx, [rsi]
0x140048b7b  jmp     short loc_140048B80
0x140048b7d  mov     rcx, rsi; lpFileName
0x140048b80  xor     edi, edi
0x140048b82  mov     [rsp+320h+hTemplateFile], rdi; hTemplateFile
0x140048b87  mov     [rsp+320h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140048b8f  mov     [rsp+320h+dwCreationDisposition], 3; dwCreationDisposition
0x140048b97  xor     r9d, r9d; lpSecurityAttributes
0x140048b9a  lea     eax, [rdi+1]
0x140048b9d  mov     r8d, eax; dwShareMode
0x140048ba0  mov     edx, eax; dwDesiredAccess
0x140048ba2  call    cs:__imp_CreateFileW
0x140048ba9  nop     dword ptr [rax+rax+00h]
0x140048bae  mov     rbx, rax
0x140048bb1  mov     [rsp+320h+var_2E0], rax
0x140048bb6  dec     rax
0x140048bb9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140048bbd  ja      loc_140048F1A
0x140048bc3  xorps   xmm0, xmm0
0x140048bc6  xor     eax, eax
0x140048bc8  movups  xmmword ptr [rbp+220h+lpOutBuffer], xmm0
0x140048bcf  mov     [rbp+220h+var_D0], rax
0x140048bd6  lea     rcx, [rbp+220h+lpOutBuffer]
0x140048bdd  call    ??0?$vector@UVpSubnodeMetadata@VirtualMachine@Config@@V?$allocator@UVpSubnodeMetadata@VirtualMachine@Config@@@std@@@std@@QEAA@XZ; std::vector<Config::VirtualMachine::VpSubnodeMetadata>::vector<Config::VirtualMachine::VpSubnodeMetadata>(void)
0x140048be2  nop
0x140048be3  lea     ecx, [rdi+34h]
0x140048be6  mov     [rbp+220h+nOutBufferSize], ecx
0x140048bec  mov     r14d, ecx
0x140048bef  mov     rdx, [rbp+220h+lpOutBuffer]
0x140048bf6  mov     r13, [rbp+220h+lpOutBuffer+8]
0x140048bfd  mov     rcx, r13
0x140048c00  sub     rcx, rdx
0x140048c03  cmp     r14, rcx
0x140048c06  jnb     short loc_140048C0E
0x140048c08  lea     rax, [r14+rdx]
0x140048c0c  jmp     short loc_140048C44
0x140048c0e  jbe     short loc_140048C4B
0x140048c10  mov     rax, [rbp+220h+var_D0]
0x140048c17  sub     rax, rdx
0x140048c1a  cmp     r14, rax
0x140048c1d  jbe     short loc_140048C30
0x140048c1f  mov     rdx, r14
0x140048c22  lea     rcx, [rbp+220h+lpOutBuffer]
0x140048c29  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140048c2e  jmp     short loc_140048C4B
0x140048c30  sub     r14, rcx
0x140048c33  mov     r8, r14; Size
0x140048c36  xor     edx, edx; Val
0x140048c38  mov     rcx, r13; void *
0x140048c3b  call    memset_0
0x140048c40  lea     rax, [r14+r13]
0x140048c44  mov     [rbp+220h+lpOutBuffer+8], rax
0x140048c4b  mov     eax, [rbp+220h+nOutBufferSize]
0x140048c51  mov     rcx, [rbp+220h+lpOutBuffer]
0x140048c58  mov     [rsp+320h+lpOverlapped], rdi; lpOverlapped
0x140048c5d  lea     rdx, [rbp+220h+nOutBufferSize]
0x140048c64  mov     [rsp+320h+hTemplateFile], rdx; lpBytesReturned
0x140048c69  mov     [rsp+320h+dwFlagsAndAttributes], eax; nOutBufferSize
0x140048c6d  mov     qword ptr [rsp+320h+dwCreationDisposition], rcx; unsigned int
0x140048c72  xor     r9d, r9d; nInBufferSize
0x140048c75  xor     r8d, r8d; lpInBuffer
0x140048c78  mov     edx, 226444h; dwIoControlCode
0x140048c7d  mov     rcx, rbx; hDevice
0x140048c80  call    cs:__imp_DeviceIoControl
0x140048c87  nop     dword ptr [rax+rax+00h]
0x140048c8c  test    eax, eax
0x140048c8e  jnz     short loc_140048CD8
0x140048c90  call    cs:__imp_GetLastError
0x140048c97  nop     dword ptr [rax+rax+00h]
0x140048c9c  cmp     eax, 0EAh
0x140048ca1  jz      short loc_140048CAE
0x140048ca3  mov     rcx, [rbp+228h]; this
0x140048caa  test    eax, eax
0x140048cac  jnz     short loc_140048CC3
0x140048cae  mov     rax, [rbp+220h+lpOutBuffer]
0x140048cb5  mov     ecx, [rax]
0x140048cb7  lea     ecx, ds:14h[rcx*2]
0x140048cbe  jmp     loc_140048BE6
0x140048cc3  mov     r9d, eax; char *
0x140048cc6  lea     r8, aOnecoreVmCompu_12; "onecore\\vm\\compute\\management\\orche"...
0x140048ccd  mov     edx, 82h; void *
0x140048cd2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140048cd8  mov     r13, [rbp+220h+lpOutBuffer]
0x140048cdf  cmp     dword ptr [r12+28h], 1
0x140048ce5  jnz     short loc_140048D15
0x140048ce7  test    byte ptr [r13+10h], 1
0x140048cec  jnz     short loc_140048D15
0x140048cee  mov     rax, [r12]
0x140048cf2  mov     [r15], rax
0x140048cf5  mov     [r15+8], dil
0x140048cf9  lea     rcx, [rbp+220h+lpOutBuffer]
0x140048d00  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140048d05  nop
0x140048d06  lea     rcx, [rsp+320h+var_2E0]; void *
0x140048d0b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140048d10  jmp     loc_140048AE8
0x140048d15  mov     r14d, 0FFFFh
0x140048d1b  cmp     dword ptr [r12+28h], 2
0x140048d21  jnz     short loc_140048D55
0x140048d23  mov     r8, rsi
0x140048d26  lea     rdx, [rsp+320h+var_2B8]
0x140048d2b  lea     rcx, [r12+30h]
0x140048d30  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNetworkProperty@System@Responses@Schema@@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNetworkProperty@System@Responses@Schema@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNetworkProperty@System@Responses@Schema@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Schema::Responses::System::NetworkProperty,std::less<void>,std::allocator<std::pair<std::wstring const,Schema::Responses::System::NetworkProperty>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x140048d35  mov     r8, rsi
0x140048d38  mov     r14, [rsp+320h+var_2A8]
0x140048d3d  mov     rdx, r14
0x140048d40  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>,std::less<void>,std::allocator<std::pair<std::wstring const,Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>>,void *> * const,std::wstring const &)
0x140048d45  test    al, al
0x140048d47  jz      short loc_140048CEE
0x140048d49  cmp     r14, [r12+30h]
0x140048d4e  jz      short loc_140048CEE
0x140048d50  movzx   r14d, word ptr [r14+40h]
0x140048d55  mov     [rbp+220h+var_E8], rdi
0x140048d5c  xor     edx, edx; Val
0x140048d5e  mov     r8d, 1A0h; Size
0x140048d64  lea     rcx, [rbp+220h+var_290]; void *
0x140048d68  call    memset_0
0x140048d6d  mov     [rbp+220h+var_290], 1A0h
0x140048d74  mov     [rbp+220h+var_288], 1
0x140048d7b  mov     [rbp+220h+var_280], rbx
0x140048d7f  xor     edx, edx
0x140048d81  lea     rcx, [rbp+220h+var_E8]
0x140048d88  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHCMNOTIFICATION__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(HCMNOTIFICATION__ *)
0x140048d8d  lea     r9, [rbp+220h+var_E8]
0x140048d94  lea     r8, ?GpuPnPListener@GpuDetails@VirtualGpu@VmCommonHelpers@ComputeService@@YAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; ComputeService::VmCommonHelpers::VirtualGpu::GpuDetails::GpuPnPListener(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x140048d9b  mov     rdx, r12
0x140048d9e  lea     rcx, [rbp+220h+var_290]
0x140048da2  call    cs:__imp_CM_Register_Notification
0x140048da9  nop     dword ptr [rax+rax+00h]
0x140048dae  test    eax, eax
0x140048db0  jz      short loc_140048DE5
0x140048db2  mov     edx, 1Fh; DefaultErr
0x140048db7  mov     ecx, eax; CmReturnCode
0x140048db9  call    cs:__imp_CM_MapCrToWin32Err
0x140048dc0  nop     dword ptr [rax+rax+00h]
0x140048dc5  mov     rcx, [rbp+228h]; this
0x140048dcc  test    eax, eax
0x140048dce  jz      short loc_140048DE5
0x140048dd0  mov     r9d, eax; char *
0x140048dd3  lea     r8, aOnecoreVmCompu_12; "onecore\\vm\\compute\\management\\orche"...
0x140048dda  mov     edx, 0B8h; void *
0x140048ddf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140048de5  lea     rcx, [r12+10h]
0x140048dea  mov     r8, rsi
0x140048ded  lea     rdx, [rsp+320h+Uuid]
0x140048df2  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>>,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>>>>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x140048df7  mov     rcx, [rax]
0x140048dfa  add     rcx, 40h ; '@'
0x140048dfe  lea     rax, [rbp+220h+var_E8]
0x140048e05  cmp     rcx, rax
0x140048e08  jz      short loc_140048E1D
0x140048e0a  mov     rdx, [rbp+220h+var_E8]
0x140048e11  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHCMNOTIFICATION__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(HCMNOTIFICATION__ *)
0x140048e16  mov     [rbp+220h+var_E8], rdi
0x140048e1d  lea     rcx, [rbp+220h+var_A0]; void *
0x140048e24  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140048e29  mov     [rbp+220h+var_80], 0FFFFFFFFFFFFFFFFh
0x140048e34  xorps   xmm0, xmm0
0x140048e37  movups  [rbp+220h+var_78], xmm0
0x140048e3e  movups  [rbp+220h+var_68], xmm0
0x140048e45  movups  [rbp+220h+var_58], xmm0
0x140048e4c  mov     rdx, rsi
0x140048e4f  lea     rcx, [rbp+220h+var_A0]
0x140048e56  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140048e5b  lea     rdx, [rsp+320h+var_2E0]
0x140048e60  lea     rcx, [rbp+220h+var_80]
  ... truncated ...
```
