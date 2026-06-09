# CSdCommonImpl::QueryFileCount(_GUID const *,_FILETIME,_FILETIME,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x18004aa80`
- end: `0x18004b057`
- name: `?QueryFileCount@CSdCommonImpl@@UEAAJPEBU_GUID@@U_FILETIME@@1PEA_K22@Z`
- size: `1495`
- prototype: `__int64 __fastcall(CSdCommonImpl *__hidden this, const struct _GUID *, struct _FILETIME, struct _FILETIME, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003520`
- `0x180003534`
- `0x18001646c`
- `0x18004aa80`
- `0x180072e08`
- `0x180072f14`
- `0x18009e8e4`
- `0x18009f560`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18004acec`
- `ole32!CoTaskMemFree` at `0x18004ad06`
- `ole32!CoTaskMemFree` at `0x18004ae39`
- `ole32!CoTaskMemFree` at `0x18004ae53`
- `ole32!CoTaskMemFree` at `0x18004afad`
- `ole32!CoTaskMemFree` at `0x18004afc5`
- `ole32!CoTaskMemFree` at `0x18004acec`
- `ole32!CoTaskMemFree` at `0x18004ad06`
- `ole32!CoTaskMemFree` at `0x18004ae39`
- `ole32!CoTaskMemFree` at `0x18004ae53`
- `ole32!CoTaskMemFree` at `0x18004afad`
- `ole32!CoTaskMemFree` at `0x18004afc5`

## string_xrefs

- `0x18004aad1`: `CSdCommonImpl::QueryFileCount`

## pseudocode

```c
__int64 __fastcall CSdCommonImpl::QueryFileCount(
        CSdCommonImpl *this,
        const struct _GUID *a2,
        struct _FILETIME a3,
        struct _FILETIME a4,
        unsigned __int64 *a5,
        unsigned __int64 *a6,
        unsigned __int64 *a7)
{
  __int16 v11; // ax
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rsi
  unsigned __int64 v14; // rbx
  int v15; // eax
  unsigned __int16 *v16; // rax
  int v17; // ecx
  int v18; // edx
  __int64 v19; // rax
  unsigned int v20; // ebx
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v23; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  int v26; // [rsp+70h] [rbp-90h] BYREF
  __int16 v27; // [rsp+74h] [rbp-8Ch]
  __int16 v28; // [rsp+76h] [rbp-8Ah]
  __int64 v29; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v30; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v31; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v32[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v33[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v34[8]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v35[8]; // [rsp+E8h] [rbp-18h] BYREF
  GUID v36; // [rsp+F0h] [rbp-10h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v26, "CSdCommonImpl::QueryFileCount", 0xA26u, 1u);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(v35);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(v34);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v31);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v30);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v29);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v25);
  v24 = 0;
  v36 = GUID_NULL;
  v33[0] = qword_1800EE510;
  v33[1] = 0;
  v32[0] = qword_1800EE510;
  v32[1] = 0;
  pv = 0;
  v23 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  v11 = 2621;
  if ( a2 && (v27 = 2621, v11 = 2622, a5) && (v27 = 2622, v11 = 2623, a6) && (v27 = 2623, v11 = 2624, a7) )
  {
    v26 = 0;
    v27 = 2624;
    v26 = (*(__int64 (__fastcall **)(CSdCommonImpl *, struct _FILETIME, struct _FILETIME, _QWORD, _QWORD, int, int, GUID *, __int64 *))(*(_QWORD *)this + 96LL))(
            this,
            a3,
            a3,
            0,
            0,
            1,
            1,
            &IID_ISdUniCursor,
            &v31);
    v11 = 2630;
    if ( v26 >= 0 )
    {
      v27 = 2630;
      v26 = (*(__int64 (__fastcall **)(CSdCommonImpl *, struct _FILETIME, struct _FILETIME, _QWORD, _QWORD, int, int, GUID *, __int64 *))(*(_QWORD *)this + 96LL))(
              this,
              a3,
              a4,
              0,
              0,
              1,
              1,
              &IID_ISdUniCursor,
              &v30);
      v11 = 2631;
      if ( v26 >= 0 )
      {
        v12 = 0;
        v13 = 0;
        v14 = 0;
        v27 = 2631;
        while ( 1 )
        {
LABEL_14:
          ATL::CComPtrBase<ISdUniCursor>::Release(&v29);
          v15 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v31 + 24LL))(
                  v31,
                  &IID_ISdFileRecord,
                  &v29);
          v26 = v15;
          if ( v15 < 0 )
          {
            v11 = 2636;
            goto LABEL_48;
          }
          v27 = 2636;
          if ( v15 == 1 )
          {
            *a5 = v12;
            *a6 = v13;
            *a7 = v14;
            goto LABEL_49;
          }
          v26 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 128LL))(v29, &v24);
          v11 = 2642;
          if ( v26 < 0 )
            goto LABEL_48;
          v27 = 2642;
          if ( (v24 & 0x10) == 0 )
          {
            CoTaskMemFree(pv);
            pv = 0;
            CoTaskMemFree(v23);
            v23 = 0;
            v26 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v29 + 32LL))(v29, &pv);
            v11 = 2653;
            if ( v26 < 0 )
              goto LABEL_48;
            v27 = 2653;
            if ( *(_WORD *)pv != 46 || *((_WORD *)pv + 1) && (*((_WORD *)pv + 1) != 46 || *((_WORD *)pv + 2)) )
              break;
          }
        }
        v26 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v29 + 24LL))(v29, &v23);
        v11 = 2660;
        if ( v26 >= 0 )
        {
          v27 = 2660;
          v26 = CBsString::Set((CBsString *)v33, v23, (const unsigned __int16 *)pv);
          v11 = 2661;
          if ( v26 >= 0 )
          {
            v27 = 2661;
            while ( 1 )
            {
              ATL::CComPtrBase<ISdUniCursor>::Release(&v25);
              v26 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v30 + 24LL))(
                      v30,
                      &IID_ISdFileRecord,
                      &v25);
              v11 = 2669;
              if ( v26 < 0 )
                break;
              v27 = 2669;
              v26 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 128LL))(v25, &v24);
              v11 = 2671;
              if ( v26 < 0 )
                break;
              v27 = 2671;
              if ( (v24 & 0x10) == 0 )
              {
                CoTaskMemFree(pv);
                pv = 0;
                CoTaskMemFree(v23);
                v23 = 0;
                v26 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v25 + 32LL))(v25, &pv);
                v11 = 2681;
                if ( v26 < 0 )
                  break;
                v27 = 2681;
                if ( *(_WORD *)pv != 46 || *((_WORD *)pv + 1) && (*((_WORD *)pv + 1) != 46 || *((_WORD *)pv + 2)) )
                {
                  v26 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v25 + 24LL))(v25, &v23);
                  v11 = 2687;
                  if ( v26 < 0 )
                    break;
                  v27 = 2687;
                  v26 = CBsString::Set((CBsString *)v32, v23, (const unsigned __int16 *)pv);
                  v11 = 2688;
                  if ( v26 < 0 )
                    break;
                  v27 = 2688;
                  ++v13;
                  v16 = (unsigned __int16 *)v33[0];
                  do
                  {
                    v17 = *(unsigned __int16 *)((char *)v16 + v32[0] - v33[0]);
                    v18 = *v16 - v17;
                    if ( v18 )
                      break;
                    ++v16;
                  }
                  while ( v17 );
                  if ( !v18 )
                  {
                    v26 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v25 + 96LL))(v25, &v36);
                    v11 = 2693;
                    if ( v26 < 0 )
                      break;
                    v27 = 2693;
                    ++v12;
                    v19 = *(_QWORD *)&v36.Data1 - *(_QWORD *)&a2->Data1;
                    if ( *(_QWORD *)&v36.Data1 == *(_QWORD *)&a2->Data1 )
                      v19 = *(_QWORD *)v36.Data4 - *(_QWORD *)a2->Data4;
                    if ( v19 )
                      ++v14;
                    goto LABEL_14;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v26 = -2147024809;
  }
LABEL_48:
  v28 = v11;
LABEL_49:
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v23);
  v23 = 0;
  v20 = v26;
  CBsString::_Release((CBsString *)v32);
  CBsString::_Release((CBsString *)v33);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>(&v25);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>(&v29);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>(&v30);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>(&v31);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>(v34);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>(v35);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v26);
  return v20;
}

```

## disassembly

```asm
0x18004aa80  mov     [rsp-8+arg_8], rbx
0x18004aa85  push    rbp
0x18004aa86  push    rsi
0x18004aa87  push    rdi
0x18004aa88  push    r12
0x18004aa8a  push    r13
0x18004aa8c  push    r14
0x18004aa8e  push    r15
0x18004aa90  lea     rbp, [rsp-10h]
0x18004aa95  sub     rsp, 110h
0x18004aa9c  mov     rax, cs:__security_cookie
0x18004aaa3  xor     rax, rsp
0x18004aaa6  mov     [rbp+40h+var_40], rax
0x18004aaaa  mov     rdi, r9
0x18004aaad  mov     rbx, r8
0x18004aab0  mov     r13, rdx
0x18004aab3  mov     rsi, rcx
0x18004aab6  mov     r12, [rbp+40h+arg_20]
0x18004aaba  mov     r14, [rbp+40h+arg_28]
0x18004aabe  mov     r15, [rbp+40h+arg_30]
0x18004aac5  mov     r9d, 1; unsigned __int16
0x18004aacb  mov     r8d, 0A26h; unsigned __int16
0x18004aad1  lea     rdx, aCsdcommonimplQ_8; "CSdCommonImpl::QueryFileCount"
0x18004aad8  lea     rcx, [rsp+140h+var_D0]; this
0x18004aadd  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004aae2  lea     rcx, [rbp+40h+var_58]; void *
0x18004aae6  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18004aaeb  lea     rcx, [rbp+40h+var_60]; void *
0x18004aaef  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18004aaf4  lea     rcx, [rbp+40h+var_88]; void *
0x18004aaf8  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18004aafd  lea     rcx, [rbp+40h+var_90]; void *
0x18004ab01  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18004ab06  lea     rcx, [rbp+40h+var_98]; void *
0x18004ab0a  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18004ab0f  lea     rcx, [rsp+140h+var_D8]; void *
0x18004ab14  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18004ab19  xor     edx, edx
0x18004ab1b  mov     [rsp+140h+var_E0], edx
0x18004ab1f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004ab26  movdqu  [rbp+40h+var_50], xmm0
0x18004ab2b  lea     rax, qword_1800EE510
0x18004ab32  mov     [rbp+40h+var_70], rax
0x18004ab36  mov     [rbp+40h+var_68], rdx
0x18004ab3a  mov     [rbp+40h+var_80], rax
0x18004ab3e  mov     [rbp+40h+var_78], rdx
0x18004ab42  mov     [rsp+140h+pv], rdx
0x18004ab47  mov     [rsp+140h+var_E8], rdx
0x18004ab4c  test    r12, r12
0x18004ab4f  jz      short loc_18004AB55
0x18004ab51  mov     [r12], rdx
0x18004ab55  test    r14, r14
0x18004ab58  jz      short loc_18004AB5D
0x18004ab5a  mov     [r14], rdx
0x18004ab5d  test    r15, r15
0x18004ab60  jz      short loc_18004AB65
0x18004ab62  mov     [r15], rdx
0x18004ab65  mov     eax, 0A3Dh
0x18004ab6a  test    r13, r13
0x18004ab6d  jz      loc_18004AF9B
0x18004ab73  mov     [rsp+140h+var_CC], ax
0x18004ab78  mov     eax, 0A3Eh
0x18004ab7d  test    r12, r12
0x18004ab80  jz      loc_18004AF9B
0x18004ab86  mov     [rsp+140h+var_CC], ax
0x18004ab8b  mov     eax, 0A3Fh
0x18004ab90  test    r14, r14
0x18004ab93  jz      loc_18004AF9B
0x18004ab99  mov     [rsp+140h+var_CC], ax
0x18004ab9e  mov     eax, 0A40h
0x18004aba3  test    r15, r15
0x18004aba6  jz      loc_18004AF9B
0x18004abac  mov     [rsp+140h+var_D0], edx
0x18004abb0  mov     [rsp+140h+var_CC], ax
0x18004abb5  mov     rax, [rsi]
0x18004abb8  lea     rcx, [rbp+40h+var_88]
0x18004abbc  mov     [rsp+140h+var_100], rcx
0x18004abc1  lea     rcx, IID_ISdUniCursor
0x18004abc8  mov     [rsp+140h+var_108], rcx
0x18004abcd  mov     [rsp+140h+var_110], 1
0x18004abd5  mov     [rsp+140h+var_118], 1
0x18004abdd  mov     [rsp+140h+var_120], rdx
0x18004abe2  xor     r9d, r9d
0x18004abe5  mov     r8, rbx
0x18004abe8  mov     rdx, rbx
0x18004abeb  mov     rcx, rsi
0x18004abee  mov     rax, [rax+60h]
0x18004abf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004abf7  mov     [rsp+140h+var_D0], eax
0x18004abfb  xor     edx, edx
0x18004abfd  test    eax, eax
0x18004abff  mov     eax, 0A46h
0x18004ac04  js      loc_18004AFA3
0x18004ac0a  mov     [rsp+140h+var_CC], ax
0x18004ac0f  mov     rax, [rsi]
0x18004ac12  lea     rcx, [rbp+40h+var_90]
0x18004ac16  mov     [rsp+140h+var_100], rcx
0x18004ac1b  lea     rcx, IID_ISdUniCursor
0x18004ac22  mov     [rsp+140h+var_108], rcx
0x18004ac27  mov     [rsp+140h+var_110], 1
0x18004ac2f  mov     [rsp+140h+var_118], 1
0x18004ac37  mov     [rsp+140h+var_120], rdx
0x18004ac3c  xor     r9d, r9d
0x18004ac3f  mov     r8, rdi
0x18004ac42  mov     rdx, rbx
0x18004ac45  mov     rcx, rsi
0x18004ac48  mov     rax, [rax+60h]
0x18004ac4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac51  mov     [rsp+140h+var_D0], eax
0x18004ac55  xor     ecx, ecx
0x18004ac57  test    eax, eax
0x18004ac59  mov     eax, 0A47h
0x18004ac5e  js      loc_18004AFA3
0x18004ac64  mov     edi, ecx
0x18004ac66  mov     esi, ecx
0x18004ac68  mov     ebx, ecx
0x18004ac6a  mov     [rsp+140h+var_CC], ax
0x18004ac6f  lea     rcx, [rbp+40h+var_98]
0x18004ac73  call    ?Release@?$CComPtrBase@UISdUniCursor@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISdUniCursor>::Release(void)
0x18004ac78  mov     rcx, [rbp+40h+var_88]
0x18004ac7c  mov     rax, [rcx]
0x18004ac7f  lea     r8, [rbp+40h+var_98]
0x18004ac83  lea     rdx, IID_ISdFileRecord
0x18004ac8a  mov     rax, [rax+18h]
0x18004ac8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac93  mov     [rsp+140h+var_D0], eax
0x18004ac97  test    eax, eax
0x18004ac99  js      loc_18004AF94
0x18004ac9f  mov     ecx, 0A4Ch
0x18004aca4  mov     [rsp+140h+var_CC], cx
0x18004aca9  cmp     eax, 1
0x18004acac  jz      loc_18004AF88
0x18004acb2  mov     rcx, [rbp+40h+var_98]
0x18004acb6  mov     rax, [rcx]
0x18004acb9  lea     rdx, [rsp+140h+var_E0]
0x18004acbe  mov     rax, [rax+80h]
0x18004acc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004acca  mov     [rsp+140h+var_D0], eax
0x18004acce  test    eax, eax
0x18004acd0  mov     eax, 0A52h
0x18004acd5  js      loc_18004AFA3
0x18004acdb  mov     [rsp+140h+var_CC], ax
0x18004ace0  test    byte ptr [rsp+140h+var_E0], 10h
0x18004ace5  jnz     short loc_18004AC6F
0x18004ace7  mov     rcx, [rsp+140h+pv]; pv
0x18004acec  call    cs:__imp_CoTaskMemFree
0x18004acf3  nop     dword ptr [rax+rax+00h]
0x18004acf8  mov     [rsp+140h+pv], 0
0x18004ad01  mov     rcx, [rsp+140h+var_E8]; pv
0x18004ad06  call    cs:__imp_CoTaskMemFree
0x18004ad0d  nop     dword ptr [rax+rax+00h]
0x18004ad12  mov     [rsp+140h+var_E8], 0
0x18004ad1b  mov     rcx, [rbp+40h+var_98]
0x18004ad1f  mov     rax, [rcx]
0x18004ad22  lea     rdx, [rsp+140h+pv]
0x18004ad27  mov     rax, [rax+20h]
0x18004ad2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad30  mov     [rsp+140h+var_D0], eax
0x18004ad34  xor     ecx, ecx
0x18004ad36  test    eax, eax
0x18004ad38  mov     eax, 0A5Dh
0x18004ad3d  js      loc_18004AFA3
0x18004ad43  mov     [rsp+140h+var_CC], ax
0x18004ad48  mov     rax, [rsp+140h+pv]
0x18004ad4d  cmp     word ptr [rax], 2Eh ; '.'
0x18004ad51  jnz     short loc_18004AD6E
0x18004ad53  cmp     [rax+2], cx
0x18004ad57  jz      loc_18004AC6F
0x18004ad5d  cmp     word ptr [rax+2], 2Eh ; '.'
0x18004ad62  jnz     short loc_18004AD6E
0x18004ad64  cmp     [rax+4], cx
0x18004ad68  jz      loc_18004AC6F
0x18004ad6e  mov     rcx, [rbp+40h+var_98]
0x18004ad72  mov     rax, [rcx]
0x18004ad75  lea     rdx, [rsp+140h+var_E8]
0x18004ad7a  mov     rax, [rax+18h]
0x18004ad7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad83  mov     [rsp+140h+var_D0], eax
0x18004ad87  test    eax, eax
0x18004ad89  mov     eax, 0A64h
0x18004ad8e  js      loc_18004AFA3
0x18004ad94  mov     [rsp+140h+var_CC], ax
0x18004ad99  mov     r8, [rsp+140h+pv]; unsigned __int16 *
0x18004ad9e  mov     rdx, [rsp+140h+var_E8]; unsigned __int16 *
0x18004ada3  lea     rcx, [rbp+40h+var_70]; this
0x18004ada7  call    ?Set@CBsString@@QEAAJPEBG0@Z; CBsString::Set(ushort const *,ushort const *)
0x18004adac  mov     [rsp+140h+var_D0], eax
0x18004adb0  test    eax, eax
0x18004adb2  mov     eax, 0A65h
0x18004adb7  js      loc_18004AFA3
0x18004adbd  mov     [rsp+140h+var_CC], ax
0x18004adc2  lea     rcx, [rsp+140h+var_D8]
0x18004adc7  call    ?Release@?$CComPtrBase@UISdUniCursor@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISdUniCursor>::Release(void)
0x18004adcc  mov     rcx, [rbp+40h+var_90]
0x18004add0  mov     rax, [rcx]
0x18004add3  lea     r8, [rsp+140h+var_D8]
0x18004add8  lea     rdx, IID_ISdFileRecord
0x18004addf  mov     rax, [rax+18h]
0x18004ade3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ade8  mov     [rsp+140h+var_D0], eax
0x18004adec  test    eax, eax
0x18004adee  mov     eax, 0A6Dh
0x18004adf3  js      loc_18004AFA3
0x18004adf9  mov     [rsp+140h+var_CC], ax
0x18004adfe  mov     rcx, [rsp+140h+var_D8]
0x18004ae03  mov     rax, [rcx]
0x18004ae06  lea     rdx, [rsp+140h+var_E0]
0x18004ae0b  mov     rax, [rax+80h]
0x18004ae12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae17  mov     [rsp+140h+var_D0], eax
0x18004ae1b  test    eax, eax
0x18004ae1d  mov     eax, 0A6Fh
0x18004ae22  js      loc_18004AFA3
0x18004ae28  mov     [rsp+140h+var_CC], ax
0x18004ae2d  test    byte ptr [rsp+140h+var_E0], 10h
0x18004ae32  jnz     short loc_18004ADC2
0x18004ae34  mov     rcx, [rsp+140h+pv]; pv
0x18004ae39  call    cs:__imp_CoTaskMemFree
0x18004ae40  nop     dword ptr [rax+rax+00h]
0x18004ae45  mov     [rsp+140h+pv], 0
0x18004ae4e  mov     rcx, [rsp+140h+var_E8]; pv
0x18004ae53  call    cs:__imp_CoTaskMemFree
0x18004ae5a  nop     dword ptr [rax+rax+00h]
0x18004ae5f  mov     [rsp+140h+var_E8], 0
0x18004ae68  mov     rcx, [rsp+140h+var_D8]
0x18004ae6d  mov     rax, [rcx]
0x18004ae70  lea     rdx, [rsp+140h+pv]
0x18004ae75  mov     rax, [rax+20h]
0x18004ae79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae7e  mov     [rsp+140h+var_D0], eax
0x18004ae82  xor     ecx, ecx
0x18004ae84  test    eax, eax
0x18004ae86  mov     eax, 0A79h
0x18004ae8b  js      loc_18004AFA3
0x18004ae91  mov     [rsp+140h+var_CC], ax
0x18004ae96  mov     rax, [rsp+140h+pv]
0x18004ae9b  cmp     word ptr [rax], 2Eh ; '.'
0x18004ae9f  jnz     short loc_18004AEBC
0x18004aea1  cmp     [rax+2], cx
0x18004aea5  jz      loc_18004ADC2
0x18004aeab  cmp     word ptr [rax+2], 2Eh ; '.'
0x18004aeb0  jnz     short loc_18004AEBC
0x18004aeb2  cmp     [rax+4], cx
0x18004aeb6  jz      loc_18004ADC2
0x18004aebc  mov     rcx, [rsp+140h+var_D8]
0x18004aec1  mov     rax, [rcx]
0x18004aec4  lea     rdx, [rsp+140h+var_E8]
0x18004aec9  mov     rax, [rax+18h]
0x18004aecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aed2  mov     [rsp+140h+var_D0], eax
0x18004aed6  test    eax, eax
0x18004aed8  mov     eax, 0A7Fh
0x18004aedd  js      loc_18004AFA3
0x18004aee3  mov     [rsp+140h+var_CC], ax
0x18004aee8  mov     r8, [rsp+140h+pv]; unsigned __int16 *
0x18004aeed  mov     rdx, [rsp+140h+var_E8]; unsigned __int16 *
0x18004aef2  lea     rcx, [rbp+40h+var_80]; this
0x18004aef6  call    ?Set@CBsString@@QEAAJPEBG0@Z; CBsString::Set(ushort const *,ushort const *)
0x18004aefb  mov     [rsp+140h+var_D0], eax
0x18004aeff  test    eax, eax
0x18004af01  mov     eax, 0A80h
0x18004af06  js      loc_18004AFA3
0x18004af0c  mov     [rsp+140h+var_CC], ax
0x18004af11  inc     rsi
0x18004af14  mov     rax, [rbp+40h+var_70]
0x18004af18  mov     r8, [rbp+40h+var_80]
0x18004af1c  sub     r8, rax
0x18004af1f  movzx   edx, word ptr [rax]
0x18004af22  movzx   ecx, word ptr [rax+r8]
0x18004af27  sub     edx, ecx
0x18004af29  jnz     short loc_18004AF33
0x18004af2b  add     rax, 2
0x18004af2f  test    ecx, ecx
0x18004af31  jnz     short loc_18004AF1F
0x18004af33  test    edx, edx
0x18004af35  jnz     loc_18004ADC2
0x18004af3b  mov     rcx, [rsp+140h+var_D8]
0x18004af40  mov     rax, [rcx]
0x18004af43  lea     rdx, [rbp+40h+var_50]
0x18004af47  mov     rax, [rax+60h]
0x18004af4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af50  mov     [rsp+140h+var_D0], eax
0x18004af54  test    eax, eax
0x18004af56  mov     eax, 0A85h
0x18004af5b  js      short loc_18004AFA3
0x18004af5d  mov     [rsp+140h+var_CC], ax
0x18004af62  inc     rdi
0x18004af65  mov     rax, qword ptr [rbp+40h+var_50]
0x18004af69  sub     rax, [r13+0]
0x18004af6d  jnz     short loc_18004AF77
0x18004af6f  mov     rax, qword ptr [rbp+40h+var_50+8]
0x18004af73  sub     rax, [r13+8]
0x18004af77  test    rax, rax
0x18004af7a  jz      loc_18004AC6F
0x18004af80  inc     rbx
0x18004af83  jmp     loc_18004AC6F
0x18004af88  mov     [r12], rdi
0x18004af8c  mov     [r14], rsi
0x18004af8f  mov     [r15], rbx
0x18004af92  jmp     short loc_18004AFA8
  ... truncated ...
```
