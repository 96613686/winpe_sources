# wil_details_RecordCachedUsage

- ea: `0x14001ed70`
- end: `0x14001eebe`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140055050`

## callees

- `0x14001ed70`
- `0x140040a30`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x14001ee9f`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x14001ee9f`

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
0x14001ed70  sub     rsp, 68h
0x14001ed74  mov     rax, cs:__security_cookie
0x14001ed7b  xor     rax, rsp
0x14001ed7e  mov     [rsp+68h+var_18], rax
0x14001ed83  mov     r9, rdx
0x14001ed86  mov     r10d, ecx
0x14001ed89  prefetchw byte ptr [rdx]
0x14001ed8c  mov     eax, [rdx]
0x14001ed8e  mov     r8d, eax
0x14001ed91  and     r8d, 0FFC0401Eh
0x14001ed98  lock cmpxchg [rdx], r8d
0x14001ed9d  jnz     short loc_14001ED8E
0x14001ed9f  mov     r8d, eax
0x14001eda2  mov     ecx, eax
0x14001eda4  shr     r8d, 1
0x14001eda7  and     r8d, 0Fh
0x14001edab  jz      short loc_14001EDC8
0x14001edad  prefetchw byte ptr [rdx+4]
0x14001edb1  mov     eax, [rdx+4]
0x14001edb4  mov     edx, eax
0x14001edb6  or      edx, r8d
0x14001edb9  lock cmpxchg [r9+4], edx
0x14001edbf  jnz     short loc_14001EDB4
0x14001edc1  not     eax
0x14001edc3  and     eax, r8d
0x14001edc6  jmp     short loc_14001EDCB
0x14001edc8  mov     eax, r8d
0x14001edcb  mov     r8d, 2
0x14001edd1  lea     r9d, [r8-1]
0x14001edd5  test    r9b, al
0x14001edd8  jz      short loc_14001EDEE
0x14001edda  mov     [rsp+68h+var_48], r10d
0x14001eddf  lea     rdx, [rsp+68h+var_40]
0x14001ede4  mov     [rsp+68h+var_44], 10002h
0x14001edec  jmp     short loc_14001EDF3
0x14001edee  lea     rdx, [rsp+68h+var_48]
0x14001edf3  test    r8b, al
0x14001edf6  jz      short loc_14001EE06
0x14001edf8  mov     [rdx], r10d
0x14001edfb  mov     dword ptr [rdx+4], 10006h
0x14001ee02  add     rdx, 8
0x14001ee06  test    al, 4
0x14001ee08  jz      short loc_14001EE18
0x14001ee0a  mov     [rdx], r10d
0x14001ee0d  mov     dword ptr [rdx+4], 10003h
0x14001ee14  add     rdx, 8
0x14001ee18  cmp     eax, 8
0x14001ee1b  jb      short loc_14001EE2B
0x14001ee1d  mov     [rdx], r10d
0x14001ee20  mov     dword ptr [rdx+4], 10007h
0x14001ee27  add     rdx, 8
0x14001ee2b  mov     r8d, ecx
0x14001ee2e  mov     r11d, 1FFh
0x14001ee34  shr     r8d, 5
0x14001ee38  test    r11d, r8d
0x14001ee3b  jz      short loc_14001EE5E
0x14001ee3d  and     r8w, r11w
0x14001ee41  mov     [rdx], r10d
0x14001ee44  mov     eax, ecx
0x14001ee46  mov     [rdx+6], r8w
0x14001ee4b  shr     eax, 0Eh
0x14001ee4e  and     ax, r9w
0x14001ee52  shl     ax, 2
0x14001ee56  mov     [rdx+4], ax
0x14001ee5a  add     rdx, 8
0x14001ee5e  mov     eax, ecx
0x14001ee60  shr     eax, 0Fh
0x14001ee63  test    al, 7Fh
0x14001ee65  jz      short loc_14001EE89
0x14001ee67  shr     ecx, 16h
0x14001ee6a  and     ax, 7Fh
0x14001ee6e  and     cx, r9w
0x14001ee72  mov     [rdx], r10d
0x14001ee75  shl     cx, 2
0x14001ee79  add     cx, r9w
0x14001ee7d  mov     [rdx+6], ax
0x14001ee81  mov     [rdx+4], cx
0x14001ee85  add     rdx, 8
0x14001ee89  lea     rax, [rsp+68h+var_48]
0x14001ee8e  sub     rdx, rax
0x14001ee91  sar     rdx, 3
0x14001ee95  test    rdx, rdx
0x14001ee98  jle     short loc_14001EEAB
0x14001ee9a  lea     rcx, [rsp+68h+var_48]
0x14001ee9f  call    cs:__imp_RtlRecordFeatureUsage
0x14001eea6  nop     dword ptr [rax+rax+00h]
0x14001eeab  mov     rcx, [rsp+68h+var_18]
0x14001eeb0  xor     rcx, rsp; StackCookie
0x14001eeb3  call    __security_check_cookie
0x14001eeb8  add     rsp, 68h
0x14001eebc  retn
```
