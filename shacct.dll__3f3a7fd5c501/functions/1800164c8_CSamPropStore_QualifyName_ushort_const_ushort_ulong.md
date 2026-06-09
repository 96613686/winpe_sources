# CSamPropStore::_QualifyName(ushort const *,ushort *,ulong)

- ea: `0x1800164c8`
- end: `0x180016564`
- name: `?_QualifyName@CSamPropStore@@AEAAJPEBGPEAGK@Z`
- size: `156`
- prototype: `int(CSamPropStore *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180015d30`

## callees

- `0x18000b828`
- `0x18000bcc0`
- `0x18000c240`
- `0x1800164c8`
- `0x180016aa8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001651d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001651d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800164f9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800164f9`

## pseudocode

```c
__int64 __fastcall CSamPropStore::_QualifyName(CSamPropStore *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  DWORD nSize; // [rsp+30h] [rbp-38h] BYREF
  WCHAR Buffer[16]; // [rsp+38h] [rbp-30h] BYREF

  nSize = 16;
  if ( !GetComputerNameW(Buffer, &nSize) )
    return ResultFromKnownLastError();
  if ( CompareStringW(0x7Fu, 1u, Buffer, -1, a2, -1) == 2 )
    return SHQualifyUsernameAsLocal(a2, a3);
  return StringCchCopyW(a3, 0x111u, a2);
}

```

## disassembly

```asm
0x1800164c8  mov     [rsp+arg_0], rbx
0x1800164cd  push    rdi
0x1800164ce  sub     rsp, 60h
0x1800164d2  mov     rax, cs:__security_cookie
0x1800164d9  xor     rax, rsp
0x1800164dc  mov     [rsp+68h+var_10], rax
0x1800164e1  mov     rbx, rdx
0x1800164e4  mov     [rsp+68h+nSize], 10h
0x1800164ec  lea     rdx, [rsp+68h+nSize]; nSize
0x1800164f1  mov     rdi, r8
0x1800164f4  lea     rcx, [rsp+68h+Buffer]; lpBuffer
0x1800164f9  call    cs:__imp_GetComputerNameW
0x1800164ff  test    eax, eax
0x180016501  jz      short loc_180016547
0x180016503  or      r9d, 0FFFFFFFFh; cchCount1
0x180016507  lea     r8, [rsp+68h+Buffer]; lpString1
0x18001650c  mov     [rsp+68h+cchCount2], r9d; cchCount2
0x180016511  mov     [rsp+68h+lpString2], rbx; lpString2
0x180016516  lea     edx, [r9+2]; dwCmpFlags
0x18001651a  lea     ecx, [rdx+7Eh]; Locale
0x18001651d  call    cs:__imp_CompareStringW
0x180016523  cmp     eax, 2
0x180016526  jnz     short loc_180016535
0x180016528  mov     rdx, rdi; unsigned __int16 *
0x18001652b  mov     rcx, rbx; unsigned __int16 *
0x18001652e  call    SHQualifyUsernameAsLocal
0x180016533  jmp     short loc_18001654C
0x180016535  mov     r8, rbx; unsigned __int16 *
0x180016538  mov     edx, 111h; unsigned __int64
0x18001653d  mov     rcx, rdi; unsigned __int16 *
0x180016540  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016545  jmp     short loc_18001654C
0x180016547  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001654c  mov     rcx, [rsp+68h+var_10]
0x180016551  xor     rcx, rsp; StackCookie
0x180016554  call    __security_check_cookie
0x180016559  mov     rbx, [rsp+68h+arg_0]
0x18001655e  add     rsp, 60h
0x180016562  pop     rdi
0x180016563  retn
```
