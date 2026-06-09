# mmInitializeMultipleCriticalSections(_RTL_CRITICAL_SECTION * *,long)

- ea: `0x180004a24`
- end: `0x180004a82`
- name: `?mmInitializeMultipleCriticalSections@@YAHPEAPEAU_RTL_CRITICAL_SECTION@@J@Z`
- size: `94`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION **, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004940`

## callees

- `0x180004a24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004a42`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004a42`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004a72`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004a72`

## pseudocode

```c
__int64 __fastcall mmInitializeMultipleCriticalSections(struct _RTL_CRITICAL_SECTION **a1)
{
  int v1; // edi
  __int64 v2; // rbx
  int i; // ebx

  v1 = 0;
  v2 = 0;
  do
  {
    InitializeCriticalSection((LPCRITICAL_SECTION)(&acs)[v2]);
    ++v1;
    ++v2;
  }
  while ( v1 < 6 );
  if ( v1 == 6 )
    return 1;
  for ( i = 0; i < v1; ++i )
    DeleteCriticalSection((LPCRITICAL_SECTION)(&acs)[i]);
  return 0;
}

```

## disassembly

```asm
0x180004a24  mov     [rsp+arg_0], rbx
0x180004a29  mov     [rsp+arg_8], rsi
0x180004a2e  push    rdi
0x180004a2f  sub     rsp, 20h
0x180004a33  xor     edi, edi
0x180004a35  lea     rsi, ?acs@@3PAPEAU_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION * near * acs
0x180004a3c  xor     ebx, ebx
0x180004a3e  mov     rcx, [rsi+rbx*8]; lpCriticalSection
0x180004a42  call    cs:__imp_InitializeCriticalSection
0x180004a48  inc     edi
0x180004a4a  inc     rbx
0x180004a4d  cmp     edi, 6
0x180004a50  jl      short loc_180004A3E
0x180004a52  jnz     short loc_180004A69
0x180004a54  mov     eax, 1
0x180004a59  mov     rbx, [rsp+28h+arg_0]
0x180004a5e  mov     rsi, [rsp+28h+arg_8]
0x180004a63  add     rsp, 20h
0x180004a67  pop     rdi
0x180004a68  retn
0x180004a69  xor     ebx, ebx
0x180004a6b  movsxd  rcx, ebx
0x180004a6e  mov     rcx, [rsi+rcx*8]; lpCriticalSection
0x180004a72  call    cs:__imp_DeleteCriticalSection
0x180004a78  inc     ebx
0x180004a7a  cmp     ebx, edi
0x180004a7c  jl      short loc_180004A6B
0x180004a7e  xor     eax, eax
0x180004a80  jmp     short loc_180004A59
```
