# YGetSpoolFileInfo(void *,ulong,ulong,uchar *,ulong,ulong *,Call_Route)

- ea: `0x140039b9c`
- end: `0x140039c9b`
- name: `?YGetSpoolFileInfo@@YAKPEAXKKPEAEKPEAKW4Call_Route@@@Z`
- size: `255`
- prototype: `unsigned int __high(void *, unsigned int, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, enum Call_Route)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140034720`
- `0x1400347e0`

## callees

- `0x140002a70`
- `0x140002ac0`
- `0x140039b9c`
- `0x1400606a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039bdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039c52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039c66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039bdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039c52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039c66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140039c76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140039c76`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140039bcf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140039c0d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140039bcf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140039c0d`

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
0x140039b9c  push    rbx
0x140039b9e  push    rbp
0x140039b9f  push    rsi
0x140039ba0  push    rdi
0x140039ba1  push    r12
0x140039ba3  push    r13
0x140039ba5  push    r14
0x140039ba7  push    r15
0x140039ba9  sub     rsp, 38h
0x140039bad  mov     r14, [rsp+78h+arg_28]
0x140039bb5  mov     r12d, r8d
0x140039bb8  mov     r8d, edx; dwProcessId
0x140039bbb  mov     ebp, edx
0x140039bbd  xor     edx, edx; bInheritHandle
0x140039bbf  mov     r13, rcx
0x140039bc2  mov     r15, r9
0x140039bc5  mov     dword ptr [r14], 0
0x140039bcc  lea     ecx, [rdx+40h]; dwDesiredAccess
0x140039bcf  call    cs:__imp_OpenProcess
0x140039bd5  mov     rdi, rax
0x140039bd8  test    rax, rax
0x140039bdb  jnz     short loc_140039BF2
0x140039bdd  call    cs:__imp_GetLastError
0x140039be3  mov     ebx, eax
0x140039be5  cmp     eax, 5
0x140039be8  jz      short loc_140039BF2
0x140039bea  test    eax, eax
0x140039bec  jnz     loc_140039C88
0x140039bf2  xor     esi, esi
0x140039bf4  lea     ecx, [rsi+1]
0x140039bf7  call    ?YImpersonateClient@@YAHW4Call_Route@@@Z; YImpersonateClient(Call_Route)
0x140039bfc  test    eax, eax
0x140039bfe  jz      short loc_140039C66
0x140039c00  test    rdi, rdi
0x140039c03  jnz     short loc_140039C29
0x140039c05  mov     r8d, ebp; dwProcessId
0x140039c08  lea     ecx, [rsi+40h]; dwDesiredAccess
0x140039c0b  xor     edx, edx; bInheritHandle
0x140039c0d  call    cs:__imp_OpenProcess
0x140039c13  mov     rdi, rax
0x140039c16  test    rax, rax
0x140039c19  jnz     short loc_140039C29
0x140039c1b  call    cs:__imp_GetLastError
0x140039c21  mov     ebx, eax
0x140039c23  test    eax, eax
0x140039c25  jnz     short loc_140039C5A
0x140039c27  jmp     short loc_140039C2B
0x140039c29  xor     ebx, ebx
0x140039c2b  mov     eax, [rsp+78h+arg_20]
0x140039c32  mov     r9, r15
0x140039c35  mov     [rsp+78h+var_50], r14
0x140039c3a  mov     r8d, r12d
0x140039c3d  mov     rdx, rdi
0x140039c40  mov     [rsp+78h+var_58], eax
0x140039c44  mov     rcx, r13
0x140039c47  call    SplGetSpoolFileInfo
0x140039c4c  mov     esi, eax
0x140039c4e  test    eax, eax
0x140039c50  jnz     short loc_140039C5A
0x140039c52  call    cs:__imp_GetLastError
0x140039c58  mov     ebx, eax
0x140039c5a  mov     ecx, 1
0x140039c5f  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x140039c64  jmp     short loc_140039C6E
0x140039c66  call    cs:__imp_GetLastError
0x140039c6c  mov     ebx, eax
0x140039c6e  test    rdi, rdi
0x140039c71  jz      short loc_140039C7C
0x140039c73  mov     rcx, rdi; hObject
0x140039c76  call    cs:__imp_CloseHandle
0x140039c7c  test    esi, esi
0x140039c7e  jnz     short loc_140039C88
0x140039c80  test    ebx, ebx
0x140039c82  lea     eax, [rsi+6]
0x140039c85  cmovz   ebx, eax
0x140039c88  mov     eax, ebx
0x140039c8a  add     rsp, 38h
0x140039c8e  pop     r15
0x140039c90  pop     r14
0x140039c92  pop     r13
0x140039c94  pop     r12
0x140039c96  pop     rdi
0x140039c97  pop     rsi
0x140039c98  pop     rbp
0x140039c99  pop     rbx
0x140039c9a  retn
```
