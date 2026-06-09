# HrRegisterServiceWithEventing(SmartComPtr<IXMLDOMNode> &,CUString const &,int)

- ea: `0x180007db0`
- end: `0x18000801f`
- name: `?HrRegisterServiceWithEventing@@YAJAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@H@Z`
- size: `623`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800092cc`
- `0x18000b0d0`

## callees

- `0x180007db0`
- `0x180009d50`
- `0x18000a060`
- `0x18000f8a0`
- `0x180036b48`
- `0x180036fc8`
- `0x18003a798`
- `0x18003b1cc`
- `0x18003c018`
- `0x180045b90`
- `0x180045be8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007e10`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007efd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f46`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f85`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007e10`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007efd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f46`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f85`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007e79`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007e79`

## string_xrefs

- `0x180007df2`: `ddd:serviceId`

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
0x180007db0  push    rbp
0x180007db2  push    rbx
0x180007db3  push    rsi
0x180007db4  push    rdi
0x180007db5  push    r12
0x180007db7  push    r13
0x180007db9  push    r14
0x180007dbb  push    r15
0x180007dbd  mov     rbp, rsp
0x180007dc0  sub     rsp, 48h
0x180007dc4  mov     r15d, r8d
0x180007dc7  mov     rsi, rdx
0x180007dca  mov     rbx, rcx
0x180007dcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dd4  lea     r13, WPP_GLOBAL_Control
0x180007ddb  cmp     rcx, r13
0x180007dde  jnz     loc_180007F5E
0x180007de4  xor     r12d, r12d
0x180007de7  lea     r8, [rbp+Block]
0x180007deb  mov     rdx, rbx
0x180007dee  mov     [rbp+Block], r12
0x180007df2  lea     rcx, aDddServiceid; "ddd:serviceId"
0x180007df9  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x180007dfe  mov     edi, eax
0x180007e00  test    eax, eax
0x180007e02  jns     short loc_180007E30
0x180007e04  test    edi, edi
0x180007e06  jnz     loc_180007FE8
0x180007e0c  mov     rcx, [rbp+Block]; Block
0x180007e10  call    cs:__imp_free
0x180007e17  nop     dword ptr [rax+rax+00h]
0x180007e1c  mov     eax, edi
0x180007e1e  add     rsp, 48h
0x180007e22  pop     r15
0x180007e24  pop     r14
0x180007e26  pop     r13
0x180007e28  pop     r12
0x180007e2a  pop     rdi
0x180007e2b  pop     rsi
0x180007e2c  pop     rbx
0x180007e2d  pop     rbp
0x180007e2e  retn
0x180007e30  lea     rax, [rbp+var_18]
0x180007e34  mov     rbx, r12
0x180007e37  mov     [rbp+var_18], rbx
0x180007e3b  cmp     rsi, rax
0x180007e3e  jz      short loc_180007E5A
0x180007e40  mov     rdx, [rsi]; unsigned __int16 *
0x180007e43  lea     rcx, [rbp+var_18]; this
0x180007e47  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x180007e4c  mov     rbx, [rbp+var_18]
0x180007e50  mov     edi, eax
0x180007e52  test    eax, eax
0x180007e54  js      loc_180007F43
0x180007e5a  test    rbx, rbx
0x180007e5d  jz      loc_180007FA1
0x180007e63  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007e67  inc     rsi
0x180007e6a  cmp     [rbx+rsi*2], r12w
0x180007e6f  jnz     short loc_180007E67
0x180007e71  add     rsi, 2
0x180007e75  lea     rcx, [rsi+rsi]; Size
0x180007e79  call    cs:__imp_malloc
0x180007e80  nop     dword ptr [rax+rax+00h]
0x180007e85  mov     r14, rax
0x180007e88  test    rax, rax
0x180007e8b  jz      loc_180007FA9
0x180007e91  mov     [rax], r12w
0x180007e95  test    rbx, rbx
0x180007e98  jz      short loc_180007EBD
0x180007e9a  mov     rdx, rsi; cchDest
0x180007e9d  call    StringValidateDestW
0x180007ea2  mov     edi, eax
0x180007ea4  test    eax, eax
0x180007ea6  js      loc_180007FB3
0x180007eac  mov     r9, rbx; pszSrc
0x180007eaf  mov     rcx, r14; pszDest
0x180007eb2  call    StringCopyWorkerW
0x180007eb7  mov     edi, eax
0x180007eb9  test    edi, edi
0x180007ebb  js      short loc_180007EFA
0x180007ebd  lea     r8, [rbp+pcchDestLength]; pcchDestLength
0x180007ec1  mov     [rbp+pcchDestLength], r12
0x180007ec5  mov     rdx, rsi; cchDest
0x180007ec8  mov     rcx, r14; pszDest
0x180007ecb  call    StringValidateDestAndLengthW
0x180007ed0  mov     edi, eax
0x180007ed2  test    eax, eax
0x180007ed4  js      short loc_180007EF2
0x180007ed6  mov     rax, [rbp+pcchDestLength]
0x180007eda  lea     r9, asc_180063AD8; "+"
0x180007ee1  sub     rsi, rax
0x180007ee4  mov     rdx, rsi; cchDest
0x180007ee7  lea     rcx, [r14+rax*2]; pszDest
0x180007eeb  call    StringCopyWorkerW
0x180007ef0  mov     edi, eax
0x180007ef2  test    edi, edi
0x180007ef4  jns     loc_180007F82
0x180007efa  mov     rcx, r14; Block
0x180007efd  call    cs:__imp_free
0x180007f04  nop     dword ptr [rax+rax+00h]
0x180007f09  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f10  cmp     rcx, r13
0x180007f13  jnz     loc_180007FC1
0x180007f19  test    edi, edi
0x180007f1b  js      short loc_180007F43
0x180007f1d  mov     rdx, [rbp+Block]; unsigned __int16 *
0x180007f21  lea     rcx, [rbp+var_18]; this
0x180007f25  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180007f2a  mov     rbx, [rbp+var_18]
0x180007f2e  mov     edi, eax
0x180007f30  test    eax, eax
0x180007f32  js      short loc_180007F43
0x180007f34  mov     rcx, rbx; unsigned __int16 *
0x180007f37  test    r15d, r15d
0x180007f3a  jz      short loc_180007F57
0x180007f3c  call    ?HrRegisterEventSource@@YAJPEBG@Z; HrRegisterEventSource(ushort const *)
0x180007f41  mov     edi, eax
0x180007f43  mov     rcx, rbx; Block
0x180007f46  call    cs:__imp_free
0x180007f4d  nop     dword ptr [rax+rax+00h]
0x180007f52  jmp     loc_180007E04
0x180007f57  call    ?HrDeregisterEventSource@@YAJPEBG@Z; HrDeregisterEventSource(ushort const *)
0x180007f5c  jmp     short loc_180007F41
0x180007f5e  test    byte ptr [rcx+1Ch], 40h
0x180007f62  jz      loc_180007DE4
0x180007f68  mov     rcx, [rcx+10h]
0x180007f6c  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180007f73  mov     edx, 7Ch ; '|'
0x180007f78  call    WPP_SF_
0x180007f7d  jmp     loc_180007DE4
0x180007f82  mov     rcx, rbx; Block
0x180007f85  call    cs:__imp_free
0x180007f8c  nop     dword ptr [rax+rax+00h]
0x180007f91  mov     rbx, r14
0x180007f94  mov     [rbp+var_18], rbx
0x180007f98  test    edi, edi
0x180007f9a  jz      short loc_180007F1D
0x180007f9c  jmp     loc_180007F09
0x180007fa1  mov     rsi, r12
0x180007fa4  jmp     loc_180007E71
0x180007fa9  mov     edi, 8007000Eh
0x180007fae  jmp     loc_180007F09
0x180007fb3  test    rsi, rsi
0x180007fb6  jnz     loc_180007EFA
0x180007fbc  jmp     loc_180007EB9
0x180007fc1  test    byte ptr [rcx+1Ch], 1
0x180007fc5  jz      loc_180007F19
0x180007fcb  mov     rcx, [rcx+10h]
0x180007fcf  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x180007fd6  mov     edx, 0Ch
0x180007fdb  mov     r9d, edi
0x180007fde  call    WPP_SF_d
0x180007fe3  jmp     loc_180007F19
0x180007fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fef  cmp     rcx, r13
0x180007ff2  jz      loc_180007E0C
0x180007ff8  test    byte ptr [rcx+1Ch], 1
0x180007ffc  jz      loc_180007E0C
0x180008002  mov     rcx, [rcx+10h]
0x180008006  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000800d  mov     edx, 7Dh ; '}'
0x180008012  mov     r9d, edi
0x180008015  call    WPP_SF_d
0x18000801a  jmp     loc_180007E0C
```
