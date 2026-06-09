# ComputeService::VmCommonHelpers::VirtualGpu::GpuDetails::AssignGpu(ComputeService::VmCommonHelpers::VirtualGpu::DisplayDevice &,ComputeService::VmCommonHelpers::VirtualGpu::GpuEnvironment &)

- ea: `0x1400942e0`
- end: `0x140094a09`
- name: `?AssignGpu@GpuDetails@VirtualGpu@VmCommonHelpers@ComputeService@@YAXAEAUDisplayDevice@234@AEAUGpuEnvironment@234@@Z`
- size: `1833`
- prototype: `void __fastcall(ComputeService::VmCommonHelpers::VirtualGpu::GpuDetails *__hidden this, struct ComputeService::VmCommonHelpers::VirtualGpu::DisplayDevice *, struct ComputeService::VmCommonHelpers::VirtualGpu::GpuEnvironment *)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140048514`
- `0x1401ef080`

## callees

- `0x1400142a0`
- `0x140017040`
- `0x14001d490`
- `0x140024030`
- `0x1400243f0`
- `0x140026dd0`
- `0x14002fa20`
- `0x1400421f0`
- `0x140080180`
- `0x1400942e0`
- `0x140094ba8`
- `0x140094bf4`
- `0x1400962a8`
- `0x1400b1adc`
- `0x1400c40e0`
- `0x1401332f0`
- `0x140134048`
- `0x1401eee5c`
- `0x1401efa28`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14009453c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14009453c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400943d1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140094630`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400943d1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140094630`

## string_xrefs

- `0x1400943e8`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualgpu.cpp`
- `0x14009456d`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualgpu.cpp`
- `0x140094659`: `onecore\vm\compute\management\orchestration\shared\vmcommon\virtualgpu.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall ComputeService::VmCommonHelpers::VirtualGpu::GpuDetails::AssignGpu(
        ComputeService::VmCommonHelpers::VirtualGpu::GpuDetails *this,
        struct ComputeService::VmCommonHelpers::VirtualGpu::DisplayDevice *a2,
        struct ComputeService::VmCommonHelpers::VirtualGpu::GpuEnvironment *a3)
{
  __int64 v5; // r15
  const char *v6; // r9
  __m128i v7; // xmm6
  __m128i v8; // xmm9
  __m128i v9; // xmm7
  __m128i v10; // xmm11
  __m128i v11; // xmm10
  __m128i v12; // xmm8
  __int64 v13; // r12
  ComputeService::VmCommonHelpers::VirtualGpu::GpuDetails *v14; // r8
  const WCHAR *v15; // rcx
  HANDLE FileW; // rbx
  __m128i v17; // xmm6
  __m128i v18; // xmm11
  __m128i v19; // xmm12
  __m128i v20; // xmm13
  __m128i v21; // xmm14
  __m128i v22; // xmm15
  __int64 v23; // rdx
  __int64 v24; // rcx
  int lpOutBuffer; // [rsp+28h] [rbp-E0h]
  const char *lpOutBuffera; // [rsp+28h] [rbp-E0h]
  __int64 v27; // [rsp+48h] [rbp-C0h] BYREF
  __m128i v28; // [rsp+50h] [rbp-B8h] BYREF
  __m128i v29; // [rsp+60h] [rbp-A8h]
  struct ComputeService::VmCommonHelpers::VirtualGpu::DisplayDevice *v30; // [rsp+70h] [rbp-98h]
  ComputeService::VmCommonHelpers::VirtualGpu::GpuDetails *v31; // [rsp+78h] [rbp-90h]
  char v32; // [rsp+80h] [rbp-88h]
  __m128i v33[2]; // [rsp+88h] [rbp-80h] BYREF
  __m256i v34; // [rsp+A8h] [rbp-60h]
  __int128 v35; // [rsp+C8h] [rbp-40h]
  __int128 v36; // [rsp+D8h] [rbp-30h]
  __int128 v37; // [rsp+E8h] [rbp-20h]
  __int128 v38; // [rsp+F8h] [rbp-10h]
  __int128 v39; // [rsp+158h] [rbp+50h]
  _WORD InBuffer[2]; // [rsp+168h] [rbp+60h] BYREF
  DWORD BytesReturned; // [rsp+16Ch] [rbp+64h] BYREF
  __int64 v42; // [rsp+170h] [rbp+68h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+178h] [rbp+70h] BYREF
  unsigned __int16 v44; // [rsp+198h] [rbp+90h] BYREF
  __m256i v45; // [rsp+1A0h] [rbp+98h]
  __int128 v46; // [rsp+1C0h] [rbp+B8h]
  __int128 v47; // [rsp+1D0h] [rbp+C8h]
  __int128 v48; // [rsp+1E0h] [rbp+D8h]
  __int128 v49; // [rsp+1F0h] [rbp+E8h]
  __int64 v50; // [rsp+200h] [rbp+F8h]
  char v51; // [rsp+208h] [rbp+100h]
  char v52; // [rsp+209h] [rbp+101h]
  char v53; // [rsp+20Ah] [rbp+102h]
  int v54; // [rsp+218h] [rbp+110h] BYREF
  __int128 v55; // [rsp+220h] [rbp+118h]
  _BYTE v56[32]; // [rsp+230h] [rbp+128h] BYREF
  unsigned __int64 v57; // [rsp+250h] [rbp+148h]
  char v58; // [rsp+258h] [rbp+150h]
  __int64 v59; // [rsp+260h] [rbp+158h]
  char v60; // [rsp+268h] [rbp+160h]
  unsigned __int64 v61; // [rsp+270h] [rbp+168h]
  char v62; // [rsp+278h] [rbp+170h]
  __int64 v63; // [rsp+280h] [rbp+178h]
  char v64; // [rsp+288h] [rbp+180h]
  unsigned __int64 v65; // [rsp+290h] [rbp+188h]
  char v66; // [rsp+298h] [rbp+190h]
  __int64 v67; // [rsp+2A0h] [rbp+198h]
  char v68; // [rsp+2A8h] [rbp+1A0h]
  unsigned __int64 v69; // [rsp+2B0h] [rbp+1A8h]
  char v70; // [rsp+2B8h] [rbp+1B0h]
  __int64 v71; // [rsp+2C0h] [rbp+1B8h]
  char v72; // [rsp+2C8h] [rbp+1C0h]
  unsigned __int64 v73; // [rsp+2D0h] [rbp+1C8h]
  char v74; // [rsp+2D8h] [rbp+1D0h]
  __int64 v75; // [rsp+2E0h] [rbp+1D8h]
  char v76; // [rsp+2E8h] [rbp+1E0h]
  unsigned __int64 v77; // [rsp+2F0h] [rbp+1E8h]
  char v78; // [rsp+2F8h] [rbp+1F0h]
  __int64 v79; // [rsp+300h] [rbp+1F8h]
  char v80; // [rsp+308h] [rbp+200h]
  _BYTE v81[32]; // [rsp+338h] [rbp+230h] BYREF
  __int64 v82; // [rsp+358h] [rbp+250h]
  __int16 v83; // [rsp+368h] [rbp+260h]
  __int64 v84; // [rsp+36Ch] [rbp+264h]
  __int128 v85; // [rsp+374h] [rbp+26Ch]
  __int64 v86; // [rsp+388h] [rbp+280h]
  unsigned __int64 v87; // [rsp+390h] [rbp+288h]
  __int64 v88; // [rsp+398h] [rbp+290h]
  unsigned __int64 v89; // [rsp+3A0h] [rbp+298h]
  __int64 v90; // [rsp+3A8h] [rbp+2A0h]
  unsigned __int64 v91; // [rsp+3B0h] [rbp+2A8h]
  __int64 v92; // [rsp+3B8h] [rbp+2B0h]
  unsigned __int64 v93; // [rsp+3C0h] [rbp+2B8h]
  __int64 v94; // [rsp+3C8h] [rbp+2C0h]
  unsigned __int64 v95; // [rsp+3D0h] [rbp+2C8h]
  __int64 v96; // [rsp+3D8h] [rbp+2D0h]
  unsigned __int64 v97; // [rsp+3E0h] [rbp+2D8h]
  _BYTE v98[32]; // [rsp+3E8h] [rbp+2E0h] BYREF
  __int128 OutBuffer; // [rsp+408h] [rbp+300h] BYREF
  __m128i v100; // [rsp+418h] [rbp+310h]
  __m128i v101; // [rsp+428h] [rbp+320h]
  __m128i v102; // [rsp+448h] [rbp+340h]
  __int128 v103; // [rsp+458h] [rbp+350h]
  __m128i v104; // [rsp+468h] [rbp+360h]
  __m128i v105; // [rsp+478h] [rbp+370h]
  __m128i v106; // [rsp+498h] [rbp+390h]
  __int64 v107; // [rsp+4A8h] [rbp+3A0h]
  _BYTE v108[8]; // [rsp+4B8h] [rbp+3B0h] BYREF
  __m128i v109; // [rsp+4C0h] [rbp+3B8h]
  __int128 v110; // [rsp+4D0h] [rbp+3C8h]
  __m128i v111; // [rsp+4E0h] [rbp+3D8h]
  __m128i v112; // [rsp+4F0h] [rbp+3E8h]
  __m128i v113; // [rsp+500h] [rbp+3F8h]
  __m128i v114; // [rsp+510h] [rbp+408h]
  __m128i v115; // [rsp+520h] [rbp+418h]
  __m128i v116; // [rsp+530h] [rbp+428h]
  wil::details::in1diag3 *retaddr; // [rsp+620h] [rbp+518h]

  Config::Devices::Gpup::GpuPartition::GpuPartition((Config::Devices::Gpup::GpuPartition *)&v54);
  BytesReturned = 0;
  v30 = a2;
  v31 = this;
  v32 = 1;
  v5 = *(_QWORD *)((char *)this + 60);
  memset_0(&OutBuffer, 0, 0xA8u);
  InBuffer[0] = *((_WORD *)this + 34);
  if ( !DeviceIoControl(*((HANDLE *)this + 4), 0x226448u, InBuffer, 2u, &OutBuffer, 0xA8u, &BytesReturned, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualgpu.cpp",
      v6);
  v34.m256i_i64[0] = OutBuffer;
  v7 = v100;
  v28 = v100;
  v8 = v101;
  v9 = v102;
  v39 = v103;
  v10 = v104;
  v29 = v104;
  v11 = v105;
  v12 = v106;
  v13 = v107;
  memset_0(&v44, 0, 0x78u);
  memset_0(v108, 0, 0x88u);
  v34.m256i_i64[1] = _mm_srli_si128(v7, 8).m128i_u64[0];
  v34.m256i_i64[2] = v8.m128i_i64[0];
  v34.m256i_i64[3] = v34.m256i_i64[1];
  *(_QWORD *)&v35 = v9.m128i_i64[0];
  *((_QWORD *)&v35 + 1) = _mm_srli_si128(v9, 8).m128i_u64[0];
  *(_QWORD *)&v36 = v9.m128i_i64[0];
  *((_QWORD *)&v36 + 1) = _mm_srli_si128(v10, 8).m128i_u64[0];
  *(_QWORD *)&v37 = v11.m128i_i64[0];
  *((_QWORD *)&v37 + 1) = *((_QWORD *)&v36 + 1);
  *(_QWORD *)&v38 = v12.m128i_i64[0];
  *((_QWORD *)&v38 + 1) = _mm_srli_si128(v12, 8).m128i_u64[0];
  std::wstring::wstring(lpFileName);
  if ( *((_QWORD *)this + 3) <= 7u )
    v14 = this;
  else
    v14 = *(ComputeService::VmCommonHelpers::VirtualGpu::GpuDetails **)this;
  Vml::FormatString(lpFileName, L"%ws\\VGPUCreator", v14);
  v15 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v15 = lpFileName[0];
  FileW = CreateFileW(v15, 1u, 1u, 0, 3u, 0x80u, 0);
  v27 = (__int64)FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x124,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualgpu.cpp",
      (const char *)0x8000FFFFLL,
      lpOutBuffer);
  v34.m256i_i64[0] = (__int64)FileW;
  v44 = *((_WORD *)this + 40);
  v51 = *((_BYTE *)this + 82);
  v52 = *((_BYTE *)this + 83);
  v53 = *((_BYTE *)this + 84);
  v45 = v34;
  v46 = v35;
  v47 = v36;
  v48 = v37;
  v49 = v38;
  v50 = v12.m128i_i64[0];
  if ( !DeviceIoControl(*((HANDLE *)this + 4), 0x226454u, &v44, 0x78u, v108, 0x88u, &BytesReturned, 0) )
  {
    LODWORD(lpOutBuffera) = v44;
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmcommon\\virtualgpu.cpp",
      "fail to set partition details with partition id %d",
      lpOutBuffera);
  }
  v17 = v109;
  *(__m128i *)v34.m256i_i8 = v109;
  *(_OWORD *)&v34.m256i_u64[2] = v110;
  v18 = v111;
  v19 = v112;
  v20 = v113;
  v21 = v114;
  v22 = v115;
  v33[0] = v116;
  if ( *((_WORD *)this + 40) == 0xFFFF )
    *((_WORD *)this + 40) = _mm_cvtsi128_si32(v109);
  v54 = 256;
  v55 = *(_OWORD *)((char *)this + 40);
  std::wstring::assign(v56, &szPassword);
  v77 = _mm_srli_si128(v12, 8).m128i_u64[0];
  v78 = 1;
  v71 = v11.m128i_i64[0];
  v72 = 1;
  v65 = _mm_srli_si128(v9, 8).m128i_u64[0];
  v66 = 1;
  v59 = v8.m128i_i64[0];
  v60 = 1;
  v75 = v12.m128i_i64[0];
  v76 = 1;
  v69 = _mm_srli_si128(v29, 8).m128i_u64[0];
  v70 = 1;
  v63 = v9.m128i_i64[0];
  v64 = 1;
  v57 = _mm_srli_si128(v28, 8).m128i_u64[0];
  v58 = 1;
  v79 = v13;
  v80 = 1;
  v73 = _mm_srli_si128(v11, 8).m128i_u64[0];
  v74 = 1;
  v67 = v39;
  v68 = 1;
  v61 = _mm_srli_si128(v8, 8).m128i_u64[0];
  v62 = 1;
  std::wstring::operator=(v81, this);
  v82 = v5;
  v83 = _mm_cvtsi128_si32(v17);
  v84 = *(__int64 *)((char *)v34.m256i_i64 + 4);
  v85 = *(_OWORD *)((char *)&v34.m256i_u64[1] + 4);
  v86 = v18.m128i_i64[0];
  v87 = _mm_srli_si128(v18, 8).m128i_u64[0];
  v88 = v19.m128i_i64[0];
  v89 = _mm_srli_si128(v19, 8).m128i_u64[0];
  v90 = v20.m128i_i64[0];
  v91 = _mm_srli_si128(v20, 8).m128i_u64[0];
  v92 = v21.m128i_i64[0];
  v93 = _mm_srli_si128(v21, 8).m128i_u64[0];
  v94 = v22.m128i_i64[0];
  v95 = _mm_srli_si128(v22, 8).m128i_u64[0];
  v96 = v33[0].m128i_i64[0];
  v97 = _mm_srli_si128(v33[0], 8).m128i_u64[0];
  Marshal::ToConfigurationXml<Config::Devices::Gpup::GpuPartition &,>(v98, v23, &v54);
  v42 = 0;
  wil::MakeOrThrow<VmHandleBroker,_GUID &,_GUID const &>(&v42, (char *)this + 40, &CLSID_GpupVdev);
  v29.m128i_i64[0] = (__int64)&v28;
  v28.m128i_i64[0] = (__int64)FileW;
  v27 = -1;
  std::wstring::wstring(v33, &szPassword);
  VmHandleBrokerUtils::PutHandle(v42, v33, 0, &v28);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v33);
  ComputeService::Vmwp::AddWorkerProcessDevice(
    *((_QWORD *)a2 + 11),
    &CLSID_GpupVdev,
    (char *)this + 40,
    L"Microsoft GPU Partition",
    v98,
    256,
    v42);
  v32 = 0;
  v24 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v98);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v27);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)lpFileName);
  Config::Devices::Gpup::GpuPartition::~GpuPartition((Config::Devices::Gpup::GpuPartition *)&v54);
}

```

## disassembly

```asm
0x1400942e0  mov     rax, rsp
0x1400942e3  mov     [rax+18h], rbx
0x1400942e7  mov     [rax+20h], rsi
0x1400942eb  push    rbp
0x1400942ec  push    rdi
0x1400942ed  push    r12
0x1400942ef  push    r14
0x1400942f1  push    r15
0x1400942f3  lea     rbp, [rax-518h]
0x1400942fa  sub     rsp, 5F0h
0x140094301  movaps  xmmword ptr [rax-38h], xmm6
0x140094305  movaps  xmmword ptr [rax-48h], xmm7
0x140094309  movaps  xmmword ptr [rax-58h], xmm8
0x14009430e  movaps  xmmword ptr [rax-68h], xmm9
0x140094313  movaps  xmmword ptr [rax-78h], xmm10
0x140094318  movaps  xmmword ptr [rax-88h], xmm11
0x140094320  movaps  xmmword ptr [rax-98h], xmm12
0x140094328  movaps  xmmword ptr [rax-0A8h], xmm13
0x140094330  movaps  xmmword ptr [rax-0B8h], xmm14
0x140094338  movaps  xmmword ptr [rax-0C8h], xmm15
0x140094340  mov     rax, cs:__security_cookie
0x140094347  xor     rax, rsp
0x14009434a  mov     [rbp+510h+var_D0], rax
0x140094351  mov     r14, rdx
0x140094354  mov     rsi, rcx
0x140094357  lea     rcx, [rbp+510h+var_400]; this
0x14009435e  call    ??0GpuPartition@Gpup@Devices@Config@@QEAA@XZ; Config::Devices::Gpup::GpuPartition::GpuPartition(void)
0x140094363  nop
0x140094364  mov     [rbp+510h+BytesReturned], 0
0x14009436b  mov     [rsp+610h+var_5A8], r14
0x140094370  mov     [rsp+610h+var_5A0], rsi
0x140094375  mov     [rsp+610h+var_598], 1
0x14009437a  mov     r15, [rsi+3Ch]
0x14009437e  mov     ebx, 0A8h
0x140094383  mov     r8d, ebx; Size
0x140094386  xor     edx, edx; Val
0x140094388  lea     rcx, [rbp+510h+OutBuffer]; void *
0x14009438f  call    memset_0
0x140094394  movzx   eax, word ptr [rsi+44h]
0x140094398  mov     [rbp+510h+InBuffer], ax
0x14009439c  mov     [rsp+610h+lpOverlapped], 0; lpOverlapped
0x1400943a5  lea     rax, [rbp+510h+BytesReturned]
0x1400943a9  mov     [rsp+610h+lpBytesReturned], rax; lpBytesReturned
0x1400943ae  mov     [rsp+610h+nOutBufferSize], ebx; nOutBufferSize
0x1400943b2  lea     rax, [rbp+510h+OutBuffer]
0x1400943b9  mov     [rsp+610h+lpOutBuffer], rax; lpOutBuffer
0x1400943be  mov     r9d, 2; nInBufferSize
0x1400943c4  lea     r8, [rbp+510h+InBuffer]; lpInBuffer
0x1400943c8  mov     edx, 226448h; dwIoControlCode
0x1400943cd  mov     rcx, [rsi+20h]; hDevice
0x1400943d1  call    cs:__imp_DeviceIoControl
0x1400943d8  nop     dword ptr [rax+rax+00h]
0x1400943dd  test    eax, eax
0x1400943df  jnz     short loc_1400943F8
0x1400943e1  mov     rcx, [rbp+518h]; this
0x1400943e8  lea     r8, aOnecoreVmCompu_12; "onecore\\vm\\compute\\management\\orche"...
0x1400943ef  lea     edx, [rbx+50h]; void *
0x1400943f2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400943f8  movaps  xmm0, [rbp+510h+OutBuffer]
0x1400943ff  movups  [rbp+510h+var_570], xmm0
0x140094403  movaps  xmm6, [rbp+510h+var_200]
0x14009440a  movups  [rsp+610h+var_5D0+8], xmm6
0x14009440f  movaps  xmm9, [rbp+510h+var_1F0]
0x140094417  movaps  xmm0, [rbp+510h+var_1E0]
0x14009441e  movups  [rbp+510h+var_540], xmm0
0x140094422  movaps  xmm7, [rbp+510h+var_1D0]
0x140094429  movups  xmm0, [rbp+510h+var_1C0]
0x140094430  movups  [rbp+510h+var_4C0], xmm0
0x140094434  movaps  xmm11, [rbp+510h+var_1B0]
0x14009443c  movups  xmmword ptr [rsp+610h+var_5C0+8], xmm11
0x140094442  movaps  xmm10, [rbp+510h+var_1A0]
0x14009444a  movaps  xmm8, [rbp+510h+var_180]
0x140094452  mov     r12, [rbp+510h+var_170]
0x140094459  xor     edx, edx; Val
0x14009445b  lea     r8d, [rdx+78h]; Size
0x14009445f  lea     rcx, [rbp+510h+var_480]; void *
0x140094466  call    memset_0
0x14009446b  xor     edx, edx; Val
0x14009446d  mov     r8d, 88h; Size
0x140094473  lea     rcx, [rbp+510h+var_160]; void *
0x14009447a  call    memset_0
0x14009447f  movdqa  xmm0, xmm6
0x140094483  psrldq  xmm0, 8
0x140094488  movq    qword ptr [rbp+510h+var_570+8], xmm0
0x14009448d  movsd   qword ptr [rbp+510h+var_560], xmm9
0x140094493  movq    qword ptr [rbp+510h+var_560+8], xmm0
0x140094498  movsd   qword ptr [rbp+510h+var_550], xmm7
0x14009449d  movdqa  xmm0, xmm7
0x1400944a1  psrldq  xmm0, 8
0x1400944a6  movq    qword ptr [rbp+510h+var_550+8], xmm0
0x1400944ab  movsd   qword ptr [rbp+510h+var_540], xmm7
0x1400944b0  movdqa  xmm0, xmm11
0x1400944b5  psrldq  xmm0, 8
0x1400944ba  movq    qword ptr [rbp+510h+var_540+8], xmm0
0x1400944bf  movsd   qword ptr [rbp+510h+var_530], xmm10
0x1400944c5  movq    qword ptr [rbp+510h+var_530+8], xmm0
0x1400944ca  movsd   qword ptr [rbp+510h+var_520], xmm8
0x1400944d0  movdqa  xmm0, xmm8
0x1400944d5  psrldq  xmm0, 8
0x1400944da  movq    qword ptr [rbp+510h+var_520+8], xmm0
0x1400944df  lea     rcx, [rbp+510h+lpFileName]; void *
0x1400944e3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400944e8  nop
0x1400944e9  cmp     qword ptr [rsi+18h], 7
0x1400944ee  jbe     short loc_1400944F5
0x1400944f0  mov     r8, [rsi]
0x1400944f3  jmp     short loc_1400944F8
0x1400944f5  mov     r8, rsi
0x1400944f8  lea     rdx, aWsVgpucreator; "%ws\\VGPUCreator"
0x1400944ff  lea     rcx, [rbp+510h+lpFileName]
0x140094503  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x140094508  lea     rcx, [rbp+510h+lpFileName]
0x14009450c  cmp     [rbp+510h+var_488], 7
0x140094514  cmova   rcx, [rbp+510h+lpFileName]; lpFileName
0x140094519  mov     [rsp+610h+lpBytesReturned], 0; hTemplateFile
0x140094522  mov     [rsp+610h+nOutBufferSize], 80h; dwFlagsAndAttributes
0x14009452a  mov     dword ptr [rsp+610h+lpOutBuffer], 3; int
0x140094532  xor     r9d, r9d; lpSecurityAttributes
0x140094535  lea     edx, [r9+1]; dwDesiredAccess
0x140094539  mov     r8d, edx; dwShareMode
0x14009453c  call    cs:__imp_CreateFileW
0x140094543  nop     dword ptr [rax+rax+00h]
0x140094548  mov     rbx, rax
0x14009454b  mov     qword ptr [rsp+610h+var_5D0], rax
0x140094550  inc     rax
0x140094553  test    rax, 0FFFFFFFFFFFFFFFEh
0x140094559  setz    al
0x14009455c  mov     rcx, [rbp+518h]; this
0x140094563  test    al, al
0x140094565  jz      short loc_14009457F
0x140094567  mov     r9d, 8000FFFFh; char *
0x14009456d  lea     r8, aOnecoreVmCompu_12; "onecore\\vm\\compute\\management\\orche"...
0x140094574  mov     edx, 124h; void *
0x140094579  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14009457f  mov     qword ptr [rbp+510h+var_570], rbx
0x140094583  movzx   eax, word ptr [rsi+50h]
0x140094587  mov     [rbp+510h+var_480], ax
0x14009458e  mov     al, [rsi+52h]
0x140094591  mov     [rbp+510h+var_410], al
0x140094597  mov     al, [rsi+53h]
0x14009459a  mov     [rbp+510h+var_40F], al
0x1400945a0  mov     al, [rsi+54h]
0x1400945a3  mov     [rbp+510h+var_40E], al
0x1400945a9  movaps  xmm0, [rbp+510h+var_570]
0x1400945ad  movups  [rbp+510h+var_478], xmm0
0x1400945b4  movaps  xmm1, [rbp+510h+var_560]
0x1400945b8  movups  [rbp+510h+var_468], xmm1
0x1400945bf  movaps  xmm0, [rbp+510h+var_550]
0x1400945c3  movups  [rbp+510h+var_458], xmm0
0x1400945ca  movaps  xmm1, [rbp+510h+var_540]
0x1400945ce  movups  [rbp+510h+var_448], xmm1
0x1400945d5  movaps  xmm0, [rbp+510h+var_530]
0x1400945d9  movups  [rbp+510h+var_438], xmm0
0x1400945e0  movaps  xmm1, [rbp+510h+var_520]
0x1400945e4  movups  [rbp+510h+var_428], xmm1
0x1400945eb  movsd   [rbp+510h+var_418], xmm8
0x1400945f4  mov     [rsp+610h+lpOverlapped], 0; lpOverlapped
0x1400945fd  lea     rax, [rbp+510h+BytesReturned]
0x140094601  mov     [rsp+610h+lpBytesReturned], rax; lpBytesReturned
0x140094606  mov     [rsp+610h+nOutBufferSize], 88h; nOutBufferSize
0x14009460e  lea     rax, [rbp+510h+var_160]
0x140094615  mov     [rsp+610h+lpOutBuffer], rax; lpOutBuffer
0x14009461a  mov     r9d, 78h ; 'x'; nInBufferSize
0x140094620  lea     r8, [rbp+510h+var_480]; lpInBuffer
0x140094627  mov     edx, 226454h; dwIoControlCode
0x14009462c  mov     rcx, [rsi+20h]; hDevice
0x140094630  call    cs:__imp_DeviceIoControl
0x140094637  nop     dword ptr [rax+rax+00h]
0x14009463c  test    eax, eax
0x14009463e  jnz     short loc_14009466B
0x140094640  movzx   eax, [rbp+510h+var_480]
0x140094647  mov     rcx, [rbp+518h]; this
0x14009464e  mov     dword ptr [rsp+610h+lpOutBuffer], eax; char *
0x140094652  lea     r9, aFailToSetParti; "fail to set partition details with part"...
0x140094659  lea     r8, aOnecoreVmCompu_12; "onecore\\vm\\compute\\management\\orche"...
0x140094660  mov     edx, 135h; void *
0x140094665  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x14009466b  movups  xmm6, [rbp+510h+var_158]
0x140094672  movaps  [rbp+510h+var_570], xmm6
0x140094676  movups  xmm0, [rbp+510h+var_148]
0x14009467d  movaps  [rbp+510h+var_560], xmm0
0x140094681  movups  xmm11, [rbp+510h+var_138]
0x140094689  movups  xmm12, [rbp+510h+var_128]
0x140094691  movups  xmm13, [rbp+510h+var_118]
0x140094699  movups  xmm14, [rbp+510h+var_108]
0x1400946a1  movups  xmm15, [rbp+510h+var_F8]
0x1400946a9  movups  xmm0, [rbp+510h+var_E8]
0x1400946b0  movups  [rbp+510h+var_590], xmm0
0x1400946b4  mov     eax, 0FFFFh
0x1400946b9  cmp     [rsi+50h], ax
0x1400946bd  jnz     short loc_1400946C7
0x1400946bf  movd    eax, xmm6
0x1400946c3  mov     [rsi+50h], ax
0x1400946c7  mov     [rbp+510h+var_400], 100h
0x1400946d1  lea     rdi, [rsi+28h]
0x1400946d5  movups  xmm0, xmmword ptr [rdi]
0x1400946d8  movdqu  [rbp+510h+var_3F8], xmm0
0x1400946e0  lea     rdx, szPassword
0x1400946e7  lea     rcx, [rbp+510h+var_3E8]
0x1400946ee  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1400946f3  movdqa  xmm0, xmm8
0x1400946f8  psrldq  xmm0, 8
0x1400946fd  movq    [rbp+510h+var_328], xmm0
0x140094705  mov     [rbp+510h+var_320], 1
0x14009470c  movsd   [rbp+510h+var_358], xmm10
0x140094715  mov     [rbp+510h+var_350], 1
0x14009471c  movdqa  xmm0, xmm7
0x140094720  psrldq  xmm0, 8
0x140094725  movq    [rbp+510h+var_388], xmm0
0x14009472d  mov     [rbp+510h+var_380], 1
0x140094734  movsd   [rbp+510h+var_3B8], xmm9
0x14009473d  mov     [rbp+510h+var_3B0], 1
0x140094744  movsd   [rbp+510h+var_338], xmm8
0x14009474d  mov     [rbp+510h+var_330], 1
0x140094754  movups  xmm0, xmmword ptr [rsp+610h+var_5C0+8]
0x140094759  psrldq  xmm0, 8
0x14009475e  movq    [rbp+510h+var_368], xmm0
0x140094766  mov     [rbp+510h+var_360], 1
0x14009476d  movsd   [rbp+510h+var_398], xmm7
0x140094775  mov     [rbp+510h+var_390], 1
0x14009477c  movups  xmm0, [rsp+610h+var_5D0+8]
0x140094781  psrldq  xmm0, 8
0x140094786  movq    [rbp+510h+var_3C8], xmm0
0x14009478e  mov     [rbp+510h+var_3C0], 1
0x140094795  mov     [rbp+510h+var_318], r12
0x14009479c  mov     [rbp+510h+var_310], 1
0x1400947a3  psrldq  xmm10, 8
0x1400947a9  movq    [rbp+510h+var_348], xmm10
0x1400947b2  mov     [rbp+510h+var_340], 1
0x1400947b9  movups  xmm0, [rbp+510h+var_4C0]
0x1400947bd  movsd   [rbp+510h+var_378], xmm0
0x1400947c5  mov     [rbp+510h+var_370], 1
0x1400947cc  psrldq  xmm9, 8
0x1400947d2  movq    [rbp+510h+var_3A8], xmm9
0x1400947db  mov     [rbp+510h+var_3A0], 1
0x1400947e2  mov     rdx, rsi
0x1400947e5  lea     rcx, [rbp+510h+var_2E0]
0x1400947ec  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400947f1  mov     [rbp+510h+var_2C0], r15
0x1400947f8  movd    eax, xmm6
0x1400947fc  mov     [rbp+510h+var_2B0], ax
0x140094803  mov     rax, qword ptr [rbp+510h+var_570+4]
0x140094807  mov     [rbp+510h+var_2AC], rax
0x14009480e  movups  xmm0, [rbp+510h+var_570+0Ch]
0x140094812  movdqu  [rbp+510h+var_2A4], xmm0
0x14009481a  movsd   [rbp+510h+var_290], xmm11
0x140094823  psrldq  xmm11, 8
0x140094829  movq    [rbp+510h+var_288], xmm11
0x140094832  movsd   [rbp+510h+var_280], xmm12
0x14009483b  psrldq  xmm12, 8
0x140094841  movq    [rbp+510h+var_278], xmm12
0x14009484a  movsd   [rbp+510h+var_270], xmm13
0x140094853  psrldq  xmm13, 8
0x140094859  movq    [rbp+510h+var_268], xmm13
0x140094862  movsd   [rbp+510h+var_260], xmm14
0x14009486b  psrldq  xmm14, 8
0x140094871  movq    [rbp+510h+var_258], xmm14
0x14009487a  movsd   [rbp+510h+var_250], xmm15
0x140094883  psrldq  xmm15, 8
0x140094889  movq    [rbp+510h+var_248], xmm15
0x140094892  movups  xmm0, [rbp+510h+var_590]
0x140094896  movsd   [rbp+510h+var_240], xmm0
0x14009489e  psrldq  xmm0, 8
0x1400948a3  movq    [rbp+510h+var_238], xmm0
0x1400948ab  lea     r8, [rbp+510h+var_400]
0x1400948b2  lea     rcx, [rbp+510h+var_230]
0x1400948b9  call    ??$ToConfigurationXml@AEAUGpuPartition@Gpup@Devices@Config@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAUGpuPartition@Gpup@Devices@Config@@W4MarshalFlags@0@@Z; Marshal::ToConfigurationXml<Config::Devices::Gpup::GpuPartition &,>(bool,Config::Devices::Gpup::GpuPartition &,Marshal::MarshalFlags)
0x1400948be  nop
0x1400948bf  xor     esi, esi
0x1400948c1  mov     [rbp+510h+var_4A8], rsi
0x1400948c5  lea     r8, CLSID_GpupVdev
0x1400948cc  mov     rdx, rdi
0x1400948cf  lea     rcx, [rbp+510h+var_4A8]
0x1400948d3  call    ??$MakeOrThrow@VVmHandleBroker@@AEAU_GUID@@AEBU2@@wil@@YA?AV?$ComPtr@VVmHandleBroker@@@WRL@Microsoft@@AEAU_GUID@@AEBU4@@Z; wil::MakeOrThrow<VmHandleBroker,_GUID &,_GUID const &>(_GUID &,_GUID const &)
0x1400948d8  nop
0x1400948d9  lea     rax, [rsp+610h+var_5D0+8]
0x1400948de  mov     qword ptr [rsp+610h+var_5C0+8], rax
0x1400948e3  mov     qword ptr [rsp+610h+var_5D0+8], rbx
0x1400948e8  mov     qword ptr [rsp+610h+var_5D0], 0FFFFFFFFFFFFFFFFh
0x1400948f1  lea     rdx, szPassword
0x1400948f8  lea     rcx, [rbp+510h+var_590]
0x1400948fc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140094901  nop
0x140094902  lea     r9, [rsp+610h+var_5D0+8]
0x140094907  xor     r8d, r8d
0x14009490a  lea     rdx, [rbp+510h+var_590]
0x14009490e  mov     rcx, [rbp+510h+var_4A8]
0x140094912  call    ?PutHandle@VmHandleBrokerUtils@@YAXPEAUIVmHandleBroker@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4__MIDL___MIDL_itf_ivmhandlebrokeritfs_0000_0000_0001@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; VmHandleBrokerUtils::PutHandle(IVmHandleBroker *,std::wstring const &,__MIDL___MIDL_itf_ivmhandlebrokeritfs_0000_0000_0001,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>)
0x140094917  nop
0x140094918  lea     rcx, [rbp+510h+var_590]; this
0x14009491c  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140094921  mov     rax, [rbp+510h+var_4A8]
0x140094925  mov     [rsp+610h+lpBytesReturned], rax
0x14009492a  mov     [rsp+610h+nOutBufferSize], 100h
0x140094932  lea     rax, [rbp+510h+var_230]
0x140094939  mov     [rsp+610h+lpOutBuffer], rax
0x14009493e  lea     r9, ?GpupDeviceName@@3QBGB; "Microsoft GPU Partition"
0x140094945  mov     r8, rdi
0x140094948  lea     rdx, CLSID_GpupVdev
0x14009494f  mov     rcx, [r14+58h]
  ... truncated ...
```
