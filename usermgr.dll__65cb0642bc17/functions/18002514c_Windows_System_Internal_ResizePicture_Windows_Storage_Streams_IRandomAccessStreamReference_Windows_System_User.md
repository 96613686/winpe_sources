# Windows::System::Internal::ResizePicture(Windows::Storage::Streams::IRandomAccessStreamReference *,Windows::System::UserPictureSize,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x18002514c`
- end: `0x180025406`
- name: `?ResizePicture@Internal@System@Windows@@YAJPEAUIRandomAccessStreamReference@Streams@Storage@3@W4UserPictureSize@23@PEAPEAU4563@@Z`
- size: `698`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800458e0`
- `0x1800d2674`

## callees

- `0x1800088e8`
- `0x18000ce48`
- `0x18002514c`
- `0x18002540c`
- `0x180025658`
- `0x180025adc`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800251b5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800251b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002519c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002519c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800251c6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800251c6`

## string_xrefs

- `0x180025248`: `onecore\ds\security\umstartup\usermgr\common\lib\useraccounthelper.cpp`
- `0x1800252fb`: `onecore\ds\security\umstartup\usermgr\common\lib\useraccounthelper.cpp`
- `0x180025333`: `onecore\ds\security\umstartup\usermgr\common\lib\useraccounthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::System::Internal::ResizePicture(
        __int64 a1,
        int a2,
        struct Windows::Storage::Streams::IRandomAccessStream *a3)
{
  int v5; // edx
  int v6; // edx
  unsigned int StreamReferenceFromStream; // ebx
  unsigned int v8; // esi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdx
  int v12; // eax
  struct Windows::Storage::Streams::IRandomAccessStream *v13; // rcx
  __int64 v14; // rcx
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rcx
  Windows::System::Internal *v16; // rcx
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v18)(_QWORD, GUID *, struct Windows::Storage::Streams::IRandomAccessStream **); // rdi
  int v19; // eax
  struct Windows::Storage::Streams::IRandomAccessStreamReference **v20; // r8
  struct Windows::Storage::Streams::IRandomAccessStream *v21; // rcx
  __int64 v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rcx
  Windows::System::Internal *v24; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v26; // [rsp+20h] [rbp-50h] BYREF
  __int64 v27; // [rsp+28h] [rbp-48h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, struct Windows::Storage::Streams::IRandomAccessStream **); // [rsp+30h] [rbp-40h] BYREF
  Windows::System::Internal *v29; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( a2 )
  {
    v5 = a2 - 1;
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        if ( v6 != 1 )
        {
          if ( WindowsCreateStringReference(L"Unexpected UserImageKind.", 0x19u, &hstringHeader, &string) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          StreamReferenceFromStream = -2147024809;
          RoOriginateError(2147942487LL, string);
          return StreamReferenceFromStream;
        }
        v8 = 1080;
      }
      else
      {
        v8 = 424;
      }
    }
    else
    {
      v8 = 208;
    }
  }
  else
  {
    v8 = 64;
  }
  v29 = 0;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  v10 = v9(a1, &v27);
  StreamReferenceFromStream = v10;
  if ( v10 < 0 )
  {
    v11 = 1447;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\common\\lib\\useraccounthelper.cpp",
      (const char *)(unsigned int)v10,
      (int)v26);
LABEL_38:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    return StreamReferenceFromStream;
  }
  v12 = BlockOnCompletionAndGetResults<Windows::Storage::Streams::IRandomAccessStreamWithContentType *,Windows::Storage::Streams::IRandomAccessStreamWithContentType>(
          v27,
          (__int64)&v28);
  StreamReferenceFromStream = v12;
  if ( v12 >= 0 )
  {
    v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
    v18 = **v28;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    v10 = v18(v17, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &v26);
    StreamReferenceFromStream = v10;
    if ( v10 < 0 )
    {
      v11 = 1449;
      goto LABEL_26;
    }
    v19 = ScaleAccountPictureToSize(v26, v8, &v29);
    StreamReferenceFromStream = v19;
    if ( v19 >= 0 )
    {
      StreamReferenceFromStream = Windows::System::Internal::GetStreamReferenceFromStream(v29, a3, v20);
      goto LABEL_38;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5AA,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\common\\lib\\useraccounthelper.cpp",
      (const char *)(unsigned int)v19,
      (int)v26);
    v21 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
    if ( v28 )
    {
      v28 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v23)[2])(v23);
    }
    v24 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(Windows::System::Internal *))(*(_QWORD *)v24 + 16LL))(v24);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A8,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\common\\lib\\useraccounthelper.cpp",
      (const char *)(unsigned int)v12,
      (int)v26);
    v13 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
    if ( v28 )
    {
      v28 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v15)[2])(v15);
    }
    v16 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(Windows::System::Internal *))(*(_QWORD *)v16 + 16LL))(v16);
    }
  }
  return StreamReferenceFromStream;
}

```

## disassembly

```asm
0x18002514c  mov     [rsp-28h+arg_8], rbx
0x180025151  push    rbp
0x180025152  push    rsi
0x180025153  push    rdi
0x180025154  push    r14
0x180025156  push    r15
0x180025158  mov     rbp, rsp
0x18002515b  sub     rsp, 70h
0x18002515f  mov     rax, cs:__security_cookie
0x180025166  xor     rax, rsp
0x180025169  mov     [rbp+var_10], rax
0x18002516d  mov     r14, r8
0x180025170  mov     rdi, rcx
0x180025173  xor     r15d, r15d
0x180025176  test    edx, edx
0x180025178  jz      short loc_1800251E6
0x18002517a  sub     edx, 1
0x18002517d  jz      short loc_1800251DF
0x18002517f  sub     edx, 1
0x180025182  jz      short loc_1800251D8
0x180025184  cmp     edx, 1
0x180025187  jz      short loc_1800251D1
0x180025189  lea     r9, [rbp+string]; string
0x18002518d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180025191  lea     edx, [r15+19h]; length
0x180025195  lea     rcx, aUnexpectedUser; "Unexpected UserImageKind."
0x18002519c  call    cs:__imp_WindowsCreateStringReference
0x1800251a2  test    eax, eax
0x1800251a4  jns     short loc_1800251BB
0x1800251a6  xor     r9d, r9d; lpArguments
0x1800251a9  xor     r8d, r8d; nNumberOfArguments
0x1800251ac  lea     edx, [r15+1]; dwExceptionFlags
0x1800251b0  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800251b5  call    cs:__imp_RaiseException
0x1800251bb  mov     rdx, [rbp+string]
0x1800251bf  mov     ebx, 80070057h
0x1800251c4  mov     ecx, ebx
0x1800251c6  call    cs:__imp_RoOriginateError
0x1800251cc  jmp     loc_1800253E4
0x1800251d1  mov     esi, 438h
0x1800251d6  jmp     short loc_1800251EB
0x1800251d8  mov     esi, 1A8h
0x1800251dd  jmp     short loc_1800251EB
0x1800251df  mov     esi, 0D0h
0x1800251e4  jmp     short loc_1800251EB
0x1800251e6  mov     esi, 40h ; '@'
0x1800251eb  mov     [rbp+var_38], r15
0x1800251ef  mov     [rbp+var_40], r15
0x1800251f3  mov     [rbp+var_48], r15
0x1800251f7  mov     [rbp+var_50], r15
0x1800251fb  mov     rax, [rcx]
0x1800251fe  mov     rbx, [rax+30h]
0x180025202  lea     rcx, [rbp+var_48]
0x180025206  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002520b  lea     rdx, [rbp+var_48]
0x18002520f  mov     rcx, rdi
0x180025212  mov     rax, rbx
0x180025215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002521a  mov     ebx, eax
0x18002521c  test    eax, eax
0x18002521e  jns     short loc_18002522A
0x180025220  mov     edx, 5A7h
0x180025225  jmp     loc_1800252FB
0x18002522a  lea     rdx, [rbp+var_40]
0x18002522e  mov     rcx, [rbp+var_48]
0x180025232  call    ??$BlockOnCompletionAndGetResults@PEAUIRandomAccessStreamWithContentType@Streams@Storage@Windows@@U1234@@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStreamWithContentType@Streams@Storage@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIRandomAccessStreamWithContentType@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Storage::Streams::IRandomAccessStreamWithContentType *,Windows::Storage::Streams::IRandomAccessStreamWithContentType>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStreamWithContentType *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStreamWithContentType>>,tagCOWAIT_FLAGS,void *)
0x180025237  mov     ebx, eax
0x180025239  test    eax, eax
0x18002523b  jns     loc_1800252C7
0x180025241  mov     rcx, [rbp+28h]; this
0x180025245  mov     r9d, eax; char *
0x180025248  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\umstartup\\userm"...
0x18002524f  mov     edx, 5A8h; void *
0x180025254  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025259  nop
0x18002525a  mov     rcx, [rbp+var_50]
0x18002525e  test    rcx, rcx
0x180025261  jz      short loc_180025274
0x180025263  mov     [rbp+var_50], r15
0x180025267  mov     rax, [rcx]
0x18002526a  mov     rax, [rax+10h]
0x18002526e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025273  nop
0x180025274  mov     rcx, [rbp+var_48]
0x180025278  test    rcx, rcx
0x18002527b  jz      short loc_18002528E
0x18002527d  mov     [rbp+var_48], r15
0x180025281  mov     rax, [rcx]
0x180025284  mov     rax, [rax+10h]
0x180025288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002528d  nop
0x18002528e  mov     rcx, [rbp+var_40]
0x180025292  test    rcx, rcx
0x180025295  jz      short loc_1800252A8
0x180025297  mov     [rbp+var_40], r15
0x18002529b  mov     rax, [rcx]
0x18002529e  mov     rax, [rax+10h]
0x1800252a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252a7  nop
0x1800252a8  mov     rcx, [rbp+var_38]
0x1800252ac  test    rcx, rcx
0x1800252af  jz      short loc_1800252C2
0x1800252b1  mov     [rbp+var_38], r15
0x1800252b5  mov     rax, [rcx]
0x1800252b8  mov     rax, [rax+10h]
0x1800252bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252c1  nop
0x1800252c2  jmp     loc_1800253E4
0x1800252c7  mov     rbx, [rbp+var_40]
0x1800252cb  mov     rax, [rbx]
0x1800252ce  mov     rdi, [rax]
0x1800252d1  lea     rcx, [rbp+var_50]
0x1800252d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800252da  lea     r8, [rbp+var_50]
0x1800252de  lea     rdx, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x1800252e5  mov     rcx, rbx
0x1800252e8  mov     rax, rdi
0x1800252eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252f0  mov     ebx, eax
0x1800252f2  test    eax, eax
0x1800252f4  jns     short loc_180025313
0x1800252f6  mov     edx, 5A9h; void *
0x1800252fb  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\umstartup\\userm"...
0x180025302  mov     r9d, eax; char *
0x180025305  mov     rcx, [rbp+28h]; this
0x180025309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002530e  jmp     loc_1800253BD
0x180025313  lea     r8, [rbp+var_38]; struct Windows::Storage::Streams::IRandomAccessStream **
0x180025317  mov     edx, esi; unsigned int
0x180025319  mov     rcx, [rbp+var_50]; struct Windows::Storage::Streams::IRandomAccessStream *
0x18002531d  call    ?ScaleAccountPictureToSize@@YAJPEAUIRandomAccessStream@Streams@Storage@Windows@@IPEAPEAU1234@@Z; ScaleAccountPictureToSize(Windows::Storage::Streams::IRandomAccessStream *,uint,Windows::Storage::Streams::IRandomAccessStream * *)
0x180025322  mov     ebx, eax
0x180025324  test    eax, eax
0x180025326  jns     loc_1800253AF
0x18002532c  mov     rcx, [rbp+28h]; this
0x180025330  mov     r9d, eax; char *
0x180025333  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\umstartup\\userm"...
0x18002533a  mov     edx, 5AAh; void *
0x18002533f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025344  nop
0x180025345  mov     rcx, [rbp+var_50]
0x180025349  test    rcx, rcx
0x18002534c  jz      short loc_18002535F
0x18002534e  mov     [rbp+var_50], r15
0x180025352  mov     rax, [rcx]
0x180025355  mov     rax, [rax+10h]
0x180025359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002535e  nop
0x18002535f  mov     rcx, [rbp+var_48]
0x180025363  test    rcx, rcx
0x180025366  jz      short loc_180025379
0x180025368  mov     [rbp+var_48], r15
0x18002536c  mov     rax, [rcx]
0x18002536f  mov     rax, [rax+10h]
0x180025373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025378  nop
0x180025379  mov     rcx, [rbp+var_40]
0x18002537d  test    rcx, rcx
0x180025380  jz      short loc_180025393
0x180025382  mov     [rbp+var_40], r15
0x180025386  mov     rax, [rcx]
0x180025389  mov     rax, [rax+10h]
0x18002538d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025392  nop
0x180025393  mov     rcx, [rbp+var_38]
0x180025397  test    rcx, rcx
0x18002539a  jz      short loc_1800253AD
0x18002539c  mov     [rbp+var_38], r15
0x1800253a0  mov     rax, [rcx]
0x1800253a3  mov     rax, [rax+10h]
0x1800253a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253ac  nop
0x1800253ad  jmp     short loc_1800253E4
0x1800253af  mov     rdx, r14; struct Windows::Storage::Streams::IRandomAccessStream *
0x1800253b2  mov     rcx, [rbp+var_38]; this
0x1800253b6  call    ?GetStreamReferenceFromStream@Internal@System@Windows@@YAJPEAUIRandomAccessStream@Streams@Storage@3@PEAPEAUIRandomAccessStreamReference@563@@Z; Windows::System::Internal::GetStreamReferenceFromStream(Windows::Storage::Streams::IRandomAccessStream *,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x1800253bb  mov     ebx, eax
0x1800253bd  lea     rcx, [rbp+var_50]
0x1800253c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800253c6  nop
0x1800253c7  lea     rcx, [rbp+var_48]
0x1800253cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800253d0  nop
0x1800253d1  lea     rcx, [rbp+var_40]
0x1800253d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800253da  nop
0x1800253db  lea     rcx, [rbp+var_38]
0x1800253df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800253e4  mov     eax, ebx
0x1800253e6  mov     rcx, [rbp+var_10]
0x1800253ea  xor     rcx, rsp; StackCookie
0x1800253ed  call    __security_check_cookie
0x1800253f2  mov     rbx, [rsp+70h+arg_8]
0x1800253fa  add     rsp, 70h
0x1800253fe  pop     r15
0x180025400  pop     r14
0x180025402  pop     rdi
0x180025403  pop     rsi
0x180025404  pop     rbp
0x180025405  retn
```
