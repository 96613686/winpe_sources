# CSGetUserAccountInfo

- ea: `0x1800020d0`
- end: `0x180002668`
- name: `CSGetUserAccountInfo`
- size: `1432`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180002ff0`
- `0x180014d90`

## callees

- `0x1800020d0`
- `0x180002670`
- `0x1800037e0`
- `0x1800039e0`
- `0x180003a60`
- `0x180007300`
- `0x18000cb84`
- `0x180010744`
- `0x180012f18`
- `0x180013240`
- `0x1800132b4`
- `0x180016ce9`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002250`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002250`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002361`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800023d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002415`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002361`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800023d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002415`
- `SAMLIB!SamQueryInformationUser` at `0x1800022ce`
- `SAMLIB!SamQueryInformationUser` at `0x18000233f`
- `SAMLIB!SamQueryInformationUser` at `0x1800024e0`
- `SAMLIB!SamQueryInformationUser` at `0x1800022ce`
- `SAMLIB!SamQueryInformationUser` at `0x18000233f`
- `SAMLIB!SamQueryInformationUser` at `0x1800024e0`
- `SAMLIB!SamOpenUser` at `0x1800022ad`
- `SAMLIB!SamOpenUser` at `0x1800022ad`
- `SAMLIB!SamLookupNamesInDomain2` at `0x180002276`
- `SAMLIB!SamLookupNamesInDomain2` at `0x180002276`
- `SAMLIB!SamOpenDomain` at `0x1800021c9`
- `SAMLIB!SamOpenDomain` at `0x1800021c9`
- `SAMLIB!SamConnect` at `0x1800021a9`
- `SAMLIB!SamConnect` at `0x1800021a9`
- `SAMLIB!SamCloseHandle` at `0x1800021e9`
- `SAMLIB!SamCloseHandle` at `0x180002512`
- `SAMLIB!SamCloseHandle` at `0x1800025a3`
- `SAMLIB!SamCloseHandle` at `0x1800025ad`
- `SAMLIB!SamCloseHandle` at `0x1800025ea`
- `SAMLIB!SamCloseHandle` at `0x1800025f4`
- `SAMLIB!SamCloseHandle` at `0x1800021e9`
- `SAMLIB!SamCloseHandle` at `0x180002512`
- `SAMLIB!SamCloseHandle` at `0x1800025a3`
- `SAMLIB!SamCloseHandle` at `0x1800025ad`
- `SAMLIB!SamCloseHandle` at `0x1800025ea`
- `SAMLIB!SamCloseHandle` at `0x1800025f4`
- `SAMLIB!SamFreeMemory` at `0x1800022ec`
- `SAMLIB!SamFreeMemory` at `0x180002491`
- `SAMLIB!SamFreeMemory` at `0x180002508`
- `SAMLIB!SamFreeMemory` at `0x180002557`
- `SAMLIB!SamFreeMemory` at `0x180002561`
- `SAMLIB!SamFreeMemory` at `0x1800022ec`
- `SAMLIB!SamFreeMemory` at `0x180002491`
- `SAMLIB!SamFreeMemory` at `0x180002508`
- `SAMLIB!SamFreeMemory` at `0x180002557`
- `SAMLIB!SamFreeMemory` at `0x180002561`

## pseudocode

```c
__int64 __fastcall CSGetUserAccountInfo(
        void *a1,
        __int64 a2,
        __int64 a3,
        struct _USER_ALL_INFORMATION **a4,
        struct _USER_EXTENDED_INFORMATION **a5,
        _DWORD *a6,
        _DWORD *a7)
{
  void *v9; // rbx
  struct _USER_EXTENDED_INFORMATION **v10; // r13
  __int64 v12; // r15
  int v13; // eax
  int v14; // edi
  int v15; // r14d
  int v16; // edi
  int v17; // edi
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  int v20; // ebx
  __int64 v21; // r8
  int v22; // ebx
  int v23; // r8d
  int v24; // ebx
  int v25; // r8d
  int v26; // ebx
  int v27; // ebx
  int v28; // r8d
  unsigned __int8 *v29; // rsi
  _DWORD *v30; // rax
  _DWORD *v31; // rdi
  size_t v32; // rax
  unsigned int v33; // eax
  void *v34; // rax
  unsigned int v35; // eax
  void *v36; // rax
  unsigned __int8 *v37; // rcx
  unsigned __int8 *v38; // [rsp+30h] [rbp-51h] BYREF
  __int64 v39; // [rsp+38h] [rbp-49h] BYREF
  struct _USER_ALL_INFORMATION *v40; // [rsp+40h] [rbp-41h] BYREF
  unsigned int *v41; // [rsp+48h] [rbp-39h] BYREF
  _DWORD *v42; // [rsp+50h] [rbp-31h] BYREF
  __int64 v43; // [rsp+58h] [rbp-29h]
  __int64 v44; // [rsp+60h] [rbp-21h] BYREF
  _QWORD v45[4]; // [rsp+68h] [rbp-19h] BYREF
  __int128 v46; // [rsp+88h] [rbp+7h]
  LPVOID pv; // [rsp+E8h] [rbp+67h] BYREF

  v42 = 0;
  v41 = 0;
  v9 = a1;
  if ( !a4 )
    return 2147500035LL;
  v10 = a5;
  if ( !a5 || !a3 )
    return 2147500035LL;
  if ( !*(_QWORD *)(a3 + 8) )
    return 2147942487LL;
  v12 = 0;
  *a4 = 0;
  *v10 = 0;
  pv = a1;
  v43 = 0;
  if ( a1 )
  {
    v15 = 0;
    goto LABEL_10;
  }
  v13 = CSGetAccountDomainSid(&pv);
  v9 = pv;
  v14 = v13;
  v15 = 1;
  if ( v13 >= 0 )
  {
LABEL_10:
    v45[0] = 48;
    v39 = 0;
    memset(&v45[1], 0, 24);
    v46 = 0;
    v16 = SamConnect(0, &v39, 131105, v45);
    if ( v16 < 0 )
    {
      v14 = v16 | 0x10000000;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v19 = 35;
        goto LABEL_19;
      }
    }
    else
    {
      v44 = 0;
      v17 = SamOpenDomain(v39, 131973, v9, &v44);
      if ( v17 >= 0 )
      {
        v14 = 0;
        v12 = v44;
        v43 = v39;
        goto LABEL_20;
      }
      SamCloseHandle(v39);
      v14 = v17 | 0x10000000;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v19 = 34;
LABEL_19:
        WPP_SF_d(v18[2], v19, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, (unsigned int)v14);
      }
    }
LABEL_20:
    if ( !v15 )
      goto LABEL_22;
  }
  CoTaskMemFree(v9);
LABEL_22:
  if ( v14 < 0 )
    return (unsigned int)v14;
  v20 = SamLookupNamesInDomain2(v12, 1, a3, &v41, &v42);
  if ( v20 >= 0 )
  {
    if ( *v42 != 1 )
    {
      v26 = -805306270;
      goto LABEL_69;
    }
    pv = 0;
    v22 = SamOpenUser(v12, 131867, *v41, &pv);
    if ( v22 < 0 )
    {
      v26 = v22 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, v23, a3, v26);
      goto LABEL_69;
    }
    v40 = 0;
    v24 = SamQueryInformationUser(pv, 21, &v40);
    if ( v24 < 0 )
    {
      v26 = v24 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, v25, a3, v26);
    }
    else
    {
      v26 = CopyUserStructure(v40, a4);
      SamFreeMemory(v40);
    }
    if ( v26 < 0 )
    {
LABEL_64:
      SamCloseHandle(pv);
LABEL_69:
      SamFreeMemory(v41);
      SamFreeMemory(v42);
      goto LABEL_78;
    }
    v38 = 0;
    v27 = SamQueryInformationUser(pv, 28, &v38);
    if ( v27 < 0 )
    {
      v26 = v27 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, v28, a3, v26);
      goto LABEL_61;
    }
    v29 = v38;
    if ( !v38 )
    {
      v31 = 0;
      v26 = -2147467261;
      goto LABEL_54;
    }
    v30 = CoTaskMemAlloc(0xA8u);
    v31 = v30;
    if ( !v30 )
      goto LABEL_43;
    v32 = CTCoAllocPolicy::_CoTaskMemSize(v30);
    memset_0(v31, 0, v32);
    *v31 = *(_DWORD *)v29;
    *((_BYTE *)v31 + 40) = v29[40];
    if ( *((_WORD *)v29 + 12) && *((_QWORD *)v29 + 4) )
    {
      v26 = CopyUnicodeStringAlloc((struct _UNICODE_STRING *const)(v29 + 24), (struct _UNICODE_STRING *)(v31 + 6));
      if ( v26 < 0 )
      {
LABEL_54:
        FreeUserExtStructure((struct _USER_EXTENDED_INFORMATION *)v31, 1);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            39,
            WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
            (unsigned int)v26);
        goto LABEL_57;
      }
    }
    else
    {
      v26 = 0;
      v31[6] = 0;
      *((_QWORD *)v31 + 4) = 0;
    }
    v31[2] = *((_DWORD *)v29 + 2);
    v33 = *((_DWORD *)v29 + 2);
    if ( v33 && *((_QWORD *)v29 + 2) )
    {
      v34 = CoTaskMemAlloc(v33);
      *((_QWORD *)v31 + 2) = v34;
      if ( !v34 )
      {
LABEL_43:
        v26 = -2147024882;
        goto LABEL_54;
      }
      memcpy_0(v34, *((const void **)v29 + 2), *((unsigned int *)v29 + 2));
    }
    else
    {
      *((_QWORD *)v31 + 2) = 0;
    }
    v31[12] = *((_DWORD *)v29 + 12);
    v35 = *((_DWORD *)v29 + 12);
    if ( v35 && *((_QWORD *)v29 + 7) )
    {
      v36 = CoTaskMemAlloc(v35);
      *((_QWORD *)v31 + 7) = v36;
      if ( !v36 )
      {
        v26 = -2147024882;
        goto LABEL_54;
      }
      memcpy_0(v36, *((const void **)v29 + 7), *((unsigned int *)v29 + 12));
    }
    else
    {
      *((_QWORD *)v31 + 7) = 0;
    }
    *v10 = (struct _USER_EXTENDED_INFORMATION *)v31;
LABEL_57:
    SamFreeMemory(v38);
LABEL_61:
    if ( v26 >= 0 )
    {
      v38 = 0;
      if ( (int)SamQueryInformationUser(pv, 29, &v38) >= 0 )
      {
        v37 = v38;
        *a6 = *v38;
        *a7 = 2 - (v37[1] != 0);
        SamFreeMemory(v37);
      }
    }
    goto LABEL_64;
  }
  if ( v20 == -1073741724 )
  {
    v26 = -2147023728;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, v21, a3);
    SamCloseHandle(v12);
    SamCloseHandle(v43);
    goto LABEL_79;
  }
  v26 = v20 | 0x10000000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, v21, a3, v26);
LABEL_78:
  SamCloseHandle(v12);
  SamCloseHandle(v43);
  if ( v26 < 0 )
  {
LABEL_79:
    if ( *a4 )
    {
      FreeUserStructure(*a4, 1);
      *a4 = 0;
    }
    if ( *v10 )
    {
      FreeUserExtStructure(*v10, 1);
      *v10 = 0;
    }
  }
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x1800020d0  push    rbp
0x1800020d2  push    rbx
0x1800020d3  push    rsi
0x1800020d4  push    r12
0x1800020d6  push    r13
0x1800020d8  lea     rbp, [rsp-1Fh]
0x1800020dd  sub     rsp, 0A0h
0x1800020e4  xor     eax, eax
0x1800020e6  mov     r12, r9
0x1800020e9  mov     [rbp+3Fh+var_70], rax
0x1800020ed  mov     rsi, r8
0x1800020f0  mov     [rbp+3Fh+var_78], rax
0x1800020f4  mov     rbx, rcx
0x1800020f7  test    r9, r9
0x1800020fa  jz      loc_180002661
0x180002100  mov     r13, [rbp+3Fh+arg_20]
0x180002104  test    r13, r13
0x180002107  jz      loc_180002661
0x18000210d  test    r8, r8
0x180002110  jz      loc_180002661
0x180002116  cmp     [r8+8], rax
0x18000211a  jnz     short loc_180002126
0x18000211c  mov     eax, 80070057h
0x180002121  jmp     loc_18000264E
0x180002126  mov     [rsp+0C0h+arg_0], rdi
0x18000212e  mov     [rsp+0C0h+arg_8], r14
0x180002136  mov     [rsp+0C0h+arg_10], r15
0x18000213e  mov     r15, rax
0x180002141  mov     [r9], rax
0x180002144  mov     [r13+0], rax
0x180002148  mov     [rbp+3Fh+pv], rcx
0x18000214c  mov     [rbp+3Fh+var_68], rax
0x180002150  test    rcx, rcx
0x180002153  jnz     short loc_180002176
0x180002155  lea     rcx, [rbp+3Fh+pv]
0x180002159  call    CSGetAccountDomainSid
0x18000215e  mov     rbx, [rbp+3Fh+pv]
0x180002162  mov     edi, eax
0x180002164  mov     r14d, 1
0x18000216a  test    eax, eax
0x18000216c  js      loc_18000224D
0x180002172  xor     eax, eax
0x180002174  jmp     short loc_180002179
0x180002176  mov     r14d, eax
0x180002179  xorps   xmm0, xmm0
0x18000217c  mov     [rbp+3Fh+var_58], 30h ; '0'
0x180002184  lea     r9, [rbp+3Fh+var_58]
0x180002188  mov     [rbp+3Fh+var_40], r15
0x18000218c  mov     r8d, 20021h
0x180002192  mov     [rbp+3Fh+var_88], rax
0x180002196  lea     rdx, [rbp+3Fh+var_88]
0x18000219a  mov     [rbp+3Fh+var_50], rax
0x18000219e  xor     ecx, ecx
0x1800021a0  mov     [rbp+3Fh+var_48], rax
0x1800021a4  movdqu  [rbp+3Fh+var_38], xmm0
0x1800021a9  call    cs:__imp_SamConnect
0x1800021af  mov     edi, eax
0x1800021b1  test    eax, eax
0x1800021b3  js      short loc_180002213
0x1800021b5  mov     rcx, [rbp+3Fh+var_88]
0x1800021b9  lea     r9, [rbp+3Fh+var_60]
0x1800021bd  mov     r8, rbx
0x1800021c0  mov     [rbp+3Fh+var_60], r15
0x1800021c4  mov     edx, 20385h
0x1800021c9  call    cs:__imp_SamOpenDomain
0x1800021cf  mov     edi, eax
0x1800021d1  test    eax, eax
0x1800021d3  js      short loc_1800021E5
0x1800021d5  mov     rax, [rbp+3Fh+var_88]
0x1800021d9  xor     edi, edi
0x1800021db  mov     r15, [rbp+3Fh+var_60]
0x1800021df  mov     [rbp+3Fh+var_68], rax
0x1800021e3  jmp     short loc_180002248
0x1800021e5  mov     rcx, [rbp+3Fh+var_88]
0x1800021e9  call    cs:__imp_SamCloseHandle
0x1800021ef  bts     edi, 1Ch
0x1800021f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021fa  lea     rax, WPP_GLOBAL_Control
0x180002201  cmp     rcx, rax
0x180002204  jz      short loc_180002248
0x180002206  test    byte ptr [rcx+1Ch], 2
0x18000220a  jz      short loc_180002248
0x18000220c  mov     edx, 22h ; '"'
0x180002211  jmp     short loc_180002235
0x180002213  bts     edi, 1Ch
0x180002217  mov     rcx, cs:WPP_GLOBAL_Control
0x18000221e  lea     rax, WPP_GLOBAL_Control
0x180002225  cmp     rcx, rax
0x180002228  jz      short loc_180002248
0x18000222a  test    byte ptr [rcx+1Ch], 2
0x18000222e  jz      short loc_180002248
0x180002230  mov     edx, 23h ; '#'
0x180002235  mov     rcx, [rcx+10h]
0x180002239  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180002240  mov     r9d, edi
0x180002243  call    WPP_SF_d
0x180002248  test    r14d, r14d
0x18000224b  jz      short loc_180002256
0x18000224d  mov     rcx, rbx; pv
0x180002250  call    cs:__imp_CoTaskMemFree
0x180002256  test    edi, edi
0x180002258  js      loc_18000265D
0x18000225e  lea     rax, [rbp+3Fh+var_70]
0x180002262  mov     r8, rsi
0x180002265  lea     r9, [rbp+3Fh+var_78]
0x180002269  mov     [rsp+0C0h+var_A0], rax
0x18000226e  mov     edx, 1
0x180002273  mov     rcx, r15
0x180002276  call    cs:__imp_SamLookupNamesInDomain2
0x18000227c  mov     ebx, eax
0x18000227e  test    eax, eax
0x180002280  js      loc_180002569
0x180002286  mov     rax, [rbp+3Fh+var_70]
0x18000228a  cmp     dword ptr [rax], 1
0x18000228d  jnz     loc_18000254E
0x180002293  mov     r8, [rbp+3Fh+var_78]
0x180002297  lea     r9, [rbp+3Fh+pv]
0x18000229b  xor     r14d, r14d
0x18000229e  mov     edx, 2031Bh
0x1800022a3  mov     [rbp+3Fh+pv], r14
0x1800022a7  mov     rcx, r15
0x1800022aa  mov     r8d, [r8]
0x1800022ad  call    cs:__imp_SamOpenUser
0x1800022b3  mov     ebx, eax
0x1800022b5  test    eax, eax
0x1800022b7  js      loc_18000251A
0x1800022bd  mov     rcx, [rbp+3Fh+pv]
0x1800022c1  lea     r8, [rbp+3Fh+var_80]
0x1800022c5  mov     edx, 15h
0x1800022ca  mov     [rbp+3Fh+var_80], r14
0x1800022ce  call    cs:__imp_SamQueryInformationUser
0x1800022d4  mov     ebx, eax
0x1800022d6  test    eax, eax
0x1800022d8  js      short loc_1800022F4
0x1800022da  mov     rcx, [rbp+3Fh+var_80]; struct _USER_ALL_INFORMATION *
0x1800022de  mov     rdx, r12; struct _USER_ALL_INFORMATION **
0x1800022e1  call    ?CopyUserStructure@@YAJQEAU_USER_ALL_INFORMATION@@PEAPEAU1@@Z; CopyUserStructure(_USER_ALL_INFORMATION * const,_USER_ALL_INFORMATION * *)
0x1800022e6  mov     rcx, [rbp+3Fh+var_80]
0x1800022ea  mov     ebx, eax
0x1800022ec  call    cs:__imp_SamFreeMemory
0x1800022f2  jmp     short loc_180002326
0x1800022f4  bts     ebx, 1Ch
0x1800022f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022ff  lea     rax, WPP_GLOBAL_Control
0x180002306  cmp     rcx, rax
0x180002309  jz      short loc_180002326
0x18000230b  test    byte ptr [rcx+1Ch], 2
0x18000230f  jz      short loc_180002326
0x180002311  mov     rcx, [rcx+10h]
0x180002315  mov     edx, 33h ; '3'
0x18000231a  mov     r9, rsi
0x18000231d  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180002321  call    WPP_SF_ZD
0x180002326  test    ebx, ebx
0x180002328  js      loc_18000250E
0x18000232e  mov     rcx, [rbp+3Fh+pv]
0x180002332  lea     r8, [rbp+3Fh+var_90]
0x180002336  mov     edx, 1Ch
0x18000233b  mov     [rbp+3Fh+var_90], r14
0x18000233f  call    cs:__imp_SamQueryInformationUser
0x180002345  mov     ebx, eax
0x180002347  test    eax, eax
0x180002349  js      loc_180002499
0x18000234f  mov     rsi, [rbp+3Fh+var_90]
0x180002353  test    rsi, rsi
0x180002356  jz      loc_180002447
0x18000235c  mov     ecx, 0A8h; cb
0x180002361  call    cs:__imp_CoTaskMemAlloc
0x180002367  mov     rdi, rax
0x18000236a  test    rax, rax
0x18000236d  jz      short loc_1800023E3
0x18000236f  mov     rcx, rax; void *
0x180002372  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180002377  mov     r8, rax; Size
0x18000237a  xor     edx, edx; Val
0x18000237c  mov     rcx, rdi; void *
0x18000237f  call    memset_0
0x180002384  mov     eax, [rsi]
0x180002386  lea     rcx, [rsi+18h]; struct _UNICODE_STRING *
0x18000238a  mov     [rdi], eax
0x18000238c  movzx   eax, byte ptr [rsi+28h]
0x180002390  mov     [rdi+28h], al
0x180002393  cmp     [rcx], r14w
0x180002397  jbe     short loc_1800023B4
0x180002399  cmp     [rsi+20h], r14
0x18000239d  jz      short loc_1800023B4
0x18000239f  lea     rdx, [rdi+18h]; struct _UNICODE_STRING *
0x1800023a3  call    ?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z; CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)
0x1800023a8  mov     ebx, eax
0x1800023aa  test    eax, eax
0x1800023ac  js      loc_18000244F
0x1800023b2  jmp     short loc_1800023BF
0x1800023b4  mov     ebx, r14d
0x1800023b7  mov     [rdi+18h], r14d
0x1800023bb  mov     [rdi+20h], r14
0x1800023bf  mov     eax, [rsi+8]
0x1800023c2  mov     [rdi+8], eax
0x1800023c5  mov     eax, [rsi+8]
0x1800023c8  test    eax, eax
0x1800023ca  jz      short loc_1800023FC
0x1800023cc  cmp     [rsi+10h], r14
0x1800023d0  jz      short loc_1800023FC
0x1800023d2  mov     ecx, eax; cb
0x1800023d4  call    cs:__imp_CoTaskMemAlloc
0x1800023da  mov     [rdi+10h], rax
0x1800023de  test    rax, rax
0x1800023e1  jnz     short loc_1800023EA
0x1800023e3  mov     ebx, 8007000Eh
0x1800023e8  jmp     short loc_18000244F
0x1800023ea  mov     r8d, [rsi+8]; Size
0x1800023ee  mov     rcx, rax; void *
0x1800023f1  mov     rdx, [rsi+10h]; Src
0x1800023f5  call    memcpy_0
0x1800023fa  jmp     short loc_180002400
0x1800023fc  mov     [rdi+10h], r14
0x180002400  mov     eax, [rsi+30h]
0x180002403  mov     [rdi+30h], eax
0x180002406  mov     eax, [rsi+30h]
0x180002409  test    eax, eax
0x18000240b  jz      short loc_18000243D
0x18000240d  cmp     [rsi+38h], r14
0x180002411  jz      short loc_18000243D
0x180002413  mov     ecx, eax; cb
0x180002415  call    cs:__imp_CoTaskMemAlloc
0x18000241b  mov     [rdi+38h], rax
0x18000241f  test    rax, rax
0x180002422  jnz     short loc_18000242B
0x180002424  mov     ebx, 8007000Eh
0x180002429  jmp     short loc_18000244F
0x18000242b  mov     r8d, [rsi+30h]; Size
0x18000242f  mov     rcx, rax; void *
0x180002432  mov     rdx, [rsi+38h]; Src
0x180002436  call    memcpy_0
0x18000243b  jmp     short loc_180002441
0x18000243d  mov     [rdi+38h], r14
0x180002441  mov     [r13+0], rdi
0x180002445  jmp     short loc_18000248D
0x180002447  mov     rdi, r14
0x18000244a  mov     ebx, 80004003h
0x18000244f  mov     edx, 1; int
0x180002454  mov     rcx, rdi; pv
0x180002457  call    ?FreeUserExtStructure@@YAJPEAU_USER_EXTENDED_INFORMATION@@H@Z; FreeUserExtStructure(_USER_EXTENDED_INFORMATION *,int)
0x18000245c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002463  lea     rax, WPP_GLOBAL_Control
0x18000246a  cmp     rcx, rax
0x18000246d  jz      short loc_18000248D
0x18000246f  test    byte ptr [rcx+1Ch], 2
0x180002473  jz      short loc_18000248D
0x180002475  mov     rcx, [rcx+10h]
0x180002479  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180002480  mov     edx, 27h ; '''
0x180002485  mov     r9d, ebx
0x180002488  call    WPP_SF_d
0x18000248d  mov     rcx, [rbp+3Fh+var_90]
0x180002491  call    cs:__imp_SamFreeMemory
0x180002497  jmp     short loc_1800024CB
0x180002499  bts     ebx, 1Ch
0x18000249d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024a4  lea     rax, WPP_GLOBAL_Control
0x1800024ab  cmp     rcx, rax
0x1800024ae  jz      short loc_1800024CB
0x1800024b0  test    byte ptr [rcx+1Ch], 2
0x1800024b4  jz      short loc_1800024CB
0x1800024b6  mov     rcx, [rcx+10h]
0x1800024ba  mov     edx, 34h ; '4'
0x1800024bf  mov     r9, rsi
0x1800024c2  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1800024c6  call    WPP_SF_ZD
0x1800024cb  test    ebx, ebx
0x1800024cd  js      short loc_18000250E
0x1800024cf  mov     rcx, [rbp+3Fh+pv]
0x1800024d3  lea     r8, [rbp+3Fh+var_90]
0x1800024d7  mov     edx, 1Dh
0x1800024dc  mov     [rbp+3Fh+var_90], r14
0x1800024e0  call    cs:__imp_SamQueryInformationUser
0x1800024e6  test    eax, eax
0x1800024e8  js      short loc_18000250E
0x1800024ea  mov     rcx, [rbp+3Fh+var_90]
0x1800024ee  mov     rax, [rbp+3Fh+arg_28]
0x1800024f2  movzx   edx, byte ptr [rcx]
0x1800024f5  mov     [rax], edx
0x1800024f7  movzx   eax, byte ptr [rcx+1]
0x1800024fb  neg     al
0x1800024fd  mov     rax, [rbp+3Fh+arg_30]
0x180002501  sbb     edx, edx
0x180002503  add     edx, 2
0x180002506  mov     [rax], edx
0x180002508  call    cs:__imp_SamFreeMemory
0x18000250e  mov     rcx, [rbp+3Fh+pv]
0x180002512  call    cs:__imp_SamCloseHandle
0x180002518  jmp     short loc_180002553
0x18000251a  bts     ebx, 1Ch
0x18000251e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002525  lea     rax, WPP_GLOBAL_Control
0x18000252c  cmp     rcx, rax
0x18000252f  jz      short loc_180002553
0x180002531  test    byte ptr [rcx+1Ch], 2
0x180002535  jz      short loc_180002553
0x180002537  mov     rcx, [rcx+10h]
0x18000253b  mov     edx, 35h ; '5'
  ... truncated ...
```
