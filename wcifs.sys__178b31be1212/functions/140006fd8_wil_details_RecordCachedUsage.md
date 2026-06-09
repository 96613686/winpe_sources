# wil_details_RecordCachedUsage

- ea: `0x140006fd8`
- end: `0x140007126`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: `_DWORD *__fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140022770`

## callees

- `0x140006fd8`
- `0x140007c60`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x140007107`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x140007107`

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
0x140006fd8  sub     rsp, 68h
0x140006fdc  mov     rax, cs:__security_cookie
0x140006fe3  xor     rax, rsp
0x140006fe6  mov     [rsp+68h+var_18], rax
0x140006feb  mov     r9, rdx
0x140006fee  mov     r10d, ecx
0x140006ff1  prefetchw byte ptr [rdx]
0x140006ff4  mov     eax, [rdx]
0x140006ff6  mov     r8d, eax
0x140006ff9  and     r8d, 0FFC0401Eh
0x140007000  lock cmpxchg [rdx], r8d
0x140007005  jnz     short loc_140006FF6
0x140007007  mov     r8d, eax
0x14000700a  mov     ecx, eax
0x14000700c  shr     r8d, 1
0x14000700f  and     r8d, 0Fh
0x140007013  jz      short loc_140007030
0x140007015  prefetchw byte ptr [rdx+4]
0x140007019  mov     eax, [rdx+4]
0x14000701c  mov     edx, eax
0x14000701e  or      edx, r8d
0x140007021  lock cmpxchg [r9+4], edx
0x140007027  jnz     short loc_14000701C
0x140007029  not     eax
0x14000702b  and     eax, r8d
0x14000702e  jmp     short loc_140007033
0x140007030  mov     eax, r8d
0x140007033  mov     r8d, 2
0x140007039  lea     r9d, [r8-1]
0x14000703d  test    r9b, al
0x140007040  jz      short loc_140007056
0x140007042  mov     [rsp+68h+var_48], r10d
0x140007047  lea     rdx, [rsp+68h+var_40]
0x14000704c  mov     [rsp+68h+var_44], 10002h
0x140007054  jmp     short loc_14000705B
0x140007056  lea     rdx, [rsp+68h+var_48]
0x14000705b  test    r8b, al
0x14000705e  jz      short loc_14000706E
0x140007060  mov     [rdx], r10d
0x140007063  mov     dword ptr [rdx+4], 10006h
0x14000706a  add     rdx, 8
0x14000706e  test    al, 4
0x140007070  jz      short loc_140007080
0x140007072  mov     [rdx], r10d
0x140007075  mov     dword ptr [rdx+4], 10003h
0x14000707c  add     rdx, 8
0x140007080  cmp     eax, 8
0x140007083  jb      short loc_140007093
0x140007085  mov     [rdx], r10d
0x140007088  mov     dword ptr [rdx+4], 10007h
0x14000708f  add     rdx, 8
0x140007093  mov     r8d, ecx
0x140007096  mov     r11d, 1FFh
0x14000709c  shr     r8d, 5
0x1400070a0  test    r11d, r8d
0x1400070a3  jz      short loc_1400070C6
0x1400070a5  and     r8w, r11w
0x1400070a9  mov     [rdx], r10d
0x1400070ac  mov     eax, ecx
0x1400070ae  mov     [rdx+6], r8w
0x1400070b3  shr     eax, 0Eh
0x1400070b6  and     ax, r9w
0x1400070ba  shl     ax, 2
0x1400070be  mov     [rdx+4], ax
0x1400070c2  add     rdx, 8
0x1400070c6  mov     eax, ecx
0x1400070c8  shr     eax, 0Fh
0x1400070cb  test    al, 7Fh
0x1400070cd  jz      short loc_1400070F1
0x1400070cf  shr     ecx, 16h
0x1400070d2  and     ax, 7Fh
0x1400070d6  and     cx, r9w
0x1400070da  mov     [rdx], r10d
0x1400070dd  shl     cx, 2
0x1400070e1  add     cx, r9w
0x1400070e5  mov     [rdx+6], ax
0x1400070e9  mov     [rdx+4], cx
0x1400070ed  add     rdx, 8
0x1400070f1  lea     rax, [rsp+68h+var_48]
0x1400070f6  sub     rdx, rax
0x1400070f9  sar     rdx, 3
0x1400070fd  test    rdx, rdx
0x140007100  jle     short loc_140007113
0x140007102  lea     rcx, [rsp+68h+var_48]
0x140007107  call    cs:__imp_RtlRecordFeatureUsage
0x14000710e  nop     dword ptr [rax+rax+00h]
0x140007113  mov     rcx, [rsp+68h+var_18]
0x140007118  xor     rcx, rsp; StackCookie
0x14000711b  call    __security_check_cookie
0x140007120  add     rsp, 68h
0x140007124  retn
```
