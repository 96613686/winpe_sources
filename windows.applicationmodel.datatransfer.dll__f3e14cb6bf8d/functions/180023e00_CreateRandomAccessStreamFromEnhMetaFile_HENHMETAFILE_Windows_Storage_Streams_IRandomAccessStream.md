# CreateRandomAccessStreamFromEnhMetaFile(HENHMETAFILE__ *,Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x180023e00`
- end: `0x180023f0a`
- name: `?CreateRandomAccessStreamFromEnhMetaFile@@YAJPEAUHENHMETAFILE__@@PEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(HENHMETAFILE hEMF, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800560c0`

## callees

- `0x180023e00`
- `0x18002415c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180023ef0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180023ef0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180023edd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180023edd`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180023e80`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180023e80`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180023ef9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180023ef9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180023e39`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180023e39`
- `ext-ms-win-gdi-metafile-l1-1-0!GetEnhMetaFileBits` at `0x180023e1b`
- `ext-ms-win-gdi-metafile-l1-1-0!GetEnhMetaFileBits` at `0x180023e59`
- `ext-ms-win-gdi-metafile-l1-1-0!GetEnhMetaFileBits` at `0x180023e1b`
- `ext-ms-win-gdi-metafile-l1-1-0!GetEnhMetaFileBits` at `0x180023e59`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateRandomAccessStreamFromEnhMetaFile(
        HENHMETAFILE hEMF,
        struct Windows::Storage::Streams::IRandomAccessStream **a2)
{
  UINT EnhMetaFileBits; // eax
  UINT v5; // edi
  HRESULT OnlyRandomAccessStreamOverStream; // edi
  BYTE *v7; // rax
  BYTE *v8; // rbx
  LPSTREAM v9; // rcx
  unsigned int StringW; // eax
  LPSTREAM ppstm; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  EnhMetaFileBits = GetEnhMetaFileBits(hEMF, 0, 0);
  v5 = EnhMetaFileBits;
  if ( EnhMetaFileBits )
  {
    v7 = (BYTE *)GlobalAlloc(0x40u, EnhMetaFileBits);
    v8 = v7;
    if ( v7 )
    {
      if ( v5 == GetEnhMetaFileBits(hEMF, v5, v7) )
      {
        ppstm = 0;
        OnlyRandomAccessStreamOverStream = CreateStreamOnHGlobal(v8, 1, &ppstm);
        if ( OnlyRandomAccessStreamOverStream >= 0 )
        {
          v8 = 0;
          OnlyRandomAccessStreamOverStream = CreateReadOnlyRandomAccessStreamOverStream(ppstm, a2);
        }
        v9 = ppstm;
        if ( ppstm )
        {
          ppstm = 0;
          (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v9 + 16LL))(v9);
        }
        if ( OnlyRandomAccessStreamOverStream >= 0 )
          goto LABEL_14;
      }
      else
      {
        OnlyRandomAccessStreamOverStream = -2147467259;
      }
      ppstm = 0;
      StringW = LoadStringW(&_ImageBase, 0xCu, (LPWSTR)&ppstm, 0);
      if ( StringW )
        RoOriginateErrorW((unsigned int)OnlyRandomAccessStreamOverStream, StringW, ppstm);
    }
    else
    {
      OnlyRandomAccessStreamOverStream = -2147024882;
    }
LABEL_14:
    GlobalFree(v8);
    return (unsigned int)OnlyRandomAccessStreamOverStream;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x180023e00  push    rbx
0x180023e02  push    rbp
0x180023e03  push    rsi
0x180023e04  push    rdi
0x180023e05  sub     rsp, 28h
0x180023e09  mov     rsi, rdx
0x180023e0c  mov     rbp, rcx
0x180023e0f  mov     qword ptr [rdx], 0
0x180023e16  xor     r8d, r8d; lpData
0x180023e19  xor     edx, edx; nSize
0x180023e1b  call    cs:__imp_GetEnhMetaFileBits
0x180023e21  mov     edi, eax
0x180023e23  test    eax, eax
0x180023e25  jnz     short loc_180023E31
0x180023e27  mov     edi, 80070057h
0x180023e2c  jmp     loc_180023EFF
0x180023e31  mov     rdx, rdi; dwBytes
0x180023e34  mov     ecx, 40h ; '@'; uFlags
0x180023e39  call    cs:__imp_GlobalAlloc
0x180023e3f  mov     rbx, rax
0x180023e42  test    rax, rax
0x180023e45  jnz     short loc_180023E51
0x180023e47  mov     edi, 8007000Eh
0x180023e4c  jmp     loc_180023EF6
0x180023e51  mov     r8, rbx; lpData
0x180023e54  mov     edx, edi; nSize
0x180023e56  mov     rcx, rbp; hEMF
0x180023e59  call    cs:__imp_GetEnhMetaFileBits
0x180023e5f  cmp     edi, eax
0x180023e61  jz      short loc_180023E6A
0x180023e63  mov     edi, 80004005h
0x180023e68  jmp     short loc_180023EC1
0x180023e6a  mov     [rsp+48h+ppstm], 0
0x180023e73  lea     r8, [rsp+48h+ppstm]; ppstm
0x180023e78  mov     edx, 1; fDeleteOnRelease
0x180023e7d  mov     rcx, rbx; hGlobal
0x180023e80  call    cs:__imp_CreateStreamOnHGlobal
0x180023e86  mov     edi, eax
0x180023e88  test    eax, eax
0x180023e8a  js      short loc_180023E9D
0x180023e8c  xor     ebx, ebx
0x180023e8e  mov     rdx, rsi; struct Windows::Storage::Streams::IRandomAccessStream **
0x180023e91  mov     rcx, [rsp+48h+ppstm]; struct IStream *
0x180023e96  call    ?CreateReadOnlyRandomAccessStreamOverStream@@YAJPEAUIStream@@PEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; CreateReadOnlyRandomAccessStreamOverStream(IStream *,Windows::Storage::Streams::IRandomAccessStream * *)
0x180023e9b  mov     edi, eax
0x180023e9d  mov     rcx, [rsp+48h+ppstm]
0x180023ea2  test    rcx, rcx
0x180023ea5  jz      short loc_180023EBD
0x180023ea7  mov     [rsp+48h+ppstm], 0
0x180023eb0  mov     rax, [rcx]
0x180023eb3  mov     rax, [rax+10h]
0x180023eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ebc  nop
0x180023ebd  test    edi, edi
0x180023ebf  jns     short loc_180023EF6
0x180023ec1  mov     [rsp+48h+ppstm], 0
0x180023eca  xor     r9d, r9d; cchBufferMax
0x180023ecd  lea     r8, [rsp+48h+ppstm]; lpBuffer
0x180023ed2  lea     edx, [r9+0Ch]; uID
0x180023ed6  lea     rcx, __ImageBase; hInstance
0x180023edd  call    cs:__imp_LoadStringW
0x180023ee3  test    eax, eax
0x180023ee5  jz      short loc_180023EF6
0x180023ee7  mov     r8, [rsp+48h+ppstm]
0x180023eec  mov     edx, eax
0x180023eee  mov     ecx, edi
0x180023ef0  call    cs:__imp_RoOriginateErrorW
0x180023ef6  mov     rcx, rbx; hMem
0x180023ef9  call    cs:__imp_GlobalFree
0x180023eff  mov     eax, edi
0x180023f01  add     rsp, 28h
0x180023f05  pop     rdi
0x180023f06  pop     rsi
0x180023f07  pop     rbp
0x180023f08  pop     rbx
0x180023f09  retn
```
