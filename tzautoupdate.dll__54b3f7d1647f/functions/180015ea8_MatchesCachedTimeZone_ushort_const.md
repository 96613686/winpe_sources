# MatchesCachedTimeZone(ushort const *)

- ea: `0x180015ea8`
- end: `0x180015f61`
- name: `?MatchesCachedTimeZone@@YA_NPEBG@Z`
- size: `185`
- prototype: `bool __fastcall(LPCWCH lpString2)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800169f8`

## callees

- `0x180015ea8`
- `0x18001b0f6`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015f3c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015f3c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015f18`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015f18`

## pseudocode

```c
bool __fastcall MatchesCachedTimeZone(LPCWCH lpString2)
{
  DWORD pcbData[4]; // [rsp+40h] [rbp-128h] BYREF
  WCHAR String1[128]; // [rsp+50h] [rbp-118h] BYREF

  memset_0(String1, 0, sizeof(String1));
  pcbData[0] = 256;
  return !RegGetValueW(
            HKEY_USERS,
            L"S-1-5-19\\Control Panel\\International\\TzNotification",
            L"PreviousTzChange",
            2u,
            0,
            String1,
            pcbData)
      && CompareStringOrdinal(String1, -1, lpString2, -1, 0) == 2;
}

```

## disassembly

```asm
0x180015ea8  push    rbx
0x180015eaa  sub     rsp, 160h
0x180015eb1  mov     rax, cs:__security_cookie
0x180015eb8  xor     rax, rsp
0x180015ebb  mov     [rsp+168h+var_18], rax
0x180015ec3  mov     rbx, rcx
0x180015ec6  xor     edx, edx; Val
0x180015ec8  lea     rcx, [rsp+168h+String1]; void *
0x180015ecd  mov     r8d, 100h; Size
0x180015ed3  call    memset_0
0x180015ed8  lea     rax, [rsp+168h+var_128]
0x180015edd  mov     [rsp+168h+var_128], 100h
0x180015ee5  mov     [rsp+168h+pcbData], rax; pcbData
0x180015eea  lea     r8, ValueName; "PreviousTzChange"
0x180015ef1  lea     rax, [rsp+168h+String1]
0x180015ef6  mov     r9d, 2; dwFlags
0x180015efc  mov     [rsp+168h+pvData], rax; pvData
0x180015f01  lea     rdx, aS1519ControlPa; "S-1-5-19\\Control Panel\\International"...
0x180015f08  mov     rcx, 0FFFFFFFF80000003h; hkey
0x180015f0f  mov     [rsp+168h+pdwType], 0; pdwType
0x180015f18  call    cs:__imp_RegGetValueW
0x180015f1e  test    eax, eax
0x180015f20  jz      short loc_180015F26
0x180015f22  xor     al, al
0x180015f24  jmp     short loc_180015F48
0x180015f26  or      edx, 0FFFFFFFFh; cchCount1
0x180015f29  mov     dword ptr [rsp+168h+pdwType], 0; bIgnoreCase
0x180015f31  mov     r9d, edx; cchCount2
0x180015f34  lea     rcx, [rsp+168h+String1]; lpString1
0x180015f39  mov     r8, rbx; lpString2
0x180015f3c  call    cs:__imp_CompareStringOrdinal
0x180015f42  cmp     eax, 2
0x180015f45  setz    al
0x180015f48  mov     rcx, [rsp+168h+var_18]
0x180015f50  xor     rcx, rsp; StackCookie
0x180015f53  call    __security_check_cookie
0x180015f58  add     rsp, 160h
0x180015f5f  pop     rbx
0x180015f60  retn
```
