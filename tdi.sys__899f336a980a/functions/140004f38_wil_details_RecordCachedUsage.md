# wil_details_RecordCachedUsage

- ea: `0x140004f38`
- end: `0x140005086`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b460`

## callees

- `0x140004f38`
- `0x1400054b0`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x140005067`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x140005067`

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
0x140004f38  sub     rsp, 68h
0x140004f3c  mov     rax, cs:__security_cookie
0x140004f43  xor     rax, rsp
0x140004f46  mov     [rsp+68h+var_18], rax
0x140004f4b  mov     r9, rdx
0x140004f4e  mov     r10d, ecx
0x140004f51  prefetchw byte ptr [rdx]
0x140004f54  mov     eax, [rdx]
0x140004f56  mov     r8d, eax
0x140004f59  and     r8d, 0FFC0401Eh
0x140004f60  lock cmpxchg [rdx], r8d
0x140004f65  jnz     short loc_140004F56
0x140004f67  mov     r8d, eax
0x140004f6a  mov     ecx, eax
0x140004f6c  shr     r8d, 1
0x140004f6f  and     r8d, 0Fh
0x140004f73  jz      short loc_140004F90
0x140004f75  prefetchw byte ptr [rdx+4]
0x140004f79  mov     eax, [rdx+4]
0x140004f7c  mov     edx, eax
0x140004f7e  or      edx, r8d
0x140004f81  lock cmpxchg [r9+4], edx
0x140004f87  jnz     short loc_140004F7C
0x140004f89  not     eax
0x140004f8b  and     eax, r8d
0x140004f8e  jmp     short loc_140004F93
0x140004f90  mov     eax, r8d
0x140004f93  mov     r8d, 2
0x140004f99  lea     r9d, [r8-1]
0x140004f9d  test    r9b, al
0x140004fa0  jz      short loc_140004FB6
0x140004fa2  mov     [rsp+68h+var_48], r10d
0x140004fa7  lea     rdx, [rsp+68h+var_40]
0x140004fac  mov     [rsp+68h+var_44], 10002h
0x140004fb4  jmp     short loc_140004FBB
0x140004fb6  lea     rdx, [rsp+68h+var_48]
0x140004fbb  test    r8b, al
0x140004fbe  jz      short loc_140004FCE
0x140004fc0  mov     [rdx], r10d
0x140004fc3  mov     dword ptr [rdx+4], 10006h
0x140004fca  add     rdx, 8
0x140004fce  test    al, 4
0x140004fd0  jz      short loc_140004FE0
0x140004fd2  mov     [rdx], r10d
0x140004fd5  mov     dword ptr [rdx+4], 10003h
0x140004fdc  add     rdx, 8
0x140004fe0  cmp     eax, 8
0x140004fe3  jb      short loc_140004FF3
0x140004fe5  mov     [rdx], r10d
0x140004fe8  mov     dword ptr [rdx+4], 10007h
0x140004fef  add     rdx, 8
0x140004ff3  mov     r8d, ecx
0x140004ff6  mov     r11d, 1FFh
0x140004ffc  shr     r8d, 5
0x140005000  test    r11d, r8d
0x140005003  jz      short loc_140005026
0x140005005  and     r8w, r11w
0x140005009  mov     [rdx], r10d
0x14000500c  mov     eax, ecx
0x14000500e  mov     [rdx+6], r8w
0x140005013  shr     eax, 0Eh
0x140005016  and     ax, r9w
0x14000501a  shl     ax, 2
0x14000501e  mov     [rdx+4], ax
0x140005022  add     rdx, 8
0x140005026  mov     eax, ecx
0x140005028  shr     eax, 0Fh
0x14000502b  test    al, 7Fh
0x14000502d  jz      short loc_140005051
0x14000502f  shr     ecx, 16h
0x140005032  and     ax, 7Fh
0x140005036  and     cx, r9w
0x14000503a  mov     [rdx], r10d
0x14000503d  shl     cx, 2
0x140005041  add     cx, r9w
0x140005045  mov     [rdx+6], ax
0x140005049  mov     [rdx+4], cx
0x14000504d  add     rdx, 8
0x140005051  lea     rax, [rsp+68h+var_48]
0x140005056  sub     rdx, rax
0x140005059  sar     rdx, 3
0x14000505d  test    rdx, rdx
0x140005060  jle     short loc_140005073
0x140005062  lea     rcx, [rsp+68h+var_48]
0x140005067  call    cs:__imp_RtlRecordFeatureUsage
0x14000506e  nop     dword ptr [rax+rax+00h]
0x140005073  mov     rcx, [rsp+68h+var_18]
0x140005078  xor     rcx, rsp; StackCookie
0x14000507b  call    __security_check_cookie
0x140005080  add     rsp, 68h
0x140005084  retn
```
