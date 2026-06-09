# CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY

- ea: `0x1800204a0`
- end: `0x180020562`
- name: `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY`
- size: `194`
- prototype: `__int64 __fastcall(LPCSTR lpProcName)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020568`
- `0x18002064c`
- `0x180020718`

## callees

- `0x18000c6ec`
- `0x1800204a0`
- `0x1800207f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020509`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e6b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e6b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020549`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e6d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020549`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e6d8`
- `KERNEL32!DeactivateActCtx` at `0x18002053c`
- `KERNEL32!DeactivateActCtx` at `0x18002e6cb`
- `KERNEL32!DeactivateActCtx` at `0x18002053c`
- `KERNEL32!DeactivateActCtx` at `0x18002e6cb`

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
0x1800204a0  mov     rax, rsp
0x1800204a3  mov     [rax+8], rbx
0x1800204a7  mov     [rax+18h], rsi
0x1800204ab  push    rdi
0x1800204ac  sub     rsp, 30h
0x1800204b0  mov     rsi, rcx
0x1800204b3  xor     ebx, ebx
0x1800204b5  mov     [rax-10h], rbx
0x1800204b9  xor     edi, edi
0x1800204bb  mov     [rax-18h], edi
0x1800204be  mov     [rax+10h], rbx
0x1800204c2  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x1800204c8  jnz     short loc_1800204DD
0x1800204ca  lea     rcx, [rax+10h]; lpCookie
0x1800204ce  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800204d3  mov     edi, eax
0x1800204d5  mov     [rsp+38h+var_18], eax
0x1800204d9  test    eax, eax
0x1800204db  jz      short loc_180020517
0x1800204dd  mov     rax, cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x1800204e4  test    rax, rax
0x1800204e7  jnz     short loc_180020503
0x1800204e9  xor     ebx, ebx
0x1800204eb  mov     rcx, cs:lpLibFileName; lpLibFileName
0x1800204f2  call    IsolationAwarePrivatezlybNQyVOeNelJ
0x1800204f7  test    rax, rax
0x1800204fa  jz      short loc_180020512
0x1800204fc  mov     cs:?m@?1??CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY@@9@4UIsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB@@A, rax; IsolationAwarePrivate_zHGnoyr_zBqHyr_vAsB `CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY'::`2'::m
0x180020503  mov     rdx, rsi; lpProcName
0x180020506  mov     rcx, rax; hModule
0x180020509  call    cs:__imp_GetProcAddress
0x18002050f  mov     rbx, rax
0x180020512  mov     [rsp+38h+var_10], rbx
0x180020517  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002051e  jnz     short loc_18002054F
0x180020520  test    edi, edi
0x180020522  jz      short loc_18002054F
0x180020524  test    rbx, rbx
0x180020527  jnz     short loc_180020533
0x180020529  call    cs:__imp_GetLastError
0x18002052f  mov     edi, eax
0x180020531  jmp     short loc_180020535
0x180020533  xor     edi, edi
0x180020535  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18002053a  xor     ecx, ecx; dwFlags
0x18002053c  call    cs:__imp_DeactivateActCtx
0x180020542  test    rbx, rbx
0x180020545  jnz     short loc_18002054F
0x180020547  mov     ecx, edi; dwErrCode
0x180020549  call    cs:__imp_SetLastError
0x18002054f  mov     rax, rbx
0x180020552  mov     rbx, [rsp+38h+arg_0]
0x180020557  mov     rsi, [rsp+38h+arg_10]
0x18002055c  add     rsp, 30h
0x180020560  pop     rdi
0x180020561  retn
0x18002e696  push    rbx
0x18002e698  push    rbp
0x18002e699  push    rdi
0x18002e69a  sub     rsp, 20h
0x18002e69e  mov     rbp, rdx
0x18002e6a1  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002e6a8  jnz     short loc_18002E6DF
0x18002e6aa  cmp     dword ptr [rbp+20h], 0
0x18002e6ae  jz      short loc_18002E6DF
0x18002e6b0  mov     rbx, [rbp+28h]
0x18002e6b4  test    rbx, rbx
0x18002e6b7  jnz     short loc_18002E6C3
0x18002e6b9  call    cs:__imp_GetLastError
0x18002e6bf  mov     edi, eax
0x18002e6c1  jmp     short loc_18002E6C5
0x18002e6c3  xor     edi, edi
0x18002e6c5  mov     rdx, [rbp+48h]; ulCookie
0x18002e6c9  xor     ecx, ecx; dwFlags
0x18002e6cb  call    cs:__imp_DeactivateActCtx
0x18002e6d1  test    rbx, rbx
0x18002e6d4  jnz     short loc_18002E6DF
0x18002e6d6  mov     ecx, edi; dwErrCode
0x18002e6d8  call    cs:__imp_SetLastError
0x18002e6de  nop
0x18002e6df  add     rsp, 20h
0x18002e6e3  pop     rdi
0x18002e6e4  pop     rbp
0x18002e6e5  pop     rbx
0x18002e6e6  retn
```
