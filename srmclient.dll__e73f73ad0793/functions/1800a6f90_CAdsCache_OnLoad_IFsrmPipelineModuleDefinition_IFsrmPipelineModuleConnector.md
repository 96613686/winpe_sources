# CAdsCache::OnLoad(IFsrmPipelineModuleDefinition *,IFsrmPipelineModuleConnector * *)

- ea: `0x1800a6f90`
- end: `0x1800a73cf`
- name: `?OnLoad@CAdsCache@@UEAAJPEAUIFsrmPipelineModuleDefinition@@PEAPEAUIFsrmPipelineModuleConnector@@@Z`
- size: `1087`
- prototype: `int(CAdsCache *__hidden this, struct IFsrmPipelineModuleDefinition *, struct IFsrmPipelineModuleConnector **)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18006fe68`
- `0x18006febc`
- `0x18007006c`
- `0x1800700b8`
- `0x180070380`
- `0x180071efc`
- `0x180073a80`
- `0x180073d04`
- `0x180075510`
- `0x180075eb8`
- `0x18007691c`
- `0x18008b790`
- `0x1800a5a94`
- `0x1800a686c`
- `0x1800a6f90`
- `0x1800a79fc`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## string_xrefs

- `0x1800a7359`: `COM Call %S failed [0x%08lx]`
- `0x1800a6fcd`: `base\fs\fsrm\service\moduleimpl\adscache.cpp`
- `0x1800a720b`: `base\fs\fsrm\service\moduleimpl\adscache.cpp`
- `0x1800a72a8`: `base\fs\fsrm\service\moduleimpl\adscache.cpp`
- `0x1800a7334`: `base\fs\fsrm\service\moduleimpl\adscache.cpp`
- `0x1800a739b`: `base\fs\fsrm\service\moduleimpl\adscache.cpp`
- `0x1800a7220`: `Module was already initialized.`
- `0x1800a6fdb`: `CAdsCache::OnLoad`
- `0x1800a71fd`: `CAdsCache::OnLoad`
- `0x1800a729a`: `CAdsCache::OnLoad`
- `0x1800a7326`: `CAdsCache::OnLoad`
- `0x1800a738d`: `CAdsCache::OnLoad`
- `0x1800a70c5`: `System\CurrentControlSet\Services\SrmSvc\Settings`
- `0x1800a70e6`: `SkipReadOnlyFiles`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CAdsCache::OnLoad(
        unsigned __int64 this,
        struct IFsrmPipelineModuleDefinition *a2,
        struct IFsrmPipelineModuleConnector **a3)
{
  CAdsCache *v6; // rcx
  bool v7; // r9
  int v8; // eax
  int v9; // eax
  volatile signed __int32 *v10; // rbx
  signed __int32 i; // eax
  unsigned int v12; // ebx
  __int64 v14; // rax
  int Hr; // eax
  char v16; // al
  struct CSrmDebugInfo *v17; // rax
  CSrmDebugInfo *v18; // rax
  unsigned int v19; // ebx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // [rsp+28h] [rbp-270h]
  unsigned int v23[2]; // [rsp+40h] [rbp-258h] BYREF
  __int64 v24; // [rsp+48h] [rbp-250h] BYREF
  LPVOID v25[3]; // [rsp+50h] [rbp-248h] BYREF
  int v26; // [rsp+68h] [rbp-230h] BYREF
  _BYTE *v27; // [rsp+70h] [rbp-228h]
  _com_error *v28; // [rsp+78h] [rbp-220h] BYREF
  const exception *v29; // [rsp+80h] [rbp-218h] BYREF
  _QWORD v30[3]; // [rsp+88h] [rbp-210h] BYREF
  int v31; // [rsp+A0h] [rbp-1F8h]
  int v32; // [rsp+A4h] [rbp-1F4h]
  int v33; // [rsp+A8h] [rbp-1F0h]
  _DWORD v34[26]; // [rsp+B0h] [rbp-1E8h] BYREF
  _BYTE v35[152]; // [rsp+118h] [rbp-180h] BYREF
  void **v36; // [rsp+1B0h] [rbp-E8h] BYREF
  int v37; // [rsp+1B8h] [rbp-E0h]
  unsigned int v38; // [rsp+1DCh] [rbp-BCh]

  *(_QWORD *)v23 = v30;
  v30[0] = L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp";
  v30[1] = L"CAdsCache::OnLoad";
  v30[2] = L"ADSCACHC";
  v31 = 84;
  v32 = 22;
  v33 = 255;
  v34[24] = 0x1000000;
  memset_0(v34, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v36, (const struct CSrmDebugInfo *)v30, 0);
  try
  {
    if ( *(_BYTE *)(this - 8 + 72) )
    {
      *(_QWORD *)v23 = v35;
      v14 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v35,
              (__int64)L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
              (__int64)L"ADSCACHC",
              (__int64)L"CAdsCache::OnLoad",
              91,
              22);
      CSrmFunctionTracer::Throw(&v36, v14, 2147767062LL, L"Module was already initialized.");
    }
    if ( !a2 || !a3 )
    {
      v27 = v35;
      v21 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v35,
              (__int64)L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
              (__int64)L"ADSCACHC",
              (__int64)L"CAdsCache::OnLoad",
              96,
              22);
      CSrmFunctionTracer::Throw(&v36, v21, 2147942487LL, L"Invalid arguments");
    }
    *a3 = 0;
    *(_QWORD *)(this + 80) = 0;
    *(_QWORD *)(this + 88) = 0;
    *(_QWORD *)(this + 96) = 0;
    *(_DWORD *)(this + 104) = 0;
    CAdsCache::ValidateModuleDefinition(v6, a2);
    CAdsCache::GetModuleDefinitionParameters((CAdsCache *)(this - 8), a2);
    *(_DWORD *)(this + 68) = FciGetAdsCacheSizeLimit();
    v25[2] = 0;
    v25[1] = 0;
    v25[0] = (LPVOID)257;
    v23[0] = 0;
    if ( !CSrmRegistryKey::Open(
            (CSrmRegistryKey *)v25,
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\SrmSvc\\Settings")
      || !CSrmRegistryKey::GetValue((CSrmRegistryKey *)v25, L"SkipReadOnlyFiles", v23, v7)
      || (v8 = 0, !v23[0]) )
    {
      v8 = 1;
    }
    *(_DWORD *)(this + 108) = v8;
    v24 = 0;
    v9 = ATL::CComObject<CFsrmPipelineModuleConnector>::CreateInstance(&v24);
    v37 = v9;
    if ( v9 < 0 )
    {
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v36, Hr);
      v16 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v36, 0x88u, v16, 0);
    }
    v37 = v9;
    v10 = (volatile signed __int32 *)v24;
    for ( i = *(_DWORD *)(v24 + 8);
          i != 0x7FFFFFFF && i != _InterlockedCompareExchange(v10 + 2, i + 1, i);
          i = *((_DWORD *)v10 + 2) )
    {
      ;
    }
    v37 = (*(__int64 (__fastcall **)(volatile signed __int32 *, struct IFsrmPipelineModuleDefinition *, unsigned __int64))(*(_QWORD *)v10 + 88LL))(
            v10,
            a2,
            this & -(__int64)(this != 8));
    if ( v37 < 0 )
    {
      *(_QWORD *)v23 = v35;
      v17 = (struct CSrmDebugInfo *)CSrmDebugInfo::CSrmDebugInfo(
                                      (__int64)v30,
                                      (__int64)L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
                                      (__int64)L"ADSCACHC",
                                      (__int64)L"CAdsCache::OnLoad",
                                      140,
                                      0);
      v18 = CSrmDebugInfo::operator<<(v17, (CSrmDebugInfo *)v35, L"IFsrmPipelineModuleConnector::Bind");
      CSrmFunctionTracer::LogError((__int64)&v36, 0x8004302C, (__int64)v18, 1u);
      CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v30);
      v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
      v27 = v35;
      v20 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v35,
              (__int64)L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
              (__int64)L"ADSCACHC",
              (__int64)L"CAdsCache::OnLoad",
              140,
              17);
      LODWORD(v22) = v19;
      CSrmFunctionTracer::Throw(
        &v36,
        v20,
        v19,
        L"COM Call %S failed [0x%08lx]",
        "spConnector->Bind(pDefinition, this)",
        v22);
    }
    v24 = 0;
    *a3 = (struct IFsrmPipelineModuleConnector *)v10;
    *(_BYTE *)(this + 64) = 1;
    CSrmRegistryKey::~CSrmRegistryKey(v25);
  }
  catch ( long v26 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v36,
      v26,
      L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
      L"ADSCACHC",
      L"CAdsCache::OnLoad",
      0x92u,
      v38);
  }
  catch ( _com_error *v28 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v36,
      v28,
      L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
      L"ADSCACHC",
      L"CAdsCache::OnLoad",
      0x92u,
      v38);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v36,
      L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
      L"ADSCACHC",
      L"CAdsCache::OnLoad",
      0x92u,
      v38);
  }
  catch ( const exception *v29 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v36,
      v29,
      L"base\\fs\\fsrm\\service\\moduleimpl\\adscache.cpp",
      L"ADSCACHC",
      L"CAdsCache::OnLoad",
      0x92u,
      v38);
  }
  v12 = v37;
  v36 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v36);
  return v12;
}

```

## disassembly

```asm
0x1800a6f90  mov     r11, rsp
0x1800a6f93  mov     [r11+20h], rbx
0x1800a6f97  push    rsi
0x1800a6f98  push    rdi
0x1800a6f99  push    r12
0x1800a6f9b  push    r14
0x1800a6f9d  push    r15
0x1800a6f9f  sub     rsp, 270h
0x1800a6fa6  mov     rax, cs:__security_cookie
0x1800a6fad  xor     rax, rsp
0x1800a6fb0  mov     [rsp+298h+var_38], rax
0x1800a6fb8  mov     r15, r8
0x1800a6fbb  mov     r14, rdx
0x1800a6fbe  mov     rdi, rcx
0x1800a6fc1  lea     rax, [r11-210h]
0x1800a6fc8  mov     qword ptr [rsp+298h+var_258], rax
0x1800a6fcd  lea     rax, aBaseFsFsrmServ_16; "base\\fs\\fsrm\\service\\moduleimpl\\ad"...
0x1800a6fd4  mov     [r11-210h], rax
0x1800a6fdb  lea     rax, aCadscacheOnloa; "CAdsCache::OnLoad"
0x1800a6fe2  mov     [r11-208h], rax
0x1800a6fe9  lea     rax, aAdscachc; "ADSCACHC"
0x1800a6ff0  mov     [r11-200h], rax
0x1800a6ff7  mov     [rsp+298h+var_1F8], 54h ; 'T'
0x1800a7002  mov     ebx, 16h
0x1800a7007  mov     [rsp+298h+var_1F4], ebx
0x1800a700e  mov     [rsp+298h+var_1F0], 0FFh
0x1800a7019  xor     r12d, r12d
0x1800a701c  mov     [rsp+298h+var_188], 1000000h
0x1800a7027  xor     edx, edx; Val
0x1800a7029  lea     r8d, [rbx+4Ah]; Size
0x1800a702d  lea     rcx, [r11-1E8h]; void *
0x1800a7034  call    memset_0
0x1800a7039  nop
0x1800a703a  xor     r8d, r8d
0x1800a703d  lea     rdx, [rsp+298h+var_210]
0x1800a7045  lea     rcx, [rsp+298h+var_E8]
0x1800a704d  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800a7052  nop
0x1800a7053  lea     rsi, [rdi-8]
0x1800a7057  cmp     [rsi+48h], r12b
0x1800a705b  jnz     loc_1800A71E4
0x1800a7061  test    r14, r14
0x1800a7064  jz      loc_1800A7374
0x1800a706a  test    r15, r15
0x1800a706d  jz      loc_1800A7374
0x1800a7073  mov     [r15], r12
0x1800a7076  mov     [rdi+50h], r12
0x1800a707a  mov     [rdi+58h], r12
0x1800a707e  mov     [rdi+60h], r12
0x1800a7082  mov     [rdi+68h], r12d
0x1800a7086  mov     rdx, r14; struct IFsrmPipelineModuleDefinition *
0x1800a7089  call    ?ValidateModuleDefinition@CAdsCache@@AEAAXPEAUIFsrmPipelineModuleDefinition@@@Z; CAdsCache::ValidateModuleDefinition(IFsrmPipelineModuleDefinition *)
0x1800a708e  mov     rdx, r14; struct IFsrmPipelineModuleDefinition *
0x1800a7091  mov     rcx, rsi; this
0x1800a7094  call    ?GetModuleDefinitionParameters@CAdsCache@@AEAAXPEAUIFsrmPipelineModuleDefinition@@@Z; CAdsCache::GetModuleDefinitionParameters(IFsrmPipelineModuleDefinition *)
0x1800a7099  call    FciGetAdsCacheSizeLimit
0x1800a709e  mov     [rdi+44h], eax
0x1800a70a1  mov     [rsp+298h+var_238], r12
0x1800a70a6  mov     [rsp+298h+var_240], r12
0x1800a70ab  mov     [rsp+298h+var_244], r12d
0x1800a70b0  mov     [rsp+298h+var_248], 1
0x1800a70b8  mov     [rsp+298h+var_248], 101h
0x1800a70c0  mov     [rsp+298h+var_258], r12d
0x1800a70c5  lea     r8, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Sr"...
0x1800a70cc  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800a70d3  lea     rcx, [rsp+298h+var_248]; this
0x1800a70d8  call    ?Open@CSrmRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CSrmRegistryKey::Open(HKEY__ *,ushort const *,...)
0x1800a70dd  test    al, al
0x1800a70df  jz      short loc_1800A7105
0x1800a70e1  lea     r8, [rsp+298h+var_258]; unsigned int *
0x1800a70e6  lea     rdx, aSkipreadonlyfi_0; "SkipReadOnlyFiles"
0x1800a70ed  lea     rcx, [rsp+298h+var_248]; this
0x1800a70f2  call    ?GetValue@CSrmRegistryKey@@QEAA_NPEBGPEAK_N@Z; CSrmRegistryKey::GetValue(ushort const *,ulong *,bool)
0x1800a70f7  test    al, al
0x1800a70f9  jz      short loc_1800A7105
0x1800a70fb  cmp     [rsp+298h+var_258], r12d
0x1800a7100  mov     eax, r12d
0x1800a7103  jnz     short loc_1800A710A
0x1800a7105  mov     eax, 1
0x1800a710a  mov     [rdi+6Ch], eax
0x1800a710d  mov     [rsp+298h+var_250], r12
0x1800a7112  lea     rcx, [rsp+298h+var_250]
0x1800a7117  call    ?CreateInstance@?$CComObject@VCFsrmPipelineModuleConnector@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFsrmPipelineModuleConnector>::CreateInstance(ATL::CComObject<CFsrmPipelineModuleConnector> * *)
0x1800a711c  mov     [rsp+298h+var_E0], eax
0x1800a7123  test    eax, eax
0x1800a7125  js      loc_1800A723E
0x1800a712b  mov     [rsp+298h+var_E0], eax
0x1800a7132  mov     rbx, [rsp+298h+var_250]
0x1800a7137  mov     eax, [rbx+8]
0x1800a713a  cmp     eax, 7FFFFFFFh
0x1800a713f  jz      short loc_1800A7150
0x1800a7141  lea     ecx, [rax+1]
0x1800a7144  lock cmpxchg [rbx+8], ecx
0x1800a7149  jz      short loc_1800A7150
0x1800a714b  mov     eax, [rbx+8]
0x1800a714e  jmp     short loc_1800A713A
0x1800a7150  mov     rax, [rbx]
0x1800a7153  neg     rsi
0x1800a7156  sbb     r8, r8
0x1800a7159  and     r8, rdi
0x1800a715c  mov     rdx, r14
0x1800a715f  mov     rcx, rbx
0x1800a7162  mov     rax, [rax+58h]
0x1800a7166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a716b  mov     [rsp+298h+var_E0], eax
0x1800a7172  test    eax, eax
0x1800a7174  js      loc_1800A727F
0x1800a717a  mov     [rsp+298h+var_250], r12
0x1800a717f  mov     [r15], rbx
0x1800a7182  mov     byte ptr [rdi+40h], 1
0x1800a7186  lea     rcx, [rsp+298h+var_248]; this
0x1800a718b  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x1800a7190  nop
0x1800a7191  mov     ebx, [rsp+298h+var_E0]
0x1800a7198  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800a719f  mov     [rsp+298h+var_E8], rax
0x1800a71a7  lea     rcx, [rsp+298h+var_E8]; this
0x1800a71af  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800a71b4  mov     eax, ebx
0x1800a71b6  mov     rcx, [rsp+298h+var_38]
0x1800a71be  xor     rcx, rsp; StackCookie
0x1800a71c1  call    __security_check_cookie
0x1800a71c6  mov     rbx, [rsp+298h+arg_18]
0x1800a71ce  add     rsp, 270h
0x1800a71d5  pop     r15
0x1800a71d7  pop     r14
0x1800a71d9  pop     r12
0x1800a71db  pop     rdi
0x1800a71dc  pop     rsi
0x1800a71dd  retn
0x1800a71de  jmp     short loc_1800A7191
0x1800a71e0  jmp     short loc_1800A7191
0x1800a71e2  jmp     short loc_1800A7191
0x1800a71e4  lea     rax, [rsp+298h+var_180]
0x1800a71ec  mov     qword ptr [rsp+298h+var_258], rax
0x1800a71f1  mov     dword ptr [rsp+298h+var_270], ebx
0x1800a71f5  mov     dword ptr [rsp+298h+var_278], 5Bh ; '['
0x1800a71fd  lea     r9, aCadscacheOnloa; "CAdsCache::OnLoad"
0x1800a7204  lea     r8, aAdscachc; "ADSCACHC"
0x1800a720b  lea     rdx, aBaseFsFsrmServ_16; "base\\fs\\fsrm\\service\\moduleimpl\\ad"...
0x1800a7212  lea     rcx, [rsp+298h+var_180]
0x1800a721a  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800a721f  nop
0x1800a7220  lea     r9, aModuleWasAlrea; "Module was already initialized."
0x1800a7227  mov     r8d, 80045316h
0x1800a722d  mov     rdx, rax
0x1800a7230  lea     rcx, [rsp+298h+var_E8]
0x1800a7238  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x1800a723e  lea     rcx, [rsp+298h+var_E8]; this
0x1800a7246  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800a724b  mov     edx, eax; int
0x1800a724d  lea     rcx, [rsp+298h+var_E8]; this
0x1800a7255  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800a725a  lea     rcx, [rsp+298h+var_E8]; this
0x1800a7262  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800a7267  mov     r8d, eax; char
0x1800a726a  xor     r9d, r9d; unsigned __int16 *
0x1800a726d  mov     edx, 88h; unsigned int
0x1800a7272  lea     rcx, [rsp+298h+var_E8]; this
0x1800a727a  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800a727f  lea     rax, [rsp+298h+var_180]
0x1800a7287  mov     qword ptr [rsp+298h+var_258], rax
0x1800a728c  mov     dword ptr [rsp+298h+var_270], r12d
0x1800a7291  mov     edi, 8Ch
0x1800a7296  mov     dword ptr [rsp+298h+var_278], edi
0x1800a729a  lea     r9, aCadscacheOnloa; "CAdsCache::OnLoad"
0x1800a72a1  lea     r8, aAdscachc; "ADSCACHC"
0x1800a72a8  lea     rdx, aBaseFsFsrmServ_16; "base\\fs\\fsrm\\service\\moduleimpl\\ad"...
0x1800a72af  lea     rcx, [rsp+298h+var_210]
0x1800a72b7  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800a72bc  nop
0x1800a72bd  lea     r8, aIfsrmpipelinem_4; "IFsrmPipelineModuleConnector::Bind"
0x1800a72c4  lea     rdx, [rsp+298h+var_180]; this
0x1800a72cc  mov     rcx, rax; struct CSrmDebugInfo *
0x1800a72cf  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x1800a72d4  nop
0x1800a72d5  mov     r9d, 1
0x1800a72db  mov     r8, rax
0x1800a72de  mov     edx, 8004302Ch
0x1800a72e3  lea     rcx, [rsp+298h+var_E8]
0x1800a72eb  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x1800a72f0  nop
0x1800a72f1  lea     rcx, [rsp+298h+var_210]; this
0x1800a72f9  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x1800a72fe  lea     rcx, [rsp+298h+var_E8]; this
0x1800a7306  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800a730b  mov     ebx, eax
0x1800a730d  lea     rax, [rsp+298h+var_180]
0x1800a7315  mov     [rsp+298h+var_228], rax
0x1800a731a  mov     dword ptr [rsp+298h+var_270], 11h
0x1800a7322  mov     dword ptr [rsp+298h+var_278], edi
0x1800a7326  lea     r9, aCadscacheOnloa; "CAdsCache::OnLoad"
0x1800a732d  lea     r8, aAdscachc; "ADSCACHC"
0x1800a7334  lea     rdx, aBaseFsFsrmServ_16; "base\\fs\\fsrm\\service\\moduleimpl\\ad"...
0x1800a733b  lea     rcx, [rsp+298h+var_180]
0x1800a7343  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800a7348  nop
0x1800a7349  mov     dword ptr [rsp+298h+var_270], ebx
0x1800a734d  lea     rcx, aSpconnectorBin; "spConnector->Bind(pDefinition, this)"
0x1800a7354  mov     [rsp+298h+var_278], rcx
0x1800a7359  lea     r9, aComCallSFailed; "COM Call %S failed [0x%08lx]"
0x1800a7360  mov     r8d, ebx
0x1800a7363  mov     rdx, rax
0x1800a7366  lea     rcx, [rsp+298h+var_E8]
0x1800a736e  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x1800a7374  lea     rax, [rsp+298h+var_180]
0x1800a737c  mov     [rsp+298h+var_228], rax
0x1800a7381  mov     dword ptr [rsp+298h+var_270], ebx
0x1800a7385  mov     dword ptr [rsp+298h+var_278], 60h ; '`'
0x1800a738d  lea     r9, aCadscacheOnloa; "CAdsCache::OnLoad"
0x1800a7394  lea     r8, aAdscachc; "ADSCACHC"
0x1800a739b  lea     rdx, aBaseFsFsrmServ_16; "base\\fs\\fsrm\\service\\moduleimpl\\ad"...
0x1800a73a2  lea     rcx, [rsp+298h+var_180]
0x1800a73aa  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800a73af  nop
0x1800a73b0  lea     r9, aInvalidArgumen; "Invalid arguments"
0x1800a73b7  mov     r8d, 80070057h
0x1800a73bd  mov     rdx, rax
0x1800a73c0  lea     rcx, [rsp+298h+var_E8]
0x1800a73c8  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
