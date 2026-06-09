# SclpRemoveContextNoOps

- ea: `0x1800072d0`
- end: `0x1800073be`
- name: `SclpRemoveContextNoOps`
- size: `238`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006024`

## callees

- `0x1800072d0`
- `0x18000a524`

## import_xrefs

- `ntdll!_wcsicmp` at `0x1800072fe`
- `ntdll!_wcsicmp` at `0x180007361`
- `ntdll!_wcsicmp` at `0x1800072fe`
- `ntdll!_wcsicmp` at `0x180007361`

## string_xrefs

- `0x18000732f`: `Old and new paths are identical ([%ws]); skipping path replacement...`
- `0x1800072e2`: `SclpRemoveContextNoOps`
- `0x180007392`: `Old and new SID strings are identical ([%ws]); skipping SID replacement...`

## pseudocode

```c
__int64 __fastcall SclpRemoveContextNoOps(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rcx

  if ( (*(_DWORD *)(a1 + 8) & 2) != 0 )
  {
    v2 = a1 + 32;
    if ( !_wcsicmp((const wchar_t *)(a1 + 32), (const wchar_t *)(a1 + 552)) )
    {
      v3 = a1 + 1152;
      if ( !a1 )
        v3 = 0;
      SclLogGenericMessage(
        v3,
        1,
        (int)SclEvent_Generic_Info,
        1209,
        (__int64)"SclpRemoveContextNoOps",
        "Old and new paths are identical ([%ws]); skipping path replacement...",
        v2);
      *(_DWORD *)(a1 + 8) &= ~2u;
    }
  }
  if ( (*(_DWORD *)(a1 + 8) & 4) != 0 && !_wcsicmp((const wchar_t *)(a1 + 1336), (const wchar_t *)(a1 + 1856)) )
  {
    v4 = a1 + 1152;
    if ( !a1 )
      v4 = 0;
    SclLogGenericMessage(
      v4,
      1,
      (int)SclEvent_Generic_Info,
      1220,
      (__int64)"SclpRemoveContextNoOps",
      "Old and new SID strings are identical ([%ws]); skipping SID replacement...",
      a1 + 1336);
    *(_DWORD *)(a1 + 8) &= ~4u;
  }
  return 0;
}

```

## disassembly

```asm
0x1800072d0  mov     [rsp+arg_0], rbx
0x1800072d5  mov     [rsp+arg_8], rbp
0x1800072da  push    rdi
0x1800072db  sub     rsp, 40h
0x1800072df  mov     eax, [rcx+8]
0x1800072e2  lea     rbp, aSclpremovecont; "SclpRemoveContextNoOps"
0x1800072e9  mov     rbx, rcx
0x1800072ec  test    al, 2
0x1800072ee  jz      short loc_180007349
0x1800072f0  lea     rdi, [rcx+20h]
0x1800072f4  lea     rdx, [rcx+228h]; String2
0x1800072fb  mov     rcx, rdi; String1
0x1800072fe  call    cs:__imp__wcsicmp
0x180007304  test    eax, eax
0x180007306  jnz     short loc_180007349
0x180007308  xor     eax, eax
0x18000730a  mov     [rsp+48h+var_18], rdi
0x18000730f  test    rbx, rbx
0x180007312  lea     rcx, [rbx+480h]
0x180007319  mov     r9d, 4B9h
0x18000731f  lea     r8, SclEvent_Generic_Info
0x180007326  cmovz   rcx, rax
0x18000732a  mov     edx, 1
0x18000732f  lea     rax, aOldAndNewPaths_0; "Old and new paths are identical ([%ws])"...
0x180007336  mov     [rsp+48h+var_20], rax
0x18000733b  mov     [rsp+48h+var_28], rbp
0x180007340  call    SclLogGenericMessage
0x180007345  and     dword ptr [rbx+8], 0FFFFFFFDh
0x180007349  mov     eax, [rbx+8]
0x18000734c  test    al, 4
0x18000734e  jz      short loc_1800073AC
0x180007350  lea     rdi, [rbx+538h]
0x180007357  mov     rcx, rdi; String1
0x18000735a  lea     rdx, [rbx+740h]; String2
0x180007361  call    cs:__imp__wcsicmp
0x180007367  test    eax, eax
0x180007369  jnz     short loc_1800073AC
0x18000736b  xor     eax, eax
0x18000736d  mov     [rsp+48h+var_18], rdi
0x180007372  test    rbx, rbx
0x180007375  lea     rcx, [rbx+480h]
0x18000737c  mov     r9d, 4C4h
0x180007382  lea     r8, SclEvent_Generic_Info
0x180007389  cmovz   rcx, rax
0x18000738d  mov     edx, 1
0x180007392  lea     rax, aOldAndNewSidSt; "Old and new SID strings are identical ("...
0x180007399  mov     [rsp+48h+var_20], rax
0x18000739e  mov     [rsp+48h+var_28], rbp
0x1800073a3  call    SclLogGenericMessage
0x1800073a8  and     dword ptr [rbx+8], 0FFFFFFFBh
0x1800073ac  mov     rbx, [rsp+48h+arg_0]
0x1800073b1  xor     eax, eax
0x1800073b3  mov     rbp, [rsp+48h+arg_8]
0x1800073b8  add     rsp, 40h
0x1800073bc  pop     rdi
0x1800073bd  retn
```
