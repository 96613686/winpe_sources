# SetPersistentHandlerValue(HKEY__ *,_GUID,int)

- ea: `0x180004584`
- end: `0x180004624`
- name: `?SetPersistentHandlerValue@@YAJPEAUHKEY__@@U_GUID@@H@Z`
- size: `160`
- prototype: `__int64 __fastcall(HKEY hKey, GUID *rguid, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e938`

## callees

- `0x180004584`
- `0x180005cc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800045ba`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800045ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800045f1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800045f1`

## pseudocode

```c
signed int __fastcall SetPersistentHandlerValue(HKEY hKey, GUID *rguid, int a3)
{
  signed int result; // eax
  OLECHAR sz[40]; // [rsp+30h] [rbp-68h] BYREF

  result = StringFromGUID2(rguid, sz, 39);
  if ( result >= 0 )
  {
    result = RegSetValueExW(
               hKey,
               (LPCWSTR)((unsigned __int64)L"OriginalPersistentHandler" & -(__int64)(a3 != 0)),
               0,
               1u,
               (const BYTE *)sz,
               0x4Eu);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180004584  mov     [rsp+arg_10], rbx
0x180004589  push    rdi
0x18000458a  sub     rsp, 90h
0x180004591  mov     rax, cs:__security_cookie
0x180004598  xor     rax, rsp
0x18000459b  mov     [rsp+98h+var_18], rax
0x1800045a3  mov     rax, rdx
0x1800045a6  mov     ebx, r8d
0x1800045a9  mov     rdi, rcx
0x1800045ac  lea     rdx, [rsp+98h+sz]; lpsz
0x1800045b1  mov     rcx, rax; rguid
0x1800045b4  mov     r8d, 27h ; '''; cchMax
0x1800045ba  call    cs:__imp_StringFromGUID2
0x1800045c0  test    eax, eax
0x1800045c2  js      short loc_180004603
0x1800045c4  lea     rax, aOriginalpersis; "OriginalPersistentHandler"
0x1800045cb  mov     [rsp+98h+cbData], 4Eh ; 'N'; cbData
0x1800045d3  neg     ebx
0x1800045d5  mov     r9d, 1; dwType
0x1800045db  mov     rcx, rdi; hKey
0x1800045de  sbb     rdx, rdx
0x1800045e1  xor     r8d, r8d; Reserved
0x1800045e4  and     rdx, rax; lpValueName
0x1800045e7  lea     rax, [rsp+98h+sz]
0x1800045ec  mov     [rsp+98h+lpData], rax; lpData
0x1800045f1  call    cs:__imp_RegSetValueExW
0x1800045f7  test    eax, eax
0x1800045f9  jle     short loc_180004603
0x1800045fb  movzx   eax, ax
0x1800045fe  or      eax, 80070000h
0x180004603  mov     rcx, [rsp+98h+var_18]
0x18000460b  xor     rcx, rsp; StackCookie
0x18000460e  call    __security_check_cookie
0x180004613  mov     rbx, [rsp+98h+arg_10]
0x18000461b  add     rsp, 90h
0x180004622  pop     rdi
0x180004623  retn
```
