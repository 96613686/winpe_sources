# udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::initializer_list_DXCoreHardwareIDParts___

- ea: `0x180028b88`
- end: `0x180028f39`
- name: `udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::initializer_list_DXCoreHardwareIDParts___`
- size: `945`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180029ef4`
- `0x18002b0b4`

## callees

- `0x1800038ac`
- `0x180005cc0`
- `0x18000f82c`
- `0x180028b88`
- `0x180029498`
- `0x18002c180`
- `0x18002c464`
- `0x180032010`

## import_xrefs

- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x180028c13`
- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x180028c13`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::initializer_list_DXCoreHardwareIDParts___(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // esi
  _DWORD *v6; // r13
  int v7; // eax
  _QWORD *v8; // r12
  _QWORD *i; // rdi
  unsigned __int128 v10; // kr00_16
  __int64 v11; // rax
  unsigned int v12; // r14d
  _DWORD *v13; // r12
  __int64 v14; // rax
  _DWORD *m; // rdx
  __int128 *n; // rcx
  _OWORD *v17; // r9
  _DWORD *j; // rdx
  __int64 *k; // rcx
  int v21; // [rsp+20h] [rbp-A9h]
  __int64 v22; // [rsp+30h] [rbp-99h] BYREF
  __int64 *v23; // [rsp+38h] [rbp-91h] BYREF
  __int64 *v24; // [rsp+40h] [rbp-89h] BYREF
  int v25; // [rsp+48h] [rbp-81h]
  __int64 *v26; // [rsp+50h] [rbp-79h] BYREF
  unsigned __int128 v27; // [rsp+58h] [rbp-71h] BYREF
  __int64 v28; // [rsp+68h] [rbp-61h]
  _DWORD *v29; // [rsp+70h] [rbp-59h]
  _QWORD *v30; // [rsp+78h] [rbp-51h]
  _QWORD *v31; // [rsp+80h] [rbp-49h]
  __int128 v32; // [rsp+88h] [rbp-41h] BYREF
  unsigned int v33; // [rsp+98h] [rbp-31h]
  char v34; // [rsp+9Ch] [rbp-2Dh] BYREF
  __int128 v35; // [rsp+A0h] [rbp-29h] BYREF
  __int128 v36; // [rsp+B0h] [rbp-19h] BYREF
  __int128 v37; // [rsp+C0h] [rbp-9h]
  __int64 v38; // [rsp+D0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v31 = a1;
  v5 = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v25 = 1;
  v6 = (_DWORD *)*a3;
  v29 = (_DWORD *)a3[1];
  v27 = 0;
  v28 = 0;
  v24 = DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU;
  std::vector<_GUID const *>::push_back(&v27, &v24);
  v26 = 0;
  v7 = DXCoreCreateAdapterFactory(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, &v26);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\npu_detection.h",
      (const char *)(unsigned int)v7,
      v21);
  v8 = (_QWORD *)*((_QWORD *)&v27 + 1);
  v10 = v27;
  v30 = (_QWORD *)(v10 >> 64);
  for ( i = (_QWORD *)v10; i != v8; ++i )
  {
    v23 = 0;
    v11 = *v26;
    v23 = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64, _QWORD, GUID *, __int64 **))(v11 + 24))(
           v26,
           1,
           *i,
           &GUID_526c7776_40e9_459b_b711_f32ad76dfc28,
           &v23) >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64 *))(*v23 + 32))(v23);
      if ( v12 )
      {
        v13 = v29;
        while ( 1 )
        {
          v22 = 0;
          v14 = *v23;
          v22 = 0;
          if ( (*(int (__fastcall **)(__int64 *, _QWORD, GUID *, __int64 *))(v14 + 24))(
                 v23,
                 v5,
                 &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e,
                 &v22) >= 0 )
          {
            if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 40LL))(v22, 11) )
            {
              v32 = 0;
              v33 = 0;
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 40LL))(v22, 14)
                && (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v22 + 48LL))(
                     v22,
                     14,
                     20,
                     &v32) >= 0 )
              {
                goto LABEL_14;
              }
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 40LL))(v22, 3) )
              {
                v35 = 0;
                if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v22 + 48LL))(
                       v22,
                       3,
                       16,
                       &v35) >= 0 )
                  break;
              }
            }
          }
LABEL_36:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
          if ( ++v5 >= v12 )
          {
            v8 = v30;
            v5 = 0;
            goto LABEL_38;
          }
        }
        *(_QWORD *)&v32 = v35;
        v33 = HIDWORD(v35);
        DWORD2(v32) = DWORD2(v35);
LABEL_14:
        v24 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 40LL))(v22, 1)
          && (*(int (__fastcall **)(__int64, __int64, __int64, __int64 **))(*(_QWORD *)v22 + 48LL))(v22, 1, 8, &v24) >= 0 )
        {
          v36 = v32;
          *(_QWORD *)&v37 = v33;
          *((_QWORD *)&v37 + 1) = v24;
          if ( v6 == v13 )
          {
LABEL_25:
            v17 = (_OWORD *)a1[1];
            for ( j = (_DWORD *)*a1; j != (_DWORD *)v17; j += 8 )
            {
              for ( k = (__int64 *)&v36; k != &v38; k += 4 )
              {
                if ( *j == *(_DWORD *)k && j[1] == *((_DWORD *)k + 1) )
                  goto LABEL_36;
              }
            }
            if ( v17 == (_OWORD *)a1[2] )
            {
              std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(
                a1,
                a1[1],
                &v36);
            }
            else
            {
              *v17 = v36;
              v17[1] = v37;
              a1[1] += 32LL;
            }
          }
          else
          {
            for ( m = (_DWORD *)*a3; m != (_DWORD *)a3[1]; m += 5 )
            {
              for ( n = &v32; n != (__int128 *)&v34; n = (__int128 *)((char *)n + 20) )
              {
                if ( *m == *(_DWORD *)n && m[1] == *((_DWORD *)n + 1) )
                  goto LABEL_25;
              }
            }
          }
        }
        goto LABEL_36;
      }
    }
LABEL_38:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  if ( (_QWORD)v27 )
    std::_Deallocate<16>(v27, (v28 - v27) & 0xFFFFFFFFFFFFFFF8uLL);
  return a1;
}

```

## disassembly

```asm
0x180028b88  push    rbp
0x180028b8a  push    rbx
0x180028b8b  push    rsi
0x180028b8c  push    rdi
0x180028b8d  push    r12
0x180028b8f  push    r13
0x180028b91  push    r14
0x180028b93  push    r15
0x180028b95  lea     rbp, [rsp-1Fh]
0x180028b9a  sub     rsp, 0E8h
0x180028ba1  mov     rax, cs:__security_cookie
0x180028ba8  xor     rax, rsp
0x180028bab  mov     [rbp+57h+var_50], rax
0x180028baf  mov     r15, r8
0x180028bb2  mov     rbx, rcx
0x180028bb5  mov     [rbp+57h+var_A0], rcx
0x180028bb9  xor     esi, esi
0x180028bbb  mov     [rsp+120h+var_D8], esi
0x180028bbf  mov     [rcx], rsi
0x180028bc2  mov     [rcx+8], rsi
0x180028bc6  mov     [rcx+10h], rsi
0x180028bca  mov     [rsp+120h+var_D8], 1
0x180028bd2  mov     r13, [r8]
0x180028bd5  mov     rax, [r8+8]
0x180028bd9  mov     [rbp+57h+var_B0], rax
0x180028bdd  xorps   xmm0, xmm0
0x180028be0  movdqu  [rbp+57h+var_C8], xmm0
0x180028be5  mov     [rbp+57h+var_B8], rsi
0x180028be9  lea     rax, DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU
0x180028bf0  mov     [rsp+120h+var_E0], rax
0x180028bf5  lea     rdx, [rsp+120h+var_E0]
0x180028bfa  lea     rcx, [rbp+57h+var_C8]
0x180028bfe  call    ?push_back@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAAX$$QEAPEBU_GUID@@@Z; std::vector<_GUID const *>::push_back(_GUID const * &&)
0x180028c03  nop
0x180028c04  mov     [rbp+57h+var_D0], rsi
0x180028c08  lea     rdx, [rbp+57h+var_D0]
0x180028c0c  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x180028c13  call    cs:__imp_DXCoreCreateAdapterFactory
0x180028c19  mov     rcx, [rbp+5Fh]; this
0x180028c1d  test    eax, eax
0x180028c1f  jns     short loc_180028C36
0x180028c21  mov     r9d, eax; char *
0x180028c24  lea     r8, aOnecoreInterna_3; "OneCore\\Internal\\Shell\\inc\\npu_dete"...
0x180028c2b  mov     edx, 17Dh; void *
0x180028c30  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180028c36  mov     rdi, qword ptr [rbp+57h+var_C8]
0x180028c3a  mov     r12, qword ptr [rbp+57h+var_C8+8]
0x180028c3e  mov     [rbp+57h+var_A8], r12
0x180028c42  jmp     loc_180028EE9
0x180028c47  mov     [rsp+120h+var_E8], rsi
0x180028c4c  mov     rcx, [rbp+57h+var_D0]
0x180028c50  mov     rax, [rcx]
0x180028c53  mov     [rsp+120h+var_E8], rsi
0x180028c58  lea     rdx, [rsp+120h+var_E8]
0x180028c5d  mov     qword ptr [rsp+120h+var_100], rdx
0x180028c62  lea     r9, _GUID_526c7776_40e9_459b_b711_f32ad76dfc28
0x180028c69  mov     r8, [rdi]
0x180028c6c  mov     edx, 1
0x180028c71  mov     rax, [rax+18h]
0x180028c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c7a  test    eax, eax
0x180028c7c  js      loc_180028EDB
0x180028c82  mov     rcx, [rsp+120h+var_E8]
0x180028c87  mov     rax, [rcx]
0x180028c8a  mov     rax, [rax+20h]
0x180028c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c93  mov     r14d, eax
0x180028c96  test    eax, eax
0x180028c98  jz      loc_180028EDB
0x180028c9e  test    eax, eax
0x180028ca0  jz      loc_180028ED9
0x180028ca6  mov     r12, [rbp+57h+var_B0]
0x180028caa  mov     [rsp+120h+var_F0], 0
0x180028cb3  mov     rcx, [rsp+120h+var_E8]
0x180028cb8  mov     rax, [rcx]
0x180028cbb  mov     [rsp+120h+var_F0], 0
0x180028cc4  lea     r9, [rsp+120h+var_F0]
0x180028cc9  lea     r8, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x180028cd0  mov     edx, esi
0x180028cd2  mov     rax, [rax+18h]
0x180028cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028cdb  test    eax, eax
0x180028cdd  js      loc_180028EC0
0x180028ce3  mov     rcx, [rsp+120h+var_F0]
0x180028ce8  mov     rax, [rcx]
0x180028ceb  mov     edx, 0Bh
0x180028cf0  mov     rax, [rax+28h]
0x180028cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028cf9  test    al, al
0x180028cfb  jz      loc_180028EC0
0x180028d01  xorps   xmm0, xmm0
0x180028d04  xor     eax, eax
0x180028d06  movups  [rbp+57h+var_98], xmm0
0x180028d0a  mov     [rbp+57h+var_88], eax
0x180028d0d  mov     rcx, [rsp+120h+var_F0]
0x180028d12  mov     rax, [rcx]
0x180028d15  mov     edx, 0Eh
0x180028d1a  mov     rax, [rax+28h]
0x180028d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d23  test    al, al
0x180028d25  jz      short loc_180028D49
0x180028d27  mov     rcx, [rsp+120h+var_F0]
0x180028d2c  mov     rax, [rcx]
0x180028d2f  lea     r9, [rbp+57h+var_98]
0x180028d33  mov     edx, 0Eh
0x180028d38  lea     r8d, [rdx+6]
0x180028d3c  mov     rax, [rax+30h]
0x180028d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d45  test    eax, eax
0x180028d47  jns     short loc_180028DAC
0x180028d49  mov     rcx, [rsp+120h+var_F0]
0x180028d4e  mov     rax, [rcx]
0x180028d51  mov     edx, 3
0x180028d56  mov     rax, [rax+28h]
0x180028d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d5f  test    al, al
0x180028d61  jz      loc_180028EC0
0x180028d67  xorps   xmm0, xmm0
0x180028d6a  movups  [rbp+57h+var_80], xmm0
0x180028d6e  mov     rcx, [rsp+120h+var_F0]
0x180028d73  mov     rax, [rcx]
0x180028d76  lea     r9, [rbp+57h+var_80]
0x180028d7a  mov     edx, 3
0x180028d7f  lea     r8d, [rdx+0Dh]
0x180028d83  mov     rax, [rax+30h]
0x180028d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d8c  test    eax, eax
0x180028d8e  js      loc_180028EC0
0x180028d94  mov     eax, dword ptr [rbp+57h+var_80]
0x180028d97  mov     dword ptr [rbp+57h+var_98], eax
0x180028d9a  mov     eax, dword ptr [rbp+57h+var_80+4]
0x180028d9d  mov     dword ptr [rbp+57h+var_98+4], eax
0x180028da0  mov     eax, dword ptr [rbp+57h+var_80+0Ch]
0x180028da3  mov     [rbp+57h+var_88], eax
0x180028da6  mov     eax, dword ptr [rbp+57h+var_80+8]
0x180028da9  mov     dword ptr [rbp+57h+var_98+8], eax
0x180028dac  mov     [rsp+120h+var_E0], 0
0x180028db5  mov     rcx, [rsp+120h+var_F0]
0x180028dba  mov     rax, [rcx]
0x180028dbd  mov     edx, 1
0x180028dc2  mov     rax, [rax+28h]
0x180028dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028dcb  test    al, al
0x180028dcd  jz      loc_180028EC0
0x180028dd3  mov     rcx, [rsp+120h+var_F0]
0x180028dd8  mov     rax, [rcx]
0x180028ddb  lea     r9, [rsp+120h+var_E0]
0x180028de0  mov     edx, 1
0x180028de5  lea     r8d, [rdx+7]
0x180028de9  mov     rax, [rax+30h]
0x180028ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028df2  test    eax, eax
0x180028df4  js      loc_180028EC0
0x180028dfa  mov     eax, dword ptr [rbp+57h+var_98]
0x180028dfd  mov     dword ptr [rbp+57h+var_70], eax
0x180028e00  mov     eax, dword ptr [rbp+57h+var_98+4]
0x180028e03  mov     dword ptr [rbp+57h+var_70+4], eax
0x180028e06  mov     eax, dword ptr [rbp+57h+var_98+8]
0x180028e09  mov     dword ptr [rbp+57h+var_70+8], eax
0x180028e0c  mov     eax, dword ptr [rbp+57h+var_98+0Ch]
0x180028e0f  mov     dword ptr [rbp+57h+var_70+0Ch], eax
0x180028e12  mov     eax, [rbp+57h+var_88]
0x180028e15  mov     dword ptr [rbp+57h+var_60], eax
0x180028e18  xor     eax, eax
0x180028e1a  mov     dword ptr [rbp+57h+var_60+4], eax
0x180028e1d  mov     rax, [rsp+120h+var_E0]
0x180028e22  mov     qword ptr [rbp+57h+var_60+8], rax
0x180028e26  cmp     r13, r12
0x180028e29  jz      short loc_180028E5F
0x180028e2b  mov     rdx, [r15]
0x180028e2e  cmp     rdx, [r15+8]
0x180028e32  jz      loc_180028EC0
0x180028e38  lea     rcx, [rbp+57h+var_98]
0x180028e3c  lea     rax, [rbp+57h+var_84]
0x180028e40  cmp     rcx, rax
0x180028e43  jz      short loc_180028E59
0x180028e45  mov     eax, [rcx]
0x180028e47  cmp     [rdx], eax
0x180028e49  jnz     short loc_180028E53
0x180028e4b  mov     eax, [rcx+4]
0x180028e4e  cmp     [rdx+4], eax
0x180028e51  jz      short loc_180028E5F
0x180028e53  add     rcx, 14h
0x180028e57  jmp     short loc_180028E3C
0x180028e59  add     rdx, 14h
0x180028e5d  jmp     short loc_180028E2E
0x180028e5f  mov     r9, [rbx+8]
0x180028e63  mov     rdx, [rbx]
0x180028e66  cmp     rdx, r9
0x180028e69  jz      short loc_180028E92
0x180028e6b  lea     rcx, [rbp+57h+var_70]
0x180028e6f  lea     rax, [rbp+57h+var_50]
0x180028e73  cmp     rcx, rax
0x180028e76  jz      short loc_180028E8C
0x180028e78  mov     eax, [rcx]
0x180028e7a  cmp     [rdx], eax
0x180028e7c  jnz     short loc_180028E86
0x180028e7e  mov     eax, [rcx+4]
0x180028e81  cmp     [rdx+4], eax
0x180028e84  jz      short loc_180028EC0
0x180028e86  add     rcx, 20h ; ' '
0x180028e8a  jmp     short loc_180028E6F
0x180028e8c  add     rdx, 20h ; ' '
0x180028e90  jmp     short loc_180028E66
0x180028e92  cmp     r9, [rbx+10h]
0x180028e96  jz      short loc_180028EB0
0x180028e98  movups  xmm0, [rbp+57h+var_70]
0x180028e9c  movups  xmmword ptr [r9], xmm0
0x180028ea0  movups  xmm1, [rbp+57h+var_60]
0x180028ea4  movups  xmmword ptr [r9+10h], xmm1
0x180028ea9  add     qword ptr [rbx+8], 20h ; ' '
0x180028eae  jmp     short loc_180028EC0
0x180028eb0  lea     r8, [rbp+57h+var_70]
0x180028eb4  mov     rdx, r9
0x180028eb7  mov     rcx, rbx
0x180028eba  call    ??$_Emplace_reallocate@AEBUFoundNpu@npu_detection@udk@@@?$vector@UFoundNpu@npu_detection@udk@@V?$allocator@UFoundNpu@npu_detection@udk@@@std@@@std@@AEAAPEAUFoundNpu@npu_detection@udk@@QEAU234@AEBU234@@Z; std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(udk::npu_detection::FoundNpu * const,udk::npu_detection::FoundNpu const &)
0x180028ebf  nop
0x180028ec0  lea     rcx, [rsp+120h+var_F0]
0x180028ec5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028eca  inc     esi
0x180028ecc  cmp     esi, r14d
0x180028ecf  jb      loc_180028CAA
0x180028ed5  mov     r12, [rbp+57h+var_A8]
0x180028ed9  xor     esi, esi
0x180028edb  lea     rcx, [rsp+120h+var_E8]
0x180028ee0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028ee5  add     rdi, 8
0x180028ee9  cmp     rdi, r12
0x180028eec  jnz     loc_180028C47
0x180028ef2  lea     rcx, [rbp+57h+var_D0]
0x180028ef6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028efb  nop
0x180028efc  mov     rcx, qword ptr [rbp+57h+var_C8]
0x180028f00  test    rcx, rcx
0x180028f03  jz      short loc_180028F15
0x180028f05  mov     rdx, [rbp+57h+var_B8]
0x180028f09  sub     rdx, rcx
0x180028f0c  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180028f10  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180028f15  mov     rax, rbx
0x180028f18  mov     rcx, [rbp+57h+var_50]
0x180028f1c  xor     rcx, rsp; StackCookie
0x180028f1f  call    __security_check_cookie
0x180028f24  add     rsp, 0E8h
0x180028f2b  pop     r15
0x180028f2d  pop     r14
0x180028f2f  pop     r13
0x180028f31  pop     r12
0x180028f33  pop     rdi
0x180028f34  pop     rsi
0x180028f35  pop     rbx
0x180028f36  pop     rbp
0x180028f37  retn
```
