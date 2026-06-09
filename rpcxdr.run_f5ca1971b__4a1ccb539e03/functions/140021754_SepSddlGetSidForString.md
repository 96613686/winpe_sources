# SepSddlGetSidForString

- ea: `0x140021754`
- end: `0x140021805`
- name: `SepSddlGetSidForString`
- size: `177`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140021398`

## callees

- `0x140021754`

## import_xrefs

- `ntoskrnl!IoIsWdmVersionAvailable` at `0x1400217ba`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x1400217ba`
- `ntoskrnl!_wcsnicmp` at `0x14002178e`
- `ntoskrnl!_wcsnicmp` at `0x14002178e`
- `ntoskrnl!SeExports` at `0x1400217d1`

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
    if ( !_wcsnicmp(Str1, (const wchar_t *)&qword_14001A160[3 * i + 1] + 2, HIDWORD(qword_14001A160[3 * i + 2])) )
      break;
  }
  v7 = LODWORD(qword_14001A160[3 * i + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_14001A160[3 * i + 2])];
  if ( !v7 || IoIsWdmVersionAvailable(1u, 0x20u) )
  {
    _mm_lfence();
    v8 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_14001A160[3 * i]);
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
0x140021754  push    rbx
0x140021756  push    rsi
0x140021757  push    rdi
0x140021758  push    r12
0x14002175a  push    r14
0x14002175c  push    r15
0x14002175e  sub     rsp, 28h
0x140021762  mov     r15, r8
0x140021765  lea     r12, qword_14001A160
0x14002176c  mov     rdi, rdx
0x14002176f  mov     r14, rcx
0x140021772  xor     ebx, ebx
0x140021774  cmp     ebx, 0Eh
0x140021777  jnb     short loc_1400217EA
0x140021779  lea     rsi, [rbx+rbx*2]
0x14002177d  mov     rcx, r14; Str1
0x140021780  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x140021785  lea     rdx, [r12+0Ch]
0x14002178a  lea     rdx, [rdx+rsi*8]; Str2
0x14002178e  call    cs:__imp__wcsnicmp
0x140021795  nop     dword ptr [rax+rax+00h]
0x14002179a  test    eax, eax
0x14002179c  jz      short loc_1400217A2
0x14002179e  inc     ebx
0x1400217a0  jmp     short loc_140021774
0x1400217a2  cmp     dword ptr [r12+rsi*8+8], 1
0x1400217a8  mov     eax, [r12+rsi*8+14h]
0x1400217ad  lea     rdx, [r14+rax*2]
0x1400217b1  mov     [r15], rdx
0x1400217b4  jnz     short loc_1400217CE
0x1400217b6  mov     dl, 20h ; ' '; MinorVersion
0x1400217b8  mov     cl, 1; MajorVersion
0x1400217ba  call    cs:__imp_IoIsWdmVersionAvailable
0x1400217c1  nop     dword ptr [rax+rax+00h]
0x1400217c6  test    al, al
0x1400217c8  jnz     short loc_1400217CE
0x1400217ca  xor     eax, eax
0x1400217cc  jmp     short loc_1400217E3
0x1400217ce  lfence
0x1400217d1  mov     rax, cs:__imp_SeExports
0x1400217d8  mov     rdx, [r12+rsi*8]
0x1400217dc  mov     rcx, [rax]
0x1400217df  mov     rax, [rdx+rcx]
0x1400217e3  mov     [rdi], rax
0x1400217e6  xor     eax, eax
0x1400217e8  jmp     short loc_1400217F6
0x1400217ea  mov     qword ptr [rdi], 0
0x1400217f1  mov     eax, 0C0000073h
0x1400217f6  add     rsp, 28h
0x1400217fa  pop     r15
0x1400217fc  pop     r14
0x1400217fe  pop     r12
0x140021800  pop     rdi
0x140021801  pop     rsi
0x140021802  pop     rbx
0x140021803  retn
```
