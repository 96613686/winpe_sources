# wil_details_RecordCachedUsage

- ea: `0x1400023e8`
- end: `0x140002536`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: `_DWORD *__fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140010a00`

## callees

- `0x1400023e8`
- `0x140002750`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x140002517`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x140002517`

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
0x1400023e8  sub     rsp, 68h
0x1400023ec  mov     rax, cs:__security_cookie
0x1400023f3  xor     rax, rsp
0x1400023f6  mov     [rsp+68h+var_18], rax
0x1400023fb  mov     r9, rdx
0x1400023fe  mov     r10d, ecx
0x140002401  prefetchw byte ptr [rdx]
0x140002404  mov     eax, [rdx]
0x140002406  mov     r8d, eax
0x140002409  and     r8d, 0FFC0401Eh
0x140002410  lock cmpxchg [rdx], r8d
0x140002415  jnz     short loc_140002406
0x140002417  mov     r8d, eax
0x14000241a  mov     ecx, eax
0x14000241c  shr     r8d, 1
0x14000241f  and     r8d, 0Fh
0x140002423  jz      short loc_140002440
0x140002425  prefetchw byte ptr [rdx+4]
0x140002429  mov     eax, [rdx+4]
0x14000242c  mov     edx, eax
0x14000242e  or      edx, r8d
0x140002431  lock cmpxchg [r9+4], edx
0x140002437  jnz     short loc_14000242C
0x140002439  not     eax
0x14000243b  and     eax, r8d
0x14000243e  jmp     short loc_140002443
0x140002440  mov     eax, r8d
0x140002443  mov     r8d, 2
0x140002449  lea     r9d, [r8-1]
0x14000244d  test    r9b, al
0x140002450  jz      short loc_140002466
0x140002452  mov     [rsp+68h+var_48], r10d
0x140002457  lea     rdx, [rsp+68h+var_40]
0x14000245c  mov     [rsp+68h+var_44], 10002h
0x140002464  jmp     short loc_14000246B
0x140002466  lea     rdx, [rsp+68h+var_48]
0x14000246b  test    r8b, al
0x14000246e  jz      short loc_14000247E
0x140002470  mov     [rdx], r10d
0x140002473  mov     dword ptr [rdx+4], 10006h
0x14000247a  add     rdx, 8
0x14000247e  test    al, 4
0x140002480  jz      short loc_140002490
0x140002482  mov     [rdx], r10d
0x140002485  mov     dword ptr [rdx+4], 10003h
0x14000248c  add     rdx, 8
0x140002490  cmp     eax, 8
0x140002493  jb      short loc_1400024A3
0x140002495  mov     [rdx], r10d
0x140002498  mov     dword ptr [rdx+4], 10007h
0x14000249f  add     rdx, 8
0x1400024a3  mov     r8d, ecx
0x1400024a6  mov     r11d, 1FFh
0x1400024ac  shr     r8d, 5
0x1400024b0  test    r11d, r8d
0x1400024b3  jz      short loc_1400024D6
0x1400024b5  and     r8w, r11w
0x1400024b9  mov     [rdx], r10d
0x1400024bc  mov     eax, ecx
0x1400024be  mov     [rdx+6], r8w
0x1400024c3  shr     eax, 0Eh
0x1400024c6  and     ax, r9w
0x1400024ca  shl     ax, 2
0x1400024ce  mov     [rdx+4], ax
0x1400024d2  add     rdx, 8
0x1400024d6  mov     eax, ecx
0x1400024d8  shr     eax, 0Fh
0x1400024db  test    al, 7Fh
0x1400024dd  jz      short loc_140002501
0x1400024df  shr     ecx, 16h
0x1400024e2  and     ax, 7Fh
0x1400024e6  and     cx, r9w
0x1400024ea  mov     [rdx], r10d
0x1400024ed  shl     cx, 2
0x1400024f1  add     cx, r9w
0x1400024f5  mov     [rdx+6], ax
0x1400024f9  mov     [rdx+4], cx
0x1400024fd  add     rdx, 8
0x140002501  lea     rax, [rsp+68h+var_48]
0x140002506  sub     rdx, rax
0x140002509  sar     rdx, 3
0x14000250d  test    rdx, rdx
0x140002510  jle     short loc_140002523
0x140002512  lea     rcx, [rsp+68h+var_48]
0x140002517  call    cs:__imp_RtlRecordFeatureUsage
0x14000251e  nop     dword ptr [rax+rax+00h]
0x140002523  mov     rcx, [rsp+68h+var_18]
0x140002528  xor     rcx, rsp; StackCookie
0x14000252b  call    __security_check_cookie
0x140002530  add     rsp, 68h
0x140002534  retn
```
