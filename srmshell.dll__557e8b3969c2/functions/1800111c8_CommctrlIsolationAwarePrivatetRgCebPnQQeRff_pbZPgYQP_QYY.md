# CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY

- ea: `0x1800111c8`
- end: `0x18001128a`
- name: `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY`
- size: `194`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180011454`
- `0x180011550`
- `0x18001161c`
- `0x180011950`

## callees

- `0x1800111c8`
- `0x1800117d4`
- `0x180011860`
- `0x180011a40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011251`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011271`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011271`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011231`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011231`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180011264`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180011264`

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
0x1800111c8  mov     rax, rsp
0x1800111cb  mov     [rax+8], rbx
0x1800111cf  mov     [rax+18h], rsi
0x1800111d3  push    rdi
0x1800111d4  sub     rsp, 30h
0x1800111d8  mov     rsi, rcx
0x1800111db  xor     ebx, ebx
0x1800111dd  mov     [rax-10h], rbx
0x1800111e1  xor     edi, edi
0x1800111e3  mov     [rax-18h], edi
0x1800111e6  mov     [rax+10h], rbx
0x1800111ea  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x1800111f0  jnz     short loc_180011205
0x1800111f2  lea     rcx, [rax+10h]; lpCookie
0x1800111f6  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800111fb  mov     edi, eax
0x1800111fd  mov     [rsp+38h+var_18], eax
0x180011201  test    eax, eax
0x180011203  jz      short loc_18001123F
0x180011205  mov     rax, cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x18001120c  test    rax, rax
0x18001120f  jnz     short loc_18001122B
0x180011211  xor     ebx, ebx
0x180011213  mov     rcx, cs:lpLibFileName; lpLibFileName
0x18001121a  call    IsolationAwarePrivatezlybNQyVOeNelJ
0x18001121f  test    rax, rax
0x180011222  jz      short loc_18001123A
0x180011224  mov     cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A, rax; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x18001122b  mov     rdx, rsi; lpProcName
0x18001122e  mov     rcx, rax; hModule
0x180011231  call    cs:__imp_GetProcAddress
0x180011237  mov     rbx, rax
0x18001123a  mov     [rsp+38h+var_10], rbx
0x18001123f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180011246  jnz     short loc_180011277
0x180011248  test    edi, edi
0x18001124a  jz      short loc_180011277
0x18001124c  test    rbx, rbx
0x18001124f  jnz     short loc_18001125B
0x180011251  call    cs:__imp_GetLastError
0x180011257  mov     edi, eax
0x180011259  jmp     short loc_18001125D
0x18001125b  xor     edi, edi
0x18001125d  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180011262  xor     ecx, ecx; dwFlags
0x180011264  call    cs:__imp_DeactivateActCtx
0x18001126a  test    rbx, rbx
0x18001126d  jnz     short loc_180011277
0x18001126f  mov     ecx, edi; dwErrCode
0x180011271  call    cs:__imp_SetLastError
0x180011277  mov     rax, rbx
0x18001127a  mov     rbx, [rsp+38h+arg_0]
0x18001127f  mov     rsi, [rsp+38h+arg_10]
0x180011284  add     rsp, 30h
0x180011288  pop     rdi
0x180011289  retn
0x18001e259  push    rbx
0x18001e25b  push    rbp
0x18001e25c  push    rdi
0x18001e25d  sub     rsp, 20h
0x18001e261  mov     rbp, rdx
0x18001e264  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001e26b  jnz     short loc_18001E2A2
0x18001e26d  cmp     dword ptr [rbp+20h], 0
0x18001e271  jz      short loc_18001E2A2
0x18001e273  mov     rbx, [rbp+28h]
0x18001e277  test    rbx, rbx
0x18001e27a  jnz     short loc_18001E286
0x18001e27c  call    cs:__imp_GetLastError
0x18001e282  mov     edi, eax
0x18001e284  jmp     short loc_18001E288
0x18001e286  xor     edi, edi
0x18001e288  mov     rdx, [rbp+48h]; ulCookie
0x18001e28c  xor     ecx, ecx; dwFlags
0x18001e28e  call    cs:__imp_DeactivateActCtx
0x18001e294  test    rbx, rbx
0x18001e297  jnz     short loc_18001E2A2
0x18001e299  mov     ecx, edi; dwErrCode
0x18001e29b  call    cs:__imp_SetLastError
0x18001e2a1  nop
0x18001e2a2  add     rsp, 20h
0x18001e2a6  pop     rdi
0x18001e2a7  pop     rbp
0x18001e2a8  pop     rbx
0x18001e2a9  retn
```
