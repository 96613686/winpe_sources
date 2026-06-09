# CSamPropStore::_CopyGroupMembersFromCache(ushort * * *,ulong *,int *)

- ea: `0x180015d30`
- end: `0x1800161e2`
- name: `?_CopyGroupMembersFromCache@CSamPropStore@@AEAAJPEAPEAPEAGPEAKPEAH@Z`
- size: `1202`
- prototype: `int(CSamPropStore *__hidden this, unsigned __int16 ***, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014d90`

## callees

- `0x180005d80`
- `0x1800087b0`
- `0x18000c240`
- `0x180012f18`
- `0x180015d30`
- `0x1800164c8`
- `0x180017010`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x180015ec6`
- `SHCORE!SHStrDupW` at `0x180015fd4`
- `SHCORE!SHStrDupW` at `0x180016075`
- `SHCORE!SHStrDupW` at `0x180016126`
- `SHCORE!SHStrDupW` at `0x180016164`
- `SHCORE!SHStrDupW` at `0x180015ec6`
- `SHCORE!SHStrDupW` at `0x180015fd4`
- `SHCORE!SHStrDupW` at `0x180016075`
- `SHCORE!SHStrDupW` at `0x180016126`
- `SHCORE!SHStrDupW` at `0x180016164`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016100`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001613e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016100`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001613e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015fe1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016133`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016185`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180015fe1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016133`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016185`

## pseudocode

```c
__int64 __fastcall CSamPropStore::_CopyGroupMembersFromCache(
        CSamPropStore *this,
        unsigned __int16 ***a2,
        unsigned int *a3,
        int *a4)
{
  unsigned int v4; // r13d
  __int64 v6; // rcx
  unsigned int *v7; // r15
  HRESULT v9; // ebx
  unsigned int v10; // r14d
  void *v11; // rcx
  unsigned int v12; // r9d
  unsigned __int64 v13; // r15
  void *v14; // rcx
  unsigned __int64 v15; // r9
  int v16; // eax
  __int64 (__fastcall ***v17)(_QWORD, GUID *, unsigned __int64 *); // rcx
  CSamPropStore *v18; // rcx
  unsigned int v19; // r9d
  void *v20; // rcx
  unsigned int v21; // r9d
  unsigned __int16 **v22; // rax
  const unsigned __int16 *v23; // rdx
  CSamPropStore *v24; // rcx
  unsigned int v25; // r9d
  unsigned __int16 **v26; // rax
  const unsigned __int16 *v27; // rdx
  CSamPropStore *v28; // rcx
  unsigned int v29; // r9d
  unsigned __int64 v31; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v32; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int *v33; // [rsp+30h] [rbp-D0h] BYREF
  PROPVARIANT v34[2]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v35; // [rsp+48h] [rbp-B8h]
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h]
  WCHAR psz[280]; // [rsp+70h] [rbp-90h] BYREF

  v4 = 0;
  v33 = a3;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v6 = *((_QWORD *)this + 12);
  v7 = a3;
  v35 = 0;
  v9 = 0;
  *(_OWORD *)v34 = 0;
  if ( v6 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v6 + 40LL))(
           v6,
           &PKEY_SAM_GroupMembers,
           v34);
    if ( v9 >= 0 )
    {
      if ( !LOWORD(v34[0]) )
      {
        *a4 = 0;
        *v7 = 0;
        goto LABEL_53;
      }
      if ( LOWORD(v34[0]) != 8 )
      {
        if ( LOWORD(v34[0]) == 13 )
        {
          v33 = 0;
          v9 = (**(__int64 (__fastcall ***)(PROPVARIANT, GUID *, unsigned int **))v34[1])(
                 v34[1],
                 &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                 &v33);
          if ( v9 >= 0 )
          {
            v37 = 0;
            *(_OWORD *)pvar = 0;
            v9 = (*(__int64 (__fastcall **)(unsigned int *, __int128 *, PROPVARIANT *))(*(_QWORD *)v33 + 40LL))(
                   v33,
                   &PKEY_SAM_Name,
                   pvar);
            if ( v9 >= 0 )
            {
              v22 = (unsigned __int16 **)CoTaskMemAlloc(8u);
              v23 = (const unsigned __int16 *)pvar[1];
              *a2 = v22;
              v9 = CSamPropStore::_QualifyName(v24, v23, psz, v25);
              if ( v9 >= 0 )
                v9 = SHStrDupW(psz, *a2);
              PropVariantClear(pvar);
            }
          }
          goto LABEL_51;
        }
        if ( LOWORD(v34[0]) != 31 )
        {
          switch ( LOWORD(v34[0]) )
          {
            case 0x1008u:
              v10 = (unsigned int)v34[1];
              v31 = v35;
              *a2 = 0;
              if ( !v10 )
                goto LABEL_43;
              v32 = 0;
              v9 = ULongLongMult(v10, 8u, &v32);
              if ( v9 >= 0 )
                v9 = CTCoAllocPolicy::Alloc(v20, 1u, v32, (void **)a2);
              if ( v9 < 0 )
                goto LABEL_43;
              do
              {
                v9 = CSamPropStore::_QualifyName(
                       (CSamPropStore *)v20,
                       *(const unsigned __int16 **)(v31 + 8LL * v4),
                       psz,
                       v21);
                if ( v9 < 0 )
                  break;
                v9 = SHStrDupW(psz, &(*a2)[v4]);
                if ( v9 < 0 )
                  break;
                ++v4;
              }
              while ( v4 < v10 );
              break;
            case 0x100Cu:
              v10 = (unsigned int)v34[1];
              v32 = v35;
              *a2 = 0;
              if ( v10 )
              {
                v31 = 0;
                v9 = ULongLongMult(v10, 8u, &v31);
                if ( v9 >= 0 )
                {
                  v16 = CTCoAllocPolicy::Alloc(v14, 1u, v31, (void **)a2);
                  v15 = v32;
                  v9 = v16;
                }
                if ( v9 >= 0 )
                {
                  while ( v4 < v10 )
                  {
                    if ( *(_WORD *)(v15 + 24LL * v4) != 13 )
                    {
                      v9 = -2147024809;
                      goto LABEL_43;
                    }
                    v17 = *(__int64 (__fastcall ****)(_QWORD, GUID *, unsigned __int64 *))(v15 + 24LL * v4 + 8);
                    v31 = 0;
                    v9 = (**v17)(v17, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v31);
                    if ( v9 >= 0 )
                    {
                      v37 = 0;
                      *(_OWORD *)pvar = 0;
                      v9 = (*(__int64 (__fastcall **)(unsigned __int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v31 + 40LL))(
                             v31,
                             &PKEY_SAM_Name,
                             pvar);
                      if ( v9 >= 0 )
                      {
                        v9 = CSamPropStore::_QualifyName(v18, (const unsigned __int16 *)pvar[1], psz, v19);
                        if ( v9 >= 0 )
                          v9 = SHStrDupW(psz, &(*a2)[v4]);
                        PropVariantClear(pvar);
                      }
                    }
                    v15 = v32;
                    ++v4;
                  }
                }
              }
              goto LABEL_43;
            case 0x101Fu:
              v10 = (unsigned int)v34[1];
              v32 = v35;
              *a2 = 0;
              if ( !v10 )
                goto LABEL_43;
              v31 = 0;
              v9 = ULongLongMult(v10, 8u, &v31);
              if ( v9 >= 0 )
                v9 = CTCoAllocPolicy::Alloc(v11, 1u, v31, (void **)a2);
              if ( v9 < 0 )
                goto LABEL_43;
              v13 = v32;
              do
              {
                v9 = CSamPropStore::_QualifyName(
                       (CSamPropStore *)v11,
                       *(const unsigned __int16 **)(v13 + 8LL * v4),
                       psz,
                       v12);
                if ( v9 < 0 )
                  break;
                v9 = SHStrDupW(psz, &(*a2)[v4]);
                if ( v9 < 0 )
                  break;
                ++v4;
              }
              while ( v4 < v10 );
              break;
            default:
              v9 = -2147024809;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  22,
                  WPP_7df418057efb386bc095915f6151cd01_Traceguids,
                  LOWORD(v34[0]));
              }
              goto LABEL_53;
          }
          v7 = v33;
LABEL_43:
          *a4 = 1;
          *v7 = v10;
LABEL_53:
          PropVariantClear(v34);
          return (unsigned int)v9;
        }
      }
      v26 = (unsigned __int16 **)CoTaskMemAlloc(8u);
      v27 = (const unsigned __int16 *)v34[1];
      *a2 = v26;
      v9 = CSamPropStore::_QualifyName(v28, v27, psz, v29);
      if ( v9 >= 0 )
        v9 = SHStrDupW(psz, *a2);
LABEL_51:
      *a4 = 0;
      *v7 = 1;
      goto LABEL_53;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_7df418057efb386bc095915f6151cd01_Traceguids,
        (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180015d30  push    rbp
0x180015d32  push    rbx
0x180015d33  push    rsi
0x180015d34  push    r12
0x180015d36  push    r13
0x180015d38  push    r14
0x180015d3a  push    r15
0x180015d3c  lea     rbp, [rsp-1B0h]
0x180015d44  sub     rsp, 2B0h
0x180015d4b  mov     rax, cs:__security_cookie
0x180015d52  xor     rax, rsp
0x180015d55  mov     [rbp+1E0h+var_40], rax
0x180015d5c  xor     r13d, r13d
0x180015d5f  mov     [rsp+2E0h+var_2B0], r8
0x180015d64  mov     [rdx], r13
0x180015d67  xor     eax, eax
0x180015d69  mov     [r8], r13d
0x180015d6c  xorps   xmm0, xmm0
0x180015d6f  mov     [r9], r13d
0x180015d72  mov     r12, r9
0x180015d75  mov     rcx, [rcx+60h]
0x180015d79  mov     r15, r8
0x180015d7c  mov     [rsp+2E0h+var_298], rax
0x180015d81  mov     rsi, rdx
0x180015d84  mov     ebx, r13d
0x180015d87  movups  xmmword ptr [rsp+2E0h+var_2A8], xmm0
0x180015d8c  test    rcx, rcx
0x180015d8f  jz      loc_1800161BE
0x180015d95  mov     rax, [rcx]
0x180015d98  lea     r8, [rsp+2E0h+var_2A8]
0x180015d9d  lea     rdx, PKEY_SAM_GroupMembers
0x180015da4  mov     rax, [rax+28h]
0x180015da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dad  mov     ebx, eax
0x180015daf  test    eax, eax
0x180015db1  js      loc_18001618D
0x180015db7  movzx   r9d, word ptr [rsp+2E0h+var_2A8]
0x180015dbd  mov     eax, r9d
0x180015dc0  test    r9d, r9d
0x180015dc3  jz      loc_180016179
0x180015dc9  lea     edx, [r13+8]; unsigned __int64
0x180015dcd  sub     eax, edx
0x180015dcf  jz      loc_18001613B
0x180015dd5  sub     eax, 5
0x180015dd8  jz      loc_18001609E
0x180015dde  sub     eax, 12h
0x180015de1  jz      loc_18001613B
0x180015de7  sub     eax, 0FE9h
0x180015dec  jz      loc_180015FFE
0x180015df2  sub     eax, 4
0x180015df5  jz      loc_180015EE3
0x180015dfb  cmp     eax, 13h
0x180015dfe  jz      short loc_180015E3F
0x180015e00  mov     ebx, 80070057h
0x180015e05  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e0c  lea     rax, WPP_GLOBAL_Control
0x180015e13  cmp     rcx, rax
0x180015e16  jz      loc_180016180
0x180015e1c  test    byte ptr [rcx+1Ch], 4
0x180015e20  jz      loc_180016180
0x180015e26  mov     rcx, [rcx+10h]
0x180015e2a  lea     edx, [r13+16h]
0x180015e2e  lea     r8, WPP_7df418057efb386bc095915f6151cd01_Traceguids
0x180015e35  call    WPP_SF_d
0x180015e3a  jmp     loc_180016180
0x180015e3f  mov     r14d, dword ptr [rsp+2E0h+var_2A8+8]
0x180015e44  mov     rax, [rsp+2E0h+var_298]
0x180015e49  mov     [rsp+2E0h+var_2B8], rax
0x180015e4e  mov     [rsi], r13
0x180015e51  test    r14d, r14d
0x180015e54  jz      loc_18001608E
0x180015e5a  mov     ecx, r14d; unsigned __int64
0x180015e5d  mov     [rsp+2E0h+var_2C0], r13
0x180015e62  lea     r8, [rsp+2E0h+var_2C0]; unsigned __int64 *
0x180015e67  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180015e6c  mov     ebx, eax
0x180015e6e  test    eax, eax
0x180015e70  js      short loc_180015E86
0x180015e72  mov     r8, [rsp+2E0h+var_2C0]; unsigned __int64
0x180015e77  mov     r9, rsi; void **
0x180015e7a  mov     edx, 1; unsigned int
0x180015e7f  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180015e84  mov     ebx, eax
0x180015e86  test    ebx, ebx
0x180015e88  js      loc_18001608E
0x180015e8e  test    r14d, r14d
0x180015e91  jz      loc_18001608E
0x180015e97  mov     r15, [rsp+2E0h+var_2B8]
0x180015e9c  mov     eax, r13d
0x180015e9f  lea     r8, [rsp+2E0h+psz]; unsigned __int16 *
0x180015ea4  mov     rdx, [r15+rax*8]; unsigned __int16 *
0x180015ea8  call    ?_QualifyName@CSamPropStore@@AEAAJPEBGPEAGK@Z; CSamPropStore::_QualifyName(ushort const *,ushort *,ulong)
0x180015ead  mov     ebx, eax
0x180015eaf  test    eax, eax
0x180015eb1  js      loc_180016089
0x180015eb7  mov     rax, [rsi]
0x180015eba  mov     ecx, r13d
0x180015ebd  lea     rdx, [rax+rcx*8]; ppwsz
0x180015ec1  lea     rcx, [rsp+2E0h+psz]; psz
0x180015ec6  call    cs:__imp_SHStrDupW
0x180015ecc  mov     ebx, eax
0x180015ece  test    eax, eax
0x180015ed0  js      loc_180016089
0x180015ed6  inc     r13d
0x180015ed9  cmp     r13d, r14d
0x180015edc  jb      short loc_180015E9C
0x180015ede  jmp     loc_180016089
0x180015ee3  mov     r14d, dword ptr [rsp+2E0h+var_2A8+8]
0x180015ee8  mov     r9, [rsp+2E0h+var_298]
0x180015eed  mov     [rsp+2E0h+var_2B8], r9
0x180015ef2  mov     [rsi], r13
0x180015ef5  test    r14d, r14d
0x180015ef8  jz      loc_18001608E
0x180015efe  mov     ecx, r14d; unsigned __int64
0x180015f01  mov     [rsp+2E0h+var_2C0], r13
0x180015f06  lea     r8, [rsp+2E0h+var_2C0]; unsigned __int64 *
0x180015f0b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180015f10  mov     ebx, eax
0x180015f12  test    eax, eax
0x180015f14  js      short loc_180015F2F
0x180015f16  mov     r8, [rsp+2E0h+var_2C0]; unsigned __int64
0x180015f1b  mov     r9, rsi; void **
0x180015f1e  mov     edx, 1; unsigned int
0x180015f23  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180015f28  mov     r9, [rsp+2E0h+var_2B8]
0x180015f2d  mov     ebx, eax
0x180015f2f  test    ebx, ebx
0x180015f31  js      loc_18001608E
0x180015f37  cmp     r13d, r14d
0x180015f3a  jnb     loc_18001608E
0x180015f40  mov     eax, r13d
0x180015f43  lea     rcx, [rax+rax*2]
0x180015f47  cmp     word ptr [r9+rcx*8], 0Dh
0x180015f4d  jnz     loc_180015FF4
0x180015f53  mov     rcx, [r9+rcx*8+8]
0x180015f58  lea     r8, [rsp+2E0h+var_2C0]
0x180015f5d  mov     [rsp+2E0h+var_2C0], 0
0x180015f66  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180015f6d  mov     rax, [rcx]
0x180015f70  mov     rax, [rax]
0x180015f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f78  mov     ebx, eax
0x180015f7a  test    eax, eax
0x180015f7c  js      short loc_180015FE7
0x180015f7e  mov     rcx, [rsp+2E0h+var_2C0]
0x180015f83  lea     r8, [rsp+2E0h+pvar]
0x180015f88  xor     eax, eax
0x180015f8a  lea     rdx, PKEY_SAM_Name
0x180015f91  mov     [rsp+2E0h+var_280], rax
0x180015f96  xorps   xmm0, xmm0
0x180015f99  movups  xmmword ptr [rsp+2E0h+pvar], xmm0
0x180015f9e  mov     rax, [rcx]
0x180015fa1  mov     rax, [rax+28h]
0x180015fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015faa  mov     ebx, eax
0x180015fac  test    eax, eax
0x180015fae  js      short loc_180015FE7
0x180015fb0  mov     rdx, [rsp+2E0h+pvar+8]; unsigned __int16 *
0x180015fb5  lea     r8, [rsp+2E0h+psz]; unsigned __int16 *
0x180015fba  call    ?_QualifyName@CSamPropStore@@AEAAJPEBGPEAGK@Z; CSamPropStore::_QualifyName(ushort const *,ushort *,ulong)
0x180015fbf  mov     ebx, eax
0x180015fc1  test    eax, eax
0x180015fc3  js      short loc_180015FDC
0x180015fc5  mov     rax, [rsi]
0x180015fc8  mov     ecx, r13d
0x180015fcb  lea     rdx, [rax+rcx*8]; ppwsz
0x180015fcf  lea     rcx, [rsp+2E0h+psz]; psz
0x180015fd4  call    cs:__imp_SHStrDupW
0x180015fda  mov     ebx, eax
0x180015fdc  lea     rcx, [rsp+2E0h+pvar]; pvar
0x180015fe1  call    cs:__imp_PropVariantClear
0x180015fe7  mov     r9, [rsp+2E0h+var_2B8]
0x180015fec  inc     r13d
0x180015fef  jmp     loc_180015F37
0x180015ff4  mov     ebx, 80070057h
0x180015ff9  jmp     loc_18001608E
0x180015ffe  mov     r14d, dword ptr [rsp+2E0h+var_2A8+8]
0x180016003  mov     rax, [rsp+2E0h+var_298]
0x180016008  mov     [rsp+2E0h+var_2C0], rax
0x18001600d  mov     [rsi], r13
0x180016010  test    r14d, r14d
0x180016013  jz      short loc_18001608E
0x180016015  mov     ecx, r14d; unsigned __int64
0x180016018  mov     [rsp+2E0h+var_2B8], r13
0x18001601d  lea     r8, [rsp+2E0h+var_2B8]; unsigned __int64 *
0x180016022  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180016027  mov     ebx, eax
0x180016029  test    eax, eax
0x18001602b  js      short loc_180016041
0x18001602d  mov     r8, [rsp+2E0h+var_2B8]; unsigned __int64
0x180016032  mov     r9, rsi; void **
0x180016035  mov     edx, 1; unsigned int
0x18001603a  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18001603f  mov     ebx, eax
0x180016041  test    ebx, ebx
0x180016043  js      short loc_18001608E
0x180016045  test    r14d, r14d
0x180016048  jz      short loc_18001608E
0x18001604a  mov     r15, [rsp+2E0h+var_2C0]
0x18001604f  mov     eax, r13d
0x180016052  lea     r8, [rsp+2E0h+psz]; unsigned __int16 *
0x180016057  mov     rdx, [r15+rax*8]; unsigned __int16 *
0x18001605b  call    ?_QualifyName@CSamPropStore@@AEAAJPEBGPEAGK@Z; CSamPropStore::_QualifyName(ushort const *,ushort *,ulong)
0x180016060  mov     ebx, eax
0x180016062  test    eax, eax
0x180016064  js      short loc_180016089
0x180016066  mov     rax, [rsi]
0x180016069  mov     ecx, r13d
0x18001606c  lea     rdx, [rax+rcx*8]; ppwsz
0x180016070  lea     rcx, [rsp+2E0h+psz]; psz
0x180016075  call    cs:__imp_SHStrDupW
0x18001607b  mov     ebx, eax
0x18001607d  test    eax, eax
0x18001607f  js      short loc_180016089
0x180016081  inc     r13d
0x180016084  cmp     r13d, r14d
0x180016087  jb      short loc_18001604F
0x180016089  mov     r15, [rsp+2E0h+var_2B0]
0x18001608e  mov     dword ptr [r12], 1
0x180016096  mov     [r15], r14d
0x180016099  jmp     loc_180016180
0x18001609e  mov     rcx, [rsp+2E0h+var_2A8+8]
0x1800160a3  lea     r8, [rsp+2E0h+var_2B0]
0x1800160a8  mov     [rsp+2E0h+var_2B0], r13
0x1800160ad  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1800160b4  mov     rax, [rcx]
0x1800160b7  mov     rax, [rax]
0x1800160ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160bf  mov     ebx, eax
0x1800160c1  test    eax, eax
0x1800160c3  js      loc_18001616C
0x1800160c9  mov     rcx, [rsp+2E0h+var_2B0]
0x1800160ce  lea     r8, [rsp+2E0h+pvar]
0x1800160d3  xor     eax, eax
0x1800160d5  lea     rdx, PKEY_SAM_Name
0x1800160dc  mov     [rsp+2E0h+var_280], rax
0x1800160e1  xorps   xmm0, xmm0
0x1800160e4  movups  xmmword ptr [rsp+2E0h+pvar], xmm0
0x1800160e9  mov     rax, [rcx]
0x1800160ec  mov     rax, [rax+28h]
0x1800160f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160f5  mov     ebx, eax
0x1800160f7  test    eax, eax
0x1800160f9  js      short loc_18001616C
0x1800160fb  mov     ecx, 8; cb
0x180016100  call    cs:__imp_CoTaskMemAlloc
0x180016106  mov     rdx, [rsp+2E0h+pvar+8]; unsigned __int16 *
0x18001610b  lea     r8, [rsp+2E0h+psz]; unsigned __int16 *
0x180016110  mov     [rsi], rax
0x180016113  call    ?_QualifyName@CSamPropStore@@AEAAJPEBGPEAGK@Z; CSamPropStore::_QualifyName(ushort const *,ushort *,ulong)
0x180016118  mov     ebx, eax
0x18001611a  test    eax, eax
0x18001611c  js      short loc_18001612E
0x18001611e  mov     rdx, [rsi]; ppwsz
0x180016121  lea     rcx, [rsp+2E0h+psz]; psz
0x180016126  call    cs:__imp_SHStrDupW
0x18001612c  mov     ebx, eax
0x18001612e  lea     rcx, [rsp+2E0h+pvar]; pvar
0x180016133  call    cs:__imp_PropVariantClear
0x180016139  jmp     short loc_18001616C
0x18001613b  mov     rcx, rdx; cb
0x18001613e  call    cs:__imp_CoTaskMemAlloc
0x180016144  mov     rdx, [rsp+2E0h+var_2A8+8]; unsigned __int16 *
0x180016149  lea     r8, [rsp+2E0h+psz]; unsigned __int16 *
0x18001614e  mov     [rsi], rax
0x180016151  call    ?_QualifyName@CSamPropStore@@AEAAJPEBGPEAGK@Z; CSamPropStore::_QualifyName(ushort const *,ushort *,ulong)
0x180016156  mov     ebx, eax
0x180016158  test    eax, eax
0x18001615a  js      short loc_18001616C
0x18001615c  mov     rdx, [rsi]; ppwsz
0x18001615f  lea     rcx, [rsp+2E0h+psz]; psz
0x180016164  call    cs:__imp_SHStrDupW
0x18001616a  mov     ebx, eax
0x18001616c  mov     [r12], r13d
0x180016170  mov     dword ptr [r15], 1
0x180016177  jmp     short loc_180016180
0x180016179  mov     [r12], r13d
0x18001617d  mov     [r15], r13d
0x180016180  lea     rcx, [rsp+2E0h+var_2A8]; pvar
0x180016185  call    cs:__imp_PropVariantClear
0x18001618b  jmp     short loc_1800161BE
0x18001618d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016194  lea     rax, WPP_GLOBAL_Control
0x18001619b  cmp     rcx, rax
0x18001619e  jz      short loc_1800161BE
0x1800161a0  test    byte ptr [rcx+1Ch], 4
0x1800161a4  jz      short loc_1800161BE
0x1800161a6  mov     rcx, [rcx+10h]
0x1800161aa  lea     r8, WPP_7df418057efb386bc095915f6151cd01_Traceguids
0x1800161b1  mov     edx, 17h
0x1800161b6  mov     r9d, ebx
0x1800161b9  call    WPP_SF_d
0x1800161be  mov     eax, ebx
0x1800161c0  mov     rcx, [rbp+1E0h+var_40]
0x1800161c7  xor     rcx, rsp; StackCookie
0x1800161ca  call    __security_check_cookie
0x1800161cf  add     rsp, 2B0h
0x1800161d6  pop     r15
0x1800161d8  pop     r14
0x1800161da  pop     r13
  ... truncated ...
```
