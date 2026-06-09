# InternetTime_SetW32TimeServer(ushort const *)

- ea: `0x18001493c`
- end: `0x1800149b6`
- name: `?InternetTime_SetW32TimeServer@@YAJPEBG@Z`
- size: `122`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800149bc`
- `0x18001d3d0`

## callees

- `0x1800089c8`
- `0x18001493c`
- `0x180014ebc`
- `0x180028f60`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x180014987`
- `SHLWAPI!__imp_StrCmpICW` at `0x180014987`

## string_xrefs

- `0x18001497b`: `time.windows.com`

## pseudocode

```c
__int64 __fastcall InternetTime_SetW32TimeServer(unsigned __int16 *a1)
{
  int v2; // ebx
  WCHAR pszStr1[264]; // [rsp+20h] [rbp-228h] BYREF

  v2 = SetW32TimeServer(a1);
  if ( v2 >= 0 )
  {
    StringCchCopyW(pszStr1, 0x104u, (size_t *)a1);
    return StrCmpICW(pszStr1, L"time.windows.com") != 0 ? (unsigned int)v2 : 0;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001493c  mov     [rsp+arg_8], rbx
0x180014941  push    rdi
0x180014942  sub     rsp, 240h
0x180014949  mov     rax, cs:__security_cookie
0x180014950  xor     rax, rsp
0x180014953  mov     [rsp+248h+var_18], rax
0x18001495b  mov     rdi, rcx
0x18001495e  call    ?SetW32TimeServer@@YAJPEBG@Z; SetW32TimeServer(ushort const *)
0x180014963  mov     ebx, eax
0x180014965  test    eax, eax
0x180014967  js      short loc_180014993
0x180014969  mov     r8, rdi; unsigned __int16 *
0x18001496c  lea     rcx, [rsp+248h+pszStr1]; unsigned __int16 *
0x180014971  mov     edx, 104h; unsigned __int64
0x180014976  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001497b  lea     rdx, pszStr2; "time.windows.com"
0x180014982  lea     rcx, [rsp+248h+pszStr1]; pszStr1
0x180014987  call    cs:__imp_StrCmpICW
0x18001498d  neg     eax
0x18001498f  sbb     ecx, ecx
0x180014991  and     ebx, ecx
0x180014993  mov     eax, ebx
0x180014995  mov     rcx, [rsp+248h+var_18]
0x18001499d  xor     rcx, rsp; StackCookie
0x1800149a0  call    __security_check_cookie
0x1800149a5  mov     rbx, [rsp+248h+arg_8]
0x1800149ad  add     rsp, 240h
0x1800149b4  pop     rdi
0x1800149b5  retn
```
