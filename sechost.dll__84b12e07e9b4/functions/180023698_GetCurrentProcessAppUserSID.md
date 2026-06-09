# GetCurrentProcessAppUserSID

- ea: `0x180023698`
- end: `0x180023705`
- name: `GetCurrentProcessAppUserSID`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180017ce0`

## callees

- `0x180018a7c`
- `0x180023698`

## import_xrefs

- `ntdll!NtClose` at `0x1800236ed`
- `ntdll!NtClose` at `0x1800236ed`
- `ntdll!NtOpenProcessTokenEx` at `0x1800236c5`
- `ntdll!NtOpenProcessTokenEx` at `0x1800236c5`

## pseudocode

```c
__int64 __fastcall GetCurrentProcessAppUserSID(_QWORD *a1, _QWORD *a2)
{
  unsigned int AppUserSID; // ebx
  HANDLE Handle; // [rsp+40h] [rbp+18h] BYREF

  Handle = 0;
  AppUserSID = NtOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0, &Handle);
  if ( !AppUserSID )
    AppUserSID = GetAppUserSID(Handle, a1, a2);
  if ( Handle )
    NtClose(Handle);
  return AppUserSID;
}

```

## disassembly

```asm
0x180023698  mov     rax, rsp
0x18002369b  mov     [rax+8], rbx
0x18002369f  mov     [rax+10h], rsi
0x1800236a3  push    rdi
0x1800236a4  sub     rsp, 20h
0x1800236a8  xor     r8d, r8d; HandleAttributes
0x1800236ab  mov     qword ptr [rax+18h], 0
0x1800236b3  mov     rdi, rdx
0x1800236b6  lea     r9, [rax+18h]; TokenHandle
0x1800236ba  mov     rsi, rcx
0x1800236bd  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800236c1  lea     edx, [r8+8]; DesiredAccess
0x1800236c5  call    cs:__imp_NtOpenProcessTokenEx
0x1800236cb  mov     ebx, eax
0x1800236cd  test    eax, eax
0x1800236cf  jnz     short loc_1800236E3
0x1800236d1  mov     rcx, [rsp+28h+Handle]; TokenHandle
0x1800236d6  mov     r8, rdi
0x1800236d9  mov     rdx, rsi
0x1800236dc  call    GetAppUserSID
0x1800236e1  mov     ebx, eax
0x1800236e3  mov     rcx, [rsp+28h+Handle]; Handle
0x1800236e8  test    rcx, rcx
0x1800236eb  jz      short loc_1800236F3
0x1800236ed  call    cs:__imp_NtClose
0x1800236f3  mov     rsi, [rsp+28h+arg_8]
0x1800236f8  mov     eax, ebx
0x1800236fa  mov     rbx, [rsp+28h+arg_0]
0x1800236ff  add     rsp, 20h
0x180023703  pop     rdi
0x180023704  retn
```
