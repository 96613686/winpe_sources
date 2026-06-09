# CWsmTrackingConfig::CTrackingPathInfo::deserialize(read_buffer_aligned &)

- ea: `0x14000cad0`
- end: `0x14000cdad`
- name: `?deserialize@CTrackingPathInfo@CWsmTrackingConfig@@UEAAJAEAVread_buffer_aligned@@@Z`
- size: `733`
- prototype: `__int64 __fastcall(CWsmTrackingConfig::CTrackingPathInfo *__hidden this, struct read_buffer_aligned *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x140008b58`
- `0x140008c08`
- `0x140009120`
- `0x140009368`
- `0x14000b414`
- `0x14000cad0`
- `0x14000d0a8`
- `0x14000d174`
- `0x14000f9e0`
- `0x14000fa40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000cc6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ccb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cd1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cd73`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cc6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ccb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cd1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cd73`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::CTrackingPathInfo::deserialize(
        CWsmTrackingConfig::CTrackingPathInfo *this,
        struct read_buffer_aligned *a2)
{
  __int64 result; // rax
  __int64 *v5; // rax
  __int64 v6; // rcx
  unsigned int v7; // edx
  unsigned int v8; // eax
  unsigned int v9; // ecx
  unsigned int v10; // r8d
  int v11; // edi
  unsigned int v12; // edi
  int v13; // edi
  unsigned int v14; // eax
  __int64 *v15; // r12
  __int64 *v16; // r15
  __int64 v17; // rbp
  _QWORD *v18; // rdi
  const struct std::nothrow_t *v19; // rdx
  char *v20; // rax
  CWsmTrackingConfig::CTrackingOverrideInfo *v21; // r14
  __int64 v22; // rax
  PVOID v23; // rdx
  CWsmTrackingConfig::CTrackingOverrideInfo *v24; // rdi
  __int64 v25; // rcx
  __int64 v26; // rax
  __int128 v27; // xmm0
  __int64 v28; // xmm1_8
  __int64 v29; // rcx
  PVOID v30; // r14
  __int64 v31; // rax
  PVOID v32; // rbx
  CWsmTrackingConfig::CTrackingOverrideInfo *v33; // [rsp+20h] [rbp-48h] BYREF
  CWsmTrackingConfig::CTrackingOverrideInfo **v34; // [rsp+28h] [rbp-40h]
  PVOID P; // [rsp+70h] [rbp+8h] BYREF

  CWsmTrackingConfig::CTrackingPathInfo::Release(this);
  result = (*(__int64 (__fastcall **)(char *, struct read_buffer_aligned *))(*((_QWORD *)this + 4) + 8LL))(
             (char *)this + 32,
             a2);
  if ( (int)result < 0 )
    return result;
  v5 = (__int64 *)*((_QWORD *)this + 5);
  if ( v5 )
    v6 = *v5;
  else
    v6 = 0;
  *((_QWORD *)this + 9) = v6;
  v7 = *((_DWORD *)a2 + 3);
  if ( (v7 & 3) != 0 )
  {
    v8 = v7 + (*((_DWORD *)a2 + 3) & 3);
    v9 = -1;
    if ( v8 >= v7 )
      v9 = v7 + (*((_DWORD *)a2 + 3) & 3);
    v10 = v8 < v7 ? 0xC0000095 : 0;
    if ( v8 < v7 )
      return v10;
    *((_DWORD *)a2 + 3) = v9;
  }
  else
  {
    v9 = *((_DWORD *)a2 + 3);
  }
  v11 = *((_DWORD *)a2 + 2);
  if ( v9 == v11 )
    return (unsigned int)-2147483614;
  v12 = v11 - v9;
  if ( v12 >= 4 )
    v12 = 4;
  memmove((char *)this + 80, (const void *)(*(_QWORD *)a2 + v9), v12);
  *((_DWORD *)a2 + 3) += v12;
  result = read_buffer_aligned::read<unsigned long>(a2, (char *)this + 84);
  v13 = result;
  if ( (int)result >= 0 )
  {
    v14 = *((_DWORD *)this + 21);
    if ( !v14 )
      return (unsigned int)v13;
    v15 = (__int64 *)((char *)this + 8);
    if ( (unsigned __int8)utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>::resize(
                            (char *)this + 8,
                            v14) )
    {
      v16 = (__int64 *)((char *)this + 48);
      if ( (unsigned __int8)utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(
                              (char *)this + 48,
                              *((unsigned int *)this + 21)) )
      {
        v17 = 0;
        if ( *((_DWORD *)this + 21) )
        {
          while ( 1 )
          {
            P = 0;
            v18 = (_QWORD *)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,>(
                              &v33,
                              &P);
            v20 = (char *)operator new(0x40u, v19);
            if ( v20 )
            {
              *(_QWORD *)v20 = &CWsmTrackingConfig::CTrackingOverrideInfo::`vftable';
              *((_QWORD *)v20 + 1) = &wsm_stable_path::`vftable';
              *((_QWORD *)v20 + 2) = 0;
              *((_QWORD *)v20 + 3) = &wsm_wstring::`vftable';
              *((_QWORD *)v20 + 4) = 0;
              *(_OWORD *)(v20 + 40) = 0;
              *((_QWORD *)v20 + 7) = 0;
              *v18 = v20;
              v13 = 0;
            }
            else
            {
              v13 = -1073741670;
            }
            if ( v33 )
            {
              v21 = *v34;
              *v34 = v33;
              if ( v21 )
              {
                CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(v21);
                ExFreePoolWithTag(v21, 0x6E6D7377u);
              }
            }
            if ( v13 < 0 )
              break;
            v22 = *v15;
            v23 = P;
            P = 0;
            v24 = *(CWsmTrackingConfig::CTrackingOverrideInfo **)(v22 + 8 * v17);
            *(_QWORD *)(v22 + 8 * v17) = v23;
            if ( v24 )
            {
              CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(v24);
              ExFreePoolWithTag(v24, 0x6E6D7377u);
            }
            v13 = (*(__int64 (__fastcall **)(_QWORD, struct read_buffer_aligned *))(**(_QWORD **)(*v15 + 8 * v17) + 8LL))(
                    *(_QWORD *)(*v15 + 8 * v17),
                    a2);
            if ( v13 < 0 )
              break;
            v25 = *(_QWORD *)(*v15 + 8 * v17);
            v26 = *v16;
            v27 = *(_OWORD *)(v25 + 40);
            v28 = *(_QWORD *)(v25 + 56);
            v29 = 3 * v17;
            *(_OWORD *)(v26 + 8 * v29) = v27;
            *(_QWORD *)(v26 + 8 * v29 + 16) = v28;
            v30 = P;
            if ( P )
            {
              CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo((CWsmTrackingConfig::CTrackingOverrideInfo *)P);
              ExFreePoolWithTag(v30, 0x6E6D7377u);
            }
            v17 = (unsigned int)(v17 + 1);
            if ( (unsigned int)v17 >= *((_DWORD *)this + 21) )
              goto LABEL_32;
          }
          v32 = P;
          if ( P )
          {
            CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo((CWsmTrackingConfig::CTrackingOverrideInfo *)P);
            ExFreePoolWithTag(v32, 0x6E6D7377u);
          }
        }
        else
        {
LABEL_32:
          v31 = *((_QWORD *)this + 7) - *((_QWORD *)this + 6);
          *((_QWORD *)this + 11) = *v16;
          *((_DWORD *)this + 21) = -1431655765 * (v31 >> 3);
        }
        return (unsigned int)v13;
      }
    }
    return 3221225626LL;
  }
  return result;
}

```

## disassembly

```asm
0x14000cad0  mov     [rsp+arg_8], rbx
0x14000cad5  mov     [rsp+arg_10], rbp
0x14000cada  push    rsi
0x14000cadb  push    rdi
0x14000cadc  push    r12
0x14000cade  push    r14
0x14000cae0  push    r15
0x14000cae2  sub     rsp, 40h
0x14000cae6  mov     rsi, rdx
0x14000cae9  mov     rbx, rcx
0x14000caec  call    ?Release@CTrackingPathInfo@CWsmTrackingConfig@@IEAAXXZ; CWsmTrackingConfig::CTrackingPathInfo::Release(void)
0x14000caf1  lea     rcx, [rbx+20h]
0x14000caf5  mov     rdx, rsi
0x14000caf8  mov     rax, [rcx]
0x14000cafb  mov     rax, [rax+8]
0x14000caff  call    _guard_dispatch_icall
0x14000cb04  test    eax, eax
0x14000cb06  js      loc_14000CD93
0x14000cb0c  mov     rax, [rbx+28h]
0x14000cb10  test    rax, rax
0x14000cb13  jz      short loc_14000CB1A
0x14000cb15  mov     rcx, [rax]
0x14000cb18  jmp     short loc_14000CB1C
0x14000cb1a  xor     ecx, ecx
0x14000cb1c  mov     [rbx+48h], rcx
0x14000cb20  mov     edx, [rsi+0Ch]
0x14000cb23  mov     eax, edx
0x14000cb25  and     eax, 3
0x14000cb28  jz      short loc_14000CB4B
0x14000cb2a  add     eax, edx
0x14000cb2c  or      ecx, 0FFFFFFFFh
0x14000cb2f  cmp     eax, edx
0x14000cb31  cmovnb  ecx, eax
0x14000cb34  sbb     r8d, r8d
0x14000cb37  and     r8d, 0C0000095h
0x14000cb3e  cmp     eax, edx
0x14000cb40  jb      loc_14000CD90
0x14000cb46  mov     [rsi+0Ch], ecx
0x14000cb49  jmp     short loc_14000CB4D
0x14000cb4b  mov     ecx, edx
0x14000cb4d  mov     edi, [rsi+8]
0x14000cb50  cmp     ecx, edi
0x14000cb52  jz      loc_14000CD8A
0x14000cb58  sub     edi, ecx
0x14000cb5a  mov     edx, ecx
0x14000cb5c  mov     eax, 4
0x14000cb61  lea     rcx, [rbx+50h]; void *
0x14000cb65  cmp     edi, eax
0x14000cb67  cmovnb  edi, eax
0x14000cb6a  add     rdx, [rsi]; Src
0x14000cb6d  mov     r8d, edi; Size
0x14000cb70  call    memmove
0x14000cb75  add     [rsi+0Ch], edi
0x14000cb78  lea     rdx, [rbx+54h]
0x14000cb7c  mov     rcx, rsi
0x14000cb7f  call    ??$read@K@read_buffer_aligned@@QEAAJAEAK@Z; read_buffer_aligned::read<ulong>(ulong &)
0x14000cb84  mov     edi, eax
0x14000cb86  test    eax, eax
0x14000cb88  js      loc_14000CD93
0x14000cb8e  mov     eax, [rbx+54h]
0x14000cb91  test    eax, eax
0x14000cb93  jz      loc_14000CD7F
0x14000cb99  lea     r12, [rbx+8]
0x14000cb9d  mov     edx, eax
0x14000cb9f  mov     rcx, r12
0x14000cba2  call    ?resize@?$vector@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@2@@utl@@QEAA_N_K@Z; utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>::resize(unsigned __int64)
0x14000cba7  test    al, al
0x14000cba9  jz      loc_14000CD83
0x14000cbaf  mov     edx, [rbx+54h]
0x14000cbb2  lea     r15, [rbx+30h]
0x14000cbb6  mov     rcx, r15
0x14000cbb9  call    ?resize@?$vector@U_WSM_TRACKING_PATH_INFO@@V?$allocator@U_WSM_TRACKING_PATH_INFO@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(unsigned __int64)
0x14000cbbe  test    al, al
0x14000cbc0  jz      loc_14000CD83
0x14000cbc6  xor     ebp, ebp
0x14000cbc8  cmp     [rbx+54h], ebp
0x14000cbcb  jbe     loc_14000CD34
0x14000cbd1  lea     rdx, [rsp+68h+P]
0x14000cbd6  mov     [rsp+68h+P], 0
0x14000cbdf  lea     rcx, [rsp+68h+var_48]
0x14000cbe4  call    ??$out_ptr@XV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@0@@Z
0x14000cbe9  mov     ecx, 40h ; '@'; NumberOfBytes
0x14000cbee  mov     rdi, rax
0x14000cbf1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000cbf6  test    rax, rax
0x14000cbf9  jz      short loc_14000CC3F
0x14000cbfb  lea     rcx, ??_7CTrackingOverrideInfo@CWsmTrackingConfig@@6B@; const CWsmTrackingConfig::CTrackingOverrideInfo::`vftable'
0x14000cc02  xorps   xmm0, xmm0
0x14000cc05  mov     [rax], rcx
0x14000cc08  lea     rcx, ??_7wsm_stable_path@@6B@; const wsm_stable_path::`vftable'
0x14000cc0f  mov     [rax+8], rcx
0x14000cc13  lea     rcx, ??_7wsm_wstring@@6B@; const wsm_wstring::`vftable'
0x14000cc1a  mov     qword ptr [rax+10h], 0
0x14000cc22  mov     [rax+18h], rcx
0x14000cc26  xor     ecx, ecx
0x14000cc28  mov     qword ptr [rax+20h], 0
0x14000cc30  movups  xmmword ptr [rax+28h], xmm0
0x14000cc34  mov     [rax+38h], rcx
0x14000cc38  mov     [rdi], rax
0x14000cc3b  xor     edi, edi
0x14000cc3d  jmp     short loc_14000CC44
0x14000cc3f  mov     edi, 0C000009Ah
0x14000cc44  mov     rcx, [rsp+68h+var_48]
0x14000cc49  test    rcx, rcx
0x14000cc4c  jz      short loc_14000CC7A
0x14000cc4e  mov     rax, [rsp+68h+var_40]
0x14000cc53  mov     r14, [rax]
0x14000cc56  mov     [rax], rcx
0x14000cc59  test    r14, r14
0x14000cc5c  jz      short loc_14000CC7A
0x14000cc5e  mov     rcx, r14; this
0x14000cc61  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x14000cc66  mov     edx, 6E6D7377h; Tag
0x14000cc6b  mov     rcx, r14; P
0x14000cc6e  call    cs:__imp_ExFreePoolWithTag
0x14000cc75  nop     dword ptr [rax+rax+00h]
0x14000cc7a  test    edi, edi
0x14000cc7c  js      loc_14000CD59
0x14000cc82  mov     rax, [r12]
0x14000cc86  mov     rdx, [rsp+68h+P]
0x14000cc8b  mov     [rsp+68h+P], 0
0x14000cc94  mov     rdi, [rax+rbp*8]
0x14000cc98  mov     [rax+rbp*8], rdx
0x14000cc9c  test    rdi, rdi
0x14000cc9f  jz      short loc_14000CCBD
0x14000cca1  mov     rcx, rdi; this
0x14000cca4  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x14000cca9  mov     edx, 6E6D7377h; Tag
0x14000ccae  mov     rcx, rdi; P
0x14000ccb1  call    cs:__imp_ExFreePoolWithTag
0x14000ccb8  nop     dword ptr [rax+rax+00h]
0x14000ccbd  mov     rax, [r12]
0x14000ccc1  mov     rdx, rsi
0x14000ccc4  mov     rcx, [rax+rbp*8]
0x14000ccc8  mov     rax, [rcx]
0x14000cccb  mov     rax, [rax+8]
0x14000cccf  call    _guard_dispatch_icall
0x14000ccd4  mov     edi, eax
0x14000ccd6  test    eax, eax
0x14000ccd8  js      short loc_14000CD59
0x14000ccda  mov     rax, [r12]
0x14000ccde  mov     rcx, [rax+rbp*8]
0x14000cce2  mov     rax, [r15]
0x14000cce5  movups  xmm0, xmmword ptr [rcx+28h]
0x14000cce9  movsd   xmm1, qword ptr [rcx+38h]
0x14000ccee  lea     rcx, ds:0[rbp*2]
0x14000ccf6  add     rcx, rbp
0x14000ccf9  movups  xmmword ptr [rax+rcx*8], xmm0
0x14000ccfd  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x14000cd03  mov     r14, [rsp+68h+P]
0x14000cd08  test    r14, r14
0x14000cd0b  jz      short loc_14000CD29
0x14000cd0d  mov     rcx, r14; this
0x14000cd10  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x14000cd15  mov     edx, 6E6D7377h; Tag
0x14000cd1a  mov     rcx, r14; P
0x14000cd1d  call    cs:__imp_ExFreePoolWithTag
0x14000cd24  nop     dword ptr [rax+rax+00h]
0x14000cd29  inc     ebp
0x14000cd2b  cmp     ebp, [rbx+54h]
0x14000cd2e  jb      loc_14000CBD1
0x14000cd34  mov     rcx, [r15]
0x14000cd37  mov     rdx, 0AAAAAAAAAAAAAAABh
0x14000cd41  mov     rax, [r15+8]
0x14000cd45  sub     rax, rcx
0x14000cd48  mov     [rbx+58h], rcx
0x14000cd4c  sar     rax, 3
0x14000cd50  imul    rax, rdx
0x14000cd54  mov     [rbx+54h], eax
0x14000cd57  jmp     short loc_14000CD7F
0x14000cd59  mov     rbx, [rsp+68h+P]
0x14000cd5e  test    rbx, rbx
0x14000cd61  jz      short loc_14000CD7F
0x14000cd63  mov     rcx, rbx; this
0x14000cd66  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x14000cd6b  mov     edx, 6E6D7377h; Tag
0x14000cd70  mov     rcx, rbx; P
0x14000cd73  call    cs:__imp_ExFreePoolWithTag
0x14000cd7a  nop     dword ptr [rax+rax+00h]
0x14000cd7f  mov     eax, edi
0x14000cd81  jmp     short loc_14000CD93
0x14000cd83  mov     eax, 0C000009Ah
0x14000cd88  jmp     short loc_14000CD93
0x14000cd8a  mov     r8d, 80000022h
0x14000cd90  mov     eax, r8d
0x14000cd93  lea     r11, [rsp+68h+var_28]
0x14000cd98  mov     rbx, [r11+38h]
0x14000cd9c  mov     rbp, [r11+40h]
0x14000cda0  mov     rsp, r11
0x14000cda3  pop     r15
0x14000cda5  pop     r14
0x14000cda7  pop     r12
0x14000cda9  pop     rdi
0x14000cdaa  pop     rsi
0x14000cdab  retn
```
