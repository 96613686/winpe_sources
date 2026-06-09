# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140039350`
- end: `0x14003945d`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140039314`

## callees

- `0x140039314`
- `0x140039350`

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
0x140039350  mov     [rsp+arg_8], rbx
0x140039355  mov     [rsp+arg_10], rbp
0x14003935a  push    rsi
0x14003935b  push    rdi
0x14003935c  push    r13
0x14003935e  push    r14
0x140039360  push    r15
0x140039362  sub     rsp, 20h
0x140039366  mov     r13d, 1
0x14003936c  mov     [rsp+48h+arg_0], 0
0x140039375  mov     esi, edx
0x140039377  mov     r15, rcx
0x14003937a  shr     esi, 6
0x14003937d  mov     ecx, 0C00h
0x140039382  mov     eax, edx
0x140039384  and     esi, r13d
0x140039387  and     eax, ecx
0x140039389  mov     rbx, rdx
0x14003938c  mov     edi, r13d
0x14003938f  cmp     eax, ecx
0x140039391  jz      short loc_14003939B
0x140039393  test    esi, esi
0x140039395  jnz     short loc_14003939B
0x140039397  xor     ebp, ebp
0x140039399  jmp     short loc_140039409
0x14003939b  mov     r14, [r8+20h]
0x14003939f  xor     ebp, ebp
0x1400393a1  cmp     eax, ecx
0x1400393a3  setz    bpl
0x1400393a7  test    r14, r14
0x1400393aa  jz      short loc_140039409
0x1400393ac  mov     rax, [r14]
0x1400393af  test    rax, rax
0x1400393b2  jz      short loc_1400393FA
0x1400393b4  cmp     byte ptr [rax+1Eh], 0
0x1400393b8  jnz     short loc_1400393E5
0x1400393ba  cmp     byte ptr [rax+1Dh], 0
0x1400393be  jnz     short loc_1400393E5
0x1400393c0  mov     rcx, [rax]
0x1400393c3  mov     rdx, rax
0x1400393c6  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x1400393cb  test    edi, edi
0x1400393cd  jz      short loc_1400393D9
0x1400393cf  test    r13b, al
0x1400393d2  jz      short loc_1400393D9
0x1400393d4  mov     edi, r13d
0x1400393d7  jmp     short loc_1400393DB
0x1400393d9  xor     edi, edi
0x1400393db  add     r14, 8
0x1400393df  test    edi, edi
0x1400393e1  jnz     short loc_1400393AC
0x1400393e3  jmp     short loc_1400393FA
0x1400393e5  test    edi, edi
0x1400393e7  jz      short loc_1400393F8
0x1400393e9  cmp     byte ptr [rax+1Fh], 0
0x1400393ed  jz      short loc_1400393F8
0x1400393ef  mov     edi, r13d
0x1400393f2  add     r14, 8
0x1400393f6  jmp     short loc_1400393AC
0x1400393f8  xor     edi, edi
0x1400393fa  test    esi, esi
0x1400393fc  jz      short loc_140039407
0x1400393fe  test    edi, edi
0x140039400  jz      short loc_140039407
0x140039402  mov     esi, r13d
0x140039405  jmp     short loc_140039409
0x140039407  xor     esi, esi
0x140039409  mov     edx, ebx
0x14003940b  and     edx, 0FFFFFFFEh
0x14003940e  or      edx, esi
0x140039410  test    ebp, ebp
0x140039412  jz      short loc_14003941C
0x140039414  test    edi, edi
0x140039416  jnz     short loc_14003941C
0x140039418  btr     edx, 0Ah
0x14003941c  mov     eax, ebx
0x14003941e  mov     ecx, edx
0x140039420  and     eax, r13d
0x140039423  and     ecx, 0FFFFFFCFh
0x140039426  cmp     eax, esi
0x140039428  mov     eax, ebx
0x14003942a  cmovz   ecx, edx
0x14003942d  btr     ecx, 9
0x140039431  mov     dword ptr [rsp+48h+arg_0], ecx
0x140039435  lock cmpxchg [r15], ecx
0x14003943a  jz      short loc_140039440
0x14003943c  mov     ebx, eax
0x14003943e  jmp     short loc_140039409
0x140039440  mov     rax, [rsp+48h+arg_0]
0x140039445  mov     rbx, [rsp+48h+arg_8]
0x14003944a  mov     rbp, [rsp+48h+arg_10]
0x14003944f  add     rsp, 20h
0x140039453  pop     r15
0x140039455  pop     r14
0x140039457  pop     r13
0x140039459  pop     rdi
0x14003945a  pop     rsi
0x14003945b  retn
```
