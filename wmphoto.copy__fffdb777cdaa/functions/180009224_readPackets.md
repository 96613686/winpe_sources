# readPackets

- ea: `0x180009224`
- end: `0x1800093a3`
- name: `readPackets`
- size: `383`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007340`
- `0x180008ce0`
- `0x18000f244`

## callees

- `0x180001f1c`
- `0x180009224`

## pseudocode

```c
__int64 __fastcall readPackets(__int64 a1)
{
  unsigned __int64 i; // rdi
  unsigned __int8 v4; // cl
  unsigned __int64 j; // rdx
  unsigned __int64 v6; // rcx
  __int64 v7; // rax
  unsigned __int64 k; // rdi

  if ( *(_QWORD *)(a1 + 34536) || *(_QWORD *)(a1 + 34528) != *(_DWORD *)(a1 + 4LL * *(_QWORD *)(a1 + 34384) + 16608) )
    return 0;
  if ( !*(_DWORD *)(a1 + 35672) )
  {
    for ( i = 0; i <= *(unsigned int *)(a1 + 216); ++i )
    {
      if ( *(_DWORD *)(a1 + 168) )
      {
        v4 = *(_BYTE *)(a1 + 34352);
        if ( v4 )
        {
          for ( j = 0; j < v4; ++j )
          {
            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 34472) + 8 * (j + i * v4)) + 48LL) = 0;
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 34472) + 8 * (j + i * *(unsigned __int8 *)(a1 + 34352))) + 32LL) = 0;
            v6 = j + i * *(unsigned __int8 *)(a1 + 34352);
            *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 34472) + 8 * v6) + 52LL) = 0;
            v4 = *(_BYTE *)(a1 + 34352);
          }
        }
      }
      else
      {
        if ( *(_QWORD *)(a1 + 34480) )
          v7 = *(_QWORD *)(*(_QWORD *)(a1 + 34472) + 8 * i);
        else
          v7 = *(_QWORD *)(a1 + 34368);
        *(_DWORD *)(v7 + 48) = 0;
        *(_QWORD *)(v7 + 32) = 0;
        *(_BYTE *)(v7 + 52) = 0;
      }
      if ( (unsigned int)ResetCodingContextDec(*(_QWORD *)(a1 + 34496) + 704 * i) )
        return 0xFFFFFFFFLL;
    }
    return 0;
  }
  if ( *(_QWORD *)(a1 + 34480) )
  {
    for ( k = 0; k <= *(unsigned int *)(a1 + 216); ++k )
    {
      if ( (unsigned int)ResetCodingContextDec(*(_QWORD *)(a1 + 34496) + 704 * k) )
        return 0xFFFFFFFFLL;
    }
    return 0;
  }
  if ( !(unsigned int)ResetCodingContextDec(*(_QWORD *)(a1 + 34496)) )
    return 0;
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180009224  mov     [rsp+arg_0], rbx
0x180009229  push    rdi
0x18000922a  sub     rsp, 20h
0x18000922e  cmp     qword ptr [rcx+86E8h], 0
0x180009236  mov     rbx, rcx
0x180009239  jz      short loc_180009248
0x18000923b  xor     eax, eax
0x18000923d  mov     rbx, [rsp+28h+arg_0]
0x180009242  add     rsp, 20h
0x180009246  pop     rdi
0x180009247  retn
0x180009248  mov     rax, [rcx+8650h]
0x18000924f  mov     edx, [rcx+rax*4+40E0h]
0x180009256  cmp     [rcx+86E0h], rdx
0x18000925d  jnz     short loc_18000923B
0x18000925f  cmp     dword ptr [rcx+8B58h], 0
0x180009266  jnz     loc_180009357
0x18000926c  xor     edi, edi
0x18000926e  mov     eax, [rbx+0D8h]
0x180009274  cmp     rdi, rax
0x180009277  ja      short loc_18000923B
0x180009279  cmp     dword ptr [rbx+0A8h], 0
0x180009280  jz      loc_18000931C
0x180009286  mov     cl, [rbx+8630h]
0x18000928c  test    cl, cl
0x18000928e  jz      short loc_1800092FD
0x180009290  xor     edx, edx
0x180009292  mov     rax, [rbx+86A8h]
0x180009299  movzx   ecx, cl
0x18000929c  imul    rcx, rdi
0x1800092a0  add     rcx, rdx
0x1800092a3  mov     rcx, [rax+rcx*8]
0x1800092a7  mov     dword ptr [rcx+30h], 0
0x1800092ae  mov     rax, [rbx+86A8h]
0x1800092b5  movzx   ecx, byte ptr [rbx+8630h]
0x1800092bc  imul    rcx, rdi
0x1800092c0  add     rcx, rdx
0x1800092c3  mov     rcx, [rax+rcx*8]
0x1800092c7  mov     qword ptr [rcx+20h], 0
0x1800092cf  mov     rax, [rbx+86A8h]
0x1800092d6  movzx   ecx, byte ptr [rbx+8630h]
0x1800092dd  imul    rcx, rdi
0x1800092e1  add     rcx, rdx
0x1800092e4  inc     rdx
0x1800092e7  mov     rcx, [rax+rcx*8]
0x1800092eb  mov     byte ptr [rcx+34h], 0
0x1800092ef  movzx   eax, byte ptr [rbx+8630h]
0x1800092f6  mov     cl, al
0x1800092f8  cmp     rdx, rax
0x1800092fb  jb      short loc_180009292
0x1800092fd  imul    rcx, rdi, 2C0h
0x180009304  add     rcx, [rbx+86C0h]
0x18000930b  call    ResetCodingContextDec
0x180009310  test    eax, eax
0x180009312  jnz     short loc_18000934F
0x180009314  inc     rdi
0x180009317  jmp     loc_18000926E
0x18000931c  cmp     qword ptr [rbx+86B0h], 0
0x180009324  jnz     short loc_180009342
0x180009326  mov     rax, [rbx+8640h]
0x18000932d  mov     dword ptr [rax+30h], 0
0x180009334  mov     qword ptr [rax+20h], 0
0x18000933c  mov     byte ptr [rax+34h], 0
0x180009340  jmp     short loc_1800092FD
0x180009342  mov     rax, [rbx+86A8h]
0x180009349  mov     rax, [rax+rdi*8]
0x18000934d  jmp     short loc_18000932D
0x18000934f  or      eax, 0FFFFFFFFh
0x180009352  jmp     loc_18000923D
0x180009357  cmp     qword ptr [rcx+86B0h], 0
0x18000935f  jbe     short loc_18000938E
0x180009361  xor     edi, edi
0x180009363  mov     eax, [rbx+0D8h]
0x180009369  cmp     rdi, rax
0x18000936c  ja      loc_18000923B
0x180009372  imul    rcx, rdi, 2C0h
0x180009379  add     rcx, [rbx+86C0h]
0x180009380  call    ResetCodingContextDec
0x180009385  test    eax, eax
0x180009387  jnz     short loc_18000934F
0x180009389  inc     rdi
0x18000938c  jmp     short loc_180009363
0x18000938e  mov     rcx, [rcx+86C0h]
0x180009395  call    ResetCodingContextDec
0x18000939a  test    eax, eax
0x18000939c  jnz     short loc_18000934F
0x18000939e  jmp     loc_18000923B
```
