# DigestOpenSamUser

- ea: `0x18002357c`
- end: `0x180023b84`
- name: `DigestOpenSamUser`
- size: `1544`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x18001d5e8`

## callees

- `0x180003520`
- `0x180006d00`
- `0x180009770`
- `0x180011fec`
- `0x1800185b8`
- `0x180018b18`
- `0x180022eb0`
- `0x180023440`
- `0x18002357c`
- `0x180023f80`
- `0x180033680`
- `0x180036d94`
- `0x180036fac`
- `0x1800377bc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180023603`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180023603`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180023829`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180023829`
- `SAMSRV!SamIAccountRestrictions` at `0x180023a55`
- `SAMSRV!SamIAccountRestrictions` at `0x180023a55`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180023840`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180023840`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x180023695`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x1800236ed`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x18002375e`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x180023695`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x1800236ed`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x18002375e`

## pseudocode

```c
__int64 __fastcall DigestOpenSamUser(__int64 a1, _QWORD *a2, HLOCAL *a3, unsigned int *a4)
{
  unsigned int *v4; // r14
  int v8; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  int inited; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  int v14; // eax
  size_t v15; // rdi
  int v16; // eax
  int v17; // eax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  struct _SAMPR_GET_GROUPS_BUFFER *v22; // rdx
  struct _PACTYPE *v23; // rsi
  unsigned int v24; // eax
  void *v25; // rax
  unsigned int *v26; // rdi
  unsigned int v27; // eax
  unsigned int v28; // edx
  __int64 v29; // rax
  unsigned __int64 v30; // rcx
  unsigned int v31; // [rsp+40h] [rbp-39h]
  struct _PAC_INFO_BUFFER **v32; // [rsp+48h] [rbp-31h]
  union _LARGE_INTEGER *v33; // [rsp+50h] [rbp-29h]
  union _LARGE_INTEGER *v34; // [rsp+58h] [rbp-21h]
  struct _LSA_LAST_INTER_LOGON_INFO *v35; // [rsp+60h] [rbp-19h]
  struct _UNICODE_STRING v36; // [rsp+70h] [rbp-9h] BYREF
  void *Src; // [rsp+80h] [rbp+7h] BYREF
  unsigned int v38[4]; // [rsp+88h] [rbp+Fh] BYREF
  size_t Size; // [rsp+E8h] [rbp+6Fh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+F0h] [rbp+77h] BYREF
  unsigned int *v41; // [rsp+F8h] [rbp+7Fh]

  v41 = a4;
  Size = 0;
  v4 = a4;
  *(_OWORD *)v38 = 0;
  SystemTimeAsFileTime = 0;
  v36.Buffer = 0;
  *(_QWORD *)&v36.Length = 0;
  Src = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids);
  *a3 = 0;
  *v4 = 0;
  *a2 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v8 = DigestOpenSam();
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids,
        (unsigned int)v8);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_30;
  }
  v31 = (unsigned int)a2;
  if ( *(_WORD *)(a1 + 496) )
  {
    inited = SamIGetUserLogonInformation2(l_AccountDomainHandle, 0, a1 + 496, 1827853, 256, 0);
    v9 = inited;
    if ( inited < 0 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_29;
      v12 = 42;
      goto LABEL_13;
    }
  }
  else
  {
    v14 = SamIGetUserLogonInformation2(l_AccountDomainHandle, 0, a1 + 472, 1827853, 256, 0);
    if ( v14 >= 0 )
    {
      *(_DWORD *)(a1 + 488) = 1;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids,
          (unsigned int)v14);
      v31 = (unsigned int)a2;
      inited = SamIGetUserLogonInformation2(l_AccountDomainHandle, 512, a1 + 472, 1827853, 256, 0);
      v9 = inited;
      if ( inited < 0 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_29;
        v12 = 44;
LABEL_13:
        v13 = (unsigned int)inited;
LABEL_14:
        WPP_SF_d(v10[2], v12, &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids, v13);
        v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_29:
        v4 = v41;
        goto LABEL_30;
      }
      *(_DWORD *)(a1 + 488) = 2;
    }
  }
  v15 = Size;
  UnicodeStringFree(a1 + 496);
  UnicodeStringFree(a1 + 512);
  v16 = UnicodeStringWCharDuplicate(a1 + 496, *(_QWORD *)(v15 + 56), *(_WORD *)(v15 + 48) >> 1);
  v9 = v16;
  if ( v16 < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids,
        (unsigned int)v16);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_29;
  }
  inited = UnicodeStringDuplicate(a1 + 512, &word_1800459F8);
  v9 = inited;
  if ( inited < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_29;
    v12 = 46;
    goto LABEL_13;
  }
  *(_WORD *)(a1 + 4) &= ~1u;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids,
      *(unsigned __int16 *)(v15 + 304),
      *(unsigned __int16 *)(v15 + 306));
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  v19 = *(_DWORD *)(v15 + 280);
  if ( (v19 & 1) != 0 )
  {
    v9 = -1073741710;
    goto LABEL_29;
  }
  if ( (v19 & 0x400) != 0 )
  {
    v9 = -1073741260;
    goto LABEL_29;
  }
  if ( (v19 & 0x1000) != 0 )
  {
    v9 = -1073741062;
    goto LABEL_29;
  }
  v20 = *(_QWORD *)(v15 + 24);
  if ( v20 && v20 < *(_QWORD *)&SystemTimeAsFileTime )
  {
    v9 = -1073741421;
    goto LABEL_29;
  }
  if ( (v19 & 0x10) != 0 )
  {
    v21 = *(_QWORD *)(v15 + 40);
    if ( v21 < *(_QWORD *)&SystemTimeAsFileTime )
    {
      v9 = v21 != 0 ? -1073741711 : -1073741276;
      if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 )
        goto LABEL_29;
      v12 = 48;
      v13 = v9;
      goto LABEL_14;
    }
  }
  if ( (v19 & 0x20000) != 0 )
  {
    v9 = -1073741711;
    goto LABEL_29;
  }
  inited = SamIAccountRestrictions(*a2, a1 + 528, v15 + 160, v15 + 288, &v36.Buffer);
  v9 = inited;
  if ( inited < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_29;
    v12 = 49;
    goto LABEL_13;
  }
  *(_DWORD *)(a1 + 1032) = *(_DWORD *)(v15 + 272);
  inited = PAC_InitEx2(
             (struct _SAMPR_USER_ALL_INFORMATION *)v15,
             v22,
             (struct _SID_AND_ATTRIBUTES_LIST *)v38,
             hMem,
             &stru_180045A08,
             &v36,
             (size_t)&Size,
             (unsigned int)v38,
             v31,
             v32,
             v33,
             v34,
             v35,
             (struct _PACTYPE **)&Src);
  v9 = inited;
  if ( inited < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_29;
    v12 = 50;
    goto LABEL_13;
  }
  v23 = (struct _PACTYPE *)Src;
  v24 = PAC_GetSize((struct _PACTYPE *)Src);
  v4 = v41;
  *v41 = v24;
  v25 = MIDL_user_allocate(v24);
  *a3 = v25;
  v26 = (unsigned int *)v25;
  if ( v25 )
  {
    v27 = PAC_GetSize(v23);
    if ( *v4 >= v27 )
    {
      memcpy_0(v26, v23, v27);
      v28 = 0;
      if ( *v26 )
      {
        while ( 1 )
        {
          v29 = 2LL * v28;
          v30 = *(_QWORD *)&v26[4 * v28 + 4];
          if ( v30 < (unsigned __int64)v23 )
            break;
          ++v28;
          *(_QWORD *)&v26[2 * v29 + 4] = v30 - (_QWORD)v23;
          if ( v28 >= *v26 )
            goto LABEL_86;
        }
        *(_QWORD *)&v26[4 * v28 + 4] = -1;
      }
    }
  }
  else
  {
    v9 = -2146893056;
  }
LABEL_86:
  DigestFreeMemory(v23);
  v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_30:
  if ( Size )
  {
    SamIFree_UserInternal6Information(Size);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)&v38[2] )
  {
    SamIFreeSidAndAttributesList(v38);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (v9 & 0x80000000) != 0 )
  {
    if ( *a3 )
    {
      DigestFreeMemory(*a3);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      *a3 = 0;
      *v4 = 0;
    }
    if ( *a2 )
    {
      v17 = DigestCloseSamUser(*a2);
      if ( v17 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids,
          (unsigned int)v17);
      *a2 = 0;
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v10 != &WPP_GLOBAL_Control && *((char *)v10 + 28) < 0 )
    WPP_SF_d(v10[2], 52, &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18002357c  mov     [rsp-8+arg_0], rbx
0x180023581  mov     [rsp-8+arg_18], r9
0x180023586  push    rbp
0x180023587  push    rsi
0x180023588  push    rdi
0x180023589  push    r12
0x18002358b  push    r13
0x18002358d  push    r14
0x18002358f  push    r15
0x180023591  lea     rbp, [rsp-27h]
0x180023596  sub     rsp, 0A0h
0x18002359d  xor     r15d, r15d
0x1800235a0  xorps   xmm0, xmm0
0x1800235a3  mov     [rbp+57h+arg_8], r15
0x1800235a7  mov     r14, r9
0x1800235aa  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x1800235ae  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15
0x1800235b2  mov     r13, r8
0x1800235b5  mov     [rbp+57h+var_60.Buffer], r15
0x1800235b9  mov     r12, rdx
0x1800235bc  mov     qword ptr [rbp+57h+var_60.Length], r15
0x1800235c0  mov     rsi, rcx
0x1800235c3  mov     [rbp+57h+Src], r15
0x1800235c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235ce  lea     rdi, WPP_GLOBAL_Control
0x1800235d5  cmp     rcx, rdi
0x1800235d8  jz      short loc_1800235F4
0x1800235da  test    byte ptr [rcx+1Ch], 80h
0x1800235de  jz      short loc_1800235F4
0x1800235e0  mov     rcx, [rcx+10h]
0x1800235e4  lea     edx, [r15+28h]
0x1800235e8  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x1800235ef  call    WPP_SF_
0x1800235f4  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800235f8  mov     [r13+0], r15
0x1800235fc  mov     [r14], r15d
0x1800235ff  mov     [r12], r15
0x180023603  call    cs:__imp_GetSystemTimeAsFileTime
0x180023609  call    DigestOpenSam
0x18002360e  mov     ebx, eax
0x180023610  test    eax, eax
0x180023612  jns     short loc_180023652
0x180023614  mov     rcx, cs:WPP_GLOBAL_Control
0x18002361b  cmp     rcx, rdi
0x18002361e  jz      loc_18002381D
0x180023624  test    byte ptr [rcx+1Ch], 1
0x180023628  jz      loc_18002381D
0x18002362e  mov     rcx, [rcx+10h]
0x180023632  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180023639  mov     edx, 29h ; ')'
0x18002363e  mov     r9d, eax
0x180023641  call    WPP_SF_d
0x180023646  mov     rcx, cs:WPP_GLOBAL_Control
0x18002364d  jmp     loc_18002381D
0x180023652  mov     rcx, cs:?l_AccountDomainHandle@@3PEAXEA; void * l_AccountDomainHandle
0x180023659  lea     rax, [rbp+57h+var_48]
0x18002365d  mov     qword ptr [rsp+0D0h+var_90], r12; unsigned int
0x180023662  lea     r14, [rsi+1F0h]
0x180023669  mov     qword ptr [rsp+0D0h+var_98], rax; unsigned int
0x18002366e  xor     edx, edx
0x180023670  lea     rax, [rbp+57h+arg_8]
0x180023674  mov     r9d, 1BE40Dh
0x18002367a  mov     [rsp+0D0h+Size], rax; Size
0x18002367f  mov     [rsp+0D0h+var_A8], r15
0x180023684  mov     dword ptr [rsp+0D0h+var_B0], 100h
0x18002368c  cmp     [r14], r15w
0x180023690  jz      short loc_1800236E3
0x180023692  mov     r8, r14
0x180023695  call    cs:__imp_SamIGetUserLogonInformation2
0x18002369b  mov     ebx, eax
0x18002369d  test    eax, eax
0x18002369f  jns     loc_1800237A4
0x1800236a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236ac  cmp     rcx, rdi
0x1800236af  jz      loc_180023819
0x1800236b5  test    byte ptr [rcx+1Ch], 1
0x1800236b9  jz      loc_180023819
0x1800236bf  mov     edx, 2Ah ; '*'
0x1800236c4  mov     r9d, eax
0x1800236c7  mov     rcx, [rcx+10h]
0x1800236cb  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x1800236d2  call    WPP_SF_d
0x1800236d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236de  jmp     loc_180023819
0x1800236e3  lea     rbx, [rsi+1D8h]
0x1800236ea  mov     r8, rbx
0x1800236ed  call    cs:__imp_SamIGetUserLogonInformation2
0x1800236f3  test    eax, eax
0x1800236f5  jns     loc_18002379A
0x1800236fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180023702  cmp     rcx, rdi
0x180023705  jz      short loc_180023725
0x180023707  test    byte ptr [rcx+1Ch], 4
0x18002370b  jz      short loc_180023725
0x18002370d  mov     rcx, [rcx+10h]
0x180023711  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180023718  mov     edx, 2Bh ; '+'
0x18002371d  mov     r9d, eax
0x180023720  call    WPP_SF_d
0x180023725  mov     rcx, cs:?l_AccountDomainHandle@@3PEAXEA; void * l_AccountDomainHandle
0x18002372c  lea     rax, [rbp+57h+var_48]
0x180023730  mov     qword ptr [rsp+0D0h+var_90], r12
0x180023735  mov     r9d, 1BE40Dh
0x18002373b  mov     qword ptr [rsp+0D0h+var_98], rax
0x180023740  mov     r8, rbx
0x180023743  lea     rax, [rbp+57h+arg_8]
0x180023747  mov     edx, 200h
0x18002374c  mov     [rsp+0D0h+Size], rax
0x180023751  mov     [rsp+0D0h+var_A8], r15
0x180023756  mov     dword ptr [rsp+0D0h+var_B0], 100h
0x18002375e  call    cs:__imp_SamIGetUserLogonInformation2
0x180023764  mov     ebx, eax
0x180023766  test    eax, eax
0x180023768  jns     short loc_18002378E
0x18002376a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023771  cmp     rcx, rdi
0x180023774  jz      loc_180023819
0x18002377a  test    byte ptr [rcx+1Ch], 1
0x18002377e  jz      loc_180023819
0x180023784  mov     edx, 2Ch ; ','
0x180023789  jmp     loc_1800236C4
0x18002378e  mov     dword ptr [rsi+1E8h], 2
0x180023798  jmp     short loc_1800237A4
0x18002379a  mov     dword ptr [rsi+1E8h], 1
0x1800237a4  mov     rdi, [rbp+57h+arg_8]
0x1800237a8  mov     rcx, r14
0x1800237ab  call    UnicodeStringFree
0x1800237b0  lea     r15, [rsi+200h]
0x1800237b7  mov     rcx, r15
0x1800237ba  call    UnicodeStringFree
0x1800237bf  movzx   r8d, word ptr [rdi+30h]
0x1800237c4  mov     rcx, r14
0x1800237c7  mov     rdx, [rdi+38h]
0x1800237cb  shr     r8w, 1
0x1800237cf  call    UnicodeStringWCharDuplicate
0x1800237d4  mov     ebx, eax
0x1800237d6  test    eax, eax
0x1800237d8  jns     loc_1800238F6
0x1800237de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800237e5  lea     rdi, WPP_GLOBAL_Control
0x1800237ec  cmp     rcx, rdi
0x1800237ef  jz      short loc_180023816
0x1800237f1  test    byte ptr [rcx+1Ch], 1
0x1800237f5  jz      short loc_180023816
0x1800237f7  mov     rcx, [rcx+10h]
0x1800237fb  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180023802  mov     edx, 2Dh ; '-'
0x180023807  mov     r9d, eax
0x18002380a  call    WPP_SF_d
0x18002380f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023816  xor     r15d, r15d
0x180023819  mov     r14, [rbp+57h+arg_18]
0x18002381d  mov     rax, [rbp+57h+arg_8]
0x180023821  test    rax, rax
0x180023824  jz      short loc_180023836
0x180023826  mov     rcx, rax
0x180023829  call    cs:__imp_SamIFree_UserInternal6Information
0x18002382f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023836  cmp     qword ptr [rbp+57h+var_48+8], r15
0x18002383a  jz      short loc_18002384D
0x18002383c  lea     rcx, [rbp+57h+var_48]
0x180023840  call    cs:__imp_SamIFreeSidAndAttributesList
0x180023846  mov     rcx, cs:WPP_GLOBAL_Control
0x18002384d  test    ebx, ebx
0x18002384f  jns     short loc_1800238B6
0x180023851  cmp     [r13+0], r15
0x180023855  jz      short loc_18002386E
0x180023857  mov     rcx, [r13+0]; hMem
0x18002385b  call    DigestFreeMemory
0x180023860  mov     rcx, cs:WPP_GLOBAL_Control
0x180023867  mov     [r13+0], r15
0x18002386b  mov     [r14], r15d
0x18002386e  cmp     [r12], r15
0x180023872  jz      short loc_1800238B6
0x180023874  mov     rcx, [r12]
0x180023878  call    DigestCloseSamUser
0x18002387d  test    eax, eax
0x18002387f  jns     short loc_1800238AB
0x180023881  mov     rcx, cs:WPP_GLOBAL_Control
0x180023888  cmp     rcx, rdi
0x18002388b  jz      short loc_1800238AB
0x18002388d  test    byte ptr [rcx+1Ch], 1
0x180023891  jz      short loc_1800238AB
0x180023893  mov     rcx, [rcx+10h]
0x180023897  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x18002389e  mov     edx, 33h ; '3'
0x1800238a3  mov     r9d, eax
0x1800238a6  call    WPP_SF_d
0x1800238ab  mov     [r12], r15
0x1800238af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238b6  cmp     rcx, rdi
0x1800238b9  jz      short loc_1800238D9
0x1800238bb  test    byte ptr [rcx+1Ch], 80h
0x1800238bf  jz      short loc_1800238D9
0x1800238c1  mov     rcx, [rcx+10h]
0x1800238c5  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x1800238cc  mov     edx, 34h ; '4'
0x1800238d1  mov     r9d, ebx
0x1800238d4  call    WPP_SF_d
0x1800238d9  mov     eax, ebx
0x1800238db  mov     rbx, [rsp+0D0h+arg_0]
0x1800238e3  add     rsp, 0A0h
0x1800238ea  pop     r15
0x1800238ec  pop     r14
0x1800238ee  pop     r13
0x1800238f0  pop     r12
0x1800238f2  pop     rdi
0x1800238f3  pop     rsi
0x1800238f4  pop     rbp
0x1800238f5  retn
0x1800238f6  lea     rdx, word_1800459F8
0x1800238fd  mov     rcx, r15
0x180023900  call    UnicodeStringDuplicate
0x180023905  xor     r15d, r15d
0x180023908  mov     ebx, eax
0x18002390a  test    eax, eax
0x18002390c  jns     short loc_180023938
0x18002390e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023915  lea     rdi, WPP_GLOBAL_Control
0x18002391c  cmp     rcx, rdi
0x18002391f  jz      loc_180023819
0x180023925  test    byte ptr [rcx+1Ch], 1
0x180023929  jz      loc_180023819
0x18002392f  lea     edx, [r15+2Eh]
0x180023933  jmp     loc_1800236C4
0x180023938  mov     eax, 0FFFEh
0x18002393d  and     [rsi+4], ax
0x180023941  mov     rcx, cs:WPP_GLOBAL_Control
0x180023948  lea     rax, WPP_GLOBAL_Control
0x18002394f  cmp     rcx, rax
0x180023952  jz      short loc_180023989
0x180023954  test    byte ptr [rcx+1Ch], 4
0x180023958  jz      short loc_180023989
0x18002395a  movzx   eax, word ptr [rdi+132h]
0x180023961  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180023968  movzx   r9d, word ptr [rdi+130h]
0x180023970  mov     edx, 2Fh ; '/'
0x180023975  mov     rcx, [rcx+10h]
0x180023979  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18002397d  call    WPP_SF_dd
0x180023982  mov     rcx, cs:WPP_GLOBAL_Control
0x180023989  mov     eax, [rdi+118h]
0x18002398f  test    al, 1
0x180023991  jz      short loc_1800239A4
0x180023993  mov     ebx, 0C0000072h
0x180023998  lea     rdi, WPP_GLOBAL_Control
0x18002399f  jmp     loc_180023819
0x1800239a4  bt      eax, 0Ah
0x1800239a8  jnb     short loc_1800239B1
0x1800239aa  mov     ebx, 0C0000234h
0x1800239af  jmp     short loc_180023998
0x1800239b1  bt      eax, 0Ch
0x1800239b5  jnb     short loc_1800239BE
0x1800239b7  mov     ebx, 0C00002FAh
0x1800239bc  jmp     short loc_180023998
0x1800239be  mov     rdx, [rdi+18h]
0x1800239c2  test    rdx, rdx
0x1800239c5  jz      short loc_1800239D4
0x1800239c7  cmp     rdx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800239cb  jge     short loc_1800239D4
0x1800239cd  mov     ebx, 0C0000193h
0x1800239d2  jmp     short loc_180023998
0x1800239d4  test    al, 10h
0x1800239d6  jz      short loc_180023A1A
0x1800239d8  mov     rdx, [rdi+28h]
0x1800239dc  cmp     rdx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800239e0  jge     short loc_180023A1A
0x1800239e2  neg     rdx
0x1800239e5  lea     rdi, WPP_GLOBAL_Control
0x1800239ec  sbb     ebx, ebx
0x1800239ee  and     ebx, 0FFFFFE4Dh
0x1800239f4  add     ebx, 0C0000224h
0x1800239fa  cmp     rcx, rdi
0x1800239fd  jz      loc_180023819
0x180023a03  test    byte ptr [rcx+1Ch], 1
0x180023a07  jz      loc_180023819
0x180023a0d  mov     edx, 30h ; '0'
0x180023a12  mov     r9d, ebx
0x180023a15  jmp     loc_1800236C7
0x180023a1a  bt      eax, 11h
0x180023a1e  jnb     short loc_180023A2A
0x180023a20  mov     ebx, 0C0000071h
0x180023a25  jmp     loc_180023998
0x180023a2a  mov     rcx, [r12]
0x180023a2e  lea     rax, [rbp+57h+var_60]
0x180023a32  mov     [rsp+0D0h+var_A8], rax; struct _UNICODE_STRING *
0x180023a37  lea     r9, [rdi+120h]
0x180023a3e  lea     rax, [rbp+57h+var_60.Buffer]
0x180023a42  lea     r8, [rdi+0A0h]
0x180023a49  mov     [rsp+0D0h+var_B0], rax
0x180023a4e  lea     rdx, [rsi+210h]
0x180023a55  call    cs:__imp_SamIAccountRestrictions
0x180023a5b  mov     ebx, eax
0x180023a5d  test    eax, eax
0x180023a5f  jns     short loc_180023A8C
0x180023a61  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a68  lea     rdi, WPP_GLOBAL_Control
0x180023a6f  cmp     rcx, rdi
0x180023a72  jz      loc_180023819
0x180023a78  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
