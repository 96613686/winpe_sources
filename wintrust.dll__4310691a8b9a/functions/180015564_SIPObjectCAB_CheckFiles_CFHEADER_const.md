# SIPObjectCAB_::CheckFiles(CFHEADER const &)

- ea: `0x180015564`
- end: `0x180015608`
- name: `?CheckFiles@SIPObjectCAB_@@AEAAHAEBUCFHEADER@@@Z`
- size: `164`
- prototype: `__int64 __fastcall(HANDLE *this, const struct CFHEADER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800151a8`

## callees

- `0x180015564`
- `0x180015610`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800155c0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800155c0`

## pseudocode

```c
__int64 __fastcall SIPObjectCAB_::CheckFiles(HANDLE *this, const struct CFHEADER *a2)
{
  unsigned __int64 i; // rbx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-28h] BYREF
  __int128 Buffer; // [rsp+38h] [rbp-20h] BYREF

  NumberOfBytesRead = 0;
  Buffer = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= *((unsigned __int16 *)a2 + 14) )
      return 1;
    if ( !ReadFile(this[1], &Buffer, 0x10u, &NumberOfBytesRead, 0)
      || NumberOfBytesRead != 16
      || !(unsigned int)SIPObjectCAB_::SkipStringInFile((SIPObjectCAB_ *)this) )
    {
      break;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180015564  mov     [rsp+arg_8], rbx
0x180015569  mov     [rsp+arg_10], rsi
0x18001556e  push    rdi
0x18001556f  sub     rsp, 50h
0x180015573  mov     rax, cs:__security_cookie
0x18001557a  xor     rax, rsp
0x18001557d  mov     [rsp+58h+var_10], rax
0x180015582  xorps   xmm0, xmm0
0x180015585  mov     [rsp+58h+NumberOfBytesRead], 0
0x18001558d  movups  [rsp+58h+Buffer], xmm0
0x180015592  mov     rsi, rdx
0x180015595  mov     rdi, rcx
0x180015598  xor     ebx, ebx
0x18001559a  movzx   eax, word ptr [rsi+1Ch]
0x18001559e  cmp     rbx, rax
0x1800155a1  jnb     short loc_1800155E2
0x1800155a3  mov     rcx, [rdi+8]; hFile
0x1800155a7  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800155ac  mov     r8d, 10h; nNumberOfBytesToRead
0x1800155b2  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1800155bb  lea     rdx, [rsp+58h+Buffer]; lpBuffer
0x1800155c0  call    cs:__imp_ReadFile
0x1800155c6  test    eax, eax
0x1800155c8  jz      short loc_180015604
0x1800155ca  cmp     [rsp+58h+NumberOfBytesRead], 10h
0x1800155cf  jnz     short loc_180015604
0x1800155d1  mov     rcx, rdi; this
0x1800155d4  call    ?SkipStringInFile@SIPObjectCAB_@@AEAAHXZ; SIPObjectCAB_::SkipStringInFile(void)
0x1800155d9  test    eax, eax
0x1800155db  jz      short loc_180015604
0x1800155dd  inc     rbx
0x1800155e0  jmp     short loc_18001559A
0x1800155e2  mov     eax, 1
0x1800155e7  mov     rcx, [rsp+58h+var_10]
0x1800155ec  xor     rcx, rsp; StackCookie
0x1800155ef  call    __security_check_cookie
0x1800155f4  mov     rbx, [rsp+58h+arg_8]
0x1800155f9  mov     rsi, [rsp+58h+arg_10]
0x1800155fe  add     rsp, 50h
0x180015602  pop     rdi
0x180015603  retn
0x180015604  xor     eax, eax
0x180015606  jmp     short loc_1800155E7
```
