# IsolationAwareCreatePropertySheetPageW

- ea: `0x180011290`
- end: `0x180011381`
- name: `IsolationAwareCreatePropertySheetPageW`
- size: `241`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800059e0`

## callees

- `0x180011290`
- `0x1800117d4`
- `0x180011a40`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e2da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011373`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e2fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011373`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e2fa`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180011367`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e2ee`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180011367`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e2ee`

## string_xrefs

- `0x1800112e8`: `CreatePropertySheetPageW`

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
0x180011290  mov     rax, rsp
0x180011293  mov     [rax+10h], rbx
0x180011297  mov     [rax+18h], rsi
0x18001129b  push    rdi
0x18001129c  sub     rsp, 30h
0x1800112a0  mov     rdi, rcx
0x1800112a3  xor     ebx, ebx
0x1800112a5  mov     [rax-18h], rbx
0x1800112a9  mov     rsi, cs:?s_pfn@?1??IsolationAwareCreatePropertySheetPageW@@9@4P6APEAU_PSP@@PEBU_PROPSHEETPAGEW@@@ZEA; _PSP * (*`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(_PROPSHEETPAGEW const *)
0x1800112b0  mov     [rax+8], rbx
0x1800112b4  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, ebx
0x1800112ba  jnz     short loc_1800112E3
0x1800112bc  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, ebx
0x1800112c2  jnz     short loc_1800112E3
0x1800112c4  lea     rcx, [rax+8]; lpCookie
0x1800112c8  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800112cd  test    eax, eax
0x1800112cf  jnz     short loc_1800112E3
0x1800112d1  xor     eax, eax
0x1800112d3  mov     rbx, [rsp+38h+arg_8]
0x1800112d8  mov     rsi, [rsp+38h+arg_10]
0x1800112dd  add     rsp, 30h
0x1800112e1  pop     rdi
0x1800112e2  retn
0x1800112e3  test    rsi, rsi
0x1800112e6  jnz     short loc_180011300
0x1800112e8  lea     rcx, aCreateproperty; "CreatePropertySheetPageW"
0x1800112ef  call    PrshtIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x1800112f4  test    rax, rax
0x1800112f7  jz      short loc_180011338
0x1800112f9  mov     cs:?s_pfn@?1??IsolationAwareCreatePropertySheetPageW@@9@4P6APEAU_PSP@@PEBU_PROPSHEETPAGEW@@@ZEA, rax; _PSP * (*`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(_PROPSHEETPAGEW const *)
0x180011300  mov     eax, [rdi+4]
0x180011303  mov     ecx, 4000h
0x180011308  test    ecx, eax
0x18001130a  jnz     short loc_180011321
0x18001130c  cmp     dword ptr [rdi], 60h ; '`'
0x18001130f  jb      short loc_180011321
0x180011311  or      eax, ecx
0x180011313  mov     [rdi+4], eax
0x180011316  mov     rax, cs:WinbaseIsolationAwarePrivateT_UnPgpgk
0x18001131d  mov     [rdi+58h], rax
0x180011321  mov     rcx, rdi
0x180011324  mov     rax, cs:?s_pfn@?1??IsolationAwareCreatePropertySheetPageW@@9@4P6APEAU_PSP@@PEBU_PROPSHEETPAGEW@@@ZEA; _PSP * (*`IsolationAwareCreatePropertySheetPageW'::`2'::s_pfn)(_PROPSHEETPAGEW const *)
0x18001132b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011330  mov     rbx, rax
0x180011333  mov     [rsp+38h+var_18], rax
0x180011338  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001133f  jz      short loc_18001134A
0x180011341  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180011348  jnz     short loc_180011379
0x18001134a  test    rbx, rbx
0x18001134d  jnz     short loc_18001135C
0x18001134f  lea     esi, [rbx+1]
0x180011352  call    cs:__imp_GetLastError
0x180011358  mov     edi, eax
0x18001135a  jmp     short loc_180011360
0x18001135c  xor     esi, esi
0x18001135e  xor     edi, edi
0x180011360  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180011365  xor     ecx, ecx; dwFlags
0x180011367  call    cs:__imp_DeactivateActCtx
0x18001136d  test    esi, esi
0x18001136f  jz      short loc_180011379
0x180011371  mov     ecx, edi; dwErrCode
0x180011373  call    cs:__imp_SetLastError
0x180011379  mov     rax, rbx
0x18001137c  jmp     loc_1800112D3
0x18001e2b1  push    rbx
0x18001e2b3  push    rbp
0x18001e2b4  push    rdi
0x18001e2b5  sub     rsp, 20h
0x18001e2b9  mov     rbp, rdx
0x18001e2bc  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001e2c3  jz      short loc_18001E2CE
0x18001e2c5  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001e2cc  jnz     short loc_18001E301
0x18001e2ce  cmp     qword ptr [rbp+20h], 0
0x18001e2d3  jnz     short loc_18001E2E4
0x18001e2d5  mov     edi, 1
0x18001e2da  call    cs:__imp_GetLastError
0x18001e2e0  mov     ebx, eax
0x18001e2e2  jmp     short loc_18001E2E8
0x18001e2e4  xor     edi, edi
0x18001e2e6  xor     ebx, ebx
0x18001e2e8  mov     rdx, [rbp+40h]; ulCookie
0x18001e2ec  xor     ecx, ecx; dwFlags
0x18001e2ee  call    cs:__imp_DeactivateActCtx
0x18001e2f4  test    edi, edi
0x18001e2f6  jz      short loc_18001E301
0x18001e2f8  mov     ecx, ebx; dwErrCode
0x18001e2fa  call    cs:__imp_SetLastError
0x18001e300  nop
0x18001e301  add     rsp, 20h
0x18001e305  pop     rdi
0x18001e306  pop     rbp
0x18001e307  pop     rbx
0x18001e308  retn
```
