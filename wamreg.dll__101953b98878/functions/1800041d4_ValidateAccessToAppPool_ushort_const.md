# ValidateAccessToAppPool(ushort const *)

- ea: `0x1800041d4`
- end: `0x180004290`
- name: `?ValidateAccessToAppPool@@YAJPEBG@Z`
- size: `188`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003b90`

## callees

- `0x1800041d4`
- `0x180004298`
- `0x180006822`
- `0x180006850`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000422a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000422a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000423e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000423e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004267`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004267`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004218`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004218`

## pseudocode

```c
__int64 __fastcall ValidateAccessToAppPool(const unsigned __int16 *a1)
{
  int v2; // ebx
  _BYTE v4[32]; // [rsp+20h] [rbp-158h] BYREF
  unsigned __int16 *v5; // [rsp+40h] [rbp-138h]
  unsigned __int16 v6[128]; // [rsp+60h] [rbp-118h] BYREF

  memset_0(v6, 0, sizeof(v6));
  STRU::STRU((STRU *)v4, v6, 0x80u);
  v2 = STRU::Copy((STRU *)v4, L"\\LM\\W3SVC\\AppPools\\");
  if ( v2 >= 0 )
  {
    v2 = STRU::Append((STRU *)v4, a1);
    if ( v2 >= 0 )
    {
      v2 = ValidateAccessToMetabaseKey(v5, 3u);
      if ( v2 >= 0 )
        v2 = 0;
    }
  }
  STRU::~STRU((STRU *)v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800041d4  mov     [rsp+arg_8], rbx
0x1800041d9  push    rdi
0x1800041da  sub     rsp, 170h
0x1800041e1  mov     rax, cs:__security_cookie
0x1800041e8  xor     rax, rsp
0x1800041eb  mov     [rsp+178h+var_18], rax
0x1800041f3  mov     rdi, rcx
0x1800041f6  xor     edx, edx; Val
0x1800041f8  lea     rcx, [rsp+178h+var_118]; void *
0x1800041fd  mov     r8d, 100h; Size
0x180004203  call    memset_0
0x180004208  mov     r8d, 80h
0x18000420e  lea     rdx, [rsp+178h+var_118]
0x180004213  lea     rcx, [rsp+178h+var_158]
0x180004218  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000421e  lea     rdx, aLmW3svcApppool_0; "\\LM\\W3SVC\\AppPools\\"
0x180004225  lea     rcx, [rsp+178h+var_158]
0x18000422a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004230  mov     ebx, eax
0x180004232  test    eax, eax
0x180004234  js      short loc_180004262
0x180004236  mov     rdx, rdi
0x180004239  lea     rcx, [rsp+178h+var_158]
0x18000423e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004244  mov     ebx, eax
0x180004246  test    eax, eax
0x180004248  js      short loc_180004262
0x18000424a  mov     rcx, [rsp+178h+var_138]; unsigned __int16 *
0x18000424f  mov     edx, 3; unsigned int
0x180004254  call    ?ValidateAccessToMetabaseKey@@YAJPEBGK@Z; ValidateAccessToMetabaseKey(ushort const *,ulong)
0x180004259  mov     ebx, eax
0x18000425b  xor     eax, eax
0x18000425d  test    ebx, ebx
0x18000425f  cmovns  ebx, eax
0x180004262  lea     rcx, [rsp+178h+var_158]
0x180004267  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000426d  mov     eax, ebx
0x18000426f  mov     rcx, [rsp+178h+var_18]
0x180004277  xor     rcx, rsp; StackCookie
0x18000427a  call    __security_check_cookie
0x18000427f  mov     rbx, [rsp+178h+arg_8]
0x180004287  add     rsp, 170h
0x18000428e  pop     rdi
0x18000428f  retn
```
