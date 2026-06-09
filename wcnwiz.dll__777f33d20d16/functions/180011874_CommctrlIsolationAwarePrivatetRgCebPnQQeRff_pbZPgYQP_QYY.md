# CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY

- ea: `0x180011874`
- end: `0x18001191a`
- name: `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY`
- size: `166`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011920`
- `0x180011a14`
- `0x180011ae0`
- `0x180011bb8`
- `0x18001a918`
- `0x18001aa00`
- `0x18001aad8`
- `0x18001cd90`

## callees

- `0x18000d428`
- `0x180011874`
- `0x180011c74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011901`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fb20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011901`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fb20`
- `KERNEL32!DeactivateActCtx` at `0x1800118f4`
- `KERNEL32!DeactivateActCtx` at `0x18002fb13`
- `KERNEL32!DeactivateActCtx` at `0x1800118f4`
- `KERNEL32!DeactivateActCtx` at `0x18002fb13`

## pseudocode

```c
__int64 __fastcall CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY(__int64 a1)
{
  __int64 v2; // rbx
  int v3; // edi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v3 = 0;
  ulCookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || (v3 = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie)) != 0 )
    v2 = IsolationAwarePrivatezltRgCebPnQQeRff(
           &`CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::c,
           &`CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m,
           a1);
  if ( !IsolationAwarePrivateT_SqbjaYRiRY && v3 )
  {
    if ( v2 )
      LastError = 0;
    else
      LastError = GetLastError();
    DeactivateActCtx(0, ulCookie);
    if ( !v2 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x180011874  mov     rax, rsp
0x180011877  mov     [rax+8], rbx
0x18001187b  mov     [rax+18h], rsi
0x18001187f  push    rdi
0x180011880  sub     rsp, 30h
0x180011884  mov     rsi, rcx
0x180011887  xor     ebx, ebx
0x180011889  mov     [rax-10h], rbx
0x18001188d  xor     edi, edi
0x18001188f  mov     [rax-18h], edi
0x180011892  mov     [rax+10h], rbx
0x180011896  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x18001189c  jnz     short loc_1800118B1
0x18001189e  lea     rcx, [rax+10h]; lpCookie
0x1800118a2  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800118a7  mov     edi, eax
0x1800118a9  mov     [rsp+38h+var_18], eax
0x1800118ad  test    eax, eax
0x1800118af  jz      short loc_1800118CF
0x1800118b1  mov     r8, rsi
0x1800118b4  lea     rdx, ?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x1800118bb  lea     rcx, ?c@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_pBAFGnAG_zBqHyr_vAsB@@B; IsolationAwarePrivate_pBAFGnAG_zBqHyr_vAsB const `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::c
0x1800118c2  call    IsolationAwarePrivatezltRgCebPnQQeRff
0x1800118c7  mov     rbx, rax
0x1800118ca  mov     [rsp+38h+var_10], rax
0x1800118cf  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800118d6  jnz     short loc_180011907
0x1800118d8  test    edi, edi
0x1800118da  jz      short loc_180011907
0x1800118dc  test    rbx, rbx
0x1800118df  jnz     short loc_1800118EB
0x1800118e1  call    cs:__imp_GetLastError
0x1800118e7  mov     edi, eax
0x1800118e9  jmp     short loc_1800118ED
0x1800118eb  xor     edi, edi
0x1800118ed  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x1800118f2  xor     ecx, ecx; dwFlags
0x1800118f4  call    cs:__imp_DeactivateActCtx
0x1800118fa  test    rbx, rbx
0x1800118fd  jnz     short loc_180011907
0x1800118ff  mov     ecx, edi; dwErrCode
0x180011901  call    cs:__imp_SetLastError
0x180011907  mov     rax, rbx
0x18001190a  mov     rbx, [rsp+38h+arg_0]
0x18001190f  mov     rsi, [rsp+38h+arg_10]
0x180011914  add     rsp, 30h
0x180011918  pop     rdi
0x180011919  retn
0x18002fade  push    rbx
0x18002fae0  push    rbp
0x18002fae1  push    rdi
0x18002fae2  sub     rsp, 20h
0x18002fae6  mov     rbp, rdx
0x18002fae9  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002faf0  jnz     short loc_18002FB27
0x18002faf2  cmp     dword ptr [rbp+20h], 0
0x18002faf6  jz      short loc_18002FB27
0x18002faf8  mov     rbx, [rbp+28h]
0x18002fafc  test    rbx, rbx
0x18002faff  jnz     short loc_18002FB0B
0x18002fb01  call    cs:__imp_GetLastError
0x18002fb07  mov     edi, eax
0x18002fb09  jmp     short loc_18002FB0D
0x18002fb0b  xor     edi, edi
0x18002fb0d  mov     rdx, [rbp+48h]; ulCookie
0x18002fb11  xor     ecx, ecx; dwFlags
0x18002fb13  call    cs:__imp_DeactivateActCtx
0x18002fb19  test    rbx, rbx
0x18002fb1c  jnz     short loc_18002FB27
0x18002fb1e  mov     ecx, edi; dwErrCode
0x18002fb20  call    cs:__imp_SetLastError
0x18002fb26  nop
0x18002fb27  add     rsp, 20h
0x18002fb2b  pop     rdi
0x18002fb2c  pop     rbp
0x18002fb2d  pop     rbx
0x18002fb2e  retn
```
