# CW32System::ImmSetCompositionFontA(ulong,tagLOGFONTA *,int)

- ea: `0x180091514`
- end: `0x180091588`
- name: `?ImmSetCompositionFontA@CW32System@@SAHKPEAUtagLOGFONTA@@H@Z`
- size: `116`
- prototype: `__int64 __fastcall(unsigned int, struct tagLOGFONTA *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18006762c`

## callees

- `0x180091514`
- `0x180092fb0`
- `0x180095010`

## string_xrefs

- `0x180091556`: `ImmSetCompositionFontA`

## pseudocode

```c
__int64 __fastcall CW32System::ImmSetCompositionFontA(unsigned int a1, struct tagLOGFONTA *a2, int a3)
{
  __int64 (__fastcall *v6)(_QWORD, struct tagLOGFONTA *); // rax

  if ( a3 )
    return (*(int (__fastcall **)(__int64, _QWORD, struct tagLOGFONTA *))(*(_QWORD *)qword_1800A7598 + 392LL))(
             qword_1800A7598,
             a1,
             a2) >= 0;
  v6 = (__int64 (__fastcall *)(_QWORD, struct tagLOGFONTA *))qword_1800A71E8;
  if ( !qword_1800A71E8 )
  {
    SetIMEProcAddr(&qword_1800A71E8, 0, "ImmSetCompositionFontA");
    v6 = (__int64 (__fastcall *)(_QWORD, struct tagLOGFONTA *))qword_1800A71E8;
  }
  return v6(a1, a2);
}

```

## disassembly

```asm
0x180091514  mov     [rsp+arg_0], rbx
0x180091519  push    rdi
0x18009151a  sub     rsp, 20h
0x18009151e  mov     rbx, rdx
0x180091521  mov     edi, ecx
0x180091523  test    r8d, r8d
0x180091526  jz      short loc_18009154A
0x180091528  mov     rcx, cs:qword_1800A7598
0x18009152f  mov     r8, rdx
0x180091532  mov     edx, edi
0x180091534  mov     rax, [rcx]
0x180091537  mov     rax, [rax+188h]
0x18009153e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091543  not     eax
0x180091545  shr     eax, 1Fh
0x180091548  jmp     short loc_18009157C
0x18009154a  mov     rax, cs:qword_1800A71E8
0x180091551  test    rax, rax
0x180091554  jnz     short loc_180091572
0x180091556  lea     r8, aImmsetcomposit_0; "ImmSetCompositionFontA"
0x18009155d  xor     edx, edx
0x18009155f  lea     rcx, qword_1800A71E8
0x180091566  call    SetIMEProcAddr
0x18009156b  mov     rax, cs:qword_1800A71E8
0x180091572  mov     rdx, rbx
0x180091575  mov     ecx, edi
0x180091577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009157c  mov     rbx, [rsp+28h+arg_0]
0x180091581  add     rsp, 20h
0x180091585  pop     rdi
0x180091586  retn
```
