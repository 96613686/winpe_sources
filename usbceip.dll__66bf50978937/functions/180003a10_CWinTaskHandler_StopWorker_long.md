# CWinTaskHandler::StopWorker(long *)

- ea: `0x180003a10`
- end: `0x180003a79`
- name: `?StopWorker@CWinTaskHandler@@MEAAJPEAJ@Z`
- size: `105`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180003a10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a52`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003a3c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003a3c`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::StopWorker(CWinTaskHandler *this, int *a2)
{
  unsigned int v3; // ebx
  DWORD v4; // eax
  signed int LastError; // eax
  __int64 result; // rax

  if ( *((_QWORD *)this + 5) )
  {
    _InterlockedExchange((volatile __int32 *)this + 9, 1);
    v3 = 0;
    v4 = WaitForSingleObject(*((HANDLE *)this + 5), 0xFFFFFFFF);
    if ( v4 )
    {
      if ( v4 == -1 )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v3 = -2147467259;
      }
    }
  }
  else
  {
    v3 = -2147024809;
  }
  result = v3;
  _InterlockedExchange((volatile __int32 *)this + 9, 0);
  return result;
}

```

## disassembly

```asm
0x180003a10  mov     [rsp+arg_0], rbx
0x180003a15  push    rdi
0x180003a16  sub     rsp, 20h
0x180003a1a  cmp     qword ptr [rcx+28h], 0
0x180003a1f  mov     rdi, rcx
0x180003a22  jnz     short loc_180003A2B
0x180003a24  mov     ebx, 80070057h
0x180003a29  jmp     short loc_180003A67
0x180003a2b  mov     eax, 1
0x180003a30  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003a33  xchg    eax, [rcx+24h]
0x180003a36  mov     rcx, [rcx+28h]; hHandle
0x180003a3a  xor     ebx, ebx
0x180003a3c  call    cs:__imp_WaitForSingleObject
0x180003a42  test    eax, eax
0x180003a44  jz      short loc_180003A67
0x180003a46  cmp     eax, 0FFFFFFFFh
0x180003a49  jz      short loc_180003A52
0x180003a4b  mov     ebx, 80004005h
0x180003a50  jmp     short loc_180003A67
0x180003a52  call    cs:__imp_GetLastError
0x180003a58  mov     ebx, eax
0x180003a5a  test    eax, eax
0x180003a5c  jle     short loc_180003A67
0x180003a5e  movzx   ebx, ax
0x180003a61  or      ebx, 80070000h
0x180003a67  xor     ecx, ecx
0x180003a69  mov     eax, ebx
0x180003a6b  xchg    ecx, [rdi+24h]
0x180003a6e  mov     rbx, [rsp+28h+arg_0]
0x180003a73  add     rsp, 20h
0x180003a77  pop     rdi
0x180003a78  retn
```
