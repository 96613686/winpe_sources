# AutoProfile::~AutoProfile(void)

- ea: `0x1800042f0`
- end: `0x18000437e`
- name: `??1AutoProfile@@QEAA@XZ`
- size: `142`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800043c0`
- `0x18000b808`
- `0x180015bc0`
- `0x18001652e`

## callees

- `0x1800042f0`
- `0x180007ca8`
- `0x180007d10`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004371`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000432c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000432c`
- `wbemcomn!ErrorTrace` at `0x180004344`
- `wbemcomn!ErrorTrace` at `0x180004362`
- `wbemcomn!ErrorTrace` at `0x180004344`
- `wbemcomn!ErrorTrace` at `0x180004362`
- `wbemcomn!DebugTrace` at `0x180004324`
- `wbemcomn!DebugTrace` at `0x180004324`
- `USERENV!UnloadUserProfile` at `0x18000430b`
- `USERENV!UnloadUserProfile` at `0x18000430b`

## string_xrefs

- `0x180004356`: `Registry event provider unable to CoImpersonateClient hr2= 0x%x.\n`

## pseudocode

```c
void __fastcall AutoProfile::~AutoProfile(HANDLE *this)
{
  DWORD LastError; // eax
  int v3; // eax
  HANDLE v4; // rcx

  if ( *(_DWORD *)this )
  {
    WbemCoRevertToSelf();
    if ( UnloadUserProfile(this[1], this[2]) )
    {
      DebugTrace(9, "Profile@0x%x unload.\n", (_DWORD)this);
    }
    else
    {
      LastError = GetLastError();
      ErrorTrace(9, "Profile@0x%x failed to unload 0x%x.\n", (_DWORD)this, LastError);
    }
    v3 = WbemCoImpersonateClient();
    if ( v3 < 0 )
      ErrorTrace(9, "Registry event provider unable to CoImpersonateClient hr2= 0x%x.\n", v3);
  }
  v4 = this[1];
  if ( v4 )
    CloseHandle(v4);
}

```

## disassembly

```asm
0x1800042f0  push    rbx
0x1800042f2  sub     rsp, 20h
0x1800042f6  mov     rbx, rcx
0x1800042f9  cmp     dword ptr [rcx], 0
0x1800042fc  jz      short loc_180004368
0x1800042fe  call    ?WbemCoRevertToSelf@@YAJXZ; WbemCoRevertToSelf(void)
0x180004303  mov     rdx, [rbx+10h]; hProfile
0x180004307  mov     rcx, [rbx+8]; hToken
0x18000430b  call    cs:__imp_UnloadUserProfile
0x180004311  test    eax, eax
0x180004313  jz      short loc_18000432C
0x180004315  mov     r8, rbx
0x180004318  lea     rdx, aProfile0xXUnlo; "Profile@0x%x unload.\n"
0x18000431f  mov     ecx, 9
0x180004324  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000432a  jmp     short loc_18000434A
0x18000432c  call    cs:__imp_GetLastError
0x180004332  mov     r9d, eax
0x180004335  mov     r8, rbx
0x180004338  lea     rdx, aProfile0xXFail; "Profile@0x%x failed to unload 0x%x.\n"
0x18000433f  mov     ecx, 9
0x180004344  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x18000434a  call    ?WbemCoImpersonateClient@@YAJXZ; WbemCoImpersonateClient(void)
0x18000434f  test    eax, eax
0x180004351  jns     short loc_180004368
0x180004353  mov     r8d, eax
0x180004356  lea     rdx, aRegistryEventP; "Registry event provider unable to CoImp"...
0x18000435d  mov     ecx, 9
0x180004362  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x180004368  mov     rcx, [rbx+8]; hObject
0x18000436c  test    rcx, rcx
0x18000436f  jz      short loc_180004378
0x180004371  call    cs:__imp_CloseHandle
0x180004377  nop
0x180004378  add     rsp, 20h
0x18000437c  pop     rbx
0x18000437d  retn
```
