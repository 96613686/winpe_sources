# AuthMgrPreConnectConfigureOneX(void *,ulong,void *,DOT11_MSMSEC_RUNTIME_STATE *,int)

- ea: `0x1800262ac`
- end: `0x18002648e`
- name: `?AuthMgrPreConnectConfigureOneX@@YAKPEAXK0PEAUDOT11_MSMSEC_RUNTIME_STATE@@H@Z`
- size: `482`
- prototype: `unsigned int __fastcall(void *, unsigned int, void *, struct DOT11_MSMSEC_RUNTIME_STATE *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180025b00`
- `0x1800260f0`
- `0x18003a5d8`

## callees

- `0x18000892c`
- `0x180008998`
- `0x1800262ac`
- `0x180043a30`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18002637f`
- `WS2_32!__imp_htonl` at `0x18002637f`
- `OneX!OneXSetRuntimeState` at `0x18002640f`
- `OneX!OneXSetRuntimeState` at `0x18002640f`
- `OneX!OneXAddEapAttributes` at `0x1800263c9`
- `OneX!OneXAddEapAttributes` at `0x1800263c9`
- `OneX!OneXUpdatePortProfile` at `0x18002632f`
- `OneX!OneXUpdatePortProfile` at `0x18002632f`

## pseudocode

```c
__int64 __fastcall AuthMgrPreConnectConfigureOneX(
        void *a1,
        unsigned int a2,
        void *a3,
        struct DOT11_MSMSEC_RUNTIME_STATE *a4,
        int a5)
{
  unsigned int v9; // eax
  unsigned int v10; // ebx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  _DWORD v15[2]; // [rsp+30h] [rbp-40h] BYREF
  u_long *v16; // [rsp+38h] [rbp-38h]
  _QWORD v17[2]; // [rsp+40h] [rbp-30h] BYREF
  u_long v18; // [rsp+50h] [rbp-20h] BYREF
  char v19; // [rsp+54h] [rbp-1Ch]
  __int64 v20; // [rsp+55h] [rbp-1Bh]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids);
  v9 = OneXUpdatePortProfile(1, a1, a2, a3, 0, 0);
  v10 = v9;
  if ( !v9 )
  {
    if ( !a5 )
      goto LABEL_13;
    v19 = 70;
    v18 = htonl(0x137u);
    v20 = 4;
    v16 = &v18;
    v15[0] = 26;
    v17[1] = v15;
    v15[1] = 13;
    v17[0] = 1;
    v9 = OneXAddEapAttributes(1, a1, v17, 0);
    v10 = v9;
    if ( v9 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v10;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_22;
      v12 = 12;
    }
    else
    {
LABEL_13:
      if ( a4 )
        v13 = *((_QWORD *)a4 + 1);
      else
        v13 = 0;
      v9 = OneXSetRuntimeState(1, a1, v13, 0);
      v10 = v9;
      if ( !v9 )
        goto LABEL_21;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v10;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_22;
      v12 = 13;
    }
LABEL_20:
    WPP_SF_d(v11[7], v12, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v9);
LABEL_21:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v12 = 11;
    goto LABEL_20;
  }
LABEL_22:
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x100) != 0 )
    WPP_SF_d(v11[7], 14, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x1800262ac  push    rbp
0x1800262ae  push    rbx
0x1800262af  push    rsi
0x1800262b0  push    rdi
0x1800262b1  push    r12
0x1800262b3  push    r13
0x1800262b5  push    r14
0x1800262b7  mov     rbp, rsp
0x1800262ba  sub     rsp, 70h
0x1800262be  mov     rax, cs:__security_cookie
0x1800262c5  xor     rax, rsp
0x1800262c8  mov     [rbp+var_10], rax
0x1800262cc  mov     rdi, r9
0x1800262cf  mov     r14, r8
0x1800262d2  mov     ebx, edx
0x1800262d4  mov     rsi, rcx
0x1800262d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262de  lea     r12, WPP_GLOBAL_Control
0x1800262e5  lea     r13, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x1800262ec  cmp     rcx, r12
0x1800262ef  jz      short loc_18002630B
0x1800262f1  test    dword ptr [rcx+44h], 100h
0x1800262f8  jz      short loc_18002630B
0x1800262fa  mov     rcx, [rcx+38h]
0x1800262fe  mov     edx, 0Ah
0x180026303  mov     r8, r13
0x180026306  call    WPP_SF_
0x18002630b  mov     r9, r14
0x18002630e  mov     [rsp+70h+var_48], 0
0x180026317  mov     r14d, 1
0x18002631d  mov     [rsp+70h+var_50], 0
0x180026326  mov     ecx, r14d
0x180026329  mov     r8d, ebx
0x18002632c  mov     rdx, rsi
0x18002632f  call    cs:__imp_OneXUpdatePortProfile
0x180026336  nop     dword ptr [rax+rax+00h]
0x18002633b  mov     ebx, eax
0x18002633d  test    eax, eax
0x18002633f  jz      short loc_180026364
0x180026341  mov     rcx, cs:WPP_GLOBAL_Control
0x180026348  cmp     rcx, r12
0x18002634b  jz      loc_180026470
0x180026351  test    [rcx+44h], r14b
0x180026355  jz      loc_18002644E
0x18002635b  lea     edx, [r14+0Ah]
0x18002635f  jmp     loc_180026438
0x180026364  cmp     [rbp+arg_20], 0
0x180026368  jz      loc_1800263F8
0x18002636e  xor     eax, eax
0x180026370  mov     ecx, 137h; hostlong
0x180026375  mov     [rbp+var_20], rax
0x180026379  mov     [rbp+var_18], eax
0x18002637c  mov     [rbp+var_14], al
0x18002637f  call    cs:__imp_htonl
0x180026386  nop     dword ptr [rax+rax+00h]
0x18002638b  xor     r9d, r9d
0x18002638e  mov     byte ptr [rbp+var_20+4], 46h ; 'F'
0x180026392  mov     dword ptr [rbp+var_20], eax
0x180026395  lea     r8, [rbp+var_30]
0x180026399  lea     rax, [rbp+var_20]
0x18002639d  mov     [rbp+var_20+5], 4
0x1800263a5  mov     [rbp+var_38], rax
0x1800263a9  mov     rdx, rsi
0x1800263ac  lea     rax, [rbp+var_40]
0x1800263b0  mov     [rbp+var_40], 1Ah
0x1800263b7  mov     ecx, r14d
0x1800263ba  mov     [rbp+var_28], rax
0x1800263be  mov     [rbp+var_3C], 0Dh
0x1800263c5  mov     [rbp+var_30], r14
0x1800263c9  call    cs:__imp_OneXAddEapAttributes
0x1800263d0  nop     dword ptr [rax+rax+00h]
0x1800263d5  mov     ebx, eax
0x1800263d7  test    eax, eax
0x1800263d9  jz      short loc_1800263F8
0x1800263db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263e2  cmp     rcx, r12
0x1800263e5  jz      loc_180026470
0x1800263eb  test    [rcx+44h], r14b
0x1800263ef  jz      short loc_18002644E
0x1800263f1  mov     edx, 0Ch
0x1800263f6  jmp     short loc_180026438
0x1800263f8  test    rdi, rdi
0x1800263fb  jz      short loc_180026403
0x1800263fd  mov     r8, [rdi+8]
0x180026401  jmp     short loc_180026406
0x180026403  xor     r8d, r8d
0x180026406  xor     r9d, r9d
0x180026409  mov     rdx, rsi
0x18002640c  mov     ecx, r14d
0x18002640f  call    cs:__imp_OneXSetRuntimeState
0x180026416  nop     dword ptr [rax+rax+00h]
0x18002641b  mov     ebx, eax
0x18002641d  test    eax, eax
0x18002641f  jz      short loc_180026447
0x180026421  mov     rcx, cs:WPP_GLOBAL_Control
0x180026428  cmp     rcx, r12
0x18002642b  jz      short loc_180026470
0x18002642d  test    [rcx+44h], r14b
0x180026431  jz      short loc_18002644E
0x180026433  mov     edx, 0Dh
0x180026438  mov     rcx, [rcx+38h]
0x18002643c  mov     r9d, eax
0x18002643f  mov     r8, r13
0x180026442  call    WPP_SF_d
0x180026447  mov     rcx, cs:WPP_GLOBAL_Control
0x18002644e  cmp     rcx, r12
0x180026451  jz      short loc_180026470
0x180026453  test    dword ptr [rcx+44h], 100h
0x18002645a  jz      short loc_180026470
0x18002645c  mov     rcx, [rcx+38h]
0x180026460  mov     edx, 0Eh
0x180026465  mov     r9d, ebx
0x180026468  mov     r8, r13
0x18002646b  call    WPP_SF_d
0x180026470  mov     eax, ebx
0x180026472  mov     rcx, [rbp+var_10]
0x180026476  xor     rcx, rsp; StackCookie
0x180026479  call    __security_check_cookie
0x18002647e  add     rsp, 70h
0x180026482  pop     r14
0x180026484  pop     r13
0x180026486  pop     r12
0x180026488  pop     rdi
0x180026489  pop     rsi
0x18002648a  pop     rbx
0x18002648b  pop     rbp
0x18002648c  retn
```
