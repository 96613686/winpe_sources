# DeleteWatermarkState(ushort const *,ushort const *)

- ea: `0x18002a480`
- end: `0x18002a529`
- name: `?DeleteWatermarkState@@YAJPEBG0@Z`
- size: `169`
- prototype: `signed int __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18002ab90`
- `0x18002ace8`
- `0x18002ade4`
- `0x18002af60`
- `0x18002b390`
- `0x18002b480`

## callees

- `0x180008320`
- `0x180012ef0`
- `0x180021ec0`
- `0x180022a10`
- `0x18002a480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4f2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002a4e8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002a4e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
signed int __fastcall DeleteWatermarkState(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned __int64 v4; // rdx
  signed int result; // eax
  WCHAR FileName[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(FileName, 0, 0x208u);
  if ( !a2 || (result = StringCchCopyW(FileName, 0x104u, a2), result >= 0) )
  {
    result = StringCchCatW(FileName, v4, a1);
    if ( result >= 0 )
    {
      if ( DeleteFileW(FileName) )
      {
        return 0;
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002a480  mov     [rsp+arg_10], rbx
0x18002a485  push    rdi
0x18002a486  sub     rsp, 240h
0x18002a48d  mov     rax, cs:__security_cookie
0x18002a494  xor     rax, rsp
0x18002a497  mov     [rsp+248h+var_18], rax
0x18002a49f  mov     rbx, rdx
0x18002a4a2  mov     rdi, rcx
0x18002a4a5  xor     edx, edx; Val
0x18002a4a7  lea     rcx, [rsp+248h+FileName]; void *
0x18002a4ac  mov     r8d, 208h; Size
0x18002a4b2  call    memset_0
0x18002a4b7  test    rbx, rbx
0x18002a4ba  jz      short loc_18002A4D2
0x18002a4bc  mov     r8, rbx; unsigned __int16 *
0x18002a4bf  lea     rcx, [rsp+248h+FileName]; unsigned __int16 *
0x18002a4c4  mov     edx, 104h; unsigned __int64
0x18002a4c9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a4ce  test    eax, eax
0x18002a4d0  js      short loc_18002A508
0x18002a4d2  mov     r8, rdi; unsigned __int16 *
0x18002a4d5  lea     rcx, [rsp+248h+FileName]; unsigned __int16 *
0x18002a4da  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a4df  test    eax, eax
0x18002a4e1  js      short loc_18002A508
0x18002a4e3  lea     rcx, [rsp+248h+FileName]; lpFileName
0x18002a4e8  call    cs:__imp_DeleteFileW
0x18002a4ee  test    eax, eax
0x18002a4f0  jnz     short loc_18002A506
0x18002a4f2  call    cs:__imp_GetLastError
0x18002a4f8  test    eax, eax
0x18002a4fa  jle     short loc_18002A508
0x18002a4fc  movzx   eax, ax
0x18002a4ff  or      eax, 80070000h
0x18002a504  jmp     short loc_18002A508
0x18002a506  xor     eax, eax
0x18002a508  mov     rcx, [rsp+248h+var_18]
0x18002a510  xor     rcx, rsp; StackCookie
0x18002a513  call    __security_check_cookie
0x18002a518  mov     rbx, [rsp+248h+arg_10]
0x18002a520  add     rsp, 240h
0x18002a527  pop     rdi
0x18002a528  retn
```
