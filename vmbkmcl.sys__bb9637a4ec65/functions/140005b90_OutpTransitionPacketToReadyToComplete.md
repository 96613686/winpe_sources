# OutpTransitionPacketToReadyToComplete

- ea: `0x140005b90`
- end: `0x140005c35`
- name: `OutpTransitionPacketToReadyToComplete`
- size: `165`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400037e0`
- `0x140006700`
- `0x140009a34`
- `0x140009d8c`

## callees

- `0x140005b90`
- `0x1400097ec`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140005c09`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140005c09`

## pseudocode

```c
char __fastcall OutpTransitionPacketToReadyToComplete(__int64 a1, __int64 a2)
{
  signed __int64 v2; // rax
  signed __int64 *v5; // rdx
  signed __int64 v6; // r8
  signed __int64 v7; // rcx
  struct _RTL_AVL_TABLE *v8; // rcx
  int Buffer; // [rsp+20h] [rbp-18h] BYREF
  __int64 v11; // [rsp+24h] [rbp-14h]

  v2 = *(unsigned int *)(a2 + 28);
  if ( (_DWORD)v2 )
  {
    v11 = 0;
    if ( (unsigned int)v2 >= *(_DWORD *)(a1 + 720) )
    {
      v8 = *(struct _RTL_AVL_TABLE **)(a1 + 752);
      Buffer = v2;
      LOBYTE(v2) = RtlDeleteElementGenericTableAvl(v8, &Buffer);
    }
    else
    {
      v5 = *(signed __int64 **)(a1 + 712);
      v6 = v2;
      _m_prefetchw(v5);
      v2 = *v5;
      do
      {
        v5[v6] = v2;
        v7 = v2;
        v2 = _InterlockedCompareExchange64(v5, v6, v2);
      }
      while ( v2 != v7 );
    }
    *(_DWORD *)(a2 + 28) = 0;
  }
  if ( *(_BYTE *)(a2 + 61) == 1 && *(_QWORD *)(a2 + 80) )
  {
    LOBYTE(v2) = KmclpFreeBounceList(*(_QWORD *)a1);
    *(_QWORD *)(a2 + 80) = 0;
  }
  *(_DWORD *)(a2 + 24) = 4;
  return v2;
}

```

## disassembly

```asm
0x140005b90  mov     [rsp+arg_0], rbx
0x140005b95  push    rdi
0x140005b96  sub     rsp, 30h
0x140005b9a  mov     eax, [rdx+1Ch]
0x140005b9d  mov     rbx, rdx
0x140005ba0  mov     rdi, rcx
0x140005ba3  test    eax, eax
0x140005ba5  jnz     short loc_140005BC0
0x140005ba7  cmp     byte ptr [rbx+3Dh], 1
0x140005bab  jz      short loc_140005C17
0x140005bad  mov     dword ptr [rbx+18h], 4
0x140005bb4  mov     rbx, [rsp+38h+arg_0]
0x140005bb9  add     rsp, 30h
0x140005bbd  pop     rdi
0x140005bbe  retn
0x140005bc0  xor     ecx, ecx
0x140005bc2  mov     [rsp+38h+var_14], rcx
0x140005bc7  cmp     eax, [rdi+2D0h]
0x140005bcd  jnb     short loc_140005BF9
0x140005bcf  mov     rdx, [rdi+2C8h]
0x140005bd6  mov     r8, rax
0x140005bd9  prefetchw byte ptr [rdx]
0x140005bdc  mov     rax, [rdx]
0x140005bdf  mov     [rdx+r8*8], rax
0x140005be3  mov     rcx, rax
0x140005be6  lock cmpxchg [rdx], r8
0x140005beb  cmp     rax, rcx
0x140005bee  jnz     short loc_140005BDF
0x140005bf0  mov     dword ptr [rbx+1Ch], 0
0x140005bf7  jmp     short loc_140005BA7
0x140005bf9  mov     rcx, [rdi+2F0h]; Table
0x140005c00  lea     rdx, [rsp+38h+Buffer]; Buffer
0x140005c05  mov     [rsp+38h+Buffer], eax
0x140005c09  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140005c10  nop     dword ptr [rax+rax+00h]
0x140005c15  jmp     short loc_140005BF0
0x140005c17  mov     rdx, [rbx+50h]
0x140005c1b  test    rdx, rdx
0x140005c1e  jz      short loc_140005BAD
0x140005c20  mov     rcx, [rdi]
0x140005c23  call    KmclpFreeBounceList
0x140005c28  mov     qword ptr [rbx+50h], 0
0x140005c30  jmp     loc_140005BAD
```
