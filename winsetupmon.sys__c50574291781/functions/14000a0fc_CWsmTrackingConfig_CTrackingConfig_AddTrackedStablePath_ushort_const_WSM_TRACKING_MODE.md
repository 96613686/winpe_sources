# CWsmTrackingConfig::CTrackingConfig::AddTrackedStablePath(ushort const *,_WSM_TRACKING_MODE)

- ea: `0x14000a0fc`
- end: `0x14000a2f4`
- name: `?AddTrackedStablePath@CTrackingConfig@CWsmTrackingConfig@@QEAAJPEBGW4_WSM_TRACKING_MODE@@@Z`
- size: `504`
- prototype: `int __high(const unsigned __int16 *, enum _WSM_TRACKING_MODE)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000a300`

## callees

- `0x140008bb0`
- `0x1400091cc`
- `0x14000a0fc`
- `0x14000a8c4`
- `0x14000d0a8`
- `0x14000d21c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a1d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a211`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a24f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a2e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a1d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a211`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a24f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a2e0`
- `ntoskrnl!_wcsicmp` at `0x14000a12b`
- `ntoskrnl!_wcsicmp` at `0x14000a12b`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::CTrackingConfig::AddTrackedStablePath(__int64 a1, const wchar_t *a2, int a3)
{
  __int64 v3; // rdi
  struct CWsmTrackingConfig::CTrackingPathInfo **v7; // rax
  int Instance; // r14d
  void ***v9; // rdi
  __int64 v10; // rdx
  PVOID v11; // rax
  void ***v12; // rdi
  __int64 *v13; // rdi
  PVOID v14; // rbx
  __int64 v16; // r8
  unsigned __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int128 v20; // xmm0
  __int64 v21; // xmm1_8
  __int64 v22; // rcx
  PVOID v23; // rbx
  const wchar_t *v24; // [rsp+20h] [rbp-38h] BYREF
  int v25; // [rsp+28h] [rbp-30h]
  __int64 v26; // [rsp+2Ch] [rbp-2Ch]
  int v27; // [rsp+34h] [rbp-24h]
  void ***v28; // [rsp+38h] [rbp-20h] BYREF
  void ****v29; // [rsp+40h] [rbp-18h]
  PVOID P; // [rsp+90h] [rbp+38h] BYREF

  v3 = 0;
  if ( !*(_DWORD *)(a1 + 104) )
  {
LABEL_4:
    if ( (unsigned __int8)utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::resize(
                            a1 + 8,
                            ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8)) >> 3) + 1) )
    {
      v26 = 0;
      v27 = 0;
      v24 = a2;
      v25 = a3;
      P = 0;
      v7 = (struct CWsmTrackingConfig::CTrackingPathInfo **)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,>(
                                                              &v28,
                                                              &P);
      Instance = CWsmTrackingConfig::CTrackingPathInfo::CreateInstance(
                   (struct _WSM_TRACKING_PATH_INFO *const)&v24,
                   1,
                   v7);
      if ( v28 )
      {
        v9 = *v29;
        *v29 = v28;
        if ( v9 )
        {
          CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(v9);
          ExFreePoolWithTag(v9, 0x6E6D7377u);
        }
      }
      if ( Instance >= 0 )
      {
        v10 = *(_QWORD *)(a1 + 16);
        v11 = P;
        P = 0;
        v12 = *(void ****)(v10 - 8);
        *(_QWORD *)(v10 - 8) = v11;
        if ( v12 )
        {
          CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(v12);
          ExFreePoolWithTag(v12, 0x6E6D7377u);
        }
        v13 = (__int64 *)(a1 + 32);
        if ( !utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(
                (__int64 *)(a1 + 32),
                (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8)) >> 3) )
        {
          v14 = P;
          if ( P )
          {
            CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo((void ***)P);
            ExFreePoolWithTag(v14, 0x6E6D7377u);
          }
          return 3221225626LL;
        }
        v16 = 0;
        v17 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a1 + 40) - *(_QWORD *)(a1 + 32)) >> 3);
        *(_DWORD *)(a1 + 104) = v17;
        if ( (_DWORD)v17 )
        {
          do
          {
            v18 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v16);
            v19 = *v13;
            v20 = *(_OWORD *)(v18 + 72);
            v21 = *(_QWORD *)(v18 + 88);
            v22 = 3 * v16;
            *(_OWORD *)(v19 + 8 * v22) = v20;
            v16 = (unsigned int)(v16 + 1);
            *(_QWORD *)(v19 + 8 * v22 + 16) = v21;
          }
          while ( (unsigned int)v16 < *(_DWORD *)(a1 + 104) );
        }
        *(_QWORD *)(a1 + 112) = *v13;
      }
      v23 = P;
      if ( P )
      {
        CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo((void ***)P);
        ExFreePoolWithTag(v23, 0x6E6D7377u);
      }
      return (unsigned int)Instance;
    }
    return 3221225626LL;
  }
  while ( _wcsicmp(*(const wchar_t **)(*(_QWORD *)(a1 + 112) + 24 * v3), a2) )
  {
    v3 = (unsigned int)(v3 + 1);
    if ( (unsigned int)v3 >= *(_DWORD *)(a1 + 104) )
      goto LABEL_4;
  }
  return 3221226768LL;
}

```

## disassembly

```asm
0x14000a0fc  push    rbp
0x14000a0fe  push    rbx
0x14000a0ff  push    rsi
0x14000a100  push    rdi
0x14000a101  push    r14
0x14000a103  push    r15
0x14000a105  mov     rbp, rsp
0x14000a108  sub     rsp, 58h
0x14000a10c  xor     edi, edi
0x14000a10e  mov     r15d, r8d
0x14000a111  mov     r14, rdx
0x14000a114  mov     rbx, rcx
0x14000a117  cmp     [rcx+68h], edi
0x14000a11a  jbe     short loc_14000A146
0x14000a11c  mov     rcx, [rbx+70h]
0x14000a120  lea     r8, [rdi+rdi*2]
0x14000a124  mov     rdx, r14; Str2
0x14000a127  mov     rcx, [rcx+r8*8]; Str1
0x14000a12b  call    cs:__imp__wcsicmp
0x14000a132  nop     dword ptr [rax+rax+00h]
0x14000a137  test    eax, eax
0x14000a139  jz      loc_14000A26E
0x14000a13f  inc     edi
0x14000a141  cmp     edi, [rbx+68h]
0x14000a144  jb      short loc_14000A11C
0x14000a146  lea     rsi, [rbx+8]
0x14000a14a  mov     rdx, [rsi+8]
0x14000a14e  mov     rcx, rsi
0x14000a151  sub     rdx, [rsi]
0x14000a154  sar     rdx, 3
0x14000a158  inc     rdx
0x14000a15b  call    ?resize@?$vector@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@@2@@utl@@QEAA_N_K@Z; utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>>>::resize(unsigned __int64)
0x14000a160  test    al, al
0x14000a162  jz      loc_14000A25B
0x14000a168  lea     rdx, [rbp+P]
0x14000a16c  mov     [rbp+var_2C], 0
0x14000a174  lea     rcx, [rbp+var_20]
0x14000a178  mov     [rbp+var_24], 0
0x14000a17f  mov     [rbp+var_38], r14
0x14000a183  mov     [rbp+var_30], r15d
0x14000a187  mov     [rbp+P], 0
0x14000a18f  call    ??$out_ptr@XV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@@Z
0x14000a194  mov     r8, rax; struct CWsmTrackingConfig::CTrackingPathInfo **
0x14000a197  lea     rcx, [rbp+var_38]; struct _WSM_TRACKING_PATH_INFO *
0x14000a19b  mov     dl, 1; bool
0x14000a19d  call    ?CreateInstance@CTrackingPathInfo@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_PATH_INFO@@_NPEAPEAV12@@Z; CWsmTrackingConfig::CTrackingPathInfo::CreateInstance(_WSM_TRACKING_PATH_INFO * const,bool,CWsmTrackingConfig::CTrackingPathInfo * *)
0x14000a1a2  mov     r14d, eax
0x14000a1a5  mov     r15d, 6E6D7377h
0x14000a1ab  mov     rax, [rbp+var_20]
0x14000a1af  test    rax, rax
0x14000a1b2  jz      short loc_14000A1DD
0x14000a1b4  mov     rdx, [rbp+var_18]
0x14000a1b8  mov     rdi, [rdx]
0x14000a1bb  mov     [rdx], rax
0x14000a1be  test    rdi, rdi
0x14000a1c1  jz      short loc_14000A1DD
0x14000a1c3  mov     rcx, rdi; this
0x14000a1c6  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000a1cb  mov     edx, r15d; Tag
0x14000a1ce  mov     rcx, rdi; P
0x14000a1d1  call    cs:__imp_ExFreePoolWithTag
0x14000a1d8  nop     dword ptr [rax+rax+00h]
0x14000a1dd  test    r14d, r14d
0x14000a1e0  js      loc_14000A2C9
0x14000a1e6  mov     rdx, [rbx+10h]
0x14000a1ea  mov     rax, [rbp+P]
0x14000a1ee  mov     [rbp+P], 0
0x14000a1f6  mov     rdi, [rdx-8]
0x14000a1fa  mov     [rdx-8], rax
0x14000a1fe  test    rdi, rdi
0x14000a201  jz      short loc_14000A21D
0x14000a203  mov     rcx, rdi; this
0x14000a206  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000a20b  mov     edx, r15d; Tag
0x14000a20e  mov     rcx, rdi; P
0x14000a211  call    cs:__imp_ExFreePoolWithTag
0x14000a218  nop     dword ptr [rax+rax+00h]
0x14000a21d  mov     rdx, [rsi+8]
0x14000a221  lea     rdi, [rbx+20h]
0x14000a225  sub     rdx, [rsi]
0x14000a228  mov     rcx, rdi
0x14000a22b  sar     rdx, 3
0x14000a22f  call    ?resize@?$vector@U_WSM_TRACKING_PATH_INFO@@V?$allocator@U_WSM_TRACKING_PATH_INFO@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(unsigned __int64)
0x14000a234  test    al, al
0x14000a236  jnz     short loc_14000A275
0x14000a238  mov     rbx, [rbp+P]
0x14000a23c  test    rbx, rbx
0x14000a23f  jz      short loc_14000A25B
0x14000a241  mov     rcx, rbx; this
0x14000a244  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000a249  mov     edx, r15d; Tag
0x14000a24c  mov     rcx, rbx; P
0x14000a24f  call    cs:__imp_ExFreePoolWithTag
0x14000a256  nop     dword ptr [rax+rax+00h]
0x14000a25b  mov     eax, 0C000009Ah
0x14000a260  add     rsp, 58h
0x14000a264  pop     r15
0x14000a266  pop     r14
0x14000a268  pop     rdi
0x14000a269  pop     rsi
0x14000a26a  pop     rbx
0x14000a26b  pop     rbp
0x14000a26c  retn
0x14000a26e  mov     eax, 0C0000510h
0x14000a273  jmp     short loc_14000A260
0x14000a275  mov     rcx, [rdi+8]
0x14000a279  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000a283  sub     rcx, [rdi]
0x14000a286  xor     r8d, r8d
0x14000a289  sar     rcx, 3
0x14000a28d  imul    rcx, rax
0x14000a291  mov     [rbx+68h], ecx
0x14000a294  test    ecx, ecx
0x14000a296  jz      short loc_14000A2C2
0x14000a298  mov     rax, [rsi]
0x14000a29b  mov     rcx, [rax+r8*8]
0x14000a29f  mov     rax, [rdi]
0x14000a2a2  movups  xmm0, xmmword ptr [rcx+48h]
0x14000a2a6  movsd   xmm1, qword ptr [rcx+58h]
0x14000a2ab  lea     rcx, [r8+r8*2]
0x14000a2af  movups  xmmword ptr [rax+rcx*8], xmm0
0x14000a2b3  inc     r8d
0x14000a2b6  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x14000a2bc  cmp     r8d, [rbx+68h]
0x14000a2c0  jb      short loc_14000A298
0x14000a2c2  mov     rax, [rdi]
0x14000a2c5  mov     [rbx+70h], rax
0x14000a2c9  mov     rbx, [rbp+P]
0x14000a2cd  test    rbx, rbx
0x14000a2d0  jz      short loc_14000A2EC
0x14000a2d2  mov     rcx, rbx; this
0x14000a2d5  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000a2da  mov     edx, r15d; Tag
0x14000a2dd  mov     rcx, rbx; P
0x14000a2e0  call    cs:__imp_ExFreePoolWithTag
0x14000a2e7  nop     dword ptr [rax+rax+00h]
0x14000a2ec  mov     eax, r14d
0x14000a2ef  jmp     loc_14000A260
```
