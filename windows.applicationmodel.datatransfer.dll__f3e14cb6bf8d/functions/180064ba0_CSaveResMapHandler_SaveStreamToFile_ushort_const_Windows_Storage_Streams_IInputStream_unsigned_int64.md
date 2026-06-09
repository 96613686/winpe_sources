# CSaveResMapHandler::_SaveStreamToFile(ushort const *,Windows::Storage::Streams::IInputStream *,unsigned __int64)

- ea: `0x180064ba0`
- end: `0x180064d6a`
- name: `?_SaveStreamToFile@CSaveResMapHandler@@AEAAJPEBGPEAUIInputStream@Streams@Storage@Windows@@_K@Z`
- size: `458`
- prototype: `__int64 __fastcall(CSaveResMapHandler *this, const unsigned __int16 *, struct Windows::Storage::Streams::IInputStream *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180064880`

## callees

- `0x180008b68`
- `0x18000dfb8`
- `0x1800615b8`
- `0x180064ba0`
- `0x180081010`

## import_xrefs

- `SHCORE!SHCreateStreamOnFileEx` at `0x180064be6`
- `SHCORE!SHCreateStreamOnFileEx` at `0x180064be6`
- `SHCORE!CreateRandomAccessStreamOverStream` at `0x180064c17`
- `SHCORE!CreateRandomAccessStreamOverStream` at `0x180064c17`
- `SHCORE!__imp_RandomAccessStreamCopyAsync` at `0x180064c7c`
- `SHCORE!__imp_RandomAccessStreamCopyAsync` at `0x180064c7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSaveResMapHandler::_SaveStreamToFile(
        CSaveResMapHandler *this,
        const unsigned __int16 *a2,
        struct Windows::Storage::Streams::IInputStream *a3,
        __int64 a4)
{
  HRESULT RandomAccessStreamOverStream; // ebx
  __int64 v8; // rax
  _QWORD *v9; // rdi
  IStream *v10; // rsi
  __int64 v11; // rdx
  IStream **v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  IStream *v16; // rcx
  IStream *ppstm; // [rsp+30h] [rbp-20h] BYREF
  __int64 v19; // [rsp+38h] [rbp-18h] BYREF
  __int64 v20; // [rsp+40h] [rbp-10h] BYREF
  __int64 v21; // [rsp+48h] [rbp-8h] BYREF

  ppstm = 0;
  RandomAccessStreamOverStream = SHCreateStreamOnFileEx(a2, 0x21u, 0x4000100u, 1, 0, &ppstm);
  if ( RandomAccessStreamOverStream >= 0 )
  {
    v21 = 0;
    v8 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v21);
    RandomAccessStreamOverStream = CreateRandomAccessStreamOverStream(
                                     ppstm,
                                     0,
                                     &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da,
                                     v8);
    if ( RandomAccessStreamOverStream >= 0 )
    {
      v20 = 0;
      RandomAccessStreamOverStream = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 72LL))(
                                       v21,
                                       0,
                                       &v20);
      if ( RandomAccessStreamOverStream >= 0 )
      {
        v19 = 0;
        RandomAccessStreamOverStream = RandomAccessStreamCopyAsync(
                                         a3,
                                         v20,
                                         a4,
                                         3,
                                         &GUID_8f1db6e3_6556_5516_825c_1021ee27cd0c,
                                         &v19);
        if ( RandomAccessStreamOverStream >= 0 )
        {
          RandomAccessStreamOverStream = WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>(v19);
          if ( RandomAccessStreamOverStream >= 0 )
          {
            v9 = (_QWORD *)((char *)this + 536);
            v10 = ppstm;
            RandomAccessStreamOverStream = 0;
            v11 = v9[1];
            if ( v11 != v9[3]
              || (RandomAccessStreamOverStream = CTSimpleArray<IStream *,4294967294,CTPolicyCoTaskMem<IStream *>,CSimpleArrayStandardCompareHelper<IStream *>,CSimpleArrayStandardMergeHelper<IStream *>>::EnsureCapacity(
                                                   v9,
                                                   v11 + 1),
                  RandomAccessStreamOverStream >= 0) )
            {
              v12 = (IStream **)(*v9 + 8 * v9[1]++);
              if ( v12 )
                *v12 = v10;
            }
            if ( RandomAccessStreamOverStream >= 0 )
              ppstm = 0;
          }
        }
        v13 = v19;
        if ( v19 )
        {
          v19 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
      }
      v14 = v20;
      if ( v20 )
      {
        v20 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
    v15 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  v16 = ppstm;
  if ( ppstm )
  {
    ppstm = 0;
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return (unsigned int)RandomAccessStreamOverStream;
}

```

## disassembly

```asm
0x180064ba0  push    rbp
0x180064ba2  push    rbx
0x180064ba3  push    rsi
0x180064ba4  push    rdi
0x180064ba5  push    r14
0x180064ba7  mov     rbp, rsp
0x180064baa  sub     rsp, 50h
0x180064bae  mov     rsi, r9
0x180064bb1  mov     r14, r8
0x180064bb4  mov     rax, rdx
0x180064bb7  mov     rdi, rcx
0x180064bba  mov     [rbp+var_20], 0
0x180064bc2  lea     rcx, [rbp+var_20]
0x180064bc6  mov     [rsp+50h+ppstm], rcx; ppstm
0x180064bcb  mov     [rsp+50h+pstmTemplate], 0; pstmTemplate
0x180064bd4  mov     edx, 21h ; '!'; grfMode
0x180064bd9  lea     r9d, [rdx-20h]; fCreate
0x180064bdd  mov     r8d, 4000100h; dwAttributes
0x180064be3  mov     rcx, rax; pszFile
0x180064be6  call    cs:__imp_SHCreateStreamOnFileEx
0x180064bec  mov     ebx, eax
0x180064bee  test    eax, eax
0x180064bf0  js      loc_180064D3F
0x180064bf6  mov     [rbp+var_8], 0
0x180064bfe  lea     rcx, [rbp+var_8]
0x180064c02  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x180064c07  mov     r9, rax
0x180064c0a  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x180064c11  xor     edx, edx
0x180064c13  mov     rcx, [rbp+var_20]
0x180064c17  call    cs:__imp_CreateRandomAccessStreamOverStream
0x180064c1d  mov     ebx, eax
0x180064c1f  test    eax, eax
0x180064c21  js      loc_180064D21
0x180064c27  mov     [rbp+var_10], 0
0x180064c2f  mov     rcx, [rbp+var_8]
0x180064c33  mov     rax, [rcx]
0x180064c36  lea     r8, [rbp+var_10]
0x180064c3a  xor     edx, edx
0x180064c3c  mov     rax, [rax+48h]
0x180064c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064c45  mov     ebx, eax
0x180064c47  test    eax, eax
0x180064c49  js      loc_180064D03
0x180064c4f  mov     [rbp+var_18], 0
0x180064c57  lea     rax, [rbp+var_18]
0x180064c5b  mov     [rsp+50h+ppstm], rax
0x180064c60  lea     rax, _GUID_8f1db6e3_6556_5516_825c_1021ee27cd0c
0x180064c67  mov     [rsp+50h+pstmTemplate], rax
0x180064c6c  mov     r9d, 3
0x180064c72  mov     r8, rsi
0x180064c75  mov     rdx, [rbp+var_10]
0x180064c79  mov     rcx, r14
0x180064c7c  call    cs:__imp_RandomAccessStreamCopyAsync
0x180064c82  mov     ebx, eax
0x180064c84  test    eax, eax
0x180064c86  js      short loc_180064CE5
0x180064c88  mov     rcx, [rbp+var_18]
0x180064c8c  call    ??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@_K_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@_K_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@_K_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64> *,tagCOWAIT_FLAGS,void *)
0x180064c91  mov     ebx, eax
0x180064c93  test    eax, eax
0x180064c95  js      short loc_180064CE5
0x180064c97  add     rdi, 218h
0x180064c9e  mov     rsi, [rbp+var_20]
0x180064ca2  xor     ebx, ebx
0x180064ca4  mov     rdx, [rdi+8]
0x180064ca8  cmp     rdx, [rdi+18h]
0x180064cac  jnz     short loc_180064CBF
0x180064cae  inc     rdx
0x180064cb1  mov     rcx, rdi
0x180064cb4  call    ?EnsureCapacity@?$CTSimpleArray@PEAUIStream@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUIStream@@@@V?$CSimpleArrayStandardCompareHelper@PEAUIStream@@@@V?$CSimpleArrayStandardMergeHelper@PEAUIStream@@@@@@QEAAJ_K@Z; CTSimpleArray<IStream *,4294967294,CTPolicyCoTaskMem<IStream *>,CSimpleArrayStandardCompareHelper<IStream *>,CSimpleArrayStandardMergeHelper<IStream *>>::EnsureCapacity(unsigned __int64)
0x180064cb9  mov     ebx, eax
0x180064cbb  test    eax, eax
0x180064cbd  js      short loc_180064CD9
0x180064cbf  inc     qword ptr [rdi+8]
0x180064cc3  mov     rdx, [rdi+8]
0x180064cc7  mov     rax, [rdi]
0x180064cca  dec     rdx
0x180064ccd  lea     rdx, [rax+rdx*8]
0x180064cd1  test    rdx, rdx
0x180064cd4  jz      short loc_180064CD9
0x180064cd6  mov     [rdx], rsi
0x180064cd9  test    ebx, ebx
0x180064cdb  js      short loc_180064CE5
0x180064cdd  mov     [rbp+var_20], 0
0x180064ce5  mov     rcx, [rbp+var_18]
0x180064ce9  test    rcx, rcx
0x180064cec  jz      short loc_180064D03
0x180064cee  mov     [rbp+var_18], 0
0x180064cf6  mov     rax, [rcx]
0x180064cf9  mov     rax, [rax+10h]
0x180064cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d02  nop
0x180064d03  mov     rcx, [rbp+var_10]
0x180064d07  test    rcx, rcx
0x180064d0a  jz      short loc_180064D21
0x180064d0c  mov     [rbp+var_10], 0
0x180064d14  mov     rax, [rcx]
0x180064d17  mov     rax, [rax+10h]
0x180064d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d20  nop
0x180064d21  mov     rcx, [rbp+var_8]
0x180064d25  test    rcx, rcx
0x180064d28  jz      short loc_180064D3F
0x180064d2a  mov     [rbp+var_8], 0
0x180064d32  mov     rax, [rcx]
0x180064d35  mov     rax, [rax+10h]
0x180064d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d3e  nop
0x180064d3f  mov     rcx, [rbp+var_20]
0x180064d43  test    rcx, rcx
0x180064d46  jz      short loc_180064D5D
0x180064d48  mov     [rbp+var_20], 0
0x180064d50  mov     rax, [rcx]
0x180064d53  mov     rax, [rax+10h]
0x180064d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d5c  nop
0x180064d5d  mov     eax, ebx
0x180064d5f  add     rsp, 50h
0x180064d63  pop     r14
0x180064d65  pop     rdi
0x180064d66  pop     rsi
0x180064d67  pop     rbx
0x180064d68  pop     rbp
0x180064d69  retn
```
