# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140023144`
- end: `0x140023251`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140023108`

## callees

- `0x140023108`
- `0x140023144`

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
0x140023144  mov     [rsp+arg_8], rbx
0x140023149  mov     [rsp+arg_10], rbp
0x14002314e  push    rsi
0x14002314f  push    rdi
0x140023150  push    r13
0x140023152  push    r14
0x140023154  push    r15
0x140023156  sub     rsp, 20h
0x14002315a  mov     r13d, 1
0x140023160  mov     [rsp+48h+arg_0], 0
0x140023169  mov     esi, edx
0x14002316b  mov     r15, rcx
0x14002316e  shr     esi, 6
0x140023171  mov     ecx, 0C00h
0x140023176  mov     eax, edx
0x140023178  and     esi, r13d
0x14002317b  and     eax, ecx
0x14002317d  mov     rbx, rdx
0x140023180  mov     edi, r13d
0x140023183  cmp     eax, ecx
0x140023185  jz      short loc_14002318F
0x140023187  test    esi, esi
0x140023189  jnz     short loc_14002318F
0x14002318b  xor     ebp, ebp
0x14002318d  jmp     short loc_1400231FD
0x14002318f  mov     r14, [r8+20h]
0x140023193  xor     ebp, ebp
0x140023195  cmp     eax, ecx
0x140023197  setz    bpl
0x14002319b  test    r14, r14
0x14002319e  jz      short loc_1400231FD
0x1400231a0  mov     rax, [r14]
0x1400231a3  test    rax, rax
0x1400231a6  jz      short loc_1400231EE
0x1400231a8  cmp     byte ptr [rax+1Eh], 0
0x1400231ac  jnz     short loc_1400231D9
0x1400231ae  cmp     byte ptr [rax+1Dh], 0
0x1400231b2  jnz     short loc_1400231D9
0x1400231b4  mov     rcx, [rax]
0x1400231b7  mov     rdx, rax
0x1400231ba  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x1400231bf  test    edi, edi
0x1400231c1  jz      short loc_1400231CD
0x1400231c3  test    r13b, al
0x1400231c6  jz      short loc_1400231CD
0x1400231c8  mov     edi, r13d
0x1400231cb  jmp     short loc_1400231CF
0x1400231cd  xor     edi, edi
0x1400231cf  add     r14, 8
0x1400231d3  test    edi, edi
0x1400231d5  jnz     short loc_1400231A0
0x1400231d7  jmp     short loc_1400231EE
0x1400231d9  test    edi, edi
0x1400231db  jz      short loc_1400231EC
0x1400231dd  cmp     byte ptr [rax+1Fh], 0
0x1400231e1  jz      short loc_1400231EC
0x1400231e3  mov     edi, r13d
0x1400231e6  add     r14, 8
0x1400231ea  jmp     short loc_1400231A0
0x1400231ec  xor     edi, edi
0x1400231ee  test    esi, esi
0x1400231f0  jz      short loc_1400231FB
0x1400231f2  test    edi, edi
0x1400231f4  jz      short loc_1400231FB
0x1400231f6  mov     esi, r13d
0x1400231f9  jmp     short loc_1400231FD
0x1400231fb  xor     esi, esi
0x1400231fd  mov     edx, ebx
0x1400231ff  and     edx, 0FFFFFFFEh
0x140023202  or      edx, esi
0x140023204  test    ebp, ebp
0x140023206  jz      short loc_140023210
0x140023208  test    edi, edi
0x14002320a  jnz     short loc_140023210
0x14002320c  btr     edx, 0Ah
0x140023210  mov     eax, ebx
0x140023212  mov     ecx, edx
0x140023214  and     eax, r13d
0x140023217  and     ecx, 0FFFFFFCFh
0x14002321a  cmp     eax, esi
0x14002321c  mov     eax, ebx
0x14002321e  cmovz   ecx, edx
0x140023221  btr     ecx, 9
0x140023225  mov     dword ptr [rsp+48h+arg_0], ecx
0x140023229  lock cmpxchg [r15], ecx
0x14002322e  jz      short loc_140023234
0x140023230  mov     ebx, eax
0x140023232  jmp     short loc_1400231FD
0x140023234  mov     rax, [rsp+48h+arg_0]
0x140023239  mov     rbx, [rsp+48h+arg_8]
0x14002323e  mov     rbp, [rsp+48h+arg_10]
0x140023243  add     rsp, 20h
0x140023247  pop     r15
0x140023249  pop     r14
0x14002324b  pop     r13
0x14002324d  pop     rdi
0x14002324e  pop     rsi
0x14002324f  retn
```
