# readPackets

- ea: `0x180009334`
- end: `0x1800094b4`
- name: `readPackets`
- size: `384`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007400`
- `0x180008df0`
- `0x18000f3b4`

## callees

- `0x180001f6c`
- `0x180009334`

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
0x180009334  mov     [rsp+arg_0], rbx
0x180009339  push    rdi
0x18000933a  sub     rsp, 20h
0x18000933e  cmp     qword ptr [rcx+86E8h], 0
0x180009346  mov     rbx, rcx
0x180009349  jz      short loc_180009359
0x18000934b  xor     eax, eax
0x18000934d  mov     rbx, [rsp+28h+arg_0]
0x180009352  add     rsp, 20h
0x180009356  pop     rdi
0x180009357  retn
0x180009359  mov     rax, [rcx+8650h]
0x180009360  mov     edx, [rcx+rax*4+40E0h]
0x180009367  cmp     [rcx+86E0h], rdx
0x18000936e  jnz     short loc_18000934B
0x180009370  cmp     dword ptr [rcx+8B58h], 0
0x180009377  jnz     loc_180009468
0x18000937d  xor     edi, edi
0x18000937f  mov     eax, [rbx+0D8h]
0x180009385  cmp     rdi, rax
0x180009388  ja      short loc_18000934B
0x18000938a  cmp     dword ptr [rbx+0A8h], 0
0x180009391  jz      loc_18000942D
0x180009397  mov     cl, [rbx+8630h]
0x18000939d  test    cl, cl
0x18000939f  jz      short loc_18000940E
0x1800093a1  xor     edx, edx
0x1800093a3  mov     rax, [rbx+86A8h]
0x1800093aa  movzx   ecx, cl
0x1800093ad  imul    rcx, rdi
0x1800093b1  add     rcx, rdx
0x1800093b4  mov     rcx, [rax+rcx*8]
0x1800093b8  mov     dword ptr [rcx+30h], 0
0x1800093bf  mov     rax, [rbx+86A8h]
0x1800093c6  movzx   ecx, byte ptr [rbx+8630h]
0x1800093cd  imul    rcx, rdi
0x1800093d1  add     rcx, rdx
0x1800093d4  mov     rcx, [rax+rcx*8]
0x1800093d8  mov     qword ptr [rcx+20h], 0
0x1800093e0  mov     rax, [rbx+86A8h]
0x1800093e7  movzx   ecx, byte ptr [rbx+8630h]
0x1800093ee  imul    rcx, rdi
0x1800093f2  add     rcx, rdx
0x1800093f5  inc     rdx
0x1800093f8  mov     rcx, [rax+rcx*8]
0x1800093fc  mov     byte ptr [rcx+34h], 0
0x180009400  movzx   eax, byte ptr [rbx+8630h]
0x180009407  mov     cl, al
0x180009409  cmp     rdx, rax
0x18000940c  jb      short loc_1800093A3
0x18000940e  imul    rcx, rdi, 2C0h
0x180009415  add     rcx, [rbx+86C0h]
0x18000941c  call    ResetCodingContextDec
0x180009421  test    eax, eax
0x180009423  jnz     short loc_180009460
0x180009425  inc     rdi
0x180009428  jmp     loc_18000937F
0x18000942d  cmp     qword ptr [rbx+86B0h], 0
0x180009435  jnz     short loc_180009453
0x180009437  mov     rax, [rbx+8640h]
0x18000943e  mov     dword ptr [rax+30h], 0
0x180009445  mov     qword ptr [rax+20h], 0
0x18000944d  mov     byte ptr [rax+34h], 0
0x180009451  jmp     short loc_18000940E
0x180009453  mov     rax, [rbx+86A8h]
0x18000945a  mov     rax, [rax+rdi*8]
0x18000945e  jmp     short loc_18000943E
0x180009460  or      eax, 0FFFFFFFFh
0x180009463  jmp     loc_18000934D
0x180009468  cmp     qword ptr [rcx+86B0h], 0
0x180009470  jbe     short loc_18000949F
0x180009472  xor     edi, edi
0x180009474  mov     eax, [rbx+0D8h]
0x18000947a  cmp     rdi, rax
0x18000947d  ja      loc_18000934B
0x180009483  imul    rcx, rdi, 2C0h
0x18000948a  add     rcx, [rbx+86C0h]
0x180009491  call    ResetCodingContextDec
0x180009496  test    eax, eax
0x180009498  jnz     short loc_180009460
0x18000949a  inc     rdi
0x18000949d  jmp     short loc_180009474
0x18000949f  mov     rcx, [rcx+86C0h]
0x1800094a6  call    ResetCodingContextDec
0x1800094ab  test    eax, eax
0x1800094ad  jnz     short loc_180009460
0x1800094af  jmp     loc_18000934B
```
