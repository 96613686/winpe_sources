# wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState

- ea: `0x140025948`
- end: `0x140025a55`
- name: `wil_details_EvaluateFeatureDependencies_ReevaluateCachedFeatureEnabledState`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002590c`

## callees

- `0x14002590c`
- `0x140025948`

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
0x140025948  mov     [rsp+arg_8], rbx
0x14002594d  mov     [rsp+arg_10], rbp
0x140025952  push    rsi
0x140025953  push    rdi
0x140025954  push    r13
0x140025956  push    r14
0x140025958  push    r15
0x14002595a  sub     rsp, 20h
0x14002595e  mov     r13d, 1
0x140025964  mov     [rsp+48h+arg_0], 0
0x14002596d  mov     esi, edx
0x14002596f  mov     r15, rcx
0x140025972  shr     esi, 6
0x140025975  mov     ecx, 0C00h
0x14002597a  mov     eax, edx
0x14002597c  and     esi, r13d
0x14002597f  and     eax, ecx
0x140025981  mov     rbx, rdx
0x140025984  mov     edi, r13d
0x140025987  cmp     eax, ecx
0x140025989  jz      short loc_140025993
0x14002598b  test    esi, esi
0x14002598d  jnz     short loc_140025993
0x14002598f  xor     ebp, ebp
0x140025991  jmp     short loc_140025A01
0x140025993  mov     r14, [r8+20h]
0x140025997  xor     ebp, ebp
0x140025999  cmp     eax, ecx
0x14002599b  setz    bpl
0x14002599f  test    r14, r14
0x1400259a2  jz      short loc_140025A01
0x1400259a4  mov     rax, [r14]
0x1400259a7  test    rax, rax
0x1400259aa  jz      short loc_1400259F2
0x1400259ac  cmp     byte ptr [rax+1Eh], 0
0x1400259b0  jnz     short loc_1400259DD
0x1400259b2  cmp     byte ptr [rax+1Dh], 0
0x1400259b6  jnz     short loc_1400259DD
0x1400259b8  mov     rcx, [rax]
0x1400259bb  mov     rdx, rax
0x1400259be  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x1400259c3  test    edi, edi
0x1400259c5  jz      short loc_1400259D1
0x1400259c7  test    r13b, al
0x1400259ca  jz      short loc_1400259D1
0x1400259cc  mov     edi, r13d
0x1400259cf  jmp     short loc_1400259D3
0x1400259d1  xor     edi, edi
0x1400259d3  add     r14, 8
0x1400259d7  test    edi, edi
0x1400259d9  jnz     short loc_1400259A4
0x1400259db  jmp     short loc_1400259F2
0x1400259dd  test    edi, edi
0x1400259df  jz      short loc_1400259F0
0x1400259e1  cmp     byte ptr [rax+1Fh], 0
0x1400259e5  jz      short loc_1400259F0
0x1400259e7  mov     edi, r13d
0x1400259ea  add     r14, 8
0x1400259ee  jmp     short loc_1400259A4
0x1400259f0  xor     edi, edi
0x1400259f2  test    esi, esi
0x1400259f4  jz      short loc_1400259FF
0x1400259f6  test    edi, edi
0x1400259f8  jz      short loc_1400259FF
0x1400259fa  mov     esi, r13d
0x1400259fd  jmp     short loc_140025A01
0x1400259ff  xor     esi, esi
0x140025a01  mov     edx, ebx
0x140025a03  and     edx, 0FFFFFFFEh
0x140025a06  or      edx, esi
0x140025a08  test    ebp, ebp
0x140025a0a  jz      short loc_140025A14
0x140025a0c  test    edi, edi
0x140025a0e  jnz     short loc_140025A14
0x140025a10  btr     edx, 0Ah
0x140025a14  mov     eax, ebx
0x140025a16  mov     ecx, edx
0x140025a18  and     eax, r13d
0x140025a1b  and     ecx, 0FFFFFFCFh
0x140025a1e  cmp     eax, esi
0x140025a20  mov     eax, ebx
0x140025a22  cmovz   ecx, edx
0x140025a25  btr     ecx, 9
0x140025a29  mov     dword ptr [rsp+48h+arg_0], ecx
0x140025a2d  lock cmpxchg [r15], ecx
0x140025a32  jz      short loc_140025A38
0x140025a34  mov     ebx, eax
0x140025a36  jmp     short loc_140025A01
0x140025a38  mov     rax, [rsp+48h+arg_0]
0x140025a3d  mov     rbx, [rsp+48h+arg_8]
0x140025a42  mov     rbp, [rsp+48h+arg_10]
0x140025a47  add     rsp, 20h
0x140025a4b  pop     r15
0x140025a4d  pop     r14
0x140025a4f  pop     r13
0x140025a51  pop     rdi
0x140025a52  pop     rsi
0x140025a53  retn
```
