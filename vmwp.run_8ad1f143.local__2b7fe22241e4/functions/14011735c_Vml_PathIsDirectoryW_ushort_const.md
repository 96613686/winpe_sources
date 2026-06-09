# Vml::PathIsDirectoryW(ushort const *)

- ea: `0x14011735c`
- end: `0x140117483`
- name: `?PathIsDirectoryW@Vml@@YAHPEBG@Z`
- size: `295`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1401172a0`

## callees

- `0x14011735c`
- `0x140132960`
- `0x140132d50`
- `0x14013361c`
- `0x140188180`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14011744f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14011744f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x140117398`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x140117398`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x140117381`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x140117381`
- `MPR!WNetGetResourceInformationW` at `0x140117406`
- `MPR!WNetGetResourceInformationW` at `0x140117406`

## pseudocode

```c
__int64 __fastcall Vml::PathIsDirectoryW(WCHAR *lpFileName, const unsigned __int16 *a2)
{
  struct _NETRESOURCEW *v3; // rax
  struct _NETRESOURCEW *v4; // rdi
  unsigned int v5; // ebx
  DWORD FileAttributesW; // eax
  LPWSTR lpSystem; // [rsp+20h] [rbp-28h] BYREF
  DWORD cbBuffer; // [rsp+28h] [rbp-20h] BYREF
  struct _NETRESOURCEW *v10; // [rsp+30h] [rbp-18h] BYREF

  if ( !lpFileName || PathIsUNCServerW(lpFileName) )
    return 0;
  if ( !PathIsUNCServerShareW(lpFileName) )
  {
LABEL_13:
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW != -1 )
      return (FileAttributesW >> 4) & 1;
    return 0;
  }
  v3 = (struct _NETRESOURCEW *)operator new(0x400u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v3;
  if ( !v3 )
  {
    v10 = 0;
LABEL_12:
    __1__unique_ptr_TNetResourceBuffer__7__PathIsDirectoryW_Vml__YAHPEBG_Z_U__default_delete_TNetResourceBuffer__7__PathIsDirectoryW_Vml__YAHPEBG_Z__std___std__QEAA_XZ(&v10);
    goto LABEL_13;
  }
  memset_0(v3, 0, 0x400u);
  *(_QWORD *)&v4->dwScope = 2;
  v4->lpRemoteName = lpFileName;
  cbBuffer = 1024;
  lpSystem = 0;
  v10 = v4;
  if ( WNetGetResourceInformationW(v4, v4, &cbBuffer, &lpSystem) || !v4->dwDisplayType )
    goto LABEL_12;
  if ( v4->dwDisplayType != 3 || (v5 = 1, v4->dwType > 1) )
    v5 = 0;
  __1__unique_ptr_TNetResourceBuffer__7__PathIsDirectoryW_Vml__YAHPEBG_Z_U__default_delete_TNetResourceBuffer__7__PathIsDirectoryW_Vml__YAHPEBG_Z__std___std__QEAA_XZ(&v10);
  return v5;
}

```

## disassembly

```asm
0x14011735c  mov     [rsp+arg_8], rbx
0x140117361  push    rdi
0x140117362  sub     rsp, 40h
0x140117366  mov     rax, cs:__security_cookie
0x14011736d  xor     rax, rsp
0x140117370  mov     [rsp+48h+var_10], rax
0x140117375  mov     rbx, rcx
0x140117378  test    rcx, rcx
0x14011737b  jz      loc_140117468
0x140117381  call    cs:__imp_PathIsUNCServerW
0x140117388  nop     dword ptr [rax+rax+00h]
0x14011738d  test    eax, eax
0x14011738f  jnz     loc_140117468
0x140117395  mov     rcx, rbx; pszPath
0x140117398  call    cs:__imp_PathIsUNCServerShareW
0x14011739f  nop     dword ptr [rax+rax+00h]
0x1401173a4  test    eax, eax
0x1401173a6  jz      loc_14011744C
0x1401173ac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1401173b3  mov     ecx, 400h; unsigned __int64
0x1401173b8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1401173bd  mov     rdi, rax
0x1401173c0  test    rax, rax
0x1401173c3  jz      short loc_140117439
0x1401173c5  xor     edx, edx; Val
0x1401173c7  mov     r8d, 400h; Size
0x1401173cd  mov     rcx, rax; void *
0x1401173d0  call    memset_0
0x1401173d5  mov     qword ptr [rdi], 2
0x1401173dc  lea     r9, [rsp+48h+lpSystem]; lplpSystem
0x1401173e1  mov     [rdi+18h], rbx
0x1401173e5  lea     r8, [rsp+48h+cbBuffer]; lpcbBuffer
0x1401173ea  mov     rdx, rdi; lpBuffer
0x1401173ed  mov     [rsp+48h+cbBuffer], 400h
0x1401173f5  mov     rcx, rdi; lpNetResource
0x1401173f8  mov     [rsp+48h+lpSystem], 0
0x140117401  mov     [rsp+48h+var_18], rdi
0x140117406  call    cs:__imp_WNetGetResourceInformationW
0x14011740d  nop     dword ptr [rax+rax+00h]
0x140117412  test    eax, eax
0x140117414  jnz     short loc_140117442
0x140117416  cmp     [rdi+8], eax
0x140117419  jz      short loc_140117442
0x14011741b  cmp     dword ptr [rdi+8], 3
0x14011741f  jnz     short loc_140117429
0x140117421  lea     ebx, [rax+1]
0x140117424  cmp     [rdi+4], ebx
0x140117427  jbe     short loc_14011742B
0x140117429  xor     ebx, ebx
0x14011742b  lea     rcx, [rsp+48h+var_18]
0x140117430  call    ??1?$unique_ptr@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@U?$default_delete@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@@std@@@std@@QEAA@XZ; std::unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>::~unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>(void)
0x140117435  mov     eax, ebx
0x140117437  jmp     short loc_14011746A
0x140117439  mov     [rsp+48h+var_18], 0
0x140117442  lea     rcx, [rsp+48h+var_18]
0x140117447  call    ??1?$unique_ptr@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@U?$default_delete@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@@std@@@std@@QEAA@XZ; std::unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>::~unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>(void)
0x14011744c  mov     rcx, rbx; lpFileName
0x14011744f  call    cs:__imp_GetFileAttributesW
0x140117456  nop     dword ptr [rax+rax+00h]
0x14011745b  cmp     eax, 0FFFFFFFFh
0x14011745e  jz      short loc_140117468
0x140117460  shr     eax, 4
0x140117463  and     eax, 1
0x140117466  jmp     short loc_14011746A
0x140117468  xor     eax, eax
0x14011746a  mov     rcx, [rsp+48h+var_10]
0x14011746f  xor     rcx, rsp; StackCookie
0x140117472  call    __security_check_cookie
0x140117477  mov     rbx, [rsp+48h+arg_8]
0x14011747c  add     rsp, 40h
0x140117480  pop     rdi
0x140117481  retn
```
