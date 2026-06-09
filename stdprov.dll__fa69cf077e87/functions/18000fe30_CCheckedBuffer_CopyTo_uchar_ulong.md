# CCheckedBuffer::CopyTo(uchar *,ulong)

- ea: `0x18000fe30`
- end: `0x18000fe61`
- name: `?CopyTo@CCheckedBuffer@@QEAA_NPEAEK@Z`
- size: `49`
- prototype: `char __fastcall(CCheckedBuffer *this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800101d4`

## callees

- `0x18000fe30`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000fe50`
- `msvcrt!memmove_s` at `0x18000fe50`

## pseudocode

```c
char __fastcall CCheckedBuffer::CopyTo(CCheckedBuffer *this, unsigned __int8 *a2, unsigned int a3)
{
  if ( *((_BYTE *)this + 24) || *((_DWORD *)this + 5) < a3 )
    return 0;
  memmove_s(a2, a3, *((const void *const *)this + 1), a3);
  return 1;
}

```

## disassembly

```asm
0x18000fe30  sub     rsp, 28h
0x18000fe34  cmp     byte ptr [rcx+18h], 0
0x18000fe38  mov     rax, rdx
0x18000fe3b  jnz     short loc_18000FE5A
0x18000fe3d  cmp     [rcx+14h], r8d
0x18000fe41  jb      short loc_18000FE5A
0x18000fe43  mov     edx, r8d; DestinationSize
0x18000fe46  mov     r9d, r8d; SourceSize
0x18000fe49  mov     r8, [rcx+8]; Source
0x18000fe4d  mov     rcx, rax; Destination
0x18000fe50  call    cs:__imp_memmove_s
0x18000fe56  mov     al, 1
0x18000fe58  jmp     short loc_18000FE5C
0x18000fe5a  xor     al, al
0x18000fe5c  add     rsp, 28h
0x18000fe60  retn
```
