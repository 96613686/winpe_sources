# SafeMemCopyAndAdvanceInput<bool>(bool *,uchar * &,uchar *,long)

- ea: `0x18000e760`
- end: `0x18000e7be`
- name: `??$SafeMemCopyAndAdvanceInput@_N@@YAJPEA_NAEAPEAEPEAEJ@Z`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e9a0`

## callees

- `0x180002fb0`
- `0x18000e760`

## pseudocode

```c
int __fastcall SafeMemCopyAndAdvanceInput<bool>(void *a1, const void *const *a2, _BYTE *a3)
{
  int result; // eax
  bool v5; // sf

  if ( a3 <= *a2 || !a1 || !*a2 || !a3 || a3 == *(_BYTE **)a2 )
    return -2147024809;
  result = memcpy_s(a1, 1u, *a2, 1u);
  v5 = result < 0;
  if ( !result )
  {
    result = 0;
LABEL_12:
    ++*a2;
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
0x18000e760  push    rbx
0x18000e762  sub     rsp, 20h
0x18000e766  mov     rbx, rdx
0x18000e769  cmp     r8, [rdx]
0x18000e76c  jbe     short loc_18000E7B3
0x18000e76e  test    rcx, rcx
0x18000e771  jz      short loc_18000E7B3
0x18000e773  cmp     qword ptr [rdx], 0
0x18000e777  jz      short loc_18000E7B3
0x18000e779  test    r8, r8
0x18000e77c  jz      short loc_18000E7B3
0x18000e77e  sub     r8, [rdx]
0x18000e781  cmp     r8, 1
0x18000e785  jb      short loc_18000E7B3
0x18000e787  mov     r8, [rdx]; Source
0x18000e78a  mov     r9d, 1; SourceSize
0x18000e790  mov     edx, r9d; DestinationSize
0x18000e793  call    memcpy_s
0x18000e798  test    eax, eax
0x18000e79a  jz      short loc_18000E7AC
0x18000e79c  jle     short loc_18000E7A8
0x18000e79e  movzx   eax, ax
0x18000e7a1  or      eax, 80070000h
0x18000e7a6  test    eax, eax
0x18000e7a8  js      short loc_18000E7B8
0x18000e7aa  jmp     short loc_18000E7AE
0x18000e7ac  xor     eax, eax
0x18000e7ae  inc     qword ptr [rbx]
0x18000e7b1  jmp     short loc_18000E7B8
0x18000e7b3  mov     eax, 80070057h
0x18000e7b8  add     rsp, 20h
0x18000e7bc  pop     rbx
0x18000e7bd  retn
```
