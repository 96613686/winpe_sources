# CleanUpErrorString(ushort *)

- ea: `0x180013dd8`
- end: `0x180013e30`
- name: `?CleanUpErrorString@@YAJPEAG@Z`
- size: `88`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180013ec4`
- `0x18001473c`

## callees

- `0x180013dd8`

## import_xrefs

- `SHLWAPI!PathRemoveBlanksW` at `0x180013de1`
- `SHLWAPI!PathRemoveBlanksW` at `0x180013de1`

## pseudocode

```c
__int64 __fastcall CleanUpErrorString(unsigned __int16 *a1)
{
  __int64 v2; // rax
  __int64 v3; // rcx

  PathRemoveBlanksW(a1);
  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  while ( (_DWORD)v2 )
  {
    v3 = (unsigned int)(v2 - 1);
    if ( a1[v3] != 10 && a1[v3] != 13 )
      break;
    a1[v3] = 0;
    v2 = -1;
    do
      ++v2;
    while ( a1[v2] );
  }
  return 0;
}

```

## disassembly

```asm
0x180013dd8  push    rbx
0x180013dda  sub     rsp, 20h
0x180013dde  mov     rbx, rcx
0x180013de1  call    cs:__imp_PathRemoveBlanksW
0x180013de7  or      r8, 0FFFFFFFFFFFFFFFFh
0x180013deb  mov     rax, r8
0x180013dee  xor     edx, edx
0x180013df0  inc     rax
0x180013df3  cmp     [rbx+rax*2], dx
0x180013df7  jnz     short loc_180013DF0
0x180013df9  jmp     short loc_180013E24
0x180013dfb  lea     ecx, [rax-1]
0x180013dfe  mov     eax, 0Ah
0x180013e03  cmp     ax, [rbx+rcx*2]
0x180013e07  jz      short loc_180013E14
0x180013e09  mov     eax, 0Dh
0x180013e0e  cmp     ax, [rbx+rcx*2]
0x180013e12  jnz     short loc_180013E28
0x180013e14  mov     [rbx+rcx*2], dx
0x180013e18  mov     rax, r8
0x180013e1b  inc     rax
0x180013e1e  cmp     [rbx+rax*2], dx
0x180013e22  jnz     short loc_180013E1B
0x180013e24  test    eax, eax
0x180013e26  jnz     short loc_180013DFB
0x180013e28  xor     eax, eax
0x180013e2a  add     rsp, 20h
0x180013e2e  pop     rbx
0x180013e2f  retn
```
