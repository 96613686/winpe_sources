# SetBootStatusPolicy(ushort const *)

- ea: `0x180010fc0`
- end: `0x180011039`
- name: `?SetBootStatusPolicy@@YAJPEBG@Z`
- size: `121`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000f258`

## callees

- `0x1800054d0`
- `0x180011f20`
- `0x18001afe2`
- `0x18001b020`

## string_xrefs

- `0x180010ff3`: `/c %%windir%%\system32\bcdedit.exe /set {bootloadersettings} BOOTSTATUSPOLICY %s`
- `0x180011014`: `%windir%\system32\cmd.exe`

## pseudocode

```c
__int64 __fastcall SetBootStatusPolicy(const unsigned __int16 *a1)
{
  WCHAR v3[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(v3, 0, 0x208u);
  StringCchPrintfW(
    v3,
    0x104u,
    L"/c %%windir%%\\system32\\bcdedit.exe /set {bootloadersettings} BOOTSTATUSPOLICY %s",
    a1);
  return ExecuteBackgroundProcess(L"%windir%\\system32\\cmd.exe", v3, 1, 0);
}

```

## disassembly

```asm
0x180010fc0  push    rbx
0x180010fc2  sub     rsp, 240h
0x180010fc9  mov     rax, cs:__security_cookie
0x180010fd0  xor     rax, rsp
0x180010fd3  mov     [rsp+248h+var_18], rax
0x180010fdb  mov     rbx, rcx
0x180010fde  xor     edx, edx; Val
0x180010fe0  lea     rcx, [rsp+248h+var_228]; void *
0x180010fe5  mov     r8d, 208h; Size
0x180010feb  call    memset_0
0x180010ff0  mov     r9, rbx
0x180010ff3  lea     r8, aCWindirSystem3; "/c %%windir%%\\system32\\bcdedit.exe /s"...
0x180010ffa  mov     edx, 104h; unsigned __int64
0x180010fff  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x180011004  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011009  xor     r9d, r9d; unsigned int *
0x18001100c  lea     rdx, [rsp+248h+var_228]; LPCWSTR
0x180011011  mov     r8b, 1; bool
0x180011014  lea     rcx, aWindirSystem32; "%windir%\\system32\\cmd.exe"
0x18001101b  call    ?ExecuteBackgroundProcess@@YAJPEBG0_NPEAK@Z; ExecuteBackgroundProcess(ushort const *,ushort const *,bool,ulong *)
0x180011020  mov     rcx, [rsp+248h+var_18]
0x180011028  xor     rcx, rsp; StackCookie
0x18001102b  call    __security_check_cookie
0x180011030  add     rsp, 240h
0x180011037  pop     rbx
0x180011038  retn
```
