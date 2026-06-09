# WriteRemainingCTFCode

- ea: `0x18000bd00`
- end: `0x18000bdd3`
- name: `WriteRemainingCTFCode`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800059a0`

## callees

- `0x18000b160`
- `0x18000bc10`
- `0x18000bd00`
- `0x18000d570`
- `0x18000d900`
- `0x18000ddd4`

## pseudocode

```c
__int64 __fastcall WriteRemainingCTFCode(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  unsigned int v5; // ebx
  int v6; // r9d
  int v7; // ecx

  VerifyConditionInternal(*(_QWORD *)(a1 + 136), 1);
  Write255UShort(a2, *(unsigned __int16 *)(a1 + 96));
  v4 = *(_QWORD *)(a1 + 112);
  v5 = *(unsigned __int16 *)(a1 + 96);
  v6 = *(_DWORD *)(v4 + 48);
  v7 = *(_DWORD *)(v4 + 40);
  if ( (int)(v6 + v5) > v7 )
  {
    *(_DWORD *)(v4 + 40) = v5 + v6 + (v7 >> 1) + 2;
    VerifyGlyphBuffersize(a1, 1, *(unsigned int *)(*(_QWORD *)(a1 + 112) + 40LL));
    *(_QWORD *)(*(_QWORD *)(a1 + 112) + 32LL) = MTX_mem_realloc(
                                                  *(_QWORD *)(a1 + 136),
                                                  *(_QWORD *)(*(_QWORD *)(a1 + 112) + 32LL),
                                                  *(unsigned int *)(*(_QWORD *)(a1 + 112) + 40LL));
  }
  memcpyHuge(
    *(_QWORD *)(*(_QWORD *)(a1 + 112) + 32LL) + *(int *)(*(_QWORD *)(a1 + 112) + 48LL),
    *(_QWORD *)(a1 + 104),
    v5);
  *(_DWORD *)(*(_QWORD *)(a1 + 112) + 48LL) += v5;
  return VerifyConditionInternal(
           *(_QWORD *)(a1 + 136),
           *(_DWORD *)(*(_QWORD *)(a1 + 112) + 48LL) <= *(_DWORD *)(*(_QWORD *)(a1 + 112) + 40LL));
}

```

## disassembly

```asm
0x18000bd00  mov     [rsp+arg_0], rbx
0x18000bd05  push    rdi
0x18000bd06  sub     rsp, 20h
0x18000bd0a  mov     rbx, rdx
0x18000bd0d  mov     rdi, rcx
0x18000bd10  mov     rcx, [rcx+88h]
0x18000bd17  mov     edx, 1
0x18000bd1c  call    VerifyConditionInternal
0x18000bd21  movzx   edx, word ptr [rdi+60h]
0x18000bd25  mov     rcx, rbx
0x18000bd28  call    Write255UShort
0x18000bd2d  mov     r8, [rdi+70h]
0x18000bd31  movzx   ebx, word ptr [rdi+60h]
0x18000bd35  mov     r9d, [r8+30h]
0x18000bd39  mov     ecx, [r8+28h]
0x18000bd3d  lea     eax, [r9+rbx]
0x18000bd41  cmp     eax, ecx
0x18000bd43  jg      short loc_18000BD8A
0x18000bd45  mov     rax, [rdi+70h]
0x18000bd49  mov     r8d, ebx
0x18000bd4c  mov     rdx, [rdi+68h]
0x18000bd50  movsxd  rcx, dword ptr [rax+30h]
0x18000bd54  add     rcx, [rax+20h]
0x18000bd58  call    memcpyHuge
0x18000bd5d  mov     r8, [rdi+70h]
0x18000bd61  xor     edx, edx
0x18000bd63  add     [r8+30h], ebx
0x18000bd67  mov     rcx, [rdi+70h]
0x18000bd6b  mov     eax, [rcx+28h]
0x18000bd6e  cmp     [rcx+30h], eax
0x18000bd71  mov     rcx, [rdi+88h]
0x18000bd78  setle   dl
0x18000bd7b  mov     rbx, [rsp+28h+arg_0]
0x18000bd80  add     rsp, 20h
0x18000bd84  pop     rdi
0x18000bd85  jmp     VerifyConditionInternal
0x18000bd8a  sar     ecx, 1
0x18000bd8c  mov     edx, 1
0x18000bd91  lea     eax, [r9+rcx]
0x18000bd95  mov     rcx, rdi
0x18000bd98  add     eax, 2
0x18000bd9b  add     eax, ebx
0x18000bd9d  mov     [r8+28h], eax
0x18000bda1  mov     r8, [rdi+70h]
0x18000bda5  mov     r8d, [r8+28h]
0x18000bda9  call    VerifyGlyphBuffersize
0x18000bdae  mov     rdx, [rdi+70h]
0x18000bdb2  mov     rcx, [rdi+88h]
0x18000bdb9  mov     r8d, [rdx+28h]
0x18000bdbd  mov     rdx, [rdx+20h]
0x18000bdc1  call    MTX_mem_realloc
0x18000bdc6  mov     rcx, [rdi+70h]
0x18000bdca  mov     [rcx+20h], rax
0x18000bdce  jmp     loc_18000BD45
```
