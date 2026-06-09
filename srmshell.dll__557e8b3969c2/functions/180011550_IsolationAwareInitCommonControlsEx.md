# IsolationAwareInitCommonControlsEx

- ea: `0x180011550`
- end: `0x180011613`
- name: `IsolationAwareInitCommonControlsEx`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008288`

## callees

- `0x1800111c8`
- `0x180011550`
- `0x1800117d4`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e338`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800115fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e358`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800115fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e358`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800115ef`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e34c`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800115ef`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e34c`

## string_xrefs

- `0x180011595`: `InitCommonControlsEx`

## pseudocode

```c
__int64 __fastcall IsolationAwareInitCommonControlsEx(__int64 a1)
{
  unsigned int v2; // edi
  __int64 (__fastcall *v3)(__int64); // rbx
  __int64 result; // rax
  __int64 v5; // rax
  int v6; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v3 = (__int64 (__fastcall *)(__int64))`IsolationAwareInitCommonControlsEx'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk && !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    result = IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie);
    if ( !(_DWORD)result )
      return result;
  }
  if ( !v3 )
  {
    v5 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("InitCommonControlsEx");
    v3 = (__int64 (__fastcall *)(__int64))v5;
    if ( !v5 )
      goto LABEL_8;
    `IsolationAwareInitCommonControlsEx'::`2'::s_pfn = v5;
  }
  v2 = v3(a1);
LABEL_8:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v2 )
    {
      v6 = 0;
      LastError = 0;
    }
    else
    {
      v6 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v6 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x180011550  mov     rax, rsp
0x180011553  mov     [rax+8], rbx
0x180011557  mov     [rax+18h], rsi
0x18001155b  push    rdi
0x18001155c  sub     rsp, 30h
0x180011560  mov     rsi, rcx
0x180011563  xor     edi, edi
0x180011565  mov     [rax-18h], edi
0x180011568  mov     rbx, cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x18001156f  mov     [rax+10h], rdi
0x180011573  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x180011579  jnz     short loc_180011590
0x18001157b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180011581  jnz     short loc_180011590
0x180011583  lea     rcx, [rax+10h]; lpCookie
0x180011587  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18001158c  test    eax, eax
0x18001158e  jz      short loc_180011603
0x180011590  test    rbx, rbx
0x180011593  jnz     short loc_1800115B0
0x180011595  lea     rcx, aInitcommoncont; "InitCommonControlsEx"
0x18001159c  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x1800115a1  mov     rbx, rax
0x1800115a4  test    rax, rax
0x1800115a7  jz      short loc_1800115C1
0x1800115a9  mov     cs:?s_pfn@?1??IsolationAwareInitCommonControlsEx@@9@4P6AHPEBUtagINITCOMMONCONTROLSEX@@@ZEA, rax; int (*`IsolationAwareInitCommonControlsEx'::`2'::s_pfn)(tagINITCOMMONCONTROLSEX const *)
0x1800115b0  mov     rcx, rsi
0x1800115b3  mov     rax, rbx
0x1800115b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115bb  mov     edi, eax
0x1800115bd  mov     [rsp+38h+var_18], eax
0x1800115c1  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800115c8  jz      short loc_1800115D3
0x1800115ca  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800115d1  jnz     short loc_180011601
0x1800115d3  test    edi, edi
0x1800115d5  jnz     short loc_1800115E4
0x1800115d7  lea     esi, [rdi+1]
0x1800115da  call    cs:__imp_GetLastError
0x1800115e0  mov     ebx, eax
0x1800115e2  jmp     short loc_1800115E8
0x1800115e4  xor     esi, esi
0x1800115e6  xor     ebx, ebx
0x1800115e8  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x1800115ed  xor     ecx, ecx; dwFlags
0x1800115ef  call    cs:__imp_DeactivateActCtx
0x1800115f5  test    esi, esi
0x1800115f7  jz      short loc_180011601
0x1800115f9  mov     ecx, ebx; dwErrCode
0x1800115fb  call    cs:__imp_SetLastError
0x180011601  mov     eax, edi
0x180011603  mov     rbx, [rsp+38h+arg_0]
0x180011608  mov     rsi, [rsp+38h+arg_10]
0x18001160d  add     rsp, 30h
0x180011611  pop     rdi
0x180011612  retn
0x18001e310  push    rbx
0x18001e312  push    rbp
0x18001e313  push    rdi
0x18001e314  sub     rsp, 20h
0x18001e318  mov     rbp, rdx
0x18001e31b  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001e322  jz      short loc_18001E32D
0x18001e324  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001e32b  jnz     short loc_18001E35F
0x18001e32d  cmp     dword ptr [rbp+20h], 0
0x18001e331  jnz     short loc_18001E342
0x18001e333  mov     edi, 1
0x18001e338  call    cs:__imp_GetLastError
0x18001e33e  mov     ebx, eax
0x18001e340  jmp     short loc_18001E346
0x18001e342  xor     edi, edi
0x18001e344  xor     ebx, ebx
0x18001e346  mov     rdx, [rbp+48h]; ulCookie
0x18001e34a  xor     ecx, ecx; dwFlags
0x18001e34c  call    cs:__imp_DeactivateActCtx
0x18001e352  test    edi, edi
0x18001e354  jz      short loc_18001E35F
0x18001e356  mov     ecx, ebx; dwErrCode
0x18001e358  call    cs:__imp_SetLastError
0x18001e35e  nop
0x18001e35f  add     rsp, 20h
0x18001e363  pop     rdi
0x18001e364  pop     rbp
0x18001e365  pop     rbx
0x18001e366  retn
```
