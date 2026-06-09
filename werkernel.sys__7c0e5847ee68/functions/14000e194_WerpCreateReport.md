# WerpCreateReport

- ea: `0x14000e194`
- end: `0x14000e259`
- name: `WerpCreateReport`
- size: `197`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000c6f0`

## callees

- `0x14000e194`
- `0x14000e464`
- `0x14000e83c`
- `0x14000f8bc`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000e1e2`
- `ntoskrnl!DbgPrintEx` at `0x14000e1e2`

## pseudocode

```c
__int64 __fastcall WerpCreateReport(int a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  __int64 result; // rax

  if ( !a2 || !a3 || !a4 || !a1 )
    return 3221225485LL;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(a2 + 2 * v10) );
  if ( v10 >= 0x10 )
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: Key key length exceeded\n");
    return 3221225485LL;
  }
  do
    ++v9;
  while ( *(_WORD *)(a3 + 2 * v9) );
  if ( v9 >= 0x28 )
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: Key id length exceeded\n");
    return 3221225485LL;
  }
  if ( !WerKernelLiveReportInitialized )
    return 3221225474LL;
  result = WerpRefreshRootPath(v10, 0);
  if ( a1 == 1 )
    return WerpCreateReportMini(a2, a3, a4);
  if ( a1 == 2 )
    return WerpCreateReportFull(a2, a3, a4, a5);
  return result;
}

```

## disassembly

```asm
0x14000e194  push    rbx
0x14000e196  push    rbp
0x14000e197  push    rsi
0x14000e198  push    rdi
0x14000e199  sub     rsp, 28h
0x14000e19d  mov     rsi, rdx
0x14000e1a0  mov     rbp, r9
0x14000e1a3  xor     edx, edx
0x14000e1a5  mov     rdi, r8
0x14000e1a8  mov     ebx, ecx
0x14000e1aa  test    rsi, rsi
0x14000e1ad  jz      short loc_14000E1EE
0x14000e1af  test    r8, r8
0x14000e1b2  jz      short loc_14000E1EE
0x14000e1b4  test    r9, r9
0x14000e1b7  jz      short loc_14000E1EE
0x14000e1b9  test    ecx, ecx
0x14000e1bb  jz      short loc_14000E1EE
0x14000e1bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000e1c1  mov     rcx, rax
0x14000e1c4  inc     rcx
0x14000e1c7  cmp     [rsi+rcx*2], dx
0x14000e1cb  jnz     short loc_14000E1C4
0x14000e1cd  cmp     rcx, 10h
0x14000e1d1  jb      short loc_14000E1FD
0x14000e1d3  lea     r8, aWerkernelhostK; "WERKERNELHOST: Key key length exceeded"...
0x14000e1da  mov     edx, 1; Level
0x14000e1df  lea     ecx, [rdx+4]; ComponentId
0x14000e1e2  call    cs:__imp_DbgPrintEx
0x14000e1e9  nop     dword ptr [rax+rax+00h]
0x14000e1ee  mov     eax, 0C000000Dh
0x14000e1f3  add     rsp, 28h
0x14000e1f7  pop     rdi
0x14000e1f8  pop     rsi
0x14000e1f9  pop     rbp
0x14000e1fa  pop     rbx
0x14000e1fb  retn
0x14000e1fd  inc     rax
0x14000e200  cmp     [r8+rax*2], dx
0x14000e205  jnz     short loc_14000E1FD
0x14000e207  cmp     rax, 28h ; '('
0x14000e20b  jb      short loc_14000E216
0x14000e20d  lea     r8, aWerkernelhostK_0; "WERKERNELHOST: Key id length exceeded\n"
0x14000e214  jmp     short loc_14000E1DA
0x14000e216  cmp     cs:WerKernelLiveReportInitialized, dl
0x14000e21c  jnz     short loc_14000E225
0x14000e21e  mov     eax, 0C0000002h
0x14000e223  jmp     short loc_14000E1F3
0x14000e225  call    WerpRefreshRootPath
0x14000e22a  cmp     ebx, 1
0x14000e22d  jnz     short loc_14000E23F
0x14000e22f  mov     r8, rbp
0x14000e232  mov     rdx, rdi
0x14000e235  mov     rcx, rsi
0x14000e238  call    WerpCreateReportMini
0x14000e23d  jmp     short loc_14000E1F3
0x14000e23f  cmp     ebx, 2
0x14000e242  jnz     short loc_14000E1F3
0x14000e244  mov     r9, [rsp+48h+arg_20]
0x14000e249  mov     r8, rbp
0x14000e24c  mov     rdx, rdi
0x14000e24f  mov     rcx, rsi
0x14000e252  call    WerpCreateReportFull
0x14000e257  jmp     short loc_14000E1F3
```
