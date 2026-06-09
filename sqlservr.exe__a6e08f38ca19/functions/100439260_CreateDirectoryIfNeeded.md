# CreateDirectoryIfNeeded

- ea: `0x100439260`
- end: `0x10043931e`
- name: `CreateDirectoryIfNeeded`
- size: `190`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x100439260`
- `0x100439330`

## callees

- `0x100401580`
- `0x100439260`
- `0x1004534f8`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x100439286`
- `KERNEL32!CreateDirectoryW` at `0x100439286`
- `KERNEL32!GetLastError` at `0x100439290`
- `KERNEL32!GetLastError` at `0x100439290`
- `svl!SvlPathGetParent` at `0x1004392c4`
- `svl!SvlPathGetParent` at `0x1004392c4`

## pseudocode

```c
__int64 __fastcall CreateDirectoryIfNeeded(const WCHAR *a1)
{
  unsigned int v2; // ebx
  signed int LastError; // eax
  __int64 result; // rax
  _BYTE v5[16]; // [rsp+20h] [rbp-238h] BYREF
  _BYTE v6[528]; // [rsp+30h] [rbp-228h] BYREF

  v2 = 0;
  if ( !CreateDirectoryW(a1, 0) )
  {
    LastError = GetLastError();
    if ( LastError == 3 )
    {
      v5[0] = 0;
      memset_0(v6, 0, 0x20Au);
      result = SvlPathGetParent(a1, v6, 261, v5);
      if ( (int)result < 0 || (result = CreateDirectoryIfNeeded(v6), v2 = result, (int)result < 0) )
      {
        _mm_lfence();
        return result;
      }
    }
    else if ( LastError != 183 )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      else
        return (unsigned int)LastError;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x100439260  mov     [rsp+arg_8], rbx
0x100439265  push    rdi
0x100439266  sub     rsp, 250h
0x10043926d  mov     rax, cs:__security_cookie
0x100439274  xor     rax, rsp
0x100439277  mov     [rsp+258h+var_18], rax
0x10043927f  xor     edx, edx; lpSecurityAttributes
0x100439281  mov     rdi, rcx
0x100439284  xor     ebx, ebx
0x100439286  call    cs:__imp_CreateDirectoryW
0x10043928c  test    eax, eax
0x10043928e  jnz     short loc_1004392FB
0x100439290  call    cs:__imp_GetLastError
0x100439296  cmp     eax, 3
0x100439299  jnz     short loc_1004392E3
0x10043929b  xor     edx, edx; Val
0x10043929d  mov     [rsp+258h+var_238], bl
0x1004392a1  mov     r8d, 20Ah; Size
0x1004392a7  lea     rcx, [rsp+258h+var_228]; void *
0x1004392ac  call    memset_0
0x1004392b1  lea     r9, [rsp+258h+var_238]
0x1004392b6  mov     r8d, 105h
0x1004392bc  lea     rdx, [rsp+258h+var_228]
0x1004392c1  mov     rcx, rdi
0x1004392c4  call    cs:__imp_SvlPathGetParent
0x1004392ca  test    eax, eax
0x1004392cc  js      short loc_1004392DE
0x1004392ce  lea     rcx, [rsp+258h+var_228]
0x1004392d3  call    CreateDirectoryIfNeeded
0x1004392d8  mov     ebx, eax
0x1004392da  test    eax, eax
0x1004392dc  jns     short loc_1004392FB
0x1004392de  lfence
0x1004392e1  jmp     short loc_1004392FD
0x1004392e3  cmp     eax, 0B7h
0x1004392e8  jz      short loc_1004392FB
0x1004392ea  test    eax, eax
0x1004392ec  jg      short loc_1004392F2
0x1004392ee  mov     ebx, eax
0x1004392f0  jmp     short loc_1004392FB
0x1004392f2  movzx   ebx, ax
0x1004392f5  or      ebx, 80070000h
0x1004392fb  mov     eax, ebx
0x1004392fd  mov     rcx, [rsp+258h+var_18]
0x100439305  xor     rcx, rsp; StackCookie
0x100439308  call    __security_check_cookie
0x10043930d  mov     rbx, [rsp+258h+arg_8]
0x100439315  add     rsp, 250h
0x10043931c  pop     rdi
0x10043931d  retn
```
