# YGetSpoolFileInfo(void *,ulong,ulong,uchar *,ulong,ulong *,Call_Route)

- ea: `0x14003d024`
- end: `0x14003d14e`
- name: `?YGetSpoolFileInfo@@YAKPEAXKKPEAEKPEAKW4Call_Route@@@Z`
- size: `298`
- prototype: `unsigned int __high(void *, unsigned int, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, enum Call_Route)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140037320`
- `0x1400373f0`

## callees

- `0x1400028e0`
- `0x140002940`
- `0x14003d024`
- `0x1400665b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d06b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d0b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d0f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d10c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d06b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d0b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d0f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d10c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d122`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d122`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003d057`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003d0a1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003d057`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003d0a1`

## pseudocode

```c
__int64 __fastcall YGetSpoolFileInfo(__int64 a1, DWORD a2, int a3, __int64 a4, unsigned int a5, _DWORD *a6)
{
  HANDLE v10; // rdi
  DWORD LastError; // eax
  DWORD v12; // ebx
  int SpoolFileInfo; // esi

  *a6 = 0;
  v10 = OpenProcess(0x40u, 0, a2);
  if ( !v10 )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError != 5 )
    {
      if ( LastError )
        return v12;
    }
  }
  SpoolFileInfo = 0;
  if ( !(unsigned int)YImpersonateClient(1) )
  {
    v12 = GetLastError();
    goto LABEL_14;
  }
  if ( v10 || (v10 = OpenProcess(0x40u, 0, a2)) != 0 )
  {
    v12 = 0;
    goto LABEL_10;
  }
  v12 = GetLastError();
  if ( !v12 )
  {
LABEL_10:
    SpoolFileInfo = SplGetSpoolFileInfo(a1, v10, a3, a4, a5, a6);
    if ( !SpoolFileInfo )
      v12 = GetLastError();
  }
  YRevertToSelf(1);
LABEL_14:
  if ( v10 )
    CloseHandle(v10);
  if ( !SpoolFileInfo && !v12 )
    return 6;
  return v12;
}

```

## disassembly

```asm
0x14003d024  push    rbx
0x14003d026  push    rbp
0x14003d027  push    rsi
0x14003d028  push    rdi
0x14003d029  push    r12
0x14003d02b  push    r13
0x14003d02d  push    r14
0x14003d02f  push    r15
0x14003d031  sub     rsp, 38h
0x14003d035  mov     r14, [rsp+78h+arg_28]
0x14003d03d  mov     r12d, r8d
0x14003d040  mov     r8d, edx; dwProcessId
0x14003d043  mov     ebp, edx
0x14003d045  xor     edx, edx; bInheritHandle
0x14003d047  mov     r13, rcx
0x14003d04a  mov     r15, r9
0x14003d04d  mov     dword ptr [r14], 0
0x14003d054  lea     ecx, [rdx+40h]; dwDesiredAccess
0x14003d057  call    cs:__imp_OpenProcess
0x14003d05e  nop     dword ptr [rax+rax+00h]
0x14003d063  mov     rdi, rax
0x14003d066  test    rax, rax
0x14003d069  jnz     short loc_14003D086
0x14003d06b  call    cs:__imp_GetLastError
0x14003d072  nop     dword ptr [rax+rax+00h]
0x14003d077  mov     ebx, eax
0x14003d079  cmp     eax, 5
0x14003d07c  jz      short loc_14003D086
0x14003d07e  test    eax, eax
0x14003d080  jnz     loc_14003D13A
0x14003d086  xor     esi, esi
0x14003d088  lea     ecx, [rsi+1]
0x14003d08b  call    ?YImpersonateClient@@YAHW4Call_Route@@@Z; YImpersonateClient(Call_Route)
0x14003d090  test    eax, eax
0x14003d092  jz      short loc_14003D10C
0x14003d094  test    rdi, rdi
0x14003d097  jnz     short loc_14003D0C9
0x14003d099  mov     r8d, ebp; dwProcessId
0x14003d09c  lea     ecx, [rsi+40h]; dwDesiredAccess
0x14003d09f  xor     edx, edx; bInheritHandle
0x14003d0a1  call    cs:__imp_OpenProcess
0x14003d0a8  nop     dword ptr [rax+rax+00h]
0x14003d0ad  mov     rdi, rax
0x14003d0b0  test    rax, rax
0x14003d0b3  jnz     short loc_14003D0C9
0x14003d0b5  call    cs:__imp_GetLastError
0x14003d0bc  nop     dword ptr [rax+rax+00h]
0x14003d0c1  mov     ebx, eax
0x14003d0c3  test    eax, eax
0x14003d0c5  jnz     short loc_14003D100
0x14003d0c7  jmp     short loc_14003D0CB
0x14003d0c9  xor     ebx, ebx
0x14003d0cb  mov     eax, [rsp+78h+arg_20]
0x14003d0d2  mov     r9, r15
0x14003d0d5  mov     [rsp+78h+var_50], r14
0x14003d0da  mov     r8d, r12d
0x14003d0dd  mov     rdx, rdi
0x14003d0e0  mov     [rsp+78h+var_58], eax
0x14003d0e4  mov     rcx, r13
0x14003d0e7  call    SplGetSpoolFileInfo
0x14003d0ec  mov     esi, eax
0x14003d0ee  test    eax, eax
0x14003d0f0  jnz     short loc_14003D100
0x14003d0f2  call    cs:__imp_GetLastError
0x14003d0f9  nop     dword ptr [rax+rax+00h]
0x14003d0fe  mov     ebx, eax
0x14003d100  mov     ecx, 1
0x14003d105  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x14003d10a  jmp     short loc_14003D11A
0x14003d10c  call    cs:__imp_GetLastError
0x14003d113  nop     dword ptr [rax+rax+00h]
0x14003d118  mov     ebx, eax
0x14003d11a  test    rdi, rdi
0x14003d11d  jz      short loc_14003D12E
0x14003d11f  mov     rcx, rdi; hObject
0x14003d122  call    cs:__imp_CloseHandle
0x14003d129  nop     dword ptr [rax+rax+00h]
0x14003d12e  test    esi, esi
0x14003d130  jnz     short loc_14003D13A
0x14003d132  test    ebx, ebx
0x14003d134  lea     eax, [rsi+6]
0x14003d137  cmovz   ebx, eax
0x14003d13a  mov     eax, ebx
0x14003d13c  add     rsp, 38h
0x14003d140  pop     r15
0x14003d142  pop     r14
0x14003d144  pop     r13
0x14003d146  pop     r12
0x14003d148  pop     rdi
0x14003d149  pop     rsi
0x14003d14a  pop     rbp
0x14003d14b  pop     rbx
0x14003d14c  retn
```
