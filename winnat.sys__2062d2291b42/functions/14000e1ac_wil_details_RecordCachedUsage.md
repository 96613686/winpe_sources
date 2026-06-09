# wil_details_RecordCachedUsage

- ea: `0x14000e1ac`
- end: `0x14000e2fa`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400301a0`

## callees

- `0x14000e1ac`
- `0x14001f320`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000e2db`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000e2db`

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
0x14000e1ac  sub     rsp, 68h
0x14000e1b0  mov     rax, cs:__security_cookie
0x14000e1b7  xor     rax, rsp
0x14000e1ba  mov     [rsp+68h+var_18], rax
0x14000e1bf  mov     r9, rdx
0x14000e1c2  mov     r10d, ecx
0x14000e1c5  prefetchw byte ptr [rdx]
0x14000e1c8  mov     eax, [rdx]
0x14000e1ca  mov     r8d, eax
0x14000e1cd  and     r8d, 0FFC0401Eh
0x14000e1d4  lock cmpxchg [rdx], r8d
0x14000e1d9  jnz     short loc_14000E1CA
0x14000e1db  mov     r8d, eax
0x14000e1de  mov     ecx, eax
0x14000e1e0  shr     r8d, 1
0x14000e1e3  and     r8d, 0Fh
0x14000e1e7  jz      short loc_14000E204
0x14000e1e9  prefetchw byte ptr [rdx+4]
0x14000e1ed  mov     eax, [rdx+4]
0x14000e1f0  mov     edx, eax
0x14000e1f2  or      edx, r8d
0x14000e1f5  lock cmpxchg [r9+4], edx
0x14000e1fb  jnz     short loc_14000E1F0
0x14000e1fd  not     eax
0x14000e1ff  and     eax, r8d
0x14000e202  jmp     short loc_14000E207
0x14000e204  mov     eax, r8d
0x14000e207  mov     r8d, 2
0x14000e20d  lea     r9d, [r8-1]
0x14000e211  test    r9b, al
0x14000e214  jz      short loc_14000E22A
0x14000e216  mov     [rsp+68h+var_48], r10d
0x14000e21b  lea     rdx, [rsp+68h+var_40]
0x14000e220  mov     [rsp+68h+var_44], 10002h
0x14000e228  jmp     short loc_14000E22F
0x14000e22a  lea     rdx, [rsp+68h+var_48]
0x14000e22f  test    r8b, al
0x14000e232  jz      short loc_14000E242
0x14000e234  mov     [rdx], r10d
0x14000e237  mov     dword ptr [rdx+4], 10006h
0x14000e23e  add     rdx, 8
0x14000e242  test    al, 4
0x14000e244  jz      short loc_14000E254
0x14000e246  mov     [rdx], r10d
0x14000e249  mov     dword ptr [rdx+4], 10003h
0x14000e250  add     rdx, 8
0x14000e254  cmp     eax, 8
0x14000e257  jb      short loc_14000E267
0x14000e259  mov     [rdx], r10d
0x14000e25c  mov     dword ptr [rdx+4], 10007h
0x14000e263  add     rdx, 8
0x14000e267  mov     r8d, ecx
0x14000e26a  mov     r11d, 1FFh
0x14000e270  shr     r8d, 5
0x14000e274  test    r11d, r8d
0x14000e277  jz      short loc_14000E29A
0x14000e279  and     r8w, r11w
0x14000e27d  mov     [rdx], r10d
0x14000e280  mov     eax, ecx
0x14000e282  mov     [rdx+6], r8w
0x14000e287  shr     eax, 0Eh
0x14000e28a  and     ax, r9w
0x14000e28e  shl     ax, 2
0x14000e292  mov     [rdx+4], ax
0x14000e296  add     rdx, 8
0x14000e29a  mov     eax, ecx
0x14000e29c  shr     eax, 0Fh
0x14000e29f  test    al, 7Fh
0x14000e2a1  jz      short loc_14000E2C5
0x14000e2a3  shr     ecx, 16h
0x14000e2a6  and     ax, 7Fh
0x14000e2aa  and     cx, r9w
0x14000e2ae  mov     [rdx], r10d
0x14000e2b1  shl     cx, 2
0x14000e2b5  add     cx, r9w
0x14000e2b9  mov     [rdx+6], ax
0x14000e2bd  mov     [rdx+4], cx
0x14000e2c1  add     rdx, 8
0x14000e2c5  lea     rax, [rsp+68h+var_48]
0x14000e2ca  sub     rdx, rax
0x14000e2cd  sar     rdx, 3
0x14000e2d1  test    rdx, rdx
0x14000e2d4  jle     short loc_14000E2E7
0x14000e2d6  lea     rcx, [rsp+68h+var_48]
0x14000e2db  call    cs:__imp_RtlRecordFeatureUsage
0x14000e2e2  nop     dword ptr [rax+rax+00h]
0x14000e2e7  mov     rcx, [rsp+68h+var_18]
0x14000e2ec  xor     rcx, rsp; StackCookie
0x14000e2ef  call    __security_check_cookie
0x14000e2f4  add     rsp, 68h
0x14000e2f8  retn
```
