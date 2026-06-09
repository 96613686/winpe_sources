# UtilFolderExists(ushort const *)

- ea: `0x1800117fc`
- end: `0x1800118a0`
- name: `?UtilFolderExists@@YA_NPEBG@Z`
- size: `164`
- prototype: `bool __fastcall(LPCWSTR lpSrc)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000f834`

## callees

- `0x180005c80`
- `0x180005ddc`
- `0x180009580`
- `0x18000983c`
- `0x18000ad10`
- `0x1800117fc`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18001185e`
- `KERNEL32!CreateFileW` at `0x18001185e`
- `KERNEL32!GetFileAttributesW` at `0x18001182e`
- `KERNEL32!GetFileAttributesW` at `0x18001182e`

## pseudocode

```c
bool __fastcall UtilFolderExists(LPCWSTR lpSrc)
{
  HANDLE FileW; // rax
  bool v3; // bl
  LPCWSTR lpFileName[5]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v6; // [rsp+78h] [rbp+10h] BYREF

  v6 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpFileName);
  if ( (int)UtilExpandEnvironmentStrings(lpSrc) >= 0 && (GetFileAttributesW(lpFileName[0]) & 0x10) != 0 )
  {
    FileW = CreateFileW(lpFileName[0], 0, 3u, 0, 3u, 0x2000000u, 0);
    tlx::unique_any<tlx::file_handle_traits>::reset(&v6, FileW);
    v3 = (unsigned __int64)(v6 + 1) > 1;
  }
  else
  {
    v3 = 0;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpFileName);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v6);
  return v3;
}

```

## disassembly

```asm
0x1800117fc  push    rbx
0x1800117fe  sub     rsp, 60h
0x180011802  mov     rbx, rcx
0x180011805  mov     [rsp+68h+arg_8], 0
0x18001180e  lea     rcx, [rsp+68h+lpFileName]; void *
0x180011813  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180011818  lea     rdx, [rsp+68h+lpFileName]
0x18001181d  mov     rcx, rbx; lpSrc
0x180011820  call    ?UtilExpandEnvironmentStrings@@YAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; UtilExpandEnvironmentStrings(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180011825  test    eax, eax
0x180011827  js      short loc_180011882
0x180011829  mov     rcx, [rsp+68h+lpFileName]; lpFileName
0x18001182e  call    cs:__imp_GetFileAttributesW
0x180011834  test    al, 10h
0x180011836  jz      short loc_180011882
0x180011838  mov     rcx, [rsp+68h+lpFileName]; lpFileName
0x18001183d  mov     r8d, 3; dwShareMode
0x180011843  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18001184c  xor     r9d, r9d; lpSecurityAttributes
0x18001184f  mov     [rsp+68h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180011857  xor     edx, edx; dwDesiredAccess
0x180011859  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001185e  call    cs:__imp_CreateFileW
0x180011864  mov     rdx, rax
0x180011867  lea     rcx, [rsp+68h+arg_8]
0x18001186c  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180011871  mov     rax, [rsp+68h+arg_8]
0x180011876  inc     rax
0x180011879  cmp     rax, 1
0x18001187d  setnbe  bl
0x180011880  jmp     short loc_180011884
0x180011882  xor     ebx, ebx
0x180011884  lea     rcx, [rsp+68h+lpFileName]
0x180011889  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001188e  lea     rcx, [rsp+68h+arg_8]
0x180011893  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180011898  mov     al, bl
0x18001189a  add     rsp, 60h
0x18001189e  pop     rbx
0x18001189f  retn
```
