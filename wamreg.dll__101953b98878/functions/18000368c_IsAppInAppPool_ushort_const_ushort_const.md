# IsAppInAppPool(ushort const *,ushort const *)

- ea: `0x18000368c`
- end: `0x1800036eb`
- name: `?IsAppInAppPool@@YAHPEBG0@Z`
- size: `95`
- prototype: `__int64 __fastcall(const unsigned __int16 *, wchar_t *String2)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1800030b0`

## callees

- `0x180001084`
- `0x18000368c`
- `0x180005f74`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800036c6`
- `msvcrt!_wcsicmp` at `0x1800036c6`

## pseudocode

```c
_BOOL8 __fastcall IsAppInAppPool(WamRegMetabaseConfig *a1, wchar_t *String2)
{
  BOOL v3; // ebx
  wchar_t *String1; // [rsp+40h] [rbp+18h] BYREF

  v3 = 0;
  String1 = 0;
  if ( (int)WamRegMetabaseConfig::MDGetStringAttribute(a1, (const unsigned __int16 *)a1, 9101, &String1) >= 0 && String1 )
    v3 = _wcsicmp(String1, String2) == 0;
  operator delete(String1);
  return v3;
}

```

## disassembly

```asm
0x18000368c  mov     [rsp+arg_0], rbx
0x180003691  push    rsi
0x180003692  sub     rsp, 20h
0x180003696  mov     rsi, rdx
0x180003699  lea     r9, [rsp+28h+String1]; unsigned __int16 **
0x18000369e  xor     ebx, ebx
0x1800036a0  mov     rdx, rcx; unsigned __int16 *
0x1800036a3  mov     r8d, 238Dh; unsigned int
0x1800036a9  mov     [rsp+28h+String1], rbx
0x1800036ae  call    ?MDGetStringAttribute@WamRegMetabaseConfig@@QEAAJPEBGKPEAPEAG@Z; WamRegMetabaseConfig::MDGetStringAttribute(ushort const *,ulong,ushort * *)
0x1800036b3  test    eax, eax
0x1800036b5  js      short loc_1800036D4
0x1800036b7  cmp     [rsp+28h+String1], rbx
0x1800036bc  jz      short loc_1800036D4
0x1800036be  mov     rcx, [rsp+28h+String1]; String1
0x1800036c3  mov     rdx, rsi; String2
0x1800036c6  call    cs:__imp__wcsicmp
0x1800036cc  test    eax, eax
0x1800036ce  lea     ecx, [rbx+1]
0x1800036d1  cmovz   ebx, ecx
0x1800036d4  mov     rcx, [rsp+28h+String1]; Block
0x1800036d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800036de  mov     eax, ebx
0x1800036e0  mov     rbx, [rsp+28h+arg_0]
0x1800036e5  add     rsp, 20h
0x1800036e9  pop     rsi
0x1800036ea  retn
```
