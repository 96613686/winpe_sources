# FilePayloadHandler::BackupCurrentPayload(void)

- ea: `0x18003daf0`
- end: `0x18003db3f`
- name: `?BackupCurrentPayload@FilePayloadHandler@@UEAAXXZ`
- size: `79`
- prototype: `void __fastcall(FilePayloadHandler *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x1800101e0`
- `0x180019e68`
- `0x18003daf0`

## import_xrefs

- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18003db19`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18003db19`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FilePayloadHandler::BackupCurrentPayload(FilePayloadHandler *this)
{
  char *v1; // rcx
  __int64 v2; // r8
  const WCHAR *v3; // rax
  LPCWSTR v4; // rdx
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (char *)this + 104;
  if ( *((_QWORD *)v1 + 2) )
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v1);
    v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v2 + 72);
    if ( !CopyFileW(v3, v4, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x8A,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\payloadhandlers\\filepayloadhandler.cpp",
        v5);
  }
}

```

## disassembly

```asm
0x18003daf0  sub     rsp, 28h
0x18003daf4  mov     r8, rcx
0x18003daf7  add     rcx, 68h ; 'h'
0x18003dafb  cmp     qword ptr [rcx+10h], 0
0x18003db00  jz      short loc_18003DB3A
0x18003db02  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003db07  lea     rcx, [r8+48h]
0x18003db0b  mov     rdx, rax
0x18003db0e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003db13  mov     rcx, rax; lpExistingFileName
0x18003db16  xor     r8d, r8d; bFailIfExists
0x18003db19  call    cs:__imp_CopyFileW
0x18003db1f  test    eax, eax
0x18003db21  jnz     short loc_18003DB3A
0x18003db23  mov     rcx, [rsp+28h]; this
0x18003db28  lea     r8, aOnecoreBaseFli_9; "onecore\\base\\flighting\\onesettings\\"...
0x18003db2f  mov     edx, 8Ah; void *
0x18003db34  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003db3a  add     rsp, 28h
0x18003db3e  retn
```
