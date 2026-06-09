# CDVRSource::ReadBytesLocked(void *,ulong,ulong *)

- ea: `0x180006ea8`
- end: `0x180006f18`
- name: `?ReadBytesLocked@CDVRSource@@IEAAJPEAXKPEAK@Z`
- size: `112`
- prototype: `__int64 __fastcall(CDVRSource *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800067e0`

## callees

- `0x180006ea8`
- `0x18002b010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006f00`
- `KERNEL32!GetLastError` at `0x180006f00`
- `KERNEL32!ReadFile` at `0x180006ef2`
- `KERNEL32!ReadFile` at `0x180006ef2`

## pseudocode

```c
signed int __fastcall CDVRSource::ReadBytesLocked(CDVRSource *this, void *a2, DWORD a3, unsigned int *a4)
{
  __int64 v4; // r10
  signed int result; // eax
  unsigned int v7; // ecx
  DWORD v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = a3;
  v4 = *((_QWORD *)this + 18);
  if ( v4 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD, DWORD *, void *))(*(_QWORD *)v4 + 40LL))(
               *((_QWORD *)this + 18),
               &v8,
               a2);
    v7 = 0;
    if ( result >= 0 )
      v7 = v8;
    *a4 = v7;
  }
  else if ( ReadFile(*((HANDLE *)this + 10), a2, a3, a4, 0) )
  {
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180006ea8  mov     [rsp+arg_10], r8d
0x180006ead  push    rbx
0x180006eae  sub     rsp, 30h
0x180006eb2  mov     r10, [rcx+90h]
0x180006eb9  mov     rbx, r9
0x180006ebc  test    r10, r10
0x180006ebf  jz      short loc_180006EE5
0x180006ec1  mov     rax, [r10]
0x180006ec4  mov     r8, rdx
0x180006ec7  lea     rdx, [rsp+38h+arg_10]
0x180006ecc  mov     rcx, r10
0x180006ecf  mov     rax, [rax+28h]
0x180006ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ed8  xor     ecx, ecx
0x180006eda  test    eax, eax
0x180006edc  cmovns  ecx, [rsp+38h+arg_10]
0x180006ee1  mov     [rbx], ecx
0x180006ee3  jmp     short loc_180006F12
0x180006ee5  mov     rcx, [rcx+50h]; hFile
0x180006ee9  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180006ef2  call    cs:__imp_ReadFile
0x180006ef8  test    eax, eax
0x180006efa  jz      short loc_180006F00
0x180006efc  xor     eax, eax
0x180006efe  jmp     short loc_180006F12
0x180006f00  call    cs:__imp_GetLastError
0x180006f06  test    eax, eax
0x180006f08  jle     short loc_180006F12
0x180006f0a  movzx   eax, ax
0x180006f0d  or      eax, 80070000h
0x180006f12  add     rsp, 30h
0x180006f16  pop     rbx
0x180006f17  retn
```
