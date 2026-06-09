# Vml::PathIsDirectoryW(ushort const *)

- ea: `0x1400b817c`
- end: `0x1400b82a3`
- name: `?PathIsDirectoryW@Vml@@YAHPEBG@Z`
- size: `295`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1400a8fd0`
- `0x1400b61e0`
- `0x1400b80c0`

## callees

- `0x1400b817c`
- `0x1401332f0`
- `0x140133358`
- `0x140134048`
- `0x1401907fc`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x1400b81a1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x1400b81a1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x1400b81b8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x1400b81b8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400b826f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400b826f`
- `MPR!WNetGetResourceInformationW` at `0x1400b8226`
- `MPR!WNetGetResourceInformationW` at `0x1400b8226`

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
0x1400b817c  mov     [rsp+arg_8], rbx
0x1400b8181  push    rdi
0x1400b8182  sub     rsp, 40h
0x1400b8186  mov     rax, cs:__security_cookie
0x1400b818d  xor     rax, rsp
0x1400b8190  mov     [rsp+48h+var_10], rax
0x1400b8195  mov     rbx, rcx
0x1400b8198  test    rcx, rcx
0x1400b819b  jz      loc_1400B8288
0x1400b81a1  call    cs:__imp_PathIsUNCServerW
0x1400b81a8  nop     dword ptr [rax+rax+00h]
0x1400b81ad  test    eax, eax
0x1400b81af  jnz     loc_1400B8288
0x1400b81b5  mov     rcx, rbx; pszPath
0x1400b81b8  call    cs:__imp_PathIsUNCServerShareW
0x1400b81bf  nop     dword ptr [rax+rax+00h]
0x1400b81c4  test    eax, eax
0x1400b81c6  jz      loc_1400B826C
0x1400b81cc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400b81d3  mov     ecx, 400h; unsigned __int64
0x1400b81d8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400b81dd  mov     rdi, rax
0x1400b81e0  test    rax, rax
0x1400b81e3  jz      short loc_1400B8259
0x1400b81e5  xor     edx, edx; Val
0x1400b81e7  mov     r8d, 400h; Size
0x1400b81ed  mov     rcx, rax; void *
0x1400b81f0  call    memset_0
0x1400b81f5  mov     qword ptr [rdi], 2
0x1400b81fc  lea     r9, [rsp+48h+lpSystem]; lplpSystem
0x1400b8201  mov     [rdi+18h], rbx
0x1400b8205  lea     r8, [rsp+48h+cbBuffer]; lpcbBuffer
0x1400b820a  mov     rdx, rdi; lpBuffer
0x1400b820d  mov     [rsp+48h+cbBuffer], 400h
0x1400b8215  mov     rcx, rdi; lpNetResource
0x1400b8218  mov     [rsp+48h+lpSystem], 0
0x1400b8221  mov     [rsp+48h+var_18], rdi
0x1400b8226  call    cs:__imp_WNetGetResourceInformationW
0x1400b822d  nop     dword ptr [rax+rax+00h]
0x1400b8232  test    eax, eax
0x1400b8234  jnz     short loc_1400B8262
0x1400b8236  cmp     [rdi+8], eax
0x1400b8239  jz      short loc_1400B8262
0x1400b823b  cmp     dword ptr [rdi+8], 3
0x1400b823f  jnz     short loc_1400B8249
0x1400b8241  lea     ebx, [rax+1]
0x1400b8244  cmp     [rdi+4], ebx
0x1400b8247  jbe     short loc_1400B824B
0x1400b8249  xor     ebx, ebx
0x1400b824b  lea     rcx, [rsp+48h+var_18]
0x1400b8250  call    ??1?$unique_ptr@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@U?$default_delete@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@@std@@@std@@QEAA@XZ; std::unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>::~unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>(void)
0x1400b8255  mov     eax, ebx
0x1400b8257  jmp     short loc_1400B828A
0x1400b8259  mov     [rsp+48h+var_18], 0
0x1400b8262  lea     rcx, [rsp+48h+var_18]
0x1400b8267  call    ??1?$unique_ptr@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@U?$default_delete@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@@std@@@std@@QEAA@XZ; std::unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>::~unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>(void)
0x1400b826c  mov     rcx, rbx; lpFileName
0x1400b826f  call    cs:__imp_GetFileAttributesW
0x1400b8276  nop     dword ptr [rax+rax+00h]
0x1400b827b  cmp     eax, 0FFFFFFFFh
0x1400b827e  jz      short loc_1400B8288
0x1400b8280  shr     eax, 4
0x1400b8283  and     eax, 1
0x1400b8286  jmp     short loc_1400B828A
0x1400b8288  xor     eax, eax
0x1400b828a  mov     rcx, [rsp+48h+var_10]
0x1400b828f  xor     rcx, rsp; StackCookie
0x1400b8292  call    __security_check_cookie
0x1400b8297  mov     rbx, [rsp+48h+arg_8]
0x1400b829c  add     rsp, 40h
0x1400b82a0  pop     rdi
0x1400b82a1  retn
```
