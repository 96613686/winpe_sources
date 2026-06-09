# CSchedule::Delete(ushort const *)

- ea: `0x180028260`
- end: `0x1800282c9`
- name: `?Delete@CSchedule@@UEAAJPEBG@Z`
- size: `105`
- prototype: `__int64 __fastcall(CSchedule *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1800074c8`
- `0x180026ce4`
- `0x180028260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002829a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002829a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180028290`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180028290`

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
0x180028260  push    rbx
0x180028262  sub     rsp, 20h
0x180028266  mov     [rsp+28h+lpFileName], 0
0x18002826f  test    rdx, rdx
0x180028272  jnz     short loc_18002827B
0x180028274  mov     ebx, 80070057h
0x180028279  jmp     short loc_1800282C1
0x18002827b  lea     r8, [rsp+28h+lpFileName]; unsigned __int16 **
0x180028280  call    ?CheckJobName@CSchedule@@AEAAJPEBGPEAPEAG@Z; CSchedule::CheckJobName(ushort const *,ushort * *)
0x180028285  mov     ebx, eax
0x180028287  test    eax, eax
0x180028289  js      short loc_1800282AF
0x18002828b  mov     rcx, [rsp+28h+lpFileName]; lpFileName
0x180028290  call    cs:__imp_DeleteFileW
0x180028296  test    eax, eax
0x180028298  jnz     short loc_1800282AF
0x18002829a  call    cs:__imp_GetLastError
0x1800282a0  mov     ebx, eax
0x1800282a2  test    eax, eax
0x1800282a4  jle     short loc_1800282AF
0x1800282a6  movzx   ebx, ax
0x1800282a9  or      ebx, 80070000h
0x1800282af  cmp     [rsp+28h+lpFileName], 0
0x1800282b5  jz      short loc_1800282C1
0x1800282b7  mov     rcx, [rsp+28h+lpFileName]; Block
0x1800282bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800282c1  mov     eax, ebx
0x1800282c3  add     rsp, 20h
0x1800282c7  pop     rbx
0x1800282c8  retn
```
