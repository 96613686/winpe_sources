# AslEnvGetSysNativeDirPathForGuestBuf

- ea: `0x14000f158`
- end: `0x14000f286`
- name: `AslEnvGetSysNativeDirPathForGuestBuf`
- size: `302`
- prototype: `__int64 __fastcall(_WORD *, __int64, _WORD *, unsigned __int16, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140013060`

## callees

- `0x14000f158`
- `0x14000f28c`
- `0x14001008c`
- `0x1400100c4`
- `0x1400103d8`
- `0x140011d6c`
- `0x14002e3e2`
- `0x14002e420`

## string_xrefs

- `0x14000f22b`: `RtlStringCchCopyW failed [%x]`
- `0x14000f1d3`: `AslPathToSystemPathBuf failed [%x]`
- `0x14000f206`: `AslPathCombine failed [%x]`
- `0x14000f238`: `AslEnvGetSysNativeDirPathForGuestBuf`

## pseudocode

```c
__int64 __fastcall AslEnvGetSysNativeDirPathForGuestBuf(
        _WORD *a1,
        __int64 a2,
        _WORD *a3,
        unsigned __int16 a4,
        _WORD *a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  const char *v11; // r9
  __int64 v12; // r8
  int v14; // [rsp+20h] [rbp-C8h]
  unsigned __int16 v15[64]; // [rsp+30h] [rbp-B8h] BYREF

  memset_0(v15, 0, sizeof(v15));
  *a1 = 0;
  if ( a5 && *a5 != a4 )
  {
    v9 = AslPathToSystemPathBuf(v15, 0x40u, L"\\SysNative");
    v10 = v9;
    if ( v9 < 0 )
    {
      v11 = "AslPathToSystemPathBuf failed [%x]";
      v12 = 1847;
LABEL_11:
      v14 = v9;
      AslLogCallPrintf(1, "AslEnvGetSysNativeDirPathForGuestBuf", v12, v11, v14);
      return v10;
    }
    if ( a3 && *a3 )
    {
      v9 = AslPathCombine(v15, a3, a1, a2);
      v10 = v9;
      if ( v9 < 0 )
      {
        v11 = "AslPathCombine failed [%x]";
        v12 = 1857;
        goto LABEL_11;
      }
    }
    else
    {
      v9 = RtlStringCchCopyW(a1, a2, v15);
      v10 = v9;
      if ( v9 < 0 )
      {
        v11 = "RtlStringCchCopyW failed [%x]";
        v12 = 1865;
        goto LABEL_11;
      }
    }
    return v10;
  }
  return AslEnvGetSystem32DirPathBuf((_DWORD)a1, a2, (_DWORD)a3, a4, (__int64)a5);
}

```

## disassembly

```asm
0x14000f158  push    rbx
0x14000f15a  push    rbp
0x14000f15b  push    rsi
0x14000f15c  push    rdi
0x14000f15d  push    r14
0x14000f15f  sub     rsp, 0C0h
0x14000f166  mov     rax, cs:__security_cookie
0x14000f16d  xor     rax, rsp
0x14000f170  mov     [rsp+0E8h+var_38], rax
0x14000f178  mov     rdi, r8
0x14000f17b  mov     rbp, rdx
0x14000f17e  mov     rsi, rcx
0x14000f181  xor     edx, edx; Val
0x14000f183  mov     r8d, 80h; Size
0x14000f189  lea     rcx, [rsp+0E8h+var_B8]; void *
0x14000f18e  movzx   ebx, r9w
0x14000f192  call    memset_0
0x14000f197  mov     rax, [rsp+0E8h+arg_20]
0x14000f19f  xor     r14d, r14d
0x14000f1a2  mov     [rsi], r14w
0x14000f1a6  test    rax, rax
0x14000f1a9  jz      loc_14000F251
0x14000f1af  cmp     [rax], bx
0x14000f1b2  jz      loc_14000F251
0x14000f1b8  lea     r8, aSysnative; "\\SysNative"
0x14000f1bf  lea     edx, [r14+40h]; unsigned __int64
0x14000f1c3  lea     rcx, [rsp+0E8h+var_B8]; unsigned __int16 *
0x14000f1c8  call    AslPathToSystemPathBuf
0x14000f1cd  mov     ebx, eax
0x14000f1cf  test    eax, eax
0x14000f1d1  jns     short loc_14000F1E2
0x14000f1d3  lea     r9, aAslpathtosyste; "AslPathToSystemPathBuf failed [%x]"
0x14000f1da  mov     r8d, 737h
0x14000f1e0  jmp     short loc_14000F238
0x14000f1e2  test    rdi, rdi
0x14000f1e5  jz      short loc_14000F215
0x14000f1e7  cmp     [rdi], r14w
0x14000f1eb  jz      short loc_14000F215
0x14000f1ed  mov     r9, rbp
0x14000f1f0  lea     rcx, [rsp+0E8h+var_B8]
0x14000f1f5  mov     r8, rsi
0x14000f1f8  mov     rdx, rdi
0x14000f1fb  call    AslPathCombine
0x14000f200  mov     ebx, eax
0x14000f202  test    eax, eax
0x14000f204  jns     short loc_14000F24D
0x14000f206  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x14000f20d  mov     r8d, 741h
0x14000f213  jmp     short loc_14000F238
0x14000f215  lea     r8, [rsp+0E8h+var_B8]
0x14000f21a  mov     rdx, rbp
0x14000f21d  mov     rcx, rsi
0x14000f220  call    RtlStringCchCopyW
0x14000f225  mov     ebx, eax
0x14000f227  test    eax, eax
0x14000f229  jns     short loc_14000F24D
0x14000f22b  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14000f232  mov     r8d, 749h
0x14000f238  lea     rdx, aAslenvgetsysna; "AslEnvGetSysNativeDirPathForGuestBuf"
0x14000f23f  mov     [rsp+0E8h+var_C8], eax
0x14000f243  mov     ecx, 1
0x14000f248  call    AslLogCallPrintf
0x14000f24d  mov     eax, ebx
0x14000f24f  jmp     short loc_14000F268
0x14000f251  movzx   r9d, bx
0x14000f255  mov     qword ptr [rsp+0E8h+var_C8], rax
0x14000f25a  mov     r8, rdi
0x14000f25d  mov     rdx, rbp
0x14000f260  mov     rcx, rsi
0x14000f263  call    AslEnvGetSystem32DirPathBuf
0x14000f268  mov     rcx, [rsp+0E8h+var_38]
0x14000f270  xor     rcx, rsp; StackCookie
0x14000f273  call    __security_check_cookie
0x14000f278  add     rsp, 0C0h
0x14000f27f  pop     r14
0x14000f281  pop     rdi
0x14000f282  pop     rsi
0x14000f283  pop     rbp
0x14000f284  pop     rbx
0x14000f285  retn
```
