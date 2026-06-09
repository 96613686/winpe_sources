# SclOpenKey

- ea: `0x1800025ec`
- end: `0x180002637`
- name: `SclOpenKey`
- size: `75`
- prototype: `NTSTATUS __fastcall(void *, struct _UNICODE_STRING *, ACCESS_MASK, int, void **KeyHandle)`
- caller_count: `3`
- callee_count: `0`
- tags: `reparse_path, loader_planting`

## callers

- `0x18000548c`
- `0x180009cd0`
- `0x18000b21c`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18000262c`
- `ntdll!NtOpenKey` at `0x18000262c`

## pseudocode

```c
NTSTATUS __fastcall SclOpenKey(void *a1, struct _UNICODE_STRING *a2, ACCESS_MASK a3, int a4, void **KeyHandle)
{
  struct _OBJECT_ATTRIBUTES v6; // [rsp+20h] [rbp-38h] BYREF

  v6.RootDirectory = a1;
  memset(&v6.Attributes + 1, 0, 20);
  v6.ObjectName = a2;
  *(_QWORD *)&v6.Length = 48;
  v6.Attributes = a4 | 0x40;
  return NtOpenKey(KeyHandle, a3, &v6);
}

```

## disassembly

```asm
0x1800025ec  mov     r11, rsp
0x1800025ef  sub     rsp, 58h
0x1800025f3  mov     eax, r8d
0x1800025f6  mov     [r11-30h], rcx
0x1800025fa  mov     rcx, [rsp+58h+KeyHandle]; KeyHandle
0x180002602  xor     r8d, r8d
0x180002605  mov     [r11-1Ch], r8d
0x180002609  or      r9d, 40h
0x18000260d  mov     [r11-28h], rdx
0x180002611  lea     r8, [r11-38h]; ObjectAttributes
0x180002615  xorps   xmm0, xmm0
0x180002618  mov     qword ptr [r11-38h], 30h ; '0'
0x180002620  mov     [r11-20h], r9d
0x180002624  mov     edx, eax; DesiredAccess
0x180002626  movdqu  [rsp+58h+var_18], xmm0
0x18000262c  call    cs:__imp_NtOpenKey
0x180002632  add     rsp, 58h
0x180002636  retn
```
