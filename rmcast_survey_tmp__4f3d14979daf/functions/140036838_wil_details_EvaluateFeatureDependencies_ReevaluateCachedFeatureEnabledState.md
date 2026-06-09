# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140036838`
- end: `0x1400368ee`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400367fc`

## callees

- `0x1400367fc`
- `0x140036838`

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
0x140036838  push    rbx
0x14003683a  push    rbp
0x14003683b  push    rsi
0x14003683c  push    rdi
0x14003683d  sub     rsp, 28h
0x140036841  mov     edi, edx
0x140036843  mov     [rsp+48h+arg_0], 0
0x14003684c  shr     edi, 6
0x14003684f  mov     rbx, rdx
0x140036852  mov     rbp, rcx
0x140036855  and     edi, 1
0x140036858  jz      short loc_1400368B4
0x14003685a  mov     rsi, [r8+20h]
0x14003685e  test    rsi, rsi
0x140036861  jz      short loc_1400368B4
0x140036863  mov     rax, [rsi]
0x140036866  test    rax, rax
0x140036869  jz      short loc_1400368B4
0x14003686b  cmp     byte ptr [rax+1Eh], 0
0x14003686f  jnz     short loc_14003689D
0x140036871  cmp     byte ptr [rax+1Dh], 0
0x140036875  jnz     short loc_14003689D
0x140036877  mov     rcx, [rax]
0x14003687a  mov     rdx, rax
0x14003687d  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x140036882  test    edi, edi
0x140036884  jz      short loc_140036891
0x140036886  test    al, 1
0x140036888  jz      short loc_140036891
0x14003688a  mov     edi, 1
0x14003688f  jmp     short loc_140036893
0x140036891  xor     edi, edi
0x140036893  add     rsi, 8
0x140036897  test    edi, edi
0x140036899  jnz     short loc_140036863
0x14003689b  jmp     short loc_1400368B4
0x14003689d  test    edi, edi
0x14003689f  jz      short loc_1400368B2
0x1400368a1  cmp     byte ptr [rax+1Fh], 0
0x1400368a5  jz      short loc_1400368B2
0x1400368a7  mov     edi, 1
0x1400368ac  add     rsi, 8
0x1400368b0  jmp     short loc_140036863
0x1400368b2  xor     edi, edi
0x1400368b4  mov     ecx, ebx
0x1400368b6  mov     eax, ebx
0x1400368b8  and     ecx, 0FFFFFFFEh
0x1400368bb  and     eax, 1
0x1400368be  or      ecx, edi
0x1400368c0  mov     edx, ecx
0x1400368c2  and     edx, 0FFFFFFCFh
0x1400368c5  cmp     eax, edi
0x1400368c7  mov     eax, ebx
0x1400368c9  cmovz   edx, ecx
0x1400368cc  btr     edx, 9
0x1400368d0  mov     dword ptr [rsp+48h+arg_0], edx
0x1400368d4  lock cmpxchg [rbp+0], edx
0x1400368d9  jz      short loc_1400368DF
0x1400368db  mov     ebx, eax
0x1400368dd  jmp     short loc_1400368B4
0x1400368df  mov     rax, [rsp+48h+arg_0]
0x1400368e4  add     rsp, 28h
0x1400368e8  pop     rdi
0x1400368e9  pop     rsi
0x1400368ea  pop     rbp
0x1400368eb  pop     rbx
0x1400368ec  retn
```
