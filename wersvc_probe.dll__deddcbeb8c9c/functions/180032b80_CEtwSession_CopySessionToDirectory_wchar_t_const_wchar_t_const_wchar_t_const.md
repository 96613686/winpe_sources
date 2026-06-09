# CEtwSession::CopySessionToDirectory(wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x180032b80`
- end: `0x180032c39`
- name: `?CopySessionToDirectory@CEtwSession@@AEAAJPEB_W00@Z`
- size: `185`
- prototype: `int(CEtwSession *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180032e2c`

## callees

- `0x1800029f4`
- `0x180004a44`
- `0x180032b80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bee`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180032be4`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180032be4`

## pseudocode

```c
__int64 __fastcall CEtwSession::CopySessionToDirectory(
        CEtwSession *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  signed int v5; // ebx
  signed int LastError; // eax
  LPCWSTR lpNewFileName[2]; // [rsp+30h] [rbp-28h] BYREF
  _WORD v9[12]; // [rsp+40h] [rbp-18h] BYREF

  lpNewFileName[0] = v9;
  lpNewFileName[1] = v9;
  v9[0] = 0;
  v5 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpNewFileName, L"%s\\%s", a4, a3);
  if ( v5 >= 0 )
  {
    if ( CopyFileExW(a2, lpNewFileName[0], 0, 0, 0, 0) )
    {
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
    }
  }
  if ( lpNewFileName[0] != v9 )
    operator delete((void *)lpNewFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180032b80  mov     r11, rsp
0x180032b83  mov     [r11+8], rbx
0x180032b87  push    rdi
0x180032b88  sub     rsp, 50h
0x180032b8c  lea     rax, [r11-18h]
0x180032b90  mov     r10, r9
0x180032b93  mov     [r11-28h], rax
0x180032b97  lea     rcx, [r11-28h]
0x180032b9b  lea     rax, [r11-18h]
0x180032b9f  mov     rdi, rdx
0x180032ba2  mov     [r11-20h], rax
0x180032ba6  lea     rdx, aSS; "%s\\%s"
0x180032bad  xor     eax, eax
0x180032baf  mov     r9, r8
0x180032bb2  mov     r8, r10
0x180032bb5  mov     [rsp+58h+var_18], ax
0x180032bba  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180032bbf  mov     ebx, eax
0x180032bc1  test    eax, eax
0x180032bc3  js      short loc_180032C11
0x180032bc5  mov     rdx, [rsp+58h+lpNewFileName]; lpNewFileName
0x180032bca  xor     r9d, r9d; lpData
0x180032bcd  mov     [rsp+58h+dwCopyFlags], 0; dwCopyFlags
0x180032bd5  xor     r8d, r8d; lpProgressRoutine
0x180032bd8  mov     rcx, rdi; lpExistingFileName
0x180032bdb  mov     [rsp+58h+pbCancel], 0; pbCancel
0x180032be4  call    cs:__imp_CopyFileExW
0x180032bea  test    eax, eax
0x180032bec  jnz     short loc_180032C0F
0x180032bee  call    cs:__imp_GetLastError
0x180032bf4  mov     ebx, eax
0x180032bf6  test    eax, eax
0x180032bf8  jle     short loc_180032C03
0x180032bfa  movzx   ebx, ax
0x180032bfd  or      ebx, 80070000h
0x180032c03  test    ebx, ebx
0x180032c05  mov     eax, 80004005h
0x180032c0a  cmovns  ebx, eax
0x180032c0d  jmp     short loc_180032C11
0x180032c0f  xor     ebx, ebx
0x180032c11  mov     rcx, [rsp+58h+lpNewFileName]; void *
0x180032c16  lea     rax, [rsp+58h+var_18]
0x180032c1b  cmp     rcx, rax
0x180032c1e  jz      short loc_180032C2C
0x180032c20  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180032c27  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032c2c  mov     eax, ebx
0x180032c2e  mov     rbx, [rsp+58h+arg_0]
0x180032c33  add     rsp, 50h
0x180032c37  pop     rdi
0x180032c38  retn
```
