# DeleteRepository(void)

- ea: `0x180013ddc`
- end: `0x180013ed6`
- name: `?DeleteRepository@@YAJXZ`
- size: `250`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000dcdc`

## callees

- `0x180004120`
- `0x180004c30`
- `0x180007bc4`
- `0x18000b4f4`
- `0x180013ddc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e95`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180013e80`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180013e80`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013dea`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013e2f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013dea`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013e2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 DeleteRepository(void)
{
  WCHAR *v0; // rax
  const unsigned __int16 *v1; // rdi
  int RepositoryDirectory; // ebx
  int i; // esi
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rbp
  _QWORD v7[2]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v8[7]; // [rsp+30h] [rbp-38h] BYREF

  v0 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(0x20Au);
  v1 = v0;
  v8[0] = v0;
  v8[1] = 0;
  if ( v0 )
    RepositoryDirectory = GetRepositoryDirectory(v0);
  else
    RepositoryDirectory = -2147217402;
  for ( i = 0; RepositoryDirectory >= 0 && i != 5; ++i )
  {
    v4 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x20Au);
    v5 = v4;
    v7[0] = v4;
    v7[1] = 0;
    if ( v4 )
    {
      StringCchCopyW(v4, 0x105u, v1);
      StringCchCatW(v5, 0x105u, off_180021EC0[i]);
      if ( !DeleteFileW(v5) && GetLastError() != 2 && GetLastError() != 3 )
      {
        RepositoryDirectory = -2147217407;
        CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v7);
        break;
      }
    }
    else
    {
      RepositoryDirectory = -2147217402;
    }
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v7);
  }
  CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v8);
  return (unsigned int)RepositoryDirectory;
}

```

## disassembly

```asm
0x180013ddc  push    rbx
0x180013dde  push    rbp
0x180013ddf  push    rsi
0x180013de0  push    rdi
0x180013de1  sub     rsp, 48h
0x180013de5  mov     ecx, 20Ah
0x180013dea  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180013df0  mov     rdi, rax
0x180013df3  mov     [rsp+68h+var_38], rax
0x180013df8  mov     [rsp+68h+var_30], 0
0x180013e01  test    rax, rax
0x180013e04  jnz     short loc_180013E0D
0x180013e06  mov     ebx, 80041006h
0x180013e0b  jmp     short loc_180013E17
0x180013e0d  mov     rcx, rdi; lpDst
0x180013e10  call    ?GetRepositoryDirectory@@YAJQEAG@Z; GetRepositoryDirectory(ushort * const)
0x180013e15  mov     ebx, eax
0x180013e17  xor     esi, esi
0x180013e19  test    ebx, ebx
0x180013e1b  js      loc_180013EC1
0x180013e21  cmp     esi, 5
0x180013e24  jz      loc_180013EC1
0x180013e2a  mov     ecx, 20Ah
0x180013e2f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180013e35  mov     rbp, rax
0x180013e38  mov     [rsp+68h+var_48], rax
0x180013e3d  mov     [rsp+68h+var_40], 0
0x180013e46  test    rax, rax
0x180013e49  jnz     short loc_180013E52
0x180013e4b  mov     ebx, 80041006h
0x180013e50  jmp     short loc_180013EA0
0x180013e52  mov     r8, rdi; unsigned __int16 *
0x180013e55  mov     edx, 105h; unsigned __int64
0x180013e5a  mov     rcx, rbp; unsigned __int16 *
0x180013e5d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013e62  movsxd  r8, esi
0x180013e65  lea     rax, off_180021EC0; "\\index.btr"
0x180013e6c  mov     r8, [rax+r8*8]; unsigned __int16 *
0x180013e70  mov     edx, 105h; unsigned __int64
0x180013e75  mov     rcx, rbp; unsigned __int16 *
0x180013e78  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013e7d  mov     rcx, rbp; lpFileName
0x180013e80  call    cs:__imp_DeleteFileW
0x180013e86  test    eax, eax
0x180013e88  jnz     short loc_180013EA0
0x180013e8a  call    cs:__imp_GetLastError
0x180013e90  cmp     eax, 2
0x180013e93  jz      short loc_180013EA0
0x180013e95  call    cs:__imp_GetLastError
0x180013e9b  cmp     eax, 3
0x180013e9e  jnz     short loc_180013EB1
0x180013ea0  lea     rcx, [rsp+68h+var_48]
0x180013ea5  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x180013eaa  inc     esi
0x180013eac  jmp     loc_180013E19
0x180013eb1  mov     ebx, 80041001h
0x180013eb6  lea     rcx, [rsp+68h+var_48]
0x180013ebb  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x180013ec0  nop
0x180013ec1  lea     rcx, [rsp+68h+var_38]
0x180013ec6  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x180013ecb  mov     eax, ebx
0x180013ecd  add     rsp, 48h
0x180013ed1  pop     rdi
0x180013ed2  pop     rsi
0x180013ed3  pop     rbp
0x180013ed4  pop     rbx
0x180013ed5  retn
```
