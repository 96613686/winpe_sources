# WdsRemoveDirectoryWithFlags

- ea: `0x18000b348`
- end: `0x18000b37a`
- name: `WdsRemoveDirectoryWithFlags`
- size: `50`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006b48`
- `0x18000b380`
- `0x18000b5f8`

## callees

- `0x18000aa40`
- `0x18000b230`
- `0x18000b348`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b356`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b356`

## pseudocode

```c
__int64 __fastcall WdsRemoveDirectoryWithFlags(__int64 a1, char a2)
{
  int v3; // edx

  if ( a1 )
  {
    v3 = a2 & 0x21;
    if ( v3 )
      return DeleteFileEx2(a1, v3);
    else
      return WdsRemoveDirectory();
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18000b348  sub     rsp, 28h
0x18000b34c  test    rcx, rcx
0x18000b34f  jnz     short loc_18000B363
0x18000b351  mov     ecx, 57h ; 'W'; dwErrCode
0x18000b356  call    cs:__imp_SetLastError
0x18000b35c  xor     eax, eax
0x18000b35e  add     rsp, 28h
0x18000b362  retn
0x18000b363  and     edx, 21h
0x18000b366  jnz     short loc_18000B371
0x18000b368  add     rsp, 28h
0x18000b36c  jmp     WdsRemoveDirectory
0x18000b371  add     rsp, 28h
0x18000b375  jmp     DeleteFileEx2
```
