# BasepSxsMapViewOfSection

- ea: `0x180004900`
- end: `0x18000499f`
- name: `BasepSxsMapViewOfSection`
- size: `159`
- prototype: `__int64 __usercall@<rax>(PVOID *BaseAddress@<rcx>, ULONG_PTR)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004660`

## callees

- `0x180004900`

## import_xrefs

- `ntdll!NtMapViewOfSection` at `0x180004961`
- `ntdll!NtMapViewOfSection` at `0x180004961`

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
0x180004900  mov     [rsp+arg_8], rbx
0x180004905  push    rdi
0x180004906  sub     rsp, 50h
0x18000490a  mov     rax, r8
0x18000490d  movzx   edi, r9w
0x180004911  xor     r8d, r8d
0x180004914  mov     rbx, rcx
0x180004917  mov     [rcx], r8
0x18000491a  test    rdi, rdi
0x18000491d  jnz     short loc_180004982
0x18000491f  mov     [rsp+58h+AccessProtection], 2; AccessProtection
0x180004927  lea     rcx, [rsp+58h+arg_20]
0x18000492f  mov     [rsp+58h+AllocationType], 400000h; AllocationType
0x180004937  mov     [rsp+58h+InheritDisposition], 1; InheritDisposition
0x18000493f  mov     [rsp+58h+ViewSize], rcx; ViewSize
0x180004944  lea     rcx, [rsp+58h+arg_0]
0x180004949  mov     [rsp+58h+SectionOffset], rcx; SectionOffset
0x18000494e  mov     rcx, rax; SectionHandle
0x180004951  mov     [rsp+58h+CommitSize], r8; CommitSize
0x180004956  mov     r8, rbx; BaseAddress
0x180004959  mov     qword ptr [rsp+58h+arg_0], r9
0x18000495e  xor     r9d, r9d; ZeroBits
0x180004961  call    cs:__imp_NtMapViewOfSection
0x180004968  nop     dword ptr [rax+rax+00h]
0x18000496d  test    eax, eax
0x18000496f  jns     short loc_18000497D
0x180004971  mov     rbx, [rsp+58h+arg_8]
0x180004976  add     rsp, 50h
0x18000497a  pop     rdi
0x18000497b  retn
0x18000497d  add     [rbx], rdi
0x180004980  jmp     short loc_180004971
0x180004982  mov     rcx, [rsp+58h+arg_20]
0x18000498a  sub     r9, rdi
0x18000498d  test    rcx, rcx
0x180004990  jz      short loc_18000491F
0x180004992  add     rcx, rdi
0x180004995  mov     [rsp+58h+arg_20], rcx
0x18000499d  jmp     short loc_18000491F
```
