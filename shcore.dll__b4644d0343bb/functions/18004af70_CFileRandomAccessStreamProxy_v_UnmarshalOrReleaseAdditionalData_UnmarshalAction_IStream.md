# CFileRandomAccessStreamProxy::v_UnmarshalOrReleaseAdditionalData(UnmarshalAction,IStream *)

- ea: `0x18004af70`
- end: `0x18004b174`
- name: `?v_UnmarshalOrReleaseAdditionalData@CFileRandomAccessStreamProxy@@EEAAJW4UnmarshalAction@@PEAUIStream@@@Z`
- size: `516`
- prototype: `int __high(enum UnmarshalAction, struct IStream *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ddd4`
- `0x180011380`
- `0x1800113c0`
- `0x18004af70`
- `0x18004b17c`
- `0x18004b288`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b154`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b154`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18004b043`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x18004b043`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18004b04b`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18004b04b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CFileRandomAccessStreamProxy::v_UnmarshalOrReleaseAdditionalData(
        _QWORD *a1,
        unsigned int a2,
        IStream *a3)
{
  PWSTR v6; // rdi
  HRESULT v7; // ebx
  HRESULT v8; // eax
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, __int64 *); // rbx
  __int64 v11; // rcx
  LPVOID v12; // rcx
  LPVOID v14; // [rsp+40h] [rbp-20h] BYREF
  PWSTR ppsz; // [rsp+48h] [rbp-18h] BYREF
  __int64 v16; // [rsp+50h] [rbp-10h]
  __int64 v17; // [rsp+58h] [rbp-8h]
  LPVOID ppv; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v19; // [rsp+B8h] [rbp+58h] BYREF

  v6 = 0;
  ppsz = 0;
  v16 = 0;
  v17 = 0;
  v7 = IStream_Read(a3, a1 + 18, 4u);
  if ( v7 >= 0 )
  {
    v7 = IStream_Read(a3, (char *)a1 + 148, 4u);
    if ( v7 >= 0 )
    {
      v7 = IStream_Read(a3, a1 + 19, 4u);
      if ( v7 >= 0 )
      {
        v16 = -1;
        v17 = -1;
        v7 = IStream_ReadStr(a3, &ppsz);
        if ( v7 >= 0 )
        {
          ppv = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&ppv);
          ppv = 0;
          if ( a2 )
            v8 = CoReleaseMarshalData(a3);
          else
            v8 = CoUnmarshalInterface(a3, &GUID_bb94daad_7836_4d62_9557_2a7b83839b7b, &ppv);
          v7 = v8;
          if ( v8 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(a1 + 21);
            v7 = CRasFilePlaceholderParams::UnmarshalOrReleaseAdditionalData(a2, a3, a1 + 21);
            if ( v7 >= 0 && !a2 )
            {
              v19 = a1[21];
              v14 = ppv;
              Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(a1 + 20);
              v7 = Microsoft::WRL::Details::MakeAndInitialize<CFileRandomAccessStream,Windows::Storage::Streams::IRandomAccessStream,enum Windows::Storage::FileAccessMode,enum TransactionType &,enum SAFE_SAVE_OPTIONS &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>> &,ISafeSaveHandleManager *,CRasFilePlaceholderParams *>(
                     (int)a1 + 160,
                     (int)a1 + 144,
                     (int)a1 + 148,
                     (int)a1 + 152,
                     (__int64)&ppsz,
                     (__int64)&v14,
                     (__int64)&v19);
              if ( v7 >= 0 )
              {
                v19 = 0;
                v9 = ppv;
                v10 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v19);
                v7 = v10(v9, &v19);
                v11 = v19;
                if ( v19 )
                {
                  v19 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
                }
              }
            }
          }
          v12 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
          }
        }
        v6 = ppsz;
      }
    }
  }
  if ( v6 )
    CoTaskMemFree(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004af70  mov     [rsp-38h+arg_8], rbx
0x18004af75  push    rbp
0x18004af76  push    rsi
0x18004af77  push    rdi
0x18004af78  push    r12
0x18004af7a  push    r13
0x18004af7c  push    r14
0x18004af7e  push    r15
0x18004af80  mov     rbp, rsp
0x18004af83  sub     rsp, 60h
0x18004af87  mov     rsi, r8
0x18004af8a  mov     r15d, edx
0x18004af8d  mov     r14, rcx
0x18004af90  xor     edi, edi
0x18004af92  mov     [rbp+ppsz], rdi
0x18004af96  mov     [rbp+var_10], rdi
0x18004af9a  mov     [rbp+var_8], rdi
0x18004af9e  lea     rdx, [rcx+90h]; pv
0x18004afa5  lea     r13d, [rdi+4]
0x18004afa9  mov     r8d, r13d; cb
0x18004afac  mov     rcx, rsi; pstm
0x18004afaf  call    IStream_Read
0x18004afb4  mov     ebx, eax
0x18004afb6  test    eax, eax
0x18004afb8  js      loc_18004B14C
0x18004afbe  lea     r12, [r14+94h]
0x18004afc5  mov     r8d, r13d; cb
0x18004afc8  mov     rdx, r12; pv
0x18004afcb  mov     rcx, rsi; pstm
0x18004afce  call    IStream_Read
0x18004afd3  mov     ebx, eax
0x18004afd5  test    eax, eax
0x18004afd7  js      loc_18004B14C
0x18004afdd  lea     r13, [r14+98h]
0x18004afe4  lea     r8d, [rdi+4]; cb
0x18004afe8  mov     rdx, r13; pv
0x18004afeb  mov     rcx, rsi; pstm
0x18004afee  call    IStream_Read
0x18004aff3  mov     ebx, eax
0x18004aff5  test    eax, eax
0x18004aff7  js      loc_18004B14C
0x18004affd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004b001  mov     [rbp+var_10], rax
0x18004b005  mov     [rbp+var_8], rax
0x18004b009  lea     rdx, [rbp+ppsz]; ppsz
0x18004b00d  mov     rcx, rsi; pstm
0x18004b010  call    IStream_ReadStr
0x18004b015  mov     ebx, eax
0x18004b017  test    eax, eax
0x18004b019  js      loc_18004B148
0x18004b01f  mov     [rbp+ppv], rdi
0x18004b023  lea     rcx, [rbp+ppv]
0x18004b027  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18004b02c  mov     [rbp+ppv], rdi
0x18004b030  mov     rcx, rsi; pStm
0x18004b033  test    r15d, r15d
0x18004b036  jnz     short loc_18004B04B
0x18004b038  lea     r8, [rbp+ppv]; ppv
0x18004b03c  lea     rdx, _GUID_bb94daad_7836_4d62_9557_2a7b83839b7b; riid
0x18004b043  call    cs:__imp_CoUnmarshalInterface
0x18004b049  jmp     short loc_18004B051
0x18004b04b  call    cs:__imp_CoReleaseMarshalData
0x18004b051  mov     ebx, eax
0x18004b053  test    eax, eax
0x18004b055  js      loc_18004B12A
0x18004b05b  lea     rdi, [r14+0A8h]
0x18004b062  mov     rcx, rdi
0x18004b065  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18004b06a  mov     r8, rdi
0x18004b06d  mov     rdx, rsi
0x18004b070  mov     ecx, r15d
0x18004b073  call    ?UnmarshalOrReleaseAdditionalData@CRasFilePlaceholderParams@@SAJW4UnmarshalAction@@PEAUIStream@@PEAPEAV1@@Z; CRasFilePlaceholderParams::UnmarshalOrReleaseAdditionalData(UnmarshalAction,IStream *,CRasFilePlaceholderParams * *)
0x18004b078  mov     ebx, eax
0x18004b07a  test    eax, eax
0x18004b07c  js      loc_18004B12A
0x18004b082  test    r15d, r15d
0x18004b085  jnz     loc_18004B12A
0x18004b08b  mov     rax, [rdi]
0x18004b08e  mov     [rbp+arg_18], rax
0x18004b092  mov     rax, [rbp+ppv]
0x18004b096  mov     [rbp+var_20], rax
0x18004b09a  lea     rbx, [r14+0A0h]
0x18004b0a1  mov     rcx, rbx
0x18004b0a4  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18004b0a9  lea     rax, [rbp+arg_18]
0x18004b0ad  mov     [rsp+60h+var_30], rax
0x18004b0b2  lea     rax, [rbp+var_20]
0x18004b0b6  mov     [rsp+60h+var_38], rax
0x18004b0bb  lea     rax, [rbp+ppsz]
0x18004b0bf  mov     [rsp+60h+var_40], rax
0x18004b0c4  mov     r9, r13
0x18004b0c7  mov     r8, r12
0x18004b0ca  lea     rdx, [r14+90h]
0x18004b0d1  mov     rcx, rbx
0x18004b0d4  call    ??$MakeAndInitialize@VCFileRandomAccessStream@@UIRandomAccessStream@Streams@Storage@Windows@@W4FileAccessMode@45@AEAW4TransactionType@@AEAW4SAFE_SAVE_OPTIONS@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@5@PEAUISafeSaveHandleManager@@PEAVCRasFilePlaceholderParams@@@Details@WRL@Microsoft@@YAJPEAPEAUIRandomAccessStream@Streams@Storage@Windows@@$$QEAW4FileAccessMode@56@AEAW4TransactionType@@AEAW4SAFE_SAVE_OPTIONS@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@6@$$QEAPEAUISafeSaveHandleManager@@$$QEAPEAVCRasFilePlaceholderParams@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CFileRandomAccessStream,Windows::Storage::Streams::IRandomAccessStream,Windows::Storage::FileAccessMode,TransactionType &,SAFE_SAVE_OPTIONS &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ISafeSaveHandleManager *,CRasFilePlaceholderParams *>(Windows::Storage::Streams::IRandomAccessStream * *,Windows::Storage::FileAccessMode &&,TransactionType &,SAFE_SAVE_OPTIONS &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ISafeSaveHandleManager * &&,CRasFilePlaceholderParams * &&)
0x18004b0d9  mov     ebx, eax
0x18004b0db  test    eax, eax
0x18004b0dd  js      short loc_18004B12A
0x18004b0df  mov     [rbp+arg_18], 0
0x18004b0e7  mov     rdi, [rbp+ppv]
0x18004b0eb  mov     rax, [rdi]
0x18004b0ee  mov     rbx, [rax+18h]
0x18004b0f2  lea     rcx, [rbp+arg_18]
0x18004b0f6  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18004b0fb  lea     rdx, [rbp+arg_18]
0x18004b0ff  mov     rcx, rdi
0x18004b102  mov     rax, rbx
0x18004b105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b10a  mov     ebx, eax
0x18004b10c  mov     rcx, [rbp+arg_18]
0x18004b110  test    rcx, rcx
0x18004b113  jz      short loc_18004B12A
0x18004b115  mov     [rbp+arg_18], 0
0x18004b11d  mov     rax, [rcx]
0x18004b120  mov     rax, [rax+10h]
0x18004b124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b129  nop
0x18004b12a  mov     rcx, [rbp+ppv]
0x18004b12e  test    rcx, rcx
0x18004b131  jz      short loc_18004B148
0x18004b133  mov     [rbp+ppv], 0
0x18004b13b  mov     rax, [rcx]
0x18004b13e  mov     rax, [rax+10h]
0x18004b142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b147  nop
0x18004b148  mov     rdi, [rbp+ppsz]
0x18004b14c  test    rdi, rdi
0x18004b14f  jz      short loc_18004B15A
0x18004b151  mov     rcx, rdi; pv
0x18004b154  call    cs:__imp_CoTaskMemFree
0x18004b15a  mov     eax, ebx
0x18004b15c  mov     rbx, [rsp+60h+arg_8]
0x18004b164  add     rsp, 60h
0x18004b168  pop     r15
0x18004b16a  pop     r14
0x18004b16c  pop     r13
0x18004b16e  pop     r12
0x18004b170  pop     rdi
0x18004b171  pop     rsi
0x18004b172  pop     rbp
0x18004b173  retn
```
