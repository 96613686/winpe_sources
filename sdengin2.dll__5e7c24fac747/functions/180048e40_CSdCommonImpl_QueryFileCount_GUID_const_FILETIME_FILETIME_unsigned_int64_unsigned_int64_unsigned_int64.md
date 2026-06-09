# CSdCommonImpl::QueryFileCount(_GUID const *,_FILETIME,_FILETIME,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180048e40`
- end: `0x1800493f2`
- name: `?QueryFileCount@CSdCommonImpl@@UEAAJPEBU_GUID@@U_FILETIME@@1PEA_K22@Z`
- size: `1458`
- prototype: `__int64 __fastcall(CSdCommonImpl *__hidden this, const struct _GUID *, struct _FILETIME, struct _FILETIME, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003430`
- `0x180003444`
- `0x180015b08`
- `0x180048e40`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18009a22c`
- `0x18009ae34`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800490ac`
- `ole32!CoTaskMemFree` at `0x1800490c0`
- `ole32!CoTaskMemFree` at `0x1800491ed`
- `ole32!CoTaskMemFree` at `0x180049201`
- `ole32!CoTaskMemFree` at `0x180049355`
- `ole32!CoTaskMemFree` at `0x180049367`
- `ole32!CoTaskMemFree` at `0x1800490ac`
- `ole32!CoTaskMemFree` at `0x1800490c0`
- `ole32!CoTaskMemFree` at `0x1800491ed`
- `ole32!CoTaskMemFree` at `0x180049201`
- `ole32!CoTaskMemFree` at `0x180049355`
- `ole32!CoTaskMemFree` at `0x180049367`

## string_xrefs

- `0x180048e91`: `CSdCommonImpl::QueryFileCount`

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
  __int64 v34; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v35; // [rsp+E8h] [rbp-18h] BYREF
  GUID v36; // [rsp+F0h] [rbp-10h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v26, "CSdCommonImpl::QueryFileCount", 2598, 1);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v35);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v34);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v31);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v30);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v29);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v25);
  v24 = 0;
  v36 = GUID_NULL;
  v33[0] = qword_1800E8530;
  v33[1] = 0;
  v32[0] = qword_1800E8530;
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
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>((__int64)&v25);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>((__int64)&v29);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>((__int64)&v30);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>((__int64)&v31);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>((__int64)&v34);
  ATL::CComPtr<ISdUniCursor>::~CComPtr<ISdUniCursor>((__int64)&v35);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v26);
  return v20;
}

```

## disassembly

```asm
0x180048e40  mov     [rsp-8+arg_8], rbx
0x180048e45  push    rbp
0x180048e46  push    rsi
0x180048e47  push    rdi
0x180048e48  push    r12
0x180048e4a  push    r13
0x180048e4c  push    r14
0x180048e4e  push    r15
0x180048e50  lea     rbp, [rsp-10h]
0x180048e55  sub     rsp, 110h
0x180048e5c  mov     rax, cs:__security_cookie
0x180048e63  xor     rax, rsp
0x180048e66  mov     [rbp+40h+var_40], rax
0x180048e6a  mov     rdi, r9
0x180048e6d  mov     rbx, r8
0x180048e70  mov     r13, rdx
0x180048e73  mov     rsi, rcx
0x180048e76  mov     r12, [rbp+40h+arg_20]
0x180048e7a  mov     r14, [rbp+40h+arg_28]
0x180048e7e  mov     r15, [rbp+40h+arg_30]
0x180048e85  mov     r9d, 1; unsigned __int16
0x180048e8b  mov     r8d, 0A26h; unsigned __int16
0x180048e91  lea     rdx, aCsdcommonimplQ_8; "CSdCommonImpl::QueryFileCount"
0x180048e98  lea     rcx, [rsp+140h+var_D0]; this
0x180048e9d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180048ea2  lea     rcx, [rbp+40h+var_58]; void *
0x180048ea6  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x180048eab  lea     rcx, [rbp+40h+var_60]; void *
0x180048eaf  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x180048eb4  lea     rcx, [rbp+40h+var_88]; void *
0x180048eb8  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x180048ebd  lea     rcx, [rbp+40h+var_90]; void *
0x180048ec1  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x180048ec6  lea     rcx, [rbp+40h+var_98]; void *
0x180048eca  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x180048ecf  lea     rcx, [rsp+140h+var_D8]; void *
0x180048ed4  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x180048ed9  xor     edx, edx
0x180048edb  mov     [rsp+140h+var_E0], edx
0x180048edf  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180048ee6  movdqu  [rbp+40h+var_50], xmm0
0x180048eeb  lea     rax, qword_1800E8530
0x180048ef2  mov     [rbp+40h+var_70], rax
0x180048ef6  mov     [rbp+40h+var_68], rdx
0x180048efa  mov     [rbp+40h+var_80], rax
0x180048efe  mov     [rbp+40h+var_78], rdx
0x180048f02  mov     [rsp+140h+pv], rdx
0x180048f07  mov     [rsp+140h+var_E8], rdx
0x180048f0c  test    r12, r12
0x180048f0f  jz      short loc_180048F15
0x180048f11  mov     [r12], rdx
0x180048f15  test    r14, r14
0x180048f18  jz      short loc_180048F1D
0x180048f1a  mov     [r14], rdx
0x180048f1d  test    r15, r15
0x180048f20  jz      short loc_180048F25
0x180048f22  mov     [r15], rdx
0x180048f25  mov     eax, 0A3Dh
0x180048f2a  test    r13, r13
0x180048f2d  jz      loc_180049343
0x180048f33  mov     [rsp+140h+var_CC], ax
0x180048f38  mov     eax, 0A3Eh
0x180048f3d  test    r12, r12
0x180048f40  jz      loc_180049343
0x180048f46  mov     [rsp+140h+var_CC], ax
0x180048f4b  mov     eax, 0A3Fh
0x180048f50  test    r14, r14
0x180048f53  jz      loc_180049343
0x180048f59  mov     [rsp+140h+var_CC], ax
0x180048f5e  mov     eax, 0A40h
0x180048f63  test    r15, r15
0x180048f66  jz      loc_180049343
0x180048f6c  mov     [rsp+140h+var_D0], edx
0x180048f70  mov     [rsp+140h+var_CC], ax
0x180048f75  mov     rax, [rsi]
0x180048f78  lea     rcx, [rbp+40h+var_88]
0x180048f7c  mov     [rsp+140h+var_100], rcx
0x180048f81  lea     rcx, IID_ISdUniCursor
0x180048f88  mov     [rsp+140h+var_108], rcx
0x180048f8d  mov     [rsp+140h+var_110], 1
0x180048f95  mov     [rsp+140h+var_118], 1
0x180048f9d  mov     [rsp+140h+var_120], rdx
0x180048fa2  xor     r9d, r9d
0x180048fa5  mov     r8, rbx
0x180048fa8  mov     rdx, rbx
0x180048fab  mov     rcx, rsi
0x180048fae  mov     rax, [rax+60h]
0x180048fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048fb7  mov     [rsp+140h+var_D0], eax
0x180048fbb  xor     edx, edx
0x180048fbd  test    eax, eax
0x180048fbf  mov     eax, 0A46h
0x180048fc4  js      loc_18004934B
0x180048fca  mov     [rsp+140h+var_CC], ax
0x180048fcf  mov     rax, [rsi]
0x180048fd2  lea     rcx, [rbp+40h+var_90]
0x180048fd6  mov     [rsp+140h+var_100], rcx
0x180048fdb  lea     rcx, IID_ISdUniCursor
0x180048fe2  mov     [rsp+140h+var_108], rcx
0x180048fe7  mov     [rsp+140h+var_110], 1
0x180048fef  mov     [rsp+140h+var_118], 1
0x180048ff7  mov     [rsp+140h+var_120], rdx
0x180048ffc  xor     r9d, r9d
0x180048fff  mov     r8, rdi
0x180049002  mov     rdx, rbx
0x180049005  mov     rcx, rsi
0x180049008  mov     rax, [rax+60h]
0x18004900c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049011  mov     [rsp+140h+var_D0], eax
0x180049015  xor     ecx, ecx
0x180049017  test    eax, eax
0x180049019  mov     eax, 0A47h
0x18004901e  js      loc_18004934B
0x180049024  mov     edi, ecx
0x180049026  mov     esi, ecx
0x180049028  mov     ebx, ecx
0x18004902a  mov     [rsp+140h+var_CC], ax
0x18004902f  lea     rcx, [rbp+40h+var_98]
0x180049033  call    ?Release@?$CComPtrBase@UISdUniCursor@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISdUniCursor>::Release(void)
0x180049038  mov     rcx, [rbp+40h+var_88]
0x18004903c  mov     rax, [rcx]
0x18004903f  lea     r8, [rbp+40h+var_98]
0x180049043  lea     rdx, IID_ISdFileRecord
0x18004904a  mov     rax, [rax+18h]
0x18004904e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049053  mov     [rsp+140h+var_D0], eax
0x180049057  test    eax, eax
0x180049059  js      loc_18004933C
0x18004905f  mov     ecx, 0A4Ch
0x180049064  mov     [rsp+140h+var_CC], cx
0x180049069  cmp     eax, 1
0x18004906c  jz      loc_180049330
0x180049072  mov     rcx, [rbp+40h+var_98]
0x180049076  mov     rax, [rcx]
0x180049079  lea     rdx, [rsp+140h+var_E0]
0x18004907e  mov     rax, [rax+80h]
0x180049085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004908a  mov     [rsp+140h+var_D0], eax
0x18004908e  test    eax, eax
0x180049090  mov     eax, 0A52h
0x180049095  js      loc_18004934B
0x18004909b  mov     [rsp+140h+var_CC], ax
0x1800490a0  test    byte ptr [rsp+140h+var_E0], 10h
0x1800490a5  jnz     short loc_18004902F
0x1800490a7  mov     rcx, [rsp+140h+pv]; pv
0x1800490ac  call    cs:__imp_CoTaskMemFree
0x1800490b2  mov     [rsp+140h+pv], 0
0x1800490bb  mov     rcx, [rsp+140h+var_E8]; pv
0x1800490c0  call    cs:__imp_CoTaskMemFree
0x1800490c6  mov     [rsp+140h+var_E8], 0
0x1800490cf  mov     rcx, [rbp+40h+var_98]
0x1800490d3  mov     rax, [rcx]
0x1800490d6  lea     rdx, [rsp+140h+pv]
0x1800490db  mov     rax, [rax+20h]
0x1800490df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800490e4  mov     [rsp+140h+var_D0], eax
0x1800490e8  xor     ecx, ecx
0x1800490ea  test    eax, eax
0x1800490ec  mov     eax, 0A5Dh
0x1800490f1  js      loc_18004934B
0x1800490f7  mov     [rsp+140h+var_CC], ax
0x1800490fc  mov     rax, [rsp+140h+pv]
0x180049101  cmp     word ptr [rax], 2Eh ; '.'
0x180049105  jnz     short loc_180049122
0x180049107  cmp     [rax+2], cx
0x18004910b  jz      loc_18004902F
0x180049111  cmp     word ptr [rax+2], 2Eh ; '.'
0x180049116  jnz     short loc_180049122
0x180049118  cmp     [rax+4], cx
0x18004911c  jz      loc_18004902F
0x180049122  mov     rcx, [rbp+40h+var_98]
0x180049126  mov     rax, [rcx]
0x180049129  lea     rdx, [rsp+140h+var_E8]
0x18004912e  mov     rax, [rax+18h]
0x180049132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049137  mov     [rsp+140h+var_D0], eax
0x18004913b  test    eax, eax
0x18004913d  mov     eax, 0A64h
0x180049142  js      loc_18004934B
0x180049148  mov     [rsp+140h+var_CC], ax
0x18004914d  mov     r8, [rsp+140h+pv]; unsigned __int16 *
0x180049152  mov     rdx, [rsp+140h+var_E8]; unsigned __int16 *
0x180049157  lea     rcx, [rbp+40h+var_70]; this
0x18004915b  call    ?Set@CBsString@@QEAAJPEBG0@Z; CBsString::Set(ushort const *,ushort const *)
0x180049160  mov     [rsp+140h+var_D0], eax
0x180049164  test    eax, eax
0x180049166  mov     eax, 0A65h
0x18004916b  js      loc_18004934B
0x180049171  mov     [rsp+140h+var_CC], ax
0x180049176  lea     rcx, [rsp+140h+var_D8]
0x18004917b  call    ?Release@?$CComPtrBase@UISdUniCursor@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISdUniCursor>::Release(void)
0x180049180  mov     rcx, [rbp+40h+var_90]
0x180049184  mov     rax, [rcx]
0x180049187  lea     r8, [rsp+140h+var_D8]
0x18004918c  lea     rdx, IID_ISdFileRecord
0x180049193  mov     rax, [rax+18h]
0x180049197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004919c  mov     [rsp+140h+var_D0], eax
0x1800491a0  test    eax, eax
0x1800491a2  mov     eax, 0A6Dh
0x1800491a7  js      loc_18004934B
0x1800491ad  mov     [rsp+140h+var_CC], ax
0x1800491b2  mov     rcx, [rsp+140h+var_D8]
0x1800491b7  mov     rax, [rcx]
0x1800491ba  lea     rdx, [rsp+140h+var_E0]
0x1800491bf  mov     rax, [rax+80h]
0x1800491c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800491cb  mov     [rsp+140h+var_D0], eax
0x1800491cf  test    eax, eax
0x1800491d1  mov     eax, 0A6Fh
0x1800491d6  js      loc_18004934B
0x1800491dc  mov     [rsp+140h+var_CC], ax
0x1800491e1  test    byte ptr [rsp+140h+var_E0], 10h
0x1800491e6  jnz     short loc_180049176
0x1800491e8  mov     rcx, [rsp+140h+pv]; pv
0x1800491ed  call    cs:__imp_CoTaskMemFree
0x1800491f3  mov     [rsp+140h+pv], 0
0x1800491fc  mov     rcx, [rsp+140h+var_E8]; pv
0x180049201  call    cs:__imp_CoTaskMemFree
0x180049207  mov     [rsp+140h+var_E8], 0
0x180049210  mov     rcx, [rsp+140h+var_D8]
0x180049215  mov     rax, [rcx]
0x180049218  lea     rdx, [rsp+140h+pv]
0x18004921d  mov     rax, [rax+20h]
0x180049221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049226  mov     [rsp+140h+var_D0], eax
0x18004922a  xor     ecx, ecx
0x18004922c  test    eax, eax
0x18004922e  mov     eax, 0A79h
0x180049233  js      loc_18004934B
0x180049239  mov     [rsp+140h+var_CC], ax
0x18004923e  mov     rax, [rsp+140h+pv]
0x180049243  cmp     word ptr [rax], 2Eh ; '.'
0x180049247  jnz     short loc_180049264
0x180049249  cmp     [rax+2], cx
0x18004924d  jz      loc_180049176
0x180049253  cmp     word ptr [rax+2], 2Eh ; '.'
0x180049258  jnz     short loc_180049264
0x18004925a  cmp     [rax+4], cx
0x18004925e  jz      loc_180049176
0x180049264  mov     rcx, [rsp+140h+var_D8]
0x180049269  mov     rax, [rcx]
0x18004926c  lea     rdx, [rsp+140h+var_E8]
0x180049271  mov     rax, [rax+18h]
0x180049275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004927a  mov     [rsp+140h+var_D0], eax
0x18004927e  test    eax, eax
0x180049280  mov     eax, 0A7Fh
0x180049285  js      loc_18004934B
0x18004928b  mov     [rsp+140h+var_CC], ax
0x180049290  mov     r8, [rsp+140h+pv]; unsigned __int16 *
0x180049295  mov     rdx, [rsp+140h+var_E8]; unsigned __int16 *
0x18004929a  lea     rcx, [rbp+40h+var_80]; this
0x18004929e  call    ?Set@CBsString@@QEAAJPEBG0@Z; CBsString::Set(ushort const *,ushort const *)
0x1800492a3  mov     [rsp+140h+var_D0], eax
0x1800492a7  test    eax, eax
0x1800492a9  mov     eax, 0A80h
0x1800492ae  js      loc_18004934B
0x1800492b4  mov     [rsp+140h+var_CC], ax
0x1800492b9  inc     rsi
0x1800492bc  mov     rax, [rbp+40h+var_70]
0x1800492c0  mov     r8, [rbp+40h+var_80]
0x1800492c4  sub     r8, rax
0x1800492c7  movzx   edx, word ptr [rax]
0x1800492ca  movzx   ecx, word ptr [rax+r8]
0x1800492cf  sub     edx, ecx
0x1800492d1  jnz     short loc_1800492DB
0x1800492d3  add     rax, 2
0x1800492d7  test    ecx, ecx
0x1800492d9  jnz     short loc_1800492C7
0x1800492db  test    edx, edx
0x1800492dd  jnz     loc_180049176
0x1800492e3  mov     rcx, [rsp+140h+var_D8]
0x1800492e8  mov     rax, [rcx]
0x1800492eb  lea     rdx, [rbp+40h+var_50]
0x1800492ef  mov     rax, [rax+60h]
0x1800492f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800492f8  mov     [rsp+140h+var_D0], eax
0x1800492fc  test    eax, eax
0x1800492fe  mov     eax, 0A85h
0x180049303  js      short loc_18004934B
0x180049305  mov     [rsp+140h+var_CC], ax
0x18004930a  inc     rdi
0x18004930d  mov     rax, qword ptr [rbp+40h+var_50]
0x180049311  sub     rax, [r13+0]
0x180049315  jnz     short loc_18004931F
0x180049317  mov     rax, qword ptr [rbp+40h+var_50+8]
0x18004931b  sub     rax, [r13+8]
0x18004931f  test    rax, rax
0x180049322  jz      loc_18004902F
0x180049328  inc     rbx
0x18004932b  jmp     loc_18004902F
0x180049330  mov     [r12], rdi
0x180049334  mov     [r14], rsi
0x180049337  mov     [r15], rbx
0x18004933a  jmp     short loc_180049350
0x18004933c  mov     eax, 0A4Ch
0x180049341  jmp     short loc_18004934B
0x180049343  mov     [rsp+140h+var_D0], 80070057h
0x18004934b  mov     [rsp+140h+var_CA], ax
  ... truncated ...
```
