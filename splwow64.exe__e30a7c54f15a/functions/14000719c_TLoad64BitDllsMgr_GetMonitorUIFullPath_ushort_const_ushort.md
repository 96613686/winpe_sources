# TLoad64BitDllsMgr::GetMonitorUIFullPath(ushort const *,ushort *)

- ea: `0x14000719c`
- end: `0x140007292`
- name: `?GetMonitorUIFullPath@TLoad64BitDllsMgr@@IEBAKPEBGPEAG@Z`
- size: `246`
- prototype: `unsigned int(TLoad64BitDllsMgr *__hidden this, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x140007548`

## callees

- `0x140005f18`
- `0x14000719c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400071e3`
- `KERNEL32!GetLastError` at `0x14000722f`
- `KERNEL32!GetLastError` at `0x1400071e3`
- `KERNEL32!GetLastError` at `0x14000722f`
- `KERNEL32!GetFullPathNameW` at `0x1400071d9`
- `KERNEL32!GetFullPathNameW` at `0x1400071d9`
- `KERNEL32!GetSystemDirectoryW` at `0x140007225`
- `KERNEL32!GetSystemDirectoryW` at `0x140007225`
- `KERNEL32!GetFileAttributesW` at `0x140007272`
- `KERNEL32!GetFileAttributesW` at `0x140007272`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400071f6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140007216`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400071f6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140007216`

## pseudocode

```c
__int64 __fastcall TLoad64BitDllsMgr::GetMonitorUIFullPath(
        TLoad64BitDllsMgr *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  unsigned int v5; // ebx
  UINT SystemDirectoryW; // eax
  signed int LastError; // eax
  LPWSTR FilePart; // [rsp+50h] [rbp+8h] BYREF

  FilePart = 0;
  if ( !a2 || !a3 )
    return 87;
  if ( !GetFullPathNameW(a2, 0x104u, a3, &FilePart) )
    return GetLastError();
  if ( !(unsigned int)_o__wcsicmp(a3, a2) )
  {
    v5 = 0;
LABEL_15:
    if ( GetFileAttributesW(a3) != -1 )
      return v5;
    return GetLastError();
  }
  v5 = 123;
  if ( FilePart && !(unsigned int)_o__wcsicmp(FilePart, a2) )
  {
    SystemDirectoryW = GetSystemDirectoryW(a3, 0x104u);
    if ( SystemDirectoryW )
    {
      LastError = StringCchPrintfW(&a3[SystemDirectoryW], 260 - SystemDirectoryW, L"\\%s", a2);
      v5 = 0;
      if ( LastError >= 0 || (v5 = (unsigned __int16)LastError, (LastError & 0x1FFF0000) == 0x70000) )
      {
LABEL_14:
        if ( v5 )
          return v5;
        goto LABEL_15;
      }
    }
    else
    {
      LastError = GetLastError();
    }
    v5 = LastError;
    goto LABEL_14;
  }
  return v5;
}

```

## disassembly

```asm
0x14000719c  mov     [rsp+FilePart], rcx
0x1400071a1  push    rbx
0x1400071a2  push    rbp
0x1400071a3  push    rsi
0x1400071a4  push    rdi
0x1400071a5  sub     rsp, 28h
0x1400071a9  mov     [rsp+48h+FilePart], 0
0x1400071b2  mov     rdi, r8
0x1400071b5  mov     rsi, rdx
0x1400071b8  test    rdx, rdx
0x1400071bb  jz      loc_140007282
0x1400071c1  test    r8, r8
0x1400071c4  jz      loc_140007282
0x1400071ca  mov     ebp, 104h
0x1400071cf  lea     r9, [rsp+48h+FilePart]; lpFilePart
0x1400071d4  mov     edx, ebp; nBufferLength
0x1400071d6  mov     rcx, rsi; lpFileName
0x1400071d9  call    cs:__imp_GetFullPathNameW
0x1400071df  test    eax, eax
0x1400071e1  jnz     short loc_1400071F0
0x1400071e3  call    cs:__imp_GetLastError
0x1400071e9  mov     ebx, eax
0x1400071eb  jmp     loc_140007287
0x1400071f0  mov     rdx, rsi
0x1400071f3  mov     rcx, rdi
0x1400071f6  call    cs:__imp__o__wcsicmp
0x1400071fc  test    eax, eax
0x1400071fe  jnz     short loc_140007204
0x140007200  xor     ebx, ebx
0x140007202  jmp     short loc_14000726F
0x140007204  mov     rcx, [rsp+48h+FilePart]
0x140007209  mov     ebx, 7Bh ; '{'
0x14000720e  test    rcx, rcx
0x140007211  jz      short loc_140007287
0x140007213  mov     rdx, rsi
0x140007216  call    cs:__imp__o__wcsicmp
0x14000721c  test    eax, eax
0x14000721e  jnz     short loc_140007287
0x140007220  mov     edx, ebp; uSize
0x140007222  mov     rcx, rdi; lpBuffer
0x140007225  call    cs:__imp_GetSystemDirectoryW
0x14000722b  test    eax, eax
0x14000722d  jnz     short loc_140007237
0x14000722f  call    cs:__imp_GetLastError
0x140007235  jmp     short loc_140007269
0x140007237  sub     ebp, eax
0x140007239  lea     r8, aS; "\\%s"
0x140007240  mov     eax, eax
0x140007242  mov     r9, rsi
0x140007245  mov     edx, ebp; unsigned __int64
0x140007247  lea     rcx, [rdi+rax*2]; unsigned __int16 *
0x14000724b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007250  xor     ebx, ebx
0x140007252  test    eax, eax
0x140007254  jns     short loc_14000726B
0x140007256  mov     ecx, eax
0x140007258  movzx   ebx, ax
0x14000725b  and     ecx, 1FFF0000h
0x140007261  cmp     ecx, 70000h
0x140007267  jz      short loc_14000726B
0x140007269  mov     ebx, eax
0x14000726b  test    ebx, ebx
0x14000726d  jnz     short loc_140007287
0x14000726f  mov     rcx, rdi; lpFileName
0x140007272  call    cs:__imp_GetFileAttributesW
0x140007278  cmp     eax, 0FFFFFFFFh
0x14000727b  jnz     short loc_140007287
0x14000727d  jmp     loc_1400071E3
0x140007282  mov     ebx, 57h ; 'W'
0x140007287  mov     eax, ebx
0x140007289  add     rsp, 28h
0x14000728d  pop     rdi
0x14000728e  pop     rsi
0x14000728f  pop     rbp
0x140007290  pop     rbx
0x140007291  retn
```
