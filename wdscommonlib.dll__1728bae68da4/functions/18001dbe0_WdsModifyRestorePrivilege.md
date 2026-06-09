# WdsModifyRestorePrivilege

- ea: `0x18001dbe0`
- end: `0x18001dc1e`
- name: `WdsModifyRestorePrivilege`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180019aec`
- `0x18001acf0`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18001dbf9`
- `ntdll!RtlAdjustPrivilege` at `0x18001dbf9`

## pseudocode

```c
int __fastcall WdsModifyRestorePrivilege(BOOLEAN a1)
{
  NTSTATUS v1; // ecx
  int result; // eax
  unsigned __int8 OldValue; // [rsp+38h] [rbp+10h] BYREF

  OldValue = 0;
  v1 = RtlAdjustPrivilege(0x12u, a1, 0, &OldValue);
  result = v1 | 0x10000000;
  if ( (v1 & 0xC0000000) != 0xC0000000 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18001dbe0  push    rbx
0x18001dbe2  sub     rsp, 20h
0x18001dbe6  xor     ebx, ebx
0x18001dbe8  lea     r9, [rsp+28h+OldValue]; OldValue
0x18001dbed  mov     dl, cl; NewValue
0x18001dbef  mov     [rsp+28h+OldValue], bl
0x18001dbf3  xor     r8d, r8d; ForThread
0x18001dbf6  lea     ecx, [rbx+12h]; Privilege
0x18001dbf9  call    cs:__imp_RtlAdjustPrivilege
0x18001dc00  nop     dword ptr [rax+rax+00h]
0x18001dc05  mov     ecx, eax
0x18001dc07  mov     edx, 0C0000000h
0x18001dc0c  bts     eax, 1Ch
0x18001dc10  and     ecx, edx
0x18001dc12  cmp     ecx, edx
0x18001dc14  cmovnz  eax, ebx
0x18001dc17  add     rsp, 20h
0x18001dc1b  pop     rbx
0x18001dc1c  retn
```
