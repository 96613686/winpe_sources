# CBitmapFormat::_SetFromStgMedium(ushort,tagSTGMEDIUM *,DataPackageUsage)

- ea: `0x180055ce0`
- end: `0x180055fcf`
- name: `?_SetFromStgMedium@CBitmapFormat@@MEAAJGPEAUtagSTGMEDIUM@@W4DataPackageUsage@@@Z`
- size: `751`
- prototype: `__int64 __fastcall(CDataFormat *, const struct _GUID *, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`
- `0x18000581b`
- `0x180023f10`
- `0x180024030`
- `0x180051c38`
- `0x180055ce0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055e34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055e34`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180055f22`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180055f22`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180055f10`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180055f10`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055e4d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055d8c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180055e83`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180055e83`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180055e03`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180055e03`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180055d54`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180055d54`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180055def`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180055def`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180055d2f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180055d2f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180055d81`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180055d81`

## string_xrefs

- `0x180055e2d`: `Windows.Storage.Streams.RandomAccessStreamReference`

## pseudocode

```c
__int64 __fastcall CBitmapFormat::_SetFromStgMedium(
        CDataFormat *a1,
        const struct _GUID *a2,
        __int64 a3,
        unsigned int a4)
{
  size_t v7; // rdi
  char *v8; // rax
  char *v9; // rbx
  void *v10; // rsi
  const void *v11; // rax
  signed int LastError; // eax
  signed int ActivationFactory; // edi
  __int64 v14; // rdx
  struct Windows::Storage::Streams::IRandomAccessStream *v15; // rcx
  HSTRING v16; // rbx
  __int64 v17; // rcx
  char *v18; // rbx
  unsigned int StringW; // eax
  char *v20; // rcx
  __int64 v21; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v22; // rcx
  WCHAR Buffer[4]; // [rsp+20h] [rbp-40h] BYREF
  struct Windows::Storage::Streams::IRandomAccessStream *v25; // [rsp+28h] [rbp-38h] BYREF
  __int64 v26; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF

  v25 = 0;
  if ( *(_DWORD *)a3 == 1 && ((_WORD)a2 == 8 || (_WORD)a2 == 17) )
  {
    v7 = GlobalSize(*(HGLOBAL *)(a3 + 8));
    if ( v7 + 14 > 0xFFFFFFFF )
    {
      ActivationFactory = -2147024362;
    }
    else
    {
      v8 = (char *)GlobalAlloc(0x40u, (unsigned int)(v7 + 14));
      v9 = v8;
      *(_QWORD *)Buffer = v8;
      if ( v8 )
      {
        *(_WORD *)v8 = 19778;
        *(_DWORD *)(v8 + 10) = 14;
        *(_DWORD *)(v8 + 2) = v7 + 14;
        v10 = *(void **)(a3 + 8);
        v11 = GlobalLock(v10);
        if ( v11 )
        {
          memcpy_0(v9 + 14, v11, v7);
          v15 = v25;
          if ( v25 )
          {
            v25 = 0;
            (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v15 + 16LL))(v15);
          }
          LOBYTE(v14) = 1;
          ActivationFactory = CreateRandomAccessStreamOnHGlobal(Buffer, v14, &v25);
          GlobalUnlock(v10);
          v9 = *(char **)Buffer;
        }
        else
        {
          LastError = GetLastError();
          ActivationFactory = LastError;
          if ( LastError > 0 )
            ActivationFactory = (unsigned __int16)LastError | 0x80070000;
          if ( ActivationFactory >= 0 )
            ActivationFactory = -2147467259;
        }
      }
      else
      {
        ActivationFactory = -2147024882;
      }
      GlobalFree(v9);
    }
    if ( ActivationFactory >= 0 )
    {
LABEL_19:
      v26 = 0;
      if ( WindowsCreateStringReference(
             L"Windows.Storage.Streams.RandomAccessStreamReference",
             0x33u,
             &hstringHeader,
             &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v16 = string;
      v17 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      ActivationFactory = RoGetActivationFactory(v16, &GUID_857309dc_3fbf_4e7d_986f_ef3b1a07a964, &v26);
      if ( ActivationFactory >= 0 )
      {
        *(_QWORD *)Buffer = 0;
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, struct Windows::Storage::Streams::IRandomAccessStream *, WCHAR *))(*(_QWORD *)v26 + 64LL))(
                              v26,
                              v25,
                              Buffer);
        if ( ActivationFactory >= 0 )
        {
          v18 = *(char **)Buffer;
          if ( *(_QWORD *)Buffer )
          {
            (*(void (__fastcall **)(CDataFormat *))(*(_QWORD *)a1 + 72LL))(a1);
            CDataFormat::_ClearDelegate(a1);
            ActivationFactory = (*(__int64 (__fastcall **)(CDataFormat *, char *, _QWORD))(*(_QWORD *)a1 + 56LL))(
                                  a1,
                                  v18,
                                  a4);
          }
          else
          {
            ActivationFactory = -2147467261;
          }
        }
        v20 = *(char **)Buffer;
        if ( *(_QWORD *)Buffer )
        {
          *(_QWORD *)Buffer = 0;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v20 + 16LL))(v20);
        }
      }
      v21 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
    }
  }
  else
  {
    ActivationFactory = -2147221399;
    if ( *(_DWORD *)a3 != 16 )
      goto LABEL_36;
    ActivationFactory = CreateReadOnlyRandomAccessStreamFromHBITMAP(*(HBITMAP *)(a3 + 8), a2, &v25);
    if ( ActivationFactory >= 0 )
      goto LABEL_19;
    *(_QWORD *)Buffer = 0;
    StringW = LoadStringW(&_ImageBase, 0xAu, Buffer, 0);
    if ( StringW )
      RoOriginateErrorW((unsigned int)ActivationFactory, StringW, *(_QWORD *)Buffer);
  }
LABEL_36:
  v22 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180055ce0  push    rbp
0x180055ce2  push    rbx
0x180055ce3  push    rsi
0x180055ce4  push    rdi
0x180055ce5  push    r12
0x180055ce7  push    r14
0x180055ce9  push    r15
0x180055ceb  mov     rbp, rsp
0x180055cee  sub     rsp, 60h
0x180055cf2  mov     rax, cs:__security_cookie
0x180055cf9  xor     rax, rsp
0x180055cfc  mov     [rbp+var_8], rax
0x180055d00  mov     r12d, r9d
0x180055d03  mov     rsi, r8
0x180055d06  mov     r15, rcx
0x180055d09  mov     [rbp+var_38], 0
0x180055d11  cmp     dword ptr [r8], 1
0x180055d15  jnz     loc_180055ED0
0x180055d1b  cmp     dx, 8
0x180055d1f  jz      short loc_180055D2B
0x180055d21  cmp     dx, 11h
0x180055d25  jnz     loc_180055ED0
0x180055d2b  mov     rcx, [r8+8]; hMem
0x180055d2f  call    cs:__imp_GlobalSize
0x180055d35  mov     rdi, rax
0x180055d38  lea     rcx, [rax+0Eh]
0x180055d3c  mov     eax, 0FFFFFFFFh
0x180055d41  cmp     rcx, rax
0x180055d44  ja      loc_180055E0B
0x180055d4a  mov     r14d, ecx
0x180055d4d  mov     edx, ecx; dwBytes
0x180055d4f  mov     ecx, 40h ; '@'; uFlags
0x180055d54  call    cs:__imp_GlobalAlloc
0x180055d5a  mov     rbx, rax
0x180055d5d  mov     qword ptr [rbp+Buffer], rax
0x180055d61  test    rax, rax
0x180055d64  jz      loc_180055DFB
0x180055d6a  mov     word ptr [rax], 4D42h
0x180055d6f  mov     dword ptr [rax+0Ah], 0Eh
0x180055d76  mov     [rax+2], r14d
0x180055d7a  mov     rsi, [rsi+8]
0x180055d7e  mov     rcx, rsi; hMem
0x180055d81  call    cs:__imp_GlobalLock
0x180055d87  test    rax, rax
0x180055d8a  jnz     short loc_180055DAD
0x180055d8c  call    cs:__imp_GetLastError
0x180055d92  mov     edi, eax
0x180055d94  test    eax, eax
0x180055d96  jle     short loc_180055DA1
0x180055d98  movzx   edi, ax
0x180055d9b  or      edi, 80070000h
0x180055da1  mov     eax, 80004005h
0x180055da6  test    edi, edi
0x180055da8  cmovns  edi, eax
0x180055dab  jmp     short loc_180055E00
0x180055dad  lea     rcx, [rbx+0Eh]; void *
0x180055db1  mov     r8, rdi; Size
0x180055db4  mov     rdx, rax; Src
0x180055db7  call    memcpy_0
0x180055dbc  nop
0x180055dbd  mov     rcx, [rbp+var_38]
0x180055dc1  test    rcx, rcx
0x180055dc4  jz      short loc_180055DDB
0x180055dc6  mov     [rbp+var_38], 0
0x180055dce  mov     rax, [rcx]
0x180055dd1  mov     rax, [rax+10h]
0x180055dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055dda  nop
0x180055ddb  lea     r8, [rbp+var_38]
0x180055ddf  mov     dl, 1
0x180055de1  lea     rcx, [rbp+Buffer]
0x180055de5  call    ?CreateRandomAccessStreamOnHGlobal@@YAJ$$QEAPEAX_NPEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; CreateRandomAccessStreamOnHGlobal(void * &&,bool,Windows::Storage::Streams::IRandomAccessStream * *)
0x180055dea  mov     edi, eax
0x180055dec  mov     rcx, rsi; hMem
0x180055def  call    cs:__imp_GlobalUnlock
0x180055df5  mov     rbx, qword ptr [rbp+Buffer]
0x180055df9  jmp     short loc_180055E00
0x180055dfb  mov     edi, 8007000Eh
0x180055e00  mov     rcx, rbx; hMem
0x180055e03  call    cs:__imp_GlobalFree
0x180055e09  jmp     short loc_180055E10
0x180055e0b  mov     edi, 80070216h
0x180055e10  test    edi, edi
0x180055e12  js      loc_180055F94
0x180055e18  mov     [rbp+var_30], 0
0x180055e20  lea     r9, [rbp+string]; string
0x180055e24  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180055e28  mov     edx, 33h ; '3'; length
0x180055e2d  lea     rcx, ?RuntimeClass_Windows_Storage_Streams_RandomAccessStreamReference@@3QBGB; "Windows.Storage.Streams.RandomAccessStr"...
0x180055e34  call    cs:__imp_WindowsCreateStringReference
0x180055e3a  test    eax, eax
0x180055e3c  jns     short loc_180055E53
0x180055e3e  xor     r9d, r9d; lpArguments
0x180055e41  xor     r8d, r8d; nNumberOfArguments
0x180055e44  lea     edx, [r9+1]; dwExceptionFlags
0x180055e48  mov     ecx, 0C000000Dh; dwExceptionCode
0x180055e4d  call    cs:__imp_RaiseException
0x180055e53  mov     rbx, [rbp+string]
0x180055e57  mov     rcx, [rbp+var_30]
0x180055e5b  test    rcx, rcx
0x180055e5e  jz      short loc_180055E75
0x180055e60  mov     [rbp+var_30], 0
0x180055e68  mov     rax, [rcx]
0x180055e6b  mov     rax, [rax+10h]
0x180055e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e74  nop
0x180055e75  lea     r8, [rbp+var_30]
0x180055e79  lea     rdx, _GUID_857309dc_3fbf_4e7d_986f_ef3b1a07a964
0x180055e80  mov     rcx, rbx
0x180055e83  call    cs:__imp_RoGetActivationFactory
0x180055e89  mov     edi, eax
0x180055e8b  test    eax, eax
0x180055e8d  js      loc_180055F76
0x180055e93  mov     qword ptr [rbp+Buffer], 0
0x180055e9b  mov     rcx, [rbp+var_30]
0x180055e9f  mov     rax, [rcx]
0x180055ea2  lea     r8, [rbp+Buffer]
0x180055ea6  mov     rdx, [rbp+var_38]
0x180055eaa  mov     rax, [rax+40h]
0x180055eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055eb3  mov     edi, eax
0x180055eb5  test    eax, eax
0x180055eb7  js      loc_180055F58
0x180055ebd  mov     rbx, qword ptr [rbp+Buffer]
0x180055ec1  test    rbx, rbx
0x180055ec4  jnz     short loc_180055F2A
0x180055ec6  mov     edi, 80004003h
0x180055ecb  jmp     loc_180055F58
0x180055ed0  mov     edi, 80040069h
0x180055ed5  cmp     dword ptr [r8], 10h
0x180055ed9  jnz     loc_180055F94
0x180055edf  lea     r8, [rbp+var_38]; struct Windows::Storage::Streams::IRandomAccessStream **
0x180055ee3  mov     rcx, [rsi+8]; HBITMAP
0x180055ee7  call    ?CreateReadOnlyRandomAccessStreamFromHBITMAP@@YAJPEAUHBITMAP__@@AEBU_GUID@@PEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; CreateReadOnlyRandomAccessStreamFromHBITMAP(HBITMAP__ *,_GUID const &,Windows::Storage::Streams::IRandomAccessStream * *)
0x180055eec  mov     edi, eax
0x180055eee  test    eax, eax
0x180055ef0  jns     loc_180055E18
0x180055ef6  mov     qword ptr [rbp+Buffer], 0
0x180055efe  xor     r9d, r9d; cchBufferMax
0x180055f01  lea     r8, [rbp+Buffer]; lpBuffer
0x180055f05  lea     edx, [r9+0Ah]; uID
0x180055f09  lea     rcx, __ImageBase; hInstance
0x180055f10  call    cs:__imp_LoadStringW
0x180055f16  test    eax, eax
0x180055f18  jz      short loc_180055F94
0x180055f1a  mov     r8, qword ptr [rbp+Buffer]
0x180055f1e  mov     edx, eax
0x180055f20  mov     ecx, edi
0x180055f22  call    cs:__imp_RoOriginateErrorW
0x180055f28  jmp     short loc_180055F94
0x180055f2a  mov     rax, [r15]
0x180055f2d  mov     rcx, r15
0x180055f30  mov     rax, [rax+48h]
0x180055f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f39  mov     rcx, r15; this
0x180055f3c  call    ?_ClearDelegate@CDataFormat@@IEAAXXZ; CDataFormat::_ClearDelegate(void)
0x180055f41  mov     rax, [r15]
0x180055f44  mov     r8d, r12d
0x180055f47  mov     rdx, rbx
0x180055f4a  mov     rcx, r15
0x180055f4d  mov     rax, [rax+38h]
0x180055f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f56  mov     edi, eax
0x180055f58  mov     rcx, qword ptr [rbp+Buffer]
0x180055f5c  test    rcx, rcx
0x180055f5f  jz      short loc_180055F76
0x180055f61  mov     qword ptr [rbp+Buffer], 0
0x180055f69  mov     rax, [rcx]
0x180055f6c  mov     rax, [rax+10h]
0x180055f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f75  nop
0x180055f76  mov     rcx, [rbp+var_30]
0x180055f7a  test    rcx, rcx
0x180055f7d  jz      short loc_180055F94
0x180055f7f  mov     [rbp+var_30], 0
0x180055f87  mov     rax, [rcx]
0x180055f8a  mov     rax, [rax+10h]
0x180055f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f93  nop
0x180055f94  mov     rcx, [rbp+var_38]
0x180055f98  test    rcx, rcx
0x180055f9b  jz      short loc_180055FB2
0x180055f9d  mov     [rbp+var_38], 0
0x180055fa5  mov     rax, [rcx]
0x180055fa8  mov     rax, [rax+10h]
0x180055fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fb1  nop
0x180055fb2  mov     eax, edi
0x180055fb4  mov     rcx, [rbp+var_8]
0x180055fb8  xor     rcx, rsp; StackCookie
0x180055fbb  call    __security_check_cookie
0x180055fc0  add     rsp, 60h
0x180055fc4  pop     r15
0x180055fc6  pop     r14
0x180055fc8  pop     r12
0x180055fca  pop     rdi
0x180055fcb  pop     rsi
0x180055fcc  pop     rbx
0x180055fcd  pop     rbp
0x180055fce  retn
```
