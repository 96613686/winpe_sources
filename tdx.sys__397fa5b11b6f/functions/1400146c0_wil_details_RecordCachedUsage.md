# wil_details_RecordCachedUsage

- ea: `0x1400146c0`
- end: `0x14001480e`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400232f0`

## callees

- `0x1400146c0`
- `0x1400184b0`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400147ef`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400147ef`

## pseudocode

```c
_DWORD *__fastcall wil_details_RecordCachedUsage(int a1, __int64 a2)
{
  unsigned __int32 v3; // ecx
  int v4; // r8d
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  unsigned int v7; // eax
  char *v8; // rdx
  _DWORD *result; // rax
  _DWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  char v11; // [rsp+28h] [rbp-40h] BYREF

  _m_prefetchw((const void *)a2);
  v3 = _InterlockedAnd((volatile signed __int32 *)a2, 0xFFC0401E);
  v4 = (v3 >> 1) & 0xF;
  if ( v4 )
  {
    _m_prefetchw((const void *)(a2 + 4));
    v5 = *(_DWORD *)(a2 + 4);
    do
    {
      v6 = v5;
      v5 = _InterlockedCompareExchange((volatile signed __int32 *)(a2 + 4), v4 | v5, v5);
    }
    while ( v6 != v5 );
    v7 = v4 & ~v5;
  }
  else
  {
    v7 = 0;
  }
  if ( (v7 & 1) != 0 )
  {
    v10[0] = a1;
    v8 = &v11;
    v10[1] = 65538;
  }
  else
  {
    v8 = (char *)v10;
  }
  if ( (v7 & 2) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_DWORD *)v8 + 1) = 65542;
    v8 += 8;
  }
  if ( (v7 & 4) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_DWORD *)v8 + 1) = 65539;
    v8 += 8;
  }
  if ( v7 >= 8 )
  {
    *(_DWORD *)v8 = a1;
    *((_DWORD *)v8 + 1) = 65543;
    v8 += 8;
  }
  if ( ((v3 >> 5) & 0x1FF) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 3) = (v3 >> 5) & 0x1FF;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 14) & 1);
    v8 += 8;
  }
  if ( ((v3 >> 15) & 0x7F) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 3) = (v3 >> 15) & 0x7F;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 22) & 1) + 1;
    v8 += 8;
  }
  result = v10;
  if ( (v8 - (char *)v10) >> 3 > 0 )
    return (_DWORD *)RtlRecordFeatureUsage(v10);
  return result;
}

```

## disassembly

```asm
0x1400146c0  sub     rsp, 68h
0x1400146c4  mov     rax, cs:__security_cookie
0x1400146cb  xor     rax, rsp
0x1400146ce  mov     [rsp+68h+var_18], rax
0x1400146d3  mov     r9, rdx
0x1400146d6  mov     r10d, ecx
0x1400146d9  prefetchw byte ptr [rdx]
0x1400146dc  mov     eax, [rdx]
0x1400146de  mov     r8d, eax
0x1400146e1  and     r8d, 0FFC0401Eh
0x1400146e8  lock cmpxchg [rdx], r8d
0x1400146ed  jnz     short loc_1400146DE
0x1400146ef  mov     r8d, eax
0x1400146f2  mov     ecx, eax
0x1400146f4  shr     r8d, 1
0x1400146f7  and     r8d, 0Fh
0x1400146fb  jz      short loc_140014718
0x1400146fd  prefetchw byte ptr [rdx+4]
0x140014701  mov     eax, [rdx+4]
0x140014704  mov     edx, eax
0x140014706  or      edx, r8d
0x140014709  lock cmpxchg [r9+4], edx
0x14001470f  jnz     short loc_140014704
0x140014711  not     eax
0x140014713  and     eax, r8d
0x140014716  jmp     short loc_14001471B
0x140014718  mov     eax, r8d
0x14001471b  mov     r8d, 2
0x140014721  lea     r9d, [r8-1]
0x140014725  test    r9b, al
0x140014728  jz      short loc_14001473E
0x14001472a  mov     [rsp+68h+var_48], r10d
0x14001472f  lea     rdx, [rsp+68h+var_40]
0x140014734  mov     [rsp+68h+var_44], 10002h
0x14001473c  jmp     short loc_140014743
0x14001473e  lea     rdx, [rsp+68h+var_48]
0x140014743  test    r8b, al
0x140014746  jz      short loc_140014756
0x140014748  mov     [rdx], r10d
0x14001474b  mov     dword ptr [rdx+4], 10006h
0x140014752  add     rdx, 8
0x140014756  test    al, 4
0x140014758  jz      short loc_140014768
0x14001475a  mov     [rdx], r10d
0x14001475d  mov     dword ptr [rdx+4], 10003h
0x140014764  add     rdx, 8
0x140014768  cmp     eax, 8
0x14001476b  jb      short loc_14001477B
0x14001476d  mov     [rdx], r10d
0x140014770  mov     dword ptr [rdx+4], 10007h
0x140014777  add     rdx, 8
0x14001477b  mov     r8d, ecx
0x14001477e  mov     r11d, 1FFh
0x140014784  shr     r8d, 5
0x140014788  test    r11d, r8d
0x14001478b  jz      short loc_1400147AE
0x14001478d  and     r8w, r11w
0x140014791  mov     [rdx], r10d
0x140014794  mov     eax, ecx
0x140014796  mov     [rdx+6], r8w
0x14001479b  shr     eax, 0Eh
0x14001479e  and     ax, r9w
0x1400147a2  shl     ax, 2
0x1400147a6  mov     [rdx+4], ax
0x1400147aa  add     rdx, 8
0x1400147ae  mov     eax, ecx
0x1400147b0  shr     eax, 0Fh
0x1400147b3  test    al, 7Fh
0x1400147b5  jz      short loc_1400147D9
0x1400147b7  shr     ecx, 16h
0x1400147ba  and     ax, 7Fh
0x1400147be  and     cx, r9w
0x1400147c2  mov     [rdx], r10d
0x1400147c5  shl     cx, 2
0x1400147c9  add     cx, r9w
0x1400147cd  mov     [rdx+6], ax
0x1400147d1  mov     [rdx+4], cx
0x1400147d5  add     rdx, 8
0x1400147d9  lea     rax, [rsp+68h+var_48]
0x1400147de  sub     rdx, rax
0x1400147e1  sar     rdx, 3
0x1400147e5  test    rdx, rdx
0x1400147e8  jle     short loc_1400147FB
0x1400147ea  lea     rcx, [rsp+68h+var_48]
0x1400147ef  call    cs:__imp_RtlRecordFeatureUsage
0x1400147f6  nop     dword ptr [rax+rax+00h]
0x1400147fb  mov     rcx, [rsp+68h+var_18]
0x140014800  xor     rcx, rsp; StackCookie
0x140014803  call    __security_check_cookie
0x140014808  add     rsp, 68h
0x14001480c  retn
```
