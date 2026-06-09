# SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x18001987c`
- end: `0x180019955`
- name: `?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `217`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `12`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180008a50`
- `0x1800197c8`
- `0x18001b43c`
- `0x18001e3ec`
- `0x18001e5d0`
- `0x18001edb4`
- `0x180022534`
- `0x180032754`
- `0x18003336c`
- `0x1800423d0`
- `0x180042470`
- `0x18004fb2c`

## callees

- `0x18001987c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001993f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001993f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800198e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800198e9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800198d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800198d7`

## pseudocode

```c
__int64 __fastcall SHRegSetString(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, const BYTE *a4)
{
  unsigned __int64 v4; // rdi
  HKEY v7; // rsi
  LSTATUS v8; // ebx
  HKEY hKey; // [rsp+50h] [rbp-48h] BYREF

  v4 = -1;
  v7 = a1;
  do
    ++v4;
  while ( *(_WORD *)&a4[2 * v4] );
  if ( v4 >= 0x7FFFFFFF )
  {
    LOWORD(v8) = 534;
    return (unsigned __int16)v8 | 0x80070000;
  }
  hKey = 0;
  if ( a2 && *a2 )
  {
    v8 = RegCreateKeyExW(a1, a2, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v8 )
      goto LABEL_8;
    a1 = hKey;
  }
  else
  {
    hKey = a1;
  }
  v8 = RegSetValueExW(a1, a3, 0, 1u, a4, 2 * v4 + 2);
  if ( hKey != v7 )
    RegCloseKey(hKey);
LABEL_8:
  if ( v8 > 0 )
    return (unsigned __int16)v8 | 0x80070000;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001987c  push    rbx
0x18001987e  push    rbp
0x18001987f  push    rsi
0x180019880  push    rdi
0x180019881  push    r14
0x180019883  push    r15
0x180019885  sub     rsp, 68h
0x180019889  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001988d  mov     rbp, r9
0x180019890  xor     r15d, r15d
0x180019893  mov     r14, r8
0x180019896  mov     rsi, rcx
0x180019899  inc     rdi
0x18001989c  cmp     [r9+rdi*2], r15w
0x1800198a1  jnz     short loc_180019899
0x1800198a3  cmp     rdi, 7FFFFFFFh
0x1800198aa  jnb     short loc_18001990B
0x1800198ac  mov     [rsp+98h+hKey], r15
0x1800198b1  test    rdx, rdx
0x1800198b4  jnz     short loc_180019912
0x1800198b6  mov     [rsp+98h+hKey], rcx
0x1800198bb  lea     eax, ds:2[rdi*2]
0x1800198c2  mov     r9d, 1; dwType
0x1800198c8  mov     [rsp+98h+cbData], eax; cbData
0x1800198cc  xor     r8d, r8d; Reserved
0x1800198cf  mov     rdx, r14; lpValueName
0x1800198d2  mov     [rsp+98h+lpData], rbp; lpData
0x1800198d7  call    cs:__imp_RegSetValueExW
0x1800198dd  mov     rcx, [rsp+98h+hKey]; hKey
0x1800198e2  mov     ebx, eax
0x1800198e4  cmp     rcx, rsi
0x1800198e7  jz      short loc_1800198EF
0x1800198e9  call    cs:__imp_RegCloseKey
0x1800198ef  test    ebx, ebx
0x1800198f1  jle     short loc_1800198FC
0x1800198f3  movzx   ebx, bx
0x1800198f6  or      ebx, 80070000h
0x1800198fc  mov     eax, ebx
0x1800198fe  add     rsp, 68h
0x180019902  pop     r15
0x180019904  pop     r14
0x180019906  pop     rdi
0x180019907  pop     rsi
0x180019908  pop     rbp
0x180019909  pop     rbx
0x18001990a  retn
0x18001990b  mov     ebx, 216h
0x180019910  jmp     short loc_1800198F3
0x180019912  cmp     [rdx], r15w
0x180019916  jz      short loc_1800198B6
0x180019918  mov     [rsp+98h+lpdwDisposition], r15; lpdwDisposition
0x18001991d  lea     rax, [rsp+98h+hKey]
0x180019922  mov     [rsp+98h+phkResult], rax; phkResult
0x180019927  xor     r9d, r9d; lpClass
0x18001992a  mov     [rsp+98h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18001992f  xor     r8d, r8d; Reserved
0x180019932  mov     [rsp+98h+cbData], 2; samDesired
0x18001993a  mov     dword ptr [rsp+98h+lpData], r15d; dwOptions
0x18001993f  call    cs:__imp_RegCreateKeyExW
0x180019945  mov     ebx, eax
0x180019947  test    eax, eax
0x180019949  jnz     short loc_1800198EF
0x18001994b  mov     rcx, [rsp+98h+hKey]
0x180019950  jmp     loc_1800198BB
```
