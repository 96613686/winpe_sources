# IsolationAwareCreatePropertySheetPageW

- ea: `0x180017b24`
- end: `0x180017c15`
- name: `IsolationAwareCreatePropertySheetPageW`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800175b8`

## callees

- `0x180009a60`
- `0x18000dd78`
- `0x180017b24`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017be6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017be6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017c07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800296dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017c07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800296dc`
- `KERNEL32!DeactivateActCtx` at `0x180017bfb`
- `KERNEL32!DeactivateActCtx` at `0x1800296d0`
- `KERNEL32!DeactivateActCtx` at `0x180017bfb`
- `KERNEL32!DeactivateActCtx` at `0x1800296d0`

## string_xrefs

- `0x180017b7c`: `CreatePropertySheetPageW`

## pseudocode

```c
__int64 __fastcall IsolationAwareCreatePropertySheetPageW(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  __int64 v5; // rax
  int v6; // eax
  int v7; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  v3 = `IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  if ( v3 )
    goto LABEL_8;
  v5 = PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("CreatePropertySheetPageW");
  if ( v5 )
  {
    `IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn = v5;
LABEL_8:
    v6 = *(_DWORD *)(a1 + 4);
    if ( (v6 & 0x4000) == 0 && *(_DWORD *)a1 >= 0x60u )
    {
      *(_DWORD *)(a1 + 4) = v6 | 0x4000;
      *(_QWORD *)(a1 + 88) = WinbaseIsolationAwarePrivateT_UnPgpgk;
    }
    v2 = ((__int64 (__fastcall *)(__int64))`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(a1);
  }
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v2 )
    {
      v7 = 0;
      LastError = 0;
    }
    else
    {
      v7 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v7 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x180017b24  mov     rax, rsp
0x180017b27  mov     [rax+10h], rbx
0x180017b2b  mov     [rax+18h], rsi
0x180017b2f  push    rdi
0x180017b30  sub     rsp, 30h
0x180017b34  mov     rdi, rcx
0x180017b37  xor     ebx, ebx
0x180017b39  mov     [rax-18h], rbx
0x180017b3d  mov     rsi, cs:?s_pfn@?1??IsolationAwareCreatePropertySheetPageW@@9@4P6APEAU_PSP@@PEBU_PROPSHEETPAGEW@@@ZEA; _PSP * (*`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(_PROPSHEETPAGEW const *)
0x180017b44  mov     [rax+8], rbx
0x180017b48  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, ebx
0x180017b4e  jnz     short loc_180017B77
0x180017b50  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, ebx
0x180017b56  jnz     short loc_180017B77
0x180017b58  lea     rcx, [rax+8]; lpCookie
0x180017b5c  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180017b61  test    eax, eax
0x180017b63  jnz     short loc_180017B77
0x180017b65  xor     eax, eax
0x180017b67  mov     rbx, [rsp+38h+arg_8]
0x180017b6c  mov     rsi, [rsp+38h+arg_10]
0x180017b71  add     rsp, 30h
0x180017b75  pop     rdi
0x180017b76  retn
0x180017b77  test    rsi, rsi
0x180017b7a  jnz     short loc_180017B94
0x180017b7c  lea     rcx, aCreateproperty; "CreatePropertySheetPageW"
0x180017b83  call    PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x180017b88  test    rax, rax
0x180017b8b  jz      short loc_180017BCC
0x180017b8d  mov     cs:?s_pfn@?1??IsolationAwareCreatePropertySheetPageW@@9@4P6APEAU_PSP@@PEBU_PROPSHEETPAGEW@@@ZEA, rax; _PSP * (*`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(_PROPSHEETPAGEW const *)
0x180017b94  mov     eax, [rdi+4]
0x180017b97  mov     ecx, 4000h
0x180017b9c  test    ecx, eax
0x180017b9e  jnz     short loc_180017BB5
0x180017ba0  cmp     dword ptr [rdi], 60h ; '`'
0x180017ba3  jb      short loc_180017BB5
0x180017ba5  or      eax, ecx
0x180017ba7  mov     [rdi+4], eax
0x180017baa  mov     rax, cs:WinbaseIsolationAwarePrivateT_UnPgpgk
0x180017bb1  mov     [rdi+58h], rax
0x180017bb5  mov     rcx, rdi
0x180017bb8  mov     rax, cs:?s_pfn@?1??IsolationAwareCreatePropertySheetPageW@@9@4P6APEAU_PSP@@PEBU_PROPSHEETPAGEW@@@ZEA; _PSP * (*`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(_PROPSHEETPAGEW const *)
0x180017bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bc4  mov     rbx, rax
0x180017bc7  mov     [rsp+38h+var_18], rax
0x180017bcc  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180017bd3  jz      short loc_180017BDE
0x180017bd5  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180017bdc  jnz     short loc_180017C0D
0x180017bde  test    rbx, rbx
0x180017be1  jnz     short loc_180017BF0
0x180017be3  lea     esi, [rbx+1]
0x180017be6  call    cs:__imp_GetLastError
0x180017bec  mov     edi, eax
0x180017bee  jmp     short loc_180017BF4
0x180017bf0  xor     esi, esi
0x180017bf2  xor     edi, edi
0x180017bf4  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180017bf9  xor     ecx, ecx; dwFlags
0x180017bfb  call    cs:__imp_DeactivateActCtx
0x180017c01  test    esi, esi
0x180017c03  jz      short loc_180017C0D
0x180017c05  mov     ecx, edi; dwErrCode
0x180017c07  call    cs:__imp_SetLastError
0x180017c0d  mov     rax, rbx
0x180017c10  jmp     loc_180017B67
0x180029693  push    rbx
0x180029695  push    rbp
0x180029696  push    rdi
0x180029697  sub     rsp, 20h
0x18002969b  mov     rbp, rdx
0x18002969e  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800296a5  jz      short loc_1800296B0
0x1800296a7  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800296ae  jnz     short loc_1800296E3
0x1800296b0  cmp     qword ptr [rbp+20h], 0
0x1800296b5  jnz     short loc_1800296C6
0x1800296b7  mov     edi, 1
0x1800296bc  call    cs:__imp_GetLastError
0x1800296c2  mov     ebx, eax
0x1800296c4  jmp     short loc_1800296CA
0x1800296c6  xor     edi, edi
0x1800296c8  xor     ebx, ebx
0x1800296ca  mov     rdx, [rbp+40h]; ulCookie
0x1800296ce  xor     ecx, ecx; dwFlags
0x1800296d0  call    cs:__imp_DeactivateActCtx
0x1800296d6  test    edi, edi
0x1800296d8  jz      short loc_1800296E3
0x1800296da  mov     ecx, ebx; dwErrCode
0x1800296dc  call    cs:__imp_SetLastError
0x1800296e2  nop
0x1800296e3  add     rsp, 20h
0x1800296e7  pop     rdi
0x1800296e8  pop     rbp
0x1800296e9  pop     rbx
0x1800296ea  retn
```
