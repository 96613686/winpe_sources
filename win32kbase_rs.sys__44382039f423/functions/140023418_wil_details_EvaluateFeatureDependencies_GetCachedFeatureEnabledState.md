# wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState

- ea: `0x140023418`
- end: `0x140023546`
- name: `wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState`
- size: `302`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002332c`
- `0x140023418`

## callees

- `0x140023418`

## pseudocode

```c
__int64 __fastcall wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2)
{
  unsigned __int32 v2; // ebp
  int v4; // edi
  BOOL v5; // ebx
  BOOL v6; // esi
  _QWORD *v7; // r14
  __int64 v8; // rax
  char CachedFeatureEnabledState; // al
  unsigned int v10; // r8d
  unsigned int v11; // eax
  unsigned int v12; // edx
  unsigned __int32 v13; // eax
  __int64 v15; // [rsp+50h] [rbp+8h]

  v2 = *a1;
  v15 = *(unsigned int *)a1;
  if ( (*a1 & 0x200) != 0 )
  {
    HIDWORD(v15) = 0;
    v4 = (v2 >> 6) & 1;
    v5 = 1;
    if ( (*a1 & 0xC00) == 0xC00 || v4 )
    {
      v7 = *(_QWORD **)(a2 + 32);
      v6 = (*a1 & 0xC00) == 3072;
      if ( v7 )
      {
        while ( 1 )
        {
          v8 = *v7;
          if ( !*v7 )
            break;
          if ( *(_BYTE *)(v8 + 30) || *(_BYTE *)(v8 + 29) )
          {
            if ( !*(_BYTE *)(v8 + 31) )
            {
              v5 = 0;
              break;
            }
            v5 = 1;
            ++v7;
          }
          else
          {
            CachedFeatureEnabledState = wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(
                                          *(_QWORD *)v8,
                                          *v7);
            v5 = (CachedFeatureEnabledState & 1) != 0;
            ++v7;
            if ( (CachedFeatureEnabledState & 1) == 0 )
              break;
          }
        }
        v4 = v4 && v5;
      }
    }
    else
    {
      v6 = 0;
    }
    do
    {
      v10 = v4 | v2 & 0xFFFFFFFE;
      if ( v6 )
      {
        v11 = v4 & 0xFFFFFBFF | v2 & 0xFFFFFBFE;
        if ( v5 )
          v11 = v4 | v2 & 0xFFFFFFFE;
        v10 = v11;
      }
      v12 = v10 & 0xFFFFFFCF;
      v13 = v2;
      if ( (v2 & 1) == v4 )
        v12 = v10;
      LODWORD(v15) = v12 & 0xFFFFFDFF;
      v2 = _InterlockedCompareExchange(a1, v12 & 0xFFFFFDFF, v2);
    }
    while ( v13 != v2 );
  }
  return v15;
}

```

## disassembly

```asm
0x140023418  mov     [rsp+arg_8], rbx
0x14002341d  mov     [rsp+arg_10], rbp
0x140023422  push    rsi
0x140023423  push    rdi
0x140023424  push    r13
0x140023426  push    r14
0x140023428  push    r15
0x14002342a  sub     rsp, 20h
0x14002342e  mov     ebp, [rcx]
0x140023430  mov     r15, rcx
0x140023433  mov     [rsp+48h+arg_0], 0
0x14002343c  mov     dword ptr [rsp+48h+arg_0], ebp
0x140023440  bt      ebp, 9
0x140023444  jnb     loc_140023529
0x14002344a  mov     r13d, 1
0x140023450  mov     [rsp+48h+arg_0], 0
0x140023459  mov     ecx, 0C00h
0x14002345e  mov     edi, ebp
0x140023460  shr     edi, 6
0x140023463  mov     eax, ebp
0x140023465  and     edi, r13d
0x140023468  and     eax, ecx
0x14002346a  mov     ebx, r13d
0x14002346d  cmp     eax, ecx
0x14002346f  jz      short loc_140023479
0x140023471  test    edi, edi
0x140023473  jnz     short loc_140023479
0x140023475  xor     esi, esi
0x140023477  jmp     short loc_1400234E7
0x140023479  mov     r14, [rdx+20h]
0x14002347d  xor     esi, esi
0x14002347f  cmp     eax, ecx
0x140023481  setz    sil
0x140023485  test    r14, r14
0x140023488  jz      short loc_1400234E7
0x14002348a  mov     rax, [r14]
0x14002348d  test    rax, rax
0x140023490  jz      short loc_1400234D8
0x140023492  cmp     byte ptr [rax+1Eh], 0
0x140023496  jnz     short loc_1400234C3
0x140023498  cmp     byte ptr [rax+1Dh], 0
0x14002349c  jnz     short loc_1400234C3
0x14002349e  mov     rcx, [rax]
0x1400234a1  mov     rdx, rax
0x1400234a4  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x1400234a9  test    ebx, ebx
0x1400234ab  jz      short loc_1400234B7
0x1400234ad  test    r13b, al
0x1400234b0  jz      short loc_1400234B7
0x1400234b2  mov     ebx, r13d
0x1400234b5  jmp     short loc_1400234B9
0x1400234b7  xor     ebx, ebx
0x1400234b9  add     r14, 8
0x1400234bd  test    ebx, ebx
0x1400234bf  jnz     short loc_14002348A
0x1400234c1  jmp     short loc_1400234D8
0x1400234c3  test    ebx, ebx
0x1400234c5  jz      short loc_1400234D6
0x1400234c7  cmp     byte ptr [rax+1Fh], 0
0x1400234cb  jz      short loc_1400234D6
0x1400234cd  mov     ebx, r13d
0x1400234d0  add     r14, 8
0x1400234d4  jmp     short loc_14002348A
0x1400234d6  xor     ebx, ebx
0x1400234d8  test    edi, edi
0x1400234da  jz      short loc_1400234E5
0x1400234dc  test    ebx, ebx
0x1400234de  jz      short loc_1400234E5
0x1400234e0  mov     edi, r13d
0x1400234e3  jmp     short loc_1400234E7
0x1400234e5  xor     edi, edi
0x1400234e7  mov     r8d, ebp
0x1400234ea  and     r8d, 0FFFFFFFEh
0x1400234ee  or      r8d, edi
0x1400234f1  test    esi, esi
0x1400234f3  jz      short loc_140023505
0x1400234f5  mov     eax, r8d
0x1400234f8  btr     eax, 0Ah
0x1400234fc  test    ebx, ebx
0x1400234fe  cmovnz  eax, r8d
0x140023502  mov     r8d, eax
0x140023505  mov     ecx, ebp
0x140023507  mov     edx, r8d
0x14002350a  and     edx, 0FFFFFFCFh
0x14002350d  and     ecx, r13d
0x140023510  cmp     ecx, edi
0x140023512  mov     eax, ebp
0x140023514  cmovz   edx, r8d
0x140023518  btr     edx, 9
0x14002351c  mov     dword ptr [rsp+48h+arg_0], edx
0x140023520  lock cmpxchg [r15], edx
0x140023525  mov     ebp, eax
0x140023527  jnz     short loc_1400234E7
0x140023529  mov     rax, [rsp+48h+arg_0]
0x14002352e  mov     rbx, [rsp+48h+arg_8]
0x140023533  mov     rbp, [rsp+48h+arg_10]
0x140023538  add     rsp, 20h
0x14002353c  pop     r15
0x14002353e  pop     r14
0x140023540  pop     r13
0x140023542  pop     rdi
0x140023543  pop     rsi
0x140023544  retn
```
