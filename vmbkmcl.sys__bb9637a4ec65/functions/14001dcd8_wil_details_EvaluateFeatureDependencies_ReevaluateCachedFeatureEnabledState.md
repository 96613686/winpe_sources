# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x14001dcd8`
- end: `0x14001dde5`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001dc9c`

## callees

- `0x14001dc9c`
- `0x14001dcd8`

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
0x14001dcd8  mov     [rsp+arg_8], rbx
0x14001dcdd  mov     [rsp+arg_10], rbp
0x14001dce2  push    rsi
0x14001dce3  push    rdi
0x14001dce4  push    r13
0x14001dce6  push    r14
0x14001dce8  push    r15
0x14001dcea  sub     rsp, 20h
0x14001dcee  mov     r13d, 1
0x14001dcf4  mov     [rsp+48h+arg_0], 0
0x14001dcfd  mov     esi, edx
0x14001dcff  mov     r15, rcx
0x14001dd02  shr     esi, 6
0x14001dd05  mov     ecx, 0C00h
0x14001dd0a  mov     eax, edx
0x14001dd0c  and     esi, r13d
0x14001dd0f  and     eax, ecx
0x14001dd11  mov     rbx, rdx
0x14001dd14  mov     edi, r13d
0x14001dd17  cmp     eax, ecx
0x14001dd19  jz      short loc_14001DD23
0x14001dd1b  test    esi, esi
0x14001dd1d  jnz     short loc_14001DD23
0x14001dd1f  xor     ebp, ebp
0x14001dd21  jmp     short loc_14001DD91
0x14001dd23  mov     r14, [r8+20h]
0x14001dd27  xor     ebp, ebp
0x14001dd29  cmp     eax, ecx
0x14001dd2b  setz    bpl
0x14001dd2f  test    r14, r14
0x14001dd32  jz      short loc_14001DD91
0x14001dd34  mov     rax, [r14]
0x14001dd37  test    rax, rax
0x14001dd3a  jz      short loc_14001DD82
0x14001dd3c  cmp     byte ptr [rax+1Eh], 0
0x14001dd40  jnz     short loc_14001DD6D
0x14001dd42  cmp     byte ptr [rax+1Dh], 0
0x14001dd46  jnz     short loc_14001DD6D
0x14001dd48  mov     rcx, [rax]
0x14001dd4b  mov     rdx, rax
0x14001dd4e  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14001dd53  test    edi, edi
0x14001dd55  jz      short loc_14001DD61
0x14001dd57  test    r13b, al
0x14001dd5a  jz      short loc_14001DD61
0x14001dd5c  mov     edi, r13d
0x14001dd5f  jmp     short loc_14001DD63
0x14001dd61  xor     edi, edi
0x14001dd63  add     r14, 8
0x14001dd67  test    edi, edi
0x14001dd69  jnz     short loc_14001DD34
0x14001dd6b  jmp     short loc_14001DD82
0x14001dd6d  test    edi, edi
0x14001dd6f  jz      short loc_14001DD80
0x14001dd71  cmp     byte ptr [rax+1Fh], 0
0x14001dd75  jz      short loc_14001DD80
0x14001dd77  mov     edi, r13d
0x14001dd7a  add     r14, 8
0x14001dd7e  jmp     short loc_14001DD34
0x14001dd80  xor     edi, edi
0x14001dd82  test    esi, esi
0x14001dd84  jz      short loc_14001DD8F
0x14001dd86  test    edi, edi
0x14001dd88  jz      short loc_14001DD8F
0x14001dd8a  mov     esi, r13d
0x14001dd8d  jmp     short loc_14001DD91
0x14001dd8f  xor     esi, esi
0x14001dd91  mov     edx, ebx
0x14001dd93  and     edx, 0FFFFFFFEh
0x14001dd96  or      edx, esi
0x14001dd98  test    ebp, ebp
0x14001dd9a  jz      short loc_14001DDA4
0x14001dd9c  test    edi, edi
0x14001dd9e  jnz     short loc_14001DDA4
0x14001dda0  btr     edx, 0Ah
0x14001dda4  mov     eax, ebx
0x14001dda6  mov     ecx, edx
0x14001dda8  and     eax, r13d
0x14001ddab  and     ecx, 0FFFFFFCFh
0x14001ddae  cmp     eax, esi
0x14001ddb0  mov     eax, ebx
0x14001ddb2  cmovz   ecx, edx
0x14001ddb5  btr     ecx, 9
0x14001ddb9  mov     dword ptr [rsp+48h+arg_0], ecx
0x14001ddbd  lock cmpxchg [r15], ecx
0x14001ddc2  jz      short loc_14001DDC8
0x14001ddc4  mov     ebx, eax
0x14001ddc6  jmp     short loc_14001DD91
0x14001ddc8  mov     rax, [rsp+48h+arg_0]
0x14001ddcd  mov     rbx, [rsp+48h+arg_8]
0x14001ddd2  mov     rbp, [rsp+48h+arg_10]
0x14001ddd7  add     rsp, 20h
0x14001dddb  pop     r15
0x14001dddd  pop     r14
0x14001dddf  pop     r13
0x14001dde1  pop     rdi
0x14001dde2  pop     rsi
0x14001dde3  retn
```
