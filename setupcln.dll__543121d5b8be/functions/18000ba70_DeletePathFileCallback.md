# DeletePathFileCallback

- ea: `0x18000ba70`
- end: `0x18000bb0f`
- name: `DeletePathFileCallback`
- size: `159`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18000aa40`
- `0x18000ba70`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bac7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000baf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000baf5`

## pseudocode

```c
__int64 __fastcall DeletePathFileCallback(__int64 a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, _QWORD); // rax
  __int64 *v5; // rdi
  unsigned int v6; // esi

  if ( a2 )
  {
    v4 = *(__int64 (__fastcall **)(__int64, _QWORD))(a2 + 16);
    v5 = (__int64 *)(a1 + 40);
    v6 = 1;
    if ( !v4 )
      goto LABEL_17;
    v6 = v4(*v5, *(_QWORD *)(a2 + 24));
    if ( !v6 && !GetLastError() )
      SetLastError(0x4C7u);
    if ( !*(_DWORD *)a2 )
      *(_DWORD *)a2 = GetLastError();
    if ( v6 )
    {
LABEL_17:
      if ( !DeleteFileEx2(*v5, *(_DWORD *)(a2 + 12)) )
        ++*(_DWORD *)(a2 + 4);
      if ( !*(_DWORD *)a2 )
        *(_DWORD *)a2 = GetLastError();
    }
    return v6;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18000ba70  mov     [rsp+arg_0], rbx
0x18000ba75  mov     [rsp+arg_8], rsi
0x18000ba7a  push    rdi
0x18000ba7b  sub     rsp, 20h
0x18000ba7f  mov     rbx, rdx
0x18000ba82  test    rdx, rdx
0x18000ba85  jnz     short loc_18000BA94
0x18000ba87  lea     ecx, [rdx+57h]; dwErrCode
0x18000ba8a  call    cs:__imp_SetLastError
0x18000ba90  xor     eax, eax
0x18000ba92  jmp     short loc_18000BAFF
0x18000ba94  mov     rax, [rdx+10h]
0x18000ba98  lea     rdi, [rcx+28h]
0x18000ba9c  mov     esi, 1
0x18000baa1  test    rax, rax
0x18000baa4  jz      short loc_18000BADE
0x18000baa6  mov     rdx, [rdx+18h]
0x18000baaa  mov     rcx, [rdi]
0x18000baad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bab2  mov     esi, eax
0x18000bab4  test    eax, eax
0x18000bab6  jnz     short loc_18000BACD
0x18000bab8  call    cs:__imp_GetLastError
0x18000babe  test    eax, eax
0x18000bac0  jnz     short loc_18000BACD
0x18000bac2  mov     ecx, 4C7h; dwErrCode
0x18000bac7  call    cs:__imp_SetLastError
0x18000bacd  cmp     dword ptr [rbx], 0
0x18000bad0  jnz     short loc_18000BADA
0x18000bad2  call    cs:__imp_GetLastError
0x18000bad8  mov     [rbx], eax
0x18000bada  test    esi, esi
0x18000badc  jz      short loc_18000BAFD
0x18000bade  mov     edx, [rbx+0Ch]
0x18000bae1  mov     rcx, [rdi]
0x18000bae4  call    DeleteFileEx2
0x18000bae9  test    eax, eax
0x18000baeb  jnz     short loc_18000BAF0
0x18000baed  inc     dword ptr [rbx+4]
0x18000baf0  cmp     dword ptr [rbx], 0
0x18000baf3  jnz     short loc_18000BAFD
0x18000baf5  call    cs:__imp_GetLastError
0x18000bafb  mov     [rbx], eax
0x18000bafd  mov     eax, esi
0x18000baff  mov     rbx, [rsp+28h+arg_0]
0x18000bb04  mov     rsi, [rsp+28h+arg_8]
0x18000bb09  add     rsp, 20h
0x18000bb0d  pop     rdi
0x18000bb0e  retn
```
