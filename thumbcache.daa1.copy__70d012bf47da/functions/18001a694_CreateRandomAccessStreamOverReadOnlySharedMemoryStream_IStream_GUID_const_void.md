# CreateRandomAccessStreamOverReadOnlySharedMemoryStream(IStream *,_GUID const &,void * *)

- ea: `0x18001a694`
- end: `0x18001a7c1`
- name: `?CreateRandomAccessStreamOverReadOnlySharedMemoryStream@@YAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(struct IStream *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180019980`
- `0x18003cfc0`
- `0x18003d6b0`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x18001a694`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x18001a6f1`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x18001a6f1`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x18001a744`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x18001a744`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x18001a723`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x18001a723`

## string_xrefs

- `0x18001a77d`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18001a798`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateRandomAccessStreamOverReadOnlySharedMemoryStream(
        struct IStream *a1,
        const struct _GUID *a2,
        void **a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  int OnlySharedMemoryStream; // eax
  __int64 v9; // rcx
  __int64 v10; // rdx
  int v11[2]; // [rsp+20h] [rbp-28h] BYREF
  ULARGE_INTEGER pui; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a3 = 0;
  if ( !a1 )
    return 0;
  pui.QuadPart = 0;
  v6 = IStream_Size(a1, &pui);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v6,
      v11[0]);
  }
  else
  {
    *(_QWORD *)v11 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v11);
    OnlySharedMemoryStream = SHCreateReadOnlySharedMemoryStream(
                               a1,
                               pui.LowPart,
                               &GUID_0000000c_0000_0000_c000_000000000046,
                               v11);
    v7 = OnlySharedMemoryStream;
    if ( OnlySharedMemoryStream < 0 )
    {
      v10 = 132;
    }
    else
    {
      OnlySharedMemoryStream = CreateRandomAccessStreamOverStream(
                                 *(_QWORD *)v11,
                                 0,
                                 &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da,
                                 a3);
      v7 = OnlySharedMemoryStream;
      if ( OnlySharedMemoryStream >= 0 )
      {
        v9 = *(_QWORD *)v11;
        if ( *(_QWORD *)v11 )
        {
          *(_QWORD *)v11 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        return 0;
      }
      v10 = 133;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)OnlySharedMemoryStream,
      v11[0]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v11);
  }
  return v7;
}

```

## disassembly

```asm
0x18001a694  mov     [rsp+arg_8], rbx
0x18001a699  mov     [rsp+arg_18], rsi
0x18001a69e  push    rdi
0x18001a69f  sub     rsp, 40h
0x18001a6a3  mov     rax, cs:__security_cookie
0x18001a6aa  xor     rax, rsp
0x18001a6ad  mov     [rsp+48h+var_18], rax
0x18001a6b2  mov     rsi, r8
0x18001a6b5  mov     rdi, rcx
0x18001a6b8  mov     qword ptr [r8], 0
0x18001a6bf  test    rcx, rcx
0x18001a6c2  jnz     short loc_18001A6E3
0x18001a6c4  xor     eax, eax
0x18001a6c6  mov     rcx, [rsp+48h+var_18]
0x18001a6cb  xor     rcx, rsp; StackCookie
0x18001a6ce  call    __security_check_cookie
0x18001a6d3  mov     rbx, [rsp+48h+arg_8]
0x18001a6d8  mov     rsi, [rsp+48h+arg_18]
0x18001a6dd  add     rsp, 40h
0x18001a6e1  pop     rdi
0x18001a6e2  retn
0x18001a6e3  mov     qword ptr [rsp+48h+pui], 0
0x18001a6ec  lea     rdx, [rsp+48h+pui]; pui
0x18001a6f1  call    cs:__imp_IStream_Size
0x18001a6f7  mov     ebx, eax
0x18001a6f9  test    eax, eax
0x18001a6fb  js      short loc_18001A775
0x18001a6fd  mov     qword ptr [rsp+48h+var_28], 0; int
0x18001a706  lea     rcx, [rsp+48h+var_28]
0x18001a70b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a710  lea     r9, [rsp+48h+var_28]
0x18001a715  lea     r8, _GUID_0000000c_0000_0000_c000_000000000046
0x18001a71c  mov     edx, dword ptr [rsp+48h+pui]
0x18001a720  mov     rcx, rdi
0x18001a723  call    cs:__imp_SHCreateReadOnlySharedMemoryStream
0x18001a729  mov     ebx, eax
0x18001a72b  test    eax, eax
0x18001a72d  js      loc_18001A7BA
0x18001a733  mov     r9, rsi
0x18001a736  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x18001a73d  xor     edx, edx
0x18001a73f  mov     rcx, qword ptr [rsp+48h+var_28]
0x18001a744  call    cs:__imp_CreateRandomAccessStreamOverStream
0x18001a74a  mov     ebx, eax
0x18001a74c  test    eax, eax
0x18001a74e  js      short loc_18001A790
0x18001a750  mov     rcx, qword ptr [rsp+48h+var_28]
0x18001a755  test    rcx, rcx
0x18001a758  jz      short loc_18001A770
0x18001a75a  mov     qword ptr [rsp+48h+var_28], 0
0x18001a763  mov     rax, [rcx]
0x18001a766  mov     rax, [rax+10h]
0x18001a76a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a76f  nop
0x18001a770  jmp     loc_18001A6C4
0x18001a775  mov     rcx, [rsp+48h]; this
0x18001a77a  mov     r9d, ebx; char *
0x18001a77d  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001a784  mov     edx, 80h; void *
0x18001a789  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a78e  jmp     short loc_18001A7B3
0x18001a790  mov     edx, 85h; void *
0x18001a795  mov     r9d, eax; char *
0x18001a798  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001a79f  mov     rcx, [rsp+48h]; this
0x18001a7a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a7a9  lea     rcx, [rsp+48h+var_28]
0x18001a7ae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a7b3  mov     eax, ebx
0x18001a7b5  jmp     loc_18001A6C6
0x18001a7ba  mov     edx, 84h
0x18001a7bf  jmp     short loc_18001A795
```
