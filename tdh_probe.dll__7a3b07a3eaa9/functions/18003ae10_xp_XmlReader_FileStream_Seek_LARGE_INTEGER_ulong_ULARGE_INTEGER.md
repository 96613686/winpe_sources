# xp::XmlReader::FileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x18003ae10`
- end: `0x18003ae68`
- name: `?Seek@FileStream@XmlReader@xp@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `88`
- prototype: `int(xp::XmlReader::FileStream *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x18003ae10`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003ae2e`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18003ae2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae38`

## pseudocode

```c
__int64 __fastcall xp::XmlReader::FileStream::Seek(
        xp::XmlReader::FileStream *this,
        LARGE_INTEGER a2,
        DWORD a3,
        union _ULARGE_INTEGER *a4)
{
  void *v4; // rcx
  signed int LastError; // eax
  unsigned int v7; // ecx
  ULONGLONG QuadPart; // rax
  union _LARGE_INTEGER NewFilePointer; // [rsp+30h] [rbp+8h] BYREF

  v4 = (void *)*((_QWORD *)this + 2);
  NewFilePointer.QuadPart = 0;
  if ( SetFilePointerEx(v4, a2, &NewFilePointer, a3) )
  {
    QuadPart = NewFilePointer.QuadPart;
    v7 = 0;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    QuadPart = 0;
  }
  if ( a4 )
    a4->QuadPart = QuadPart;
  return v7;
}

```

## disassembly

```asm
0x18003ae10  push    rbx
0x18003ae12  sub     rsp, 20h
0x18003ae16  mov     rcx, [rcx+10h]; hFile
0x18003ae1a  mov     rbx, r9
0x18003ae1d  mov     r9d, r8d; dwMoveMethod
0x18003ae20  mov     qword ptr [rsp+28h+NewFilePointer], 0
0x18003ae29  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x18003ae2e  call    cs:__imp_SetFilePointerEx
0x18003ae34  test    eax, eax
0x18003ae36  jnz     short loc_18003AE51
0x18003ae38  call    cs:__imp_GetLastError
0x18003ae3e  mov     ecx, eax
0x18003ae40  test    eax, eax
0x18003ae42  jle     short loc_18003AE4D
0x18003ae44  movzx   ecx, ax
0x18003ae47  or      ecx, 80070000h
0x18003ae4d  xor     eax, eax
0x18003ae4f  jmp     short loc_18003AE58
0x18003ae51  mov     rax, qword ptr [rsp+28h+NewFilePointer]
0x18003ae56  xor     ecx, ecx
0x18003ae58  test    rbx, rbx
0x18003ae5b  jz      short loc_18003AE60
0x18003ae5d  mov     [rbx], rax
0x18003ae60  mov     eax, ecx
0x18003ae62  add     rsp, 20h
0x18003ae66  pop     rbx
0x18003ae67  retn
```
