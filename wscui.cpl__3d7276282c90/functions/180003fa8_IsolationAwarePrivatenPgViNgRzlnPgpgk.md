# IsolationAwarePrivatenPgViNgRzlnPgpgk

- ea: `0x180003fa8`
- end: `0x18000402e`
- name: `IsolationAwarePrivatenPgViNgRzlnPgpgk`
- size: `134`
- prototype: `__int64 __fastcall(ULONG_PTR *lpCookie)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180003e54`
- `0x180003f1c`
- `0x180006284`
- `0x180006340`
- `0x180007bc8`

## callees

- `0x180003fa8`
- `0x180004050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ff8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003fc2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003fc2`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180003fee`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180003fee`

## pseudocode

```c
__int64 __fastcall IsolationAwarePrivatenPgViNgRzlnPgpgk(ULONG_PTR *lpCookie)
{
  int v1; // eax
  DWORD LastError; // eax
  DWORD v4; // edx
  __int64 result; // rax

  v1 = WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ;
  if ( WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ )
  {
    OutputDebugStringA("IsolationAware function called after IsolationAwareCleanup\n");
    v1 = WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ;
  }
  if ( IsolationAwarePrivateT_SqbjaYRiRY
    || (v1 || (unsigned int)WinbaseIsolationAwarePrivatetRgzlnPgpgk())
    && ActivateActCtx(WinbaseIsolationAwarePrivateT_UnPgpgk, lpCookie) )
  {
    return 1;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError == 120 || LastError == 1 || LastError - 126 <= 1 || (result = 0, v4 == 50) )
  {
    IsolationAwarePrivateT_SqbjaYRiRY = 1;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180003fa8  push    rbx
0x180003faa  sub     rsp, 20h
0x180003fae  mov     eax, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x180003fb4  mov     rbx, rcx
0x180003fb7  test    eax, eax
0x180003fb9  jz      short loc_180003FCE
0x180003fbb  lea     rcx, ?debugString@?4??IsolationAwarePrivatenPgViNgRzlnPgpgk@@9@4QBDB; "IsolationAware function called after Is"...
0x180003fc2  call    cs:__imp_OutputDebugStringA
0x180003fc8  mov     eax, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x180003fce  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180003fd5  jnz     short loc_180004023
0x180003fd7  test    eax, eax
0x180003fd9  jnz     short loc_180003FE4
0x180003fdb  call    WinbaseIsolationAwarePrivatetRgzlnPgpgk
0x180003fe0  test    eax, eax
0x180003fe2  jz      short loc_180003FF8
0x180003fe4  mov     rcx, cs:WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180003feb  mov     rdx, rbx; lpCookie
0x180003fee  call    cs:__imp_ActivateActCtx
0x180003ff4  test    eax, eax
0x180003ff6  jnz     short loc_180004023
0x180003ff8  call    cs:__imp_GetLastError
0x180003ffe  mov     edx, eax
0x180004000  cmp     eax, 78h ; 'x'
0x180004003  jz      short loc_180004019
0x180004005  cmp     eax, 1
0x180004008  jz      short loc_180004019
0x18000400a  lea     ecx, [rax-7Eh]
0x18000400d  cmp     ecx, 1
0x180004010  jbe     short loc_180004019
0x180004012  xor     eax, eax
0x180004014  cmp     edx, 32h ; '2'
0x180004017  jnz     short loc_180004028
0x180004019  mov     cs:IsolationAwarePrivateT_SqbjaYRiRY, 1
0x180004023  mov     eax, 1
0x180004028  add     rsp, 20h
0x18000402c  pop     rbx
0x18000402d  retn
```
