# wil_details_RecordCachedUsage

- ea: `0x180010a84`
- end: `0x180010bcc`
- name: `wil_details_RecordCachedUsage`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a2b0`

## callees

- `0x180005680`
- `0x18000c0c4`
- `0x180010a84`

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
    v11[1] = 65538;
    v8 = &v12;
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
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 14) & 1);
    LOWORD(v9) = v9 & 0x1FF;
    *((_WORD *)v8 + 3) = v9;
    v8 += 8;
  }
  if ( ((v3 >> 15) & 0x7F) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 22) & 1) + 1;
    *((_WORD *)v8 + 3) = (v3 >> 15) & 0x7F;
    v8 += 8;
  }
  v10 = (v8 - (char *)v11) >> 3;
  if ( v10 > 0 )
    wil::details::WilApi_RecordFeatureUsageReports((wil::details *)v11, (struct __WIL_RTL_FEATURE_USAGE_DATA *)v10, v9);
}

```

## disassembly

```asm
0x180010a84  sub     rsp, 68h
0x180010a88  mov     rax, cs:__security_cookie
0x180010a8f  xor     rax, rsp
0x180010a92  mov     [rsp+68h+var_18], rax
0x180010a97  mov     r9, rdx
0x180010a9a  mov     r10d, ecx
0x180010a9d  prefetchw byte ptr [rdx]
0x180010aa0  mov     eax, [rdx]
0x180010aa2  mov     r8d, eax
0x180010aa5  and     r8d, 0FFC0401Eh
0x180010aac  lock cmpxchg [rdx], r8d
0x180010ab1  jnz     short loc_180010AA2
0x180010ab3  mov     ecx, eax
0x180010ab5  mov     r8d, eax
0x180010ab8  shr     r8d, 1
0x180010abb  and     r8d, 0Fh
0x180010abf  jz      short loc_180010ADC
0x180010ac1  prefetchw byte ptr [rdx+4]
0x180010ac5  mov     eax, [rdx+4]
0x180010ac8  mov     edx, eax
0x180010aca  or      edx, r8d
0x180010acd  lock cmpxchg [r9+4], edx
0x180010ad3  jnz     short loc_180010AC8
0x180010ad5  not     eax
0x180010ad7  and     eax, r8d
0x180010ada  jmp     short loc_180010ADF
0x180010adc  mov     eax, r8d
0x180010adf  mov     r8d, 2
0x180010ae5  lea     r9d, [r8-1]
0x180010ae9  test    r9b, al
0x180010aec  jz      short loc_180010B02
0x180010aee  mov     [rsp+68h+var_48], r10d
0x180010af3  mov     [rsp+68h+var_44], 10002h
0x180010afb  lea     rdx, [rsp+68h+var_40]
0x180010b00  jmp     short loc_180010B07
0x180010b02  lea     rdx, [rsp+68h+var_48]
0x180010b07  test    r8b, al
0x180010b0a  jz      short loc_180010B1A
0x180010b0c  mov     [rdx], r10d
0x180010b0f  mov     dword ptr [rdx+4], 10006h
0x180010b16  add     rdx, 8
0x180010b1a  test    al, 4
0x180010b1c  jz      short loc_180010B2C
0x180010b1e  mov     [rdx], r10d
0x180010b21  mov     dword ptr [rdx+4], 10003h
0x180010b28  add     rdx, 8
0x180010b2c  cmp     eax, 8
0x180010b2f  jb      short loc_180010B3F
0x180010b31  mov     [rdx], r10d
0x180010b34  mov     dword ptr [rdx+4], 10007h
0x180010b3b  add     rdx, 8
0x180010b3f  mov     r8d, ecx
0x180010b42  shr     r8d, 5
0x180010b46  mov     r11d, 1FFh
0x180010b4c  test    r11d, r8d
0x180010b4f  jz      short loc_180010B72
0x180010b51  mov     [rdx], r10d
0x180010b54  mov     eax, ecx
0x180010b56  shr     eax, 0Eh
0x180010b59  and     ax, r9w
0x180010b5d  shl     ax, 2
0x180010b61  mov     [rdx+4], ax
0x180010b65  and     r8w, r11w; unsigned __int64
0x180010b69  mov     [rdx+6], r8w
0x180010b6e  add     rdx, 8
0x180010b72  mov     eax, ecx
0x180010b74  shr     eax, 0Fh
0x180010b77  test    al, 7Fh
0x180010b79  jz      short loc_180010B9D
0x180010b7b  mov     [rdx], r10d
0x180010b7e  shr     ecx, 16h
0x180010b81  and     cx, r9w
0x180010b85  shl     cx, 2
0x180010b89  add     cx, r9w
0x180010b8d  mov     [rdx+4], cx
0x180010b91  and     ax, 7Fh
0x180010b95  mov     [rdx+6], ax
0x180010b99  add     rdx, 8
0x180010b9d  lea     rax, [rsp+68h+var_48]
0x180010ba2  sub     rdx, rax
0x180010ba5  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180010ba9  test    rdx, rdx
0x180010bac  jle     short loc_180010BB9
0x180010bae  lea     rcx, [rsp+68h+var_48]; this
0x180010bb3  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180010bb8  nop
0x180010bb9  mov     rcx, [rsp+68h+var_18]
0x180010bbe  xor     rcx, rsp; StackCookie
0x180010bc1  call    __security_check_cookie
0x180010bc6  add     rsp, 68h
0x180010bca  retn
```
