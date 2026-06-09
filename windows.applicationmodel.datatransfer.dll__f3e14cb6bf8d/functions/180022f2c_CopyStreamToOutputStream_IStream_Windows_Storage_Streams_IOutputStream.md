# CopyStreamToOutputStream(IStream *,Windows::Storage::Streams::IOutputStream *)

- ea: `0x180022f2c`
- end: `0x1800230a9`
- name: `?CopyStreamToOutputStream@@YAJPEAUIStream@@PEAUIOutputStream@Streams@Storage@Windows@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(struct IStream *, struct Windows::Storage::Streams::IOutputStream *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180039230`
- `0x1800392c0`

## callees

- `0x180002ad0`
- `0x18000dfb8`
- `0x180022f2c`
- `0x180043b6c`
- `0x180081010`

## import_xrefs

- `SHCORE!IStream_Reset` at `0x180022f4f`
- `SHCORE!IStream_Reset` at `0x180022f4f`
- `SHCORE!CreateRandomAccessStreamOverStream` at `0x180022f77`
- `SHCORE!CreateRandomAccessStreamOverStream` at `0x180022f77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022fab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180022fab`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022fe9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022fe9`

## string_xrefs

- `0x180022fa4`: `Windows.Storage.Streams.RandomAccessStream`

## pseudocode

```c
__int64 __fastcall CopyStreamToOutputStream(struct IStream *a1, struct Windows::Storage::Streams::IOutputStream *a2)
{
  HRESULT ActivationFactory; // ebx
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-40h] BYREF
  __int64 v13; // [rsp+38h] [rbp-38h] BYREF
  __int64 v14; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF

  ActivationFactory = IStream_Reset(a1);
  if ( ActivationFactory >= 0 )
  {
    v14 = 0;
    ActivationFactory = CreateRandomAccessStreamOverStream(a1, 0, &GUID_905a0fe2_bc53_11df_8c49_001e4fc686da, &v14);
    if ( ActivationFactory >= 0 )
    {
      v12 = 0;
      string = 0;
      v5 = WindowsCreateStringReference(L"Windows.Storage.Streams.RandomAccessStream", 0x2Au, &hstringHeader, &string);
      if ( v5 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
        JUMPOUT(0x1800230A8LL);
      }
      ActivationFactory = RoGetActivationFactory(string, &GUID_524cedcf_6e29_4ce5_9573_6b753db66c3a, &v12);
      if ( ActivationFactory >= 0 )
      {
        v13 = 0;
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, struct Windows::Storage::Streams::IOutputStream *, __int64 *))(*(_QWORD *)v12 + 48LL))(
                              v12,
                              v14,
                              a2,
                              &v13);
        if ( ActivationFactory >= 0 )
          ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>(v13);
        v8 = v13;
        if ( v13 )
        {
          v13 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        }
      }
      v9 = v12;
      if ( v12 )
      {
        v12 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
    v10 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180022f2c  mov     [rsp-18h+arg_10], rbx
0x180022f31  push    rbp
0x180022f32  push    rsi
0x180022f33  push    rdi
0x180022f34  mov     rbp, rsp
0x180022f37  sub     rsp, 70h
0x180022f3b  mov     rax, cs:__security_cookie
0x180022f42  xor     rax, rsp
0x180022f45  mov     [rbp+var_8], rax
0x180022f49  mov     rsi, rdx
0x180022f4c  mov     rdi, rcx
0x180022f4f  call    cs:__imp_IStream_Reset
0x180022f55  mov     ebx, eax
0x180022f57  test    eax, eax
0x180022f59  js      loc_180023083
0x180022f5f  mov     [rbp+var_30], 0
0x180022f67  lea     r9, [rbp+var_30]
0x180022f6b  lea     r8, _GUID_905a0fe2_bc53_11df_8c49_001e4fc686da
0x180022f72  xor     edx, edx
0x180022f74  mov     rcx, rdi
0x180022f77  call    cs:__imp_CreateRandomAccessStreamOverStream
0x180022f7d  mov     ebx, eax
0x180022f7f  test    eax, eax
0x180022f81  js      loc_180023065
0x180022f87  mov     [rbp+var_40], 0
0x180022f8f  mov     [rbp+string], 0
0x180022f97  lea     r9, [rbp+string]; string
0x180022f9b  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180022f9f  mov     edx, 2Ah ; '*'; length
0x180022fa4  lea     rcx, ?RuntimeClass_Windows_Storage_Streams_RandomAccessStream@@3QBGB; "Windows.Storage.Streams.RandomAccessStr"...
0x180022fab  call    cs:__imp_WindowsCreateStringReference
0x180022fb1  test    eax, eax
0x180022fb3  js      loc_1800230A1
0x180022fb9  mov     rbx, [rbp+string]
0x180022fbd  mov     rcx, [rbp+var_40]
0x180022fc1  test    rcx, rcx
0x180022fc4  jz      short loc_180022FDB
0x180022fc6  mov     [rbp+var_40], 0
0x180022fce  mov     rax, [rcx]
0x180022fd1  mov     rax, [rax+10h]
0x180022fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fda  nop
0x180022fdb  lea     r8, [rbp+var_40]
0x180022fdf  lea     rdx, _GUID_524cedcf_6e29_4ce5_9573_6b753db66c3a
0x180022fe6  mov     rcx, rbx
0x180022fe9  call    cs:__imp_RoGetActivationFactory
0x180022fef  mov     ebx, eax
0x180022ff1  test    eax, eax
0x180022ff3  js      short loc_180023047
0x180022ff5  mov     [rbp+var_38], 0
0x180022ffd  mov     rcx, [rbp+var_40]
0x180023001  mov     rax, [rcx]
0x180023004  lea     r9, [rbp+var_38]
0x180023008  mov     r8, rsi
0x18002300b  mov     rdx, [rbp+var_30]
0x18002300f  mov     rax, [rax+30h]
0x180023013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023018  mov     ebx, eax
0x18002301a  test    eax, eax
0x18002301c  js      short loc_180023029
0x18002301e  mov     rcx, [rbp+var_38]
0x180023022  call    ??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@_K_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@_K_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@_K_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64> *,tagCOWAIT_FLAGS,void *)
0x180023027  mov     ebx, eax
0x180023029  mov     rcx, [rbp+var_38]
0x18002302d  test    rcx, rcx
0x180023030  jz      short loc_180023047
0x180023032  mov     [rbp+var_38], 0
0x18002303a  mov     rax, [rcx]
0x18002303d  mov     rax, [rax+10h]
0x180023041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023046  nop
0x180023047  mov     rcx, [rbp+var_40]
0x18002304b  test    rcx, rcx
0x18002304e  jz      short loc_180023065
0x180023050  mov     [rbp+var_40], 0
0x180023058  mov     rax, [rcx]
0x18002305b  mov     rax, [rax+10h]
0x18002305f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023064  nop
0x180023065  mov     rcx, [rbp+var_30]
0x180023069  test    rcx, rcx
0x18002306c  jz      short loc_180023083
0x18002306e  mov     [rbp+var_30], 0
0x180023076  mov     rax, [rcx]
0x180023079  mov     rax, [rax+10h]
0x18002307d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023082  nop
0x180023083  mov     eax, ebx
0x180023085  mov     rcx, [rbp+var_8]
0x180023089  xor     rcx, rsp; StackCookie
0x18002308c  call    __security_check_cookie
0x180023091  mov     rbx, [rsp+70h+arg_10]
0x180023099  add     rsp, 70h
0x18002309d  pop     rdi
0x18002309e  pop     rsi
0x18002309f  pop     rbp
0x1800230a0  retn
0x1800230a1  mov     ecx, eax; this
0x1800230a3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
