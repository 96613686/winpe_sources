# CFileWriter::Position(__int64 *)

- ea: `0x383a897f0`
- end: `0x383a89874`
- name: `?Position@CFileWriter@@UEAAJPEA_J@Z`
- size: `132`
- prototype: `__int64 __fastcall(CFileWriter *__hidden this, __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x383a8a530`

## callees

- `0x383a897f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383a89842`
- `KERNEL32!GetLastError` at `0x383a8984c`
- `KERNEL32!GetLastError` at `0x383a89842`
- `KERNEL32!GetLastError` at `0x383a8984c`
- `KERNEL32!SetFilePointer` at `0x383a89833`
- `KERNEL32!SetFilePointer` at `0x383a89833`

## pseudocode

```c
signed int __fastcall CFileWriter::Position(CFileWriter *this, __int64 *a2)
{
  signed int result; // eax
  void *v4; // rcx
  __int64 DistanceToMoveHigh; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return -2147024809;
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 == (void *)-1LL )
    return -2147221301;
  HIDWORD(DistanceToMoveHigh) = 0;
  LODWORD(DistanceToMoveHigh) = SetFilePointer(v4, 0, (PLONG)&DistanceToMoveHigh + 1, 1u);
  if ( (_DWORD)DistanceToMoveHigh == -1 && GetLastError() )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    result = 0;
    *a2 = DistanceToMoveHigh;
  }
  return result;
}

```

## disassembly

```asm
0x383a897f0  push    rbx
0x383a897f2  sub     rsp, 20h
0x383a897f6  mov     rbx, rdx
0x383a897f9  test    rdx, rdx
0x383a897fc  jnz     short loc_383A89809
0x383a897fe  mov     eax, 80070057h
0x383a89803  add     rsp, 20h
0x383a89807  pop     rbx
0x383a89808  retn
0x383a89809  mov     rcx, [rcx+8]; hFile
0x383a8980d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383a89811  jnz     short loc_383A8981E
0x383a89813  mov     eax, 800400CBh
0x383a89818  add     rsp, 20h
0x383a8981c  pop     rbx
0x383a8981d  retn
0x383a8981e  lea     r8, [rsp+28h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x383a89823  mov     r9d, 1; dwMoveMethod
0x383a89829  xor     edx, edx; lDistanceToMove
0x383a8982b  mov     dword ptr [rsp+28h+DistanceToMoveHigh+4], 0
0x383a89833  call    cs:__imp_SetFilePointer
0x383a89839  mov     dword ptr [rsp+28h+DistanceToMoveHigh], eax
0x383a8983d  cmp     eax, 0FFFFFFFFh
0x383a89840  jnz     short loc_383A89864
0x383a89842  call    cs:__imp_GetLastError
0x383a89848  test    eax, eax
0x383a8984a  jz      short loc_383A89864
0x383a8984c  call    cs:__imp_GetLastError
0x383a89852  test    eax, eax
0x383a89854  jle     short loc_383A8986E
0x383a89856  movzx   eax, ax
0x383a89859  or      eax, 80070000h
0x383a8985e  add     rsp, 20h
0x383a89862  pop     rbx
0x383a89863  retn
0x383a89864  mov     rcx, [rsp+28h+DistanceToMoveHigh]
0x383a89869  xor     eax, eax
0x383a8986b  mov     [rbx], rcx
0x383a8986e  add     rsp, 20h
0x383a89872  pop     rbx
0x383a89873  retn
```
