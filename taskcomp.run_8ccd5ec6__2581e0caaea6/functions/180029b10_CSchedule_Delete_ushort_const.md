# CSchedule::Delete(ushort const *)

- ea: `0x180029b10`
- end: `0x180029b86`
- name: `?Delete@CSchedule@@UEAAJPEBG@Z`
- size: `118`
- prototype: `__int64 __fastcall(CSchedule *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180007988`
- `0x1800284c4`
- `0x180029b10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b50`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180029b40`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180029b40`

## pseudocode

```c
__int64 __fastcall CSchedule::Delete(CSchedule *this, const unsigned __int16 *a2)
{
  signed int v2; // ebx
  signed int LastError; // eax
  LPCWSTR lpFileName; // [rsp+38h] [rbp+10h] BYREF

  lpFileName = 0;
  if ( a2 )
  {
    v2 = CSchedule::CheckJobName(this, a2, (unsigned __int16 **)&lpFileName);
    if ( v2 >= 0 && !DeleteFileW(lpFileName) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( lpFileName )
      operator delete((void *)lpFileName);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180029b10  push    rbx
0x180029b12  sub     rsp, 20h
0x180029b16  mov     [rsp+28h+lpFileName], 0
0x180029b1f  test    rdx, rdx
0x180029b22  jnz     short loc_180029B2B
0x180029b24  mov     ebx, 80070057h
0x180029b29  jmp     short loc_180029B7D
0x180029b2b  lea     r8, [rsp+28h+lpFileName]; unsigned __int16 **
0x180029b30  call    ?CheckJobName@CSchedule@@AEAAJPEBGPEAPEAG@Z; CSchedule::CheckJobName(ushort const *,ushort * *)
0x180029b35  mov     ebx, eax
0x180029b37  test    eax, eax
0x180029b39  js      short loc_180029B6B
0x180029b3b  mov     rcx, [rsp+28h+lpFileName]; lpFileName
0x180029b40  call    cs:__imp_DeleteFileW
0x180029b47  nop     dword ptr [rax+rax+00h]
0x180029b4c  test    eax, eax
0x180029b4e  jnz     short loc_180029B6B
0x180029b50  call    cs:__imp_GetLastError
0x180029b57  nop     dword ptr [rax+rax+00h]
0x180029b5c  mov     ebx, eax
0x180029b5e  test    eax, eax
0x180029b60  jle     short loc_180029B6B
0x180029b62  movzx   ebx, ax
0x180029b65  or      ebx, 80070000h
0x180029b6b  cmp     [rsp+28h+lpFileName], 0
0x180029b71  jz      short loc_180029B7D
0x180029b73  mov     rcx, [rsp+28h+lpFileName]; Block
0x180029b78  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029b7d  mov     eax, ebx
0x180029b7f  add     rsp, 20h
0x180029b83  pop     rbx
0x180029b84  retn
```
