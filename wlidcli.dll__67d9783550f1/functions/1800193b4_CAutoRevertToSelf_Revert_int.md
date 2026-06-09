# CAutoRevertToSelf::Revert(int)

- ea: `0x1800193b4`
- end: `0x180019477`
- name: `?Revert@CAutoRevertToSelf@@QEAAHH@Z`
- size: `195`
- prototype: `__int64 __fastcall(CAutoRevertToSelf *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180015e24`

## callees

- `0x1800193b4`
- `0x1800530e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019437`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800193db`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800193db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800193c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800193c1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001942b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001942b`

## string_xrefs

- `0x18001940c`: `OpenThreadToken failed (0x%x).`
- `0x180019453`: `SetThreadToken failed (0x%x).`

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
0x1800193b4  mov     [rsp+arg_0], rbx
0x1800193b9  push    rdi
0x1800193ba  sub     rsp, 30h
0x1800193be  mov     rdi, rcx
0x1800193c1  call    cs:__imp_GetCurrentThread
0x1800193c7  mov     ebx, 1
0x1800193cc  lea     r9, [rdi+8]; TokenHandle
0x1800193d0  mov     rcx, rax; ThreadHandle
0x1800193d3  mov     r8d, ebx; OpenAsSelf
0x1800193d6  mov     edx, 0F01FFh; DesiredAccess
0x1800193db  call    cs:__imp_OpenThreadToken
0x1800193e1  test    eax, eax
0x1800193e3  jnz     short loc_180019427
0x1800193e5  call    cs:__imp_GetLastError
0x1800193eb  cmp     eax, 3F0h
0x1800193f0  jnz     short loc_1800193F6
0x1800193f2  mov     eax, ebx
0x1800193f4  jmp     short loc_18001946C
0x1800193f6  test    eax, eax
0x1800193f8  jle     short loc_180019402
0x1800193fa  movzx   eax, ax
0x1800193fd  or      eax, 80070000h
0x180019402  mov     r8d, 4Bh ; 'K'; unsigned int
0x180019408  mov     [rsp+38h+var_18], eax
0x18001940c  lea     r9, aOpenthreadtoke; "OpenThreadToken failed (0x%x)."
0x180019413  lea     rdx, aOnecoreuapRest; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x18001941a  lea     ecx, [r8-49h]; unsigned __int8
0x18001941e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180019423  xor     eax, eax
0x180019425  jmp     short loc_18001946C
0x180019427  xor     edx, edx; Token
0x180019429  xor     ecx, ecx; Thread
0x18001942b  call    cs:__imp_SetThreadToken
0x180019431  mov     [rdi], eax
0x180019433  test    eax, eax
0x180019435  jnz     short loc_18001946A
0x180019437  call    cs:__imp_GetLastError
0x18001943d  test    eax, eax
0x18001943f  jle     short loc_180019449
0x180019441  movzx   eax, ax
0x180019444  or      eax, 80070000h
0x180019449  mov     r8d, 56h ; 'V'; unsigned int
0x18001944f  mov     [rsp+38h+var_18], eax
0x180019453  lea     r9, aSetthreadtoken; "SetThreadToken failed (0x%x)."
0x18001945a  lea     rdx, aOnecoreuapRest; "onecoreuap\\restricted\\ds\\inc\\idcrl"...
0x180019461  lea     ecx, [r8-54h]; unsigned __int8
0x180019465  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001946a  mov     eax, [rdi]
0x18001946c  mov     rbx, [rsp+38h+arg_0]
0x180019471  add     rsp, 30h
0x180019475  pop     rdi
0x180019476  retn
```
