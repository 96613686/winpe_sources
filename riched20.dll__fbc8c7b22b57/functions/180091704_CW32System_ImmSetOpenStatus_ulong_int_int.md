# CW32System::ImmSetOpenStatus(ulong,int,int)

- ea: `0x180091704`
- end: `0x180091776`
- name: `?ImmSetOpenStatus@CW32System@@SAHKHH@Z`
- size: `114`
- prototype: `__int64 __fastcall(unsigned int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180053b00`
- `0x180053e58`

## callees

- `0x180091704`
- `0x180092fb0`
- `0x180095010`

## string_xrefs

- `0x180091745`: `ImmSetOpenStatus`

## pseudocode

```c
__int64 __fastcall CW32System::ImmSetOpenStatus(unsigned int a1, unsigned int a2, int a3)
{
  __int64 (__fastcall *v6)(_QWORD, _QWORD); // rax

  if ( a3 )
    return (*(int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)qword_1800A7598 + 440LL))(
             qword_1800A7598,
             a1,
             a2) >= 0;
  v6 = (__int64 (__fastcall *)(_QWORD, _QWORD))qword_1800A7248;
  if ( !qword_1800A7248 )
  {
    SetIMEProcAddr(&qword_1800A7248, 0, "ImmSetOpenStatus");
    v6 = (__int64 (__fastcall *)(_QWORD, _QWORD))qword_1800A7248;
  }
  return v6(a1, a2);
}

```

## disassembly

```asm
0x180091704  mov     [rsp+arg_0], rbx
0x180091709  push    rdi
0x18009170a  sub     rsp, 20h
0x18009170e  mov     ebx, edx
0x180091710  mov     edi, ecx
0x180091712  test    r8d, r8d
0x180091715  jz      short loc_180091739
0x180091717  mov     rcx, cs:qword_1800A7598
0x18009171e  mov     r8d, edx
0x180091721  mov     edx, edi
0x180091723  mov     rax, [rcx]
0x180091726  mov     rax, [rax+1B8h]
0x18009172d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091732  not     eax
0x180091734  shr     eax, 1Fh
0x180091737  jmp     short loc_18009176A
0x180091739  mov     rax, cs:qword_1800A7248
0x180091740  test    rax, rax
0x180091743  jnz     short loc_180091761
0x180091745  lea     r8, aImmsetopenstat; "ImmSetOpenStatus"
0x18009174c  xor     edx, edx
0x18009174e  lea     rcx, qword_1800A7248
0x180091755  call    SetIMEProcAddr
0x18009175a  mov     rax, cs:qword_1800A7248
0x180091761  mov     edx, ebx
0x180091763  mov     ecx, edi
0x180091765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009176a  mov     rbx, [rsp+28h+arg_0]
0x18009176f  add     rsp, 20h
0x180091773  pop     rdi
0x180091774  retn
```
