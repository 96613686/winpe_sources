# HrRegisterServiceWithEventing(SmartComPtr<IXMLDOMNode> &,CUString const &,int)

- ea: `0x180013cb4`
- end: `0x180013f00`
- name: `?HrRegisterServiceWithEventing@@YAJAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@H@Z`
- size: `588`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800150bc`
- `0x180016d5c`

## callees

- `0x180013cb4`
- `0x180015ab0`
- `0x180015d90`
- `0x18001ab90`
- `0x180034b0c`
- `0x180034f3c`
- `0x180038324`
- `0x180038ce4`
- `0x180039a84`
- `0x180043124`
- `0x18004317c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013d14`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013df0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013e33`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013e6c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013d14`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013df0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013e33`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013e6c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180013d76`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180013d76`

## string_xrefs

- `0x180013cf6`: `ddd:serviceId`

## pseudocode

```c
__int64 __fastcall HrRegisterServiceWithEventing(__int64 a1, const unsigned __int16 **a2, int a3)
{
  HRESULT v5; // edi
  unsigned __int16 *v7; // rbx
  int v8; // eax
  __int64 v9; // rsi
  size_t v10; // rsi
  wchar_t *v11; // rax
  const wchar_t *v12; // rcx
  size_t v13; // r8
  size_t v14; // r9
  wchar_t *v15; // r14
  size_t v16; // rdx
  size_t *v17; // r8
  size_t *v18; // r8
  int v19; // eax
  HRESULT v20; // eax
  size_t v21; // [rsp+20h] [rbp-28h]
  unsigned __int16 *v22; // [rsp+30h] [rbp-18h] BYREF
  size_t pcchDestLength[2]; // [rsp+38h] [rbp-10h] BYREF

  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
  v5 = HrSelectNodeText((OLECHAR *)L"ddd:serviceId");
  if ( v5 >= 0 )
  {
    v7 = 0;
    v22 = 0;
    if ( a2 != (const unsigned __int16 **)&v22 )
    {
      v8 = CUString::HrAssign((CUString *)&v22, *a2);
      v7 = v22;
      v5 = v8;
      if ( v8 < 0 )
      {
LABEL_25:
        free(v7);
        goto LABEL_3;
      }
    }
    if ( v7 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v7[v9] );
    }
    else
    {
      v9 = 0;
    }
    v10 = v9 + 2;
    v11 = (wchar_t *)malloc(2 * v10);
    v15 = v11;
    if ( !v11 )
    {
      v5 = -2147024882;
      goto LABEL_19;
    }
    *v11 = 0;
    if ( !v7 )
      goto LABEL_15;
    v5 = StringValidateDestW(v12, v10, v13);
    if ( v5 < 0 )
    {
      if ( v10 )
        goto LABEL_18;
    }
    else
    {
      v5 = StringCopyWorkerW(v15, v16, v17, v7, v21);
    }
    if ( v5 >= 0 )
    {
LABEL_15:
      pcchDestLength[0] = 0;
      v5 = StringValidateDestAndLengthW(v15, v10, pcchDestLength, v14);
      if ( v5 >= 0 )
        v5 = StringCopyWorkerW(&v15[pcchDestLength[0]], v10 - pcchDestLength[0], v18, L"+", v21);
      if ( v5 >= 0 )
      {
        free(v7);
        v7 = v15;
        v22 = v15;
        if ( !v5 )
        {
LABEL_21:
          v19 = CUString::HrAppend((CUString *)&v22, 0);
          v7 = v22;
          v5 = v19;
          if ( v19 >= 0 )
          {
            if ( a3 )
              v20 = HrRegisterEventSource(v22);
            else
              v20 = HrDeregisterEventSource(v22);
            v5 = v20;
          }
          goto LABEL_25;
        }
LABEL_19:
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
            (unsigned int)v5);
        if ( v5 < 0 )
          goto LABEL_25;
        goto LABEL_21;
      }
    }
LABEL_18:
    free(v15);
    goto LABEL_19;
  }
LABEL_3:
  if ( v5 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      125,
      WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
      (unsigned int)v5);
  free(0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180013cb4  push    rbp
0x180013cb6  push    rbx
0x180013cb7  push    rsi
0x180013cb8  push    rdi
0x180013cb9  push    r12
0x180013cbb  push    r13
0x180013cbd  push    r14
0x180013cbf  push    r15
0x180013cc1  mov     rbp, rsp
0x180013cc4  sub     rsp, 48h
0x180013cc8  mov     r15d, r8d
0x180013ccb  mov     rsi, rdx
0x180013cce  mov     rbx, rcx
0x180013cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cd8  lea     r13, WPP_GLOBAL_Control
0x180013cdf  cmp     rcx, r13
0x180013ce2  jnz     loc_180013E45
0x180013ce8  xor     r12d, r12d
0x180013ceb  lea     r8, [rbp+Block]
0x180013cef  mov     rdx, rbx
0x180013cf2  mov     [rbp+Block], r12
0x180013cf6  lea     rcx, aDddServiceid; "ddd:serviceId"
0x180013cfd  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x180013d02  mov     edi, eax
0x180013d04  test    eax, eax
0x180013d06  jns     short loc_180013D2D
0x180013d08  test    edi, edi
0x180013d0a  jnz     loc_180013EC9
0x180013d10  mov     rcx, [rbp+Block]; Block
0x180013d14  call    cs:__imp_free
0x180013d1a  mov     eax, edi
0x180013d1c  add     rsp, 48h
0x180013d20  pop     r15
0x180013d22  pop     r14
0x180013d24  pop     r13
0x180013d26  pop     r12
0x180013d28  pop     rdi
0x180013d29  pop     rsi
0x180013d2a  pop     rbx
0x180013d2b  pop     rbp
0x180013d2c  retn
0x180013d2d  lea     rax, [rbp+var_18]
0x180013d31  mov     rbx, r12
0x180013d34  mov     [rbp+var_18], rbx
0x180013d38  cmp     rsi, rax
0x180013d3b  jz      short loc_180013D57
0x180013d3d  mov     rdx, [rsi]; unsigned __int16 *
0x180013d40  lea     rcx, [rbp+var_18]; this
0x180013d44  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x180013d49  mov     rbx, [rbp+var_18]
0x180013d4d  mov     edi, eax
0x180013d4f  test    eax, eax
0x180013d51  js      loc_180013E30
0x180013d57  test    rbx, rbx
0x180013d5a  jz      loc_180013E82
0x180013d60  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180013d64  inc     rsi
0x180013d67  cmp     [rbx+rsi*2], r12w
0x180013d6c  jnz     short loc_180013D64
0x180013d6e  add     rsi, 2
0x180013d72  lea     rcx, [rsi+rsi]; Size
0x180013d76  call    cs:__imp_malloc
0x180013d7c  mov     r14, rax
0x180013d7f  test    rax, rax
0x180013d82  jz      loc_180013E8A
0x180013d88  mov     [rax], r12w
0x180013d8c  test    rbx, rbx
0x180013d8f  jz      short loc_180013DB4
0x180013d91  mov     rdx, rsi; cchDest
0x180013d94  call    StringValidateDestW
0x180013d99  mov     edi, eax
0x180013d9b  test    eax, eax
0x180013d9d  js      loc_180013E94
0x180013da3  mov     r9, rbx; pszSrc
0x180013da6  mov     rcx, r14; pszDest
0x180013da9  call    StringCopyWorkerW
0x180013dae  mov     edi, eax
0x180013db0  test    edi, edi
0x180013db2  js      short loc_180013DED
0x180013db4  lea     r8, [rbp+pcchDestLength]; pcchDestLength
0x180013db8  mov     [rbp+pcchDestLength], r12
0x180013dbc  mov     rdx, rsi; cchDest
0x180013dbf  mov     rcx, r14; pszDest
0x180013dc2  call    StringValidateDestAndLengthW
0x180013dc7  mov     edi, eax
0x180013dc9  test    eax, eax
0x180013dcb  js      short loc_180013DE9
0x180013dcd  mov     rax, [rbp+pcchDestLength]
0x180013dd1  lea     r9, asc_180060318; "+"
0x180013dd8  sub     rsi, rax
0x180013ddb  mov     rdx, rsi; cchDest
0x180013dde  lea     rcx, [r14+rax*2]; pszDest
0x180013de2  call    StringCopyWorkerW
0x180013de7  mov     edi, eax
0x180013de9  test    edi, edi
0x180013deb  jns     short loc_180013E69
0x180013ded  mov     rcx, r14; Block
0x180013df0  call    cs:__imp_free
0x180013df6  mov     rcx, cs:WPP_GLOBAL_Control
0x180013dfd  cmp     rcx, r13
0x180013e00  jnz     loc_180013EA2
0x180013e06  test    edi, edi
0x180013e08  js      short loc_180013E30
0x180013e0a  mov     rdx, [rbp+Block]; unsigned __int16 *
0x180013e0e  lea     rcx, [rbp+var_18]; this
0x180013e12  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180013e17  mov     rbx, [rbp+var_18]
0x180013e1b  mov     edi, eax
0x180013e1d  test    eax, eax
0x180013e1f  js      short loc_180013E30
0x180013e21  mov     rcx, rbx; unsigned __int16 *
0x180013e24  test    r15d, r15d
0x180013e27  jz      short loc_180013E3E
0x180013e29  call    ?HrRegisterEventSource@@YAJPEBG@Z; HrRegisterEventSource(ushort const *)
0x180013e2e  mov     edi, eax
0x180013e30  mov     rcx, rbx; Block
0x180013e33  call    cs:__imp_free
0x180013e39  jmp     loc_180013D08
0x180013e3e  call    ?HrDeregisterEventSource@@YAJPEBG@Z; HrDeregisterEventSource(ushort const *)
0x180013e43  jmp     short loc_180013E2E
0x180013e45  test    byte ptr [rcx+1Ch], 40h
0x180013e49  jz      loc_180013CE8
0x180013e4f  mov     rcx, [rcx+10h]
0x180013e53  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180013e5a  mov     edx, 7Ch ; '|'
0x180013e5f  call    WPP_SF_
0x180013e64  jmp     loc_180013CE8
0x180013e69  mov     rcx, rbx; Block
0x180013e6c  call    cs:__imp_free
0x180013e72  mov     rbx, r14
0x180013e75  mov     [rbp+var_18], rbx
0x180013e79  test    edi, edi
0x180013e7b  jz      short loc_180013E0A
0x180013e7d  jmp     loc_180013DF6
0x180013e82  mov     rsi, r12
0x180013e85  jmp     loc_180013D6E
0x180013e8a  mov     edi, 8007000Eh
0x180013e8f  jmp     loc_180013DF6
0x180013e94  test    rsi, rsi
0x180013e97  jnz     loc_180013DED
0x180013e9d  jmp     loc_180013DB0
0x180013ea2  test    byte ptr [rcx+1Ch], 1
0x180013ea6  jz      loc_180013E06
0x180013eac  mov     rcx, [rcx+10h]
0x180013eb0  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x180013eb7  mov     edx, 0Ch
0x180013ebc  mov     r9d, edi
0x180013ebf  call    WPP_SF_d
0x180013ec4  jmp     loc_180013E06
0x180013ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ed0  cmp     rcx, r13
0x180013ed3  jz      loc_180013D10
0x180013ed9  test    byte ptr [rcx+1Ch], 1
0x180013edd  jz      loc_180013D10
0x180013ee3  mov     rcx, [rcx+10h]
0x180013ee7  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180013eee  mov     edx, 7Dh ; '}'
0x180013ef3  mov     r9d, edi
0x180013ef6  call    WPP_SF_d
0x180013efb  jmp     loc_180013D10
```
