# AddConfigFilesToInetMgr(void)

- ea: `0x18002b1f8`
- end: `0x18002b419`
- name: `?AddConfigFilesToInetMgr@@YAJXZ`
- size: `545`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180031c70`

## callees

- `0x180007824`
- `0x18002b15c`
- `0x18002b1f8`
- `0x18004d030`
- `0x18004d298`
- `0x18004d350`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18002b269`
- `KERNEL32!lstrlenW` at `0x18002b2b1`
- `KERNEL32!lstrlenW` at `0x18002b2c9`
- `KERNEL32!lstrlenW` at `0x18002b269`
- `KERNEL32!lstrlenW` at `0x18002b2b1`
- `KERNEL32!lstrlenW` at `0x18002b2c9`
- `KERNEL32!GetFileAttributesW` at `0x18002b2fd`
- `KERNEL32!GetFileAttributesW` at `0x18002b342`
- `KERNEL32!GetFileAttributesW` at `0x18002b394`
- `KERNEL32!GetFileAttributesW` at `0x18002b3c3`
- `KERNEL32!GetFileAttributesW` at `0x18002b2fd`
- `KERNEL32!GetFileAttributesW` at `0x18002b342`
- `KERNEL32!GetFileAttributesW` at `0x18002b394`
- `KERNEL32!GetFileAttributesW` at `0x18002b3c3`
- `KERNEL32!GetSystemDirectoryW` at `0x18002b24e`
- `KERNEL32!GetSystemDirectoryW` at `0x18002b24e`

## string_xrefs

- `0x18002b2aa`: `inetsrv\InetMgr.exe.config`
- `0x18002b31a`: `inetsrv\InetMgr.exe.config`
- `0x18002b2c2`: `inetsrv\WMSvc.exe.config`
- `0x18002b39f`: `inetsrv\WMSvc.exe.config`

## pseudocode

```c
__int64 AddConfigFilesToInetMgr(void)
{
  int v1; // eax
  unsigned int v2; // edi
  unsigned int v3; // ebx
  unsigned __int64 v4; // rdi
  WCHAR Buffer[264]; // [rsp+28h] [rbp-E0h] BYREF

  memset_0(Buffer, 0, 0x208u);
  if ( !GetSystemDirectoryW(Buffer, 0x103u) )
    return (unsigned int)GetLastWin32Error();
  v1 = lstrlenW(Buffer);
  v2 = v1;
  if ( !v1 )
    return (unsigned int)-2147467259;
  if ( Buffer[v1 - 1] != 92 )
  {
    v3 = StringCchCatW(Buffer, 0x104u, L"\\");
    if ( v3 )
      return v3;
    ++v2;
  }
  if ( v2 + lstrlenW(L"inetsrv\\InetMgr.exe.config") >= 0x104 || v2 + lstrlenW(L"inetsrv\\WMSvc.exe.config") >= 0x104 )
    return (unsigned int)-2147467259;
  v3 = StringCchCatW(Buffer, 0x104u, L"inetsrv\\InetMgr.exe");
  if ( v3 )
    return v3;
  if ( GetFileAttributesW(Buffer) != -1 )
  {
    if ( 2 * (unsigned __int64)v2 >= 0x208 )
      goto LABEL_24;
    Buffer[v2] = 0;
    v3 = StringCchCatW(Buffer, 0x104u, L"inetsrv\\InetMgr.exe.config");
    if ( v3 )
      return v3;
    if ( GetFileAttributesW(Buffer) == -1 )
    {
      v3 = AddConfigFile(Buffer);
      if ( v3 )
        return v3;
    }
  }
  v4 = v2;
  if ( v4 >= 260 )
LABEL_24:
    _report_rangecheckfailure();
  Buffer[v4] = 0;
  v3 = StringCchCatW(Buffer, 0x104u, L"inetsrv\\WMSvc.exe");
  if ( !v3 && GetFileAttributesW(Buffer) != -1 )
  {
    Buffer[v4] = 0;
    v3 = StringCchCatW(Buffer, 0x104u, L"inetsrv\\WMSvc.exe.config");
    if ( !v3 && GetFileAttributesW(Buffer) == -1 )
      return (unsigned int)AddConfigFile(Buffer);
  }
  return v3;
}

```

## disassembly

```asm
0x18002b1f8  mov     rax, rsp
0x18002b1fb  mov     [rax+8], rbx
0x18002b1ff  mov     [rax+10h], rsi
0x18002b203  mov     [rax+18h], rdi
0x18002b207  mov     [rax+20h], r12
0x18002b20b  push    rbp
0x18002b20c  push    r14
0x18002b20e  push    r15
0x18002b210  lea     rbp, [rax-158h]
0x18002b217  sub     rsp, 240h
0x18002b21e  mov     rax, cs:__security_cookie
0x18002b225  xor     rax, rsp
0x18002b228  mov     [rbp+150h+var_20], rax
0x18002b22f  mov     r12d, 208h
0x18002b235  lea     rcx, [rsp+250h+Buffer]; void *
0x18002b23a  mov     r8d, r12d; Size
0x18002b23d  xor     edx, edx; Val
0x18002b23f  call    memset_0
0x18002b244  mov     edx, 103h; uSize
0x18002b249  lea     rcx, [rsp+250h+Buffer]; lpBuffer
0x18002b24e  call    cs:__imp_GetSystemDirectoryW
0x18002b254  xor     esi, esi
0x18002b256  test    eax, eax
0x18002b258  jnz     short loc_18002B264
0x18002b25a  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18002b25f  jmp     loc_18002B3D8
0x18002b264  lea     rcx, [rsp+250h+Buffer]; lpString
0x18002b269  call    cs:__imp_lstrlenW
0x18002b26f  mov     edi, eax
0x18002b271  cmp     eax, 1
0x18002b274  jb      loc_18002B3DC
0x18002b27a  dec     eax
0x18002b27c  mov     r14d, 104h
0x18002b282  cmp     [rsp+rax*2+250h+Buffer], 5Ch ; '\'
0x18002b288  jz      short loc_18002B2AA
0x18002b28a  lea     r8, SubBlock; "\\"
0x18002b291  mov     edx, r14d; unsigned __int64
0x18002b294  lea     rcx, [rsp+250h+Buffer]; unsigned __int16 *
0x18002b299  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b29e  mov     ebx, eax
0x18002b2a0  test    eax, eax
0x18002b2a2  jnz     loc_18002B3E1
0x18002b2a8  inc     edi
0x18002b2aa  lea     rcx, aInetsrvInetmgr; "inetsrv\\InetMgr.exe.config"
0x18002b2b1  call    cs:__imp_lstrlenW
0x18002b2b7  add     eax, edi
0x18002b2b9  cmp     eax, r14d
0x18002b2bc  jnb     loc_18002B3DC
0x18002b2c2  lea     rcx, aInetsrvWmsvcEx_0; "inetsrv\\WMSvc.exe.config"
0x18002b2c9  call    cs:__imp_lstrlenW
0x18002b2cf  add     eax, edi
0x18002b2d1  cmp     eax, r14d
0x18002b2d4  jnb     loc_18002B3DC
0x18002b2da  lea     r8, aInetsrvInetmgr_0; "inetsrv\\InetMgr.exe"
0x18002b2e1  mov     rdx, r14; unsigned __int64
0x18002b2e4  lea     rcx, [rsp+250h+Buffer]; unsigned __int16 *
0x18002b2e9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b2ee  mov     ebx, eax
0x18002b2f0  test    eax, eax
0x18002b2f2  jnz     loc_18002B3E1
0x18002b2f8  lea     rcx, [rsp+250h+Buffer]; lpFileName
0x18002b2fd  call    cs:__imp_GetFileAttributesW
0x18002b303  or      r15d, 0FFFFFFFFh
0x18002b307  cmp     eax, r15d
0x18002b30a  jz      short loc_18002B361
0x18002b30c  mov     eax, edi
0x18002b30e  add     rax, rax
0x18002b311  cmp     rax, r12
0x18002b314  jnb     loc_18002B413
0x18002b31a  lea     r8, aInetsrvInetmgr; "inetsrv\\InetMgr.exe.config"
0x18002b321  mov     [rsp+rax+250h+Buffer], si
0x18002b326  mov     rdx, r14; unsigned __int64
0x18002b329  lea     rcx, [rsp+250h+Buffer]; unsigned __int16 *
0x18002b32e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b333  mov     ebx, eax
0x18002b335  test    eax, eax
0x18002b337  jnz     loc_18002B3E1
0x18002b33d  lea     rcx, [rsp+250h+Buffer]; lpFileName
0x18002b342  call    cs:__imp_GetFileAttributesW
0x18002b348  cmp     eax, r15d
0x18002b34b  jnz     short loc_18002B361
0x18002b34d  lea     rcx, [rsp+250h+Buffer]; lpFileName
0x18002b352  call    ?AddConfigFile@@YAJPEBG@Z; AddConfigFile(ushort const *)
0x18002b357  mov     ebx, eax
0x18002b359  test    eax, eax
0x18002b35b  jnz     loc_18002B3E1
0x18002b361  mov     eax, edi
0x18002b363  lea     rdi, [rax+rax]
0x18002b367  cmp     rdi, r12
0x18002b36a  jnb     loc_18002B413
0x18002b370  lea     r8, aInetsrvWmsvcEx; "inetsrv\\WMSvc.exe"
0x18002b377  mov     [rsp+rdi+250h+Buffer], si
0x18002b37c  mov     rdx, r14; unsigned __int64
0x18002b37f  lea     rcx, [rsp+250h+Buffer]; unsigned __int16 *
0x18002b384  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b389  mov     ebx, eax
0x18002b38b  test    eax, eax
0x18002b38d  jnz     short loc_18002B3E1
0x18002b38f  lea     rcx, [rsp+250h+Buffer]; lpFileName
0x18002b394  call    cs:__imp_GetFileAttributesW
0x18002b39a  cmp     eax, r15d
0x18002b39d  jz      short loc_18002B3E1
0x18002b39f  lea     r8, aInetsrvWmsvcEx_0; "inetsrv\\WMSvc.exe.config"
0x18002b3a6  mov     [rsp+rdi+250h+Buffer], si
0x18002b3ab  mov     rdx, r14; unsigned __int64
0x18002b3ae  lea     rcx, [rsp+250h+Buffer]; unsigned __int16 *
0x18002b3b3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b3b8  mov     ebx, eax
0x18002b3ba  test    eax, eax
0x18002b3bc  jnz     short loc_18002B3E1
0x18002b3be  lea     rcx, [rsp+250h+Buffer]; lpFileName
0x18002b3c3  call    cs:__imp_GetFileAttributesW
0x18002b3c9  cmp     eax, r15d
0x18002b3cc  jnz     short loc_18002B3E1
0x18002b3ce  lea     rcx, [rsp+250h+Buffer]; lpFileName
0x18002b3d3  call    ?AddConfigFile@@YAJPEBG@Z; AddConfigFile(ushort const *)
0x18002b3d8  mov     ebx, eax
0x18002b3da  jmp     short loc_18002B3E1
0x18002b3dc  mov     ebx, 80004005h
0x18002b3e1  mov     eax, ebx
0x18002b3e3  mov     rcx, [rbp+150h+var_20]
0x18002b3ea  xor     rcx, rsp; StackCookie
0x18002b3ed  call    __security_check_cookie
0x18002b3f2  lea     r11, [rsp+250h+var_10]
0x18002b3fa  mov     rbx, [r11+20h]
0x18002b3fe  mov     rsi, [r11+28h]
0x18002b402  mov     rdi, [r11+30h]
0x18002b406  mov     r12, [r11+38h]
0x18002b40a  mov     rsp, r11
0x18002b40d  pop     r15
0x18002b40f  pop     r14
0x18002b411  pop     rbp
0x18002b412  retn
0x18002b413  call    __report_rangecheckfailure
```
