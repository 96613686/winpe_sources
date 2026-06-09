# wil_details_RecordCachedUsage

- ea: `0x140015e90`
- end: `0x140015fde`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140039500`

## callees

- `0x140015e90`
- `0x14001bc30`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x140015fbf`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x140015fbf`

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
0x140015e90  sub     rsp, 68h
0x140015e94  mov     rax, cs:__security_cookie
0x140015e9b  xor     rax, rsp
0x140015e9e  mov     [rsp+68h+var_18], rax
0x140015ea3  mov     r9, rdx
0x140015ea6  mov     r10d, ecx
0x140015ea9  prefetchw byte ptr [rdx]
0x140015eac  mov     eax, [rdx]
0x140015eae  mov     r8d, eax
0x140015eb1  and     r8d, 0FFC0401Eh
0x140015eb8  lock cmpxchg [rdx], r8d
0x140015ebd  jnz     short loc_140015EAE
0x140015ebf  mov     r8d, eax
0x140015ec2  mov     ecx, eax
0x140015ec4  shr     r8d, 1
0x140015ec7  and     r8d, 0Fh
0x140015ecb  jz      short loc_140015EE8
0x140015ecd  prefetchw byte ptr [rdx+4]
0x140015ed1  mov     eax, [rdx+4]
0x140015ed4  mov     edx, eax
0x140015ed6  or      edx, r8d
0x140015ed9  lock cmpxchg [r9+4], edx
0x140015edf  jnz     short loc_140015ED4
0x140015ee1  not     eax
0x140015ee3  and     eax, r8d
0x140015ee6  jmp     short loc_140015EEB
0x140015ee8  mov     eax, r8d
0x140015eeb  mov     r8d, 2
0x140015ef1  lea     r9d, [r8-1]
0x140015ef5  test    r9b, al
0x140015ef8  jz      short loc_140015F0E
0x140015efa  mov     [rsp+68h+var_48], r10d
0x140015eff  lea     rdx, [rsp+68h+var_40]
0x140015f04  mov     [rsp+68h+var_44], 10002h
0x140015f0c  jmp     short loc_140015F13
0x140015f0e  lea     rdx, [rsp+68h+var_48]
0x140015f13  test    r8b, al
0x140015f16  jz      short loc_140015F26
0x140015f18  mov     [rdx], r10d
0x140015f1b  mov     dword ptr [rdx+4], 10006h
0x140015f22  add     rdx, 8
0x140015f26  test    al, 4
0x140015f28  jz      short loc_140015F38
0x140015f2a  mov     [rdx], r10d
0x140015f2d  mov     dword ptr [rdx+4], 10003h
0x140015f34  add     rdx, 8
0x140015f38  cmp     eax, 8
0x140015f3b  jb      short loc_140015F4B
0x140015f3d  mov     [rdx], r10d
0x140015f40  mov     dword ptr [rdx+4], 10007h
0x140015f47  add     rdx, 8
0x140015f4b  mov     r8d, ecx
0x140015f4e  mov     r11d, 1FFh
0x140015f54  shr     r8d, 5
0x140015f58  test    r11d, r8d
0x140015f5b  jz      short loc_140015F7E
0x140015f5d  and     r8w, r11w
0x140015f61  mov     [rdx], r10d
0x140015f64  mov     eax, ecx
0x140015f66  mov     [rdx+6], r8w
0x140015f6b  shr     eax, 0Eh
0x140015f6e  and     ax, r9w
0x140015f72  shl     ax, 2
0x140015f76  mov     [rdx+4], ax
0x140015f7a  add     rdx, 8
0x140015f7e  mov     eax, ecx
0x140015f80  shr     eax, 0Fh
0x140015f83  test    al, 7Fh
0x140015f85  jz      short loc_140015FA9
0x140015f87  shr     ecx, 16h
0x140015f8a  and     ax, 7Fh
0x140015f8e  and     cx, r9w
0x140015f92  mov     [rdx], r10d
0x140015f95  shl     cx, 2
0x140015f99  add     cx, r9w
0x140015f9d  mov     [rdx+6], ax
0x140015fa1  mov     [rdx+4], cx
0x140015fa5  add     rdx, 8
0x140015fa9  lea     rax, [rsp+68h+var_48]
0x140015fae  sub     rdx, rax
0x140015fb1  sar     rdx, 3
0x140015fb5  test    rdx, rdx
0x140015fb8  jle     short loc_140015FCB
0x140015fba  lea     rcx, [rsp+68h+var_48]
0x140015fbf  call    cs:__imp_RtlRecordFeatureUsage
0x140015fc6  nop     dword ptr [rax+rax+00h]
0x140015fcb  mov     rcx, [rsp+68h+var_18]
0x140015fd0  xor     rcx, rsp; StackCookie
0x140015fd3  call    __security_check_cookie
0x140015fd8  add     rsp, 68h
0x140015fdc  retn
```
