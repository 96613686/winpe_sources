# CFirewallManager::OnInitialize(void)

- ea: `0x180039880`
- end: `0x1800398ca`
- name: `?OnInitialize@CFirewallManager@@MEAAJXZ`
- size: `74`
- prototype: `__int64 __fastcall(CFirewallManager *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180039880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039899`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800398a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800398a8`

## pseudocode

```c
__int64 __fastcall CFirewallManager::OnInitialize(CFirewallManager *this)
{
  unsigned int v2; // edi
  HANDLE EventW; // rax
  signed int LastError; // eax

  v2 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 11) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v2;
}

```

## disassembly

```asm
0x180039880  mov     [rsp+arg_0], rbx
0x180039885  push    rdi
0x180039886  sub     rsp, 20h
0x18003988a  mov     rbx, rcx
0x18003988d  xor     r9d, r9d; lpName
0x180039890  xor     ecx, ecx; lpEventAttributes
0x180039892  xor     r8d, r8d; bInitialState
0x180039895  xor     edx, edx; bManualReset
0x180039897  xor     edi, edi
0x180039899  call    cs:__imp_CreateEventW
0x18003989f  mov     [rbx+58h], rax
0x1800398a3  test    rax, rax
0x1800398a6  jnz     short loc_1800398BD
0x1800398a8  call    cs:__imp_GetLastError
0x1800398ae  mov     edi, eax
0x1800398b0  test    eax, eax
0x1800398b2  jle     short loc_1800398BD
0x1800398b4  movzx   edi, ax
0x1800398b7  or      edi, 80070000h
0x1800398bd  mov     rbx, [rsp+28h+arg_0]
0x1800398c2  mov     eax, edi
0x1800398c4  add     rsp, 20h
0x1800398c8  pop     rdi
0x1800398c9  retn
```
