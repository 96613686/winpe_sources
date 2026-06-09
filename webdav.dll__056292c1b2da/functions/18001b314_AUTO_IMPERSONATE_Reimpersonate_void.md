# AUTO_IMPERSONATE::Reimpersonate(void)

- ea: `0x18001b314`
- end: `0x18001b362`
- name: `?Reimpersonate@AUTO_IMPERSONATE@@QEAAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(AUTO_IMPERSONATE *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800025e4`
- `0x180003c4c`
- `0x18001b2cc`

## callees

- `0x18001b314`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b340`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001b32e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001b32e`

## pseudocode

```c
__int64 __fastcall AUTO_IMPERSONATE::Reimpersonate(AUTO_IMPERSONATE *this)
{
  void *v1; // rdx
  unsigned int v2; // ebx
  signed int LastError; // eax

  v1 = (void *)*((_QWORD *)this + 1);
  v2 = 0;
  if ( v1 )
  {
    if ( SetThreadToken(0, v1) )
    {
      *(_DWORD *)this = 1;
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001b314  mov     [rsp+arg_0], rbx
0x18001b319  push    rdi
0x18001b31a  sub     rsp, 20h
0x18001b31e  mov     rdx, [rcx+8]; Token
0x18001b322  xor     ebx, ebx
0x18001b324  mov     rdi, rcx
0x18001b327  test    rdx, rdx
0x18001b32a  jz      short loc_18001B355
0x18001b32c  xor     ecx, ecx; Thread
0x18001b32e  call    cs:__imp_SetThreadToken
0x18001b334  test    eax, eax
0x18001b336  jz      short loc_18001B340
0x18001b338  mov     dword ptr [rdi], 1
0x18001b33e  jmp     short loc_18001B355
0x18001b340  call    cs:__imp_GetLastError
0x18001b346  mov     ebx, eax
0x18001b348  test    eax, eax
0x18001b34a  jle     short loc_18001B355
0x18001b34c  movzx   ebx, ax
0x18001b34f  or      ebx, 80070000h
0x18001b355  mov     eax, ebx
0x18001b357  mov     rbx, [rsp+28h+arg_0]
0x18001b35c  add     rsp, 20h
0x18001b360  pop     rdi
0x18001b361  retn
```
