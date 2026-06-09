# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14000a570`
- end: `0x14000a67d`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a41c`
- `0x14000a534`

## callees

- `0x14000a534`
- `0x14000a570`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        unsigned __int32 a2,
        __int64 a3)
{
  int v4; // esi
  signed __int32 v5; // ebx
  BOOL v6; // edi
  BOOL v7; // ebp
  _QWORD *v8; // r14
  __int64 v9; // rax
  char CachedFeatureEnabledState; // al
  unsigned int v11; // edx
  unsigned int v12; // ecx
  signed __int32 v13; // eax
  __int64 v15; // [rsp+50h] [rbp+8h]

  HIDWORD(v15) = 0;
  v4 = (a2 >> 6) & 1;
  v5 = a2;
  v6 = 1;
  if ( (a2 & 0xC00) == 0xC00 || v4 )
  {
    v8 = *(_QWORD **)(a3 + 32);
    v7 = (a2 & 0xC00) == 3072;
    if ( v8 )
    {
      while ( 1 )
      {
        v9 = *v8;
        if ( !*v8 )
          break;
        if ( *(_BYTE *)(v9 + 30) || *(_BYTE *)(v9 + 29) )
        {
          if ( !*(_BYTE *)(v9 + 31) )
          {
            v6 = 0;
            break;
          }
          v6 = 1;
          ++v8;
        }
        else
        {
          CachedFeatureEnabledState = wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
                                        *(_QWORD *)v9,
                                        *v8);
          v6 = (CachedFeatureEnabledState & 1) != 0;
          ++v8;
          if ( (CachedFeatureEnabledState & 1) == 0 )
            break;
        }
      }
      v4 = v4 && v6;
    }
  }
  else
  {
    v7 = 0;
  }
  while ( 1 )
  {
    v11 = v4 | v5 & 0xFFFFFFFE;
    if ( v7 && !v6 )
      v11 = v4 & 0xFFFFFBFF | v5 & 0xFFFFFBFE;
    v12 = v11 & 0xFFFFFFCF;
    if ( (v5 & 1) == v4 )
      v12 = v11;
    v13 = _InterlockedCompareExchange(a1, v12 & 0xFFFFFDFF, v5);
    if ( v5 == v13 )
      break;
    v5 = v13;
  }
  LODWORD(v15) = v12 & 0xFFFFFDFF;
  return v15;
}

```

## disassembly

```asm
0x14000a570  mov     [rsp+arg_8], rbx
0x14000a575  mov     [rsp+arg_10], rbp
0x14000a57a  push    rsi
0x14000a57b  push    rdi
0x14000a57c  push    r13
0x14000a57e  push    r14
0x14000a580  push    r15
0x14000a582  sub     rsp, 20h
0x14000a586  mov     r13d, 1
0x14000a58c  mov     [rsp+48h+arg_0], 0
0x14000a595  mov     esi, edx
0x14000a597  mov     r15, rcx
0x14000a59a  shr     esi, 6
0x14000a59d  mov     ecx, 0C00h
0x14000a5a2  mov     eax, edx
0x14000a5a4  and     esi, r13d
0x14000a5a7  and     eax, ecx
0x14000a5a9  mov     rbx, rdx
0x14000a5ac  mov     edi, r13d
0x14000a5af  cmp     eax, ecx
0x14000a5b1  jz      short loc_14000A5BB
0x14000a5b3  test    esi, esi
0x14000a5b5  jnz     short loc_14000A5BB
0x14000a5b7  xor     ebp, ebp
0x14000a5b9  jmp     short loc_14000A629
0x14000a5bb  mov     r14, [r8+20h]
0x14000a5bf  xor     ebp, ebp
0x14000a5c1  cmp     eax, ecx
0x14000a5c3  setz    bpl
0x14000a5c7  test    r14, r14
0x14000a5ca  jz      short loc_14000A629
0x14000a5cc  mov     rax, [r14]
0x14000a5cf  test    rax, rax
0x14000a5d2  jz      short loc_14000A61A
0x14000a5d4  cmp     byte ptr [rax+1Eh], 0
0x14000a5d8  jnz     short loc_14000A605
0x14000a5da  cmp     byte ptr [rax+1Dh], 0
0x14000a5de  jnz     short loc_14000A605
0x14000a5e0  mov     rcx, [rax]
0x14000a5e3  mov     rdx, rax
0x14000a5e6  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14000a5eb  test    edi, edi
0x14000a5ed  jz      short loc_14000A5F9
0x14000a5ef  test    r13b, al
0x14000a5f2  jz      short loc_14000A5F9
0x14000a5f4  mov     edi, r13d
0x14000a5f7  jmp     short loc_14000A5FB
0x14000a5f9  xor     edi, edi
0x14000a5fb  add     r14, 8
0x14000a5ff  test    edi, edi
0x14000a601  jnz     short loc_14000A5CC
0x14000a603  jmp     short loc_14000A61A
0x14000a605  test    edi, edi
0x14000a607  jz      short loc_14000A618
0x14000a609  cmp     byte ptr [rax+1Fh], 0
0x14000a60d  jz      short loc_14000A618
0x14000a60f  mov     edi, r13d
0x14000a612  add     r14, 8
0x14000a616  jmp     short loc_14000A5CC
0x14000a618  xor     edi, edi
0x14000a61a  test    esi, esi
0x14000a61c  jz      short loc_14000A627
0x14000a61e  test    edi, edi
0x14000a620  jz      short loc_14000A627
0x14000a622  mov     esi, r13d
0x14000a625  jmp     short loc_14000A629
0x14000a627  xor     esi, esi
0x14000a629  mov     edx, ebx
0x14000a62b  and     edx, 0FFFFFFFEh
0x14000a62e  or      edx, esi
0x14000a630  test    ebp, ebp
0x14000a632  jz      short loc_14000A63C
0x14000a634  test    edi, edi
0x14000a636  jnz     short loc_14000A63C
0x14000a638  btr     edx, 0Ah
0x14000a63c  mov     eax, ebx
0x14000a63e  mov     ecx, edx
0x14000a640  and     eax, r13d
0x14000a643  and     ecx, 0FFFFFFCFh
0x14000a646  cmp     eax, esi
0x14000a648  mov     eax, ebx
0x14000a64a  cmovz   ecx, edx
0x14000a64d  btr     ecx, 9
0x14000a651  mov     dword ptr [rsp+48h+arg_0], ecx
0x14000a655  lock cmpxchg [r15], ecx
0x14000a65a  jz      short loc_14000A660
0x14000a65c  mov     ebx, eax
0x14000a65e  jmp     short loc_14000A629
0x14000a660  mov     rax, [rsp+48h+arg_0]
0x14000a665  mov     rbx, [rsp+48h+arg_8]
0x14000a66a  mov     rbp, [rsp+48h+arg_10]
0x14000a66f  add     rsp, 20h
0x14000a673  pop     r15
0x14000a675  pop     r14
0x14000a677  pop     r13
0x14000a679  pop     rdi
0x14000a67a  pop     rsi
0x14000a67b  retn
```
