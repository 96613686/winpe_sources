# wil_details_RecordCachedUsage

- ea: `0x140010490`
- end: `0x1400105de`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001de80`

## callees

- `0x140010490`
- `0x140011e90`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400105bf`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400105bf`

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
0x140010490  sub     rsp, 68h
0x140010494  mov     rax, cs:__security_cookie
0x14001049b  xor     rax, rsp
0x14001049e  mov     [rsp+68h+var_18], rax
0x1400104a3  mov     r9, rdx
0x1400104a6  mov     r10d, ecx
0x1400104a9  prefetchw byte ptr [rdx]
0x1400104ac  mov     eax, [rdx]
0x1400104ae  mov     r8d, eax
0x1400104b1  and     r8d, 0FFC0401Eh
0x1400104b8  lock cmpxchg [rdx], r8d
0x1400104bd  jnz     short loc_1400104AE
0x1400104bf  mov     r8d, eax
0x1400104c2  mov     ecx, eax
0x1400104c4  shr     r8d, 1
0x1400104c7  and     r8d, 0Fh
0x1400104cb  jz      short loc_1400104E8
0x1400104cd  prefetchw byte ptr [rdx+4]
0x1400104d1  mov     eax, [rdx+4]
0x1400104d4  mov     edx, eax
0x1400104d6  or      edx, r8d
0x1400104d9  lock cmpxchg [r9+4], edx
0x1400104df  jnz     short loc_1400104D4
0x1400104e1  not     eax
0x1400104e3  and     eax, r8d
0x1400104e6  jmp     short loc_1400104EB
0x1400104e8  mov     eax, r8d
0x1400104eb  mov     r8d, 2
0x1400104f1  lea     r9d, [r8-1]
0x1400104f5  test    r9b, al
0x1400104f8  jz      short loc_14001050E
0x1400104fa  mov     [rsp+68h+var_48], r10d
0x1400104ff  lea     rdx, [rsp+68h+var_40]
0x140010504  mov     [rsp+68h+var_44], 10002h
0x14001050c  jmp     short loc_140010513
0x14001050e  lea     rdx, [rsp+68h+var_48]
0x140010513  test    r8b, al
0x140010516  jz      short loc_140010526
0x140010518  mov     [rdx], r10d
0x14001051b  mov     dword ptr [rdx+4], 10006h
0x140010522  add     rdx, 8
0x140010526  test    al, 4
0x140010528  jz      short loc_140010538
0x14001052a  mov     [rdx], r10d
0x14001052d  mov     dword ptr [rdx+4], 10003h
0x140010534  add     rdx, 8
0x140010538  cmp     eax, 8
0x14001053b  jb      short loc_14001054B
0x14001053d  mov     [rdx], r10d
0x140010540  mov     dword ptr [rdx+4], 10007h
0x140010547  add     rdx, 8
0x14001054b  mov     r8d, ecx
0x14001054e  mov     r11d, 1FFh
0x140010554  shr     r8d, 5
0x140010558  test    r11d, r8d
0x14001055b  jz      short loc_14001057E
0x14001055d  and     r8w, r11w
0x140010561  mov     [rdx], r10d
0x140010564  mov     eax, ecx
0x140010566  mov     [rdx+6], r8w
0x14001056b  shr     eax, 0Eh
0x14001056e  and     ax, r9w
0x140010572  shl     ax, 2
0x140010576  mov     [rdx+4], ax
0x14001057a  add     rdx, 8
0x14001057e  mov     eax, ecx
0x140010580  shr     eax, 0Fh
0x140010583  test    al, 7Fh
0x140010585  jz      short loc_1400105A9
0x140010587  shr     ecx, 16h
0x14001058a  and     ax, 7Fh
0x14001058e  and     cx, r9w
0x140010592  mov     [rdx], r10d
0x140010595  shl     cx, 2
0x140010599  add     cx, r9w
0x14001059d  mov     [rdx+6], ax
0x1400105a1  mov     [rdx+4], cx
0x1400105a5  add     rdx, 8
0x1400105a9  lea     rax, [rsp+68h+var_48]
0x1400105ae  sub     rdx, rax
0x1400105b1  sar     rdx, 3
0x1400105b5  test    rdx, rdx
0x1400105b8  jle     short loc_1400105CB
0x1400105ba  lea     rcx, [rsp+68h+var_48]
0x1400105bf  call    cs:__imp_RtlRecordFeatureUsage
0x1400105c6  nop     dword ptr [rax+rax+00h]
0x1400105cb  mov     rcx, [rsp+68h+var_18]
0x1400105d0  xor     rcx, rsp; StackCookie
0x1400105d3  call    __security_check_cookie
0x1400105d8  add     rsp, 68h
0x1400105dc  retn
```
