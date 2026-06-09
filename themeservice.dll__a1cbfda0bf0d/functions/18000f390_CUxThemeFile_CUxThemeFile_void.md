# CUxThemeFile::~CUxThemeFile(void)

- ea: `0x18000f390`
- end: `0x18000f3d1`
- name: `??1CUxThemeFile@@QEAA@XZ`
- size: `65`
- prototype: `void __fastcall(CUxThemeFile *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f0a0`

## callees

- `0x180009ea0`
- `0x18000f390`
- `0x18000f5e0`

## string_xrefs

- `0x18000f3b8`: `deleted`

## pseudocode

```c
void __fastcall CUxThemeFile::~CUxThemeFile(CUxThemeFile *this)
{
  if ( *((_QWORD *)this + 1) || *((_QWORD *)this + 2) || *((_QWORD *)this + 3) || *((_QWORD *)this + 4) )
    CUxThemeFile::CloseFile(this);
  StringCchCopyA((char *)this, 8u, "deleted");
}

```

## disassembly

```asm
0x18000f390  push    rbx
0x18000f392  sub     rsp, 20h
0x18000f396  xor     eax, eax
0x18000f398  mov     rbx, rcx
0x18000f39b  cmp     [rcx+8], rax
0x18000f39f  jnz     short loc_18000F3B3
0x18000f3a1  cmp     [rcx+10h], rax
0x18000f3a5  jnz     short loc_18000F3B3
0x18000f3a7  cmp     [rcx+18h], rax
0x18000f3ab  jnz     short loc_18000F3B3
0x18000f3ad  cmp     [rcx+20h], rax
0x18000f3b1  jz      short loc_18000F3B8
0x18000f3b3  call    ?CloseFile@CUxThemeFile@@QEAAXXZ; CUxThemeFile::CloseFile(void)
0x18000f3b8  lea     r8, aDeleted; "deleted"
0x18000f3bf  mov     edx, 8; unsigned __int64
0x18000f3c4  mov     rcx, rbx; char *
0x18000f3c7  add     rsp, 20h
0x18000f3cb  pop     rbx
0x18000f3cc  jmp     ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
```
