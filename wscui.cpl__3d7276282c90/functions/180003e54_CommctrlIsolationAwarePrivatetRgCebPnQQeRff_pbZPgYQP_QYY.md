# CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY

- ea: `0x180003e54`
- end: `0x180003f16`
- name: `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY`
- size: `194`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003f1c`
- `0x180006340`
- `0x180007bc8`

## callees

- `0x180003e54`
- `0x180003fa8`
- `0x180004040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003efd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab9c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003efd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab9c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003ebd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003ebd`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180003ef0`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000ab8f`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180003ef0`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000ab8f`

## pseudocode

```c
FARPROC __fastcall CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY(LPCSTR lpProcName)
{
  FARPROC ProcAddress; // rbx
  int v3; // edi
  HMODULE v4; // rax
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ProcAddress = 0;
  v3 = 0;
  ulCookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || (v3 = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie)) != 0 )
  {
    v4 = `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m;
    if ( `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m )
    {
LABEL_6:
      ProcAddress = GetProcAddress(v4, lpProcName);
      goto LABEL_7;
    }
    ProcAddress = 0;
    v4 = IsolationAwarePrivatezlybNQyVOeNelJ(L"Comctl32.dll");
    if ( v4 )
    {
      `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m = v4;
      goto LABEL_6;
    }
  }
LABEL_7:
  if ( !IsolationAwarePrivateT_SqbjaYRiRY && v3 )
  {
    if ( ProcAddress )
      LastError = 0;
    else
      LastError = GetLastError();
    DeactivateActCtx(0, ulCookie);
    if ( !ProcAddress )
      SetLastError(LastError);
  }
  return ProcAddress;
}

```

## disassembly

```asm
0x180003e54  mov     rax, rsp
0x180003e57  mov     [rax+8], rbx
0x180003e5b  mov     [rax+18h], rsi
0x180003e5f  push    rdi
0x180003e60  sub     rsp, 30h
0x180003e64  mov     rsi, rcx
0x180003e67  xor     ebx, ebx
0x180003e69  mov     [rax-10h], rbx
0x180003e6d  xor     edi, edi
0x180003e6f  mov     [rax-18h], edi
0x180003e72  mov     [rax+10h], rbx
0x180003e76  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180003e7c  jnz     short loc_180003E91
0x180003e7e  lea     rcx, [rax+10h]; lpCookie
0x180003e82  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180003e87  mov     edi, eax
0x180003e89  mov     [rsp+38h+var_18], eax
0x180003e8d  test    eax, eax
0x180003e8f  jz      short loc_180003ECB
0x180003e91  mov     rax, cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x180003e98  test    rax, rax
0x180003e9b  jnz     short loc_180003EB7
0x180003e9d  xor     ebx, ebx
0x180003e9f  mov     rcx, cs:lpLibFileName; lpLibFileName
0x180003ea6  call    IsolationAwarePrivatezlybNQyVOeNelJ
0x180003eab  test    rax, rax
0x180003eae  jz      short loc_180003EC6
0x180003eb0  mov     cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A, rax; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x180003eb7  mov     rdx, rsi; lpProcName
0x180003eba  mov     rcx, rax; hModule
0x180003ebd  call    cs:__imp_GetProcAddress
0x180003ec3  mov     rbx, rax
0x180003ec6  mov     [rsp+38h+var_10], rbx
0x180003ecb  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180003ed2  jnz     short loc_180003F03
0x180003ed4  test    edi, edi
0x180003ed6  jz      short loc_180003F03
0x180003ed8  test    rbx, rbx
0x180003edb  jnz     short loc_180003EE7
0x180003edd  call    cs:__imp_GetLastError
0x180003ee3  mov     edi, eax
0x180003ee5  jmp     short loc_180003EE9
0x180003ee7  xor     edi, edi
0x180003ee9  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180003eee  xor     ecx, ecx; dwFlags
0x180003ef0  call    cs:__imp_DeactivateActCtx
0x180003ef6  test    rbx, rbx
0x180003ef9  jnz     short loc_180003F03
0x180003efb  mov     ecx, edi; dwErrCode
0x180003efd  call    cs:__imp_SetLastError
0x180003f03  mov     rax, rbx
0x180003f06  mov     rbx, [rsp+38h+arg_0]
0x180003f0b  mov     rsi, [rsp+38h+arg_10]
0x180003f10  add     rsp, 30h
0x180003f14  pop     rdi
0x180003f15  retn
0x18000ab5a  push    rbx
0x18000ab5c  push    rbp
0x18000ab5d  push    rdi
0x18000ab5e  sub     rsp, 20h
0x18000ab62  mov     rbp, rdx
0x18000ab65  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000ab6c  jnz     short loc_18000ABA3
0x18000ab6e  cmp     dword ptr [rbp+20h], 0
0x18000ab72  jz      short loc_18000ABA3
0x18000ab74  mov     rbx, [rbp+28h]
0x18000ab78  test    rbx, rbx
0x18000ab7b  jnz     short loc_18000AB87
0x18000ab7d  call    cs:__imp_GetLastError
0x18000ab83  mov     edi, eax
0x18000ab85  jmp     short loc_18000AB89
0x18000ab87  xor     edi, edi
0x18000ab89  mov     rdx, [rbp+48h]; ulCookie
0x18000ab8d  xor     ecx, ecx; dwFlags
0x18000ab8f  call    cs:__imp_DeactivateActCtx
0x18000ab95  test    rbx, rbx
0x18000ab98  jnz     short loc_18000ABA3
0x18000ab9a  mov     ecx, edi; dwErrCode
0x18000ab9c  call    cs:__imp_SetLastError
0x18000aba2  nop
0x18000aba3  add     rsp, 20h
0x18000aba7  pop     rdi
0x18000aba8  pop     rbp
0x18000aba9  pop     rbx
0x18000abaa  retn
```
