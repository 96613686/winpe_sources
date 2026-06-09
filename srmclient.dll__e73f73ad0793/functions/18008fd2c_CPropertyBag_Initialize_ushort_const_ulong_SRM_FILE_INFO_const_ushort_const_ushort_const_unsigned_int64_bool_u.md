# CPropertyBag::Initialize(ushort const *,ulong,SRM_FILE_INFO const *,ushort const *,ushort const *,unsigned __int64,bool,ushort const *)

- ea: `0x18008fd2c`
- end: `0x18008ff75`
- name: `?Initialize@CPropertyBag@@AEAAXPEBGKPEBUSRM_FILE_INFO@@00_K_N0@Z`
- size: `585`
- prototype: `void __fastcall(CPropertyBag *this, const unsigned __int16 *, unsigned int, const struct SRM_FILE_INFO *, unsigned __int16 *, unsigned __int16 *, unsigned __int64, bool, unsigned __int16 *Src)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task`

## callers

- `0x18008e8c4`

## callees

- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x180010bc4`
- `0x18004e550`
- `0x18004e864`
- `0x180061be4`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180083a68`
- `0x18008fd2c`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18008fecb`
- `KERNEL32!CloseHandle` at `0x18008fecb`
- `KERNEL32!GetCurrentThread` at `0x18008fed8`
- `KERNEL32!GetCurrentThread` at `0x18008fed8`
- `ADVAPI32!OpenThreadToken` at `0x18008fef0`
- `ADVAPI32!OpenThreadToken` at `0x18008fef0`

## string_xrefs

- `0x18008fd8c`: `base\fs\fsrm\service\pipeline\propertybag.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CPropertyBag::Initialize(
        CPropertyBag *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const struct SRM_FILE_INFO *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int64 a7,
        bool a8,
        unsigned __int16 *Src)
{
  CPropertyBagFields *v13; // r13
  __int64 v14; // r8
  CPropertyBag *v15; // rbx
  char v16; // al
  __int64 v17; // rdx
  HANDLE CurrentThread; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  int LastFailureAsHRESULT; // eax
  char Hr; // al
  unsigned __int16 *v23; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v24; // [rsp+28h] [rbp-D8h]
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  CPropertyBag *v26; // [rsp+58h] [rbp-A8h]
  _QWORD *v27; // [rsp+60h] [rbp-A0h]
  _QWORD v28[3]; // [rsp+68h] [rbp-98h] BYREF
  int v29; // [rsp+80h] [rbp-80h]
  int v30; // [rsp+84h] [rbp-7Ch]
  int v31; // [rsp+88h] [rbp-78h]
  _BYTE v32[96]; // [rsp+90h] [rbp-70h] BYREF
  int v33; // [rsp+F0h] [rbp-10h]
  void **v34; // [rsp+100h] [rbp+0h] BYREF
  int v35; // [rsp+108h] [rbp+8h]

  v26 = this;
  v27 = v28;
  v28[0] = L"base\\fs\\fsrm\\service\\pipeline\\propertybag.cpp";
  v28[1] = L"CPropertyBag::Initialize";
  v28[2] = L"PROPBAGC";
  v29 = 150;
  v30 = 22;
  v31 = 255;
  v33 = 0x1000000;
  memset_0(v32, 0, sizeof(v32));
  CSrmFunctionTracer::CSrmFunctionTracer(&v34, v28, 0);
  v13 = (CPropertyBag *)((char *)this + 88);
  CPropertyBagFields::Initialize(v13, a2, a3, a4, a5, a6, a7);
  if ( Src && *Src )
  {
    v14 = -1;
    do
      ++v14;
    while ( Src[v14] );
    v15 = v26;
    std::wstring::assign((char *)v26 + 1144, Src);
  }
  else
  {
    v15 = v26;
  }
  LODWORD(v24) = 0;
  LODWORD(v23) = 1;
  CPropertyBagFieldsContextual::SetContext(v13, 0, 0, 0, v23, v24, 0, 0, 0);
  if ( a8 )
  {
    v16 = (*(__int64 (__fastcall **)(CPropertyBagFields *, __int64))(*(_QWORD *)v13 + 72LL))(v13, 0x20000);
    CSrmImpersonationSession::CSrmImpersonationSession((CSrmImpersonationSession *)&v25, v17, v16 == 0);
    if ( v25 )
    {
      if ( *((_QWORD *)v15 + 68) != -1 )
        CloseHandle(*((HANDLE *)v15 + 68));
      *((_QWORD *)v15 + 68) = -1;
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 4u, 1, (PHANDLE)v15 + 68) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v20, v19);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v34, LastFailureAsHRESULT);
        Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v34);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v34, 0xBCu, Hr, 0);
      }
      v35 = 0;
    }
    CSrmImpersonationSession::RevertImpersonation((CSrmImpersonationSession *)&v25);
  }
  v34 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v34);
}

```

## disassembly

```asm
0x18008fd2c  mov     [rsp-8+arg_10], rbx
0x18008fd31  push    rbp
0x18008fd32  push    rsi
0x18008fd33  push    rdi
0x18008fd34  push    r12
0x18008fd36  push    r13
0x18008fd38  push    r14
0x18008fd3a  push    r15
0x18008fd3c  lea     rbp, [rsp-0C0h]
0x18008fd44  sub     rsp, 1C0h
0x18008fd4b  mov     rax, cs:__security_cookie
0x18008fd52  xor     rax, rsp
0x18008fd55  mov     [rbp+0F0h+var_40], rax
0x18008fd5c  mov     r15, r9
0x18008fd5f  mov     esi, r8d
0x18008fd62  mov     r14, rdx
0x18008fd65  mov     r13, rcx
0x18008fd68  mov     [rsp+1F0h+var_198], rcx
0x18008fd6d  mov     rdi, [rbp+0F0h+arg_20]
0x18008fd74  mov     rbx, [rbp+0F0h+arg_28]
0x18008fd7b  mov     r12, [rbp+0F0h+Src]
0x18008fd82  lea     rax, [rsp+1F0h+var_188]
0x18008fd87  mov     [rsp+1F0h+var_190], rax
0x18008fd8c  lea     rax, aBaseFsFsrmServ_26; "base\\fs\\fsrm\\service\\pipeline\\prop"...
0x18008fd93  mov     [rsp+1F0h+var_188], rax
0x18008fd98  lea     rax, aCpropertybagIn_0; "CPropertyBag::Initialize"
0x18008fd9f  mov     [rsp+1F0h+var_180], rax
0x18008fda4  lea     rax, aPropbagc; "PROPBAGC"
0x18008fdab  mov     [rsp+1F0h+var_178], rax
0x18008fdb0  mov     [rbp+0F0h+var_170], 96h
0x18008fdb7  mov     [rbp+0F0h+var_16C], 16h
0x18008fdbe  mov     [rbp+0F0h+var_168], 0FFh
0x18008fdc5  mov     [rbp+0F0h+var_100], 1000000h
0x18008fdcc  xor     edx, edx; Val
0x18008fdce  lea     r8d, [rdx+60h]; Size
0x18008fdd2  lea     rcx, [rbp+0F0h+var_160]; void *
0x18008fdd6  call    memset_0
0x18008fddb  nop
0x18008fddc  xor     r8d, r8d
0x18008fddf  lea     rdx, [rsp+1F0h+var_188]
0x18008fde4  lea     rcx, [rbp+0F0h+var_F0]
0x18008fde8  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18008fded  nop
0x18008fdee  add     r13, 58h ; 'X'
0x18008fdf2  mov     rax, [rbp+0F0h+arg_30]
0x18008fdf9  mov     [rsp+1F0h+var_1C0], rax; unsigned __int64
0x18008fdfe  mov     [rsp+1F0h+var_1C8], rbx; unsigned __int16 *
0x18008fe03  mov     [rsp+1F0h+var_1D0], rdi; unsigned __int16 *
0x18008fe08  mov     r9, r15; struct SRM_FILE_INFO *
0x18008fe0b  mov     r8d, esi; unsigned int
0x18008fe0e  mov     rdx, r14; unsigned __int16 *
0x18008fe11  mov     rcx, r13; this
0x18008fe14  call    ?Initialize@CPropertyBagFields@@QEAAXPEBGKPEBUSRM_FILE_INFO@@00_K@Z; CPropertyBagFields::Initialize(ushort const *,ulong,SRM_FILE_INFO const *,ushort const *,ushort const *,unsigned __int64)
0x18008fe19  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008fe1d  xor     edi, edi
0x18008fe1f  test    r12, r12
0x18008fe22  jz      short loc_18008FE4E
0x18008fe24  cmp     [r12], di
0x18008fe29  jz      short loc_18008FE4E
0x18008fe2b  mov     r8, rsi
0x18008fe2e  inc     r8
0x18008fe31  cmp     [r12+r8*2], di
0x18008fe36  jnz     short loc_18008FE2E
0x18008fe38  mov     rbx, [rsp+1F0h+var_198]
0x18008fe3d  lea     rcx, [rbx+478h]; void *
0x18008fe44  mov     rdx, r12; Src
0x18008fe47  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18008fe4c  jmp     short loc_18008FE53
0x18008fe4e  mov     rbx, [rsp+1F0h+var_198]
0x18008fe53  mov     [rsp+1F0h+var_1B0], edi
0x18008fe57  mov     [rsp+1F0h+var_1B8], rdi
0x18008fe5c  mov     [rsp+1F0h+var_1C0], rdi
0x18008fe61  mov     dword ptr [rsp+1F0h+var_1C8], edi
0x18008fe65  mov     r14d, 1
0x18008fe6b  mov     dword ptr [rsp+1F0h+var_1D0], r14d
0x18008fe70  xor     r9d, r9d
0x18008fe73  xor     r8d, r8d
0x18008fe76  xor     edx, edx
0x18008fe78  mov     rcx, r13
0x18008fe7b  call    ?SetContext@CPropertyBagFieldsContextual@@QEAAXPEBVCVolumeStructure@@K_KW4_FsrmPipelinePhase@@W4_FsrmStorageModuleTypeInternal@@PEBG4K@Z; CPropertyBagFieldsContextual::SetContext(CVolumeStructure const *,ulong,unsigned __int64,_FsrmPipelinePhase,_FsrmStorageModuleTypeInternal,ushort const *,ushort const *,ulong)
0x18008fe80  cmp     [rbp+0F0h+arg_38], dil
0x18008fe87  jz      short loc_18008FF08
0x18008fe89  mov     rax, [r13+0]
0x18008fe8d  mov     edx, 20000h
0x18008fe92  mov     rcx, r13
0x18008fe95  mov     rax, [rax+48h]
0x18008fe99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fe9e  test    al, al
0x18008fea0  setz    r8b; bool
0x18008fea4  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18008fea9  call    ??0CSrmImpersonationSession@@QEAA@_N0@Z; CSrmImpersonationSession::CSrmImpersonationSession(bool,bool)
0x18008feae  nop
0x18008feaf  cmp     [rsp+1F0h+var_1A0], edi
0x18008feb3  jz      short loc_18008FEFD
0x18008feb5  mov     eax, [rbp+0F0h+var_E8]
0x18008feb8  mov     [rbp+0F0h+var_E8], eax
0x18008febb  cmp     [rbx+220h], rsi
0x18008fec2  jz      short loc_18008FED1
0x18008fec4  mov     rcx, [rbx+220h]; hObject
0x18008fecb  call    cs:__imp_CloseHandle
0x18008fed1  mov     [rbx+220h], rsi
0x18008fed8  call    cs:__imp_GetCurrentThread
0x18008fede  lea     r9, [rbx+220h]; TokenHandle
0x18008fee5  mov     r8d, r14d; OpenAsSelf
0x18008fee8  mov     edx, 4; DesiredAccess
0x18008feed  mov     rcx, rax; ThreadHandle
0x18008fef0  call    cs:__imp_OpenThreadToken
0x18008fef6  test    eax, eax
0x18008fef8  jz      short loc_18008FF46
0x18008fefa  mov     [rbp+0F0h+var_E8], edi
0x18008fefd  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18008ff02  call    ?RevertImpersonation@CSrmImpersonationSession@@QEAAJXZ; CSrmImpersonationSession::RevertImpersonation(void)
0x18008ff07  nop
0x18008ff08  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18008ff0f  mov     [rbp+0F0h+var_F0], rax
0x18008ff13  lea     rcx, [rbp+0F0h+var_F0]; this
0x18008ff17  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18008ff1c  mov     rcx, [rbp+0F0h+var_40]
0x18008ff23  xor     rcx, rsp; StackCookie
0x18008ff26  call    __security_check_cookie
0x18008ff2b  mov     rbx, [rsp+1F0h+arg_10]
0x18008ff33  add     rsp, 1C0h
0x18008ff3a  pop     r15
0x18008ff3c  pop     r14
0x18008ff3e  pop     r13
0x18008ff40  pop     r12
0x18008ff42  pop     rdi
0x18008ff43  pop     rsi
0x18008ff44  pop     rbp
0x18008ff45  retn
0x18008ff46  call    GetLastFailureAsHRESULT
0x18008ff4b  nop
0x18008ff4c  mov     edx, eax; int
0x18008ff4e  lea     rcx, [rbp+0F0h+var_F0]; this
0x18008ff52  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18008ff57  lea     rcx, [rbp+0F0h+var_F0]; this
0x18008ff5b  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18008ff60  mov     r8d, eax; char
0x18008ff63  xor     r9d, r9d; unsigned __int16 *
0x18008ff66  mov     edx, 0BCh; unsigned int
0x18008ff6b  lea     rcx, [rbp+0F0h+var_F0]; this
0x18008ff6f  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
