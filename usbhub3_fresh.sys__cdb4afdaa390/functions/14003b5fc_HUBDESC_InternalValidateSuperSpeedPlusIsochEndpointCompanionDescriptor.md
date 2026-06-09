# HUBDESC_InternalValidateSuperSpeedPlusIsochEndpointCompanionDescriptor

- ea: `0x14003b5fc`
- end: `0x14003b9a1`
- name: `HUBDESC_InternalValidateSuperSpeedPlusIsochEndpointCompanionDescriptor`
- size: `933`
- prototype: `__int64 __fastcall(char *, __int64, unsigned int *, int *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14003cce8`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400067ac`
- `0x14001cf04`
- `0x14002d940`
- `0x14003b5fc`
- `0x14003bf54`
- `0x14003f2fc`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBDESC_InternalValidateSuperSpeedPlusIsochEndpointCompanionDescriptor(
        char *a1,
        __int64 a2,
        unsigned int *a3,
        int *a4,
        __int64 a5)
{
  int v7; // r9d
  __int64 v8; // rbx
  unsigned int v10; // eax
  int v11; // r12d
  int v12; // r15d
  bool v13; // zf
  __int64 result; // rax
  unsigned int v15; // ecx
  int v16; // edx
  int v17; // r8d
  __int64 v18; // r10
  int v19; // eax
  __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-68h]
  __int64 v22; // [rsp+28h] [rbp-60h]
  int v23; // [rsp+28h] [rbp-60h]
  unsigned int v24; // [rsp+90h] [rbp+8h]
  int v25; // [rsp+98h] [rbp+10h] BYREF

  v7 = 0;
  v8 = a2;
  v25 = 0;
  if ( a4 )
  {
    if ( *(_BYTE *)(a2 + 48) )
      *a4 = 0;
  }
  else
  {
    a4 = &v25;
  }
  v10 = (unsigned __int8)*a1;
  v11 = a5;
  v12 = (_DWORD)a1 - *(_DWORD *)(a2 + 56);
  v13 = *(_DWORD *)(a2 + 4) == 3;
  *a3 = v10;
  if ( !v13 || !*(_DWORD *)(a2 + 16) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = v12;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(v11, a2, 5, 98, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v23);
    }
    result = (*(__int64 (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 205);
    *a4 = 2;
    goto LABEL_48;
  }
  v24 = *(_DWORD *)(a2 + 72) - v12;
  if ( (unsigned __int8)v10 < 8u )
  {
    result = (*(__int64 (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 208);
    if ( v24 >= 8 )
      *a3 = 8;
    v15 = *a3;
    *a4 = 2;
    if ( v15 < 8 )
    {
      *a4 = 1;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return result;
      LOBYTE(a2) = 2;
      result = WPP_RECORDER_SF_DDD(
                 v11,
                 a2,
                 (_DWORD)a3,
                 99,
                 (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                 *a1,
                 v12,
                 8);
LABEL_48:
      if ( !*a4 )
        return result;
      goto LABEL_49;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_DDDD(v11, a2, 5, 100, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *a1, v12, 8, v15);
    }
  }
  if ( (unsigned __int8)*a1 > 8u )
  {
    if ( HUBDESC_ShouldEnforceWin8ValidationMutable(v8) )
      *a4 = 2;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_DDD(v11, v16, v17, 101, v18, *a1, v12, 8);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 207);
  }
  v19 = *(_DWORD *)(v8 + 256);
  if ( (v19 & 8) != 0 )
  {
    *(_DWORD *)(v8 + 256) = v19 & 0xFFFFFFB7 | 0x40;
    if ( *a3 <= v24 )
    {
      if ( *((_WORD *)a1 + 1) )
      {
        if ( *(_BYTE *)(v8 + 15) )
          *a4 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_dD(
            v11,
            a2,
            5,
            104,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            v12,
            *((_WORD *)a1 + 1));
        }
        (*(void (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 210);
      }
      result = (unsigned int)(*((_DWORD *)a1 + 1) - 49153);
      if ( (unsigned int)result <= 0xFF3FFE )
        goto LABEL_48;
      if ( *(_BYTE *)(v8 + 15) )
        *a4 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Dddd(v11, a2, (_DWORD)a3, v7, v21, v12, *((_DWORD *)a1 + 1));
      v20 = 211;
    }
    else
    {
      if ( *(_WORD *)v8 > 0x200u || *(_BYTE *)(v8 + 12) )
        *a4 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v22) = v12;
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_d(v11, a2, 5, 103, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v22);
      }
      v20 = 209;
    }
    result = (*(__int64 (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), v20);
    goto LABEL_48;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v22) = v12;
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_d(v11, a2, 5, 102, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v22);
  }
  result = (*(__int64 (__fastcall **)(_QWORD, __int64))(v8 + 24))(*(_QWORD *)(v8 + 40), 206);
  *a4 = 2;
LABEL_49:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 2;
    return WPP_RECORDER_SF_(v11, a2, 5, 106, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14003b5fc  mov     rax, rsp
0x14003b5ff  mov     [rax+18h], rbx
0x14003b603  push    rbp
0x14003b604  push    rsi
0x14003b605  push    rdi
0x14003b606  push    r12
0x14003b608  push    r13
0x14003b60a  push    r14
0x14003b60c  push    r15
0x14003b60e  sub     rsp, 50h
0x14003b612  mov     rsi, r9
0x14003b615  mov     r13, r8
0x14003b618  xor     r9d, r9d
0x14003b61b  mov     rbx, rdx
0x14003b61e  mov     [rax+10h], r9d
0x14003b622  mov     r14, rcx
0x14003b625  test    rsi, rsi
0x14003b628  jnz     short loc_14003B630
0x14003b62a  lea     rsi, [rax+10h]
0x14003b62e  jmp     short loc_14003B639
0x14003b630  cmp     [rdx+30h], r9b
0x14003b634  jz      short loc_14003B639
0x14003b636  mov     [rsi], r9d
0x14003b639  movzx   eax, byte ptr [rcx]
0x14003b63c  lea     r10, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003b643  mov     r12, [rsp+88h+arg_20]
0x14003b64b  mov     r15d, r14d
0x14003b64e  sub     r15d, [rdx+38h]
0x14003b652  cmp     dword ptr [rdx+4], 3
0x14003b656  mov     [r8], eax
0x14003b659  jnz     loc_14003B910
0x14003b65f  cmp     [rdx+10h], r9d
0x14003b663  jz      loc_14003B910
0x14003b669  mov     ecx, [rdx+48h]
0x14003b66c  lea     rbp, WPP_RECORDER_INITIALIZED
0x14003b673  sub     ecx, r15d
0x14003b676  mov     edi, 2
0x14003b67b  mov     [rsp+88h+arg_0], ecx
0x14003b682  cmp     al, 8
0x14003b684  jnb     loc_14003B754
0x14003b68a  mov     rax, [rdx+18h]
0x14003b68e  mov     edx, 0D0h
0x14003b693  mov     rcx, [rbx+28h]
0x14003b697  call    _guard_dispatch_icall
0x14003b69c  cmp     [rsp+88h+arg_0], 8
0x14003b6a4  jb      short loc_14003B6AE
0x14003b6a6  mov     dword ptr [r13+0], 8
0x14003b6ae  mov     ecx, [r13+0]
0x14003b6b2  mov     [rsi], edi
0x14003b6b4  cmp     ecx, 8
0x14003b6b7  jnb     short loc_14003B70A
0x14003b6b9  mov     dword ptr [rsi], 1
0x14003b6bf  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003b6c6  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14003b6cd  jz      loc_14003B988
0x14003b6d3  movzx   eax, byte ptr [r14]
0x14003b6d7  mov     r9d, 63h ; 'c'
0x14003b6dd  mov     [rsp+88h+var_50], 8
0x14003b6e5  mov     dl, dil
0x14003b6e8  mov     [rsp+88h+var_58], r15d
0x14003b6ed  mov     rcx, r12
0x14003b6f0  mov     dword ptr [rsp+88h+var_60], eax
0x14003b6f4  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003b6fb  mov     [rsp+88h+var_68], rax
0x14003b700  call    WPP_RECORDER_SF_DDD
0x14003b705  jmp     loc_14003B956
0x14003b70a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003b711  jz      short loc_14003B74D
0x14003b713  movzx   eax, byte ptr [r14]
0x14003b717  mov     r9d, 64h ; 'd'
0x14003b71d  mov     [rsp+88h+var_48], ecx
0x14003b721  mov     dl, dil
0x14003b724  mov     [rsp+88h+var_50], 8
0x14003b72c  mov     rcx, r12
0x14003b72f  mov     [rsp+88h+var_58], r15d
0x14003b734  mov     dword ptr [rsp+88h+var_60], eax
0x14003b738  lea     r8d, [r9-5Fh]
0x14003b73c  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003b743  mov     [rsp+88h+var_68], rax
0x14003b748  call    WPP_RECORDER_SF_DDDD
0x14003b74d  lea     r10, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003b754  cmp     byte ptr [r14], 8
0x14003b758  jbe     short loc_14003B7AE
0x14003b75a  mov     rcx, rbx
0x14003b75d  call    HUBDESC_ShouldEnforceWin8ValidationMutable
0x14003b762  test    al, al
0x14003b764  jz      short loc_14003B768
0x14003b766  mov     [rsi], edi
0x14003b768  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003b76f  jz      short loc_14003B79C
0x14003b771  movzx   eax, byte ptr [r14]
0x14003b775  mov     r9d, 65h ; 'e'
0x14003b77b  mov     [rsp+88h+var_50], 8
0x14003b783  mov     dl, dil
0x14003b786  mov     [rsp+88h+var_58], r15d
0x14003b78b  mov     rcx, r12
0x14003b78e  mov     dword ptr [rsp+88h+var_60], eax
0x14003b792  mov     [rsp+88h+var_68], r10
0x14003b797  call    WPP_RECORDER_SF_DDD
0x14003b79c  mov     rax, [rbx+18h]
0x14003b7a0  mov     edx, 0CFh
0x14003b7a5  mov     rcx, [rbx+28h]
0x14003b7a9  call    _guard_dispatch_icall
0x14003b7ae  mov     eax, [rbx+100h]
0x14003b7b4  test    al, 8
0x14003b7b6  jnz     short loc_14003B800
0x14003b7b8  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003b7bf  jz      short loc_14003B7E7
0x14003b7c1  mov     r9d, 66h ; 'f'
0x14003b7c7  mov     dword ptr [rsp+88h+var_60], r15d
0x14003b7cc  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003b7d3  mov     dl, dil
0x14003b7d6  mov     rcx, r12
0x14003b7d9  mov     [rsp+88h+var_68], rax
0x14003b7de  lea     r8d, [r9-61h]
0x14003b7e2  call    WPP_RECORDER_SF_d
0x14003b7e7  mov     rax, [rbx+18h]
0x14003b7eb  mov     edx, 0CEh
0x14003b7f0  mov     rcx, [rbx+28h]
0x14003b7f4  call    _guard_dispatch_icall
0x14003b7f9  mov     [rsi], edi
0x14003b7fb  jmp     loc_14003B95E
0x14003b800  and     eax, 0FFFFFFF7h
0x14003b803  or      eax, 40h
0x14003b806  mov     [rbx+100h], eax
0x14003b80c  mov     eax, [rsp+88h+arg_0]
0x14003b813  cmp     [r13+0], eax
0x14003b817  jbe     short loc_14003B874
0x14003b819  mov     eax, 200h
0x14003b81e  xor     r13d, r13d
0x14003b821  cmp     [rbx], ax
0x14003b824  ja      short loc_14003B82C
0x14003b826  cmp     [rbx+0Ch], r13b
0x14003b82a  jz      short loc_14003B82E
0x14003b82c  mov     [rsi], edi
0x14003b82e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003b835  jz      short loc_14003B85D
0x14003b837  mov     r9d, 67h ; 'g'
0x14003b83d  mov     dword ptr [rsp+88h+var_60], r15d
0x14003b842  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003b849  mov     dl, dil
0x14003b84c  mov     rcx, r12
0x14003b84f  mov     [rsp+88h+var_68], rax
0x14003b854  lea     r8d, [r9-62h]
0x14003b858  call    WPP_RECORDER_SF_d
0x14003b85d  mov     edx, 0D1h
0x14003b862  mov     rax, [rbx+18h]
0x14003b866  mov     rcx, [rbx+28h]
0x14003b86a  call    _guard_dispatch_icall
0x14003b86f  jmp     loc_14003B959
0x14003b874  xor     r13d, r13d
0x14003b877  cmp     [r14+2], r13w
0x14003b87c  jz      short loc_14003B8D0
0x14003b87e  cmp     [rbx+0Fh], r13b
0x14003b882  jz      short loc_14003B886
0x14003b884  mov     [rsi], edi
0x14003b886  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003b88d  jz      short loc_14003B8BE
0x14003b88f  movzx   eax, word ptr [r14+2]
0x14003b894  mov     r9d, 68h ; 'h'
0x14003b89a  mov     [rsp+88h+var_58], eax
0x14003b89e  mov     dl, dil
0x14003b8a1  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003b8a8  mov     dword ptr [rsp+88h+var_60], r15d
0x14003b8ad  mov     rcx, r12
0x14003b8b0  mov     [rsp+88h+var_68], rax
0x14003b8b5  lea     r8d, [r9-63h]
0x14003b8b9  call    WPP_RECORDER_SF_dD
0x14003b8be  mov     rax, [rbx+18h]
0x14003b8c2  mov     edx, 0D2h
0x14003b8c7  mov     rcx, [rbx+28h]
0x14003b8cb  call    _guard_dispatch_icall
0x14003b8d0  mov     eax, [r14+4]
0x14003b8d4  sub     eax, 0C001h
0x14003b8d9  cmp     eax, 0FF3FFEh
0x14003b8de  jbe     short loc_14003B959
0x14003b8e0  cmp     [rbx+0Fh], r13b
0x14003b8e4  jz      short loc_14003B8E8
0x14003b8e6  mov     [rsi], edi
0x14003b8e8  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003b8ef  jz      short loc_14003B906
0x14003b8f1  mov     eax, [r14+4]
0x14003b8f5  mov     rcx, r12
0x14003b8f8  mov     [rsp+88h+var_58], eax
0x14003b8fc  mov     dword ptr [rsp+88h+var_60], r15d
0x14003b901  call    WPP_RECORDER_SF_Dddd
0x14003b906  mov     edx, 0D3h
0x14003b90b  jmp     loc_14003B862
0x14003b910  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003b917  mov     edi, 2
0x14003b91c  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14003b923  jz      short loc_14003B942
0x14003b925  lea     r9d, [rdi+60h]
0x14003b929  mov     dword ptr [rsp+88h+var_60], r15d
0x14003b92e  lea     r8d, [rdi+3]
0x14003b932  mov     [rsp+88h+var_68], r10
0x14003b937  mov     dl, dil
0x14003b93a  mov     rcx, r12
0x14003b93d  call    WPP_RECORDER_SF_d
0x14003b942  mov     rax, [rbx+18h]
0x14003b946  mov     edx, 0CDh
0x14003b94b  mov     rcx, [rbx+28h]
0x14003b94f  call    _guard_dispatch_icall
0x14003b954  mov     [rsi], edi
0x14003b956  xor     r13d, r13d
0x14003b959  cmp     [rsi], r13d
0x14003b95c  jz      short loc_14003B988
0x14003b95e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003b965  jz      short loc_14003B988
0x14003b967  mov     r9d, 6Ah ; 'j'
0x14003b96d  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003b974  mov     dl, dil
0x14003b977  mov     [rsp+88h+var_68], rax
0x14003b97c  mov     rcx, r12
0x14003b97f  lea     r8d, [r9-65h]
0x14003b983  call    WPP_RECORDER_SF_
0x14003b988  mov     rbx, [rsp+88h+arg_10]
0x14003b990  add     rsp, 50h
0x14003b994  pop     r15
0x14003b996  pop     r14
0x14003b998  pop     r13
0x14003b99a  pop     r12
0x14003b99c  pop     rdi
0x14003b99d  pop     rsi
0x14003b99e  pop     rbp
0x14003b99f  retn
```
