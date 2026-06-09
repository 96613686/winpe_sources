# SetRegStringValW(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x18005fbec`
- end: `0x18005fcb6`
- name: `?SetRegStringValW@@YAHPEAUHKEY__@@PEBG11@Z`
- size: `202`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180056b10`

## callees

- `0x180001c00`
- `0x18005fbec`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18005fc8f`
- `ADVAPI32!RegCloseKey` at `0x18005fc8f`
- `ADVAPI32!RegCreateKeyExW` at `0x18005fc41`
- `ADVAPI32!RegCreateKeyExW` at `0x18005fc41`
- `ADVAPI32!RegSetValueExW` at `0x18005fc7d`
- `ADVAPI32!RegSetValueExW` at `0x18005fc7d`

## string_xrefs

- `0x18005fc11`: `IO\Writer`
- `0x18005fc68`: `DVRDirectory`

## pseudocode

```c
_BOOL8 __fastcall SetRegStringValW(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, const BYTE *a4)
{
  __int64 v5; // rax
  BOOL v6; // ebx
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  DWORD v9; // [rsp+58h] [rbp-20h] BYREF

  hKey = 0;
  v9 = 0;
  if ( RegCreateKeyExW(a1, L"IO\\Writer", 0, 0, 0, 0x20006u, 0, &hKey, &v9) )
  {
    return 0;
  }
  else
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)&a4[2 * v5] );
    v6 = RegSetValueExW(hKey, L"DVRDirectory", 0, 1u, a4, 2 * v5 + 2) == 0;
    RegCloseKey(hKey);
  }
  return v6;
}

```

## disassembly

```asm
0x18005fbec  mov     r11, rsp
0x18005fbef  mov     [r11+10h], rbx
0x18005fbf3  push    rdi
0x18005fbf4  sub     rsp, 70h
0x18005fbf8  mov     rax, cs:__security_cookie
0x18005fbff  xor     rax, rsp
0x18005fc02  mov     [rsp+78h+var_18], rax
0x18005fc07  xor     edi, edi
0x18005fc09  lea     rax, [r11-20h]
0x18005fc0d  mov     [r11-38h], rax
0x18005fc11  lea     rdx, aIoWriter; "IO\\Writer"
0x18005fc18  lea     rax, [r11-28h]
0x18005fc1c  mov     [r11-28h], rdi
0x18005fc20  mov     [r11-40h], rax
0x18005fc24  mov     rbx, r9
0x18005fc27  mov     [r11-48h], rdi
0x18005fc2b  xor     r9d, r9d; lpClass
0x18005fc2e  mov     [rsp+78h+samDesired], 20006h; samDesired
0x18005fc36  xor     r8d, r8d; Reserved
0x18005fc39  mov     [rsp+78h+dwOptions], edi; dwOptions
0x18005fc3d  mov     [rsp+78h+var_20], edi
0x18005fc41  call    cs:__imp_RegCreateKeyExW
0x18005fc47  test    eax, eax
0x18005fc49  jnz     short loc_18005FC97
0x18005fc4b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005fc4f  inc     rax
0x18005fc52  cmp     [rbx+rax*2], di
0x18005fc56  jnz     short loc_18005FC4F
0x18005fc58  mov     rcx, [rsp+78h+hKey]; hKey
0x18005fc5d  lea     eax, ds:2[rax*2]
0x18005fc64  mov     [rsp+78h+samDesired], eax; cbData
0x18005fc68  lea     rdx, aDvrdirectory; "DVRDirectory"
0x18005fc6f  mov     r9d, 1; dwType
0x18005fc75  mov     qword ptr [rsp+78h+dwOptions], rbx; lpData
0x18005fc7a  xor     r8d, r8d; Reserved
0x18005fc7d  call    cs:__imp_RegSetValueExW
0x18005fc83  mov     rcx, [rsp+78h+hKey]; hKey
0x18005fc88  mov     ebx, edi
0x18005fc8a  test    eax, eax
0x18005fc8c  setz    bl
0x18005fc8f  call    cs:__imp_RegCloseKey
0x18005fc95  jmp     short loc_18005FC99
0x18005fc97  mov     ebx, edi
0x18005fc99  mov     eax, ebx
0x18005fc9b  mov     rcx, [rsp+78h+var_18]
0x18005fca0  xor     rcx, rsp; StackCookie
0x18005fca3  call    __security_check_cookie
0x18005fca8  mov     rbx, [rsp+78h+arg_8]
0x18005fcb0  add     rsp, 70h
0x18005fcb4  pop     rdi
0x18005fcb5  retn
```
