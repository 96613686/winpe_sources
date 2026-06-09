# CTask::HrAddNextPageToParsingStack(_GUID const *,int,int)

- ea: `0x180020b3c`
- end: `0x180020f04`
- name: `?HrAddNextPageToParsingStack@CTask@@AEAAJPEBU_GUID@@HH@Z`
- size: `968`
- prototype: `__int64 __fastcall(CTask *__hidden this, const struct _GUID *, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021d04`
- `0x1800237d8`

## callees

- `0x18000ae04`
- `0x18000ae44`
- `0x180020b3c`
- `0x180020f0c`
- `0x180021634`
- `0x180023c5c`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020eb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020eb4`

## pseudocode

```c
__int64 __fastcall CTask::HrAddNextPageToParsingStack(CTask *this, const struct _GUID *a2, int a3, int a4)
{
  unsigned int v4; // ebx
  const struct _GUID *v7; // rdi
  PVOID *v9; // rcx
  __int64 v10; // rax
  unsigned int *v11; // rsi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // eax
  struct _GUID *v16; // rdx
  unsigned int v17; // eax
  unsigned int v18; // eax
  LPVOID pv; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v21; // [rsp+48h] [rbp-38h] BYREF
  struct IXWizardPageEvent *v22; // [rsp+50h] [rbp-30h] BYREF
  struct IEnumXWizardPage *v23; // [rsp+58h] [rbp-28h] BYREF
  struct _GUID v24; // [rsp+60h] [rbp-20h] BYREF

  v4 = 0;
  pv = 0;
  v7 = a2;
  v24 = 0;
  if ( !a2 )
    goto LABEL_5;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, a2->Data1);
    goto LABEL_5;
  }
  while ( 1 )
  {
    if ( v4 )
      goto LABEL_48;
    v10 = *((_QWORD *)this + 40);
    if ( *((_QWORD *)this + 39) == v10 )
      break;
    v11 = *(unsigned int **)(v10 - 8);
    if ( v11[13] )
      goto LABEL_20;
    if ( !v7 )
      goto LABEL_27;
    v12 = *(_QWORD *)&v7->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&v7->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v12 = *(_QWORD *)v7->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( v12 )
    {
      v14 = *((_QWORD *)this + 31);
      v24 = *v7;
      v15 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v14 + 200LL))(v14, &v24);
      v4 = v15;
      if ( v15 >= 0 )
      {
        v16 = &v24;
        pv = &v24;
        goto LABEL_29;
      }
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_41;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          70,
          &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
          (unsigned int)v15);
LABEL_40:
        v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_41:
        if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
        {
          WPP_SF_d(v9[2], 74, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, v4);
          goto LABEL_5;
        }
      }
    }
    else
    {
      v13 = *(_QWORD *)&v7->Data1 - *(_QWORD *)&GUID_NULL.Data1;
      if ( *(_QWORD *)&v7->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
        v13 = *(_QWORD *)v7->Data4 - *(_QWORD *)GUID_NULL.Data4;
      if ( !v13 )
      {
        if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
          WPP_SF_d(v9[2], 71, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, *v11);
        v7 = 0;
LABEL_20:
        CTask::PopPageFromParsingStack(this);
        v4 = 0;
LABEL_5:
        v9 = (PVOID *)WPP_GLOBAL_Control;
        continue;
      }
LABEL_27:
      v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID *))(**((_QWORD **)v11 + 4) + 24LL))(
              *((_QWORD *)v11 + 4),
              1,
              &pv);
      v4 = v17;
      if ( v17 )
      {
        if ( v17 == 1 )
          goto LABEL_20;
        goto LABEL_40;
      }
      v16 = (struct _GUID *)pv;
LABEL_29:
      v21 = 0;
      v22 = 0;
      v23 = 0;
      v18 = CTask::HrCreateParsingStackData(this, v16, (LPVOID *)&v22, &v23, &v21, a4);
      v4 = v18;
      if ( !v18 )
      {
        v4 = CTask::HrAddPageToParsingStack(
               this,
               (const struct _GUID *)pv,
               (const struct _GUID *)v11,
               v22,
               v23,
               v21,
               a3,
               a4);
        (*(void (__fastcall **)(struct IXWizardPageEvent *))(*(_QWORD *)v22 + 16LL))(v22);
        (*(void (__fastcall **)(struct IEnumXWizardPage *))(*(_QWORD *)v23 + 16LL))(v23);
        if ( (v4 & 0x80000000) != 0 )
          goto LABEL_5;
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            72,
            &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
            *(unsigned int *)pv);
LABEL_47:
          v9 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_48;
        }
        goto LABEL_48;
      }
      if ( v18 != 1 || !v7 )
        goto LABEL_5;
      v4 = 262657;
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          73,
          &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
          *(unsigned int *)pv,
          262657);
        goto LABEL_5;
      }
    }
  }
  v4 = 262657;
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
  {
    WPP_SF_d(v9[2], 69, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, 262657);
    goto LABEL_47;
  }
LABEL_48:
  if ( pv != v7 && pv != &v24 )
  {
    CoTaskMemFree(pv);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 )
    WPP_SF_d(v9[2], 75, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180020b3c  push    rbp
0x180020b3e  push    rbx
0x180020b3f  push    rsi
0x180020b40  push    rdi
0x180020b41  push    r12
0x180020b43  push    r14
0x180020b45  push    r15
0x180020b47  mov     rbp, rsp
0x180020b4a  sub     rsp, 80h
0x180020b51  mov     rax, cs:__security_cookie
0x180020b58  xor     rax, rsp
0x180020b5b  mov     [rbp+var_10], rax
0x180020b5f  xor     ebx, ebx
0x180020b61  lea     rsi, WPP_GLOBAL_Control
0x180020b68  mov     [rbp+pv], rbx
0x180020b6c  xorps   xmm0, xmm0
0x180020b6f  mov     r15d, r9d
0x180020b72  mov     r12d, r8d
0x180020b75  mov     rdi, rdx
0x180020b78  mov     r14, rcx
0x180020b7b  movups  [rbp+var_20], xmm0
0x180020b7f  test    rdx, rdx
0x180020b82  jz      short loc_180020BAC
0x180020b84  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b8b  cmp     rcx, rsi
0x180020b8e  jz      short loc_180020BB3
0x180020b90  test    byte ptr [rcx+1Ch], 8
0x180020b94  jz      short loc_180020BB3
0x180020b96  mov     r9d, [rdi]
0x180020b99  lea     edx, [rbx+44h]
0x180020b9c  mov     rcx, [rcx+10h]
0x180020ba0  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180020ba7  call    WPP_SF_d
0x180020bac  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bb3  test    ebx, ebx
0x180020bb5  jnz     loc_180020E9F
0x180020bbb  mov     rax, [r14+140h]
0x180020bc2  cmp     [r14+138h], rax
0x180020bc9  jz      loc_180020E70
0x180020bcf  mov     rsi, [rax-8]
0x180020bd3  cmp     [rsi+34h], ebx
0x180020bd6  jnz     short loc_180020C47
0x180020bd8  test    rdi, rdi
0x180020bdb  jz      loc_180020CCD
0x180020be1  mov     rax, [rdi]
0x180020be4  mov     r8, qword ptr cs:GUID_NULL.Data1
0x180020beb  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x180020bf2  sub     rax, r8
0x180020bf5  jnz     short loc_180020BFE
0x180020bf7  mov     rax, [rdi+8]
0x180020bfb  sub     rax, rdx
0x180020bfe  test    rax, rax
0x180020c01  jnz     short loc_180020C5D
0x180020c03  mov     rax, [rdi]
0x180020c06  sub     rax, r8
0x180020c09  jnz     short loc_180020C12
0x180020c0b  mov     rax, [rdi+8]
0x180020c0f  sub     rax, rdx
0x180020c12  test    rax, rax
0x180020c15  jnz     loc_180020CCD
0x180020c1b  lea     rax, WPP_GLOBAL_Control
0x180020c22  cmp     rcx, rax
0x180020c25  jz      short loc_180020C45
0x180020c27  test    byte ptr [rcx+1Ch], 8
0x180020c2b  jz      short loc_180020C45
0x180020c2d  mov     r9d, [rsi]
0x180020c30  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180020c37  mov     rcx, [rcx+10h]
0x180020c3b  mov     edx, 47h ; 'G'
0x180020c40  call    WPP_SF_d
0x180020c45  xor     edi, edi
0x180020c47  mov     rcx, r14; this
0x180020c4a  call    ?PopPageFromParsingStack@CTask@@AEAAXXZ; CTask::PopPageFromParsingStack(void)
0x180020c4f  xor     ebx, ebx
0x180020c51  lea     rsi, WPP_GLOBAL_Control
0x180020c58  jmp     loc_180020BAC
0x180020c5d  movups  xmm0, xmmword ptr [rdi]
0x180020c60  mov     rcx, [r14+0F8h]
0x180020c67  lea     rdx, [rbp+var_20]
0x180020c6b  movdqu  [rbp+var_20], xmm0
0x180020c70  mov     rax, [rcx]
0x180020c73  mov     rax, [rax+0C8h]
0x180020c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c7f  mov     ebx, eax
0x180020c81  test    eax, eax
0x180020c83  js      short loc_180020C8F
0x180020c85  lea     rdx, [rbp+var_20]
0x180020c89  mov     [rbp+pv], rdx
0x180020c8d  jmp     short loc_180020CF6
0x180020c8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c96  lea     rsi, WPP_GLOBAL_Control
0x180020c9d  cmp     rcx, rsi
0x180020ca0  jz      loc_180020BB3
0x180020ca6  test    byte ptr [rcx+1Ch], 4
0x180020caa  jz      loc_180020E40
0x180020cb0  mov     rcx, [rcx+10h]
0x180020cb4  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180020cbb  mov     edx, 46h ; 'F'
0x180020cc0  mov     r9d, eax
0x180020cc3  call    WPP_SF_d
0x180020cc8  jmp     loc_180020E39
0x180020ccd  mov     rcx, [rsi+20h]
0x180020cd1  lea     r8, [rbp+pv]
0x180020cd5  xor     r9d, r9d
0x180020cd8  mov     rax, [rcx]
0x180020cdb  lea     edx, [r9+1]
0x180020cdf  mov     rax, [rax+18h]
0x180020ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ce8  mov     ebx, eax
0x180020cea  test    eax, eax
0x180020cec  jnz     loc_180020E29
0x180020cf2  mov     rdx, [rbp+pv]; struct _GUID *
0x180020cf6  lea     rax, [rbp+var_38]
0x180020cfa  mov     [rsp+80h+var_58], r15d; int
0x180020cff  lea     r9, [rbp+var_28]; struct IEnumXWizardPage **
0x180020d03  mov     [rsp+80h+var_60], rax; unsigned int *
0x180020d08  lea     r8, [rbp+var_30]; struct IXWizardPageEvent **
0x180020d0c  mov     [rbp+var_38], 0
0x180020d13  mov     rcx, r14; this
0x180020d16  mov     [rbp+var_30], 0
0x180020d1e  mov     [rbp+var_28], 0
0x180020d26  call    ?HrCreateParsingStackData@CTask@@AEAAJPEAU_GUID@@PEAPEAUIXWizardPageEvent@@PEAPEAUIEnumXWizardPage@@PEAKH@Z; CTask::HrCreateParsingStackData(_GUID *,IXWizardPageEvent * *,IEnumXWizardPage * *,ulong *,int)
0x180020d2b  mov     ebx, eax
0x180020d2d  test    eax, eax
0x180020d2f  jnz     loc_180020DCE
0x180020d35  mov     eax, [rbp+var_38]
0x180020d38  mov     r8, rsi; struct _GUID *
0x180020d3b  mov     r9, [rbp+var_30]; struct IXWizardPageEvent *
0x180020d3f  mov     rcx, r14; this
0x180020d42  mov     rdx, [rbp+pv]; struct _GUID *
0x180020d46  mov     [rsp+80h+var_48], r15d; int
0x180020d4b  mov     [rsp+80h+var_50], r12d; int
0x180020d50  mov     [rsp+80h+var_58], eax; unsigned int
0x180020d54  mov     rax, [rbp+var_28]
0x180020d58  mov     [rsp+80h+var_60], rax; struct IEnumXWizardPage *
0x180020d5d  call    ?HrAddPageToParsingStack@CTask@@AEAAJPEBU_GUID@@0PEBUIXWizardPageEvent@@PEBUIEnumXWizardPage@@KHH@Z; CTask::HrAddPageToParsingStack(_GUID const *,_GUID const *,IXWizardPageEvent const *,IEnumXWizardPage const *,ulong,int,int)
0x180020d62  mov     rcx, [rbp+var_30]
0x180020d66  mov     ebx, eax
0x180020d68  mov     rax, [rcx]
0x180020d6b  mov     rax, [rax+10h]
0x180020d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d74  mov     rcx, [rbp+var_28]
0x180020d78  mov     rax, [rcx]
0x180020d7b  mov     rax, [rax+10h]
0x180020d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d84  test    ebx, ebx
0x180020d86  js      loc_180020C51
0x180020d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d93  lea     rsi, WPP_GLOBAL_Control
0x180020d9a  cmp     rcx, rsi
0x180020d9d  jz      loc_180020E9F
0x180020da3  test    byte ptr [rcx+1Ch], 8
0x180020da7  jz      loc_180020E9F
0x180020dad  mov     r9, [rbp+pv]
0x180020db1  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180020db8  mov     rcx, [rcx+10h]
0x180020dbc  mov     edx, 48h ; 'H'
0x180020dc1  mov     r9d, [r9]
0x180020dc4  call    WPP_SF_d
0x180020dc9  jmp     loc_180020E98
0x180020dce  cmp     eax, 1
0x180020dd1  jnz     loc_180020C51
0x180020dd7  test    rdi, rdi
0x180020dda  jz      loc_180020C51
0x180020de0  mov     ebx, 40201h
0x180020de5  mov     rcx, cs:WPP_GLOBAL_Control
0x180020dec  lea     rsi, WPP_GLOBAL_Control
0x180020df3  cmp     rcx, rsi
0x180020df6  jz      loc_180020BB3
0x180020dfc  test    byte ptr [rcx+1Ch], 8
0x180020e00  jz      loc_180020BB3
0x180020e06  mov     r9, [rbp+pv]
0x180020e0a  lea     edx, [rax+48h]
0x180020e0d  mov     rcx, [rcx+10h]
0x180020e11  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180020e18  mov     dword ptr [rsp+80h+var_60], ebx
0x180020e1c  mov     r9d, [r9]
0x180020e1f  call    WPP_SF_DD
0x180020e24  jmp     loc_180020BAC
0x180020e29  cmp     eax, 1
0x180020e2c  jz      loc_180020C47
0x180020e32  lea     rsi, WPP_GLOBAL_Control
0x180020e39  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e40  cmp     rcx, rsi
0x180020e43  jz      loc_180020BB3
0x180020e49  test    byte ptr [rcx+1Ch], 4
0x180020e4d  jz      loc_180020BB3
0x180020e53  mov     rcx, [rcx+10h]
0x180020e57  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180020e5e  mov     edx, 4Ah ; 'J'
0x180020e63  mov     r9d, ebx
0x180020e66  call    WPP_SF_d
0x180020e6b  jmp     loc_180020BAC
0x180020e70  mov     ebx, 40201h
0x180020e75  cmp     rcx, rsi
0x180020e78  jz      short loc_180020E9F
0x180020e7a  test    byte ptr [rcx+1Ch], 8
0x180020e7e  jz      short loc_180020E9F
0x180020e80  mov     rcx, [rcx+10h]
0x180020e84  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180020e8b  mov     edx, 45h ; 'E'
0x180020e90  mov     r9d, ebx
0x180020e93  call    WPP_SF_d
0x180020e98  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e9f  mov     rax, [rbp+pv]
0x180020ea3  cmp     rax, rdi
0x180020ea6  jz      short loc_180020EC1
0x180020ea8  lea     rdx, [rbp+var_20]
0x180020eac  cmp     rax, rdx
0x180020eaf  jz      short loc_180020EC1
0x180020eb1  mov     rcx, rax; pv
0x180020eb4  call    cs:__imp_CoTaskMemFree
0x180020eba  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ec1  cmp     rcx, rsi
0x180020ec4  jz      short loc_180020EE4
0x180020ec6  test    byte ptr [rcx+1Ch], 10h
0x180020eca  jz      short loc_180020EE4
0x180020ecc  mov     rcx, [rcx+10h]
0x180020ed0  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180020ed7  mov     edx, 4Bh ; 'K'
0x180020edc  mov     r9d, ebx
0x180020edf  call    WPP_SF_d
0x180020ee4  mov     eax, ebx
0x180020ee6  mov     rcx, [rbp+var_10]
0x180020eea  xor     rcx, rsp; StackCookie
0x180020eed  call    __security_check_cookie
0x180020ef2  add     rsp, 80h
0x180020ef9  pop     r15
0x180020efb  pop     r14
0x180020efd  pop     r12
0x180020eff  pop     rdi
0x180020f00  pop     rsi
0x180020f01  pop     rbx
0x180020f02  pop     rbp
0x180020f03  retn
```
