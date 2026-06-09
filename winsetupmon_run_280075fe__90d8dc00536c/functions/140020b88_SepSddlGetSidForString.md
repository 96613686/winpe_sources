# SepSddlGetSidForString

- ea: `0x140020b88`
- end: `0x140020c34`
- name: `SepSddlGetSidForString`
- size: `172`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400207c8`

## callees

- `0x140020b88`

## import_xrefs

- `ntoskrnl!IoIsWdmVersionAvailable` at `0x140020bfa`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x140020bfa`
- `ntoskrnl!_wcsnicmp` at `0x140020bbd`
- `ntoskrnl!_wcsnicmp` at `0x140020bbd`
- `ntoskrnl!SeExports` at `0x140020c0e`

## pseudocode

```c
__int64 __fastcall SepSddlGetSidForString(wchar_t *Str1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rbx
  bool v8; // zf
  __int64 v9; // rax

  v6 = 0;
  while ( _wcsnicmp(Str1, (const wchar_t *)&qword_140019180[3 * v6 + 1] + 2, HIDWORD(qword_140019180[3 * v6 + 2])) )
  {
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= 0xE )
    {
      *a2 = 0;
      return 3221225587LL;
    }
  }
  v8 = LODWORD(qword_140019180[3 * v6 + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_140019180[3 * v6 + 2])];
  if ( !v8 || IoIsWdmVersionAvailable(1u, 0x20u) )
    v9 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_140019180[3 * v6]);
  else
    v9 = 0;
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x140020b88  push    rbx
0x140020b8a  push    rsi
0x140020b8b  push    rdi
0x140020b8c  push    r12
0x140020b8e  push    r14
0x140020b90  push    r15
0x140020b92  sub     rsp, 28h
0x140020b96  mov     r15, r8
0x140020b99  lea     r12, qword_140019180
0x140020ba0  mov     rdi, rdx
0x140020ba3  mov     r14, rcx
0x140020ba6  xor     ebx, ebx
0x140020ba8  lea     rsi, [rbx+rbx*2]
0x140020bac  mov     rcx, r14; Str1
0x140020baf  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x140020bb4  lea     rdx, [r12+0Ch]
0x140020bb9  lea     rdx, [rdx+rsi*8]; Str2
0x140020bbd  call    cs:__imp__wcsnicmp
0x140020bc4  nop     dword ptr [rax+rax+00h]
0x140020bc9  test    eax, eax
0x140020bcb  jz      short loc_140020BE2
0x140020bcd  inc     ebx
0x140020bcf  cmp     ebx, 0Eh
0x140020bd2  jb      short loc_140020BA8
0x140020bd4  mov     qword ptr [rdi], 0
0x140020bdb  mov     eax, 0C0000073h
0x140020be0  jmp     short loc_140020C25
0x140020be2  cmp     dword ptr [r12+rsi*8+8], 1
0x140020be8  mov     eax, [r12+rsi*8+14h]
0x140020bed  lea     rdx, [r14+rax*2]
0x140020bf1  mov     [r15], rdx
0x140020bf4  jnz     short loc_140020C0E
0x140020bf6  mov     dl, 20h ; ' '; MinorVersion
0x140020bf8  mov     cl, 1; MajorVersion
0x140020bfa  call    cs:__imp_IoIsWdmVersionAvailable
0x140020c01  nop     dword ptr [rax+rax+00h]
0x140020c06  test    al, al
0x140020c08  jnz     short loc_140020C0E
0x140020c0a  xor     eax, eax
0x140020c0c  jmp     short loc_140020C20
0x140020c0e  mov     rax, cs:__imp_SeExports
0x140020c15  mov     rdx, [r12+rsi*8]
0x140020c19  mov     rcx, [rax]
0x140020c1c  mov     rax, [rdx+rcx]
0x140020c20  mov     [rdi], rax
0x140020c23  xor     eax, eax
0x140020c25  add     rsp, 28h
0x140020c29  pop     r15
0x140020c2b  pop     r14
0x140020c2d  pop     r12
0x140020c2f  pop     rdi
0x140020c30  pop     rsi
0x140020c31  pop     rbx
0x140020c32  retn
```
