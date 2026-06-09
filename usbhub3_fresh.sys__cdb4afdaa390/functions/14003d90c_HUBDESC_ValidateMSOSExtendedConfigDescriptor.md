# HUBDESC_ValidateMSOSExtendedConfigDescriptor

- ea: `0x14003d90c`
- end: `0x14003da98`
- name: `HUBDESC_ValidateMSOSExtendedConfigDescriptor`
- size: `396`
- prototype: `char __fastcall(_DWORD *, int, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140025160`

## callees

- `0x1400025a4`
- `0x1400067ac`
- `0x14003d90c`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_ValidateMSOSExtendedConfigDescriptor(_DWORD *a1, int a2, __int64 a3, int a4)
{
  __int64 v5; // rbx
  char v7; // di
  __int64 v8; // r9
  __int64 v9; // rdx
  char v10; // cl
  unsigned __int8 v11; // cl
  __int64 v12; // rdx
  char v13; // cl
  unsigned __int8 v14; // cl
  __int64 v15; // rdx
  char v17; // [rsp+28h] [rbp-50h]

  v5 = a3;
  v7 = 1;
  if ( a2 != *a1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = a2;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_dD(a4, a2, 5, 281, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v17, *a1);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(v5 + 24))(*(_QWORD *)(v5 + 40), 126);
    if ( *(_WORD *)v5 > 0x200u || *(_BYTE *)(v5 + 12) )
      v7 = 0;
  }
  LOBYTE(a3) = 0;
  v8 = 0x87FFFFFE03FFLL;
  v9 = 0;
  do
  {
    v10 = *((_BYTE *)a1 + v9 + 18);
    if ( v10 )
    {
      if ( (_BYTE)a3 || (v11 = v10 - 48, v11 > 0x2Fu) || !_bittest64(&v8, v11) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v9) = 2;
          WPP_RECORDER_SF_(a4, v9, 5, 283, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
        }
        v15 = 123;
LABEL_29:
        (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(v5 + 24))(*(_QWORD *)(v5 + 40), v15, a3, v8);
        v7 = 0;
        goto LABEL_30;
      }
    }
    else
    {
      LOBYTE(a3) = 1;
    }
    v9 = (unsigned int)(v9 + 1);
  }
  while ( (unsigned int)v9 < 8 );
  LOBYTE(a3) = 0;
  v12 = 0;
  do
  {
    v13 = *((_BYTE *)a1 + v12 + 26);
    if ( v13 )
    {
      if ( (_BYTE)a3 || (v14 = v13 - 48, v14 > 0x2Fu) || !_bittest64(&v8, v14) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 2;
          WPP_RECORDER_SF_(a4, v12, 5, 284, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
        }
        v15 = 124;
        goto LABEL_29;
      }
    }
    else
    {
      LOBYTE(a3) = 1;
    }
    v12 = (unsigned int)(v12 + 1);
  }
  while ( (unsigned int)v12 < 8 );
  if ( v7 )
    return v7;
LABEL_30:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_(a4, v12, 5, 285, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v7;
}

```

## disassembly

```asm
0x14003d90c  push    rbx
0x14003d90e  push    rbp
0x14003d90f  push    rsi
0x14003d910  push    rdi
0x14003d911  push    r12
0x14003d913  push    r14
0x14003d915  sub     rsp, 48h
0x14003d919  mov     eax, [rcx]
0x14003d91b  lea     rbp, WPP_RECORDER_INITIALIZED
0x14003d922  lea     r12, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003d929  mov     rsi, r9
0x14003d92c  mov     rbx, r8
0x14003d92f  mov     r14, rcx
0x14003d932  mov     dil, 1
0x14003d935  cmp     edx, eax
0x14003d937  jz      short loc_14003D98A
0x14003d939  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003d940  jz      short loc_14003D965
0x14003d942  mov     [rsp+78h+var_48], eax
0x14003d946  mov     r9d, 119h
0x14003d94c  mov     dword ptr [rsp+78h+var_50], edx
0x14003d950  mov     r8d, 5
0x14003d956  mov     dl, 2
0x14003d958  mov     [rsp+78h+var_58], r12
0x14003d95d  mov     rcx, rsi
0x14003d960  call    WPP_RECORDER_SF_dD
0x14003d965  mov     rax, [rbx+18h]
0x14003d969  mov     edx, 7Eh ; '~'
0x14003d96e  mov     rcx, [rbx+28h]
0x14003d972  call    _guard_dispatch_icall
0x14003d977  mov     eax, 200h
0x14003d97c  cmp     [rbx], ax
0x14003d97f  ja      short loc_14003D987
0x14003d981  cmp     byte ptr [rbx+0Ch], 0
0x14003d985  jz      short loc_14003D98A
0x14003d987  xor     dil, dil
0x14003d98a  xor     r8b, r8b
0x14003d98d  mov     r9, 87FFFFFE03FFh
0x14003d997  xor     edx, edx
0x14003d999  mov     cl, [rdx+r14+12h]
0x14003d99e  test    cl, cl
0x14003d9a0  jnz     short loc_14003D9A7
0x14003d9a2  mov     r8b, 1
0x14003d9a5  jmp     short loc_14003D9BD
0x14003d9a7  test    r8b, r8b
0x14003d9aa  jnz     short loc_14003DA2A
0x14003d9ac  sub     cl, 30h ; '0'
0x14003d9af  cmp     cl, 2Fh ; '/'
0x14003d9b2  ja      short loc_14003DA2A
0x14003d9b4  movzx   eax, cl
0x14003d9b7  bt      r9, rax
0x14003d9bb  jnb     short loc_14003DA2A
0x14003d9bd  inc     edx
0x14003d9bf  cmp     edx, 8
0x14003d9c2  jb      short loc_14003D999
0x14003d9c4  xor     r8b, r8b
0x14003d9c7  xor     edx, edx
0x14003d9c9  mov     cl, [rdx+r14+1Ah]
0x14003d9ce  test    cl, cl
0x14003d9d0  jnz     short loc_14003D9D7
0x14003d9d2  mov     r8b, 1
0x14003d9d5  jmp     short loc_14003D9ED
0x14003d9d7  test    r8b, r8b
0x14003d9da  jnz     short loc_14003D9FF
0x14003d9dc  sub     cl, 30h ; '0'
0x14003d9df  cmp     cl, 2Fh ; '/'
0x14003d9e2  ja      short loc_14003D9FF
0x14003d9e4  movzx   eax, cl
0x14003d9e7  bt      r9, rax
0x14003d9eb  jnb     short loc_14003D9FF
0x14003d9ed  inc     edx
0x14003d9ef  cmp     edx, 8
0x14003d9f2  jb      short loc_14003D9C9
0x14003d9f4  test    dil, dil
0x14003d9f7  jnz     loc_14003DA87
0x14003d9fd  jmp     short loc_14003DA63
0x14003d9ff  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003da06  jz      short loc_14003DA23
0x14003da08  mov     r9d, 11Ch
0x14003da0e  mov     [rsp+78h+var_58], r12
0x14003da13  mov     r8d, 5
0x14003da19  mov     dl, 2
0x14003da1b  mov     rcx, rsi
0x14003da1e  call    WPP_RECORDER_SF_
0x14003da23  mov     edx, 7Ch ; '|'
0x14003da28  jmp     short loc_14003DA53
0x14003da2a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003da31  jz      short loc_14003DA4E
0x14003da33  mov     r9d, 11Bh
0x14003da39  mov     [rsp+78h+var_58], r12
0x14003da3e  mov     r8d, 5
0x14003da44  mov     dl, 2
0x14003da46  mov     rcx, rsi
0x14003da49  call    WPP_RECORDER_SF_
0x14003da4e  mov     edx, 7Bh ; '{'
0x14003da53  mov     rcx, [rbx+28h]
0x14003da57  mov     rax, [rbx+18h]
0x14003da5b  call    _guard_dispatch_icall
0x14003da60  xor     dil, dil
0x14003da63  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003da6a  jz      short loc_14003DA87
0x14003da6c  mov     r9d, 11Dh
0x14003da72  mov     [rsp+78h+var_58], r12
0x14003da77  mov     r8d, 5
0x14003da7d  mov     dl, 2
0x14003da7f  mov     rcx, rsi
0x14003da82  call    WPP_RECORDER_SF_
0x14003da87  mov     al, dil
0x14003da8a  add     rsp, 48h
0x14003da8e  pop     r14
0x14003da90  pop     r12
0x14003da92  pop     rdi
0x14003da93  pop     rsi
0x14003da94  pop     rbp
0x14003da95  pop     rbx
0x14003da96  retn
```
