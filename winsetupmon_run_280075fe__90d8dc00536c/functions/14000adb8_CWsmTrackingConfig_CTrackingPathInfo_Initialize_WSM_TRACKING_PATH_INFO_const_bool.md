# CWsmTrackingConfig::CTrackingPathInfo::Initialize(_WSM_TRACKING_PATH_INFO * const,bool)

- ea: `0x14000adb8`
- end: `0x14000affd`
- name: `?Initialize@CTrackingPathInfo@CWsmTrackingConfig@@IEAAJQEAU_WSM_TRACKING_PATH_INFO@@_N@Z`
- size: `581`
- prototype: `int(CWsmTrackingConfig::CTrackingPathInfo *__hidden this, struct _WSM_TRACKING_PATH_INFO *const, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000a8c4`

## callees

- `0x140008b58`
- `0x140009120`
- `0x14000a7a4`
- `0x14000adb8`
- `0x14000ce88`
- `0x14000d0a8`
- `0x14000d174`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000aed3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000af1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000af6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000afe8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000aed3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000af1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000af6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000afe8`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::CTrackingPathInfo::Initialize(
        CWsmTrackingConfig::CTrackingPathInfo *this,
        const unsigned __int16 **a2,
        bool a3)
{
  unsigned int Instance; // ebx
  bool v4; // r15
  const unsigned __int16 *v7; // rdx
  wsm_wstring *v8; // rcx
  int v9; // eax
  _QWORD *v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 *v13; // r13
  __int64 *v14; // r14
  __int64 v15; // rbp
  struct CWsmTrackingConfig::CTrackingOverrideInfo **v16; // rax
  CWsmTrackingConfig::CTrackingOverrideInfo *v17; // r15
  __int64 v18; // rax
  PVOID v19; // rdx
  CWsmTrackingConfig::CTrackingOverrideInfo *v20; // r15
  __int64 v21; // rcx
  __int64 v22; // rax
  __int128 v23; // xmm0
  __int64 v24; // xmm1_8
  __int64 v25; // rcx
  PVOID v26; // r15
  __int64 v27; // rax
  PVOID v29; // rdi
  CWsmTrackingConfig::CTrackingOverrideInfo *v30; // [rsp+20h] [rbp-58h] BYREF
  CWsmTrackingConfig::CTrackingOverrideInfo **v31; // [rsp+28h] [rbp-50h]
  PVOID P; // [rsp+88h] [rbp+10h] BYREF
  bool v33; // [rsp+90h] [rbp+18h]

  v33 = a3;
  Instance = 0;
  v4 = a3;
  if ( !a2 )
    return Instance;
  v7 = *a2;
  v8 = (CWsmTrackingConfig::CTrackingPathInfo *)((char *)this + 32);
  v9 = a3
     ? wsm_wstring::init(v8, v7)
     : (*(unsigned __int64 (__fastcall **)(wsm_wstring *, const unsigned __int16 *))(*(_QWORD *)v8 + 16LL))(v8, v7);
  Instance = v9;
  if ( v9 < 0 )
    return Instance;
  v10 = (_QWORD *)*((_QWORD *)this + 5);
  v11 = v10 ? *v10 : 0LL;
  *((_QWORD *)this + 9) = v11;
  *((_DWORD *)this + 20) = *((_DWORD *)a2 + 2);
  v12 = *((_DWORD *)a2 + 3);
  if ( !v12 )
    return Instance;
  v13 = (__int64 *)((char *)this + 8);
  if ( (unsigned __int8)utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>::resize(
                          (char *)this + 8,
                          v12) )
  {
    v14 = (__int64 *)((char *)this + 48);
    if ( (unsigned __int8)utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(
                            (char *)this + 48,
                            *((unsigned int *)a2 + 3)) )
    {
      v15 = 0;
      if ( *((_DWORD *)a2 + 3) )
      {
        while ( 1 )
        {
          P = 0;
          v16 = (struct CWsmTrackingConfig::CTrackingOverrideInfo **)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,>(
                                                                       &v30,
                                                                       &P);
          Instance = CWsmTrackingConfig::CTrackingOverrideInfo::CreateInstance(
                       (struct _WSM_TRACKING_OVERRIDE_INFO *const)&a2[2][12 * v15],
                       v4,
                       v16);
          if ( v30 )
          {
            v17 = *v31;
            *v31 = v30;
            if ( v17 )
            {
              CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(v17);
              ExFreePoolWithTag(v17, 0x6E6D7377u);
            }
          }
          if ( (Instance & 0x80000000) != 0 )
            break;
          v18 = *v13;
          v19 = P;
          P = 0;
          v20 = *(CWsmTrackingConfig::CTrackingOverrideInfo **)(v18 + 8 * v15);
          *(_QWORD *)(v18 + 8 * v15) = v19;
          if ( v20 )
          {
            CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(v20);
            ExFreePoolWithTag(v20, 0x6E6D7377u);
          }
          v21 = *(_QWORD *)(*v13 + 8 * v15);
          v22 = *v14;
          v23 = *(_OWORD *)(v21 + 40);
          v24 = *(_QWORD *)(v21 + 56);
          v25 = 3 * v15;
          *(_OWORD *)(v22 + 8 * v25) = v23;
          *(_QWORD *)(v22 + 8 * v25 + 16) = v24;
          v26 = P;
          if ( P )
          {
            CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo((CWsmTrackingConfig::CTrackingOverrideInfo *)P);
            ExFreePoolWithTag(v26, 0x6E6D7377u);
          }
          v4 = v33;
          v15 = (unsigned int)(v15 + 1);
          if ( (unsigned int)v15 >= *((_DWORD *)a2 + 3) )
            goto LABEL_22;
        }
        v29 = P;
        if ( P )
        {
          CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo((CWsmTrackingConfig::CTrackingOverrideInfo *)P);
          ExFreePoolWithTag(v29, 0x6E6D7377u);
        }
      }
      else
      {
LABEL_22:
        v27 = *((_QWORD *)this + 7) - *((_QWORD *)this + 6);
        *((_QWORD *)this + 11) = *v14;
        *((_DWORD *)this + 21) = -1431655765 * (v27 >> 3);
      }
      return Instance;
    }
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000adb8  mov     [rsp+arg_0], rbx
0x14000adbd  mov     [rsp+arg_10], r8b
0x14000adc2  push    rbp
0x14000adc3  push    rsi
0x14000adc4  push    rdi
0x14000adc5  push    r12
0x14000adc7  push    r13
0x14000adc9  push    r14
0x14000adcb  push    r15
0x14000adcd  sub     rsp, 40h
0x14000add1  xor     ebx, ebx
0x14000add3  mov     r15b, r8b
0x14000add6  mov     rsi, rdx
0x14000add9  mov     rdi, rcx
0x14000addc  test    rdx, rdx
0x14000addf  jz      loc_14000AFB0
0x14000ade5  mov     rdx, [rdx]; unsigned __int16 *
0x14000ade8  add     rcx, 20h ; ' '; this
0x14000adec  test    r8b, r8b
0x14000adef  jz      short loc_14000ADF8
0x14000adf1  call    ?init@wsm_wstring@@IEAAJPEBG@Z; wsm_wstring::init(ushort const *)
0x14000adf6  jmp     short loc_14000AE04
0x14000adf8  mov     rax, [rcx]
0x14000adfb  mov     rax, [rax+10h]
0x14000adff  call    _guard_dispatch_icall
0x14000ae04  mov     ebx, eax
0x14000ae06  test    eax, eax
0x14000ae08  js      loc_14000AFB0
0x14000ae0e  mov     rax, [rdi+28h]
0x14000ae12  test    rax, rax
0x14000ae15  jz      short loc_14000AE1C
0x14000ae17  mov     rcx, [rax]
0x14000ae1a  jmp     short loc_14000AE1E
0x14000ae1c  xor     ecx, ecx
0x14000ae1e  mov     [rdi+48h], rcx
0x14000ae22  mov     eax, [rsi+8]
0x14000ae25  mov     [rdi+50h], eax
0x14000ae28  mov     eax, [rsi+0Ch]
0x14000ae2b  test    eax, eax
0x14000ae2d  jz      loc_14000AFB0
0x14000ae33  lea     r13, [rdi+8]
0x14000ae37  mov     edx, eax
0x14000ae39  mov     rcx, r13
0x14000ae3c  call    ?resize@?$vector@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@2@@utl@@QEAA_N_K@Z; utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>::resize(unsigned __int64)
0x14000ae41  test    al, al
0x14000ae43  jz      loc_14000AFF6
0x14000ae49  mov     edx, [rsi+0Ch]
0x14000ae4c  lea     r14, [rdi+30h]
0x14000ae50  mov     rcx, r14
0x14000ae53  call    ?resize@?$vector@U_WSM_TRACKING_PATH_INFO@@V?$allocator@U_WSM_TRACKING_PATH_INFO@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(unsigned __int64)
0x14000ae58  test    al, al
0x14000ae5a  jz      loc_14000AFF6
0x14000ae60  xor     ebp, ebp
0x14000ae62  cmp     [rsi+0Ch], ebp
0x14000ae65  jbe     loc_14000AF8D
0x14000ae6b  lea     rdx, [rsp+78h+P]
0x14000ae73  mov     [rsp+78h+P], 0
0x14000ae7f  lea     rcx, [rsp+78h+var_58]
0x14000ae84  call    ??$out_ptr@XV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@0@@Z
0x14000ae89  mov     rcx, [rsi+10h]
0x14000ae8d  lea     rdx, ds:0[rbp*2]
0x14000ae95  add     rdx, rbp
0x14000ae98  mov     r8, rax; struct CWsmTrackingConfig::CTrackingOverrideInfo **
0x14000ae9b  lea     rcx, [rcx+rdx*8]; struct _WSM_TRACKING_OVERRIDE_INFO *
0x14000ae9f  mov     dl, r15b; bool
0x14000aea2  call    ?CreateInstance@CTrackingOverrideInfo@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_OVERRIDE_INFO@@_NPEAPEAV12@@Z; CWsmTrackingConfig::CTrackingOverrideInfo::CreateInstance(_WSM_TRACKING_OVERRIDE_INFO * const,bool,CWsmTrackingConfig::CTrackingOverrideInfo * *)
0x14000aea7  mov     rcx, [rsp+78h+var_58]
0x14000aeac  mov     ebx, eax
0x14000aeae  test    rcx, rcx
0x14000aeb1  jz      short loc_14000AEDF
0x14000aeb3  mov     rax, [rsp+78h+var_50]
0x14000aeb8  mov     r15, [rax]
0x14000aebb  mov     [rax], rcx
0x14000aebe  test    r15, r15
0x14000aec1  jz      short loc_14000AEDF
0x14000aec3  mov     rcx, r15; this
0x14000aec6  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x14000aecb  mov     edx, 6E6D7377h; Tag
0x14000aed0  mov     rcx, r15; P
0x14000aed3  call    cs:__imp_ExFreePoolWithTag
0x14000aeda  nop     dword ptr [rax+rax+00h]
0x14000aedf  test    ebx, ebx
0x14000aee1  js      loc_14000AFCB
0x14000aee7  mov     rax, [r13+0]
0x14000aeeb  mov     rdx, [rsp+78h+P]
0x14000aef3  mov     [rsp+78h+P], 0
0x14000aeff  mov     r15, [rax+rbp*8]
0x14000af03  mov     [rax+rbp*8], rdx
0x14000af07  test    r15, r15
0x14000af0a  jz      short loc_14000AF28
0x14000af0c  mov     rcx, r15; this
0x14000af0f  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x14000af14  mov     edx, 6E6D7377h; Tag
0x14000af19  mov     rcx, r15; P
0x14000af1c  call    cs:__imp_ExFreePoolWithTag
0x14000af23  nop     dword ptr [rax+rax+00h]
0x14000af28  mov     rax, [r13+0]
0x14000af2c  mov     rcx, [rax+rbp*8]
0x14000af30  mov     rax, [r14]
0x14000af33  movups  xmm0, xmmword ptr [rcx+28h]
0x14000af37  movsd   xmm1, qword ptr [rcx+38h]
0x14000af3c  lea     rcx, ds:0[rbp*2]
0x14000af44  add     rcx, rbp
0x14000af47  movups  xmmword ptr [rax+rcx*8], xmm0
0x14000af4b  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x14000af51  mov     r15, [rsp+78h+P]
0x14000af59  test    r15, r15
0x14000af5c  jz      short loc_14000AF7A
0x14000af5e  mov     rcx, r15; this
0x14000af61  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x14000af66  mov     edx, 6E6D7377h; Tag
0x14000af6b  mov     rcx, r15; P
0x14000af6e  call    cs:__imp_ExFreePoolWithTag
0x14000af75  nop     dword ptr [rax+rax+00h]
0x14000af7a  mov     r15b, [rsp+78h+arg_10]
0x14000af82  inc     ebp
0x14000af84  cmp     ebp, [rsi+0Ch]
0x14000af87  jb      loc_14000AE6B
0x14000af8d  mov     rcx, [r14]
0x14000af90  mov     rdx, 0AAAAAAAAAAAAAAABh
0x14000af9a  mov     rax, [r14+8]
0x14000af9e  sub     rax, rcx
0x14000afa1  mov     [rdi+58h], rcx
0x14000afa5  sar     rax, 3
0x14000afa9  imul    rax, rdx
0x14000afad  mov     [rdi+54h], eax
0x14000afb0  mov     eax, ebx
0x14000afb2  mov     rbx, [rsp+78h+arg_0]
0x14000afba  add     rsp, 40h
0x14000afbe  pop     r15
0x14000afc0  pop     r14
0x14000afc2  pop     r13
0x14000afc4  pop     r12
0x14000afc6  pop     rdi
0x14000afc7  pop     rsi
0x14000afc8  pop     rbp
0x14000afc9  retn
0x14000afcb  mov     rdi, [rsp+78h+P]
0x14000afd3  test    rdi, rdi
0x14000afd6  jz      short loc_14000AFB0
0x14000afd8  mov     rcx, rdi; this
0x14000afdb  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x14000afe0  mov     edx, 6E6D7377h; Tag
0x14000afe5  mov     rcx, rdi; P
0x14000afe8  call    cs:__imp_ExFreePoolWithTag
0x14000afef  nop     dword ptr [rax+rax+00h]
0x14000aff4  jmp     short loc_14000AFB0
0x14000aff6  mov     eax, 0C000009Ah
0x14000affb  jmp     short loc_14000AFB2
```
