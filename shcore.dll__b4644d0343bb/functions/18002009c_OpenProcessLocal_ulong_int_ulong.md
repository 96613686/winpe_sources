# OpenProcessLocal(ulong,int,ulong)

- ea: `0x18002009c`
- end: `0x18002010b`
- name: `?OpenProcessLocal@@YAPEAXKHK@Z`
- size: `111`
- prototype: `void *(unsigned int, int, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001fcd0`
- `0x18001fe5c`
- `0x180020f00`

## callees

- `0x18002009c`
- `0x18005df58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020103`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020103`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800200ae`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800200e9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800200ae`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800200e9`

## pseudocode

```c
HANDLE __fastcall OpenProcessLocal(__int64 a1, __int64 a2, DWORD a3)
{
  HANDLE v4; // rbx
  int v6; // ecx
  int v7; // ecx

  v4 = OpenProcess(0x40u, 0, a3);
  if ( !v4 && GetLastError() == 5 )
  {
    if ( !EnablePrivilege(v6, 1) || (v4 = OpenProcess(0x40u, 0, a3), EnablePrivilege(v7, 0), !v4) )
      SetLastError(5u);
  }
  return v4;
}

```

## disassembly

```asm
0x18002009c  mov     [rsp+arg_0], rbx
0x1800200a1  push    rdi
0x1800200a2  sub     rsp, 20h
0x1800200a6  xor     edx, edx; bInheritHandle
0x1800200a8  mov     edi, r8d
0x1800200ab  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1800200ae  call    cs:__imp_OpenProcess
0x1800200b4  mov     rbx, rax
0x1800200b7  test    rax, rax
0x1800200ba  jz      short loc_1800200CA
0x1800200bc  mov     rax, rbx
0x1800200bf  mov     rbx, [rsp+28h+arg_0]
0x1800200c4  add     rsp, 20h
0x1800200c8  pop     rdi
0x1800200c9  retn
0x1800200ca  call    cs:__imp_GetLastError
0x1800200d0  cmp     eax, 5
0x1800200d3  jnz     short loc_1800200BC
0x1800200d5  lea     edx, [rax-4]; int
0x1800200d8  call    ?EnablePrivilege@@YAHJH@Z; EnablePrivilege(long,int)
0x1800200dd  test    eax, eax
0x1800200df  jz      short loc_1800200FE
0x1800200e1  xor     edx, edx; bInheritHandle
0x1800200e3  mov     r8d, edi; dwProcessId
0x1800200e6  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1800200e9  call    cs:__imp_OpenProcess
0x1800200ef  xor     edx, edx; int
0x1800200f1  mov     rbx, rax
0x1800200f4  call    ?EnablePrivilege@@YAHJH@Z; EnablePrivilege(long,int)
0x1800200f9  test    rbx, rbx
0x1800200fc  jnz     short loc_1800200BC
0x1800200fe  mov     ecx, 5; dwErrCode
0x180020103  call    cs:__imp_SetLastError
0x180020109  jmp     short loc_1800200BC
```
