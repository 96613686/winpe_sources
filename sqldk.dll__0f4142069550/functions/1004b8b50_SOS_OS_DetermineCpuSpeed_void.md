# SOS_OS::DetermineCpuSpeed(void)

- ea: `0x1004b8b50`
- end: `0x1004b8ec0`
- name: `?DetermineCpuSpeed@SOS_OS@@SAXXZ`
- size: `880`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1004b1350`

## callees

- `0x100403070`
- `0x1004b8b50`
- `0x100567a30`
- `0x1006161ab`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1004b8c5a`
- `KERNEL32!GetCurrentThread` at `0x1004b8cd9`
- `KERNEL32!GetCurrentThread` at `0x1004b8c5a`
- `KERNEL32!GetCurrentThread` at `0x1004b8cd9`
- `KERNEL32!GetTickCount` at `0x1004b8c73`
- `KERNEL32!GetTickCount` at `0x1004b8c80`
- `KERNEL32!GetTickCount` at `0x1004b8c90`
- `KERNEL32!GetTickCount` at `0x1004b8ca4`
- `KERNEL32!GetTickCount` at `0x1004b8c73`
- `KERNEL32!GetTickCount` at `0x1004b8c80`
- `KERNEL32!GetTickCount` at `0x1004b8c90`
- `KERNEL32!GetTickCount` at `0x1004b8ca4`
- `ADVAPI32!RegQueryValueExW` at `0x1004b8dc8`
- `ADVAPI32!RegQueryValueExW` at `0x1004b8dc8`
- `ADVAPI32!RegOpenKeyExW` at `0x1004b8d8c`
- `ADVAPI32!RegOpenKeyExW` at `0x1004b8d8c`
- `ADVAPI32!RegCloseKey` at `0x1004b8e6f`
- `ADVAPI32!RegCloseKey` at `0x1004b8e6f`

## pseudocode

```c
void SOS_OS::DetermineCpuSpeed(void)
{
  __int16 v0; // dx
  __int64 v1; // rsi
  HKEY v2; // rcx
  struct OsNumaConfig *v3; // rdi
  __int64 v4; // rbx
  HANDLE CurrentThread; // rax
  DWORD TickCount; // ebx
  __int64 v7; // r14
  DWORD v8; // ebx
  unsigned __int64 v9; // rdi
  DWORD v10; // ecx
  unsigned __int64 v11; // rax
  struct OsNumaConfig *v12; // rbx
  __int64 v13; // rdi
  HANDLE v14; // rax
  __m128d v15; // xmm1
  double v16; // xmm1_8
  double v17; // xmm0_8
  unsigned __int64 v18; // rax
  __int64 v19; // rbx
  double v20; // xmm1_8
  double v21; // xmm0_8
  double v22; // xmm1_8
  void (*v23)(const wchar_t *, ...); // rax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  _OWORD *v26; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+40h] [rbp-C0h]
  HKEY v28; // [rsp+48h] [rbp-B8h]
  __int16 v29; // [rsp+50h] [rbp-B0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v31; // [rsp+60h] [rbp-A0h]
  GUID v32; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v33[8]; // [rsp+80h] [rbp-80h] BYREF

  v0 = 0;
  v1 = 0;
  v32 = Zero<XE_StaticPackage<1>::LocaleEntry>::sm_val;
  v26 = v33;
  v33[1] = xmmword_10071F990;
  v33[3] = xmmword_10071F9B0;
  v33[2] = xmmword_10071F9A0;
  v2 = (HKEY)(SOS_PublicGlobals::sm_osSystemAffinity & ~(SOS_PublicGlobals::sm_osSystemAffinity - 1LL));
  v33[5] = xmmword_10071F9D0;
  v33[4] = xmmword_10071F9C0;
  v33[7] = xmmword_10071F9F0;
  v33[0] = SOS_PublicGlobals::sm_osSystemAffinity;
  v33[6] = xmmword_10071F9E0;
  v29 = 0;
  v27 = SOS_PublicGlobals::sm_osSystemAffinity;
  v28 = v2;
  if ( !v2 )
  {
    v27 = *((_QWORD *)&v33[0] + 1);
    v29 = 1;
    v28 = 0;
    SystemAffinityEnum::MoveNextBitSet((SystemAffinityEnum *)&v26);
    v0 = v29;
    v2 = v28;
  }
  v3 = OsNumaConfig::sm_instance;
  v31 = v0;
  hKey = v2;
  v4 = *(_QWORD *)OsNumaConfig::sm_instance;
  CurrentThread = GetCurrentThread();
  (*(void (__fastcall **)(struct OsNumaConfig *, HANDLE, HKEY *, GUID *))(v4 + 48))(v3, CurrentThread, &hKey, &v32);
  TickCount = GetTickCount();
  while ( GetTickCount() == TickCount )
    ;
  v7 = 5;
  do
  {
    v8 = GetTickCount();
    v9 = __rdtsc();
    do
      v10 = GetTickCount();
    while ( v10 == v8 );
    v11 = __rdtsc();
    v1 += (v11 - v9) / (v10 - v8) * ((v11 - v9) / (v10 - v8));
    --v7;
  }
  while ( v7 );
  v12 = OsNumaConfig::sm_instance;
  v13 = *(_QWORD *)OsNumaConfig::sm_instance;
  v14 = GetCurrentThread();
  (*(void (__fastcall **)(struct OsNumaConfig *, HANDLE, GUID *, _QWORD))(v13 + 48))(v12, v14, &v32, 0);
  v15 = 0;
  if ( v1 < 0 )
    v16 = (double)(int)(v1 & 1 | ((unsigned __int64)v1 >> 1)) + (double)(int)(v1 & 1 | ((unsigned __int64)v1 >> 1));
  else
    v16 = (double)(int)v1;
  v15.m128d_f64[0] = v16 / 5.0;
  if ( v15.m128d_f64[0] < 0.0 )
    v17 = sqrt_0(v15.m128d_f64[0]);
  else
    *(_QWORD *)&v17 = *(_OWORD *)&_mm_sqrt_pd(v15);
  v18 = 0;
  if ( v17 >= 9.223372036854776e18 )
  {
    v17 = v17 - 9.223372036854776e18;
    if ( v17 < 9.223372036854776e18 )
      v18 = 0x8000000000000000uLL;
  }
  hKey = 0;
  v19 = v18 + (unsigned int)(int)v17;
  SOS_PublicGlobals::sm_CpuTicksPerMillisecond = v19;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"HARDWARE\\Description\\System\\CentralProcessor\\0", 0, 1u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"~MHz", 0, 0, Data, &cbData) )
    {
      if ( v19 )
      {
        if ( 1000LL * *(unsigned int *)Data < 0 )
          v20 = (double)(int)((1000 * (unsigned __int64)*(unsigned int *)Data) >> 1)
              + (double)(int)((1000 * (unsigned __int64)*(unsigned int *)Data) >> 1);
        else
          v20 = (double)(1000 * *(_DWORD *)Data);
        if ( v19 < 0 )
          v21 = (double)(int)(v19 & 1 | ((unsigned __int64)v19 >> 1))
              + (double)(int)(v19 & 1 | ((unsigned __int64)v19 >> 1));
        else
          v21 = (double)(int)v19;
        v22 = v20 / v21;
        if ( v22 >= 0.9 && v22 <= 1.1 )
        {
          v19 = 1000LL * *(unsigned int *)Data;
          SOS_PublicGlobals::sm_CpuTicksPerMillisecond = v19;
        }
      }
      else
      {
        v19 = 1000LL * *(unsigned int *)Data;
        SOS_PublicGlobals::sm_CpuTicksPerMillisecond = v19;
      }
    }
    RegCloseKey(hKey);
  }
  v23 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
  if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
    v23 = SOS_OS_LogUnlocalizedRoutine;
  v23(L"Number of cycles produced on the CPU in 1 millisecond: %u.\n", v19);
}

```

## disassembly

```asm
0x1004b8b50  mov     [rsp-8+arg_0], rbx
0x1004b8b55  mov     [rsp-8+arg_8], rsi
0x1004b8b5a  mov     [rsp-8+arg_10], rdi
0x1004b8b5f  mov     [rsp-8+arg_18], r12
0x1004b8b64  push    rbp
0x1004b8b65  push    r14
0x1004b8b67  push    r15
0x1004b8b69  lea     rbp, [rsp-10h]
0x1004b8b6e  sub     rsp, 110h
0x1004b8b75  mov     rax, cs:__security_cookie
0x1004b8b7c  xor     rax, rsp
0x1004b8b7f  mov     [rbp+20h+var_20], rax
0x1004b8b83  movups  xmm0, xmmword ptr cs:?sm_val@?$Zero@ULocaleEntry@?$XE_StaticPackage@$00@@@@2ULocaleEntry@?$XE_StaticPackage@$00@@B.Data1; XE_StaticPackage<1>::LocaleEntry const Zero<XE_StaticPackage<1>::LocaleEntry>::sm_val ...
0x1004b8b8a  lea     rax, [rbp+20h+var_A0]
0x1004b8b8e  xor     r15d, r15d
0x1004b8b91  movaps  xmm2, cs:?sm_osSystemAffinity@SOS_PublicGlobals@@2VSystemAffinity@@A; SystemAffinity SOS_PublicGlobals::sm_osSystemAffinity
0x1004b8b98  movzx   edx, r15w
0x1004b8b9c  movaps  xmm1, cs:xmmword_10071F9A0
0x1004b8ba3  mov     esi, r15d
0x1004b8ba6  movups  xmmword ptr [rsp+120h+var_B8.Data1], xmm0
0x1004b8bab  lea     r12d, [r15+1]
0x1004b8baf  mov     [rsp+120h+var_E8], rax
0x1004b8bb4  movaps  xmm0, cs:xmmword_10071F990
0x1004b8bbb  movq    rax, xmm2
0x1004b8bc0  movaps  [rbp+20h+var_90], xmm0
0x1004b8bc4  movaps  xmm0, cs:xmmword_10071F9B0
0x1004b8bcb  movaps  [rbp+20h+var_70], xmm0
0x1004b8bcf  movaps  xmm0, cs:xmmword_10071F9D0
0x1004b8bd6  lea     rcx, [rax-1]
0x1004b8bda  movaps  [rbp+20h+var_80], xmm1
0x1004b8bde  not     rcx
0x1004b8be1  movaps  xmm1, cs:xmmword_10071F9C0
0x1004b8be8  and     rcx, rax
0x1004b8beb  movaps  [rbp+20h+var_50], xmm0
0x1004b8bef  movaps  xmm0, cs:xmmword_10071F9F0
0x1004b8bf6  movaps  [rbp+20h+var_60], xmm1
0x1004b8bfa  movaps  xmm1, cs:xmmword_10071F9E0
0x1004b8c01  movaps  [rbp+20h+var_30], xmm0
0x1004b8c05  movaps  [rbp+20h+var_A0], xmm2
0x1004b8c09  movaps  [rbp+20h+var_40], xmm1
0x1004b8c0d  mov     [rsp+120h+var_D0], dx
0x1004b8c12  mov     [rsp+120h+var_E0], rax
0x1004b8c17  mov     [rsp+120h+var_D8], rcx
0x1004b8c1c  jnz     short loc_1004B8C46
0x1004b8c1e  mov     rax, qword ptr [rbp+20h+var_A0+8]
0x1004b8c22  lea     rcx, [rsp+120h+var_E8]; this
0x1004b8c27  mov     [rsp+120h+var_E0], rax
0x1004b8c2c  mov     [rsp+120h+var_D0], r12w
0x1004b8c32  mov     [rsp+120h+var_D8], r15
0x1004b8c37  call    ?MoveNextBitSet@SystemAffinityEnum@@QEAAHXZ; SystemAffinityEnum::MoveNextBitSet(void)
0x1004b8c3c  movzx   edx, [rsp+120h+var_D0]
0x1004b8c41  mov     rcx, [rsp+120h+var_D8]
0x1004b8c46  mov     rdi, cs:?sm_instance@OsNumaConfig@@0PEAV1@EA; OsNumaConfig * OsNumaConfig::sm_instance
0x1004b8c4d  mov     [rsp+120h+var_C0], dx
0x1004b8c52  mov     [rsp+120h+hKey], rcx
0x1004b8c57  mov     rbx, [rdi]
0x1004b8c5a  call    cs:__imp_GetCurrentThread
0x1004b8c60  lea     r9, [rsp+120h+var_B8]
0x1004b8c65  mov     rcx, rdi
0x1004b8c68  mov     rdx, rax
0x1004b8c6b  lea     r8, [rsp+120h+hKey]
0x1004b8c70  call    qword ptr [rbx+30h]
0x1004b8c73  call    cs:__imp_GetTickCount
0x1004b8c79  mov     ebx, eax
0x1004b8c7b  nop     dword ptr [rax+rax+00h]
0x1004b8c80  call    cs:__imp_GetTickCount
0x1004b8c86  cmp     eax, ebx
0x1004b8c88  jz      short loc_1004B8C80
0x1004b8c8a  mov     r14d, 5
0x1004b8c90  call    cs:__imp_GetTickCount
0x1004b8c96  mov     ebx, eax
0x1004b8c98  rdtsc
0x1004b8c9a  shl     rdx, 20h
0x1004b8c9e  or      rax, rdx
0x1004b8ca1  mov     rdi, rax
0x1004b8ca4  call    cs:__imp_GetTickCount
0x1004b8caa  mov     ecx, eax
0x1004b8cac  cmp     eax, ebx
0x1004b8cae  jz      short loc_1004B8CA4
0x1004b8cb0  rdtsc
0x1004b8cb2  shl     rdx, 20h
0x1004b8cb6  sub     ecx, ebx
0x1004b8cb8  or      rax, rdx
0x1004b8cbb  xor     edx, edx
0x1004b8cbd  sub     rax, rdi
0x1004b8cc0  div     rcx
0x1004b8cc3  imul    rax, rax
0x1004b8cc7  add     rsi, rax
0x1004b8cca  sub     r14, r12
0x1004b8ccd  jnz     short loc_1004B8C90
0x1004b8ccf  mov     rbx, cs:?sm_instance@OsNumaConfig@@0PEAV1@EA; OsNumaConfig * OsNumaConfig::sm_instance
0x1004b8cd6  mov     rdi, [rbx]
0x1004b8cd9  call    cs:__imp_GetCurrentThread
0x1004b8cdf  xor     r9d, r9d
0x1004b8ce2  lea     r8, [rsp+120h+var_B8]
0x1004b8ce7  mov     rdx, rax
0x1004b8cea  mov     rcx, rbx
0x1004b8ced  call    qword ptr [rdi+30h]
0x1004b8cf0  xorps   xmm1, xmm1
0x1004b8cf3  test    rsi, rsi
0x1004b8cf6  js      short loc_1004B8CFF
0x1004b8cf8  cvtsi2sd xmm1, rsi
0x1004b8cfd  jmp     short loc_1004B8D14
0x1004b8cff  mov     rax, rsi
0x1004b8d02  and     esi, r12d
0x1004b8d05  shr     rax, 1
0x1004b8d08  or      rax, rsi
0x1004b8d0b  cvtsi2sd xmm1, rax
0x1004b8d10  addsd   xmm1, xmm1
0x1004b8d14  divsd   xmm1, cs:__real@4014000000000000
0x1004b8d1c  xorps   xmm0, xmm0
0x1004b8d1f  ucomisd xmm0, xmm1
0x1004b8d23  ja      short loc_1004B8D2B
0x1004b8d25  sqrtpd  xmm0, xmm1
0x1004b8d29  jmp     short loc_1004B8D33
0x1004b8d2b  movaps  xmm0, xmm1; X
0x1004b8d2e  call    sqrt_0
0x1004b8d33  movsd   xmm1, cs:__real@43e0000000000000
0x1004b8d3b  xor     eax, eax
0x1004b8d3d  comisd  xmm0, xmm1
0x1004b8d41  jb      short loc_1004B8D5A
0x1004b8d43  subsd   xmm0, xmm1
0x1004b8d47  comisd  xmm0, xmm1
0x1004b8d4b  jnb     short loc_1004B8D5A
0x1004b8d4d  mov     rcx, 8000000000000000h
0x1004b8d57  mov     rax, rcx
0x1004b8d5a  cvttsd2si rbx, xmm0
0x1004b8d5f  mov     r9d, r12d; samDesired
0x1004b8d62  mov     [rsp+120h+hKey], r15
0x1004b8d67  xor     r8d, r8d; ulOptions
0x1004b8d6a  lea     rdx, aHardwareDescri; "HARDWARE\\Description\\System\\CentralP"...
0x1004b8d71  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1004b8d78  add     rbx, rax
0x1004b8d7b  lea     rax, [rsp+120h+hKey]
0x1004b8d80  mov     [rsp+120h+phkResult], rax; phkResult
0x1004b8d85  mov     cs:?sm_CpuTicksPerMillisecond@SOS_PublicGlobals@@2_KA, rbx; unsigned __int64 SOS_PublicGlobals::sm_CpuTicksPerMillisecond
0x1004b8d8c  call    cs:__imp_RegOpenKeyExW
0x1004b8d92  test    eax, eax
0x1004b8d94  jnz     loc_1004B8E75
0x1004b8d9a  mov     rcx, [rsp+120h+hKey]; hKey
0x1004b8d9f  lea     rax, [rsp+120h+cbData]
0x1004b8da4  mov     [rsp+120h+lpcbData], rax; lpcbData
0x1004b8da9  lea     rdx, aMhz; "~MHz"
0x1004b8db0  lea     rax, [rsp+120h+Data]
0x1004b8db5  mov     [rsp+120h+cbData], 4
0x1004b8dbd  xor     r9d, r9d; lpType
0x1004b8dc0  mov     [rsp+120h+phkResult], rax; lpData
0x1004b8dc5  xor     r8d, r8d; lpReserved
0x1004b8dc8  call    cs:__imp_RegQueryValueExW
0x1004b8dce  test    eax, eax
0x1004b8dd0  jnz     loc_1004B8E6A
0x1004b8dd6  mov     eax, dword ptr [rsp+120h+Data]
0x1004b8dda  test    rbx, rbx
0x1004b8ddd  jnz     short loc_1004B8DEF
0x1004b8ddf  imul    rbx, rax, 3E8h
0x1004b8de6  mov     cs:?sm_CpuTicksPerMillisecond@SOS_PublicGlobals@@2_KA, rbx; unsigned __int64 SOS_PublicGlobals::sm_CpuTicksPerMillisecond
0x1004b8ded  jmp     short loc_1004B8E6A
0x1004b8def  imul    rdx, rax, 3E8h
0x1004b8df6  xorps   xmm1, xmm1
0x1004b8df9  test    rdx, rdx
0x1004b8dfc  js      short loc_1004B8E05
0x1004b8dfe  cvtsi2sd xmm1, rdx
0x1004b8e03  jmp     short loc_1004B8E1D
0x1004b8e05  mov     rax, rdx
0x1004b8e08  mov     rcx, rdx
0x1004b8e0b  shr     rcx, 1
0x1004b8e0e  and     eax, r12d
0x1004b8e11  or      rcx, rax
0x1004b8e14  cvtsi2sd xmm1, rcx
0x1004b8e19  addsd   xmm1, xmm1
0x1004b8e1d  xorps   xmm0, xmm0
0x1004b8e20  test    rbx, rbx
0x1004b8e23  js      short loc_1004B8E2C
0x1004b8e25  cvtsi2sd xmm0, rbx
0x1004b8e2a  jmp     short loc_1004B8E44
0x1004b8e2c  mov     rax, rbx
0x1004b8e2f  mov     rcx, rbx
0x1004b8e32  shr     rcx, 1
0x1004b8e35  and     eax, r12d
0x1004b8e38  or      rcx, rax
0x1004b8e3b  cvtsi2sd xmm0, rcx
0x1004b8e40  addsd   xmm0, xmm0
0x1004b8e44  divsd   xmm1, xmm0
0x1004b8e48  comisd  xmm1, cs:__real@3feccccccccccccd
0x1004b8e50  jb      short loc_1004B8E6A
0x1004b8e52  movsd   xmm0, cs:__real@3ff199999999999a
0x1004b8e5a  comisd  xmm0, xmm1
0x1004b8e5e  jb      short loc_1004B8E6A
0x1004b8e60  mov     rbx, rdx
0x1004b8e63  mov     cs:?sm_CpuTicksPerMillisecond@SOS_PublicGlobals@@2_KA, rdx; unsigned __int64 SOS_PublicGlobals::sm_CpuTicksPerMillisecond
0x1004b8e6a  mov     rcx, [rsp+120h+hKey]; hKey
0x1004b8e6f  call    cs:__imp_RegCloseKey
0x1004b8e75  mov     rax, cs:?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA; void (*SOS_PublicGlobals::sm_LogSystemMetadataRoutine)(wchar_t const *,...)
0x1004b8e7c  lea     rcx, aNumberOfCycles; "Number of cycles produced on the CPU in"...
0x1004b8e83  test    rax, rax
0x1004b8e86  mov     rdx, rbx
0x1004b8e89  cmovz   rax, cs:?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x1004b8e91  call    rax
0x1004b8e93  mov     rcx, [rbp+20h+var_20]
0x1004b8e97  xor     rcx, rsp; StackCookie
0x1004b8e9a  call    __security_check_cookie
0x1004b8e9f  lea     r11, [rsp+120h+var_10]
0x1004b8ea7  mov     rbx, [r11+20h]
0x1004b8eab  mov     rsi, [r11+28h]
0x1004b8eaf  mov     rdi, [r11+30h]
0x1004b8eb3  mov     r12, [r11+38h]
0x1004b8eb7  mov     rsp, r11
0x1004b8eba  pop     r15
0x1004b8ebc  pop     r14
0x1004b8ebe  pop     rbp
0x1004b8ebf  retn
```
