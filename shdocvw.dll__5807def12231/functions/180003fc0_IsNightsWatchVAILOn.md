# IsNightsWatchVAILOn

- ea: `0x180003fc0`
- end: `0x180004054`
- name: `IsNightsWatchVAILOn`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d120`

## callees

- `0x180003fc0`

## import_xrefs

- `ntdll!NtQuerySecurityPolicy` at `0x180004035`
- `ntdll!NtQuerySecurityPolicy` at `0x180004035`

## pseudocode

```c
_BOOL8 IsNightsWatchVAILOn()
{
  _QWORD v1[2]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v2[2]; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v3[3]; // [rsp+50h] [rbp-18h] BYREF
  char v4; // [rsp+70h] [rbp+8h] BYREF
  int v5; // [rsp+78h] [rbp+10h] BYREF
  int v6; // [rsp+80h] [rbp+18h] BYREF

  v3[0] = 1703960;
  v3[1] = L"VailSettings";
  v2[0] = 1441812;
  v2[1] = L"VAILPolicy";
  v1[0] = 1179664;
  v1[1] = L"Enforced";
  v6 = 0;
  v4 = 0;
  v5 = 1;
  return (int)((__int64 (__fastcall *)(_QWORD *, _QWORD *, _QWORD *, int *, char *, int *))NtQuerySecurityPolicy)(
                v3,
                v2,
                v1,
                &v6,
                &v4,
                &v5) >= 0
      && v4;
}

```

## disassembly

```asm
0x180003fc0  mov     r11, rsp
0x180003fc3  sub     rsp, 68h
0x180003fc7  lea     rax, aVailsettings; "VailSettings"
0x180003fce  mov     qword ptr [r11-18h], 1A0018h
0x180003fd6  mov     [r11-10h], rax
0x180003fda  lea     r9, [r11+18h]
0x180003fde  lea     rax, aVailpolicy; "VAILPolicy"
0x180003fe5  mov     qword ptr [r11-28h], 160014h
0x180003fed  mov     [r11-20h], rax
0x180003ff1  lea     r8, [r11-38h]
0x180003ff5  lea     rax, aEnforced; "Enforced"
0x180003ffc  mov     qword ptr [r11-38h], 120010h
0x180004004  mov     [r11-30h], rax
0x180004008  lea     rdx, [r11-28h]
0x18000400c  lea     rax, [r11+10h]
0x180004010  mov     dword ptr [r11+18h], 0
0x180004018  mov     [r11-40h], rax
0x18000401c  lea     rcx, [r11-18h]
0x180004020  lea     rax, [r11+8]
0x180004024  mov     [rsp+68h+arg_0], 0
0x180004029  mov     [r11-48h], rax
0x18000402d  mov     [rsp+68h+arg_8], 1
0x180004035  call    cs:__imp_NtQuerySecurityPolicy
0x18000403b  test    eax, eax
0x18000403d  js      short loc_18000404D
0x18000403f  cmp     [rsp+68h+arg_0], 0
0x180004044  jz      short loc_18000404D
0x180004046  mov     eax, 1
0x18000404b  jmp     short loc_18000404F
0x18000404d  xor     eax, eax
0x18000404f  add     rsp, 68h
0x180004053  retn
```
