# WritePrivateProfileStringMultiW(ushort const *,ushort const *,ushort *,CStrUTF7 &,ushort const *,ushort const *)

- ea: `0x18000c2c4`
- end: `0x18000c3d9`
- name: `?WritePrivateProfileStringMultiW@@YAHPEBG0PEAGAEAVCStrUTF7@@00@Z`
- size: `277`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, struct CStrUTF7 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000c090`

## callees

- `0x18000b430`
- `0x18000c2c4`
- `0x18000c3e0`
- `0x180012550`
- `0x180013066`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000c338`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000c338`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18000c308`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18000c32f`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18000c394`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18000c308`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18000c32f`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x18000c394`

## pseudocode

```c
__int64 __fastcall WritePrivateProfileStringMultiW(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct CStrUTF7 *a4,
        const unsigned __int16 *lpKeyName,
        const unsigned __int16 *lpFileName)
{
  unsigned int v9; // ebp
  const char *v10; // rdx
  int v11; // r8d
  LPCWSTR lpString; // [rsp+20h] [rbp-468h] BYREF
  _BYTE v14[1040]; // [rsp+28h] [rbp-460h] BYREF
  int v15; // [rsp+438h] [rbp-50h]

  v9 = WritePrivateProfileStringW(a1, lpKeyName, a2, lpFileName);
  if ( a3 )
  {
    WritePrivateProfileStringW(
      a3,
      lpKeyName,
      (LPCWSTR)((unsigned __int64)a2 & -(__int64)(*((_QWORD *)a4 + 1) != 0)),
      lpFileName);
    a3[lstrlenW(a3) - 1] = 87;
    lpString = 0;
    memset_0(v14, 0, sizeof(v14));
    v10 = (const char *)*((_QWORD *)a4 + 1);
    v15 = 0;
    CStrInW::Init((CStrInW *)&lpString, v10, v11);
    if ( v15 )
      WritePrivateProfileStringW(a3, lpKeyName, lpString, lpFileName);
    if ( lpString != (LPCWSTR)v14 && ((unsigned __int64)lpString & 0xFFFFFFFFFFFF0000uLL) != 0 )
      operator delete((void *)lpString);
  }
  return v9;
}

```

## disassembly

```asm
0x18000c2c4  push    rbx
0x18000c2c6  push    rbp
0x18000c2c7  push    rsi
0x18000c2c8  push    rdi
0x18000c2c9  push    r14
0x18000c2cb  push    r15
0x18000c2cd  sub     rsp, 458h
0x18000c2d4  mov     rax, cs:__security_cookie
0x18000c2db  xor     rax, rsp
0x18000c2de  mov     [rsp+488h+var_48], rax
0x18000c2e6  mov     rdi, [rsp+488h+lpKeyName]
0x18000c2ee  mov     rbx, r8
0x18000c2f1  mov     rsi, [rsp+488h+lpFileName]
0x18000c2f9  mov     r8, rdx; lpString
0x18000c2fc  mov     r15, r9
0x18000c2ff  mov     r14, rdx
0x18000c302  mov     r9, rsi; lpFileName
0x18000c305  mov     rdx, rdi; lpKeyName
0x18000c308  call    cs:__imp_WritePrivateProfileStringW
0x18000c30e  mov     ebp, eax
0x18000c310  test    rbx, rbx
0x18000c313  jz      loc_18000C3B7
0x18000c319  mov     rcx, [r15+8]
0x18000c31d  mov     r9, rsi; lpFileName
0x18000c320  neg     rcx
0x18000c323  mov     rdx, rdi; lpKeyName
0x18000c326  mov     rcx, rbx; lpAppName
0x18000c329  sbb     r8, r8
0x18000c32c  and     r8, r14; lpString
0x18000c32f  call    cs:__imp_WritePrivateProfileStringW
0x18000c335  mov     rcx, rbx; lpString
0x18000c338  call    cs:__imp_lstrlenW
0x18000c33e  movsxd  rcx, eax
0x18000c341  xor     edx, edx; Val
0x18000c343  mov     r8d, 410h; Size
0x18000c349  mov     word ptr [rbx+rcx*2-2], 57h ; 'W'
0x18000c350  lea     rcx, [rsp+488h+var_460]; void *
0x18000c355  mov     [rsp+488h+lpString], 0
0x18000c35e  call    memset_0
0x18000c363  mov     rdx, [r15+8]; char *
0x18000c367  lea     rcx, [rsp+488h+lpString]; this
0x18000c36c  mov     [rsp+488h+var_50], 0
0x18000c377  call    ?Init@CStrInW@@IEAAXPEBDH@Z; CStrInW::Init(char const *,int)
0x18000c37c  cmp     [rsp+488h+var_50], 0
0x18000c384  jz      short loc_18000C39A
0x18000c386  mov     r8, [rsp+488h+lpString]; lpString
0x18000c38b  mov     r9, rsi; lpFileName
0x18000c38e  mov     rdx, rdi; lpKeyName
0x18000c391  mov     rcx, rbx; lpAppName
0x18000c394  call    cs:__imp_WritePrivateProfileStringW
0x18000c39a  mov     rcx, [rsp+488h+lpString]; lpMem
0x18000c39f  lea     rax, [rsp+488h+var_460]
0x18000c3a4  cmp     rcx, rax
0x18000c3a7  jz      short loc_18000C3B7
0x18000c3a9  test    rcx, 0FFFFFFFFFFFF0000h
0x18000c3b0  jz      short loc_18000C3B7
0x18000c3b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c3b7  mov     eax, ebp
0x18000c3b9  mov     rcx, [rsp+488h+var_48]
0x18000c3c1  xor     rcx, rsp; StackCookie
0x18000c3c4  call    __security_check_cookie
0x18000c3c9  add     rsp, 458h
0x18000c3d0  pop     r15
0x18000c3d2  pop     r14
0x18000c3d4  pop     rdi
0x18000c3d5  pop     rsi
0x18000c3d6  pop     rbp
0x18000c3d7  pop     rbx
0x18000c3d8  retn
```
