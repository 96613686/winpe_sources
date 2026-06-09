# CAutoRevertToSelf::Revert(int)

- ea: `0x180023d24`
- end: `0x180023dfc`
- name: `?Revert@CAutoRevertToSelf@@QEAAHH@Z`
- size: `216`
- prototype: `__int64 __fastcall(void **this, int)`
- caller_count: `34`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180023b98`
- `0x180023d10`
- `0x180023f60`
- `0x18004a4b8`
- `0x18005a66c`
- `0x18005abd0`
- `0x18005ae00`
- `0x18005afc0`
- `0x18005bae0`
- `0x180062c8c`
- `0x180072374`
- `0x18007ff00`
- `0x180081648`
- `0x180091110`
- `0x180099d08`
- `0x1800b0604`
- `0x1800c2980`
- `0x1800c3470`
- `0x1800c3e64`
- `0x1800c5e24`
- `0x1800c7b8c`
- `0x1800d83f0`
- `0x1800e17cc`
- `0x1800e1d1c`
- `0x180101364`
- `0x18010350c`
- `0x1801054a0`
- `0x180105ce8`
- `0x180106018`
- `0x1801064a8`
- `0x180107444`
- `0x18010763c`
- `0x180107854`
- `0x180107bec`

## callees

- `0x180019690`
- `0x180023d24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023dc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023dc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023d38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023d38`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180023d60`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180023d60`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023d52`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023d52`

## string_xrefs

- `0x180023da9`: `OpenThreadToken failed (0x%x).`
- `0x180023de0`: `SetThreadToken failed (0x%x).`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAutoRevertToSelf::Revert(void **this, int a2)
{
  HANDLE CurrentThread; // rax
  BOOL v5; // eax
  signed int v7; // eax
  signed int LastError; // eax

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
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\Live\\identity\\Lib\\TransferImplementation\\transferimp.h",
        0x56u,
        L"SetThreadToken failed (0x%x).",
        LastError);
    }
    return *(unsigned int *)this;
  }
  else
  {
    v7 = GetLastError();
    if ( a2 || v7 != 1008 )
    {
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\Live\\identity\\Lib\\TransferImplementation\\transferimp.h",
        0x4Bu,
        L"OpenThreadToken failed (0x%x).",
        v7);
      return 0;
    }
    else
    {
      return 1;
    }
  }
}

```

## disassembly

```asm
0x180023d24  mov     [rsp+arg_0], rbx
0x180023d29  mov     [rsp+arg_8], rsi
0x180023d2e  push    rdi
0x180023d2f  sub     rsp, 30h
0x180023d33  mov     esi, edx
0x180023d35  mov     rdi, rcx
0x180023d38  call    cs:__imp_GetCurrentThread
0x180023d3e  mov     ebx, 1
0x180023d43  lea     r9, [rdi+8]; TokenHandle
0x180023d47  mov     rcx, rax; ThreadHandle
0x180023d4a  mov     r8d, ebx; OpenAsSelf
0x180023d4d  mov     edx, 0F01FFh; DesiredAccess
0x180023d52  call    cs:__imp_OpenThreadToken
0x180023d58  test    eax, eax
0x180023d5a  jz      short loc_180023D7E
0x180023d5c  xor     edx, edx; Token
0x180023d5e  xor     ecx, ecx; Thread
0x180023d60  call    cs:__imp_SetThreadToken
0x180023d66  mov     [rdi], eax
0x180023d68  test    eax, eax
0x180023d6a  jz      short loc_180023DC4
0x180023d6c  mov     eax, [rdi]
0x180023d6e  mov     rbx, [rsp+38h+arg_0]
0x180023d73  mov     rsi, [rsp+38h+arg_8]
0x180023d78  add     rsp, 30h
0x180023d7c  pop     rdi
0x180023d7d  retn
0x180023d7e  call    cs:__imp_GetLastError
0x180023d84  test    esi, esi
0x180023d86  jnz     short loc_180023D93
0x180023d88  cmp     eax, 3F0h
0x180023d8d  jnz     short loc_180023D93
0x180023d8f  mov     eax, ebx
0x180023d91  jmp     short loc_180023D6E
0x180023d93  test    eax, eax
0x180023d95  jle     short loc_180023D9F
0x180023d97  movzx   eax, ax
0x180023d9a  or      eax, 80070000h
0x180023d9f  mov     r8d, 4Bh ; 'K'; unsigned int
0x180023da5  mov     [rsp+38h+var_18], eax
0x180023da9  lea     r9, aOpenthreadtoke; "OpenThreadToken failed (0x%x)."
0x180023db0  lea     rdx, aOnecoreuapDsEx_51; "onecoreuap\\ds\\ext\\Live\\identity\\Li"...
0x180023db7  lea     ecx, [r8-49h]; unsigned __int8
0x180023dbb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180023dc0  xor     eax, eax
0x180023dc2  jmp     short loc_180023D6E
0x180023dc4  call    cs:__imp_GetLastError
0x180023dca  test    eax, eax
0x180023dcc  jle     short loc_180023DD6
0x180023dce  movzx   eax, ax
0x180023dd1  or      eax, 80070000h
0x180023dd6  mov     r8d, 56h ; 'V'; unsigned int
0x180023ddc  mov     [rsp+38h+var_18], eax
0x180023de0  lea     r9, aSetthreadtoken; "SetThreadToken failed (0x%x)."
0x180023de7  lea     rdx, aOnecoreuapDsEx_51; "onecoreuap\\ds\\ext\\Live\\identity\\Li"...
0x180023dee  lea     ecx, [r8-54h]; unsigned __int8
0x180023df2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180023df7  jmp     loc_180023D6C
```
