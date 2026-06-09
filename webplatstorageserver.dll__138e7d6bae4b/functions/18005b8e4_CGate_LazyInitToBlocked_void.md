# CGate::LazyInitToBlocked(void)

- ea: `0x18005b8e4`
- end: `0x18005b968`
- name: `?LazyInitToBlocked@CGate@@AEAAJXZ`
- size: `132`
- prototype: `__int64 __fastcall(CGate *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800b3c78`

## callees

- `0x180035024`
- `0x18005b8e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005b909`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005b923`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005b909`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005b923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b939`

## pseudocode

```c
__int64 __fastcall CGate::LazyInitToBlocked(CGate *this)
{
  unsigned int v1; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax

  v1 = 0;
  if ( !*((_QWORD *)this + 5) )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 5) = EventW;
    if ( EventW )
      *((_QWORD *)this + 6) = CreateEventW(0, 1, 0, 0);
    if ( !*((_QWORD *)this + 5) || !*((_QWORD *)this + 6) )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      CGate::Close(this);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18005b8e4  mov     [rsp+arg_0], rbx
0x18005b8e9  mov     [rsp+arg_8], rsi
0x18005b8ee  push    rdi
0x18005b8ef  sub     rsp, 20h
0x18005b8f3  xor     ebx, ebx
0x18005b8f5  mov     rdi, rcx
0x18005b8f8  cmp     [rcx+28h], rbx
0x18005b8fc  jnz     short loc_18005B956
0x18005b8fe  xor     r9d, r9d; lpName
0x18005b901  lea     edx, [rbx+1]; bManualReset
0x18005b904  xor     r8d, r8d; bInitialState
0x18005b907  xor     ecx, ecx; lpEventAttributes
0x18005b909  call    cs:__imp_CreateEventW
0x18005b90f  mov     [rdi+28h], rax
0x18005b913  test    rax, rax
0x18005b916  jz      short loc_18005B92D
0x18005b918  xor     r9d, r9d; lpName
0x18005b91b  lea     edx, [rbx+1]; bManualReset
0x18005b91e  xor     r8d, r8d; bInitialState
0x18005b921  xor     ecx, ecx; lpEventAttributes
0x18005b923  call    cs:__imp_CreateEventW
0x18005b929  mov     [rdi+30h], rax
0x18005b92d  cmp     [rdi+28h], rbx
0x18005b931  jz      short loc_18005B939
0x18005b933  cmp     [rdi+30h], rbx
0x18005b937  jnz     short loc_18005B956
0x18005b939  call    cs:__imp_GetLastError
0x18005b93f  mov     ebx, eax
0x18005b941  test    eax, eax
0x18005b943  jle     short loc_18005B94E
0x18005b945  movzx   ebx, ax
0x18005b948  or      ebx, 80070000h
0x18005b94e  mov     rcx, rdi; this
0x18005b951  call    ?Close@CGate@@QEAAXXZ; CGate::Close(void)
0x18005b956  mov     rsi, [rsp+28h+arg_8]
0x18005b95b  mov     eax, ebx
0x18005b95d  mov     rbx, [rsp+28h+arg_0]
0x18005b962  add     rsp, 20h
0x18005b966  pop     rdi
0x18005b967  retn
```
