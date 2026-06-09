# RemoveRegProvider

- ea: `0x180036f20`
- end: `0x180037024`
- name: `RemoveRegProvider`
- size: `260`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180036db0`

## callees

- `0x18000bdb0`
- `0x18000cf50`
- `0x18000d1c0`
- `0x180036f20`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036ff7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036ff7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180036fe1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180036fe1`

## pseudocode

```c
_BOOL8 __fastcall RemoveRegProvider(__int64 a1, const unsigned __int16 *a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx
  unsigned __int16 v6[40]; // [rsp+20h] [rbp-168h] BYREF
  WCHAR SubKey[128]; // [rsp+70h] [rbp-118h] BYREF

  if ( !a1 )
    goto LABEL_9;
  if ( !a2 )
    goto LABEL_9;
  if ( !(unsigned int)guid2wstr(a1, v6) )
    goto LABEL_9;
  v3 = -1;
  v4 = -1;
  do
    ++v4;
  while ( v6[v4] );
  do
    ++v3;
  while ( a2[v3] );
  if ( (unsigned __int64)(v4 + v3 + 2) <= 0x80 )
  {
    StringCchCopyW(SubKey, 0x80u, a2);
    StringCchCatW(SubKey, 0x80u, L"\\");
    StringCchCatW(SubKey, 0x80u, v6);
    return RegDeleteKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0) == 0;
  }
  else
  {
LABEL_9:
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x180036f20  mov     [rsp+arg_10], rbx
0x180036f25  mov     [rsp+arg_18], rsi
0x180036f2a  push    rdi
0x180036f2b  sub     rsp, 180h
0x180036f32  mov     rax, cs:__security_cookie
0x180036f39  xor     rax, rsp
0x180036f3c  mov     [rsp+188h+var_18], rax
0x180036f44  xor     edi, edi
0x180036f46  mov     rbx, rdx
0x180036f49  test    rcx, rcx
0x180036f4c  jz      loc_180036FF2
0x180036f52  test    rdx, rdx
0x180036f55  jz      loc_180036FF2
0x180036f5b  lea     rdx, [rsp+188h+var_168]
0x180036f60  call    guid2wstr
0x180036f65  test    eax, eax
0x180036f67  jz      loc_180036FF2
0x180036f6d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036f71  lea     rdx, [rsp+188h+var_168]
0x180036f76  mov     rcx, rax
0x180036f79  inc     rcx
0x180036f7c  cmp     [rdx+rcx*2], di
0x180036f80  jnz     short loc_180036F79
0x180036f82  inc     rax
0x180036f85  cmp     [rbx+rax*2], di
0x180036f89  jnz     short loc_180036F82
0x180036f8b  add     rax, 2
0x180036f8f  mov     esi, 80h
0x180036f94  add     rax, rcx
0x180036f97  cmp     rax, rsi
0x180036f9a  ja      short loc_180036FF2
0x180036f9c  mov     r8, rbx; unsigned __int16 *
0x180036f9f  lea     rcx, [rsp+188h+SubKey]; unsigned __int16 *
0x180036fa4  mov     edx, esi; unsigned __int64
0x180036fa6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036fab  lea     r8, asc_1800557E4; "\\"
0x180036fb2  mov     edx, esi; unsigned __int64
0x180036fb4  lea     rcx, [rsp+188h+SubKey]; unsigned __int16 *
0x180036fb9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180036fbe  lea     r8, [rsp+188h+var_168]; unsigned __int16 *
0x180036fc3  mov     edx, esi; unsigned __int64
0x180036fc5  lea     rcx, [rsp+188h+SubKey]; unsigned __int16 *
0x180036fca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180036fcf  xor     r9d, r9d; Reserved
0x180036fd2  lea     rdx, [rsp+188h+SubKey]; lpSubKey
0x180036fd7  xor     r8d, r8d; samDesired
0x180036fda  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180036fe1  call    cs:__imp_RegDeleteKeyExW
0x180036fe7  test    eax, eax
0x180036fe9  mov     ecx, edi
0x180036feb  setz    cl
0x180036fee  mov     eax, ecx
0x180036ff0  jmp     short loc_180036FFF
0x180036ff2  mov     ecx, 57h ; 'W'; dwErrCode
0x180036ff7  call    cs:__imp_SetLastError
0x180036ffd  xor     eax, eax
0x180036fff  mov     rcx, [rsp+188h+var_18]
0x180037007  xor     rcx, rsp; StackCookie
0x18003700a  call    __security_check_cookie
0x18003700f  lea     r11, [rsp+188h+var_8]
0x180037017  mov     rbx, [r11+20h]
0x18003701b  mov     rsi, [r11+28h]
0x18003701f  mov     rsp, r11
0x180037022  pop     rdi
0x180037023  retn
```
