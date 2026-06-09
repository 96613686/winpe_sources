# CMemFileWriter::Close(void)

- ea: `0x383a8a050`
- end: `0x383a8a0f0`
- name: `?Close@CMemFileWriter@@MEAAXXZ`
- size: `160`
- prototype: `void __fastcall(CMemFileWriter *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x383a41710`
- `0x383a41e40`
- `0x383a41f30`
- `0x383a89e50`
- `0x383a89ed0`

## callees

- `0x383a8a050`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x383a8a07c`
- `KERNEL32!CloseHandle` at `0x383a8a0cc`
- `KERNEL32!CloseHandle` at `0x383a8a07c`
- `KERNEL32!CloseHandle` at `0x383a8a0cc`
- `KERNEL32!SetFilePointer` at `0x383a8a09b`
- `KERNEL32!SetFilePointer` at `0x383a8a09b`
- `KERNEL32!UnmapViewOfFile` at `0x383a8a06e`
- `KERNEL32!UnmapViewOfFile` at `0x383a8a06e`
- `KERNEL32!SetEndOfFile` at `0x383a8a0a5`
- `KERNEL32!SetEndOfFile` at `0x383a8a0a5`

## pseudocode

```c
void __fastcall CMemFileWriter::Close(CMemFileWriter *this)
{
  const void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  LONG v5; // edx
  void *v6; // rcx

  if ( *((_QWORD *)this + 5) )
  {
    v2 = (const void *)*((_QWORD *)this + 6);
    if ( v2 )
      UnmapViewOfFile(v2);
    v3 = (void *)*((_QWORD *)this + 5);
    *((_QWORD *)this + 6) = 0;
    CloseHandle(v3);
    v4 = (void *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 8) += *((unsigned int *)this + 18);
    v5 = *((_DWORD *)this + 16);
    *((_QWORD *)this + 5) = 0;
    SetFilePointer(v4, v5, (PLONG)this + 17, 0);
  }
  SetEndOfFile(*((HANDLE *)this + 1));
  v6 = (void *)*((_QWORD *)this + 1);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 8) = -1;
  *((_QWORD *)this + 7) = -1;
  if ( v6 != (void *)-1LL )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 1) = -1;
  }
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 2) = -1;
}

```

## disassembly

```asm
0x383a8a050  mov     [rsp+arg_0], rbx
0x383a8a055  push    rdi
0x383a8a056  sub     rsp, 20h
0x383a8a05a  xor     edi, edi
0x383a8a05c  mov     rbx, rcx
0x383a8a05f  cmp     [rcx+28h], rdi
0x383a8a063  jz      short loc_383A8A0A1
0x383a8a065  mov     rcx, [rcx+30h]; lpBaseAddress
0x383a8a069  test    rcx, rcx
0x383a8a06c  jz      short loc_383A8A074
0x383a8a06e  call    cs:__imp_UnmapViewOfFile
0x383a8a074  mov     rcx, [rbx+28h]; hObject
0x383a8a078  mov     [rbx+30h], rdi
0x383a8a07c  call    cs:__imp_CloseHandle
0x383a8a082  mov     eax, [rbx+48h]
0x383a8a085  mov     rcx, [rbx+8]; hFile
0x383a8a089  add     [rbx+40h], rax
0x383a8a08d  mov     edx, [rbx+40h]; lDistanceToMove
0x383a8a090  lea     r8, [rbx+44h]; lpDistanceToMoveHigh
0x383a8a094  xor     r9d, r9d; dwMoveMethod
0x383a8a097  mov     [rbx+28h], rdi
0x383a8a09b  call    cs:__imp_SetFilePointer
0x383a8a0a1  mov     rcx, [rbx+8]; hFile
0x383a8a0a5  call    cs:__imp_SetEndOfFile
0x383a8a0ab  mov     rcx, [rbx+8]; hObject
0x383a8a0af  mov     [rbx+20h], edi
0x383a8a0b2  mov     [rbx+48h], rdi
0x383a8a0b6  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x383a8a0be  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x383a8a0c6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383a8a0ca  jz      short loc_383A8A0DA
0x383a8a0cc  call    cs:__imp_CloseHandle
0x383a8a0d2  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x383a8a0da  mov     [rbx+18h], edi
0x383a8a0dd  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x383a8a0e5  mov     rbx, [rsp+28h+arg_0]
0x383a8a0ea  add     rsp, 20h
0x383a8a0ee  pop     rdi
0x383a8a0ef  retn
```
