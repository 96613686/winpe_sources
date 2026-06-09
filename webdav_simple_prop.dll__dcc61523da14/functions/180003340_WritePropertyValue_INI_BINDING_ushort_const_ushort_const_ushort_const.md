# WritePropertyValue(INI_BINDING *,ushort const *,ushort const *,ushort const *)

- ea: `0x180003340`
- end: `0x1800033d9`
- name: `?WritePropertyValue@@YAJPEAUINI_BINDING@@PEBG11@Z`
- size: `153`
- prototype: `__int64 __fastcall(LPCWSTR *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002520`

## callees

- `0x180002b34`
- `0x180003340`
- `0x180003490`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033a1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003369`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003369`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800033bb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800033bb`
- `KERNEL32!WritePrivateProfileStringW` at `0x180003397`
- `KERNEL32!WritePrivateProfileStringW` at `0x180003397`

## pseudocode

```c
__int64 __fastcall WritePropertyValue(
        LPCWSTR *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  signed int v8; // ebx
  signed int LastError; // eax
  _BYTE v11[32]; // [rsp+20h] [rbp-68h] BYREF
  LPCWSTR lpKeyName; // [rsp+40h] [rbp-48h]

  STRU::STRU((STRU *)v11);
  v8 = EncodeIniKeyName(a2, a3, (struct STRU *)v11);
  if ( v8 >= 0 )
  {
    v8 = 0;
    if ( !WritePrivateProfileStringW(a1[11], lpKeyName, a4, a1[4]) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  STRU::~STRU((STRU *)v11);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003340  push    rbx
0x180003342  push    rbp
0x180003343  push    rsi
0x180003344  push    rdi
0x180003345  sub     rsp, 68h
0x180003349  mov     rax, cs:__security_cookie
0x180003350  xor     rax, rsp
0x180003353  mov     [rsp+88h+var_30], rax
0x180003358  mov     rsi, rcx
0x18000335b  mov     rbp, r9
0x18000335e  lea     rcx, [rsp+88h+var_68]
0x180003363  mov     rdi, r8
0x180003366  mov     rbx, rdx
0x180003369  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000336f  lea     r8, [rsp+88h+var_68]; struct STRU *
0x180003374  mov     rdx, rdi; unsigned __int16 *
0x180003377  mov     rcx, rbx; unsigned __int16 *
0x18000337a  call    ?EncodeIniKeyName@@YAJPEBG0PEAVSTRU@@@Z; EncodeIniKeyName(ushort const *,ushort const *,STRU *)
0x18000337f  mov     ebx, eax
0x180003381  test    eax, eax
0x180003383  js      short loc_1800033B6
0x180003385  mov     r9, [rsi+20h]; lpFileName
0x180003389  mov     r8, rbp; lpString
0x18000338c  mov     rdx, [rsp+88h+lpKeyName]; lpKeyName
0x180003391  xor     ebx, ebx
0x180003393  mov     rcx, [rsi+58h]; lpAppName
0x180003397  call    cs:__imp_WritePrivateProfileStringW
0x18000339d  test    eax, eax
0x18000339f  jnz     short loc_1800033B6
0x1800033a1  call    cs:__imp_GetLastError
0x1800033a7  mov     ebx, eax
0x1800033a9  test    eax, eax
0x1800033ab  jle     short loc_1800033B6
0x1800033ad  movzx   ebx, ax
0x1800033b0  or      ebx, 80070000h
0x1800033b6  lea     rcx, [rsp+88h+var_68]
0x1800033bb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800033c1  mov     eax, ebx
0x1800033c3  mov     rcx, [rsp+88h+var_30]
0x1800033c8  xor     rcx, rsp; StackCookie
0x1800033cb  call    __security_check_cookie
0x1800033d0  add     rsp, 68h
0x1800033d4  pop     rdi
0x1800033d5  pop     rsi
0x1800033d6  pop     rbp
0x1800033d7  pop     rbx
0x1800033d8  retn
```
