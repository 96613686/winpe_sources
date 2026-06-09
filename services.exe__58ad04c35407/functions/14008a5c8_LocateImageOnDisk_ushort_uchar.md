# LocateImageOnDisk(ushort *,uchar)

- ea: `0x14008a5c8`
- end: `0x14008a8ad`
- name: `?LocateImageOnDisk@@YAPEAGPEAGE@Z`
- size: `741`
- prototype: `unsigned __int16 *__fastcall(LPCWSTR lpFileName, unsigned __int8)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x140027708`
- `0x140088a84`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x1400188fc`
- `0x14001f99c`
- `0x140044300`
- `0x1400582e4`
- `0x14005c0c0`
- `0x14008a5c8`
- `0x140091f24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008a724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008a79b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008a857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008a724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008a79b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008a857`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14008a6ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14008a6ef`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14008a764`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14008a82a`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14008a764`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14008a82a`

## pseudocode

```c
unsigned __int16 *__fastcall LocateImageOnDisk(wchar_t *lpFileName, const struct std::nothrow_t *a2)
{
  WCHAR *v3; // rdi
  void *lpBuffer; // rsi
  PRPC_ASYNC_STATE v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rdx
  WCHAR *v8; // rax
  DWORD LastError; // eax
  DWORD v10; // eax
  DWORD v11; // ebp
  char v12; // al
  int v13; // edx
  DWORD v14; // r14d
  unsigned __int128 v15; // rax
  DWORD v16; // eax
  LPWSTR FilePart; // [rsp+60h] [rbp+8h] BYREF

  FilePart = 0;
  v3 = 0;
  lpBuffer = 0;
  if ( !lpFileName )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_45;
    }
    v6 = 74;
    goto LABEL_6;
  }
  if ( !(_BYTE)a2 )
    goto LABEL_16;
  v7 = -1;
  do
    ++v7;
  while ( lpFileName[v7] );
  if ( wcslwr_s(lpFileName, v7 + 1) )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_45;
    }
    v6 = 75;
    goto LABEL_6;
  }
  if ( !wcsstr(lpFileName, L"\\driverstore\\") )
  {
LABEL_16:
    v8 = (WCHAR *)operator new(0x208u, a2);
    v3 = v8;
    if ( !v8 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
        || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
      {
        goto LABEL_45;
      }
      v6 = 76;
LABEL_6:
      WPP_SF_(v5->u.APC.hThread, v6, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids);
LABEL_45:
      operator delete(lpBuffer);
      lpBuffer = 0;
      goto LABEL_46;
    }
    if ( !GetSystemDirectoryW(v8, 0x104u) )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, 77, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids, LastError);
      }
      goto LABEL_45;
    }
  }
  v10 = SearchPathW(v3, lpFileName, 0, 0, 0, 0);
  v11 = v10;
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_45;
    }
    v12 = GetLastError();
    v13 = v11 + 78;
    goto LABEL_44;
  }
  v14 = v10 + 1;
  v15 = (v10 + 1) * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v14, 2u) )
    *(_QWORD *)&v15 = -1;
  lpBuffer = operator new(v15, *((const struct std::nothrow_t **)&v15 + 1));
  if ( !lpBuffer )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) != 0
      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
    {
      WPP_SF_S(WPP_GLOBAL_Control->u.APC.hThread, 79, &WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids, lpFileName);
    }
    goto LABEL_45;
  }
  v16 = SearchPathW(v3, lpFileName, 0, v14, (LPWSTR)lpBuffer, &FilePart);
  if ( !v16 || v16 > v11 )
  {
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 1) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_45;
    }
    v12 = GetLastError();
    v13 = 80;
LABEL_44:
    WPP_SF_Sd(
      WPP_GLOBAL_Control->u.APC.hThread,
      v13,
      (unsigned int)&WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids,
      (_DWORD)lpFileName,
      v12);
    goto LABEL_45;
  }
LABEL_46:
  operator delete(v3);
  return (unsigned __int16 *)lpBuffer;
}

```

## disassembly

```asm
0x14008a5c8  mov     [rsp+arg_8], rbx
0x14008a5cd  mov     [rsp+arg_10], rbp
0x14008a5d2  push    rsi
0x14008a5d3  push    rdi
0x14008a5d4  push    r12
0x14008a5d6  push    r14
0x14008a5d8  push    r15
0x14008a5da  sub     rsp, 30h
0x14008a5de  xor     r15d, r15d
0x14008a5e1  mov     rbx, rcx
0x14008a5e4  mov     [rsp+58h+FilePart], r15
0x14008a5e9  mov     edi, r15d
0x14008a5ec  mov     esi, r15d
0x14008a5ef  test    rcx, rcx
0x14008a5f2  jnz     short loc_14008A637
0x14008a5f4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008a5fb  lea     rax, WPP_GLOBAL_Control
0x14008a602  cmp     rcx, rax
0x14008a605  jz      loc_14008A880
0x14008a60b  test    byte ptr [rcx+44h], 1
0x14008a60f  jz      loc_14008A880
0x14008a615  cmp     byte ptr [rcx+41h], 2
0x14008a619  jb      loc_14008A880
0x14008a61f  lea     edx, [rbx+4Ah]
0x14008a622  mov     rcx, [rcx+38h]
0x14008a626  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14008a62d  call    WPP_SF_
0x14008a632  jmp     loc_14008A880
0x14008a637  or      r12, 0FFFFFFFFFFFFFFFFh
0x14008a63b  test    dl, dl
0x14008a63d  jz      short loc_14008A6A2
0x14008a63f  mov     rdx, r12
0x14008a642  inc     rdx
0x14008a645  cmp     [rcx+rdx*2], r15w
0x14008a64a  jnz     short loc_14008A642
0x14008a64c  inc     rdx; SizeInWords
0x14008a64f  call    _wcslwr_s
0x14008a654  test    eax, eax
0x14008a656  jz      short loc_14008A68A
0x14008a658  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008a65f  lea     rax, WPP_GLOBAL_Control
0x14008a666  cmp     rcx, rax
0x14008a669  jz      loc_14008A880
0x14008a66f  test    byte ptr [rcx+44h], 1
0x14008a673  jz      loc_14008A880
0x14008a679  cmp     byte ptr [rcx+41h], 2
0x14008a67d  jb      loc_14008A880
0x14008a683  mov     edx, 4Bh ; 'K'
0x14008a688  jmp     short loc_14008A622
0x14008a68a  lea     rdx, aDriverstore; "\\driverstore\\"
0x14008a691  mov     rcx, rbx; Str
0x14008a694  call    wcsstr
0x14008a699  test    rax, rax
0x14008a69c  jnz     loc_14008A74E
0x14008a6a2  mov     ecx, 208h; Size
0x14008a6a7  call    ??2@YAPEAX_KK0@Z; operator new(unsigned __int64,ulong,unsigned __int64)
0x14008a6ac  mov     rdi, rax
0x14008a6af  test    rax, rax
0x14008a6b2  jnz     short loc_14008A6E7
0x14008a6b4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008a6bb  lea     rax, WPP_GLOBAL_Control
0x14008a6c2  cmp     rcx, rax
0x14008a6c5  jz      loc_14008A880
0x14008a6cb  test    byte ptr [rcx+44h], 1
0x14008a6cf  jz      loc_14008A880
0x14008a6d5  cmp     byte ptr [rcx+41h], 2
0x14008a6d9  jb      loc_14008A880
0x14008a6df  lea     edx, [rdi+4Ch]
0x14008a6e2  jmp     loc_14008A622
0x14008a6e7  mov     edx, 104h; uSize
0x14008a6ec  mov     rcx, rax; lpBuffer
0x14008a6ef  call    cs:__imp_GetSystemDirectoryW
0x14008a6f5  test    eax, eax
0x14008a6f7  jnz     short loc_14008A74E
0x14008a6f9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008a700  lea     rax, WPP_GLOBAL_Control
0x14008a707  cmp     rcx, rax
0x14008a70a  jz      loc_14008A880
0x14008a710  test    byte ptr [rcx+44h], 1
0x14008a714  jz      loc_14008A880
0x14008a71a  cmp     byte ptr [rcx+41h], 2
0x14008a71e  jb      loc_14008A880
0x14008a724  call    cs:__imp_GetLastError
0x14008a72a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a731  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14008a738  mov     edx, 4Dh ; 'M'
0x14008a73d  mov     r9d, eax
0x14008a740  mov     rcx, [rcx+38h]
0x14008a744  call    WPP_SF_d
0x14008a749  jmp     loc_14008A880
0x14008a74e  mov     [rsp+58h+lpFilePart], r15; lpFilePart
0x14008a753  xor     r9d, r9d; nBufferLength
0x14008a756  xor     r8d, r8d; lpExtension
0x14008a759  mov     [rsp+58h+lpBuffer], r15; lpBuffer
0x14008a75e  mov     rdx, rbx; lpFileName
0x14008a761  mov     rcx, rdi; lpPath
0x14008a764  call    cs:__imp_SearchPathW
0x14008a76a  mov     ebp, eax
0x14008a76c  test    eax, eax
0x14008a76e  jnz     short loc_14008A7A9
0x14008a770  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008a777  lea     rax, WPP_GLOBAL_Control
0x14008a77e  cmp     rcx, rax
0x14008a781  jz      loc_14008A880
0x14008a787  test    byte ptr [rcx+44h], 1
0x14008a78b  jz      loc_14008A880
0x14008a791  cmp     byte ptr [rcx+41h], 2
0x14008a795  jb      loc_14008A880
0x14008a79b  call    cs:__imp_GetLastError
0x14008a7a1  lea     edx, [rbp+4Eh]
0x14008a7a4  jmp     loc_14008A862
0x14008a7a9  lea     r14d, [rax+1]
0x14008a7ad  mov     eax, 2
0x14008a7b2  mov     ecx, r14d
0x14008a7b5  mul     rcx
0x14008a7b8  cmovb   rax, r12
0x14008a7bc  mov     rcx, rax; Size
0x14008a7bf  call    ??2@YAPEAX_KK0@Z; operator new(unsigned __int64,ulong,unsigned __int64)
0x14008a7c4  mov     rsi, rax
0x14008a7c7  test    rax, rax
0x14008a7ca  jnz     short loc_14008A80F
0x14008a7cc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008a7d3  lea     rax, WPP_GLOBAL_Control
0x14008a7da  cmp     rcx, rax
0x14008a7dd  jz      loc_14008A880
0x14008a7e3  test    byte ptr [rcx+44h], 1
0x14008a7e7  jz      loc_14008A880
0x14008a7ed  cmp     byte ptr [rcx+41h], 2
0x14008a7f1  jb      loc_14008A880
0x14008a7f7  mov     rcx, [rcx+38h]
0x14008a7fb  lea     edx, [rsi+4Fh]
0x14008a7fe  mov     r9, rbx
0x14008a801  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14008a808  call    WPP_SF_S
0x14008a80d  jmp     short loc_14008A880
0x14008a80f  lea     rax, [rsp+58h+FilePart]
0x14008a814  mov     r9d, r14d; nBufferLength
0x14008a817  mov     [rsp+58h+lpFilePart], rax; lpFilePart
0x14008a81c  xor     r8d, r8d; lpExtension
0x14008a81f  mov     rdx, rbx; lpFileName
0x14008a822  mov     [rsp+58h+lpBuffer], rsi; lpBuffer
0x14008a827  mov     rcx, rdi; lpPath
0x14008a82a  call    cs:__imp_SearchPathW
0x14008a830  test    eax, eax
0x14008a832  jz      short loc_14008A838
0x14008a834  cmp     eax, ebp
0x14008a836  jbe     short loc_14008A88B
0x14008a838  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008a83f  lea     rax, WPP_GLOBAL_Control
0x14008a846  cmp     rcx, rax
0x14008a849  jz      short loc_14008A880
0x14008a84b  test    byte ptr [rcx+44h], 1
0x14008a84f  jz      short loc_14008A880
0x14008a851  cmp     byte ptr [rcx+41h], 2
0x14008a855  jb      short loc_14008A880
0x14008a857  call    cs:__imp_GetLastError
0x14008a85d  mov     edx, 50h ; 'P'
0x14008a862  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a869  lea     r8, WPP_4c3552fb39ef31e367e621fa2ae55379_Traceguids
0x14008a870  mov     r9, rbx
0x14008a873  mov     dword ptr [rsp+58h+lpBuffer], eax
0x14008a877  mov     rcx, [rcx+38h]
0x14008a87b  call    WPP_SF_Sd
0x14008a880  mov     rcx, rsi; void *
0x14008a883  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14008a888  mov     rsi, r15
0x14008a88b  mov     rcx, rdi; void *
0x14008a88e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14008a893  mov     rbx, [rsp+58h+arg_8]
0x14008a898  mov     rax, rsi
0x14008a89b  mov     rbp, [rsp+58h+arg_10]
0x14008a8a0  add     rsp, 30h
0x14008a8a4  pop     r15
0x14008a8a6  pop     r14
0x14008a8a8  pop     r12
0x14008a8aa  pop     rdi
0x14008a8ab  pop     rsi
0x14008a8ac  retn
```
