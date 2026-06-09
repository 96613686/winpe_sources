# BasepSxsMapViewOfSection

- ea: `0x180004750`
- end: `0x1800047ef`
- name: `BasepSxsMapViewOfSection`
- size: `159`
- prototype: `NTSTATUS __fastcall(PVOID *BaseAddress, void *, void *, union _LARGE_INTEGER, ULONG_PTR ViewSize)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800044b0`

## callees

- `0x180004750`

## import_xrefs

- `ntdll!NtMapViewOfSection` at `0x1800047b1`
- `ntdll!NtMapViewOfSection` at `0x1800047b1`

## pseudocode

```c
NTSTATUS __fastcall BasepSxsMapViewOfSection(
        PVOID *BaseAddress,
        void *a2,
        void *a3,
        union _LARGE_INTEGER a4,
        ULONG_PTR ViewSize)
{
  __int64 LowPart_low; // rdi
  NTSTATUS result; // eax
  union _LARGE_INTEGER SectionOffset; // [rsp+60h] [rbp+8h] BYREF

  LowPart_low = LOWORD(a4.LowPart);
  *BaseAddress = 0;
  if ( LOWORD(a4.LowPart) )
  {
    a4.QuadPart -= LOWORD(a4.LowPart);
    if ( ViewSize )
      ViewSize += LowPart_low;
  }
  SectionOffset = a4;
  result = NtMapViewOfSection(a3, a2, BaseAddress, 0, 0, &SectionOffset, &ViewSize, ViewShare, 0x400000u, 2u);
  if ( result >= 0 )
    *BaseAddress = (char *)*BaseAddress + LowPart_low;
  return result;
}

```

## disassembly

```asm
0x180004750  mov     [rsp+arg_8], rbx
0x180004755  push    rdi
0x180004756  sub     rsp, 50h
0x18000475a  mov     rax, r8
0x18000475d  movzx   edi, r9w
0x180004761  xor     r8d, r8d
0x180004764  mov     rbx, rcx
0x180004767  mov     [rcx], r8
0x18000476a  test    rdi, rdi
0x18000476d  jnz     short loc_1800047D2
0x18000476f  mov     [rsp+58h+AccessProtection], 2; AccessProtection
0x180004777  lea     rcx, [rsp+58h+arg_20]
0x18000477f  mov     [rsp+58h+AllocationType], 400000h; AllocationType
0x180004787  mov     [rsp+58h+InheritDisposition], 1; InheritDisposition
0x18000478f  mov     [rsp+58h+ViewSize], rcx; ViewSize
0x180004794  lea     rcx, [rsp+58h+arg_0]
0x180004799  mov     [rsp+58h+SectionOffset], rcx; SectionOffset
0x18000479e  mov     rcx, rax; SectionHandle
0x1800047a1  mov     [rsp+58h+CommitSize], r8; CommitSize
0x1800047a6  mov     r8, rbx; BaseAddress
0x1800047a9  mov     qword ptr [rsp+58h+arg_0], r9
0x1800047ae  xor     r9d, r9d; ZeroBits
0x1800047b1  call    cs:__imp_NtMapViewOfSection
0x1800047b8  nop     dword ptr [rax+rax+00h]
0x1800047bd  test    eax, eax
0x1800047bf  jns     short loc_1800047CD
0x1800047c1  mov     rbx, [rsp+58h+arg_8]
0x1800047c6  add     rsp, 50h
0x1800047ca  pop     rdi
0x1800047cb  retn
0x1800047cd  add     [rbx], rdi
0x1800047d0  jmp     short loc_1800047C1
0x1800047d2  mov     rcx, [rsp+58h+arg_20]
0x1800047da  sub     r9, rdi
0x1800047dd  test    rcx, rcx
0x1800047e0  jz      short loc_18000476F
0x1800047e2  add     rcx, rdi
0x1800047e5  mov     [rsp+58h+arg_20], rcx
0x1800047ed  jmp     short loc_18000476F
```
