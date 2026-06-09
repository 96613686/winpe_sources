# SmpQueryDwordFromRegistry

- ea: `0x140011fe8`
- end: `0x140012070`
- name: `SmpQueryDwordFromRegistry`
- size: `136`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140010dc8`
- `0x140011c50`

## callees

- `0x140011fe8`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x140012036`
- `ntdll!NtQueryValueKey` at `0x140012036`

## pseudocode

```c
__int64 __fastcall SmpQueryDwordFromRegistry(__int64 a1, struct _UNICODE_STRING *a2, int a3, _DWORD *a4)
{
  ULONG ResultLength[4]; // [rsp+30h] [rbp-238h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+40h] [rbp-228h] BYREF
  int v9; // [rsp+44h] [rbp-224h]
  int v10; // [rsp+4Ch] [rbp-21Ch]

  ResultLength[0] = 528;
  if ( NtQueryValueKey(SmpCrashDumpKey, a2, KeyValuePartialInformation, KeyValueInformation, 0x210u, ResultLength) >= 0
    && v9 == 4 )
  {
    a3 = v10;
  }
  *a4 = a3;
  return 0;
}

```

## disassembly

```asm
0x140011fe8  mov     [rsp+arg_0], rbx
0x140011fed  push    rdi
0x140011fee  sub     rsp, 260h
0x140011ff5  mov     rax, cs:__security_cookie
0x140011ffc  xor     rax, rsp
0x140011fff  mov     [rsp+268h+var_18], rax
0x140012007  mov     ecx, 210h
0x14001200c  lea     rax, [rsp+268h+var_238]
0x140012011  mov     [rsp+268h+ResultLength], rax; ResultLength
0x140012016  mov     rdi, r9
0x140012019  mov     [rsp+268h+Length], ecx; Length
0x14001201d  lea     r9, [rsp+268h+KeyValueInformation]; KeyValueInformation
0x140012022  mov     ebx, r8d
0x140012025  mov     [rsp+268h+var_238], ecx
0x140012029  mov     rcx, cs:SmpCrashDumpKey; KeyHandle
0x140012030  mov     r8d, 2; KeyValueInformationClass
0x140012036  call    cs:__imp_NtQueryValueKey
0x14001203c  test    eax, eax
0x14001203e  js      short loc_14001204B
0x140012040  cmp     [rsp+268h+var_224], 4
0x140012045  jnz     short loc_14001204B
0x140012047  mov     ebx, [rsp+268h+var_21C]
0x14001204b  mov     [rdi], ebx
0x14001204d  xor     eax, eax
0x14001204f  mov     rcx, [rsp+268h+var_18]
0x140012057  xor     rcx, rsp; StackCookie
0x14001205a  call    __security_check_cookie
0x14001205f  mov     rbx, [rsp+268h+arg_0]
0x140012067  add     rsp, 260h
0x14001206e  pop     rdi
0x14001206f  retn
```
