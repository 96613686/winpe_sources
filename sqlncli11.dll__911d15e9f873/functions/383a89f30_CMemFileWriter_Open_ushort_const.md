# CMemFileWriter::Open(ushort const *)

- ea: `0x383a89f30`
- end: `0x383a8a03e`
- name: `?Open@CMemFileWriter@@UEAAJPEBG@Z`
- size: `270`
- prototype: `__int64 __fastcall(CMemFileWriter *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x38391aed0`
- `0x383a89500`
- `0x383a89f30`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x383a8a01f`
- `KERNEL32!CloseHandle` at `0x383a8a01f`
- `KERNEL32!MapViewOfFile` at `0x383a89fe1`
- `KERNEL32!MapViewOfFile` at `0x383a89fe1`
- `KERNEL32!CreateFileMappingW` at `0x383a89fb6`
- `KERNEL32!CreateFileMappingW` at `0x383a89fb6`

## pseudocode

```c
int __fastcall CMemFileWriter::Open(HANDLE *this, const unsigned __int16 *a2)
{
  int result; // eax
  int v4; // edi
  HANDLE FileMappingW; // rax
  LPVOID v6; // rax
  void *v7; // rax

  result = CFileWriter::Open((CFileWriter *)this, a2);
  v4 = result;
  if ( result >= 0 )
  {
    FileMappingW = CreateFileMappingW(this[1], 0, 4u, 0, 0x100000u, 0);
    this[5] = FileMappingW;
    if ( FileMappingW )
    {
      *((_DWORD *)this + 19) = 0x100000;
      v6 = MapViewOfFile(FileMappingW, 2u, 0, 0, 0x100000u);
      this[6] = v6;
      if ( v6 )
      {
        v7 = (void *)*((unsigned int *)this + 19);
        this[7] = 0;
        this[8] = 0;
        *((_DWORD *)this + 18) = 0;
        this[2] = v7;
        result = v4;
        *((_DWORD *)this + 8) = 1;
        return result;
      }
      CloseHandle(this[5]);
      this[5] = 0;
    }
    return 1;
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    if ( off_383B49128[0] )
    {
      bidTraceW(off_383B43488[0], 860201, off_383B49128[0], (unsigned int)result);
      return v4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x383a89f30  mov     [rsp+arg_8], rbx
0x383a89f35  push    rdi
0x383a89f36  sub     rsp, 30h
0x383a89f3a  mov     rbx, rcx
0x383a89f3d  call    ?Open@CFileWriter@@UEAAJPEBG@Z; CFileWriter::Open(ushort const *)
0x383a89f42  mov     edi, eax
0x383a89f44  test    eax, eax
0x383a89f46  jns     short loc_383A89F95
0x383a89f48  test    byte ptr cs:_bidGblFlags, 2
0x383a89f4f  jz      loc_383A8A033
0x383a89f55  mov     rcx, cs:off_383B43488; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a89f5c  mov     rdx, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a89f63  test    rdx, rdx
0x383a89f66  jz      loc_383A8A033
0x383a89f6c  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a89f73  mov     r9d, eax
0x383a89f76  mov     edx, 0D2029h
0x383a89f7b  mov     [rsp+38h+dwMaximumSizeLow], 348h
0x383a89f83  call    _bidTraceW
0x383a89f88  mov     eax, edi
0x383a89f8a  mov     rbx, [rsp+38h+arg_8]
0x383a89f8f  add     rsp, 30h
0x383a89f93  pop     rdi
0x383a89f94  retn
0x383a89f95  mov     rcx, [rbx+8]; hFile
0x383a89f99  mov     [rsp+38h+arg_0], rsi
0x383a89f9e  xor     esi, esi
0x383a89fa0  lea     r8d, [rsi+4]; flProtect
0x383a89fa4  xor     r9d, r9d; dwMaximumSizeHigh
0x383a89fa7  xor     edx, edx; lpFileMappingAttributes
0x383a89fa9  mov     [rsp+38h+lpName], rsi; lpName
0x383a89fae  mov     [rsp+38h+dwMaximumSizeLow], 100000h; dwMaximumSizeLow
0x383a89fb6  call    cs:__imp_CreateFileMappingW
0x383a89fbc  mov     [rbx+28h], rax
0x383a89fc0  test    rax, rax
0x383a89fc3  jz      short loc_383A8A029
0x383a89fc5  lea     edx, [rsi+2]; dwDesiredAccess
0x383a89fc8  xor     r9d, r9d; dwFileOffsetLow
0x383a89fcb  xor     r8d, r8d; dwFileOffsetHigh
0x383a89fce  mov     rcx, rax; hFileMappingObject
0x383a89fd1  mov     dword ptr [rbx+4Ch], 100000h
0x383a89fd8  mov     qword ptr [rsp+38h+dwMaximumSizeLow], 100000h; dwNumberOfBytesToMap
0x383a89fe1  call    cs:__imp_MapViewOfFile
0x383a89fe7  mov     [rbx+30h], rax
0x383a89feb  test    rax, rax
0x383a89fee  jz      short loc_383A8A01B
0x383a89ff0  mov     eax, [rbx+4Ch]
0x383a89ff3  mov     [rbx+38h], rsi
0x383a89ff7  mov     [rbx+40h], rsi
0x383a89ffb  mov     [rbx+48h], esi
0x383a89ffe  mov     rsi, [rsp+38h+arg_0]
0x383a8a003  mov     [rbx+10h], rax
0x383a8a007  mov     eax, edi
0x383a8a009  mov     dword ptr [rbx+20h], 1
0x383a8a010  mov     rbx, [rsp+38h+arg_8]
0x383a8a015  add     rsp, 30h
0x383a8a019  pop     rdi
0x383a8a01a  retn
0x383a8a01b  mov     rcx, [rbx+28h]; hObject
0x383a8a01f  call    cs:__imp_CloseHandle
0x383a8a025  mov     [rbx+28h], rsi
0x383a8a029  mov     rsi, [rsp+38h+arg_0]
0x383a8a02e  mov     eax, 1
0x383a8a033  mov     rbx, [rsp+38h+arg_8]
0x383a8a038  add     rsp, 30h
0x383a8a03c  pop     rdi
0x383a8a03d  retn
```
