# WTSVirtualChannelRead

- ea: `0x180009630`
- end: `0x18000971b`
- name: `WTSVirtualChannelRead`
- size: `235`
- prototype: `BOOL __stdcall(HANDLE hChannelHandle, ULONG TimeOut, PCHAR Buffer, ULONG BufferSize, PULONG pBytesRead)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180009630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009703`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800096cd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800096cd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000969d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000969d`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1800096bc`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1800096de`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1800096bc`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1800096de`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800096f6`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800096f6`

## pseudocode

```c
BOOL __stdcall WTSVirtualChannelRead(
        HANDLE hChannelHandle,
        ULONG TimeOut,
        PCHAR Buffer,
        ULONG BufferSize,
        PULONG pBytesRead)
{
  void *v7; // rcx
  void *v8; // rcx
  DWORD v10; // eax
  void *v11; // rcx
  DWORD v12; // ecx
  _OVERLAPPED Overlapped; // [rsp+30h] [rbp-28h] BYREF

  Overlapped.Internal = 0;
  Overlapped.InternalHigh = 0;
  if ( hChannelHandle && *(_DWORD *)hChannelHandle == 1145586518 )
  {
    v7 = (void *)*((_QWORD *)hChannelHandle + 3);
    Overlapped.hEvent = 0;
    Overlapped.Pointer = 0;
    if ( ReadFile(v7, Buffer, BufferSize, pBytesRead, &Overlapped) )
      return 1;
    if ( GetLastError() != 997 )
      return 0;
    v8 = (void *)*((_QWORD *)hChannelHandle + 3);
    if ( !TimeOut )
    {
      CancelIo(v8);
      *pBytesRead = 0;
      return 1;
    }
    v10 = WaitForSingleObject(v8, TimeOut);
    v11 = (void *)*((_QWORD *)hChannelHandle + 3);
    if ( v10 != 258 )
      return GetOverlappedResult(v11, &Overlapped, pBytesRead, 0);
    CancelIo(v11);
    v12 = 996;
  }
  else
  {
    v12 = 87;
  }
  SetLastError(v12);
  return 0;
}

```

## disassembly

```asm
0x180009630  mov     r11, rsp
0x180009633  mov     [r11+8], rbx
0x180009637  mov     [r11+10h], rsi
0x18000963b  push    rdi
0x18000963c  sub     rsp, 50h
0x180009640  mov     qword ptr [r11-28h], 0
0x180009648  mov     eax, r9d
0x18000964b  mov     qword ptr [r11-20h], 0
0x180009653  mov     r10, r8
0x180009656  mov     esi, edx
0x180009658  mov     rbx, rcx
0x18000965b  test    rcx, rcx
0x18000965e  jz      loc_1800096FE
0x180009664  cmp     dword ptr [rcx], 44484356h
0x18000966a  jnz     loc_1800096FE
0x180009670  mov     rdi, [rsp+58h+pBytesRead]
0x180009678  lea     rcx, [r11-28h]
0x18000967c  mov     [r11-38h], rcx
0x180009680  mov     r9, rdi; lpNumberOfBytesRead
0x180009683  mov     rcx, [rbx+18h]; hFile
0x180009687  mov     r8d, eax; nNumberOfBytesToRead
0x18000968a  mov     rdx, r10; lpBuffer
0x18000968d  mov     qword ptr [r11-10h], 0
0x180009695  mov     qword ptr [r11-18h], 0
0x18000969d  call    cs:__imp_ReadFile
0x1800096a3  test    eax, eax
0x1800096a5  jnz     short loc_1800096C4
0x1800096a7  call    cs:__imp_GetLastError
0x1800096ad  cmp     eax, 3E5h
0x1800096b2  jnz     short loc_180009709
0x1800096b4  mov     rcx, [rbx+18h]; hHandle
0x1800096b8  test    esi, esi
0x1800096ba  jnz     short loc_1800096CB
0x1800096bc  call    cs:__imp_CancelIo
0x1800096c2  mov     [rdi], esi
0x1800096c4  mov     eax, 1
0x1800096c9  jmp     short loc_18000970B
0x1800096cb  mov     edx, esi; dwMilliseconds
0x1800096cd  call    cs:__imp_WaitForSingleObject
0x1800096d3  mov     rcx, [rbx+18h]; hFile
0x1800096d7  cmp     eax, 102h
0x1800096dc  jnz     short loc_1800096EB
0x1800096de  call    cs:__imp_CancelIo
0x1800096e4  mov     ecx, 3E4h
0x1800096e9  jmp     short loc_180009703
0x1800096eb  xor     r9d, r9d; bWait
0x1800096ee  lea     rdx, [rsp+58h+Overlapped]; lpOverlapped
0x1800096f3  mov     r8, rdi; lpNumberOfBytesTransferred
0x1800096f6  call    cs:__imp_GetOverlappedResult
0x1800096fc  jmp     short loc_18000970B
0x1800096fe  mov     ecx, 57h ; 'W'; dwErrCode
0x180009703  call    cs:__imp_SetLastError
0x180009709  xor     eax, eax
0x18000970b  mov     rbx, [rsp+58h+arg_0]
0x180009710  mov     rsi, [rsp+58h+arg_8]
0x180009715  add     rsp, 50h
0x180009719  pop     rdi
0x18000971a  retn
```
