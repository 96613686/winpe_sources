# CW32System::ImmSetCompositionWindow(ulong,tagCOMPOSITIONFORM *,int)

- ea: `0x1800915fc`
- end: `0x180091670`
- name: `?ImmSetCompositionWindow@CW32System@@SAHKPEAUtagCOMPOSITIONFORM@@H@Z`
- size: `116`
- prototype: `__int64 __fastcall(unsigned int, struct tagCOMPOSITIONFORM *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180066af0`
- `0x1800677f8`

## callees

- `0x1800915fc`
- `0x180092fb0`
- `0x180095010`

## string_xrefs

- `0x18009163e`: `ImmSetCompositionWindow`

## pseudocode

```c
__int64 __fastcall CW32System::ImmSetCompositionWindow(unsigned int a1, struct tagCOMPOSITIONFORM *a2, int a3)
{
  __int64 (__fastcall *v6)(_QWORD, struct tagCOMPOSITIONFORM *); // rax

  if ( a3 )
    return (*(int (__fastcall **)(__int64, _QWORD, struct tagCOMPOSITIONFORM *))(*(_QWORD *)qword_1800A7598 + 424LL))(
             qword_1800A7598,
             a1,
             a2) >= 0;
  v6 = (__int64 (__fastcall *)(_QWORD, struct tagCOMPOSITIONFORM *))qword_1800A71F0;
  if ( !qword_1800A71F0 )
  {
    SetIMEProcAddr(&qword_1800A71F0, 0, "ImmSetCompositionWindow");
    v6 = (__int64 (__fastcall *)(_QWORD, struct tagCOMPOSITIONFORM *))qword_1800A71F0;
  }
  return v6(a1, a2);
}

```

## disassembly

```asm
0x1800915fc  mov     [rsp+arg_0], rbx
0x180091601  push    rdi
0x180091602  sub     rsp, 20h
0x180091606  mov     rbx, rdx
0x180091609  mov     edi, ecx
0x18009160b  test    r8d, r8d
0x18009160e  jz      short loc_180091632
0x180091610  mov     rcx, cs:qword_1800A7598
0x180091617  mov     r8, rdx
0x18009161a  mov     edx, edi
0x18009161c  mov     rax, [rcx]
0x18009161f  mov     rax, [rax+1A8h]
0x180091626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009162b  not     eax
0x18009162d  shr     eax, 1Fh
0x180091630  jmp     short loc_180091664
0x180091632  mov     rax, cs:qword_1800A71F0
0x180091639  test    rax, rax
0x18009163c  jnz     short loc_18009165A
0x18009163e  lea     r8, aImmsetcomposit_1; "ImmSetCompositionWindow"
0x180091645  xor     edx, edx
0x180091647  lea     rcx, qword_1800A71F0
0x18009164e  call    SetIMEProcAddr
0x180091653  mov     rax, cs:qword_1800A71F0
0x18009165a  mov     rdx, rbx
0x18009165d  mov     ecx, edi
0x18009165f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091664  mov     rbx, [rsp+28h+arg_0]
0x180091669  add     rsp, 20h
0x18009166d  pop     rdi
0x18009166e  retn
```
