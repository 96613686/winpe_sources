# Vml::PathIsDirectoryW(ushort const *)

- ea: `0x14010766c`
- end: `0x140107793`
- name: `?PathIsDirectoryW@Vml@@YAHPEBG@Z`
- size: `295`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1401075b0`

## callees

- `0x14010766c`
- `0x14011ea40`
- `0x14011ee30`
- `0x14011f6fc`
- `0x140175510`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14010775f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14010775f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x140107691`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x140107691`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x1401076a8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x1401076a8`
- `MPR!WNetGetResourceInformationW` at `0x140107716`
- `MPR!WNetGetResourceInformationW` at `0x140107716`

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
0x14010766c  mov     [rsp+arg_8], rbx
0x140107671  push    rdi
0x140107672  sub     rsp, 40h
0x140107676  mov     rax, cs:__security_cookie
0x14010767d  xor     rax, rsp
0x140107680  mov     [rsp+48h+var_10], rax
0x140107685  mov     rbx, rcx
0x140107688  test    rcx, rcx
0x14010768b  jz      loc_140107778
0x140107691  call    cs:__imp_PathIsUNCServerW
0x140107698  nop     dword ptr [rax+rax+00h]
0x14010769d  test    eax, eax
0x14010769f  jnz     loc_140107778
0x1401076a5  mov     rcx, rbx; pszPath
0x1401076a8  call    cs:__imp_PathIsUNCServerShareW
0x1401076af  nop     dword ptr [rax+rax+00h]
0x1401076b4  test    eax, eax
0x1401076b6  jz      loc_14010775C
0x1401076bc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1401076c3  mov     ecx, 400h; unsigned __int64
0x1401076c8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1401076cd  mov     rdi, rax
0x1401076d0  test    rax, rax
0x1401076d3  jz      short loc_140107749
0x1401076d5  xor     edx, edx; Val
0x1401076d7  mov     r8d, 400h; Size
0x1401076dd  mov     rcx, rax; void *
0x1401076e0  call    memset_0
0x1401076e5  mov     qword ptr [rdi], 2
0x1401076ec  lea     r9, [rsp+48h+lpSystem]; lplpSystem
0x1401076f1  mov     [rdi+18h], rbx
0x1401076f5  lea     r8, [rsp+48h+cbBuffer]; lpcbBuffer
0x1401076fa  mov     rdx, rdi; lpBuffer
0x1401076fd  mov     [rsp+48h+cbBuffer], 400h
0x140107705  mov     rcx, rdi; lpNetResource
0x140107708  mov     [rsp+48h+lpSystem], 0
0x140107711  mov     [rsp+48h+var_18], rdi
0x140107716  call    cs:__imp_WNetGetResourceInformationW
0x14010771d  nop     dword ptr [rax+rax+00h]
0x140107722  test    eax, eax
0x140107724  jnz     short loc_140107752
0x140107726  cmp     [rdi+8], eax
0x140107729  jz      short loc_140107752
0x14010772b  cmp     dword ptr [rdi+8], 3
0x14010772f  jnz     short loc_140107739
0x140107731  lea     ebx, [rax+1]
0x140107734  cmp     [rdi+4], ebx
0x140107737  jbe     short loc_14010773B
0x140107739  xor     ebx, ebx
0x14010773b  lea     rcx, [rsp+48h+var_18]
0x140107740  call    ??1?$unique_ptr@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@U?$default_delete@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@@std@@@std@@QEAA@XZ; std::unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>::~unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>(void)
0x140107745  mov     eax, ebx
0x140107747  jmp     short loc_14010777A
0x140107749  mov     [rsp+48h+var_18], 0
0x140107752  lea     rcx, [rsp+48h+var_18]
0x140107757  call    ??1?$unique_ptr@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@U?$default_delete@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@@std@@@std@@QEAA@XZ; std::unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>::~unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>(void)
0x14010775c  mov     rcx, rbx; lpFileName
0x14010775f  call    cs:__imp_GetFileAttributesW
0x140107766  nop     dword ptr [rax+rax+00h]
0x14010776b  cmp     eax, 0FFFFFFFFh
0x14010776e  jz      short loc_140107778
0x140107770  shr     eax, 4
0x140107773  and     eax, 1
0x140107776  jmp     short loc_14010777A
0x140107778  xor     eax, eax
0x14010777a  mov     rcx, [rsp+48h+var_10]
0x14010777f  xor     rcx, rsp; StackCookie
0x140107782  call    __security_check_cookie
0x140107787  mov     rbx, [rsp+48h+arg_8]
0x14010778c  add     rsp, 40h
0x140107790  pop     rdi
0x140107791  retn
```
