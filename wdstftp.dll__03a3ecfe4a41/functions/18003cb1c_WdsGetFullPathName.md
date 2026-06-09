# WdsGetFullPathName

- ea: `0x18003cb1c`
- end: `0x18003cc52`
- name: `WdsGetFullPathName`
- size: `310`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, WCHAR **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000acfc`

## callees

- `0x18000a960`
- `0x18003cb1c`
- `0x18003ce78`
- `0x180060808`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x18003cb67`
- `KERNEL32!GetFullPathNameW` at `0x18003cbe5`
- `KERNEL32!GetFullPathNameW` at `0x18003cb67`
- `KERNEL32!GetFullPathNameW` at `0x18003cbe5`
- `KERNEL32!GetLastError` at `0x18003cb79`
- `KERNEL32!GetLastError` at `0x18003cbf5`
- `KERNEL32!GetLastError` at `0x18003cb79`
- `KERNEL32!GetLastError` at `0x18003cbf5`

## string_xrefs

- `0x18003cb8b`: `onecore\base\eco\wds\wdslib\common\src\fileutil.cpp`
- `0x18003cc07`: `onecore\base\eco\wds\wdslib\common\src\fileutil.cpp`

## pseudocode

```c
__int64 __fastcall WdsGetFullPathName(LPCWSTR lpFileName, WCHAR **a2)
{
  unsigned int v4; // ebx
  WCHAR *v5; // rdi
  DWORD FullPathNameW; // eax
  unsigned __int64 v7; // rbp
  DWORD LastError; // eax
  const char *v9; // rdx
  unsigned __int64 v10; // rax
  WCHAR *v11; // rax
  DWORD v12; // eax
  const char *v13; // rdx

  v4 = 0;
  v5 = 0;
  if ( lpFileName && *lpFileName && a2 )
  {
    FullPathNameW = GetFullPathNameW(lpFileName, 0, 0, 0);
    v7 = FullPathNameW;
    if ( !FullPathNameW )
    {
      LastError = GetLastError();
      v4 = ElValidateWin32(LastError, v9, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\fileutil.cpp", 0xFB0u);
      if ( !v4 )
        return 31;
      return v4;
    }
    v10 = 2LL * FullPathNameW;
    if ( !is_mul_ok(v7, 2u) )
      v10 = -1;
    v11 = (WCHAR *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
    v5 = v11;
    if ( !v11 )
      return 8;
    if ( GetFullPathNameW(lpFileName, v7, v11, 0) )
    {
      *a2 = v5;
      return v4;
    }
    v12 = GetLastError();
    v4 = ElValidateWin32(v12, v13, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\fileutil.cpp", 0xFC4u);
    if ( !v4 )
      v4 = 31;
  }
  else
  {
    v4 = 87;
  }
  if ( v5 )
    operator delete(v5);
  return v4;
}

```

## disassembly

```asm
0x18003cb1c  mov     [rsp+arg_0], rbx
0x18003cb21  mov     [rsp+arg_8], rbp
0x18003cb26  mov     [rsp+arg_10], rsi
0x18003cb2b  push    rdi
0x18003cb2c  push    r14
0x18003cb2e  push    r15
0x18003cb30  sub     rsp, 20h
0x18003cb34  xor     r15d, r15d
0x18003cb37  mov     r14, rdx
0x18003cb3a  mov     rsi, rcx
0x18003cb3d  mov     ebx, r15d
0x18003cb40  mov     edi, r15d
0x18003cb43  test    rcx, rcx
0x18003cb46  jz      loc_18003CC25
0x18003cb4c  cmp     [rcx], r15w
0x18003cb50  jz      loc_18003CC25
0x18003cb56  test    rdx, rdx
0x18003cb59  jz      loc_18003CC25
0x18003cb5f  xor     r9d, r9d; lpFilePart
0x18003cb62  xor     r8d, r8d; lpBuffer
0x18003cb65  xor     edx, edx; nBufferLength
0x18003cb67  call    cs:__imp_GetFullPathNameW
0x18003cb6e  nop     dword ptr [rax+rax+00h]
0x18003cb73  mov     ebp, eax
0x18003cb75  test    eax, eax
0x18003cb77  jnz     short loc_18003CBAB
0x18003cb79  call    cs:__imp_GetLastError
0x18003cb80  nop     dword ptr [rax+rax+00h]
0x18003cb85  mov     r9d, 0FB0h; unsigned int
0x18003cb8b  lea     r8, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18003cb92  mov     ecx, eax; unsigned int
0x18003cb94  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18003cb99  mov     ebx, eax
0x18003cb9b  test    eax, eax
0x18003cb9d  jnz     loc_18003CC37
0x18003cba3  lea     ebx, [rax+1Fh]
0x18003cba6  jmp     loc_18003CC37
0x18003cbab  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003cbb2  mov     eax, 2
0x18003cbb7  mul     rbp
0x18003cbba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003cbc1  cmovo   rax, rcx
0x18003cbc5  mov     rcx, rax; unsigned __int64
0x18003cbc8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003cbcd  mov     rdi, rax
0x18003cbd0  test    rax, rax
0x18003cbd3  jnz     short loc_18003CBDA
0x18003cbd5  lea     ebx, [rax+8]
0x18003cbd8  jmp     short loc_18003CC37
0x18003cbda  xor     r9d, r9d; lpFilePart
0x18003cbdd  mov     r8, rdi; lpBuffer
0x18003cbe0  mov     edx, ebp; nBufferLength
0x18003cbe2  mov     rcx, rsi; lpFileName
0x18003cbe5  call    cs:__imp_GetFullPathNameW
0x18003cbec  nop     dword ptr [rax+rax+00h]
0x18003cbf1  test    eax, eax
0x18003cbf3  jnz     short loc_18003CC20
0x18003cbf5  call    cs:__imp_GetLastError
0x18003cbfc  nop     dword ptr [rax+rax+00h]
0x18003cc01  mov     r9d, 0FC4h; unsigned int
0x18003cc07  lea     r8, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18003cc0e  mov     ecx, eax; unsigned int
0x18003cc10  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18003cc15  mov     ebx, eax
0x18003cc17  test    eax, eax
0x18003cc19  jnz     short loc_18003CC2A
0x18003cc1b  lea     ebx, [rax+1Fh]
0x18003cc1e  jmp     short loc_18003CC2A
0x18003cc20  mov     [r14], rdi
0x18003cc23  jmp     short loc_18003CC37
0x18003cc25  mov     ebx, 57h ; 'W'
0x18003cc2a  test    rdi, rdi
0x18003cc2d  jz      short loc_18003CC37
0x18003cc2f  mov     rcx, rdi; void *
0x18003cc32  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003cc37  mov     rbp, [rsp+38h+arg_8]
0x18003cc3c  mov     eax, ebx
0x18003cc3e  mov     rbx, [rsp+38h+arg_0]
0x18003cc43  mov     rsi, [rsp+38h+arg_10]
0x18003cc48  add     rsp, 20h
0x18003cc4c  pop     r15
0x18003cc4e  pop     r14
0x18003cc50  pop     rdi
0x18003cc51  retn
```
