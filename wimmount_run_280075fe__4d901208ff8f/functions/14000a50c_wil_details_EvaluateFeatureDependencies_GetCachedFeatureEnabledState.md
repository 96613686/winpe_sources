# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x14000a50c`
- end: `0x14000a5dd`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000a41c`
- `0x14000a50c`

## callees

- `0x14000a50c`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2)
{
  unsigned __int32 v2; // esi
  int v4; // ebx
  __int64 *v5; // rdi
  __int64 v6; // rax
  unsigned __int32 v7; // eax
  unsigned int v8; // r8d
  __int64 v10; // [rsp+50h] [rbp+8h]

  v2 = *a1;
  v10 = *(unsigned int *)a1;
  if ( (*a1 & 0x200) != 0 )
  {
    HIDWORD(v10) = 0;
    v4 = (v2 >> 6) & 1;
    if ( v4 )
    {
      v5 = *(__int64 **)(a2 + 32);
      if ( v5 )
      {
        while ( 1 )
        {
          v6 = *v5;
          if ( !*v5 )
            break;
          if ( *(_BYTE *)(v6 + 30) || *(_BYTE *)(v6 + 29) )
          {
            if ( !*(_BYTE *)(v6 + 31) )
            {
              v4 = 0;
              goto LABEL_12;
            }
            v4 = 1;
            ++v5;
          }
          else
          {
            v4 = (wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(*(_QWORD *)v6, *v5++) & 1) != 0;
            if ( !v4 )
              goto LABEL_12;
          }
        }
      }
    }
    do
    {
LABEL_12:
      v7 = v2;
      v8 = v4 & 0xFFFFFFCF | v2 & 0xFFFFFFCE;
      if ( (v2 & 1) == v4 )
        v8 = v4 | v2 & 0xFFFFFFFE;
      LODWORD(v10) = v8 & 0xFFFFFDFF;
      v2 = _InterlockedCompareExchange(a1, v8 & 0xFFFFFDFF, v2);
    }
    while ( v7 != v2 );
  }
  return v10;
}

```

## disassembly

```asm
0x14000a50c  push    rbx
0x14000a50e  push    rsi
0x14000a50f  push    rdi
0x14000a510  push    r14
0x14000a512  sub     rsp, 28h
0x14000a516  mov     esi, [rcx]
0x14000a518  mov     r14, rcx
0x14000a51b  mov     [rsp+48h+arg_0], 0
0x14000a524  mov     dword ptr [rsp+48h+arg_0], esi
0x14000a528  bt      esi, 9
0x14000a52c  jnb     loc_14000A5CD
0x14000a532  mov     ebx, esi
0x14000a534  mov     [rsp+48h+arg_0], 0
0x14000a53d  shr     ebx, 6
0x14000a540  and     ebx, 1
0x14000a543  jz      short loc_14000A59F
0x14000a545  mov     rdi, [rdx+20h]
0x14000a549  test    rdi, rdi
0x14000a54c  jz      short loc_14000A59F
0x14000a54e  mov     rax, [rdi]
0x14000a551  test    rax, rax
0x14000a554  jz      short loc_14000A59F
0x14000a556  cmp     byte ptr [rax+1Eh], 0
0x14000a55a  jnz     short loc_14000A588
0x14000a55c  cmp     byte ptr [rax+1Dh], 0
0x14000a560  jnz     short loc_14000A588
0x14000a562  mov     rcx, [rax]
0x14000a565  mov     rdx, rax
0x14000a568  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14000a56d  test    ebx, ebx
0x14000a56f  jz      short loc_14000A57C
0x14000a571  test    al, 1
0x14000a573  jz      short loc_14000A57C
0x14000a575  mov     ebx, 1
0x14000a57a  jmp     short loc_14000A57E
0x14000a57c  xor     ebx, ebx
0x14000a57e  add     rdi, 8
0x14000a582  test    ebx, ebx
0x14000a584  jnz     short loc_14000A54E
0x14000a586  jmp     short loc_14000A59F
0x14000a588  test    ebx, ebx
0x14000a58a  jz      short loc_14000A59D
0x14000a58c  cmp     byte ptr [rax+1Fh], 0
0x14000a590  jz      short loc_14000A59D
0x14000a592  mov     ebx, 1
0x14000a597  add     rdi, 8
0x14000a59b  jmp     short loc_14000A54E
0x14000a59d  xor     ebx, ebx
0x14000a59f  mov     edx, esi
0x14000a5a1  mov     ecx, esi
0x14000a5a3  and     edx, 0FFFFFFFEh
0x14000a5a6  and     ecx, 1
0x14000a5a9  or      edx, ebx
0x14000a5ab  mov     eax, esi
0x14000a5ad  mov     r8d, edx
0x14000a5b0  and     r8d, 0FFFFFFCFh
0x14000a5b4  cmp     ecx, ebx
0x14000a5b6  cmovz   r8d, edx
0x14000a5ba  btr     r8d, 9
0x14000a5bf  mov     dword ptr [rsp+48h+arg_0], r8d
0x14000a5c4  lock cmpxchg [r14], r8d
0x14000a5c9  mov     esi, eax
0x14000a5cb  jnz     short loc_14000A59F
0x14000a5cd  mov     rax, [rsp+48h+arg_0]
0x14000a5d2  add     rsp, 28h
0x14000a5d6  pop     r14
0x14000a5d8  pop     rdi
0x14000a5d9  pop     rsi
0x14000a5da  pop     rbx
0x14000a5db  retn
```
