# SafeMemCopyAndAdvanceInput<long>(long *,uchar * &,uchar *,long)

- ea: `0x180008fa4`
- end: `0x180009003`
- name: `??$SafeMemCopyAndAdvanceInput@J@@YAJPEAJAEAPEAEPEAEJ@Z`
- size: `95`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000afe0`
- `0x18000b208`
- `0x18000e9a0`
- `0x18000ecd4`

## callees

- `0x180002fb0`
- `0x180008fa4`

## pseudocode

```c
int __fastcall SafeMemCopyAndAdvanceInput<long>(void *a1, const void *const *a2, const void *a3)
{
  int result; // eax
  bool v5; // sf

  if ( a3 <= *a2 || !a1 || !*a2 || !a3 || (unsigned __int64)a3 - (unsigned __int64)*a2 < 4 )
    return -2147024809;
  result = memcpy_s(a1, 4u, *a2, 4u);
  v5 = result < 0;
  if ( !result )
  {
    result = 0;
LABEL_12:
    *a2 = (char *)*a2 + 4;
    return result;
  }
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v5 = result < 0;
  }
  if ( !v5 )
    goto LABEL_12;
  return result;
}

```

## disassembly

```asm
0x180008fa4  push    rbx
0x180008fa6  sub     rsp, 20h
0x180008faa  mov     rbx, rdx
0x180008fad  cmp     r8, [rdx]
0x180008fb0  jbe     short loc_180008FF8
0x180008fb2  test    rcx, rcx
0x180008fb5  jz      short loc_180008FF8
0x180008fb7  cmp     qword ptr [rdx], 0
0x180008fbb  jz      short loc_180008FF8
0x180008fbd  test    r8, r8
0x180008fc0  jz      short loc_180008FF8
0x180008fc2  sub     r8, [rdx]
0x180008fc5  cmp     r8, 4
0x180008fc9  jb      short loc_180008FF8
0x180008fcb  mov     r8, [rdx]; Source
0x180008fce  mov     r9d, 4; SourceSize
0x180008fd4  mov     edx, r9d; DestinationSize
0x180008fd7  call    memcpy_s
0x180008fdc  test    eax, eax
0x180008fde  jz      short loc_180008FF0
0x180008fe0  jle     short loc_180008FEC
0x180008fe2  movzx   eax, ax
0x180008fe5  or      eax, 80070000h
0x180008fea  test    eax, eax
0x180008fec  js      short loc_180008FFD
0x180008fee  jmp     short loc_180008FF2
0x180008ff0  xor     eax, eax
0x180008ff2  add     qword ptr [rbx], 4
0x180008ff6  jmp     short loc_180008FFD
0x180008ff8  mov     eax, 80070057h
0x180008ffd  add     rsp, 20h
0x180009001  pop     rbx
0x180009002  retn
```
