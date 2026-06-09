# VidExoVpTeardown

- ea: `0x14008476c`
- end: `0x14008487b`
- name: `VidExoVpTeardown`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140011f20`

## callees

- `0x14008476c`
- `0x140084b44`
- `0x140084c78`

## import_xrefs

- `ntoskrnl!KeRemoveQueueDpcEx` at `0x140084863`
- `ntoskrnl!KeRemoveQueueDpcEx` at `0x140084863`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084804`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084839`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084804`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084839`

## pseudocode

```c
__int64 __fastcall VidExoVpTeardown(__int64 a1, __int64 a2)
{
  __int64 i; // rdi
  unsigned int j; // esi
  __int64 v5; // rax
  __int64 v6; // r14

  if ( *(_QWORD *)(a1 + 11976) )
  {
    if ( *(_DWORD *)(a1 + 11984) )
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 11984) >> 6; i = (unsigned int)(i + 1) )
      {
        for ( j = 0; ; ++j )
        {
          v5 = *(_QWORD *)(a1 + 11976);
          if ( j >= 0x40 )
            break;
          v6 = 16LL * j + *(_QWORD *)(v5 + 8 * i);
          if ( (unsigned __int8)VidExoVppLockForDelete(a1, v6) )
          {
            VidExoVppDelete(a1, *(unsigned int **)(v6 + 8), 1);
            *(_QWORD *)(v6 + 8) = 0;
            *(_DWORD *)v6 = 0;
          }
          if ( *(_DWORD *)v6 )
            __fastfail(5u);
        }
        ExFreePoolWithTag(*(PVOID *)(v5 + 8 * i), 0x72446456u);
        *(_QWORD *)(*(_QWORD *)(a1 + 11976) + 8 * i) = 0;
      }
    }
    ExFreePoolWithTag(*(PVOID *)(a1 + 11976), 0x72446456u);
    *(_QWORD *)(a1 + 11976) = 0;
    *(_DWORD *)(a1 + 11984) = 0;
  }
  LOBYTE(a2) = 1;
  return KeRemoveQueueDpcEx(a1 + 12000, a2);
}

```

## disassembly

```asm
0x14008476c  push    rbx
0x14008476e  push    rbp
0x14008476f  push    rsi
0x140084770  push    rdi
0x140084771  push    r14
0x140084773  sub     rsp, 20h
0x140084777  cmp     qword ptr [rcx+2EC8h], 0
0x14008477f  mov     rbx, rcx
0x140084782  jz      loc_14008485A
0x140084788  cmp     dword ptr [rcx+2ED0h], 0
0x14008478f  jbe     loc_14008482D
0x140084795  xor     edi, edi
0x140084797  mov     eax, [rbx+2ED0h]
0x14008479d  shr     eax, 6
0x1400847a0  cmp     edi, eax
0x1400847a2  jnb     loc_14008482D
0x1400847a8  xor     esi, esi
0x1400847aa  mov     rax, [rbx+2EC8h]
0x1400847b1  cmp     esi, 40h ; '@'
0x1400847b4  jnb     short loc_1400847FB
0x1400847b6  mov     r14, [rax+rdi*8]
0x1400847ba  mov     ecx, esi
0x1400847bc  shl     rcx, 4
0x1400847c0  add     r14, rcx
0x1400847c3  mov     rcx, rbx
0x1400847c6  mov     rdx, r14
0x1400847c9  call    VidExoVppLockForDelete
0x1400847ce  test    al, al
0x1400847d0  jz      short loc_1400847F0
0x1400847d2  mov     rdx, [r14+8]
0x1400847d6  mov     r8b, 1
0x1400847d9  mov     rcx, rbx
0x1400847dc  call    VidExoVppDelete
0x1400847e1  mov     qword ptr [r14+8], 0
0x1400847e9  mov     dword ptr [r14], 0
0x1400847f0  mov     eax, [r14]
0x1400847f3  test    eax, eax
0x1400847f5  jnz     short loc_140084826
0x1400847f7  inc     esi
0x1400847f9  jmp     short loc_1400847AA
0x1400847fb  mov     rcx, [rax+rdi*8]; P
0x1400847ff  mov     edx, 72446456h; Tag
0x140084804  call    cs:__imp_ExFreePoolWithTag
0x14008480b  nop     dword ptr [rax+rax+00h]
0x140084810  mov     rax, [rbx+2EC8h]
0x140084817  mov     qword ptr [rax+rdi*8], 0
0x14008481f  inc     edi
0x140084821  jmp     loc_140084797
0x140084826  mov     ecx, 5
0x14008482b  int     29h; Win8: RtlFailFast(ecx)
0x14008482d  mov     rcx, [rbx+2EC8h]; P
0x140084834  mov     edx, 72446456h; Tag
0x140084839  call    cs:__imp_ExFreePoolWithTag
0x140084840  nop     dword ptr [rax+rax+00h]
0x140084845  mov     qword ptr [rbx+2EC8h], 0
0x140084850  mov     dword ptr [rbx+2ED0h], 0
0x14008485a  lea     rcx, [rbx+2EE0h]
0x140084861  mov     dl, 1
0x140084863  call    cs:__imp_KeRemoveQueueDpcEx
0x14008486a  nop     dword ptr [rax+rax+00h]
0x14008486f  add     rsp, 20h
0x140084873  pop     r14
0x140084875  pop     rdi
0x140084876  pop     rsi
0x140084877  pop     rbp
0x140084878  pop     rbx
0x140084879  retn
```
