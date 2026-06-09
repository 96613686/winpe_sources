# MsaUserExtDefaultImpl::GetPlatformQualifier(ushort * *)

- ea: `0x18003f868`
- end: `0x18003f9bc`
- name: `?GetPlatformQualifier@MsaUserExtDefaultImpl@@YAJPEAPEAG@Z`
- size: `340`
- prototype: `__int64 __fastcall(MsaUserExtDefaultImpl *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003f9c4`

## callees

- `0x180004b2c`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x180034ea0`
- `0x18003f800`
- `0x18003f868`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18003f8f1`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18003f8f1`

## string_xrefs

- `0x18003f92a`: `hr = spCopy.Allocate(bytesNeeded)`
- `0x18003f969`: `hr = StringCbCopy(spCopy, bytesNeeded, identity)`
- `0x18003f902`: `PPICommunal`

## pseudocode

```c
__int64 __fastcall MsaUserExtDefaultImpl::GetPlatformQualifier(MsaUserExtDefaultImpl *this, unsigned __int16 **a2)
{
  unsigned __int64 v3; // rbx
  const unsigned __int16 *v4; // rdi
  int v5; // eax
  int v6; // eax
  __int64 v7; // r11
  unsigned int v8; // ebx
  char *v10; // [rsp+20h] [rbp-50h]
  unsigned __int16 *v11; // [rsp+30h] [rbp-40h] BYREF
  __int64 v12; // [rsp+38h] [rbp-38h]
  __int64 v13; // [rsp+40h] [rbp-30h]
  _QWORD v14[5]; // [rsp+48h] [rbp-28h] BYREF
  int v15; // [rsp+90h] [rbp+20h] BYREF
  int v16; // [rsp+98h] [rbp+28h] BYREF

  v15 = 0;
  v11 = 0;
  v13 = 0;
  v12 = 0;
  v14[0] = "MsaUserExtDefaultImpl::GetPlatformQualifier";
  v14[1] = &v15;
  v14[2] = 0;
  v14[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\msauserextimpl\\msauserextimpl.cpp",
    "MsaUserExtDefaultImpl::GetPlatformQualifier",
    (const char *)0xE0,
    0,
    (const unsigned __int16 *)v10);
  *(_QWORD *)this = 0;
  v16 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v16, 0);
  if ( v16 == 6 )
  {
    v3 = 24;
    v4 = L"PPICommunal";
  }
  else
  {
    v3 = 18;
    v4 = L"Windows9";
  }
  v5 = Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,DummyContext>::Allocate(&v11, v3);
  v15 = v5;
  if ( v5 >= 0 )
  {
    v6 = StringCbCopyW(v11, v3, v4);
    v15 = v6;
    if ( v6 >= 0 )
    {
      v11 = 0;
      v12 = 0;
      *(_QWORD *)this = v7;
    }
    else
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\msauserextimpl\\msauserextimpl.cpp",
        "MsaUserExtDefaultImpl::GetPlatformQualifier",
        0xF3u,
        v6,
        "hr = StringCbCopy(spCopy, bytesNeeded, identity)");
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\msauserextimpl\\msauserextimpl.cpp",
      "MsaUserExtDefaultImpl::GetPlatformQualifier",
      0xF2u,
      v5,
      "hr = spCopy.Allocate(bytesNeeded)");
  }
  v8 = v15;
  CTraceFuncW<long>::~CTraceFuncW<long>(v14);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(&v11);
  return v8;
}

```

## disassembly

```asm
0x18003f868  mov     [rsp-18h+arg_10], rbx
0x18003f86d  mov     [rsp-18h+arg_18], rsi
0x18003f872  push    rbp
0x18003f873  push    rdi
0x18003f874  push    r15
0x18003f876  mov     rbp, rsp
0x18003f879  sub     rsp, 70h
0x18003f87d  lea     r15, aMsauserextdefa; "MsaUserExtDefaultImpl::GetPlatformQuali"...
0x18003f884  mov     [rbp+arg_0], 0
0x18003f88b  mov     rsi, rcx
0x18003f88e  mov     [rbp+var_40], 0
0x18003f896  lea     rax, [rbp+arg_0]
0x18003f89a  mov     [rbp+var_30], 0
0x18003f8a2  mov     rdx, r15; char *
0x18003f8a5  mov     [rbp+var_38], 0
0x18003f8ad  xor     r9d, r9d; unsigned int
0x18003f8b0  mov     [rbp+var_28], r15
0x18003f8b4  mov     r8d, 0E0h; char *
0x18003f8ba  mov     [rbp+var_20], rax
0x18003f8be  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18003f8c5  mov     [rbp+var_18], 0
0x18003f8cd  mov     [rbp+var_10], 0
0x18003f8d5  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003f8da  xor     r8d, r8d
0x18003f8dd  mov     qword ptr [rsi], 0
0x18003f8e4  lea     rdx, [rbp+arg_8]
0x18003f8e8  mov     [rbp+arg_8], 0
0x18003f8ef  xor     ecx, ecx
0x18003f8f1  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18003f8f7  cmp     [rbp+arg_8], 6
0x18003f8fb  jnz     short loc_18003F90B
0x18003f8fd  mov     ebx, 18h
0x18003f902  lea     rdi, aPpicommunal; "PPICommunal"
0x18003f909  jmp     short loc_18003F917
0x18003f90b  mov     ebx, 12h
0x18003f910  lea     rdi, aWindows9; "Windows9"
0x18003f917  mov     rdx, rbx
0x18003f91a  lea     rcx, [rbp+var_40]
0x18003f91e  call    ?Allocate@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VDummyContext@@@@QEAAJ_K@Z; Auto<ushort *,LocalAllocFunctor<ushort *>,DummyContext>::Allocate(unsigned __int64)
0x18003f923  mov     [rbp+arg_0], eax
0x18003f926  test    eax, eax
0x18003f928  jns     short loc_18003F950
0x18003f92a  lea     r8, aHrSpcopyAlloca; "hr = spCopy.Allocate(bytesNeeded)"
0x18003f931  mov     [rsp+70h+var_50], r8; char *
0x18003f936  mov     r8d, 0F2h; unsigned int
0x18003f93c  mov     r9d, eax; int
0x18003f93f  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18003f946  mov     rdx, r15; char *
0x18003f949  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003f94e  jmp     short loc_18003F990
0x18003f950  mov     r11, [rbp+var_40]
0x18003f954  mov     r8, rdi; unsigned __int16 *
0x18003f957  mov     rcx, r11; unsigned __int16 *
0x18003f95a  mov     rdx, rbx; unsigned __int64
0x18003f95d  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18003f962  mov     [rbp+arg_0], eax
0x18003f965  test    eax, eax
0x18003f967  jns     short loc_18003F97D
0x18003f969  lea     rcx, aHrStringcbcopy_0; "hr = StringCbCopy(spCopy, bytesNeeded, "...
0x18003f970  mov     r8d, 0F3h
0x18003f976  mov     [rsp+70h+var_50], rcx
0x18003f97b  jmp     short loc_18003F93C
0x18003f97d  mov     [rbp+var_40], 0
0x18003f985  mov     [rbp+var_38], 0
0x18003f98d  mov     [rsi], r11
0x18003f990  mov     ebx, [rbp+arg_0]
0x18003f993  lea     rcx, [rbp+var_28]
0x18003f997  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18003f99c  lea     rcx, [rbp+var_40]
0x18003f9a0  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x18003f9a5  lea     r11, [rsp+70h+var_s0]
0x18003f9aa  mov     eax, ebx
0x18003f9ac  mov     rbx, [r11+30h]
0x18003f9b0  mov     rsi, [r11+38h]
0x18003f9b4  mov     rsp, r11
0x18003f9b7  pop     r15
0x18003f9b9  pop     rdi
0x18003f9ba  pop     rbp
0x18003f9bb  retn
```
