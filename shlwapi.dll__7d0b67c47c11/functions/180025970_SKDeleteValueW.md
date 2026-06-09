# SKDeleteValueW

- ea: `0x180025970`
- end: `0x1800259cc`
- name: `SKDeleteValueW`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180005220`
- `0x18000eaf0`
- `0x180025970`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800259a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800259a5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002599a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002599a`

## pseudocode

```c
__int64 __fastcall SKDeleteValueW(int a1, const WCHAR *a2, const WCHAR *a3)
{
  HKEY v4; // rax
  HKEY v5; // rdi
  LSTATUS v6; // ebx

  v4 = SHGetShellKeyEx(a1, a2, 1, 2u);
  v5 = v4;
  if ( !v4 )
    return ResultFromKnownLastError();
  v6 = RegDeleteValueW(v4, a3);
  RegCloseKey(v5);
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180025970  mov     [rsp+arg_0], rbx
0x180025975  push    rdi
0x180025976  sub     rsp, 20h
0x18002597a  mov     r9d, 2
0x180025980  mov     rbx, r8
0x180025983  lea     r8d, [r9-1]
0x180025987  call    SHGetShellKeyEx
0x18002598c  mov     rdi, rax
0x18002598f  test    rax, rax
0x180025992  jz      short loc_1800259BC
0x180025994  mov     rdx, rbx; lpValueName
0x180025997  mov     rcx, rax; hKey
0x18002599a  call    cs:__imp_RegDeleteValueW
0x1800259a0  mov     rcx, rdi; hKey
0x1800259a3  mov     ebx, eax
0x1800259a5  call    cs:__imp_RegCloseKey
0x1800259ab  test    ebx, ebx
0x1800259ad  jle     short loc_1800259B8
0x1800259af  movzx   ebx, bx
0x1800259b2  or      ebx, 80070000h
0x1800259b8  mov     eax, ebx
0x1800259ba  jmp     short loc_1800259C1
0x1800259bc  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800259c1  mov     rbx, [rsp+28h+arg_0]
0x1800259c6  add     rsp, 20h
0x1800259ca  pop     rdi
0x1800259cb  retn
```
