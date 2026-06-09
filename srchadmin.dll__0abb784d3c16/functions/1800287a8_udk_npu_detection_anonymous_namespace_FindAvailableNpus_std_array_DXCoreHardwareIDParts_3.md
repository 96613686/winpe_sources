# udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::array_DXCoreHardwareIDParts_3___

- ea: `0x1800287a8`
- end: `0x180028b81`
- name: `udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::array_DXCoreHardwareIDParts_3___`
- size: `985`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180029ef4`

## callees

- `0x1800038ac`
- `0x180005cc0`
- `0x18000f82c`
- `0x1800287a8`
- `0x180029498`
- `0x18002c088`
- `0x18002c180`
- `0x18002c464`
- `0x180032010`

## import_xrefs

- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x180028873`
- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x180028873`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::array_DXCoreHardwareIDParts_3___(
        _QWORD *a1,
        __int64 a2,
        _DWORD *a3)
{
  unsigned int v5; // esi
  _DWORD *v6; // r13
  int v7; // eax
  _QWORD *i; // rdi
  _QWORD *v9; // r12
  __int64 v10; // rax
  unsigned int v11; // r14d
  __int64 v12; // rax
  _DWORD *v13; // rdx
  __int128 *j; // rcx
  _OWORD *v15; // r9
  _DWORD *k; // rdx
  __int64 *m; // rcx
  int v19; // [rsp+20h] [rbp-99h]
  __int64 v20; // [rsp+30h] [rbp-89h] BYREF
  __int64 *v21; // [rsp+38h] [rbp-81h] BYREF
  __int64 *v22; // [rsp+40h] [rbp-79h] BYREF
  int v23; // [rsp+48h] [rbp-71h]
  __int64 *v24; // [rsp+50h] [rbp-69h] BYREF
  __int128 v25; // [rsp+58h] [rbp-61h] BYREF
  __int64 v26; // [rsp+68h] [rbp-51h]
  _QWORD *v27; // [rsp+70h] [rbp-49h]
  __int128 v28; // [rsp+78h] [rbp-41h] BYREF
  unsigned int v29; // [rsp+88h] [rbp-31h]
  char v30; // [rsp+8Ch] [rbp-2Dh] BYREF
  __int128 v31; // [rsp+90h] [rbp-29h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v33; // [rsp+B0h] [rbp-9h]
  __int64 v34; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v27 = a1;
  v5 = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v23 = 1;
  v6 = a3 + 15;
  v25 = 0;
  v26 = 0;
  v21 = DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU;
  std::vector<_GUID const *>::push_back(&v25, &v21);
  v21 = DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML;
  std::vector<_GUID const *>::push_back(&v25, &v21);
  v21 = DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE;
  std::vector<_GUID const *>::push_back(&v25, &v21);
  v24 = 0;
  v7 = DXCoreCreateAdapterFactory(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, &v24);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\npu_detection.h",
      (const char *)(unsigned int)v7,
      v19);
  v9 = (_QWORD *)*((_QWORD *)&v25 + 1);
  for ( i = (_QWORD *)v25; i != v9; ++i )
  {
    v22 = 0;
    v10 = *v24;
    v22 = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64, _QWORD, GUID *, __int64 **))(v10 + 24))(
           v24,
           1,
           *i,
           &GUID_526c7776_40e9_459b_b711_f32ad76dfc28,
           &v22) >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64 *))(*v22 + 32))(v22);
      if ( v11 )
      {
        while ( 1 )
        {
          v20 = 0;
          v12 = *v22;
          v20 = 0;
          if ( (*(int (__fastcall **)(__int64 *, _QWORD, GUID *, __int64 *))(v12 + 24))(
                 v22,
                 v5,
                 &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e,
                 &v20) >= 0 )
          {
            if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 40LL))(v20, 11) )
            {
              v28 = 0;
              v29 = 0;
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 40LL))(v20, 14)
                && (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v20 + 48LL))(
                     v20,
                     14,
                     20,
                     &v28) >= 0 )
              {
                goto LABEL_13;
              }
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 40LL))(v20, 3) )
              {
                v31 = 0;
                if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v20 + 48LL))(
                       v20,
                       3,
                       16,
                       &v31) >= 0 )
                  break;
              }
            }
          }
LABEL_34:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
          if ( ++v5 >= v11 )
          {
            v5 = 0;
            goto LABEL_36;
          }
        }
        *(_QWORD *)&v28 = v31;
        v29 = HIDWORD(v31);
        DWORD2(v28) = DWORD2(v31);
LABEL_13:
        v21 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 40LL))(v20, 1)
          && (*(int (__fastcall **)(__int64, __int64, __int64, __int64 **))(*(_QWORD *)v20 + 48LL))(v20, 1, 8, &v21) >= 0 )
        {
          v32 = v28;
          *(_QWORD *)&v33 = v29;
          *((_QWORD *)&v33 + 1) = v21;
          v13 = a3;
LABEL_16:
          if ( v13 != v6 )
          {
            for ( j = &v28; ; j = (__int128 *)((char *)j + 20) )
            {
              if ( j == (__int128 *)&v30 )
              {
                v13 += 5;
                goto LABEL_16;
              }
              if ( *v13 == *(_DWORD *)j && v13[1] == *((_DWORD *)j + 1) )
                break;
            }
            v15 = (_OWORD *)a1[1];
            for ( k = (_DWORD *)*a1; k != (_DWORD *)v15; k += 8 )
            {
              for ( m = (__int64 *)&v32; m != &v34; m += 4 )
              {
                if ( *k == *(_DWORD *)m && k[1] == *((_DWORD *)m + 1) )
                  goto LABEL_34;
              }
            }
            if ( v15 == (_OWORD *)a1[2] )
            {
              std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(
                a1,
                a1[1],
                &v32);
            }
            else
            {
              *v15 = v32;
              v15[1] = v33;
              a1[1] += 32LL;
            }
          }
        }
        goto LABEL_34;
      }
    }
LABEL_36:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v24);
  if ( (_QWORD)v25 )
    std::_Deallocate<16>((_QWORD *)v25, (v26 - v25) & 0xFFFFFFFFFFFFFFF8uLL);
  return a1;
}

```

## disassembly

```asm
0x1800287a8  push    rbp
0x1800287aa  push    rbx
0x1800287ab  push    rsi
0x1800287ac  push    rdi
0x1800287ad  push    r12
0x1800287af  push    r13
0x1800287b1  push    r14
0x1800287b3  push    r15
0x1800287b5  lea     rbp, [rsp-1Fh]
0x1800287ba  sub     rsp, 0D8h
0x1800287c1  mov     rax, cs:__security_cookie
0x1800287c8  xor     rax, rsp
0x1800287cb  mov     [rbp+57h+var_50], rax
0x1800287cf  mov     r15, r8
0x1800287d2  mov     rbx, rcx
0x1800287d5  mov     [rbp+57h+var_A0], rcx
0x1800287d9  xor     esi, esi
0x1800287db  mov     [rbp+57h+var_C8], esi
0x1800287de  mov     [rcx], rsi
0x1800287e1  mov     [rcx+8], rsi
0x1800287e5  mov     [rcx+10h], rsi
0x1800287e9  mov     [rbp+57h+var_C8], 1
0x1800287f0  lea     r13, [r8+3Ch]
0x1800287f4  cmp     r8, r13
0x1800287f7  jnz     short loc_180028809
0x1800287f9  mov     rcx, [rbp+5Fh]; this
0x1800287fd  mov     r9d, 80070057h; char *
0x180028803  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028809  xorps   xmm0, xmm0
0x18002880c  movdqu  [rbp+57h+var_B8], xmm0
0x180028811  mov     [rbp+57h+var_A8], rsi
0x180028815  lea     rax, DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU
0x18002881c  mov     [rsp+110h+var_D8], rax
0x180028821  lea     rdx, [rsp+110h+var_D8]
0x180028826  lea     rcx, [rbp+57h+var_B8]
0x18002882a  call    ?push_back@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAAX$$QEAPEBU_GUID@@@Z; std::vector<_GUID const *>::push_back(_GUID const * &&)
0x18002882f  lea     rax, DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML
0x180028836  mov     [rsp+110h+var_D8], rax
0x18002883b  lea     rdx, [rsp+110h+var_D8]
0x180028840  lea     rcx, [rbp+57h+var_B8]
0x180028844  call    ?push_back@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAAX$$QEAPEBU_GUID@@@Z; std::vector<_GUID const *>::push_back(_GUID const * &&)
0x180028849  lea     rax, DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE
0x180028850  mov     [rsp+110h+var_D8], rax
0x180028855  lea     rdx, [rsp+110h+var_D8]
0x18002885a  lea     rcx, [rbp+57h+var_B8]
0x18002885e  call    ?push_back@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAAX$$QEAPEBU_GUID@@@Z; std::vector<_GUID const *>::push_back(_GUID const * &&)
0x180028863  nop
0x180028864  mov     [rbp+57h+var_C0], rsi
0x180028868  lea     rdx, [rbp+57h+var_C0]
0x18002886c  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x180028873  call    cs:__imp_DXCoreCreateAdapterFactory
0x180028879  mov     rcx, [rbp+5Fh]; this
0x18002887d  test    eax, eax
0x18002887f  jns     short loc_180028896
0x180028881  mov     r9d, eax; char *
0x180028884  lea     r8, aOnecoreInterna_3; "OneCore\\Internal\\Shell\\inc\\npu_dete"...
0x18002888b  mov     edx, 17Dh; void *
0x180028890  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180028896  mov     rdi, qword ptr [rbp+57h+var_B8]
0x18002889a  mov     r12, qword ptr [rbp+57h+var_B8+8]
0x18002889e  jmp     loc_180028B31
0x1800288a3  mov     [rbp+57h+var_D0], rsi
0x1800288a7  mov     rcx, [rbp+57h+var_C0]
0x1800288ab  mov     rax, [rcx]
0x1800288ae  mov     [rbp+57h+var_D0], rsi
0x1800288b2  lea     rdx, [rbp+57h+var_D0]
0x1800288b6  mov     qword ptr [rsp+110h+var_F0], rdx
0x1800288bb  lea     r9, _GUID_526c7776_40e9_459b_b711_f32ad76dfc28
0x1800288c2  mov     r8, [rdi]
0x1800288c5  mov     edx, 1
0x1800288ca  mov     rax, [rax+18h]
0x1800288ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288d3  test    eax, eax
0x1800288d5  js      loc_180028B24
0x1800288db  mov     rcx, [rbp+57h+var_D0]
0x1800288df  mov     rax, [rcx]
0x1800288e2  mov     rax, [rax+20h]
0x1800288e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288eb  mov     r14d, eax
0x1800288ee  test    eax, eax
0x1800288f0  jz      loc_180028B24
0x1800288f6  test    eax, eax
0x1800288f8  jz      loc_180028B22
0x1800288fe  mov     [rsp+110h+var_E0], 0
0x180028907  mov     rcx, [rbp+57h+var_D0]
0x18002890b  mov     rax, [rcx]
0x18002890e  mov     [rsp+110h+var_E0], 0
0x180028917  lea     r9, [rsp+110h+var_E0]
0x18002891c  lea     r8, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x180028923  mov     edx, esi
0x180028925  mov     rax, [rax+18h]
0x180028929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002892e  test    eax, eax
0x180028930  js      loc_180028B0D
0x180028936  mov     rcx, [rsp+110h+var_E0]
0x18002893b  mov     rax, [rcx]
0x18002893e  mov     edx, 0Bh
0x180028943  mov     rax, [rax+28h]
0x180028947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002894c  test    al, al
0x18002894e  jz      loc_180028B0D
0x180028954  xorps   xmm0, xmm0
0x180028957  xor     eax, eax
0x180028959  movups  [rbp+57h+var_98], xmm0
0x18002895d  mov     [rbp+57h+var_88], eax
0x180028960  mov     rcx, [rsp+110h+var_E0]
0x180028965  mov     rax, [rcx]
0x180028968  mov     edx, 0Eh
0x18002896d  mov     rax, [rax+28h]
0x180028971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028976  test    al, al
0x180028978  jz      short loc_18002899C
0x18002897a  mov     rcx, [rsp+110h+var_E0]
0x18002897f  mov     rax, [rcx]
0x180028982  lea     r9, [rbp+57h+var_98]
0x180028986  mov     edx, 0Eh
0x18002898b  lea     r8d, [rdx+6]
0x18002898f  mov     rax, [rax+30h]
0x180028993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028998  test    eax, eax
0x18002899a  jns     short loc_1800289FF
0x18002899c  mov     rcx, [rsp+110h+var_E0]
0x1800289a1  mov     rax, [rcx]
0x1800289a4  mov     edx, 3
0x1800289a9  mov     rax, [rax+28h]
0x1800289ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289b2  test    al, al
0x1800289b4  jz      loc_180028B0D
0x1800289ba  xorps   xmm0, xmm0
0x1800289bd  movups  [rbp+57h+var_80], xmm0
0x1800289c1  mov     rcx, [rsp+110h+var_E0]
0x1800289c6  mov     rax, [rcx]
0x1800289c9  lea     r9, [rbp+57h+var_80]
0x1800289cd  mov     edx, 3
0x1800289d2  lea     r8d, [rdx+0Dh]
0x1800289d6  mov     rax, [rax+30h]
0x1800289da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289df  test    eax, eax
0x1800289e1  js      loc_180028B0D
0x1800289e7  mov     eax, dword ptr [rbp+57h+var_80]
0x1800289ea  mov     dword ptr [rbp+57h+var_98], eax
0x1800289ed  mov     eax, dword ptr [rbp+57h+var_80+4]
0x1800289f0  mov     dword ptr [rbp+57h+var_98+4], eax
0x1800289f3  mov     eax, dword ptr [rbp+57h+var_80+0Ch]
0x1800289f6  mov     [rbp+57h+var_88], eax
0x1800289f9  mov     eax, dword ptr [rbp+57h+var_80+8]
0x1800289fc  mov     dword ptr [rbp+57h+var_98+8], eax
0x1800289ff  mov     [rsp+110h+var_D8], 0
0x180028a08  mov     rcx, [rsp+110h+var_E0]
0x180028a0d  mov     rax, [rcx]
0x180028a10  mov     edx, 1
0x180028a15  mov     rax, [rax+28h]
0x180028a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a1e  test    al, al
0x180028a20  jz      loc_180028B0D
0x180028a26  mov     rcx, [rsp+110h+var_E0]
0x180028a2b  mov     rax, [rcx]
0x180028a2e  lea     r9, [rsp+110h+var_D8]
0x180028a33  mov     edx, 1
0x180028a38  lea     r8d, [rdx+7]
0x180028a3c  mov     rax, [rax+30h]
0x180028a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a45  test    eax, eax
0x180028a47  js      loc_180028B0D
0x180028a4d  mov     eax, dword ptr [rbp+57h+var_98]
0x180028a50  mov     dword ptr [rbp+57h+var_70], eax
0x180028a53  mov     eax, dword ptr [rbp+57h+var_98+4]
0x180028a56  mov     dword ptr [rbp+57h+var_70+4], eax
0x180028a59  mov     eax, dword ptr [rbp+57h+var_98+8]
0x180028a5c  mov     dword ptr [rbp+57h+var_70+8], eax
0x180028a5f  mov     eax, dword ptr [rbp+57h+var_98+0Ch]
0x180028a62  mov     dword ptr [rbp+57h+var_70+0Ch], eax
0x180028a65  mov     eax, [rbp+57h+var_88]
0x180028a68  mov     dword ptr [rbp+57h+var_60], eax
0x180028a6b  xor     eax, eax
0x180028a6d  mov     dword ptr [rbp+57h+var_60+4], eax
0x180028a70  mov     rax, [rsp+110h+var_D8]
0x180028a75  mov     qword ptr [rbp+57h+var_60+8], rax
0x180028a79  mov     rdx, r15
0x180028a7c  cmp     rdx, r13
0x180028a7f  jz      loc_180028B0D
0x180028a85  lea     rcx, [rbp+57h+var_98]
0x180028a89  lea     rax, [rbp+57h+var_84]
0x180028a8d  cmp     rcx, rax
0x180028a90  jz      short loc_180028AA6
0x180028a92  mov     eax, [rcx]
0x180028a94  cmp     [rdx], eax
0x180028a96  jnz     short loc_180028AA0
0x180028a98  mov     eax, [rcx+4]
0x180028a9b  cmp     [rdx+4], eax
0x180028a9e  jz      short loc_180028AAC
0x180028aa0  add     rcx, 14h
0x180028aa4  jmp     short loc_180028A89
0x180028aa6  add     rdx, 14h
0x180028aaa  jmp     short loc_180028A7C
0x180028aac  mov     r9, [rbx+8]
0x180028ab0  mov     rdx, [rbx]
0x180028ab3  cmp     rdx, r9
0x180028ab6  jz      short loc_180028ADF
0x180028ab8  lea     rcx, [rbp+57h+var_70]
0x180028abc  lea     rax, [rbp+57h+var_50]
0x180028ac0  cmp     rcx, rax
0x180028ac3  jz      short loc_180028AD9
0x180028ac5  mov     eax, [rcx]
0x180028ac7  cmp     [rdx], eax
0x180028ac9  jnz     short loc_180028AD3
0x180028acb  mov     eax, [rcx+4]
0x180028ace  cmp     [rdx+4], eax
0x180028ad1  jz      short loc_180028B0D
0x180028ad3  add     rcx, 20h ; ' '
0x180028ad7  jmp     short loc_180028ABC
0x180028ad9  add     rdx, 20h ; ' '
0x180028add  jmp     short loc_180028AB3
0x180028adf  cmp     r9, [rbx+10h]
0x180028ae3  jz      short loc_180028AFD
0x180028ae5  movups  xmm0, [rbp+57h+var_70]
0x180028ae9  movups  xmmword ptr [r9], xmm0
0x180028aed  movups  xmm1, [rbp+57h+var_60]
0x180028af1  movups  xmmword ptr [r9+10h], xmm1
0x180028af6  add     qword ptr [rbx+8], 20h ; ' '
0x180028afb  jmp     short loc_180028B0D
0x180028afd  lea     r8, [rbp+57h+var_70]
0x180028b01  mov     rdx, r9
0x180028b04  mov     rcx, rbx
0x180028b07  call    ??$_Emplace_reallocate@AEBUFoundNpu@npu_detection@udk@@@?$vector@UFoundNpu@npu_detection@udk@@V?$allocator@UFoundNpu@npu_detection@udk@@@std@@@std@@AEAAPEAUFoundNpu@npu_detection@udk@@QEAU234@AEBU234@@Z; std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(udk::npu_detection::FoundNpu * const,udk::npu_detection::FoundNpu const &)
0x180028b0c  nop
0x180028b0d  lea     rcx, [rsp+110h+var_E0]
0x180028b12  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028b17  inc     esi
0x180028b19  cmp     esi, r14d
0x180028b1c  jb      loc_1800288FE
0x180028b22  xor     esi, esi
0x180028b24  lea     rcx, [rbp+57h+var_D0]
0x180028b28  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028b2d  add     rdi, 8
0x180028b31  cmp     rdi, r12
0x180028b34  jnz     loc_1800288A3
0x180028b3a  lea     rcx, [rbp+57h+var_C0]
0x180028b3e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028b43  nop
0x180028b44  mov     rcx, qword ptr [rbp+57h+var_B8]
0x180028b48  test    rcx, rcx
0x180028b4b  jz      short loc_180028B5D
0x180028b4d  mov     rdx, [rbp+57h+var_A8]
0x180028b51  sub     rdx, rcx
0x180028b54  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180028b58  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180028b5d  mov     rax, rbx
0x180028b60  mov     rcx, [rbp+57h+var_50]
0x180028b64  xor     rcx, rsp; StackCookie
0x180028b67  call    __security_check_cookie
0x180028b6c  add     rsp, 0D8h
0x180028b73  pop     r15
0x180028b75  pop     r14
0x180028b77  pop     r13
0x180028b79  pop     r12
0x180028b7b  pop     rdi
0x180028b7c  pop     rsi
0x180028b7d  pop     rbx
0x180028b7e  pop     rbp
0x180028b7f  retn
```
