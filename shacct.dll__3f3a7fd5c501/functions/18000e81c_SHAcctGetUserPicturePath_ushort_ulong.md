# SHAcctGetUserPicturePath(ushort *,ulong)

- ea: `0x18000e81c`
- end: `0x18000e8ab`
- name: `?SHAcctGetUserPicturePath@@YAJPEAGK@Z`
- size: `143`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e8b4`

## callees

- `0x18000b598`
- `0x18000bcc0`
- `0x18000c240`
- `0x18000e81c`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000e84c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000e84c`

## string_xrefs

- `0x18000e83f`: `%ProgramData%`

## pseudocode

```c
__int64 __fastcall SHAcctGetUserPicturePath(unsigned __int16 *a1)
{
  DWORD v2; // eax
  __int64 result; // rax
  WCHAR Dst[264]; // [rsp+30h] [rbp-228h] BYREF

  v2 = ExpandEnvironmentStringsW(L"%ProgramData%", Dst, 0x104u);
  if ( v2 )
  {
    if ( v2 > 0x104 )
      return 2147942522LL;
  }
  else
  {
    result = ResultFromKnownLastError();
    if ( (int)result < 0 )
      return result;
  }
  return StringCchPrintfW(a1, 0x104u, L"%s\\%s", Dst, L"Microsoft\\User Account Pictures");
}

```

## disassembly

```asm
0x18000e81c  push    rbx
0x18000e81e  sub     rsp, 250h
0x18000e825  mov     rax, cs:__security_cookie
0x18000e82c  xor     rax, rsp
0x18000e82f  mov     [rsp+258h+var_18], rax
0x18000e837  mov     rbx, rcx
0x18000e83a  lea     rdx, [rsp+258h+Dst]; lpDst
0x18000e83f  lea     rcx, Src; "%ProgramData%"
0x18000e846  mov     r8d, 104h; nSize
0x18000e84c  call    cs:__imp_ExpandEnvironmentStringsW
0x18000e852  test    eax, eax
0x18000e854  jnz     short loc_18000E89D
0x18000e856  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000e85b  test    eax, eax
0x18000e85d  js      short loc_18000E884
0x18000e85f  lea     rax, aMicrosoftUserA; "Microsoft\\User Account Pictures"
0x18000e866  mov     edx, 104h; unsigned __int64
0x18000e86b  lea     r9, [rsp+258h+Dst]
0x18000e870  mov     [rsp+258h+var_238], rax
0x18000e875  lea     r8, aSS; "%s\\%s"
0x18000e87c  mov     rcx, rbx; unsigned __int16 *
0x18000e87f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e884  mov     rcx, [rsp+258h+var_18]
0x18000e88c  xor     rcx, rsp; StackCookie
0x18000e88f  call    __security_check_cookie
0x18000e894  add     rsp, 250h
0x18000e89b  pop     rbx
0x18000e89c  retn
0x18000e89d  cmp     eax, 104h
0x18000e8a2  jbe     short loc_18000E85F
0x18000e8a4  mov     eax, 8007007Ah
0x18000e8a9  jmp     short loc_18000E884
```
