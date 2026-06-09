# HrRegDeleteValue(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180031034`
- end: `0x1800310b5`
- name: `?HrRegDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `129`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001acc4`

## callees

- `0x180031034`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180031088`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180031088`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800310a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800310a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031067`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031067`

## pseudocode

```c
__int64 __fastcall HrRegDeleteValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  LSTATUS v4; // eax
  signed int v5; // ebx
  LSTATUS v6; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_CURRENT_USER, a2, 0, 0x20006u, &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    v6 = RegDeleteValueW(hKey, a3);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    RegCloseKey(hKey);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180031034  mov     r11, rsp
0x180031037  mov     [r11+10h], rbx
0x18003103b  mov     [r11+8], rcx
0x18003103f  push    rdi
0x180031040  sub     rsp, 30h
0x180031044  mov     rdi, r8
0x180031047  mov     qword ptr [r11+8], 0
0x18003104f  lea     rax, [r11+8]
0x180031053  xor     r8d, r8d; ulOptions
0x180031056  mov     r9d, 20006h; samDesired
0x18003105c  mov     [r11-18h], rax
0x180031060  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180031067  call    cs:__imp_RegOpenKeyExW
0x18003106d  mov     ebx, eax
0x18003106f  test    eax, eax
0x180031071  jle     short loc_18003107C
0x180031073  movzx   ebx, ax
0x180031076  or      ebx, 80070000h
0x18003107c  test    ebx, ebx
0x18003107e  js      short loc_1800310A8
0x180031080  mov     rcx, [rsp+38h+hKey]; hKey
0x180031085  mov     rdx, rdi; lpValueName
0x180031088  call    cs:__imp_RegDeleteValueW
0x18003108e  mov     ebx, eax
0x180031090  test    eax, eax
0x180031092  jle     short loc_18003109D
0x180031094  movzx   ebx, ax
0x180031097  or      ebx, 80070000h
0x18003109d  mov     rcx, [rsp+38h+hKey]; hKey
0x1800310a2  call    cs:__imp_RegCloseKey
0x1800310a8  mov     eax, ebx
0x1800310aa  mov     rbx, [rsp+38h+arg_8]
0x1800310af  add     rsp, 30h
0x1800310b3  pop     rdi
0x1800310b4  retn
```
