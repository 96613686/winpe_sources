# pStrBufCreate

- ea: `0x18000e380`
- end: `0x18000e3e9`
- name: `pStrBufCreate`
- size: `105`
- prototype: `void *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000df10`

## callees

- `0x18000e380`
- `0x18000e3f0`
- `0x1800109dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e3aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e3aa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e399`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e399`

## pseudocode

```c
void *__fastcall pStrBufCreate(unsigned int a1)
{
  _QWORD *v2; // rax
  void *v3; // rbx

  v2 = HeapAlloc(hHeap, 0, 0x10u);
  v3 = v2;
  if ( !v2 )
  {
    SetLastError(8u);
LABEL_4:
    StrBufDestroyA(v3);
    return 0;
  }
  *v2 = 0;
  v2[1] = 0;
  if ( !(unsigned int)pStrBufGrow(v2, a1) )
    goto LABEL_4;
  return v3;
}

```

## disassembly

```asm
0x18000e380  mov     [rsp+arg_0], rbx
0x18000e385  push    rdi
0x18000e386  sub     rsp, 20h
0x18000e38a  xor     edx, edx; dwFlags
0x18000e38c  mov     edi, ecx
0x18000e38e  mov     rcx, cs:hHeap; hHeap
0x18000e395  lea     r8d, [rdx+10h]; dwBytes
0x18000e399  call    cs:__imp_HeapAlloc
0x18000e39f  mov     rbx, rax
0x18000e3a2  test    rax, rax
0x18000e3a5  jnz     short loc_18000E3B2
0x18000e3a7  lea     ecx, [rax+8]; dwErrCode
0x18000e3aa  call    cs:__imp_SetLastError
0x18000e3b0  jmp     short loc_18000E3CF
0x18000e3b2  mov     edx, edi
0x18000e3b4  mov     qword ptr [rax], 0
0x18000e3bb  mov     rcx, rbx
0x18000e3be  mov     qword ptr [rax+8], 0
0x18000e3c6  call    pStrBufGrow
0x18000e3cb  test    eax, eax
0x18000e3cd  jnz     short loc_18000E3DB
0x18000e3cf  mov     rcx, rbx; lpMem
0x18000e3d2  call    StrBufDestroyA
0x18000e3d7  xor     eax, eax
0x18000e3d9  jmp     short loc_18000E3DE
0x18000e3db  mov     rax, rbx
0x18000e3de  mov     rbx, [rsp+28h+arg_0]
0x18000e3e3  add     rsp, 20h
0x18000e3e7  pop     rdi
0x18000e3e8  retn
```
