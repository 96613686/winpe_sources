# FormatUNCPath(ushort *,ulong,int *)

- ea: `0x1800274f4`
- end: `0x180027606`
- name: `?FormatUNCPath@@YAXPEAGKPEAH@Z`
- size: `274`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002760c`

## callees

- `0x180008320`
- `0x18000bf34`
- `0x1800274f4`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x1800275bf`
- `SHLWAPI!StrChrW` at `0x1800275bf`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800275ad`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800275ad`
- `SHLWAPI!PathStripToRootW` at `0x180027593`
- `SHLWAPI!PathStripToRootW` at `0x180027593`
- `SHLWAPI!PathIsUNCServerShareW` at `0x1800275a0`
- `SHLWAPI!PathIsUNCServerShareW` at `0x1800275a0`
- `SHLWAPI!__imp_StrCmpNICW` at `0x180027542`
- `SHLWAPI!__imp_StrCmpNICW` at `0x18002755c`
- `SHLWAPI!__imp_StrCmpNICW` at `0x180027542`
- `SHLWAPI!__imp_StrCmpNICW` at `0x18002755c`

## pseudocode

```c
void __fastcall FormatUNCPath(unsigned __int16 *a1, __int64 a2, int *a3)
{
  WCHAR *p_pszPath; // rbx
  WCHAR pszStr1[3]; // [rsp+20h] [rbp-228h] BYREF
  unsigned __int16 v7[3]; // [rsp+26h] [rbp-222h] BYREF
  WCHAR pszPath; // [rsp+2Ch] [rbp-21Ch] BYREF

  StringCchCopyW(pszStr1, 0x104u, a1);
  if ( StrCmpNICW(pszStr1, L"\\\\?", 3) )
  {
    p_pszPath = pszStr1;
  }
  else
  {
    if ( StrCmpNICW(pszStr1, L"\\\\?\\UNC\\", 8) )
    {
      StringCchCopyW(a1, 0x824u, v7);
      return;
    }
    p_pszPath = &pszPath;
    pszPath = 92;
  }
  if ( PathStripToRootW(p_pszPath) && PathIsUNCServerShareW(p_pszPath) && PathRemoveFileSpecW(p_pszPath) )
  {
    if ( StrChrW(p_pszPath, 0x2Eu) )
    {
      StringCchCopyW(a1, 0x824u, p_pszPath + 2);
      *a3 = 0;
    }
  }
}

```

## disassembly

```asm
0x1800274f4  mov     [rsp+arg_8], rbx
0x1800274f9  mov     [rsp+arg_18], rsi
0x1800274fe  push    rdi
0x1800274ff  sub     rsp, 240h
0x180027506  mov     rax, cs:__security_cookie
0x18002750d  xor     rax, rsp
0x180027510  mov     [rsp+248h+var_18], rax
0x180027518  mov     rsi, r8
0x18002751b  mov     rdi, rcx
0x18002751e  mov     r8, rcx; unsigned __int16 *
0x180027521  mov     edx, 104h; unsigned __int64
0x180027526  lea     rcx, [rsp+248h+pszStr1]; unsigned __int16 *
0x18002752b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027530  mov     r8d, 3; nChar
0x180027536  lea     rdx, asc_18002F790; "\\\\?"
0x18002753d  lea     rcx, [rsp+248h+pszStr1]; pszStr1
0x180027542  call    cs:__imp_StrCmpNICW
0x180027548  test    eax, eax
0x18002754a  jnz     short loc_18002758B
0x18002754c  lea     r8d, [rax+8]; nChar
0x180027550  lea     rdx, aUnc; "\\\\?\\UNC\\"
0x180027557  lea     rcx, [rsp+248h+pszStr1]; pszStr1
0x18002755c  call    cs:__imp_StrCmpNICW
0x180027562  test    eax, eax
0x180027564  jnz     short loc_180027577
0x180027566  mov     eax, 5Ch ; '\'
0x18002756b  lea     rbx, [rsp+248h+pszPath]
0x180027570  mov     [rsp+248h+pszPath], ax
0x180027575  jmp     short loc_180027590
0x180027577  lea     r8, [rsp+248h+var_222]; unsigned __int16 *
0x18002757c  mov     edx, 824h; unsigned __int64
0x180027581  mov     rcx, rdi; unsigned __int16 *
0x180027584  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027589  jmp     short loc_1800275E1
0x18002758b  lea     rbx, [rsp+248h+pszStr1]
0x180027590  mov     rcx, rbx; pszPath
0x180027593  call    cs:__imp_PathStripToRootW
0x180027599  test    eax, eax
0x18002759b  jz      short loc_1800275E1
0x18002759d  mov     rcx, rbx; pszPath
0x1800275a0  call    cs:__imp_PathIsUNCServerShareW
0x1800275a6  test    eax, eax
0x1800275a8  jz      short loc_1800275E1
0x1800275aa  mov     rcx, rbx; pszPath
0x1800275ad  call    cs:__imp_PathRemoveFileSpecW
0x1800275b3  test    eax, eax
0x1800275b5  jz      short loc_1800275E1
0x1800275b7  mov     edx, 2Eh ; '.'; wMatch
0x1800275bc  mov     rcx, rbx; pszStart
0x1800275bf  call    cs:__imp_StrChrW
0x1800275c5  test    rax, rax
0x1800275c8  jz      short loc_1800275E1
0x1800275ca  lea     r8, [rbx+4]; unsigned __int16 *
0x1800275ce  mov     edx, 824h; unsigned __int64
0x1800275d3  mov     rcx, rdi; unsigned __int16 *
0x1800275d6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800275db  mov     dword ptr [rsi], 0
0x1800275e1  mov     rcx, [rsp+248h+var_18]
0x1800275e9  xor     rcx, rsp; StackCookie
0x1800275ec  call    __security_check_cookie
0x1800275f1  lea     r11, [rsp+248h+var_8]
0x1800275f9  mov     rbx, [r11+18h]
0x1800275fd  mov     rsi, [r11+28h]
0x180027601  mov     rsp, r11
0x180027604  pop     rdi
0x180027605  retn
```
