# FveFindGuidRecognition

- ea: `0x18003296c`
- end: `0x1800329c5`
- name: `FveFindGuidRecognition`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032750`

## callees

- `0x18003296c`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1800329a4`
- `ntdll!RtlCompareMemory` at `0x1800329a4`

## pseudocode

```c
__int64 __fastcall FveFindGuidRecognition(__int64 a1, unsigned int a2)
{
  __int64 v2; // rdi
  __int64 v4; // rbx
  unsigned __int64 v5; // rsi

  v2 = 0;
  if ( a2 >= 0x28 )
  {
    v4 = 0;
    v5 = a2 - 40LL;
    while ( (unsigned int)v4 <= v5 )
    {
      if ( RtlCompareMemory(INFORMATION_OFFSET_GUID, (const void *)(v4 + a1), 0x10u) == 16 )
        return v4 + a1;
      v4 = (unsigned int)(v4 + 1);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18003296c  push    rbx
0x18003296e  push    rbp
0x18003296f  push    rsi
0x180032970  push    rdi
0x180032971  push    r14
0x180032973  sub     rsp, 20h
0x180032977  xor     edi, edi
0x180032979  mov     r14, rcx
0x18003297c  cmp     edx, 28h ; '('
0x18003297f  jb      short loc_1800329B7
0x180032981  xor     ebx, ebx
0x180032983  mov     esi, edx
0x180032985  sub     rsi, 28h ; '('
0x180032989  mov     eax, ebx
0x18003298b  cmp     rax, rsi
0x18003298e  ja      short loc_1800329B7
0x180032990  lea     rbp, [rbx+r14]
0x180032994  mov     r8d, 10h; Length
0x18003299a  mov     rdx, rbp; Source2
0x18003299d  lea     rcx, INFORMATION_OFFSET_GUID; Source1
0x1800329a4  call    cs:__imp_RtlCompareMemory
0x1800329aa  cmp     rax, 10h
0x1800329ae  jz      short loc_1800329B4
0x1800329b0  inc     ebx
0x1800329b2  jmp     short loc_180032989
0x1800329b4  mov     rdi, rbp
0x1800329b7  mov     rax, rdi
0x1800329ba  add     rsp, 20h
0x1800329be  pop     r14
0x1800329c0  pop     rdi
0x1800329c1  pop     rsi
0x1800329c2  pop     rbp
0x1800329c3  pop     rbx
0x1800329c4  retn
```
