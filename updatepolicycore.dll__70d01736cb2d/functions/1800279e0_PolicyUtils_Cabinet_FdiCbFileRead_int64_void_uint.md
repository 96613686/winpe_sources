# PolicyUtils::Cabinet::FdiCbFileRead(__int64,void *,uint)

- ea: `0x1800279e0`
- end: `0x180027a2d`
- name: `?FdiCbFileRead@Cabinet@PolicyUtils@@YAI_JPEAXI@Z`
- size: `77`
- prototype: `__int64 __fastcall(INT_PTR hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180027a09`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180027a09`

## pseudocode

```c
__int64 __fastcall PolicyUtils::Cabinet::FdiCbFileRead(INT_PTR hf, void *pv, UINT cb)
{
  BOOL v3; // eax
  unsigned int v4; // ecx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-18h] BYREF

  NumberOfBytesRead = 0;
  v3 = ReadFile((HANDLE)hf, pv, cb, &NumberOfBytesRead, 0);
  v4 = -1;
  if ( v3 )
    return NumberOfBytesRead;
  return v4;
}

```

## disassembly

```asm
0x1800279e0  sub     rsp, 48h
0x1800279e4  mov     rax, cs:__security_cookie
0x1800279eb  xor     rax, rsp
0x1800279ee  mov     [rsp+48h+var_10], rax
0x1800279f3  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800279f8  mov     [rsp+48h+NumberOfBytesRead], 0
0x180027a00  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180027a09  call    cs:__imp_ReadFile
0x180027a0f  or      ecx, 0FFFFFFFFh
0x180027a12  test    eax, eax
0x180027a14  cmovnz  ecx, [rsp+48h+NumberOfBytesRead]
0x180027a19  mov     eax, ecx
0x180027a1b  mov     rcx, [rsp+48h+var_10]
0x180027a20  xor     rcx, rsp; StackCookie
0x180027a23  call    __security_check_cookie
0x180027a28  add     rsp, 48h
0x180027a2c  retn
```
