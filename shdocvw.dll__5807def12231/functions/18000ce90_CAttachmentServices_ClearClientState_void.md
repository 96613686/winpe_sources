# CAttachmentServices::ClearClientState(void)

- ea: `0x18000ce90`
- end: `0x18000cf13`
- name: `?ClearClientState@CAttachmentServices@@UEAAJXZ`
- size: `131`
- prototype: `__int64 __fastcall(CAttachmentServices *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x180004190`
- `0x180008320`
- `0x18000ce90`

## import_xrefs

- `SHLWAPI!SHDeleteKeyW` at `0x18000cee2`
- `SHLWAPI!SHDeleteKeyW` at `0x18000cee2`
- `SHLWAPI!__imp_SHGetShellKeyEx` at `0x18000cecf`
- `SHLWAPI!__imp_SHGetShellKeyEx` at `0x18000cecf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ceeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ceeb`

## pseudocode

```c
__int64 __fastcall CAttachmentServices::ClearClientState(CAttachmentServices *this, __int64 a2, int a3)
{
  HKEY v3; // rax
  HKEY v4; // rbx
  unsigned __int16 v6[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( !_ClientKey((const struct _GUID *)((char *)this + 72), v6, a3) )
    return 2147549183LL;
  LODWORD(v3) = SHGetShellKeyEx((LPCWSTR)0x11);
  v4 = v3;
  if ( v3 )
  {
    SHDeleteKeyW(v3, 0);
    RegCloseKey(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ce90  push    rbx
0x18000ce92  sub     rsp, 240h
0x18000ce99  mov     rax, cs:__security_cookie
0x18000cea0  xor     rax, rsp
0x18000cea3  mov     [rsp+248h+var_18], rax
0x18000ceab  add     rcx, 48h ; 'H'; struct _GUID *
0x18000ceaf  lea     rdx, [rsp+248h+var_228]; unsigned __int16 *
0x18000ceb4  call    ?_ClientKey@@YAHAEBU_GUID@@PEAGH@Z; _ClientKey(_GUID const &,ushort *,int)
0x18000ceb9  test    eax, eax
0x18000cebb  jz      short loc_18000CEF5
0x18000cebd  xor     r8d, r8d
0x18000cec0  lea     rdx, [rsp+248h+var_228]
0x18000cec5  mov     r9d, 3001Fh
0x18000cecb  lea     ecx, [r8+11h]; pszPath
0x18000cecf  call    cs:__imp_SHGetShellKeyEx
0x18000ced5  mov     rbx, rax
0x18000ced8  test    rax, rax
0x18000cedb  jz      short loc_18000CEF1
0x18000cedd  xor     edx, edx; pszSubKey
0x18000cedf  mov     rcx, rax; hkey
0x18000cee2  call    cs:__imp_SHDeleteKeyW
0x18000cee8  mov     rcx, rbx; hKey
0x18000ceeb  call    cs:__imp_RegCloseKey
0x18000cef1  xor     eax, eax
0x18000cef3  jmp     short loc_18000CEFA
0x18000cef5  mov     eax, 8000FFFFh
0x18000cefa  mov     rcx, [rsp+248h+var_18]
0x18000cf02  xor     rcx, rsp; StackCookie
0x18000cf05  call    __security_check_cookie
0x18000cf0a  add     rsp, 240h
0x18000cf11  pop     rbx
0x18000cf12  retn
```
