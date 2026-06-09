# Vml::PathIsDirectoryW(ushort const *)

- ea: `0x18001e848`
- end: `0x18001e968`
- name: `?PathIsDirectoryW@Vml@@YAHPEBG@Z`
- size: `288`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001afa0`
- `0x18004a43c`
- `0x18004aa68`

## callees

- `0x180002f50`
- `0x180002fb8`
- `0x180003388`
- `0x180003c78`
- `0x18001e848`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001e92f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001e92f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x18001e872`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x18001e872`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x18001e889`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x18001e889`
- `MPR!WNetGetResourceInformationW` at `0x18001e8ed`
- `MPR!WNetGetResourceInformationW` at `0x18001e8ed`

## pseudocode

```c
__int64 __fastcall Vml::PathIsDirectoryW(WCHAR *lpFileName, const unsigned __int16 *a2)
{
  struct _NETRESOURCEW *v3; // rax
  struct _NETRESOURCEW *v4; // rbx
  unsigned int v5; // edi
  DWORD FileAttributesW; // eax
  LPWSTR lpSystem; // [rsp+20h] [rbp-28h] BYREF
  DWORD cbBuffer; // [rsp+28h] [rbp-20h] BYREF

  if ( !lpFileName || PathIsUNCServerW(lpFileName) )
    return 0;
  if ( !PathIsUNCServerShareW(lpFileName)
    || (v3 = (struct _NETRESOURCEW *)operator new(0x400u, (const struct std::nothrow_t *)&std::nothrow), (v4 = v3) == 0) )
  {
LABEL_12:
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW != -1 )
      return (FileAttributesW >> 4) & 1;
    return 0;
  }
  memset_0(v3, 0, 0x400u);
  *(_QWORD *)&v4->dwScope = 2;
  v4->lpRemoteName = lpFileName;
  cbBuffer = 1024;
  lpSystem = 0;
  if ( WNetGetResourceInformationW(v4, v4, &cbBuffer, &lpSystem) || !v4->dwDisplayType )
  {
    operator delete(v4, 0x400u);
    goto LABEL_12;
  }
  if ( v4->dwDisplayType != 3 || (v5 = 1, v4->dwType > 1) )
    v5 = 0;
  operator delete(v4, 0x400u);
  return v5;
}

```

## disassembly

```asm
0x18001e848  mov     [rsp+arg_8], rbx
0x18001e84d  mov     [rsp+arg_10], rbp
0x18001e852  push    rdi
0x18001e853  sub     rsp, 40h
0x18001e857  mov     rax, cs:__security_cookie
0x18001e85e  xor     rax, rsp
0x18001e861  mov     [rsp+48h+var_18], rax
0x18001e866  mov     rdi, rcx
0x18001e869  test    rcx, rcx
0x18001e86c  jz      loc_18001E948
0x18001e872  call    cs:__imp_PathIsUNCServerW
0x18001e879  nop     dword ptr [rax+rax+00h]
0x18001e87e  test    eax, eax
0x18001e880  jnz     loc_18001E948
0x18001e886  mov     rcx, rdi; pszPath
0x18001e889  call    cs:__imp_PathIsUNCServerShareW
0x18001e890  nop     dword ptr [rax+rax+00h]
0x18001e895  test    eax, eax
0x18001e897  jz      loc_18001E92C
0x18001e89d  mov     ebp, 400h
0x18001e8a2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e8a9  mov     ecx, ebp; unsigned __int64
0x18001e8ab  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e8b0  mov     rbx, rax
0x18001e8b3  test    rax, rax
0x18001e8b6  jz      short loc_18001E92C
0x18001e8b8  mov     r8d, ebp; Size
0x18001e8bb  xor     edx, edx; Val
0x18001e8bd  mov     rcx, rax; void *
0x18001e8c0  call    memset_0
0x18001e8c5  mov     qword ptr [rbx], 2
0x18001e8cc  lea     r9, [rsp+48h+lpSystem]; lplpSystem
0x18001e8d1  mov     [rbx+18h], rdi
0x18001e8d5  lea     r8, [rsp+48h+cbBuffer]; lpcbBuffer
0x18001e8da  mov     rdx, rbx; lpBuffer
0x18001e8dd  mov     [rsp+48h+cbBuffer], ebp
0x18001e8e1  mov     rcx, rbx; lpNetResource
0x18001e8e4  mov     [rsp+48h+lpSystem], 0
0x18001e8ed  call    cs:__imp_WNetGetResourceInformationW
0x18001e8f4  nop     dword ptr [rax+rax+00h]
0x18001e8f9  test    eax, eax
0x18001e8fb  jnz     short loc_18001E921
0x18001e8fd  cmp     [rbx+8], eax
0x18001e900  jz      short loc_18001E921
0x18001e902  cmp     dword ptr [rbx+8], 3
0x18001e906  jnz     short loc_18001E910
0x18001e908  lea     edi, [rax+1]
0x18001e90b  cmp     [rbx+4], edi
0x18001e90e  jbe     short loc_18001E912
0x18001e910  xor     edi, edi
0x18001e912  mov     rdx, rbp; unsigned __int64
0x18001e915  mov     rcx, rbx; void *
0x18001e918  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e91d  mov     eax, edi
0x18001e91f  jmp     short loc_18001E94A
0x18001e921  mov     rdx, rbp; unsigned __int64
0x18001e924  mov     rcx, rbx; void *
0x18001e927  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e92c  mov     rcx, rdi; lpFileName
0x18001e92f  call    cs:__imp_GetFileAttributesW
0x18001e936  nop     dword ptr [rax+rax+00h]
0x18001e93b  cmp     eax, 0FFFFFFFFh
0x18001e93e  jz      short loc_18001E948
0x18001e940  shr     eax, 4
0x18001e943  and     eax, 1
0x18001e946  jmp     short loc_18001E94A
0x18001e948  xor     eax, eax
0x18001e94a  mov     rcx, [rsp+48h+var_18]
0x18001e94f  xor     rcx, rsp; StackCookie
0x18001e952  call    __security_check_cookie
0x18001e957  mov     rbx, [rsp+48h+arg_8]
0x18001e95c  mov     rbp, [rsp+48h+arg_10]
0x18001e961  add     rsp, 40h
0x18001e965  pop     rdi
0x18001e966  retn
```
