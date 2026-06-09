# KspCreatePersistedKeyInternal(unsigned __int64,unsigned __int64 *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x18001d030`
- end: `0x18001d4d8`
- name: `?KspCreatePersistedKeyInternal@@YAJ_KPEA_KPEBG2KK@Z`
- size: `1192`
- prototype: `int(unsigned __int64, unsigned __int64 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18002aa00`

## callees

- `0x180009e82`
- `0x18000a3c8`
- `0x18000a408`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180012b24`
- `0x1800135dc`
- `0x180013734`
- `0x18001423c`
- `0x18001ae5c`
- `0x18001d030`
- `0x18002b140`

## pseudocode

```c
__int64 __fastcall KspCreatePersistedKeyInternal(
        __int64 a1,
        unsigned __int64 *a2,
        wchar_t *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6)
{
  int v6; // r15d
  PVOID v9; // rcx
  unsigned int Handle; // esi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rcx
  char *v15; // rax
  char *v16; // rbp
  _DWORD *v17; // rdi
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  int v20; // edx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v26; // [rsp+28h] [rbp-70h]
  _DWORD v27[21]; // [rsp+44h] [rbp-54h] BYREF

  *(_QWORD *)&v27[1] = 0;
  v6 = 0;
  v27[0] = 0;
  if ( a2 && a3 )
  {
    if ( (a6 & 0xFFFFFF9F) != 0 )
    {
      WppTraceIndent(a1, 2u);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
          (_DWORD)WPP_pszIndent,
          a6);
      }
      WppTraceIndent((__int64)v9, 2u);
      Handle = -2146893815;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 12;
        v13 = 2148073481LL;
LABEL_67:
        WPP_SF_d(v11[2], v12, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, v13);
        return Handle;
      }
      return Handle;
    }
    Handle = HtGetHandle(a1, 3, &v27[1]);
    if ( Handle )
    {
      WppTraceIndent(v14, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
          (_DWORD)WPP_pszIndent,
          Handle);
      }
      return Handle;
    }
    v15 = (char *)MIDL_user_allocate(0x4C0u);
    v16 = v15;
    if ( !v15 )
    {
      Handle = -2146893810;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
          WPP_pszIndent);
      }
      return Handle;
    }
    memset_0(v15, 0, 0x4C0u);
    v17 = v16 + 1040;
    Handle = KsppTranslateAlgorithmToKeySpec(a3);
    if ( Handle )
    {
      WppTraceIndent(v18, 2u);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_62;
      }
      v20 = 15;
      goto LABEL_61;
    }
    if ( a5 )
    {
      if ( a5 == 1 )
      {
        if ( *v17 != 1 )
        {
          WppTraceIndent(v18, 2u);
          Handle = -2146893785;
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_62;
          }
          v22 = 17;
LABEL_47:
          WPP_SF_d(v21[2], v22, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, 2148073511LL);
          goto LABEL_62;
        }
      }
      else
      {
        if ( a5 != 2 )
        {
          WppTraceIndent(v18, 2u);
          Handle = -2146893785;
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_62;
          }
          v22 = 18;
          goto LABEL_47;
        }
        if ( *v17 == 1 )
        {
          *v17 = 2;
          goto LABEL_36;
        }
        if ( *v17 != 2 )
        {
          WppTraceIndent(v18, 2u);
          Handle = -2146893785;
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_62;
          }
          v22 = 16;
          goto LABEL_47;
        }
      }
    }
LABEL_36:
    if ( a4 )
    {
      Handle = KsppAnalyzeContainerName(a4, (unsigned __int16 *)v16 + 260, (unsigned __int16 *)v16, v26, (__int64)v27);
      if ( Handle )
      {
        WppTraceIndent(v23, 2u);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_62;
        }
        v20 = 19;
        goto LABEL_61;
      }
      v6 = v27[0];
    }
    if ( !v6 )
      memset_0(v16, 0, 0x104u);
    memset_0(v16 + 520, 0, 0x104u);
    *((_DWORD *)v16 + 266) = (*(_DWORD *)(*(_QWORD *)&v27[1] + 60LL) | a6) & 0x40;
    Handle = HtAddHandle(v16, 2, a2);
    if ( !Handle )
      return Handle;
    WppTraceIndent(v24, 2u);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_62:
      CspFreeH(v16);
      return Handle;
    }
    v20 = 20;
LABEL_61:
    WPP_SF_sd(
      v19[2],
      v20,
      (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
      (_DWORD)WPP_pszIndent,
      Handle);
    goto LABEL_62;
  }
  WppTraceIndent(a1, 2u);
  v13 = 2148073511LL;
  Handle = -2146893785;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = 10;
    goto LABEL_67;
  }
  return Handle;
}

```

## disassembly

```asm
0x18001d030  mov     rax, rsp
0x18001d033  mov     [rax+10h], rdx
0x18001d037  push    rbx
0x18001d038  push    rbp
0x18001d039  push    rsi
0x18001d03a  push    rdi
0x18001d03b  push    r12
0x18001d03d  push    r13
0x18001d03f  push    r14
0x18001d041  push    r15
0x18001d043  sub     rsp, 58h
0x18001d047  xor     r12d, r12d
0x18001d04a  mov     qword ptr [rax-50h], 0
0x18001d052  xor     r15d, r15d
0x18001d055  mov     [rax-58h], r12d
0x18001d059  mov     [rax-54h], r15d
0x18001d05d  mov     r13, r9
0x18001d060  mov     rbx, r8
0x18001d063  test    rdx, rdx
0x18001d066  jz      loc_18001D47F
0x18001d06c  test    rbx, rbx
0x18001d06f  jz      loc_18001D47F
0x18001d075  mov     r14d, [rsp+98h+arg_28]
0x18001d07d  test    r14d, 0FFFFFF9Fh
0x18001d084  jz      loc_18001D10F
0x18001d08a  lea     ebx, [r12+2]
0x18001d08f  mov     edx, ebx
0x18001d091  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d096  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d09d  lea     rdi, WPP_GLOBAL_Control
0x18001d0a4  cmp     rcx, rdi
0x18001d0a7  jz      short loc_18001D0D3
0x18001d0a9  test    byte ptr [rcx+1Ch], 1
0x18001d0ad  jz      short loc_18001D0D3
0x18001d0af  cmp     [rcx+19h], bl
0x18001d0b2  jb      short loc_18001D0D3
0x18001d0b4  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001d0bb  lea     edx, [rbx+9]
0x18001d0be  mov     rcx, [rcx+10h]
0x18001d0c2  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001d0c9  mov     dword ptr [rsp+98h+var_78], r14d
0x18001d0ce  call    WPP_SF_sd
0x18001d0d3  mov     edx, ebx
0x18001d0d5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d0da  mov     esi, 80090009h
0x18001d0df  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0e6  cmp     rcx, rdi
0x18001d0e9  jz      loc_18001D4C5
0x18001d0ef  test    byte ptr [rcx+1Ch], 1
0x18001d0f3  jz      loc_18001D4C5
0x18001d0f9  cmp     [rcx+19h], bl
0x18001d0fc  jb      loc_18001D4C5
0x18001d102  mov     edx, 0Ch
0x18001d107  mov     r9d, esi
0x18001d10a  jmp     loc_18001D4B5
0x18001d10f  lea     r8, [rsp+98h+var_54+4]
0x18001d114  mov     edx, 3
0x18001d119  call    HtGetHandle
0x18001d11e  mov     esi, eax
0x18001d120  test    eax, eax
0x18001d122  jz      short loc_18001D17D
0x18001d124  mov     ebx, 2
0x18001d129  mov     edx, ebx
0x18001d12b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d130  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d137  lea     rdi, WPP_GLOBAL_Control
0x18001d13e  cmp     rcx, rdi
0x18001d141  jz      loc_18001D4C5
0x18001d147  test    byte ptr [rcx+1Ch], 1
0x18001d14b  jz      loc_18001D4C5
0x18001d151  cmp     [rcx+19h], bl
0x18001d154  jb      loc_18001D4C5
0x18001d15a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001d161  lea     edx, [rbx+0Bh]
0x18001d164  mov     rcx, [rcx+10h]
0x18001d168  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001d16f  mov     dword ptr [rsp+98h+var_78], esi
0x18001d173  call    WPP_SF_sd
0x18001d178  jmp     loc_18001D4C5
0x18001d17d  mov     edi, 4C0h
0x18001d182  mov     ecx, edi; size
0x18001d184  call    MIDL_user_allocate
0x18001d189  mov     rbp, rax
0x18001d18c  test    rax, rax
0x18001d18f  jnz     short loc_18001D1E2
0x18001d191  mov     esi, 8009000Eh
0x18001d196  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d19d  lea     rdi, WPP_GLOBAL_Control
0x18001d1a4  cmp     rcx, rdi
0x18001d1a7  jz      loc_18001D4C5
0x18001d1ad  test    byte ptr [rcx+1Ch], 1
0x18001d1b1  jz      loc_18001D4C5
0x18001d1b7  lea     ebx, [rax+2]
0x18001d1ba  cmp     [rcx+19h], bl
0x18001d1bd  jb      loc_18001D4C5
0x18001d1c3  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001d1ca  lea     edx, [rax+0Eh]
0x18001d1cd  mov     rcx, [rcx+10h]
0x18001d1d1  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001d1d8  call    WPP_SF_s
0x18001d1dd  jmp     loc_18001D4C5
0x18001d1e2  mov     r8, rdi; Size
0x18001d1e5  xor     edx, edx; Val
0x18001d1e7  mov     rcx, rbp; void *
0x18001d1ea  call    memset_0
0x18001d1ef  lea     rdi, [rbp+410h]
0x18001d1f6  mov     rcx, rbx; String1
0x18001d1f9  mov     rdx, rdi
0x18001d1fc  lea     r9, [rbp+41Ch]
0x18001d203  lea     r8, [rbp+414h]
0x18001d20a  call    KsppTranslateAlgorithmToKeySpec
0x18001d20f  mov     esi, eax
0x18001d211  mov     ebx, 2
0x18001d216  test    eax, eax
0x18001d218  jz      short loc_18001D253
0x18001d21a  mov     edx, ebx
0x18001d21c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d221  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d228  lea     rdi, WPP_GLOBAL_Control
0x18001d22f  cmp     rcx, rdi
0x18001d232  jz      loc_18001D475
0x18001d238  test    byte ptr [rcx+1Ch], 1
0x18001d23c  jz      loc_18001D475
0x18001d242  cmp     [rcx+19h], bl
0x18001d245  jb      loc_18001D475
0x18001d24b  lea     edx, [rbx+0Dh]
0x18001d24e  jmp     loc_18001D45A
0x18001d253  mov     eax, [rsp+98h+arg_20]
0x18001d25a  test    eax, eax
0x18001d25c  jz      short loc_18001D2B7
0x18001d25e  sub     eax, 1
0x18001d261  jz      loc_18001D383
0x18001d267  cmp     eax, 1
0x18001d26a  jz      short loc_18001D2B0
0x18001d26c  mov     edx, ebx
0x18001d26e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d273  mov     r9d, 80090027h
0x18001d279  mov     esi, r9d
0x18001d27c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d283  lea     rdi, WPP_GLOBAL_Control
0x18001d28a  cmp     rcx, rdi
0x18001d28d  jz      loc_18001D475
0x18001d293  test    byte ptr [rcx+1Ch], 1
0x18001d297  jz      loc_18001D475
0x18001d29d  cmp     [rcx+19h], bl
0x18001d2a0  jb      loc_18001D475
0x18001d2a6  mov     edx, 12h
0x18001d2ab  jmp     loc_18001D36E
0x18001d2b0  cmp     dword ptr [rdi], 1
0x18001d2b3  jnz     short loc_18001D32B
0x18001d2b5  mov     [rdi], ebx
0x18001d2b7  lea     rdi, [rbp+208h]
0x18001d2be  test    r13, r13
0x18001d2c1  jz      loc_18001D3D7
0x18001d2c7  lea     rax, [rsp+98h+var_54]
0x18001d2cc  mov     rdx, rdi; unsigned __int16 *
0x18001d2cf  mov     [rsp+98h+var_68], rax; __int64
0x18001d2d4  lea     r9, [rsp+98h+var_58]
0x18001d2d9  mov     rcx, r13; unsigned __int16 *
0x18001d2dc  mov     [rsp+98h+var_78], rbp; unsigned __int16 *
0x18001d2e1  call    KsppAnalyzeContainerName
0x18001d2e6  mov     esi, eax
0x18001d2e8  test    eax, eax
0x18001d2ea  jz      loc_18001D3CD
0x18001d2f0  mov     edx, ebx
0x18001d2f2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d2f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2fe  lea     rdi, WPP_GLOBAL_Control
0x18001d305  cmp     rcx, rdi
0x18001d308  jz      loc_18001D475
0x18001d30e  test    byte ptr [rcx+1Ch], 1
0x18001d312  jz      loc_18001D475
0x18001d318  cmp     [rcx+19h], bl
0x18001d31b  jb      loc_18001D475
0x18001d321  mov     edx, 13h
0x18001d326  jmp     loc_18001D45A
0x18001d32b  cmp     [rdi], ebx
0x18001d32d  jz      short loc_18001D2B7
0x18001d32f  mov     edx, ebx
0x18001d331  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d336  mov     r9d, 80090027h
0x18001d33c  mov     esi, r9d
0x18001d33f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d346  lea     rdi, WPP_GLOBAL_Control
0x18001d34d  cmp     rcx, rdi
0x18001d350  jz      loc_18001D475
0x18001d356  test    byte ptr [rcx+1Ch], 1
0x18001d35a  jz      loc_18001D475
0x18001d360  cmp     [rcx+19h], bl
0x18001d363  jb      loc_18001D475
0x18001d369  mov     edx, 10h
0x18001d36e  mov     rcx, [rcx+10h]
0x18001d372  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001d379  call    WPP_SF_d
0x18001d37e  jmp     loc_18001D475
0x18001d383  cmp     dword ptr [rdi], 1
0x18001d386  jz      loc_18001D2B7
0x18001d38c  mov     edx, ebx
0x18001d38e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d393  mov     r9d, 80090027h
0x18001d399  mov     esi, r9d
0x18001d39c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3a3  lea     rdi, WPP_GLOBAL_Control
0x18001d3aa  cmp     rcx, rdi
0x18001d3ad  jz      loc_18001D475
0x18001d3b3  test    byte ptr [rcx+1Ch], 1
0x18001d3b7  jz      loc_18001D475
0x18001d3bd  cmp     [rcx+19h], bl
0x18001d3c0  jb      loc_18001D475
0x18001d3c6  mov     edx, 11h
0x18001d3cb  jmp     short loc_18001D36E
0x18001d3cd  mov     r12d, [rsp+98h+var_58]
0x18001d3d2  mov     r15d, [rsp+98h+var_54]
0x18001d3d7  mov     esi, 104h
0x18001d3dc  test    r15d, r15d
0x18001d3df  jnz     short loc_18001D3EE
0x18001d3e1  mov     r8d, esi; Size
0x18001d3e4  xor     edx, edx; Val
0x18001d3e6  mov     rcx, rbp; void *
0x18001d3e9  call    memset_0
0x18001d3ee  test    r12d, r12d
0x18001d3f1  jnz     short loc_18001D400
0x18001d3f3  mov     r8, rsi; Size
0x18001d3f6  xor     edx, edx; Val
0x18001d3f8  mov     rcx, rdi; void *
0x18001d3fb  call    memset_0
0x18001d400  mov     rax, qword ptr [rsp+98h+var_54+4]
0x18001d405  mov     edx, ebx
0x18001d407  mov     r8, [rsp+98h+arg_8]
0x18001d40f  mov     rcx, rbp
0x18001d412  or      r14d, [rax+3Ch]
0x18001d416  and     r14d, 40h
0x18001d41a  mov     [rbp+428h], r14d
0x18001d421  call    HtAddHandle
0x18001d426  mov     esi, eax
0x18001d428  test    eax, eax
0x18001d42a  jz      loc_18001D4C5
0x18001d430  mov     edx, ebx
0x18001d432  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d437  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d43e  lea     rdi, WPP_GLOBAL_Control
0x18001d445  cmp     rcx, rdi
0x18001d448  jz      short loc_18001D475
0x18001d44a  test    byte ptr [rcx+1Ch], 1
0x18001d44e  jz      short loc_18001D475
0x18001d450  cmp     [rcx+19h], bl
0x18001d453  jb      short loc_18001D475
0x18001d455  mov     edx, 14h
0x18001d45a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001d461  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001d468  mov     rcx, [rcx+10h]
0x18001d46c  mov     dword ptr [rsp+98h+var_78], esi
0x18001d470  call    WPP_SF_sd
0x18001d475  mov     rcx, rbp
0x18001d478  call    CspFreeH
0x18001d47d  jmp     short loc_18001D4C5
0x18001d47f  mov     ebx, 2
0x18001d484  mov     edx, ebx
0x18001d486  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d48b  mov     r9d, 80090027h
0x18001d491  mov     esi, r9d
0x18001d494  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d49b  lea     rdi, WPP_GLOBAL_Control
0x18001d4a2  cmp     rcx, rdi
0x18001d4a5  jz      short loc_18001D4C5
0x18001d4a7  test    byte ptr [rcx+1Ch], 1
0x18001d4ab  jz      short loc_18001D4C5
0x18001d4ad  cmp     [rcx+19h], bl
0x18001d4b0  jb      short loc_18001D4C5
0x18001d4b2  lea     edx, [rbx+8]
0x18001d4b5  mov     rcx, [rcx+10h]
0x18001d4b9  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18001d4c0  call    WPP_SF_d
0x18001d4c5  mov     eax, esi
0x18001d4c7  add     rsp, 58h
0x18001d4cb  pop     r15
0x18001d4cd  pop     r14
0x18001d4cf  pop     r13
0x18001d4d1  pop     r12
0x18001d4d3  pop     rdi
0x18001d4d4  pop     rsi
0x18001d4d5  pop     rbp
0x18001d4d6  pop     rbx
0x18001d4d7  retn
```
