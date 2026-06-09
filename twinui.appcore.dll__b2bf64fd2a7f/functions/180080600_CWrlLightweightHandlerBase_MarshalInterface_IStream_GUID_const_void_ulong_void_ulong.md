# CWrlLightweightHandlerBase::MarshalInterface(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x180080600`
- end: `0x1800807fb`
- name: `?MarshalInterface@CWrlLightweightHandlerBase@@UEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `507`
- prototype: `__int64 __usercall@<rax>(CWrlLightweightHandlerBase *__hidden this@<rcx>, struct IStream *pstm@<rdx>, const struct _GUID *@<r8>, void *@<r9>, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800040e0`
- `0x1800157b0`
- `0x180016694`
- `0x180036d70`
- `0x18004b430`
- `0x180080600`
- `0x1800808fc`
- `0x180085010`

## import_xrefs

- `SHCORE!IStream_Write` at `0x1800806c6`
- `SHCORE!IStream_Write` at `0x1800807ce`
- `SHCORE!IStream_Write` at `0x1800806c6`
- `SHCORE!IStream_Write` at `0x1800807ce`

## pseudocode

```c
__int64 __fastcall CWrlLightweightHandlerBase::MarshalInterface(
        CWrlLightweightHandlerBase *this,
        struct IStream *pstm,
        const struct _GUID *a3,
        void *a4,
        unsigned int a5,
        void *a6,
        unsigned int a7)
{
  const struct _GUID *v11; // rdx
  HRESULT StdMarshaler; // edi
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  void *v16; // rcx
  ULONG cb; // [rsp+40h] [rbp-38h] BYREF
  void *v19; // [rsp+48h] [rbp-30h] BYREF
  void *pv; // [rsp+50h] [rbp-28h] BYREF
  __int64 v21; // [rsp+58h] [rbp-20h] BYREF
  __int64 v22; // [rsp+60h] [rbp-18h] BYREF
  unsigned __int64 v23; // [rsp+68h] [rbp-10h] BYREF

  v19 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  StdMarshaler = CWrlLightweightHandlerBase::_GetStdMarshaler(this, v11, &v19);
  if ( StdMarshaler >= 0 )
  {
    StdMarshaler = (*(__int64 (__fastcall **)(void *, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int))(*(_QWORD *)v19 + 40LL))(
                     v19,
                     pstm,
                     a3,
                     a4,
                     a5,
                     a6,
                     a7);
    if ( StdMarshaler >= 0 )
    {
      StdMarshaler = (*(__int64 (__fastcall **)(CWrlLightweightHandlerBase *, const struct _GUID *, void *, _QWORD, void *, unsigned int, char *))(*(_QWORD *)this + 80LL))(
                       this,
                       a3,
                       a4,
                       a5,
                       a6,
                       a7,
                       (char *)this + 16);
      if ( StdMarshaler >= 0 )
      {
        StdMarshaler = IStream_Write(pstm, (char *)this + 16, 4u);
        if ( StdMarshaler >= 0 )
        {
          v13 = *(_QWORD *)pstm;
          v22 = 0;
          StdMarshaler = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, __int64 *))(v13 + 40))(
                           pstm,
                           0,
                           1,
                           &v22);
          if ( StdMarshaler >= 0 )
          {
            StdMarshaler = (*(__int64 (__fastcall **)(CWrlLightweightHandlerBase *, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int))(*(_QWORD *)this + 88LL))(
                             this,
                             pstm,
                             a3,
                             a4,
                             a5,
                             a6,
                             a7);
            if ( StdMarshaler >= 0 )
            {
              v14 = *(_QWORD *)pstm;
              v21 = 0;
              StdMarshaler = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, __int64 *))(v14 + 40))(
                               pstm,
                               0,
                               1,
                               &v21);
              if ( StdMarshaler >= 0 )
              {
                v15 = *((unsigned int *)this + 4);
                if ( v21 - v22 <= v15 )
                {
                  if ( v21 - v22 < v15 )
                  {
                    cb = 0;
                    StdMarshaler = ULongLongToULong(v15 - (v21 - v22), &cb);
                    if ( StdMarshaler >= 0 )
                    {
                      pv = 0;
                      v23 = 0;
                      StdMarshaler = ULongLongMult(cb, 1u, &v23);
                      if ( StdMarshaler >= 0 )
                      {
                        StdMarshaler = CTCoAllocPolicy::Alloc(v16, 1u, v23, &pv);
                        if ( StdMarshaler >= 0 )
                          StdMarshaler = IStream_Write(pstm, pv, cb);
                      }
                      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pv);
                    }
                  }
                }
                else
                {
                  StdMarshaler = -2147467259;
                }
              }
            }
          }
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  return (unsigned int)StdMarshaler;
}

```

## disassembly

```asm
0x180080600  push    rbp
0x180080602  push    rbx
0x180080603  push    rsi
0x180080604  push    rdi
0x180080605  push    r12
0x180080607  push    r13
0x180080609  push    r14
0x18008060b  push    r15
0x18008060d  mov     rbp, rsp
0x180080610  sub     rsp, 78h
0x180080614  mov     r14, rcx
0x180080617  mov     [rbp+var_30], 0
0x18008061f  lea     rcx, [rbp+var_30]
0x180080623  mov     r12, r9
0x180080626  mov     r13, r8
0x180080629  mov     rsi, rdx
0x18008062c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180080631  lea     r8, [rbp+var_30]; void **
0x180080635  mov     rcx, r14; this
0x180080638  call    ?_GetStdMarshaler@CWrlLightweightHandlerBase@@IEAAJAEBU_GUID@@PEAPEAX@Z; CWrlLightweightHandlerBase::_GetStdMarshaler(_GUID const &,void * *)
0x18008063d  mov     edi, eax
0x18008063f  test    eax, eax
0x180080641  js      loc_1800807DF
0x180080647  mov     rdx, [rbp+arg_28]
0x18008064b  mov     r9, r12
0x18008064e  mov     rcx, [rbp+var_30]
0x180080652  mov     r8, r13
0x180080655  mov     ebx, [rbp+arg_30]
0x180080658  mov     dword ptr [rsp+78h+var_48], ebx
0x18008065c  mov     [rsp+78h+var_50], rdx
0x180080661  mov     rax, [rcx]
0x180080664  mov     edx, [rbp+arg_20]
0x180080667  mov     dword ptr [rsp+78h+var_58], edx
0x18008066b  mov     rdx, rsi
0x18008066e  mov     rax, [rax+28h]
0x180080672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080677  mov     edi, eax
0x180080679  test    eax, eax
0x18008067b  js      loc_1800807DF
0x180080681  mov     rax, [r14]
0x180080684  lea     r15, [r14+10h]
0x180080688  mov     rcx, [rbp+arg_28]
0x18008068c  mov     r8, r12
0x18008068f  mov     r9d, [rbp+arg_20]
0x180080693  mov     rdx, r13
0x180080696  mov     [rsp+78h+var_48], r15
0x18008069b  mov     rax, [rax+50h]
0x18008069f  mov     dword ptr [rsp+78h+var_50], ebx
0x1800806a3  mov     [rsp+78h+var_58], rcx
0x1800806a8  mov     rcx, r14
0x1800806ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800806b0  mov     edi, eax
0x1800806b2  test    eax, eax
0x1800806b4  js      loc_1800807DF
0x1800806ba  mov     r8d, 4; cb
0x1800806c0  mov     rdx, r15; pv
0x1800806c3  mov     rcx, rsi; pstm
0x1800806c6  call    cs:__imp_IStream_Write
0x1800806cc  mov     edi, eax
0x1800806ce  test    eax, eax
0x1800806d0  js      loc_1800807DF
0x1800806d6  mov     rax, [rsi]
0x1800806d9  lea     r9, [rbp+var_18]
0x1800806dd  xor     ebx, ebx
0x1800806df  mov     rcx, rsi
0x1800806e2  mov     edx, ebx
0x1800806e4  mov     [rbp+var_18], rbx
0x1800806e8  mov     rax, [rax+28h]
0x1800806ec  lea     r8d, [rbx+1]
0x1800806f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800806f5  mov     edi, eax
0x1800806f7  test    eax, eax
0x1800806f9  js      loc_1800807DF
0x1800806ff  mov     ecx, [rbp+arg_30]
0x180080702  mov     r9, r12
0x180080705  mov     rax, [r14]
0x180080708  mov     r8, r13
0x18008070b  mov     dword ptr [rsp+78h+var_48], ecx
0x18008070f  mov     rdx, rsi
0x180080712  mov     rcx, [rbp+arg_28]
0x180080716  mov     [rsp+78h+var_50], rcx
0x18008071b  mov     ecx, [rbp+arg_20]
0x18008071e  mov     rax, [rax+58h]
0x180080722  mov     dword ptr [rsp+78h+var_58], ecx
0x180080726  mov     rcx, r14
0x180080729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008072e  xor     r14d, r14d
0x180080731  mov     edi, eax
0x180080733  test    eax, eax
0x180080735  js      loc_1800807DF
0x18008073b  mov     rax, [rsi]
0x18008073e  lea     r12d, [rbx+1]
0x180080742  lea     r9, [rbp+var_20]
0x180080746  mov     [rbp+var_20], r14
0x18008074a  mov     r8d, r12d
0x18008074d  mov     edx, ebx
0x18008074f  mov     rcx, rsi
0x180080752  mov     rax, [rax+28h]
0x180080756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008075b  mov     edi, eax
0x18008075d  test    eax, eax
0x18008075f  js      short loc_1800807DF
0x180080761  mov     rax, [rbp+var_20]
0x180080765  sub     rax, [rbp+var_18]
0x180080769  mov     ecx, [r15]
0x18008076c  cmp     rax, rcx
0x18008076f  jbe     short loc_180080778
0x180080771  mov     edi, 80004005h
0x180080776  jmp     short loc_1800807DF
0x180080778  jnb     short loc_1800807DF
0x18008077a  sub     rcx, rax; unsigned __int64
0x18008077d  mov     [rbp+cb], r14d
0x180080781  lea     rdx, [rbp+cb]; unsigned int *
0x180080785  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18008078a  mov     edi, eax
0x18008078c  test    eax, eax
0x18008078e  js      short loc_1800807DF
0x180080790  mov     ecx, [rbp+cb]; unsigned __int64
0x180080793  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180080797  mov     rdx, r12; unsigned __int64
0x18008079a  mov     [rbp+pv], r14
0x18008079e  mov     [rbp+var_10], r14
0x1800807a2  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800807a7  mov     edi, eax
0x1800807a9  test    eax, eax
0x1800807ab  js      short loc_1800807D6
0x1800807ad  mov     r8, [rbp+var_10]; unsigned __int64
0x1800807b1  lea     r9, [rbp+pv]; void **
0x1800807b5  mov     edx, r12d; unsigned int
0x1800807b8  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800807bd  mov     edi, eax
0x1800807bf  test    eax, eax
0x1800807c1  js      short loc_1800807D6
0x1800807c3  mov     r8d, [rbp+cb]; cb
0x1800807c7  mov     rcx, rsi; pstm
0x1800807ca  mov     rdx, [rbp+pv]; pv
0x1800807ce  call    cs:__imp_IStream_Write
0x1800807d4  mov     edi, eax
0x1800807d6  lea     rcx, [rbp+pv]
0x1800807da  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800807df  lea     rcx, [rbp+var_30]
0x1800807e3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800807e8  mov     eax, edi
0x1800807ea  add     rsp, 78h
0x1800807ee  pop     r15
0x1800807f0  pop     r14
0x1800807f2  pop     r13
0x1800807f4  pop     r12
0x1800807f6  pop     rdi
0x1800807f7  pop     rsi
0x1800807f8  pop     rbx
0x1800807f9  pop     rbp
0x1800807fa  retn
```
