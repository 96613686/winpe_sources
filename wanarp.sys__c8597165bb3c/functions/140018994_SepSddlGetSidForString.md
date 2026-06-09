# SepSddlGetSidForString

- ea: `0x140018994`
- end: `0x140018a45`
- name: `SepSddlGetSidForString`
- size: `177`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400185d8`

## callees

- `0x140018994`

## import_xrefs

- `ntoskrnl!SeExports` at `0x140018a11`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x1400189fa`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x1400189fa`
- `ntoskrnl!_wcsnicmp` at `0x1400189ce`
- `ntoskrnl!_wcsnicmp` at `0x1400189ce`

## pseudocode

```c
__int64 __fastcall SepSddlGetSidForString(wchar_t *Str1, _QWORD *a2, _QWORD *a3)
{
  __int64 i; // rbx
  bool v7; // zf
  __int64 v8; // rax

  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 0xE )
    {
      *a2 = 0;
      return 3221225587LL;
    }
    if ( !_wcsnicmp(Str1, (const wchar_t *)&qword_140009570[3 * i + 1] + 2, HIDWORD(qword_140009570[3 * i + 2])) )
      break;
  }
  v7 = LODWORD(qword_140009570[3 * i + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_140009570[3 * i + 2])];
  if ( !v7 || IoIsWdmVersionAvailable(1u, 0x20u) )
  {
    _mm_lfence();
    v8 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_140009570[3 * i]);
  }
  else
  {
    v8 = 0;
  }
  *a2 = v8;
  return 0;
}

```

## disassembly

```asm
0x140018994  push    rbx
0x140018996  push    rsi
0x140018997  push    rdi
0x140018998  push    r12
0x14001899a  push    r14
0x14001899c  push    r15
0x14001899e  sub     rsp, 28h
0x1400189a2  mov     r15, r8
0x1400189a5  lea     r12, qword_140009570
0x1400189ac  mov     rdi, rdx
0x1400189af  mov     r14, rcx
0x1400189b2  xor     ebx, ebx
0x1400189b4  cmp     ebx, 0Eh
0x1400189b7  jnb     short loc_140018A2A
0x1400189b9  lea     rsi, [rbx+rbx*2]
0x1400189bd  mov     rcx, r14; Str1
0x1400189c0  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x1400189c5  lea     rdx, [r12+0Ch]
0x1400189ca  lea     rdx, [rdx+rsi*8]; Str2
0x1400189ce  call    cs:__imp__wcsnicmp
0x1400189d5  nop     dword ptr [rax+rax+00h]
0x1400189da  test    eax, eax
0x1400189dc  jz      short loc_1400189E2
0x1400189de  inc     ebx
0x1400189e0  jmp     short loc_1400189B4
0x1400189e2  cmp     dword ptr [r12+rsi*8+8], 1
0x1400189e8  mov     eax, [r12+rsi*8+14h]
0x1400189ed  lea     rdx, [r14+rax*2]
0x1400189f1  mov     [r15], rdx
0x1400189f4  jnz     short loc_140018A0E
0x1400189f6  mov     dl, 20h ; ' '; MinorVersion
0x1400189f8  mov     cl, 1; MajorVersion
0x1400189fa  call    cs:__imp_IoIsWdmVersionAvailable
0x140018a01  nop     dword ptr [rax+rax+00h]
0x140018a06  test    al, al
0x140018a08  jnz     short loc_140018A0E
0x140018a0a  xor     eax, eax
0x140018a0c  jmp     short loc_140018A23
0x140018a0e  lfence
0x140018a11  mov     rax, cs:__imp_SeExports
0x140018a18  mov     rdx, [r12+rsi*8]
0x140018a1c  mov     rcx, [rax]
0x140018a1f  mov     rax, [rdx+rcx]
0x140018a23  mov     [rdi], rax
0x140018a26  xor     eax, eax
0x140018a28  jmp     short loc_140018A36
0x140018a2a  mov     qword ptr [rdi], 0
0x140018a31  mov     eax, 0C0000073h
0x140018a36  add     rsp, 28h
0x140018a3a  pop     r15
0x140018a3c  pop     r14
0x140018a3e  pop     r12
0x140018a40  pop     rdi
0x140018a41  pop     rsi
0x140018a42  pop     rbx
0x140018a43  retn
```
