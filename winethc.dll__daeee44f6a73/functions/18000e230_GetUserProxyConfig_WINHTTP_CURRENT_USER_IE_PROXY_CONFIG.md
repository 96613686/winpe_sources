# GetUserProxyConfig(_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *)

- ea: `0x18000e230`
- end: `0x18000e278`
- name: `?GetUserProxyConfig@@YAJPEAU_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG@@@Z`
- size: `72`
- prototype: `__int64 __fastcall(struct _WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009e04`
- `0x18000d160`

## callees

- `0x18000e230`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e254`
- `KERNEL32!GetLastError` at `0x18000e254`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18000e244`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18000e244`

## pseudocode

```c
__int64 __fastcall GetUserProxyConfig(WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *a1)
{
  unsigned int v2; // ebx
  signed int LastError; // eax

  if ( !a1 )
    return 2147942487LL;
  v2 = 0;
  if ( !WinHttpGetIEProxyConfigForCurrentUser(a1) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v2;
}

```

## disassembly

```asm
0x18000e230  push    rbx
0x18000e232  sub     rsp, 20h
0x18000e236  test    rcx, rcx
0x18000e239  jnz     short loc_18000E242
0x18000e23b  mov     eax, 80070057h
0x18000e240  jmp     short loc_18000E271
0x18000e242  xor     ebx, ebx
0x18000e244  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x18000e24b  nop     dword ptr [rax+rax+00h]
0x18000e250  test    eax, eax
0x18000e252  jnz     short loc_18000E26F
0x18000e254  call    cs:__imp_GetLastError
0x18000e25b  nop     dword ptr [rax+rax+00h]
0x18000e260  mov     ebx, eax
0x18000e262  test    eax, eax
0x18000e264  jle     short loc_18000E26F
0x18000e266  movzx   ebx, ax
0x18000e269  or      ebx, 80070000h
0x18000e26f  mov     eax, ebx
0x18000e271  add     rsp, 20h
0x18000e275  pop     rbx
0x18000e276  retn
```
