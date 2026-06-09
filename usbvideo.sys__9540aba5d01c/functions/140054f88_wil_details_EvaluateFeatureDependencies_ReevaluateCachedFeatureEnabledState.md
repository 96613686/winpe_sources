# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140054f88`
- end: `0x14005503e`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140054f4c`

## callees

- `0x140054f4c`
- `0x140054f88`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        unsigned __int32 a2,
        __int64 a3)
{
  signed __int32 v3; // ebx
  int v5; // edi
  __int64 *v6; // rsi
  __int64 v7; // rax
  unsigned int v8; // edx
  signed __int32 v9; // eax
  __int64 v11; // [rsp+50h] [rbp+8h]

  HIDWORD(v11) = 0;
  v3 = a2;
  v5 = (a2 >> 6) & 1;
  if ( v5 )
  {
    v6 = *(__int64 **)(a3 + 32);
    if ( v6 )
    {
      while ( 1 )
      {
        v7 = *v6;
        if ( !*v6 )
          break;
        if ( *(_BYTE *)(v7 + 30) || *(_BYTE *)(v7 + 29) )
        {
          if ( !*(_BYTE *)(v7 + 31) )
          {
            v5 = 0;
            goto LABEL_11;
          }
          v5 = 1;
          ++v6;
        }
        else
        {
          v5 = (wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(*(_DWORD **)v7, *v6++) & 1) != 0;
          if ( !v5 )
            goto LABEL_11;
        }
      }
    }
  }
  while ( 1 )
  {
LABEL_11:
    v8 = v5 & 0xFFFFFFCF | v3 & 0xFFFFFFCE;
    if ( (v3 & 1) == v5 )
      v8 = v5 | v3 & 0xFFFFFFFE;
    v9 = _InterlockedCompareExchange(a1, v8 & 0xFFFFFDFF, v3);
    if ( v3 == v9 )
      break;
    v3 = v9;
  }
  LODWORD(v11) = v8 & 0xFFFFFDFF;
  return v11;
}

```

## disassembly

```asm
0x140054f88  push    rbx
0x140054f8a  push    rbp
0x140054f8b  push    rsi
0x140054f8c  push    rdi
0x140054f8d  sub     rsp, 28h
0x140054f91  mov     edi, edx
0x140054f93  mov     [rsp+48h+arg_0], 0
0x140054f9c  shr     edi, 6
0x140054f9f  mov     rbx, rdx
0x140054fa2  mov     rbp, rcx
0x140054fa5  and     edi, 1
0x140054fa8  jz      short loc_140055004
0x140054faa  mov     rsi, [r8+20h]
0x140054fae  test    rsi, rsi
0x140054fb1  jz      short loc_140055004
0x140054fb3  mov     rax, [rsi]
0x140054fb6  test    rax, rax
0x140054fb9  jz      short loc_140055004
0x140054fbb  cmp     byte ptr [rax+1Eh], 0
0x140054fbf  jnz     short loc_140054FED
0x140054fc1  cmp     byte ptr [rax+1Dh], 0
0x140054fc5  jnz     short loc_140054FED
0x140054fc7  mov     rcx, [rax]
0x140054fca  mov     rdx, rax
0x140054fcd  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140054fd2  test    edi, edi
0x140054fd4  jz      short loc_140054FE1
0x140054fd6  test    al, 1
0x140054fd8  jz      short loc_140054FE1
0x140054fda  mov     edi, 1
0x140054fdf  jmp     short loc_140054FE3
0x140054fe1  xor     edi, edi
0x140054fe3  add     rsi, 8
0x140054fe7  test    edi, edi
0x140054fe9  jnz     short loc_140054FB3
0x140054feb  jmp     short loc_140055004
0x140054fed  test    edi, edi
0x140054fef  jz      short loc_140055002
0x140054ff1  cmp     byte ptr [rax+1Fh], 0
0x140054ff5  jz      short loc_140055002
0x140054ff7  mov     edi, 1
0x140054ffc  add     rsi, 8
0x140055000  jmp     short loc_140054FB3
0x140055002  xor     edi, edi
0x140055004  mov     ecx, ebx
0x140055006  mov     eax, ebx
0x140055008  and     ecx, 0FFFFFFFEh
0x14005500b  and     eax, 1
0x14005500e  or      ecx, edi
0x140055010  mov     edx, ecx
0x140055012  and     edx, 0FFFFFFCFh
0x140055015  cmp     eax, edi
0x140055017  mov     eax, ebx
0x140055019  cmovz   edx, ecx
0x14005501c  btr     edx, 9
0x140055020  mov     dword ptr [rsp+48h+arg_0], edx
0x140055024  lock cmpxchg [rbp+0], edx
0x140055029  jz      short loc_14005502F
0x14005502b  mov     ebx, eax
0x14005502d  jmp     short loc_140055004
0x14005502f  mov     rax, [rsp+48h+arg_0]
0x140055034  add     rsp, 28h
0x140055038  pop     rdi
0x140055039  pop     rsi
0x14005503a  pop     rbp
0x14005503b  pop     rbx
0x14005503c  retn
```
