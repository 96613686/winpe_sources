# MakeSureDirectoryPathExistsW

- ea: `0x180048b8c`
- end: `0x180048ca7`
- name: `MakeSureDirectoryPathExistsW`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180048f90`

## callees

- `0x180018318`
- `0x180018a3c`
- `0x1800212ea`
- `0x180021724`
- `0x180042240`
- `0x180048b8c`
- `0x180048f18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180048bfb`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180048bfb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180048c16`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180048c16`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180048c27`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180048c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048c31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048c31`

## string_xrefs

- `0x180048c4f`: `WPPFMT : error : Failed to create directory %ws\n`
- `0x180048c78`: `WPPFMT : error : File already exists and is not a directory: %ws\n`

## pseudocode

```c
char __fastcall MakeSureDirectoryPathExistsW(_QWORD *a1)
{
  __int64 v1; // rbx
  const wchar_t *i; // rdi
  wchar_t *v4; // rdi
  DWORD FileAttributesW; // eax
  LPCWSTR v6; // rbx
  FILE *v7; // rax
  LPCWSTR v8; // rbx
  FILE *v9; // rax
  LPCWSTR lpFileName[4]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v11[7]; // [rsp+40h] [rbp-38h] BYREF

  v1 = *a1;
  tlx::split_path<unsigned short>::_Init(v11, *a1);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpFileName);
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          lpFileName,
                          v11[0],
                          (__int64)(v11[2] - v11[0]) >> 1) )
  {
    for ( i = &lpFileName[0][(v11[1] - v1) >> 1]; ; i = v4 + 1 )
    {
      v4 = wcschr(i, 0x5Cu);
      if ( !v4 )
        break;
      *v4 = 0;
      FileAttributesW = GetFileAttributesW(lpFileName[0]);
      if ( FileAttributesW == -1 )
      {
        if ( !CreateDirectoryW(lpFileName[0], 0) && GetLastError() != 183 )
        {
          v6 = lpFileName[0];
          v7 = o___acrt_iob_func_0(2u);
          fprintf(v7, "WPPFMT : error : Failed to create directory %ws\n", v6);
          goto LABEL_2;
        }
      }
      else if ( (FileAttributesW & 0x10) == 0 )
      {
        v8 = lpFileName[0];
        v9 = o___acrt_iob_func_0(2u);
        fprintf(v9, "WPPFMT : error : File already exists and is not a directory: %ws\n", v8);
      }
      *v4 = 92;
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpFileName);
    return 1;
  }
  else
  {
LABEL_2:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpFileName);
    return 0;
  }
}

```

## disassembly

```asm
0x180048b8c  push    rbp
0x180048b8e  push    rbx
0x180048b8f  push    rsi
0x180048b90  push    rdi
0x180048b91  mov     rbp, rsp
0x180048b94  sub     rsp, 78h
0x180048b98  mov     rbx, [rcx]
0x180048b9b  mov     r8, [rcx+8]
0x180048b9f  mov     rdx, rbx
0x180048ba2  lea     rcx, [rbp+var_38]
0x180048ba6  call    ?_Init@?$split_path@G@tlx@@AEAAXPEBG_K@Z; tlx::split_path<ushort>::_Init(ushort const *,unsigned __int64)
0x180048bab  lea     rcx, [rbp+lpFileName]
0x180048baf  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180048bb4  mov     rdx, [rbp+var_38]
0x180048bb8  lea     rcx, [rbp+lpFileName]
0x180048bbc  mov     r8, [rbp+var_28]
0x180048bc0  sub     r8, rdx
0x180048bc3  sar     r8, 1
0x180048bc6  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180048bcb  test    al, al
0x180048bcd  jnz     short loc_180048BDF
0x180048bcf  lea     rcx, [rbp+lpFileName]
0x180048bd3  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180048bd8  xor     al, al
0x180048bda  jmp     loc_180048C9E
0x180048bdf  mov     rcx, [rbp+var_30]
0x180048be3  mov     esi, 5Ch ; '\'
0x180048be8  mov     rax, [rbp+lpFileName]
0x180048bec  sub     rcx, rbx
0x180048bef  sar     rcx, 1
0x180048bf2  lea     rdi, [rax+rcx*2]
0x180048bf6  mov     edx, esi; Ch
0x180048bf8  mov     rcx, rdi; Str
0x180048bfb  call    cs:__imp_wcschr
0x180048c01  mov     rdi, rax
0x180048c04  test    rax, rax
0x180048c07  jz      loc_180048C93
0x180048c0d  xor     eax, eax
0x180048c0f  mov     [rdi], ax
0x180048c12  mov     rcx, [rbp+lpFileName]; lpFileName
0x180048c16  call    cs:__imp_GetFileAttributesW
0x180048c1c  cmp     eax, 0FFFFFFFFh
0x180048c1f  jnz     short loc_180048C63
0x180048c21  mov     rcx, [rbp+lpFileName]; lpPathName
0x180048c25  xor     edx, edx; lpSecurityAttributes
0x180048c27  call    cs:__imp_CreateDirectoryW
0x180048c2d  test    eax, eax
0x180048c2f  jnz     short loc_180048C87
0x180048c31  call    cs:__imp_GetLastError
0x180048c37  cmp     eax, 0B7h
0x180048c3c  jz      short loc_180048C87
0x180048c3e  mov     rbx, [rbp+lpFileName]
0x180048c42  mov     ecx, 2; Ix
0x180048c47  call    _o___acrt_iob_func_0
0x180048c4c  mov     r8, rbx
0x180048c4f  lea     rdx, aWppfmtErrorFai_3; "WPPFMT : error : Failed to create direc"...
0x180048c56  mov     rcx, rax; Stream
0x180048c59  call    fprintf
0x180048c5e  jmp     loc_180048BCF
0x180048c63  test    al, 10h
0x180048c65  jnz     short loc_180048C87
0x180048c67  mov     rbx, [rbp+lpFileName]
0x180048c6b  mov     ecx, 2; Ix
0x180048c70  call    _o___acrt_iob_func_0
0x180048c75  mov     r8, rbx
0x180048c78  lea     rdx, aWppfmtErrorFil; "WPPFMT : error : File already exists an"...
0x180048c7f  mov     rcx, rax; Stream
0x180048c82  call    fprintf
0x180048c87  mov     [rdi], si
0x180048c8a  add     rdi, 2
0x180048c8e  jmp     loc_180048BF6
0x180048c93  lea     rcx, [rbp+lpFileName]
0x180048c97  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180048c9c  mov     al, 1
0x180048c9e  add     rsp, 78h
0x180048ca2  pop     rdi
0x180048ca3  pop     rsi
0x180048ca4  pop     rbx
0x180048ca5  pop     rbp
0x180048ca6  retn
```
