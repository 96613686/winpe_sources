# OpenRegKey

- ea: `0x14001727c`
- end: `0x1400172c1`
- name: `OpenRegKey`
- size: `69`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001a078`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400172af`
- `ntoskrnl!ZwOpenKey` at `0x1400172af`

## pseudocode

```c
NTSTATUS __fastcall OpenRegKey(void **a1, struct _UNICODE_STRING *a2)
{
  struct _OBJECT_ATTRIBUTES v3; // [rsp+20h] [rbp-38h] BYREF

  v3.ObjectName = a2;
  *(_QWORD *)&v3.Length = 48;
  v3.RootDirectory = 0;
  *(_QWORD *)&v3.Attributes = 576;
  *(_OWORD *)&v3.SecurityDescriptor = 0;
  return ZwOpenKey(a1, 0x20019u, &v3);
}

```

## disassembly

```asm
0x14001727c  mov     r11, rsp
0x14001727f  sub     rsp, 58h
0x140017283  mov     [r11-28h], rdx
0x140017287  lea     r8, [r11-38h]; ObjectAttributes
0x14001728b  xor     eax, eax
0x14001728d  mov     qword ptr [r11-38h], 30h ; '0'
0x140017295  xorps   xmm0, xmm0
0x140017298  mov     [r11-30h], rax
0x14001729c  mov     qword ptr [r11-20h], 240h
0x1400172a4  mov     edx, 20019h; DesiredAccess
0x1400172a9  movdqu  [rsp+58h+var_18], xmm0
0x1400172af  call    cs:__imp_ZwOpenKey
0x1400172b6  nop     dword ptr [rax+rax+00h]
0x1400172bb  add     rsp, 58h
0x1400172bf  retn
```
