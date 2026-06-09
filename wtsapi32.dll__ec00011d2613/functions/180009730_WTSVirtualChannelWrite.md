# WTSVirtualChannelWrite

- ea: `0x180009730`
- end: `0x1800097cb`
- name: `WTSVirtualChannelWrite`
- size: `155`
- prototype: `BOOL __stdcall(HANDLE hChannelHandle, PCHAR Buffer, ULONG Length, PULONG pBytesWritten)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180009730`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800097b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800097b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009785`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000977b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000977b`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800097a4`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800097a4`

## pseudocode

```c
BOOL __stdcall WTSVirtualChannelWrite(HANDLE hChannelHandle, PCHAR Buffer, ULONG Length, PULONG pBytesWritten)
{
  void *v6; // rcx
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-28h] BYREF

  Overlapped.Internal = 0;
  Overlapped.InternalHigh = 0;
  if ( hChannelHandle && *(_DWORD *)hChannelHandle == 1145586518 )
  {
    v6 = (void *)*((_QWORD *)hChannelHandle + 3);
    Overlapped.hEvent = 0;
    Overlapped.Pointer = 0;
    if ( WriteFile(v6, Buffer, Length, pBytesWritten, &Overlapped) )
      return 1;
    if ( GetLastError() == 997 )
      return GetOverlappedResult(*((HANDLE *)hChannelHandle + 3), &Overlapped, pBytesWritten, 1);
  }
  else
  {
    SetLastError(0x57u);
  }
  return 0;
}

```

## disassembly

```asm
0x180009730  mov     r11, rsp
0x180009733  mov     [r11+8], rbx
0x180009737  push    rdi
0x180009738  sub     rsp, 50h
0x18000973c  mov     qword ptr [r11-28h], 0
0x180009744  mov     rdi, r9
0x180009747  mov     qword ptr [r11-20h], 0
0x18000974f  mov     rbx, rcx
0x180009752  test    rcx, rcx
0x180009755  jz      short loc_1800097B3
0x180009757  cmp     dword ptr [rcx], 44484356h
0x18000975d  jnz     short loc_1800097B3
0x18000975f  mov     rcx, [rcx+18h]; hFile
0x180009763  lea     rax, [r11-28h]
0x180009767  mov     [r11-38h], rax
0x18000976b  mov     qword ptr [r11-10h], 0
0x180009773  mov     qword ptr [r11-18h], 0
0x18000977b  call    cs:__imp_WriteFile
0x180009781  test    eax, eax
0x180009783  jnz     short loc_1800097AC
0x180009785  call    cs:__imp_GetLastError
0x18000978b  cmp     eax, 3E5h
0x180009790  jnz     short loc_1800097BE
0x180009792  mov     rcx, [rbx+18h]; hFile
0x180009796  lea     rdx, [rsp+58h+Overlapped]; lpOverlapped
0x18000979b  mov     r9d, 1; bWait
0x1800097a1  mov     r8, rdi; lpNumberOfBytesTransferred
0x1800097a4  call    cs:__imp_GetOverlappedResult
0x1800097aa  jmp     short loc_1800097C0
0x1800097ac  mov     eax, 1
0x1800097b1  jmp     short loc_1800097C0
0x1800097b3  mov     ecx, 57h ; 'W'; dwErrCode
0x1800097b8  call    cs:__imp_SetLastError
0x1800097be  xor     eax, eax
0x1800097c0  mov     rbx, [rsp+58h+arg_0]
0x1800097c5  add     rsp, 50h
0x1800097c9  pop     rdi
0x1800097ca  retn
```
