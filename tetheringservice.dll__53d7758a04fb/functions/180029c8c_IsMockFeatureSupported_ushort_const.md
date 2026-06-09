# IsMockFeatureSupported(ushort const *)

- ea: `0x180029c8c`
- end: `0x180029cf8`
- name: `?IsMockFeatureSupported@@YA_NPEBG@Z`
- size: `108`
- prototype: `bool __fastcall(LPCWSTR lpValue)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18002d66c`
- `0x18002dc10`

## callees

- `0x180029c8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029cd2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029cd2`

## string_xrefs

- `0x180029ca3`: `System\CurrentControlSet\Services\IcsSvc\TestHooks`

## pseudocode

```c
bool __fastcall IsMockFeatureSupported(LPCWSTR lpValue)
{
  DWORD v2; // [rsp+58h] [rbp+10h] BYREF
  int v3; // [rsp+60h] [rbp+18h] BYREF

  v3 = 0;
  v2 = 4;
  return (RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\IcsSvc\\TestHooks",
            lpValue,
            0x10u,
            0,
            &v3,
            &v2)
        & 0xFFFFFFFD) == 0
      && v2 == 4
      && v3;
}

```

## disassembly

```asm
0x180029c8c  mov     r11, rsp
0x180029c8f  sub     rsp, 48h
0x180029c93  lea     rax, [r11+10h]
0x180029c97  mov     [rsp+48h+arg_10], 0
0x180029c9f  mov     [r11-18h], rax
0x180029ca3  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ic"...
0x180029caa  lea     rax, [r11+18h]
0x180029cae  mov     [rsp+48h+arg_8], 4
0x180029cb6  mov     r8, rcx; lpValue
0x180029cb9  mov     [r11-20h], rax
0x180029cbd  mov     r9d, 10h; dwFlags
0x180029cc3  mov     qword ptr [r11-28h], 0
0x180029ccb  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180029cd2  call    cs:__imp_RegGetValueW
0x180029cd8  test    eax, 0FFFFFFFDh
0x180029cdd  jnz     short loc_180029CF1
0x180029cdf  cmp     [rsp+48h+arg_8], 4
0x180029ce4  jnz     short loc_180029CF1
0x180029ce6  cmp     [rsp+48h+arg_10], 0
0x180029ceb  jz      short loc_180029CF1
0x180029ced  mov     al, 1
0x180029cef  jmp     short loc_180029CF3
0x180029cf1  xor     al, al
0x180029cf3  add     rsp, 48h
0x180029cf7  retn
```
