# GetPersonalTaskFolder(ITaskService *,ITaskFolder * *,int)

- ea: `0x180042fd0`
- end: `0x1800435f6`
- name: `?GetPersonalTaskFolder@@YAJPEAUITaskService@@PEAPEAUITaskFolder@@H@Z`
- size: `1574`
- prototype: `__int64 __fastcall(struct ITaskService *, struct ITaskFolder **, int)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000f090`
- `0x18003d054`
- `0x18003d4b0`
- `0x18003e334`

## callees

- `0x180003108`
- `0x1800054c4`
- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18000ef54`
- `0x18000efc4`
- `0x18000ff00`
- `0x180042fd0`
- `0x1800435fc`
- `0x1800a3010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18004355e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18004355e`
- `ADVAPI32!GetUserNameW` at `0x1800431c0`
- `ADVAPI32!GetUserNameW` at `0x1800432e8`
- `ADVAPI32!GetUserNameW` at `0x1800431c0`
- `ADVAPI32!GetUserNameW` at `0x1800432e8`
- `OLEAUT32!__imp_VariantInit` at `0x18004301a`
- `OLEAUT32!__imp_VariantInit` at `0x18004301a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004308d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004315c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004308d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004315c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043322`
- `SspiCli!GetUserNameExW` at `0x18004302e`
- `SspiCli!GetUserNameExW` at `0x18004312a`
- `SspiCli!GetUserNameExW` at `0x18004302e`
- `SspiCli!GetUserNameExW` at `0x18004312a`

## string_xrefs

- `0x180043349`: `\Microsoft\Windows\RemoteApp and Desktop Connections Update`
- `0x1800433b8`: `ITaskService::GetFolder failed`
- `0x180043478`: `GetPersonalTaskFolderSDDL failed`
- `0x180043503`: `ITaskFolder::CreateFolder failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetPersonalTaskFolder(struct ITaskService *a1, struct ITaskFolder **a2, int a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v7; // rdx
  signed int PersonalTaskFolderSDDL; // ebx
  signed int LastError; // eax
  unsigned __int64 v10; // rax
  WCHAR *v11; // rax
  unsigned __int16 *v12; // rsi
  unsigned int v13; // eax
  __int64 v14; // rdx
  signed int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // eax
  __int64 v18; // rdx
  signed int v19; // eax
  unsigned int v20; // esi
  unsigned int v21; // eax
  unsigned __int64 v22; // rax
  WCHAR *v23; // rax
  signed int v24; // eax
  HRESULT (__stdcall *GetFolder)(ITaskService *, BSTR, ITaskFolder **); // rbx
  _QWORD *v26; // rdx
  unsigned int v27; // eax
  int v28; // edx
  const char *v29; // rcx
  __int64 v30; // rbx
  __int64 (__fastcall *v31)(__int64, _QWORD *, struct ITaskFolder **); // rdi
  _QWORD *v32; // rdx
  __int64 v33; // rbx
  __int64 (__fastcall *v34)(__int64, _QWORD *, __int128 *, struct ITaskFolder **); // rdi
  __int128 v35; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  _QWORD *v37; // rdx
  unsigned int v38; // eax
  unsigned int v39; // eax
  __int64 v41; // [rsp+38h] [rbp-39h] BYREF
  _BYTE v42[8]; // [rsp+40h] [rbp-31h] BYREF
  __int64 v43; // [rsp+48h] [rbp-29h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-21h] BYREF
  __int128 v45; // [rsp+68h] [rbp-9h] BYREF
  IRecordInfo *v46; // [rsp+78h] [rbp+7h]
  ULONG nSize; // [rsp+F0h] [rbp+7Fh] BYREF

  v43 = -2;
  v41 = 0;
  nSize = 0;
  VariantInit(&pvarg);
  if ( GetUserNameExW(NameUserPrincipal, 0, &nSize) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 25;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      WPP_060bbe8053683a966e9955f0decff737_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147418113);
LABEL_7:
    PersonalTaskFolderSDDL = -2147418113;
    goto LABEL_95;
  }
  LastError = GetLastError();
  PersonalTaskFolderSDDL = LastError;
  if ( LastError == 234 )
  {
    v10 = 2LL * nSize;
    if ( !is_mul_ok(nSize, 2u) )
      v10 = -1;
    v11 = (WCHAR *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
    v12 = v11;
    if ( !v11 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_17;
      }
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 26;
LABEL_16:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        WPP_060bbe8053683a966e9955f0decff737_Traceguids,
        v13,
        -2147024882);
LABEL_17:
      PersonalTaskFolderSDDL = -2147024882;
      goto LABEL_95;
    }
    if ( !GetUserNameExW(NameUserPrincipal, v11, &nSize) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = GetLastError();
        v16 = v15;
        if ( v15 > 0 )
          v16 = (unsigned __int16)v15 | 0x80070000;
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        v18 = 27;
LABEL_25:
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, WPP_060bbe8053683a966e9955f0decff737_Traceguids, v17, v16);
        goto LABEL_26;
      }
      goto LABEL_26;
    }
    goto LABEL_58;
  }
  if ( LastError == 1332 )
  {
    if ( GetUserNameW(0, &nSize) )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_7;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 28;
      goto LABEL_6;
    }
    PersonalTaskFolderSDDL = GetLastError();
    if ( PersonalTaskFolderSDDL == 122 )
    {
      v22 = 2LL * nSize;
      if ( !is_mul_ok(nSize, 2u) )
        v22 = -1;
      v23 = (WCHAR *)operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
      v12 = v23;
      if ( !v23 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_17;
        }
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 30;
        goto LABEL_16;
      }
      if ( !GetUserNameW(v23, &nSize) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v24 = GetLastError();
          v16 = v24;
          if ( v24 > 0 )
            v16 = (unsigned __int16)v24 | 0x80070000;
          v17 = RdpWppGetCurrentThreadActivityIdPrefix();
          v18 = 31;
          goto LABEL_25;
        }
LABEL_26:
        v19 = GetLastError();
        PersonalTaskFolderSDDL = v19;
        if ( v19 > 0 )
          PersonalTaskFolderSDDL = (unsigned __int16)v19 | 0x80070000;
        goto LABEL_88;
      }
LABEL_58:
      GetFolder = a1->lpVtbl->GetFolder;
      v26 = *(_QWORD **)_bstr_t::_bstr_t(
                          (_bstr_t *)v42,
                          L"\\Microsoft\\Windows\\RemoteApp and Desktop Connections Update");
      if ( v26 )
        v26 = (_QWORD *)*v26;
      PersonalTaskFolderSDDL = ((__int64 (__fastcall *)(struct ITaskService *, _QWORD *, __int64 *))GetFolder)(
                                 a1,
                                 v26,
                                 &v41);
      _bstr_t::_Free((_bstr_t *)v42);
      if ( PersonalTaskFolderSDDL < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v27 = RdpWppGetCurrentThreadActivityIdPrefix();
          v28 = 33;
          v29 = "ITaskService::GetFolder failed";
LABEL_65:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v28,
            (unsigned int)WPP_060bbe8053683a966e9955f0decff737_Traceguids,
            v27,
            (__int64)v29,
            PersonalTaskFolderSDDL);
          goto LABEL_87;
        }
        goto LABEL_87;
      }
      v30 = v41;
      v31 = *(__int64 (__fastcall **)(__int64, _QWORD *, struct ITaskFolder **))(*(_QWORD *)v41 + 72LL);
      v32 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v42, v12);
      if ( v32 )
        v32 = (_QWORD *)*v32;
      PersonalTaskFolderSDDL = v31(v30, v32, a2);
      _bstr_t::_Free((_bstr_t *)v42);
      if ( PersonalTaskFolderSDDL < 0 )
      {
        if ( !a3 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v38 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_060bbe8053683a966e9955f0decff737_Traceguids, v38);
          }
          goto LABEL_87;
        }
        PersonalTaskFolderSDDL = GetPersonalTaskFolderSDDL(&pvarg);
        if ( PersonalTaskFolderSDDL < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v27 = RdpWppGetCurrentThreadActivityIdPrefix();
            v28 = 34;
            v29 = "GetPersonalTaskFolderSDDL failed";
            goto LABEL_65;
          }
LABEL_87:
          if ( !v12 )
            goto LABEL_95;
LABEL_88:
          operator delete[](v12);
          goto LABEL_95;
        }
        v33 = v41;
        v34 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int128 *, struct ITaskFolder **))(*(_QWORD *)v41 + 88LL);
        v35 = *(_OWORD *)&pvarg.vt;
        pRecInfo = pvarg.pRecInfo;
        v37 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v42, v12);
        if ( v37 )
          v37 = (_QWORD *)*v37;
        v45 = v35;
        v46 = pRecInfo;
        PersonalTaskFolderSDDL = v34(v33, v37, &v45, a2);
        _bstr_t::_Free((_bstr_t *)v42);
        if ( PersonalTaskFolderSDDL < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v27 = RdpWppGetCurrentThreadActivityIdPrefix();
            v28 = 35;
            v29 = "ITaskFolder::CreateFolder failed";
            goto LABEL_65;
          }
          goto LABEL_87;
        }
      }
      PersonalTaskFolderSDDL = 0;
      goto LABEL_87;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( PersonalTaskFolderSDDL > 0 )
        v20 = (unsigned __int16)PersonalTaskFolderSDDL | 0x80070000;
      else
        v20 = PersonalTaskFolderSDDL;
      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_060bbe8053683a966e9955f0decff737_Traceguids, v21, v20);
    }
    if ( PersonalTaskFolderSDDL > 0 )
      PersonalTaskFolderSDDL = (unsigned __int16)PersonalTaskFolderSDDL | 0x80070000;
  }
  else
  {
    if ( LastError > 0 )
      PersonalTaskFolderSDDL = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v39 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_060bbe8053683a966e9955f0decff737_Traceguids,
        v39,
        PersonalTaskFolderSDDL);
    }
  }
LABEL_95:
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v41);
  return (unsigned int)PersonalTaskFolderSDDL;
}

```

## disassembly

```asm
0x180042fd0  mov     rax, rsp
0x180042fd3  push    rbp
0x180042fd4  push    rdi
0x180042fd5  push    r12
0x180042fd7  push    r14
0x180042fd9  push    r15
0x180042fdb  lea     rbp, [rax-5Fh]
0x180042fdf  sub     rsp, 0A0h
0x180042fe6  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFEh
0x180042fee  mov     [rax+8], rbx
0x180042ff2  mov     [rax+10h], rsi
0x180042ff6  movaps  xmmword ptr [rax-38h], xmm6
0x180042ffa  movaps  xmmword ptr [rax-48h], xmm7
0x180042ffe  mov     r14d, r8d
0x180043001  mov     r15, rdx
0x180043004  mov     rdi, rcx
0x180043007  mov     [rbp+57h+var_90], 0
0x18004300f  mov     [rbp+57h+nSize], 0
0x180043016  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004301a  call    cs:__imp_VariantInit
0x180043020  nop
0x180043021  lea     r8, [rbp+57h+nSize]; nSize
0x180043025  xor     edx, edx; lpNameBuffer
0x180043027  lea     r12d, [rdx+8]
0x18004302b  mov     ecx, r12d; NameFormat
0x18004302e  call    cs:__imp_GetUserNameExW
0x180043034  test    al, al
0x180043036  jz      short loc_18004308D
0x180043038  lea     rax, WPP_GLOBAL_Control
0x18004303f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043046  cmp     rcx, rax
0x180043049  jz      short loc_180043083
0x18004304b  test    [rcx+1Ch], r12b
0x18004304f  jz      short loc_180043083
0x180043051  cmp     byte ptr [rcx+19h], 2
0x180043055  jb      short loc_180043083
0x180043057  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004305c  lea     edx, [r12+11h]
0x180043061  mov     [rsp+0C0h+var_A0], 8000FFFFh
0x180043069  mov     r9d, eax
0x18004306c  lea     r8, WPP_060bbe8053683a966e9955f0decff737_Traceguids
0x180043073  mov     rcx, cs:WPP_GLOBAL_Control
0x18004307a  mov     rcx, [rcx+10h]
0x18004307e  call    WPP_SF_Dd
0x180043083  mov     ebx, 8000FFFFh
0x180043088  jmp     loc_1800435BB
0x18004308d  call    cs:__imp_GetLastError
0x180043093  mov     ebx, eax
0x180043095  cmp     eax, 0EAh
0x18004309a  jnz     loc_1800431AF
0x1800430a0  mov     ecx, [rbp+57h+nSize]
0x1800430a3  mov     eax, 2
0x1800430a8  mul     rcx
0x1800430ab  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800430b2  cmovb   rax, rcx
0x1800430b6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800430bd  mov     rcx, rax; unsigned __int64
0x1800430c0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800430c5  mov     rsi, rax
0x1800430c8  test    rax, rax
0x1800430cb  jnz     short loc_180043120
0x1800430cd  lea     rax, WPP_GLOBAL_Control
0x1800430d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800430db  cmp     rcx, rax
0x1800430de  jz      short loc_180043116
0x1800430e0  test    [rcx+1Ch], r12b
0x1800430e4  jz      short loc_180043116
0x1800430e6  cmp     byte ptr [rcx+19h], 2
0x1800430ea  jb      short loc_180043116
0x1800430ec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800430f1  lea     edx, [rsi+1Ah]
0x1800430f4  mov     [rsp+0C0h+var_A0], 8007000Eh
0x1800430fc  mov     r9d, eax
0x1800430ff  lea     r8, WPP_060bbe8053683a966e9955f0decff737_Traceguids
0x180043106  mov     rcx, cs:WPP_GLOBAL_Control
0x18004310d  mov     rcx, [rcx+10h]
0x180043111  call    WPP_SF_Dd
0x180043116  mov     ebx, 8007000Eh
0x18004311b  jmp     loc_1800435BB
0x180043120  lea     r8, [rbp+57h+nSize]; nSize
0x180043124  mov     rdx, rax; lpNameBuffer
0x180043127  mov     ecx, r12d; NameFormat
0x18004312a  call    cs:__imp_GetUserNameExW
0x180043130  test    al, al
0x180043132  jnz     loc_180043342
0x180043138  lea     rax, WPP_GLOBAL_Control
0x18004313f  mov     edi, 80070000h
0x180043144  mov     rcx, cs:WPP_GLOBAL_Control
0x18004314b  cmp     rcx, rax
0x18004314e  jz      short loc_180043195
0x180043150  test    [rcx+1Ch], r12b
0x180043154  jz      short loc_180043195
0x180043156  cmp     byte ptr [rcx+19h], 2
0x18004315a  jb      short loc_180043195
0x18004315c  call    cs:__imp_GetLastError
0x180043162  mov     ebx, eax
0x180043164  test    eax, eax
0x180043166  jle     short loc_18004316D
0x180043168  movzx   ebx, ax
0x18004316b  or      ebx, edi
0x18004316d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180043172  mov     edx, 1Bh
0x180043177  mov     [rsp+0C0h+var_A0], ebx
0x18004317b  mov     r9d, eax
0x18004317e  lea     r8, WPP_060bbe8053683a966e9955f0decff737_Traceguids
0x180043185  mov     rcx, cs:WPP_GLOBAL_Control
0x18004318c  mov     rcx, [rcx+10h]
0x180043190  call    WPP_SF_Dd
0x180043195  call    cs:__imp_GetLastError
0x18004319b  mov     ebx, eax
0x18004319d  test    eax, eax
0x18004319f  jle     loc_18004355B
0x1800431a5  movzx   ebx, ax
0x1800431a8  or      ebx, edi
0x1800431aa  jmp     loc_18004355B
0x1800431af  cmp     eax, 534h
0x1800431b4  jnz     loc_180043566
0x1800431ba  lea     rdx, [rbp+57h+nSize]; pcbBuffer
0x1800431be  xor     ecx, ecx; lpBuffer
0x1800431c0  call    cs:__imp_GetUserNameW
0x1800431c6  test    eax, eax
0x1800431c8  jz      short loc_180043204
0x1800431ca  lea     rax, WPP_GLOBAL_Control
0x1800431d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800431d8  cmp     rcx, rax
0x1800431db  jz      loc_180043083
0x1800431e1  test    [rcx+1Ch], r12b
0x1800431e5  jz      loc_180043083
0x1800431eb  cmp     byte ptr [rcx+19h], 2
0x1800431ef  jb      loc_180043083
0x1800431f5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800431fa  mov     edx, 1Ch
0x1800431ff  jmp     loc_180043061
0x180043204  call    cs:__imp_GetLastError
0x18004320a  mov     ebx, eax
0x18004320c  cmp     eax, 7Ah ; 'z'
0x18004320f  jz      short loc_18004327C
0x180043211  lea     rax, WPP_GLOBAL_Control
0x180043218  mov     edi, 80070000h
0x18004321d  mov     rcx, cs:WPP_GLOBAL_Control
0x180043224  cmp     rcx, rax
0x180043227  jz      short loc_18004326A
0x180043229  test    [rcx+1Ch], r12b
0x18004322d  jz      short loc_18004326A
0x18004322f  cmp     byte ptr [rcx+19h], 2
0x180043233  jb      short loc_18004326A
0x180043235  test    ebx, ebx
0x180043237  jg      short loc_18004323D
0x180043239  mov     esi, ebx
0x18004323b  jmp     short loc_180043242
0x18004323d  movzx   esi, bx
0x180043240  or      esi, edi
0x180043242  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180043247  mov     edx, 1Dh
0x18004324c  mov     [rsp+0C0h+var_A0], esi
0x180043250  mov     r9d, eax
0x180043253  lea     r8, WPP_060bbe8053683a966e9955f0decff737_Traceguids
0x18004325a  mov     rcx, cs:WPP_GLOBAL_Control
0x180043261  mov     rcx, [rcx+10h]
0x180043265  call    WPP_SF_Dd
0x18004326a  test    ebx, ebx
0x18004326c  jle     loc_1800435BB
0x180043272  movzx   ebx, bx
0x180043275  or      ebx, edi
0x180043277  jmp     loc_1800435BB
0x18004327c  mov     ecx, [rbp+57h+nSize]
0x18004327f  mov     eax, 2
0x180043284  mul     rcx
0x180043287  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004328e  cmovb   rax, rcx
0x180043292  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180043299  mov     rcx, rax; unsigned __int64
0x18004329c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800432a1  mov     rsi, rax
0x1800432a4  test    rax, rax
0x1800432a7  jnz     short loc_1800432E1
0x1800432a9  lea     rax, WPP_GLOBAL_Control
0x1800432b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800432b7  cmp     rcx, rax
0x1800432ba  jz      loc_180043116
0x1800432c0  test    [rcx+1Ch], r12b
0x1800432c4  jz      loc_180043116
0x1800432ca  cmp     byte ptr [rcx+19h], 2
0x1800432ce  jb      loc_180043116
0x1800432d4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800432d9  lea     edx, [rsi+1Eh]
0x1800432dc  jmp     loc_1800430F4
0x1800432e1  lea     rdx, [rbp+57h+nSize]; pcbBuffer
0x1800432e5  mov     rcx, rax; lpBuffer
0x1800432e8  call    cs:__imp_GetUserNameW
0x1800432ee  test    eax, eax
0x1800432f0  jnz     short loc_180043342
0x1800432f2  lea     rax, WPP_GLOBAL_Control
0x1800432f9  mov     edi, 80070000h
0x1800432fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180043305  cmp     rcx, rax
0x180043308  jz      loc_180043195
0x18004330e  test    [rcx+1Ch], r12b
0x180043312  jz      loc_180043195
0x180043318  cmp     byte ptr [rcx+19h], 2
0x18004331c  jb      loc_180043195
0x180043322  call    cs:__imp_GetLastError
0x180043328  mov     ebx, eax
0x18004332a  test    eax, eax
0x18004332c  jle     short loc_180043333
0x18004332e  movzx   ebx, ax
0x180043331  or      ebx, edi
0x180043333  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180043338  mov     edx, 1Fh
0x18004333d  jmp     loc_180043177
0x180043342  mov     rax, [rdi]
0x180043345  mov     rbx, [rax+38h]
0x180043349  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\RemoteApp and Des"...
0x180043350  lea     rcx, [rbp+57h+var_88]; this
0x180043354  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180043359  nop
0x18004335a  mov     rdx, [rax]
0x18004335d  test    rdx, rdx
0x180043360  jz      short loc_180043365
0x180043362  mov     rdx, [rdx]
0x180043365  lea     r8, [rbp+57h+var_90]
0x180043369  mov     rcx, rdi
0x18004336c  mov     rax, rbx
0x18004336f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043374  mov     ebx, eax
0x180043376  lea     rcx, [rbp+57h+var_88]; this
0x18004337a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004337f  test    ebx, ebx
0x180043381  jns     short loc_1800433E7
0x180043383  lea     rax, WPP_GLOBAL_Control
0x18004338a  mov     rcx, cs:WPP_GLOBAL_Control
0x180043391  cmp     rcx, rax
0x180043394  jz      loc_180043556
0x18004339a  test    [rcx+1Ch], r12b
0x18004339e  jz      loc_180043556
0x1800433a4  cmp     byte ptr [rcx+19h], 2
0x1800433a8  jb      loc_180043556
0x1800433ae  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800433b3  mov     edx, 21h ; '!'
0x1800433b8  lea     rcx, aItaskserviceGe; "ITaskService::GetFolder failed"
0x1800433bf  mov     [rsp+0C0h+var_98], ebx
0x1800433c3  mov     qword ptr [rsp+0C0h+var_A0], rcx
0x1800433c8  mov     r9d, eax
0x1800433cb  lea     r8, WPP_060bbe8053683a966e9955f0decff737_Traceguids
0x1800433d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800433d9  mov     rcx, [rcx+10h]
0x1800433dd  call    WPP_SF_DsD
0x1800433e2  jmp     loc_180043556
0x1800433e7  mov     rbx, [rbp+57h+var_90]
0x1800433eb  mov     rax, [rbx]
0x1800433ee  mov     rdi, [rax+48h]
0x1800433f2  mov     rdx, rsi; unsigned __int16 *
0x1800433f5  lea     rcx, [rbp+57h+var_88]; this
0x1800433f9  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800433fe  nop
0x1800433ff  mov     rdx, [rax]
0x180043402  test    rdx, rdx
0x180043405  jz      short loc_18004340A
0x180043407  mov     rdx, [rdx]
0x18004340a  mov     r8, r15
0x18004340d  mov     rcx, rbx
0x180043410  mov     rax, rdi
0x180043413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043418  mov     ebx, eax
0x18004341a  lea     rcx, [rbp+57h+var_88]; this
0x18004341e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180043423  test    ebx, ebx
0x180043425  jns     loc_180043554
0x18004342b  test    r14d, r14d
0x18004342e  jz      loc_18004350F
0x180043434  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180043438  call    ?GetPersonalTaskFolderSDDL@@YAJAEAV_variant_t@@@Z; GetPersonalTaskFolderSDDL(_variant_t &)
0x18004343d  mov     ebx, eax
0x18004343f  test    eax, eax
0x180043441  jns     short loc_180043484
0x180043443  lea     rax, WPP_GLOBAL_Control
0x18004344a  mov     rcx, cs:WPP_GLOBAL_Control
0x180043451  cmp     rcx, rax
0x180043454  jz      loc_180043556
0x18004345a  test    [rcx+1Ch], r12b
0x18004345e  jz      loc_180043556
0x180043464  cmp     byte ptr [rcx+19h], 2
0x180043468  jb      loc_180043556
0x18004346e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180043473  mov     edx, 22h ; '"'
0x180043478  lea     rcx, aGetpersonaltas; "GetPersonalTaskFolderSDDL failed"
0x18004347f  jmp     loc_1800433BF
0x180043484  mov     rbx, [rbp+57h+var_90]
0x180043488  mov     rax, [rbx]
0x18004348b  mov     rdi, [rax+58h]
0x18004348f  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x180043493  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x180043498  mov     rdx, rsi; unsigned __int16 *
0x18004349b  lea     rcx, [rbp+57h+var_88]; this
0x18004349f  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800434a4  nop
0x1800434a5  mov     rdx, [rax]
0x1800434a8  test    rdx, rdx
0x1800434ab  jz      short loc_1800434B0
0x1800434ad  mov     rdx, [rdx]
  ... truncated ...
```
