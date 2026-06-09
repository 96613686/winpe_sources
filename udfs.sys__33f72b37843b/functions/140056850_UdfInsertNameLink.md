# UdfInsertNameLink

- ea: `0x140056850`
- end: `0x140056932`
- name: `UdfInsertNameLink`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000a08c`
- `0x14003803c`

## callees

- `0x140056850`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400568c3`
- `ntoskrnl!RtlCompareMemory` at `0x1400568c3`

## pseudocode

```c
char __fastcall UdfInsertNameLink(__int64 a1, __int64 *a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // rsi
  __int64 v5; // rbx
  __int64 v6; // rcx
  unsigned __int16 v8; // dx
  __int64 v9; // rcx
  unsigned __int16 v10; // r8
  _QWORD *v11; // rdi
  unsigned int v12; // r14d
  int v13; // ebp
  unsigned int v14; // eax

  v4 = a4;
  v5 = a4 + a3;
  *(_QWORD *)v5 = v5;
  *(_QWORD *)(v5 + 8) = 0;
  *(_QWORD *)(v5 + 16) = 0;
  v6 = *a2;
  if ( *a2 )
  {
    while ( 1 )
    {
      v8 = *(_WORD *)(v5 + 24);
      v9 = v6 - v4;
      v10 = *(_WORD *)(v4 + v9 + 24);
      v11 = (_QWORD *)(v4 + v9);
      if ( v10 <= v8 )
      {
        v13 = -1;
        v12 = *(unsigned __int16 *)(v4 + v9 + 24);
        if ( v10 == v8 )
          v13 = 0;
      }
      else
      {
        v12 = *(unsigned __int16 *)(v5 + 24);
        v13 = 1;
      }
      v14 = RtlCompareMemory(*(const void **)(v4 + v9 + 32), *(const void **)(v5 + 32), v12);
      if ( v14 < v12 )
        v13 = *(_WORD *)(v11[4] + 2 * ((unsigned __int64)v14 >> 1)) < *(_WORD *)(*(_QWORD *)(v5 + 32)
                                                                               + 2 * ((unsigned __int64)v14 >> 1))
            ? -1
            : 1;
      if ( !v13 )
        return 0;
      if ( v13 == 1 )
      {
        v6 = v11[1];
        if ( !v6 )
        {
          v11[1] = v5;
LABEL_16:
          *(_QWORD *)v5 = v11;
          return 1;
        }
      }
      else
      {
        v6 = v11[2];
        if ( !v6 )
        {
          v11[2] = v5;
          goto LABEL_16;
        }
      }
    }
  }
  else
  {
    *a2 = v5;
    return 1;
  }
}

```

## disassembly

```asm
0x140056850  push    rbx
0x140056852  push    rbp
0x140056853  push    rsi
0x140056854  push    rdi
0x140056855  push    r14
0x140056857  sub     rsp, 20h
0x14005685b  mov     esi, r9d
0x14005685e  lea     rbx, [rsi+r8]
0x140056862  mov     [rbx], rbx
0x140056865  mov     qword ptr [rbx+8], 0
0x14005686d  mov     qword ptr [rbx+10h], 0
0x140056875  mov     rcx, [rdx]
0x140056878  test    rcx, rcx
0x14005687b  jnz     short loc_140056887
0x14005687d  mov     [rdx], rbx
0x140056880  mov     al, 1
0x140056882  jmp     loc_140056926
0x140056887  movzx   edx, word ptr [rbx+18h]
0x14005688b  sub     rcx, rsi
0x14005688e  movzx   r8d, word ptr [rsi+rcx+18h]
0x140056894  lea     rdi, [rsi+rcx]
0x140056898  cmp     r8w, dx
0x14005689c  jbe     short loc_1400568A8
0x14005689e  mov     r14d, edx
0x1400568a1  mov     ebp, 1
0x1400568a6  jmp     short loc_1400568B7
0x1400568a8  or      ebp, 0FFFFFFFFh
0x1400568ab  xor     eax, eax
0x1400568ad  cmp     r8w, dx
0x1400568b1  mov     r14d, r8d
0x1400568b4  cmovz   ebp, eax
0x1400568b7  mov     rdx, [rbx+20h]; Source2
0x1400568bb  mov     rcx, [rsi+rcx+20h]; Source1
0x1400568c0  mov     r8d, r14d; Length
0x1400568c3  call    cs:__imp_RtlCompareMemory
0x1400568ca  nop     dword ptr [rax+rax+00h]
0x1400568cf  cmp     eax, r14d
0x1400568d2  jnb     short loc_1400568F3
0x1400568d4  mov     rdx, [rdi+20h]
0x1400568d8  mov     r8d, eax
0x1400568db  mov     rax, [rbx+20h]
0x1400568df  shr     r8, 1
0x1400568e2  movzx   ecx, word ptr [rax+r8*2]
0x1400568e7  cmp     [rdx+r8*2], cx
0x1400568ec  sbb     ebp, ebp
0x1400568ee  and     ebp, 0FFFFFFFEh
0x1400568f1  inc     ebp
0x1400568f3  test    ebp, ebp
0x1400568f5  jz      short loc_140056924
0x1400568f7  cmp     ebp, 1
0x1400568fa  jnz     short loc_14005690B
0x1400568fc  mov     rcx, [rdi+8]
0x140056900  test    rcx, rcx
0x140056903  jnz     short loc_140056887
0x140056905  mov     [rdi+8], rbx
0x140056909  jmp     short loc_14005691C
0x14005690b  mov     rcx, [rdi+10h]
0x14005690f  test    rcx, rcx
0x140056912  jnz     loc_140056887
0x140056918  mov     [rdi+10h], rbx
0x14005691c  mov     [rbx], rdi
0x14005691f  jmp     loc_140056880
0x140056924  xor     al, al
0x140056926  add     rsp, 20h
0x14005692a  pop     r14
0x14005692c  pop     rdi
0x14005692d  pop     rsi
0x14005692e  pop     rbp
0x14005692f  pop     rbx
0x140056930  retn
```
