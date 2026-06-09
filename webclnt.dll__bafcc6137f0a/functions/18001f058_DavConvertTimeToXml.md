# DavConvertTimeToXml

- ea: `0x18001f058`
- end: `0x18001f17b`
- name: `DavConvertTimeToXml`
- size: `291`
- prototype: `__int64 __fastcall(void *Src, size_t Size, const void *, unsigned int, FILETIME *lpFileTime, void **, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800203e4`

## callees

- `0x18001f058`
- `0x18002cf56`
- `0x18002cfa0`

## import_xrefs

- `msvcrt!wcstombs` at `0x18001f0e1`
- `msvcrt!wcstombs` at `0x18001f0e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f0fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f0fa`
- `KERNEL32!FileTimeToSystemTime` at `0x18001f0b0`
- `KERNEL32!FileTimeToSystemTime` at `0x18001f0b0`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x18001f0c4`
- `WINHTTP!WinHttpTimeFromSystemTime` at `0x18001f0c4`

## pseudocode

```c
__int64 __fastcall DavConvertTimeToXml(
        void *Src,
        size_t Size,
        const void *a3,
        unsigned int a4,
        FILETIME *lpFileTime,
        void **a6,
        _DWORD *a7)
{
  size_t v8; // rbp
  size_t v9; // r14
  unsigned int v10; // esi
  char *v12; // rdi
  char *v13; // rdi
  char *v14; // rdi
  struct _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-170h] BYREF
  WCHAR pwszTime[64]; // [rsp+40h] [rbp-158h] BYREF
  char Dest[128]; // [rsp+C0h] [rbp-D8h] BYREF

  v8 = (unsigned int)Size;
  SystemTime = 0;
  v9 = a4;
  if ( !FileTimeToSystemTime(lpFileTime, &SystemTime) || !WinHttpTimeFromSystemTime(&SystemTime, pwszTime) )
    return 0;
  v10 = wcstombs(Dest, pwszTime, 0x7Cu);
  if ( *a7 < (unsigned int)v8 + v10 + (_DWORD)v9 )
  {
    SetLastError(0x7Au);
    return 0;
  }
  v12 = (char *)*a6;
  memcpy_0(*a6, Src, v8);
  v13 = &v12[v8];
  memcpy_0(v13, Dest, v10);
  v14 = &v13[v10];
  memcpy_0(v14, a3, v9);
  *a7 -= v8 + v10 + v9;
  *a6 = &v14[v9];
  return 1;
}

```

## disassembly

```asm
0x18001f058  push    rbx
0x18001f05a  push    rbp
0x18001f05b  push    rsi
0x18001f05c  push    rdi
0x18001f05d  push    r12
0x18001f05f  push    r13
0x18001f061  push    r14
0x18001f063  push    r15
0x18001f065  sub     rsp, 158h
0x18001f06c  mov     rax, cs:__security_cookie
0x18001f073  xor     rax, rsp
0x18001f076  mov     [rsp+198h+var_58], rax
0x18001f07e  mov     r12, [rsp+198h+arg_28]
0x18001f086  mov     r13, rcx
0x18001f089  mov     rcx, [rsp+198h+lpFileTime]; lpFileTime
0x18001f091  xorps   xmm0, xmm0
0x18001f094  mov     r15, [rsp+198h+arg_30]
0x18001f09c  mov     ebp, edx
0x18001f09e  lea     rdx, [rsp+198h+SystemTime]; lpSystemTime
0x18001f0a3  movups  xmmword ptr [rsp+198h+SystemTime.wYear], xmm0
0x18001f0a8  mov     r14d, r9d
0x18001f0ab  mov     [rsp+198h+Src], r8
0x18001f0b0  call    cs:__imp_FileTimeToSystemTime
0x18001f0b6  test    eax, eax
0x18001f0b8  jz      short loc_18001F100
0x18001f0ba  lea     rdx, [rsp+198h+pwszTime]; pwszTime
0x18001f0bf  lea     rcx, [rsp+198h+SystemTime]; pst
0x18001f0c4  call    cs:__imp_WinHttpTimeFromSystemTime
0x18001f0ca  test    eax, eax
0x18001f0cc  jz      short loc_18001F100
0x18001f0ce  mov     r8d, 7Ch ; '|'; MaxCount
0x18001f0d4  lea     rdx, [rsp+198h+pwszTime]; Source
0x18001f0d9  lea     rcx, [rsp+198h+Dest]; Dest
0x18001f0e1  call    cs:__imp_wcstombs
0x18001f0e7  mov     rsi, rax
0x18001f0ea  lea     ecx, [rax+r14]
0x18001f0ee  add     ecx, ebp
0x18001f0f0  cmp     [r15], ecx
0x18001f0f3  jnb     short loc_18001F126
0x18001f0f5  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18001f0fa  call    cs:__imp_SetLastError
0x18001f100  xor     eax, eax
0x18001f102  mov     rcx, [rsp+198h+var_58]
0x18001f10a  xor     rcx, rsp; StackCookie
0x18001f10d  call    __security_check_cookie
0x18001f112  add     rsp, 158h
0x18001f119  pop     r15
0x18001f11b  pop     r14
0x18001f11d  pop     r13
0x18001f11f  pop     r12
0x18001f121  pop     rdi
0x18001f122  pop     rsi
0x18001f123  pop     rbp
0x18001f124  pop     rbx
0x18001f125  retn
0x18001f126  mov     rdi, [r12]
0x18001f12a  mov     r8, rbp; Size
0x18001f12d  mov     rcx, rdi; void *
0x18001f130  mov     rdx, r13; Src
0x18001f133  call    memcpy_0
0x18001f138  add     rdi, rbp
0x18001f13b  mov     r8d, esi; Size
0x18001f13e  mov     rcx, rdi; void *
0x18001f141  mov     ebx, esi
0x18001f143  lea     rdx, [rsp+198h+Dest]; Src
0x18001f14b  call    memcpy_0
0x18001f150  mov     rdx, [rsp+198h+Src]; Src
0x18001f155  add     rdi, rbx
0x18001f158  mov     rcx, rdi; void *
0x18001f15b  mov     r8, r14; Size
0x18001f15e  call    memcpy_0
0x18001f163  lea     eax, [rsi+r14]
0x18001f167  add     eax, ebp
0x18001f169  sub     [r15], eax
0x18001f16c  lea     rax, [rdi+r14]
0x18001f170  mov     [r12], rax
0x18001f174  mov     eax, 1
0x18001f179  jmp     short loc_18001F102
```
