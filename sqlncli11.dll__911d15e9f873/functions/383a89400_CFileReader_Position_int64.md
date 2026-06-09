# CFileReader::Position(__int64 *)

- ea: `0x383a89400`
- end: `0x383a89484`
- name: `?Position@CFileReader@@UEAAJPEA_J@Z`
- size: `132`
- prototype: `__int64 __fastcall(CFileReader *__hidden this, __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x383a89e20`

## callees

- `0x383a89400`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383a89452`
- `KERNEL32!GetLastError` at `0x383a8945c`
- `KERNEL32!GetLastError` at `0x383a89452`
- `KERNEL32!GetLastError` at `0x383a8945c`
- `KERNEL32!SetFilePointer` at `0x383a89443`
- `KERNEL32!SetFilePointer` at `0x383a89443`

## pseudocode

```c
signed int __fastcall CFileReader::Position(CFileReader *this, __int64 *a2)
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
0x383a89400  push    rbx
0x383a89402  sub     rsp, 20h
0x383a89406  mov     rbx, rdx
0x383a89409  test    rdx, rdx
0x383a8940c  jnz     short loc_383A89419
0x383a8940e  mov     eax, 80070057h
0x383a89413  add     rsp, 20h
0x383a89417  pop     rbx
0x383a89418  retn
0x383a89419  mov     rcx, [rcx+8]; hFile
0x383a8941d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383a89421  jnz     short loc_383A8942E
0x383a89423  mov     eax, 800400CBh
0x383a89428  add     rsp, 20h
0x383a8942c  pop     rbx
0x383a8942d  retn
0x383a8942e  lea     r8, [rsp+28h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x383a89433  mov     r9d, 1; dwMoveMethod
0x383a89439  xor     edx, edx; lDistanceToMove
0x383a8943b  mov     dword ptr [rsp+28h+DistanceToMoveHigh+4], 0
0x383a89443  call    cs:__imp_SetFilePointer
0x383a89449  mov     dword ptr [rsp+28h+DistanceToMoveHigh], eax
0x383a8944d  cmp     eax, 0FFFFFFFFh
0x383a89450  jnz     short loc_383A89474
0x383a89452  call    cs:__imp_GetLastError
0x383a89458  test    eax, eax
0x383a8945a  jz      short loc_383A89474
0x383a8945c  call    cs:__imp_GetLastError
0x383a89462  test    eax, eax
0x383a89464  jle     short loc_383A8947E
0x383a89466  movzx   eax, ax
0x383a89469  or      eax, 80070000h
0x383a8946e  add     rsp, 20h
0x383a89472  pop     rbx
0x383a89473  retn
0x383a89474  mov     rcx, [rsp+28h+DistanceToMoveHigh]
0x383a89479  xor     eax, eax
0x383a8947b  mov     [rbx], rcx
0x383a8947e  add     rsp, 20h
0x383a89482  pop     rbx
0x383a89483  retn
```
