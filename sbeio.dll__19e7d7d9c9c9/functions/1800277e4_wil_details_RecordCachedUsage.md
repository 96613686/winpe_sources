# wil_details_RecordCachedUsage

- ea: `0x1800277e4`
- end: `0x18002792a`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001fa08`

## callees

- `0x1800015f0`
- `0x180026dbc`
- `0x1800277e4`

## pseudocode

```c
void __fastcall wil_details_RecordCachedUsage(int a1, __int64 a2)
{
  unsigned __int32 v3; // ecx
  int v4; // r8d
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  unsigned int v7; // eax
  char *v8; // rdx
  unsigned __int64 v9; // r8
  __int64 v10; // rdx
  _DWORD v11[2]; // [rsp+20h] [rbp-48h] BYREF
  char v12; // [rsp+28h] [rbp-40h] BYREF

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
    v11[0] = a1;
    v8 = &v12;
    v11[1] = 65538;
  }
  else
  {
    v8 = (char *)v11;
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
  v9 = v3 >> 5;
  if ( (v9 & 0x1FF) != 0 )
  {
    LOWORD(v9) = v9 & 0x1FF;
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 3) = v9;
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
  v10 = (v8 - (char *)v11) >> 3;
  if ( v10 > 0 )
    wil::details::WilApi_RecordFeatureUsageReports((wil::details *)v11, (struct __WIL_RTL_FEATURE_USAGE_DATA *)v10, v9);
}

```

## disassembly

```asm
0x1800277e4  sub     rsp, 68h
0x1800277e8  mov     rax, cs:__security_cookie
0x1800277ef  xor     rax, rsp
0x1800277f2  mov     [rsp+68h+var_18], rax
0x1800277f7  mov     r9, rdx
0x1800277fa  mov     r10d, ecx
0x1800277fd  prefetchw byte ptr [rdx]
0x180027800  mov     eax, [rdx]
0x180027802  mov     r8d, eax
0x180027805  and     r8d, 0FFC0401Eh
0x18002780c  lock cmpxchg [rdx], r8d
0x180027811  jnz     short loc_180027802
0x180027813  mov     r8d, eax
0x180027816  mov     ecx, eax
0x180027818  shr     r8d, 1
0x18002781b  and     r8d, 0Fh
0x18002781f  jz      short loc_18002783C
0x180027821  prefetchw byte ptr [rdx+4]
0x180027825  mov     eax, [rdx+4]
0x180027828  mov     edx, eax
0x18002782a  or      edx, r8d
0x18002782d  lock cmpxchg [r9+4], edx
0x180027833  jnz     short loc_180027828
0x180027835  not     eax
0x180027837  and     eax, r8d
0x18002783a  jmp     short loc_18002783F
0x18002783c  mov     eax, r8d
0x18002783f  mov     r8d, 2
0x180027845  lea     r9d, [r8-1]
0x180027849  test    r9b, al
0x18002784c  jz      short loc_180027862
0x18002784e  mov     [rsp+68h+var_48], r10d
0x180027853  lea     rdx, [rsp+68h+var_40]
0x180027858  mov     [rsp+68h+var_44], 10002h
0x180027860  jmp     short loc_180027867
0x180027862  lea     rdx, [rsp+68h+var_48]
0x180027867  test    r8b, al
0x18002786a  jz      short loc_18002787A
0x18002786c  mov     [rdx], r10d
0x18002786f  mov     dword ptr [rdx+4], 10006h
0x180027876  add     rdx, 8
0x18002787a  test    al, 4
0x18002787c  jz      short loc_18002788C
0x18002787e  mov     [rdx], r10d
0x180027881  mov     dword ptr [rdx+4], 10003h
0x180027888  add     rdx, 8
0x18002788c  cmp     eax, 8
0x18002788f  jb      short loc_18002789F
0x180027891  mov     [rdx], r10d
0x180027894  mov     dword ptr [rdx+4], 10007h
0x18002789b  add     rdx, 8
0x18002789f  mov     r8d, ecx
0x1800278a2  mov     r11d, 1FFh
0x1800278a8  shr     r8d, 5
0x1800278ac  test    r11d, r8d
0x1800278af  jz      short loc_1800278D2
0x1800278b1  and     r8w, r11w; unsigned __int64
0x1800278b5  mov     [rdx], r10d
0x1800278b8  mov     eax, ecx
0x1800278ba  mov     [rdx+6], r8w
0x1800278bf  shr     eax, 0Eh
0x1800278c2  and     ax, r9w
0x1800278c6  shl     ax, 2
0x1800278ca  mov     [rdx+4], ax
0x1800278ce  add     rdx, 8
0x1800278d2  mov     eax, ecx
0x1800278d4  shr     eax, 0Fh
0x1800278d7  test    al, 7Fh
0x1800278d9  jz      short loc_1800278FD
0x1800278db  shr     ecx, 16h
0x1800278de  and     ax, 7Fh
0x1800278e2  and     cx, r9w
0x1800278e6  mov     [rdx], r10d
0x1800278e9  shl     cx, 2
0x1800278ed  add     cx, r9w
0x1800278f1  mov     [rdx+6], ax
0x1800278f5  mov     [rdx+4], cx
0x1800278f9  add     rdx, 8
0x1800278fd  lea     rax, [rsp+68h+var_48]
0x180027902  sub     rdx, rax
0x180027905  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180027909  test    rdx, rdx
0x18002790c  jle     short loc_180027918
0x18002790e  lea     rcx, [rsp+68h+var_48]; this
0x180027913  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180027918  mov     rcx, [rsp+68h+var_18]
0x18002791d  xor     rcx, rsp; StackCookie
0x180027920  call    __security_check_cookie
0x180027925  add     rsp, 68h
0x180027929  retn
```
