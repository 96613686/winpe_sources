# ComputeService::Management::_anonymous_namespace_::ModifyVSmbShare

- ea: `0x1400a63d4`
- end: `0x1400a666c`
- name: `ComputeService::Management::_anonymous_namespace_::ModifyVSmbShare`
- size: `664`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400a5de0`

## callees

- `0x140005360`
- `0x1400083bc`
- `0x140008760`
- `0x14000ddac`
- `0x14000ea60`
- `0x14000f93c`
- `0x14002c114`
- `0x140034170`
- `0x1400393b8`
- `0x14003a318`
- `0x14003a9ac`
- `0x140041b14`
- `0x140041d9c`
- `0x14004346c`
- `0x1400a3690`
- `0x1400a63d4`
- `0x1400a9770`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400a658d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400a658d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400a64d6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400a64d6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400a6565`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400a6565`

## string_xrefs

- `0x1400a65e2`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmdirectorchestrator.cpp`
- `0x1400a65fa`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmdirectorchestrator.cpp`
- `0x1400a665a`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmdirectorchestrator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ComputeService::Management::_anonymous_namespace_::ModifyVSmbShare(int a1, __int64 a2)
{
  _BYTE *v2; // rax
  const WCHAR *p_lpFileName; // rcx
  char *FileW; // rbx
  const char *v5; // r9
  const char *v6; // r9
  __int64 v7; // rax
  __int64 v8; // rax
  unsigned int v9; // eax
  const char *v10; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[16]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v14; // [rsp+58h] [rbp-A8h]
  char *v15; // [rsp+60h] [rbp-A0h]
  __int16 InBuffer[2]; // [rsp+68h] [rbp-98h] BYREF
  int OutBuffer; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD BytesReturned[4]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v19; // [rsp+80h] [rbp-80h] BYREF
  __m128i si128; // [rsp+90h] [rbp-70h]
  _OWORD v21[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v22; // [rsp+C0h] [rbp-40h]
  __int64 v23; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v24; // [rsp+D0h] [rbp-30h]
  _OWORD v25[3]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v26; // [rsp+110h] [rbp+10h] BYREF
  __int64 v27; // [rsp+120h] [rbp+20h]
  __int64 v28; // [rsp+128h] [rbp+28h]
  __int64 v29; // [rsp+130h] [rbp+30h]
  __int64 v30; // [rsp+138h] [rbp+38h]
  char v31; // [rsp+140h] [rbp+40h]
  __int128 v32; // [rsp+150h] [rbp+50h] BYREF
  __int64 v33; // [rsp+160h] [rbp+60h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  if ( a1 != 1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x159,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmdirectorchestrator.cpp",
      (const char *)0x80070032LL,
      dwCreationDisposition);
  v19 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19) = 0;
  v21[0] = 0;
  v21[1] = si128;
  LOWORD(v21[0]) = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  memset(v25, 0, sizeof(v25));
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v2 = (_BYTE *)Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::VirtualMachines::Resources::Storage::VirtualSmbShare>(
                  a2,
                  &lpFileName,
                  &v19);
  if ( !*v2 )
  {
    v7 = std::shared_ptr<ComputeService::Management::ComputeSystem>::operator-><ComputeService::Management::ComputeSystem,0>((__int64)(v2 + 8));
    v8 = std::wstring::c_str(v7);
    v9 = wil::verify_hresult<long>(2147942413LL, v8);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x1F,
      (unsigned int)"OneCore\\Internal\\VM\\inc\\MarshalUtilities.h",
      (const char *)v9,
      (int)"%ls",
      v10);
  }
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v13);
  Vml::FormatString(&lpFileName, (wchar_t *)L"\\\\?\\VMSMB\\VSMB-{dcc079ae-60ba-4d07-847c-3493609c0870}\\%ls");
  p_lpFileName = (const WCHAR *)&lpFileName;
  if ( v14 > 7 )
    p_lpFileName = lpFileName;
  FileW = (char *)CreateFileW(p_lpFileName, 0, 0, 0, 3u, 0x2000000u, 0);
  v15 = FileW;
  std::wstring::~wstring(&lpFileName);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmdirectorchestrator.cpp",
      v5);
  OutBuffer = 0;
  BytesReturned[0] = 0;
  InBuffer[0] = 2;
  v32 = 0;
  v33 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v32, 28);
  if ( !DeviceIoControl(FileW, 0x9043Cu, InBuffer, 2u, &OutBuffer, 4u, BytesReturned, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x176,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmdirectorchestrator.cpp",
      v6);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v32);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  std::vector<Schema::VirtualMachines::Resources::Storage::VirtualSmbAlternateDataStream>::_Tidy(&v26);
  std::vector<std::wstring>::_Tidy((char *)&v25[1] + 8);
  std::vector<enum Schema::VirtualMachines::Resources::Compute::XsaveProcessorFeature>::~vector<enum Schema::VirtualMachines::Resources::Compute::XsaveProcessorFeature>(v25);
  std::vector<std::wstring>::_Tidy(&v23);
  std::wstring::~wstring(v21);
  std::wstring::~wstring(&v19);
}

```

## disassembly

```asm
0x1400a63d4  push    rbp
0x1400a63d6  push    rbx
0x1400a63d7  push    rsi
0x1400a63d8  push    rdi
0x1400a63d9  lea     rbp, [rsp-78h]
0x1400a63de  sub     rsp, 178h
0x1400a63e5  mov     rax, cs:__security_cookie
0x1400a63ec  xor     rax, rsp
0x1400a63ef  mov     [rbp+90h+var_28], rax
0x1400a63f3  mov     r9, rdx
0x1400a63f6  xor     esi, esi
0x1400a63f8  mov     rax, [rbp+98h]
0x1400a63ff  cmp     ecx, 1
0x1400a6402  jnz     loc_1400A65F4
0x1400a6408  xorps   xmm0, xmm0
0x1400a640b  movups  [rbp+90h+var_110], xmm0
0x1400a640f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400a6417  movdqa  [rbp+90h+var_100], xmm1
0x1400a641c  mov     word ptr [rbp+90h+var_110], si
0x1400a6420  movups  [rbp+90h+var_F0], xmm0
0x1400a6424  movdqa  [rbp+90h+var_E0], xmm1
0x1400a6429  mov     word ptr [rbp+90h+var_F0], si
0x1400a642d  mov     [rbp+90h+var_D0], esi
0x1400a6430  mov     [rbp+90h+var_C8], rsi
0x1400a6434  movdqa  [rbp+90h+var_C0], xmm0
0x1400a6439  xorps   xmm1, xmm1
0x1400a643c  movdqa  [rbp+90h+var_B0], xmm1
0x1400a6441  movdqa  [rbp+90h+var_A0], xmm0
0x1400a6446  movdqa  [rbp+90h+var_90], xmm1
0x1400a644b  movdqa  [rbp+90h+var_80], xmm0
0x1400a6450  mov     [rbp+90h+var_70], rsi
0x1400a6454  mov     [rbp+90h+var_68], rsi
0x1400a6458  mov     [rbp+90h+var_60], rsi
0x1400a645c  mov     [rbp+90h+var_58], rsi
0x1400a6460  mov     [rbp+90h+var_50], sil
0x1400a6464  lea     r8, [rbp+90h+var_110]
0x1400a6468  lea     rdx, [rsp+190h+lpFileName]
0x1400a646d  mov     rcx, r9
0x1400a6470  call    ??$Unmarshal@UVirtualSmbShare@Storage@Resources@VirtualMachines@Schema@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEBA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@PEAUVirtualSmbShare@Storage@Resources@VirtualMachines@Schema@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::Unmarshal<Schema::VirtualMachines::Resources::Storage::VirtualSmbShare>(Schema::VirtualMachines::Resources::Storage::VirtualSmbShare *)
0x1400a6475  nop
0x1400a6476  cmp     [rax], sil
0x1400a6479  jz      loc_1400A660F
0x1400a647f  lea     rcx, [rsp+190h+var_148]
0x1400a6484  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x1400a6489  lea     r8, [rbp+90h+var_110]
0x1400a648d  cmp     qword ptr [rbp+90h+var_100+8], 7
0x1400a6492  cmova   r8, qword ptr [rbp+90h+var_110]
0x1400a6497  lea     rdx, aVmsmbVsmbDcc07; "\\\\?\\VMSMB\\VSMB-{dcc079ae-60ba-4d07-"...
0x1400a649e  lea     rcx, [rsp+190h+lpFileName]; Src
0x1400a64a3  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x1400a64a8  lea     rcx, [rsp+190h+lpFileName]
0x1400a64ad  cmp     [rsp+190h+var_138], 7
0x1400a64b3  cmova   rcx, [rsp+190h+lpFileName]; lpFileName
0x1400a64b9  mov     [rsp+190h+hTemplateFile], rsi; hTemplateFile
0x1400a64be  mov     [rsp+190h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1400a64c6  mov     [rsp+190h+dwCreationDisposition], 3; dwCreationDisposition
0x1400a64ce  xor     r9d, r9d; lpSecurityAttributes
0x1400a64d1  xor     r8d, r8d; dwShareMode
0x1400a64d4  xor     edx, edx; dwDesiredAccess
0x1400a64d6  call    cs:__imp_CreateFileW
0x1400a64dc  mov     rbx, rax
0x1400a64df  mov     [rsp+190h+var_130], rax
0x1400a64e4  lea     rcx, [rsp+190h+lpFileName]; void *
0x1400a64e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400a64ee  lea     rax, [rbx+1]
0x1400a64f2  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400a64f8  setz    al
0x1400a64fb  mov     rcx, [rbp+98h]; this
0x1400a6502  test    al, al
0x1400a6504  jnz     loc_1400A665A
0x1400a650a  mov     [rsp+190h+OutBuffer], esi
0x1400a650e  mov     [rsp+190h+BytesReturned], esi
0x1400a6512  lea     edi, [rsi+2]
0x1400a6515  mov     [rsp+190h+InBuffer], di
0x1400a651a  xorps   xmm0, xmm0
0x1400a651d  xor     eax, eax
0x1400a651f  movups  [rbp+90h+var_40], xmm0
0x1400a6523  mov     [rbp+90h+var_30], rax
0x1400a6527  lea     edx, [rsi+1Ch]; int
0x1400a652a  lea     rcx, [rbp+90h+var_40]; this
0x1400a652e  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x1400a6533  nop
0x1400a6534  mov     [rsp+190h+lpOverlapped], rsi; lpOverlapped
0x1400a6539  lea     rax, [rsp+190h+BytesReturned]
0x1400a653e  mov     [rsp+190h+hTemplateFile], rax; lpBytesReturned
0x1400a6543  mov     [rsp+190h+dwFlagsAndAttributes], 4; nOutBufferSize
0x1400a654b  lea     rax, [rsp+190h+OutBuffer]
0x1400a6550  mov     qword ptr [rsp+190h+dwCreationDisposition], rax; lpOutBuffer
0x1400a6555  mov     r9d, edi; nInBufferSize
0x1400a6558  lea     r8, [rsp+190h+InBuffer]; lpInBuffer
0x1400a655d  mov     edx, 9043Ch; dwIoControlCode
0x1400a6562  mov     rcx, rbx; hDevice
0x1400a6565  call    cs:__imp_DeviceIoControl
0x1400a656b  mov     rcx, [rbp+98h]; this
0x1400a6572  test    eax, eax
0x1400a6574  jz      short loc_1400A65E2
0x1400a6576  lea     rcx, [rbp+90h+var_40]; this
0x1400a657a  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x1400a657f  nop
0x1400a6580  lea     rax, [rbx-1]
0x1400a6584  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400a6588  ja      short loc_1400A6594
0x1400a658a  mov     rcx, rbx; hObject
0x1400a658d  call    cs:__imp_CloseHandle
0x1400a6593  nop
0x1400a6594  lea     rcx, [rbp+90h+var_80]
0x1400a6598  call    ?_Tidy@?$vector@UVirtualSmbAlternateDataStream@Storage@Resources@VirtualMachines@Schema@@V?$allocator@UVirtualSmbAlternateDataStream@Storage@Resources@VirtualMachines@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::VirtualMachines::Resources::Storage::VirtualSmbAlternateDataStream>::_Tidy(void)
0x1400a659d  lea     rcx, [rbp+90h+var_A0+8]
0x1400a65a1  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1400a65a6  lea     rcx, [rbp+90h+var_B0]
0x1400a65aa  call    ??1?$vector@W4XsaveProcessorFeature@Compute@Resources@VirtualMachines@Schema@@V?$allocator@W4XsaveProcessorFeature@Compute@Resources@VirtualMachines@Schema@@@std@@@std@@QEAA@XZ; std::vector<Schema::VirtualMachines::Resources::Compute::XsaveProcessorFeature>::~vector<Schema::VirtualMachines::Resources::Compute::XsaveProcessorFeature>(void)
0x1400a65af  lea     rcx, [rbp+90h+var_C8]
0x1400a65b3  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1400a65b8  lea     rcx, [rbp+90h+var_F0]; void *
0x1400a65bc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400a65c1  lea     rcx, [rbp+90h+var_110]; void *
0x1400a65c5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400a65ca  mov     rcx, [rbp+90h+var_28]
0x1400a65ce  xor     rcx, rsp; StackCookie
0x1400a65d1  call    __security_check_cookie
0x1400a65d6  add     rsp, 178h
0x1400a65dd  pop     rdi
0x1400a65de  pop     rsi
0x1400a65df  pop     rbx
0x1400a65e0  pop     rbp
0x1400a65e1  retn
0x1400a65e2  lea     r8, aOnecoreVmCompu_8; "onecore\\vm\\compute\\management\\orche"...
0x1400a65e9  mov     edx, 176h; void *
0x1400a65ee  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400a65f4  mov     r9d, 80070032h; char *
0x1400a65fa  lea     r8, aOnecoreVmCompu_8; "onecore\\vm\\compute\\management\\orche"...
0x1400a6601  mov     edx, 159h; void *
0x1400a6606  mov     rcx, rax; this
0x1400a6609  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400a660f  lea     rcx, [rax+8]
0x1400a6613  call    ??$?CVComputeSystem@Management@ComputeService@@$0A@@?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@QEBAPEAVComputeSystem@Management@ComputeService@@XZ; std::shared_ptr<ComputeService::Management::ComputeSystem>::operator-><ComputeService::Management::ComputeSystem,0>(void)
0x1400a6618  mov     rcx, rax
0x1400a661b  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1400a6620  mov     rdx, rax
0x1400a6623  mov     ecx, 8007000Dh
0x1400a6628  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1400a662d  mov     r9d, eax; char *
0x1400a6630  mov     rcx, [rbp+98h]; this
0x1400a6637  mov     qword ptr [rsp+190h+dwFlagsAndAttributes], rdx; char *
0x1400a663c  lea     rax, aLs; "%ls"
0x1400a6643  mov     qword ptr [rsp+190h+dwCreationDisposition], rax; int
0x1400a6648  lea     r8, aOnecoreInterna; "OneCore\\Internal\\VM\\inc\\MarshalUtil"...
0x1400a664f  mov     edx, 1Fh; void *
0x1400a6654  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400a665a  lea     r8, aOnecoreVmCompu_8; "onecore\\vm\\compute\\management\\orche"...
0x1400a6661  mov     edx, 166h; void *
0x1400a6666  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
