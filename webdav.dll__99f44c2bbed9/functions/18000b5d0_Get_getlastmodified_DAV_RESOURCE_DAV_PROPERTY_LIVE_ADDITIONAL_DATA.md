# Get_getlastmodified(DAV_RESOURCE *,DAV_PROPERTY *,LIVE_ADDITIONAL_DATA *)

- ea: `0x18000b5d0`
- end: `0x18000b6e9`
- name: `?Get_getlastmodified@@YAJPEAVDAV_RESOURCE@@PEAVDAV_PROPERTY@@PEAULIVE_ADDITIONAL_DATA@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(struct DAV_RESOURCE *, struct DAV_PROPERTY *, struct LIVE_ADDITIONAL_DATA *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000b5d0`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b674`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000b639`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000b639`
- `iisutil!SystemTimeToGMT` at `0x18000b66a`
- `iisutil!SystemTimeToGMT` at `0x18000b66a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b6c0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000b6c0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000b62b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000b62b`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000b695`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x18000b695`

## pseudocode

```c
__int64 __fastcall Get_getlastmodified(
        struct DAV_RESOURCE *a1,
        struct DAV_PROPERTY *a2,
        struct LIVE_ADDITIONAL_DATA *a3)
{
  signed int LastError; // eax
  signed int v6; // ebx
  signed int v7; // eax
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v10[32]; // [rsp+40h] [rbp-49h] BYREF
  __int64 v11; // [rsp+60h] [rbp-29h]
  char v12[32]; // [rsp+78h] [rbp-11h] BYREF
  _OWORD v13[4]; // [rsp+98h] [rbp+Fh] BYREF

  memset(v12, 0, 30);
  SystemTime = 0;
  memset(v13, 0, 60);
  STRU::STRU((STRU *)v10, (unsigned __int16 *)v13, 0x1Eu);
  if ( FileTimeToSystemTime((const FILETIME *)((char *)a3 + 20), &SystemTime) )
    goto LABEL_8;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_8:
    if ( SystemTimeToGMT(&SystemTime, v12, 0x1Eu) )
      goto LABEL_9;
    v7 = GetLastError();
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( v6 >= 0 )
    {
LABEL_9:
      v6 = STRU::CopyA((STRU *)v10, v12);
      if ( v6 >= 0 )
        v6 = (*(__int64 (__fastcall **)(struct DAV_PROPERTY *, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
               a2,
               v11,
               0,
               0);
    }
  }
  STRU::~STRU((STRU *)v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b5d0  mov     [rsp-8+arg_0], rbx
0x18000b5d5  mov     [rsp-8+arg_18], rdi
0x18000b5da  push    rbp
0x18000b5db  lea     rbp, [rsp-57h]
0x18000b5e0  sub     rsp, 0E0h
0x18000b5e7  mov     rax, cs:__security_cookie
0x18000b5ee  xor     rax, rsp
0x18000b5f1  mov     [rbp+57h+var_8], rax
0x18000b5f5  xorps   xmm0, xmm0
0x18000b5f8  lea     rcx, [rbp+57h+var_A0]
0x18000b5fc  xorps   xmm1, xmm1
0x18000b5ff  xor     eax, eax
0x18000b601  mov     rbx, r8
0x18000b604  mov     rdi, rdx
0x18000b607  movups  xmmword ptr [rbp+57h+var_68], xmm1
0x18000b60b  lea     rdx, [rbp+57h+var_48]
0x18000b60f  movups  xmmword ptr [rbp+57h+var_28], xmm0
0x18000b613  lea     r8d, [rax+1Eh]
0x18000b617  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18000b61b  movups  xmmword ptr [rbp+57h+var_68+0Eh], xmm1
0x18000b61f  movups  [rbp+57h+var_48], xmm0
0x18000b623  movups  [rbp+57h+var_38], xmm0
0x18000b627  movups  xmmword ptr [rbp+57h+var_28+0Ch], xmm0
0x18000b62b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000b631  lea     rcx, [rbx+14h]; lpFileTime
0x18000b635  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x18000b639  call    cs:__imp_FileTimeToSystemTime
0x18000b63f  test    eax, eax
0x18000b641  jnz     short loc_18000B65C
0x18000b643  call    cs:__imp_GetLastError
0x18000b649  mov     ebx, eax
0x18000b64b  test    eax, eax
0x18000b64d  jle     short loc_18000B658
0x18000b64f  movzx   ebx, ax
0x18000b652  or      ebx, 80070000h
0x18000b658  test    ebx, ebx
0x18000b65a  js      short loc_18000B6BC
0x18000b65c  mov     r8d, 1Eh
0x18000b662  lea     rdx, [rbp+57h+var_68]
0x18000b666  lea     rcx, [rbp+57h+SystemTime]
0x18000b66a  call    cs:__imp_?SystemTimeToGMT@@YAHAEBU_SYSTEMTIME@@PEADK@Z; SystemTimeToGMT(_SYSTEMTIME const &,char *,ulong)
0x18000b670  test    eax, eax
0x18000b672  jnz     short loc_18000B68D
0x18000b674  call    cs:__imp_GetLastError
0x18000b67a  mov     ebx, eax
0x18000b67c  test    eax, eax
0x18000b67e  jle     short loc_18000B689
0x18000b680  movzx   ebx, ax
0x18000b683  or      ebx, 80070000h
0x18000b689  test    ebx, ebx
0x18000b68b  js      short loc_18000B6BC
0x18000b68d  lea     rdx, [rbp+57h+var_68]
0x18000b691  lea     rcx, [rbp+57h+var_A0]
0x18000b695  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x18000b69b  mov     ebx, eax
0x18000b69d  test    eax, eax
0x18000b69f  js      short loc_18000B6BC
0x18000b6a1  mov     rax, [rdi]
0x18000b6a4  xor     r9d, r9d
0x18000b6a7  mov     rdx, [rbp+57h+var_80]
0x18000b6ab  xor     r8d, r8d
0x18000b6ae  mov     rcx, rdi
0x18000b6b1  mov     rax, [rax+40h]
0x18000b6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6ba  mov     ebx, eax
0x18000b6bc  lea     rcx, [rbp+57h+var_A0]
0x18000b6c0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000b6c6  mov     eax, ebx
0x18000b6c8  mov     rcx, [rbp+57h+var_8]
0x18000b6cc  xor     rcx, rsp; StackCookie
0x18000b6cf  call    __security_check_cookie
0x18000b6d4  lea     r11, [rsp+0E0h+var_s0]
0x18000b6dc  mov     rbx, [r11+10h]
0x18000b6e0  mov     rdi, [r11+28h]
0x18000b6e4  mov     rsp, r11
0x18000b6e7  pop     rbp
0x18000b6e8  retn
```
