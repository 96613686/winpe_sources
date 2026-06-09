# xp::XmlReader::FileStream::Read(void *,ulong,ulong *)

- ea: `0x18003a540`
- end: `0x18003a59b`
- name: `?Read@FileStream@XmlReader@xp@@UEAAJPEAXKPEAK@Z`
- size: `91`
- prototype: `__int64 __fastcall(xp::XmlReader::FileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x18003a540`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003a563`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003a563`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a56d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a56d`

## pseudocode

```c
int __fastcall xp::XmlReader::FileStream::Read(xp::XmlReader::FileStream *this, void *a2, DWORD a3, unsigned int *a4)
{
  void *v4; // rcx
  int result; // eax
  DWORD v7; // ecx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp+8h] BYREF

  v4 = (void *)*((_QWORD *)this + 2);
  NumberOfBytesRead = 0;
  if ( ReadFile(v4, a2, a3, &NumberOfBytesRead, 0) )
  {
    v7 = NumberOfBytesRead;
    result = NumberOfBytesRead == 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    v7 = 0;
  }
  if ( a4 )
    *a4 = v7;
  return result;
}

```

## disassembly

```asm
0x18003a540  push    rbx
0x18003a542  sub     rsp, 30h
0x18003a546  mov     rcx, [rcx+10h]; hFile
0x18003a54a  mov     rbx, r9
0x18003a54d  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003a552  mov     [rsp+38h+NumberOfBytesRead], 0
0x18003a55a  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18003a563  call    cs:__imp_ReadFile
0x18003a569  test    eax, eax
0x18003a56b  jnz     short loc_18003A583
0x18003a56d  call    cs:__imp_GetLastError
0x18003a573  test    eax, eax
0x18003a575  jle     short loc_18003A57F
0x18003a577  movzx   eax, ax
0x18003a57a  or      eax, 80070000h
0x18003a57f  xor     ecx, ecx
0x18003a581  jmp     short loc_18003A58E
0x18003a583  mov     ecx, [rsp+38h+NumberOfBytesRead]
0x18003a587  xor     eax, eax
0x18003a589  test    ecx, ecx
0x18003a58b  setz    al
0x18003a58e  test    rbx, rbx
0x18003a591  jz      short loc_18003A595
0x18003a593  mov     [rbx], ecx
0x18003a595  add     rsp, 30h
0x18003a599  pop     rbx
0x18003a59a  retn
```
