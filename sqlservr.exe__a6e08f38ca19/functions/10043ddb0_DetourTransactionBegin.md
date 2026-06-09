# DetourTransactionBegin

- ea: `0x10043ddb0`
- end: `0x10043de61`
- name: `DetourTransactionBegin`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10043cc10`
- `0x10043d2c0`

## callees

- `0x10043ddb0`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x10043de23`
- `KERNEL32!VirtualProtect` at `0x10043de23`
- `KERNEL32!GetLastError` at `0x10043de38`
- `KERNEL32!GetLastError` at `0x10043de38`
- `KERNEL32!GetCurrentThreadId` at `0x10043ddc1`
- `KERNEL32!GetCurrentThreadId` at `0x10043ddc1`

## pseudocode

```c
__int64 DetourTransactionBegin()
{
  _QWORD *v0; // rbx
  DWORD LastError; // edi
  __int64 result; // rax
  DWORD flOldProtect; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1004D3F60 || _InterlockedCompareExchange(&dword_1004D3F60, GetCurrentThreadId(), 0) )
    return 4317;
  v0 = lpBaseAddress;
  LastError = 0;
  lpMem = 0;
  qword_1004D3F80 = 0;
  qword_1004D3F70 = 0;
  if ( lpBaseAddress )
  {
    while ( VirtualProtect(v0, 0x10000u, 0x40u, &flOldProtect) )
    {
      v0 = (_QWORD *)v0[1];
      if ( !v0 )
        goto LABEL_8;
    }
    LastError = GetLastError();
  }
LABEL_8:
  result = LastError;
  dword_1004D3F5C = LastError;
  return result;
}

```

## disassembly

```asm
0x10043ddb0  sub     rsp, 28h
0x10043ddb4  cmp     cs:dword_1004D3F60, 0
0x10043ddbb  jnz     loc_10043DE57
0x10043ddc1  call    cs:__imp_GetCurrentThreadId
0x10043ddc7  mov     ecx, eax
0x10043ddc9  xor     eax, eax
0x10043ddcb  lock cmpxchg cs:dword_1004D3F60, ecx
0x10043ddd3  jnz     loc_10043DE57
0x10043ddd9  mov     [rsp+28h+arg_8], rbx
0x10043ddde  mov     rbx, cs:lpBaseAddress
0x10043dde5  mov     [rsp+28h+var_8], rdi
0x10043ddea  xor     edi, edi
0x10043ddec  mov     cs:lpMem, rdi
0x10043ddf3  mov     cs:qword_1004D3F80, rdi
0x10043ddfa  mov     cs:qword_1004D3F70, rdi
0x10043de01  test    rbx, rbx
0x10043de04  jz      short loc_10043DE40
0x10043de06  nop     word ptr [rax+rax]
0x10043de0b  nop     dword ptr [rax+rax+00h]
0x10043de10  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x10043de15  mov     edx, 10000h; dwSize
0x10043de1a  mov     r8d, 40h ; '@'; flNewProtect
0x10043de20  mov     rcx, rbx; lpAddress
0x10043de23  call    cs:__imp_VirtualProtect
0x10043de29  test    eax, eax
0x10043de2b  jz      short loc_10043DE38
0x10043de2d  mov     rbx, [rbx+8]
0x10043de31  test    rbx, rbx
0x10043de34  jnz     short loc_10043DE10
0x10043de36  jmp     short loc_10043DE40
0x10043de38  call    cs:__imp_GetLastError
0x10043de3e  mov     edi, eax
0x10043de40  mov     rbx, [rsp+28h+arg_8]
0x10043de45  mov     eax, edi
0x10043de47  mov     cs:dword_1004D3F5C, edi
0x10043de4d  mov     rdi, [rsp+28h+var_8]
0x10043de52  add     rsp, 28h
0x10043de56  retn
0x10043de57  mov     eax, 10DDh
0x10043de5c  add     rsp, 28h
0x10043de60  retn
```
