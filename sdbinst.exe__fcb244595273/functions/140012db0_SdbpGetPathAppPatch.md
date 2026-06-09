# SdbpGetPathAppPatch

- ea: `0x140012db0`
- end: `0x140012e93`
- name: `SdbpGetPathAppPatch`
- size: `227`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x140012ea0`
- `0x1400131a0`
- `0x140013280`
- `0x1400133f0`

## callees

- `0x14001008c`
- `0x1400100c4`
- `0x1400103d8`
- `0x140012db0`
- `0x14002e420`

## string_xrefs

- `0x140012e54`: `AslPathToSystemPathBuf failed [%x]`
- `0x140012e2f`: `AslPathCombine failed [%x]`
- `0x140012e61`: `SdbpGetPathAppPatch`

## pseudocode

```c
__int64 __fastcall SdbpGetPathAppPatch(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r10
  int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 v10; // r8
  __int128 v11; // [rsp+30h] [rbp-258h] BYREF
  int v12; // [rsp+40h] [rbp-248h]
  unsigned __int16 v13[264]; // [rsp+50h] [rbp-238h] BYREF

  v3 = a3;
  v12 = *(_DWORD *)L"h";
  v11 = *(_OWORD *)L"\\AppPatch";
  if ( a2 < 0xA )
    return 3221225507LL;
  *a1 = 0;
  v13[0] = 0;
  if ( !a3 )
    v3 = (unsigned __int16 *)&Format;
  v7 = AslPathCombine(&v11, v3, v13, 260);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = "AslPathCombine failed [%x]";
    v10 = 953;
LABEL_9:
    AslLogCallPrintf(1, "SdbpGetPathAppPatch", v10, v9, v7);
    return v8;
  }
  v7 = AslPathToSystemPathBuf(a1, a2, v13);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = "AslPathToSystemPathBuf failed [%x]";
    v10 = 959;
    goto LABEL_9;
  }
  return v8;
}

```

## disassembly

```asm
0x140012db0  push    rbx
0x140012db2  push    rsi
0x140012db3  push    rdi
0x140012db4  sub     rsp, 270h
0x140012dbb  mov     rax, cs:__security_cookie
0x140012dc2  xor     rax, rsp
0x140012dc5  mov     [rsp+288h+var_28], rax
0x140012dcd  mov     eax, dword ptr cs:aApppatch_0+10h; "h"
0x140012dd3  mov     r10, r8
0x140012dd6  mov     [rsp+288h+var_248], eax
0x140012dda  mov     rsi, rdx
0x140012ddd  mov     rdi, rcx
0x140012de0  movups  xmm0, xmmword ptr cs:aApppatch_0; "\\AppPatch"
0x140012de7  movups  [rsp+288h+var_258], xmm0
0x140012dec  cmp     rdx, 0Ah
0x140012df0  jnb     short loc_140012DF9
0x140012df2  mov     eax, 0C0000023h
0x140012df7  jmp     short loc_140012E78
0x140012df9  xor     eax, eax
0x140012dfb  lea     r8, [rsp+288h+var_238]
0x140012e00  mov     [rcx], ax
0x140012e03  test    r10, r10
0x140012e06  mov     [rsp+288h+var_238], ax
0x140012e0b  lea     rcx, [rsp+288h+var_258]
0x140012e10  lea     rax, Format
0x140012e17  mov     r9d, 104h
0x140012e1d  cmovz   r10, rax
0x140012e21  mov     rdx, r10
0x140012e24  call    AslPathCombine
0x140012e29  mov     ebx, eax
0x140012e2b  test    eax, eax
0x140012e2d  jns     short loc_140012E3E
0x140012e2f  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x140012e36  mov     r8d, 3B9h
0x140012e3c  jmp     short loc_140012E61
0x140012e3e  lea     r8, [rsp+288h+var_238]; unsigned __int16 *
0x140012e43  mov     rdx, rsi; unsigned __int64
0x140012e46  mov     rcx, rdi; unsigned __int16 *
0x140012e49  call    AslPathToSystemPathBuf
0x140012e4e  mov     ebx, eax
0x140012e50  test    eax, eax
0x140012e52  jns     short loc_140012E76
0x140012e54  lea     r9, aAslpathtosyste; "AslPathToSystemPathBuf failed [%x]"
0x140012e5b  mov     r8d, 3BFh
0x140012e61  lea     rdx, aSdbpgetpathapp_0; "SdbpGetPathAppPatch"
0x140012e68  mov     [rsp+288h+var_268], eax
0x140012e6c  mov     ecx, 1
0x140012e71  call    AslLogCallPrintf
0x140012e76  mov     eax, ebx
0x140012e78  mov     rcx, [rsp+288h+var_28]
0x140012e80  xor     rcx, rsp; StackCookie
0x140012e83  call    __security_check_cookie
0x140012e88  add     rsp, 270h
0x140012e8f  pop     rdi
0x140012e90  pop     rsi
0x140012e91  pop     rbx
0x140012e92  retn
```
