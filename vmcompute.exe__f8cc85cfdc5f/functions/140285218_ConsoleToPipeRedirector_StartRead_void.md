# ConsoleToPipeRedirector::StartRead(void)

- ea: `0x140285218`
- end: `0x140285295`
- name: `?StartRead@ConsoleToPipeRedirector@@AEAAXXZ`
- size: `125`
- prototype: `void __fastcall(ConsoleToPipeRedirector *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140080ed8`
- `0x1402849b0`

## callees

- `0x140285218`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14028526b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14028526b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140285232`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140285232`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140285282`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140285282`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14028525b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14028525b`

## pseudocode

```c
void __fastcall ConsoleToPipeRedirector::StartRead(ConsoleToPipeRedirector *this)
{
  if ( (unsigned __int64)(*((_QWORD *)this + 6) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    StartThreadpoolIo(*((PTP_IO *)this + 8));
    if ( !ReadFile(*((HANDLE *)this + 6), (char *)this + 88, 0x100u, 0, (LPOVERLAPPED)((char *)this + 344))
      && GetLastError() != 997 )
    {
      CancelThreadpoolIo(*((PTP_IO *)this + 8));
    }
  }
}

```

## disassembly

```asm
0x140285218  push    rbx
0x14028521a  sub     rsp, 30h
0x14028521e  mov     rax, [rcx+30h]
0x140285222  mov     rbx, rcx
0x140285225  dec     rax
0x140285228  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14028522c  ja      short loc_14028528E
0x14028522e  mov     rcx, [rcx+40h]; pio
0x140285232  call    cs:__imp_StartThreadpoolIo
0x140285239  nop     dword ptr [rax+rax+00h]
0x14028523e  mov     rcx, [rbx+30h]; hFile
0x140285242  lea     rax, [rbx+158h]
0x140285249  lea     rdx, [rbx+58h]; lpBuffer
0x14028524d  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x140285252  xor     r9d, r9d; lpNumberOfBytesRead
0x140285255  mov     r8d, 100h; nNumberOfBytesToRead
0x14028525b  call    cs:__imp_ReadFile
0x140285262  nop     dword ptr [rax+rax+00h]
0x140285267  test    eax, eax
0x140285269  jnz     short loc_14028528E
0x14028526b  call    cs:__imp_GetLastError
0x140285272  nop     dword ptr [rax+rax+00h]
0x140285277  cmp     eax, 3E5h
0x14028527c  jz      short loc_14028528E
0x14028527e  mov     rcx, [rbx+40h]; pio
0x140285282  call    cs:__imp_CancelThreadpoolIo
0x140285289  nop     dword ptr [rax+rax+00h]
0x14028528e  add     rsp, 30h
0x140285292  pop     rbx
0x140285293  retn
```
