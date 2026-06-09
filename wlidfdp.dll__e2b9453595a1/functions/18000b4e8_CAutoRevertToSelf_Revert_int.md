# CAutoRevertToSelf::Revert(int)

- ea: `0x18000b4e8`
- end: `0x18000b5ab`
- name: `?Revert@CAutoRevertToSelf@@QEAAHH@Z`
- size: `195`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000a998`

## callees

- `0x18000b4e8`
- `0x18000f4cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b56b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b56b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b50f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b50f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000b55f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000b55f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b4f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b4f5`

## string_xrefs

- `0x18000b540`: `OpenThreadToken failed (0x%x).`
- `0x18000b587`: `SetThreadToken failed (0x%x).`

## pseudocode

```c
__int64 __fastcall CAutoRevertToSelf::Revert(HANDLE *this)
{
  HANDLE CurrentThread; // rax
  signed int v3; // eax
  BOOL v5; // eax
  signed int LastError; // eax
  signed int v7; // [rsp+20h] [rbp-18h]
  signed int v8; // [rsp+20h] [rbp-18h]

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, this + 1) )
  {
    v5 = SetThreadToken(0, 0);
    *(_DWORD *)this = v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = LastError;
      TracePrintW(
        2u,
        "onecoreuap\\restricted\\ds\\inc\\idcrl\\transferimp.h",
        0x56u,
        L"SetThreadToken failed (0x%x).",
        v8);
    }
    return *(unsigned int *)this;
  }
  else
  {
    v3 = GetLastError();
    if ( v3 == 1008 )
    {
      return 1;
    }
    else
    {
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      v7 = v3;
      TracePrintW(
        2u,
        "onecoreuap\\restricted\\ds\\inc\\idcrl\\transferimp.h",
        0x4Bu,
        L"OpenThreadToken failed (0x%x).",
        v7);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18000b4e8  mov     [rsp+arg_0], rbx
0x18000b4ed  push    rdi
0x18000b4ee  sub     rsp, 30h
0x18000b4f2  mov     rdi, rcx
0x18000b4f5  call    cs:__imp_GetCurrentThread
0x18000b4fb  mov     ebx, 1
0x18000b500  lea     r9, [rdi+8]; TokenHandle
0x18000b504  mov     rcx, rax; ThreadHandle
0x18000b507  mov     r8d, ebx; OpenAsSelf
0x18000b50a  mov     edx, 0F01FFh; DesiredAccess
0x18000b50f  call    cs:__imp_OpenThreadToken
0x18000b515  test    eax, eax
0x18000b517  jnz     short loc_18000B55B
0x18000b519  call    cs:__imp_GetLastError
0x18000b51f  cmp     eax, 3F0h
0x18000b524  jnz     short loc_18000B52A
0x18000b526  mov     eax, ebx
0x18000b528  jmp     short loc_18000B5A0
0x18000b52a  test    eax, eax
0x18000b52c  jle     short loc_18000B536
0x18000b52e  movzx   eax, ax
0x18000b531  or      eax, 80070000h
0x18000b536  mov     r8d, 4Bh ; 'K'; unsigned int
0x18000b53c  mov     [rsp+38h+var_18], eax
0x18000b540  lea     r9, aOpenthreadtoke; "OpenThreadToken failed (0x%x)."
0x18000b547  lea     rdx, aOnecoreuapRest; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x18000b54e  lea     ecx, [r8-49h]; unsigned __int8
0x18000b552  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000b557  xor     eax, eax
0x18000b559  jmp     short loc_18000B5A0
0x18000b55b  xor     edx, edx; Token
0x18000b55d  xor     ecx, ecx; Thread
0x18000b55f  call    cs:__imp_SetThreadToken
0x18000b565  mov     [rdi], eax
0x18000b567  test    eax, eax
0x18000b569  jnz     short loc_18000B59E
0x18000b56b  call    cs:__imp_GetLastError
0x18000b571  test    eax, eax
0x18000b573  jle     short loc_18000B57D
0x18000b575  movzx   eax, ax
0x18000b578  or      eax, 80070000h
0x18000b57d  mov     r8d, 56h ; 'V'; unsigned int
0x18000b583  mov     [rsp+38h+var_18], eax
0x18000b587  lea     r9, aSetthreadtoken; "SetThreadToken failed (0x%x)."
0x18000b58e  lea     rdx, aOnecoreuapRest; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x18000b595  lea     ecx, [r8-54h]; unsigned __int8
0x18000b599  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000b59e  mov     eax, [rdi]
0x18000b5a0  mov     rbx, [rsp+38h+arg_0]
0x18000b5a5  add     rsp, 30h
0x18000b5a9  pop     rdi
0x18000b5aa  retn
```
