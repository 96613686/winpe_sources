# StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)

- ea: `0x180036e98`
- end: `0x180037222`
- name: `?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `906`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18001b388`

## callees

- `0x1800164ec`
- `0x180017e48`
- `0x180018a54`
- `0x18001cc38`
- `0x180036e98`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt64` at `0x180037038`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt64` at `0x180037038`

## string_xrefs

- `0x180037049`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180036efc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1800371f8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180037087`: `InstalledLocation`
- `0x1800370d5`: `MutableLink`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int Field; // r14d
  __int64 v9; // rdx
  int Field_UInt64; // eax
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 *v15; // [rsp+28h] [rbp-20h] BYREF
  char v16; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  if ( a3 && (a3 & 1) == 0 )
    goto LABEL_7;
  v15 = 0;
  v14 = a2 + 8;
  v16 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageFullName", &v15);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v14);
  if ( Field < 0 )
  {
    v9 = 2091;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)Field,
      v14);
    return (unsigned int)Field;
  }
  if ( a3 )
  {
LABEL_7:
    if ( (a3 & 2) == 0 )
      goto LABEL_11;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageFamily", (unsigned int *)(a2 + 16));
  if ( Field < 0 )
  {
    v9 = 2095;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_11:
    if ( (a3 & 4) == 0 )
      goto LABEL_15;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageType", (unsigned int *)(a2 + 24));
  if ( Field < 0 )
  {
    v9 = 2099;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_15:
    if ( (a3 & 8) == 0 )
      goto LABEL_19;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Flags", (unsigned int *)(a2 + 28));
  if ( Field < 0 )
  {
    v9 = 2103;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_19:
    if ( (a3 & 0x10) == 0 )
      goto LABEL_23;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Flags2", (unsigned int *)(a2 + 32));
  if ( Field < 0 )
  {
    v9 = 2107;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_23:
    if ( (a3 & 0x20) == 0 )
      goto LABEL_27;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageOrigin", (unsigned int *)(a2 + 36));
  if ( Field < 0 )
  {
    v9 = 2111;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_27:
    if ( (a3 & 0x40) == 0 )
      goto LABEL_31;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Volume", (unsigned int *)(a2 + 40));
  if ( Field < 0 )
  {
    v9 = 2115;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_31:
    if ( (a3 & 0x80u) == 0LL )
      goto LABEL_35;
  }
  Field_UInt64 = SRCacheContext_GetField_UInt64(*(_QWORD *)a1, L"OSMaxVersionTested", a2 + 48);
  Field = Field_UInt64;
  if ( Field_UInt64 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x230,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt64,
      v14);
    v9 = 2119;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_35:
    if ( (a3 & 0x100) == 0 )
      goto LABEL_39;
  }
  v15 = 0;
  v14 = a2 + 56;
  v16 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"InstalledLocation", &v15);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v14);
  if ( Field < 0 )
  {
    v9 = 2123;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_39:
    if ( (a3 & 0x200) == 0 )
      goto LABEL_43;
  }
  v15 = 0;
  v14 = a2 + 64;
  v16 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"MutableLink", &v15);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v14);
  if ( Field < 0 )
  {
    v9 = 2127;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_43:
    if ( (a3 & 0x400) == 0 )
      goto LABEL_47;
  }
  v15 = 0;
  v14 = a2 + 72;
  v16 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"MutableLocation", &v15);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v14);
  if ( Field < 0 )
  {
    v9 = 2131;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_47:
    if ( (a3 & 0x800) == 0 )
      goto LABEL_51;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"TargetDeviceFamilyName", (unsigned int *)(a2 + 80));
  if ( Field < 0 )
  {
    v9 = 2135;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_51:
    if ( (a3 & 0x1000) == 0 )
      goto LABEL_55;
  }
  v15 = 0;
  v14 = a2 + 88;
  v16 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"DisplayName", &v15);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v14);
  if ( Field < 0 )
  {
    v9 = 2139;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_55:
    if ( (a3 & 0x2000) == 0 )
      goto LABEL_58;
  }
  v12 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"SourceBundle", (unsigned int *)(a2 + 96));
  v13 = v12;
  if ( v12 >= 0 )
  {
LABEL_58:
    *(_QWORD *)a2 = a4;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v12,
      v14);
    return v13;
  }
}

```

## disassembly

```asm
0x180036e98  push    rbp
0x180036e9a  push    rbx
0x180036e9b  push    rsi
0x180036e9c  push    rdi
0x180036e9d  push    r14
0x180036e9f  push    r15
0x180036ea1  mov     rbp, rsp
0x180036ea4  sub     rsp, 48h
0x180036ea8  mov     r15, r9
0x180036eab  mov     rbx, r8
0x180036eae  mov     rdi, rdx
0x180036eb1  mov     rsi, rcx
0x180036eb4  test    r8, r8
0x180036eb7  jz      short loc_180036EBE
0x180036eb9  test    bl, 1
0x180036ebc  jz      short loc_180036F18
0x180036ebe  lea     rax, [rdx+8]
0x180036ec2  mov     [rbp+var_20], 0
0x180036eca  lea     rdx, aPackagefullnam_0; "PackageFullName"
0x180036ed1  mov     [rbp+var_28], rax
0x180036ed5  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180036ed9  mov     [rbp+var_18], 1
0x180036edd  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180036ee2  lea     rcx, [rbp+var_28]
0x180036ee6  mov     r14d, eax
0x180036ee9  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180036eee  test    r14d, r14d
0x180036ef1  jns     short loc_180036F13
0x180036ef3  mov     edx, 82Bh; void *
0x180036ef8  mov     rcx, [rbp+30h]; this
0x180036efc  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180036f03  mov     r9d, r14d; char *
0x180036f06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036f0b  mov     eax, r14d
0x180036f0e  jmp     loc_180037215
0x180036f13  test    rbx, rbx
0x180036f16  jz      short loc_180036F1D
0x180036f18  test    bl, 2
0x180036f1b  jz      short loc_180036F43
0x180036f1d  lea     r8, [rdi+10h]; unsigned int *
0x180036f21  mov     rcx, rsi; this
0x180036f24  lea     rdx, aPackagefamily; "PackageFamily"
0x180036f2b  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180036f30  mov     r14d, eax
0x180036f33  test    eax, eax
0x180036f35  jns     short loc_180036F3E
0x180036f37  mov     edx, 82Fh
0x180036f3c  jmp     short loc_180036EF8
0x180036f3e  test    rbx, rbx
0x180036f41  jz      short loc_180036F48
0x180036f43  test    bl, 4
0x180036f46  jz      short loc_180036F6E
0x180036f48  lea     r8, [rdi+18h]; unsigned int *
0x180036f4c  mov     rcx, rsi; this
0x180036f4f  lea     rdx, aPackagetype; "PackageType"
0x180036f56  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180036f5b  mov     r14d, eax
0x180036f5e  test    eax, eax
0x180036f60  jns     short loc_180036F69
0x180036f62  mov     edx, 833h
0x180036f67  jmp     short loc_180036EF8
0x180036f69  test    rbx, rbx
0x180036f6c  jz      short loc_180036F73
0x180036f6e  test    bl, 8
0x180036f71  jz      short loc_180036F9C
0x180036f73  lea     r8, [rdi+1Ch]; unsigned int *
0x180036f77  mov     rcx, rsi; this
0x180036f7a  lea     rdx, aFlags; "Flags"
0x180036f81  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180036f86  mov     r14d, eax
0x180036f89  test    eax, eax
0x180036f8b  jns     short loc_180036F97
0x180036f8d  mov     edx, 837h
0x180036f92  jmp     loc_180036EF8
0x180036f97  test    rbx, rbx
0x180036f9a  jz      short loc_180036FA1
0x180036f9c  test    bl, 10h
0x180036f9f  jz      short loc_180036FCA
0x180036fa1  lea     r8, [rdi+20h]; unsigned int *
0x180036fa5  mov     rcx, rsi; this
0x180036fa8  lea     rdx, aFlags2; "Flags2"
0x180036faf  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180036fb4  mov     r14d, eax
0x180036fb7  test    eax, eax
0x180036fb9  jns     short loc_180036FC5
0x180036fbb  mov     edx, 83Bh
0x180036fc0  jmp     loc_180036EF8
0x180036fc5  test    rbx, rbx
0x180036fc8  jz      short loc_180036FCF
0x180036fca  test    bl, 20h
0x180036fcd  jz      short loc_180036FF8
0x180036fcf  lea     r8, [rdi+24h]; unsigned int *
0x180036fd3  mov     rcx, rsi; this
0x180036fd6  lea     rdx, aPackageorigin; "PackageOrigin"
0x180036fdd  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180036fe2  mov     r14d, eax
0x180036fe5  test    eax, eax
0x180036fe7  jns     short loc_180036FF3
0x180036fe9  mov     edx, 83Fh
0x180036fee  jmp     loc_180036EF8
0x180036ff3  test    rbx, rbx
0x180036ff6  jz      short loc_180036FFD
0x180036ff8  test    bl, 40h
0x180036ffb  jz      short loc_180037026
0x180036ffd  lea     r8, [rdi+28h]; unsigned int *
0x180037001  mov     rcx, rsi; this
0x180037004  lea     rdx, aVolume; "Volume"
0x18003700b  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180037010  mov     r14d, eax
0x180037013  test    eax, eax
0x180037015  jns     short loc_180037021
0x180037017  mov     edx, 843h
0x18003701c  jmp     loc_180036EF8
0x180037021  test    rbx, rbx
0x180037024  jz      short loc_18003702A
0x180037026  test    bl, bl
0x180037028  jns     short loc_18003706C
0x18003702a  mov     rcx, [rsi]
0x18003702d  lea     r8, [rdi+30h]
0x180037031  lea     rdx, aOsmaxversionte; "OSMaxVersionTested"
0x180037038  call    cs:__imp_SRCacheContext_GetField_UInt64
0x18003703e  mov     r14d, eax
0x180037041  test    eax, eax
0x180037043  jns     short loc_180037067
0x180037045  mov     rcx, [rbp+30h]; this
0x180037049  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180037050  mov     r9d, eax; char *
0x180037053  mov     edx, 230h; void *
0x180037058  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003705d  mov     edx, 847h
0x180037062  jmp     loc_180036EF8
0x180037067  test    rbx, rbx
0x18003706a  jz      short loc_180037073
0x18003706c  bt      rbx, 8
0x180037071  jnb     short loc_1800370BA
0x180037073  lea     rax, [rdi+38h]
0x180037077  mov     [rbp+var_20], 0
0x18003707f  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180037083  mov     [rbp+var_28], rax
0x180037087  lea     rdx, aInstalledlocat; "InstalledLocation"
0x18003708e  mov     [rbp+var_18], 1
0x180037092  mov     rcx, rsi; this
0x180037095  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18003709a  lea     rcx, [rbp+var_28]
0x18003709e  mov     r14d, eax
0x1800370a1  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800370a6  test    r14d, r14d
0x1800370a9  jns     short loc_1800370B5
0x1800370ab  mov     edx, 84Bh
0x1800370b0  jmp     loc_180036EF8
0x1800370b5  test    rbx, rbx
0x1800370b8  jz      short loc_1800370C1
0x1800370ba  bt      rbx, 9
0x1800370bf  jnb     short loc_180037108
0x1800370c1  lea     rax, [rdi+40h]
0x1800370c5  mov     [rbp+var_20], 0
0x1800370cd  lea     r8, [rbp+var_20]; unsigned __int16 **
0x1800370d1  mov     [rbp+var_28], rax
0x1800370d5  lea     rdx, aMutablelink; "MutableLink"
0x1800370dc  mov     [rbp+var_18], 1
0x1800370e0  mov     rcx, rsi; this
0x1800370e3  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800370e8  lea     rcx, [rbp+var_28]
0x1800370ec  mov     r14d, eax
0x1800370ef  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800370f4  test    r14d, r14d
0x1800370f7  jns     short loc_180037103
0x1800370f9  mov     edx, 84Fh
0x1800370fe  jmp     loc_180036EF8
0x180037103  test    rbx, rbx
0x180037106  jz      short loc_18003710F
0x180037108  bt      rbx, 0Ah
0x18003710d  jnb     short loc_180037156
0x18003710f  lea     rax, [rdi+48h]
0x180037113  mov     [rbp+var_20], 0
0x18003711b  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18003711f  mov     [rbp+var_28], rax
0x180037123  lea     rdx, aMutablelocatio; "MutableLocation"
0x18003712a  mov     [rbp+var_18], 1
0x18003712e  mov     rcx, rsi; this
0x180037131  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180037136  lea     rcx, [rbp+var_28]
0x18003713a  mov     r14d, eax
0x18003713d  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180037142  test    r14d, r14d
0x180037145  jns     short loc_180037151
0x180037147  mov     edx, 853h
0x18003714c  jmp     loc_180036EF8
0x180037151  test    rbx, rbx
0x180037154  jz      short loc_18003715D
0x180037156  bt      rbx, 0Bh
0x18003715b  jnb     short loc_180037186
0x18003715d  lea     r8, [rdi+50h]; unsigned int *
0x180037161  mov     rcx, rsi; this
0x180037164  lea     rdx, aTargetdevicefa; "TargetDeviceFamilyName"
0x18003716b  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180037170  mov     r14d, eax
0x180037173  test    eax, eax
0x180037175  jns     short loc_180037181
0x180037177  mov     edx, 857h
0x18003717c  jmp     loc_180036EF8
0x180037181  test    rbx, rbx
0x180037184  jz      short loc_18003718D
0x180037186  bt      rbx, 0Ch
0x18003718b  jnb     short loc_1800371D4
0x18003718d  lea     rax, [rdi+58h]
0x180037191  mov     [rbp+var_20], 0
0x180037199  lea     r8, [rbp+var_20]; unsigned __int16 **
0x18003719d  mov     [rbp+var_28], rax
0x1800371a1  lea     rdx, aDisplayname; "DisplayName"
0x1800371a8  mov     [rbp+var_18], 1
0x1800371ac  mov     rcx, rsi; this
0x1800371af  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800371b4  lea     rcx, [rbp+var_28]
0x1800371b8  mov     r14d, eax
0x1800371bb  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800371c0  test    r14d, r14d
0x1800371c3  jns     short loc_1800371CF
0x1800371c5  mov     edx, 85Bh
0x1800371ca  jmp     loc_180036EF8
0x1800371cf  test    rbx, rbx
0x1800371d2  jz      short loc_1800371DB
0x1800371d4  bt      rbx, 0Dh
0x1800371d9  jnb     short loc_180037210
0x1800371db  lea     r8, [rdi+60h]; unsigned int *
0x1800371df  mov     rcx, rsi; this
0x1800371e2  lea     rdx, aSourcebundle; "SourceBundle"
0x1800371e9  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x1800371ee  mov     ebx, eax
0x1800371f0  test    eax, eax
0x1800371f2  jns     short loc_180037210
0x1800371f4  mov     rcx, [rbp+30h]; this
0x1800371f8  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800371ff  mov     r9d, eax; char *
0x180037202  mov     edx, 85Fh; void *
0x180037207  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003720c  mov     eax, ebx
0x18003720e  jmp     short loc_180037215
0x180037210  mov     [rdi], r15
0x180037213  xor     eax, eax
0x180037215  add     rsp, 48h
0x180037219  pop     r15
0x18003721b  pop     r14
0x18003721d  pop     rdi
0x18003721e  pop     rsi
0x18003721f  pop     rbx
0x180037220  pop     rbp
0x180037221  retn
```
