# p9fs::util::FsUtilDirect::RenameFile(void *,void *,std::basic_string_view<ushort,std::char_traits<ushort>>)

- ea: `0x18002c6e0`
- end: `0x18002c77d`
- name: `?RenameFile@FsUtilDirect@util@p9fs@@UEAAJPEAX0V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180004120`
- `0x180004c98`
- `0x18001d8b4`
- `0x18002c6e0`

## import_xrefs

- `lxutil!LxUtilFsRename` at `0x18002c73a`
- `lxutil!LxUtilFsRename` at `0x18002c73a`

## pseudocode

```c
__int64 __fastcall p9fs::util::FsUtilDirect::RenameFile(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  unsigned __int16 v5; // r8
  __int64 v6; // rax
  __int64 v7; // r9
  __int128 pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int64 v10; // [rsp+40h] [rbp-28h]
  _WORD v11[2]; // [rsp+48h] [rbp-20h] BYREF
  int v12; // [rsp+4Ch] [rbp-1Ch]
  __int64 v13; // [rsp+50h] [rbp-18h]

  v5 = 2 * *((_WORD *)a4 + 4);
  if ( v5 != 2 * a4[1] )
  {
    pExceptionObject = 0;
    v10 = 0;
    gsl::narrowing_error::narrowing_error((gsl::narrowing_error *)&pExceptionObject);
    throw (gsl::narrowing_error *)&pExceptionObject;
  }
  v11[0] = 2 * *((_WORD *)a4 + 4);
  v12 = 0;
  v6 = *a4;
  v7 = *(_QWORD *)(a1 + 8);
  v11[1] = v5;
  v13 = v6;
  return LxUtilFsRename(a2, a3, v11, v7, 0);
}

```

## disassembly

```asm
0x18002c6e0  sub     rsp, 68h
0x18002c6e4  mov     rax, cs:__security_cookie
0x18002c6eb  xor     rax, rsp
0x18002c6ee  mov     [rsp+68h+var_10], rax
0x18002c6f3  mov     rax, [r9+8]
0x18002c6f7  mov     r11, r8
0x18002c6fa  add     rax, rax
0x18002c6fd  mov     r10, rdx
0x18002c700  movzx   r8d, ax
0x18002c704  cmp     r8, rax
0x18002c707  jnz     short loc_18002C752
0x18002c709  xor     eax, eax
0x18002c70b  mov     [rsp+68h+var_20], r8w
0x18002c711  mov     [rsp+68h+var_1C], eax
0x18002c715  mov     rdx, r11
0x18002c718  mov     rax, [r9]
0x18002c71b  mov     r9, [rcx+8]
0x18002c71f  mov     rcx, r10
0x18002c722  mov     [rsp+68h+var_1E], r8w
0x18002c728  lea     r8, [rsp+68h+var_20]
0x18002c72d  mov     [rsp+68h+var_18], rax
0x18002c732  mov     [rsp+68h+var_48], 0
0x18002c73a  call    cs:__imp_LxUtilFsRename
0x18002c740  mov     rcx, [rsp+68h+var_10]
0x18002c745  xor     rcx, rsp; StackCookie
0x18002c748  call    __security_check_cookie
0x18002c74d  add     rsp, 68h
0x18002c751  retn
0x18002c752  xorps   xmm0, xmm0
0x18002c755  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18002c75a  xor     eax, eax
0x18002c75c  movups  [rsp+68h+pExceptionObject], xmm0
0x18002c761  mov     [rsp+68h+var_28], rax
0x18002c766  call    ??0narrowing_error@gsl@@QEAA@XZ; gsl::narrowing_error::narrowing_error(void)
0x18002c76b  lea     rdx, _TI2?AUnarrowing_error@gsl@@; pThrowInfo
0x18002c772  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002c777  call    _CxxThrowException_0
```
