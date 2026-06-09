# BootGetWinREVolGuid(ushort *,ulong)

- ea: `0x1400229e4`
- end: `0x140022ec2`
- name: `?BootGetWinREVolGuid@@YAHPEAGK@Z`
- size: `1246`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400235e0`
- `0x14006168c`

## callees

- `0x140021ca0`
- `0x1400229e4`
- `0x140022ec8`
- `0x140023098`
- `0x1400232ac`
- `0x1400235a8`
- `0x14003b0c0`
- `0x140091560`
- `0x1400921dc`
- `0x1400d257c`
- `0x1400d7ebc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140022d82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140022e5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140022d82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140022e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022b73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022cfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022d19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022b73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022cfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022d19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022b50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022c56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022e42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022e4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022b50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022c56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022e42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022e4b`
- `bcd!BcdOpenObject` at `0x140022aef`
- `bcd!BcdOpenObject` at `0x140022b37`
- `bcd!BcdOpenObject` at `0x140022c43`
- `bcd!BcdOpenObject` at `0x140022ddf`
- `bcd!BcdOpenObject` at `0x140022aef`
- `bcd!BcdOpenObject` at `0x140022b37`
- `bcd!BcdOpenObject` at `0x140022c43`
- `bcd!BcdOpenObject` at `0x140022ddf`
- `bcd!BcdCloseStore` at `0x140022e32`
- `bcd!BcdCloseStore` at `0x140022e32`
- `bcd!BcdOpenStore` at `0x140022a68`
- `bcd!BcdOpenStore` at `0x140022aa8`
- `bcd!BcdOpenStore` at `0x140022a68`
- `bcd!BcdOpenStore` at `0x140022aa8`
- `bcd!BcdCloseObject` at `0x140022c1f`
- `bcd!BcdCloseObject` at `0x140022e1d`
- `bcd!BcdCloseObject` at `0x140022c1f`
- `bcd!BcdCloseObject` at `0x140022e1d`

## string_xrefs

- `0x140022b42`: `::BcdOpenObject( hSysStore, &GUID_CURRENT_BOOT_ENTRY, &hObject )`
- `0x140022ab3`: `::BcdOpenStore(NULL, 0, &hSysStore )`
- `0x140022de5`: `::BcdOpenObject( hSysStore, &pRecoverySequence[dwIndex], &hObject )`
- `0x140022cd4`: `_IsValidWinRePath`
- `0x140022d67`: `_IsValidWinRePath`

## pseudocode

```c
__int64 __fastcall BootGetWinREVolGuid(unsigned __int16 *a1)
{
  void *v2; // r13
  int v3; // eax
  unsigned int v4; // ebx
  DWORD LastError; // esi
  int v6; // eax
  int v7; // eax
  int v8; // eax
  DWORD v9; // eax
  unsigned int v10; // eax
  unsigned int i; // r15d
  char *v12; // r12
  int v13; // eax
  int v14; // r12d
  int ElementData; // eax
  unsigned int v16; // r9d
  DWORD v17; // r13d
  struct _DRIVE_LAYOUT_INFORMATION_EX *v18; // rcx
  DWORD v19; // eax
  int v20; // eax
  void *v22; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v23; // [rsp+38h] [rbp-C8h] BYREF
  void *v24; // [rsp+40h] [rbp-C0h] BYREF
  void *v25; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v26; // [rsp+50h] [rbp-B0h]
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v28; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v29[526]; // [rsp+62h] [rbp-9Eh] BYREF

  TraceFunctionEnter(L"BootGetWinREVolGuid");
  v24 = 0;
  v22 = 0;
  v23 = 0;
  v2 = 0;
  pv = 0;
  v28 = 0;
  memset_0(v29, 0, 0x206u);
  if ( a1 )
  {
    *a1 = 0;
    v3 = BcdOpenStore(0, 0, &v24);
    if ( v3 < 0 )
    {
      v4 = 0;
      LastError = WIN32_FROM_NTSTATUS((unsigned int)v3);
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v6 = BcdOpenStore(0, 0, &v24);
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          41,
          (unsigned int)WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids,
          v6,
          "::BcdOpenStore(NULL, 0, &hSysStore )");
      }
      goto LABEL_44;
    }
    v7 = BcdOpenObject(v24, &GUID_CURRENT_BOOT_ENTRY, &v22);
    if ( v7 < 0 )
    {
      v4 = 0;
      LastError = WIN32_FROM_NTSTATUS((unsigned int)v7);
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v8 = BcdOpenObject(v24, &GUID_CURRENT_BOOT_ENTRY, &v22);
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          42,
          (unsigned int)WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids,
          v8,
          "::BcdOpenObject( hSysStore, &GUID_CURRENT_BOOT_ENTRY, &hObject )");
      }
      goto LABEL_44;
    }
    CoTaskMemFree(0);
    if ( !(unsigned int)_GetElementData(v22, 0x14000008u, &pv, &v23) )
    {
      if ( GetLastError() == 1168 )
      {
        v4 = 1;
        LastError = 0;
      }
      else
      {
        v4 = 0;
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v9 = GetLastError();
          WPP_SF_Ds(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            43,
            (unsigned int)WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids,
            v9,
            "bRet");
        }
      }
      goto LABEL_44;
    }
    v10 = v23 >> 4;
    LastError = 0;
    v26 = v23 >> 4;
    v4 = 1;
    for ( i = 0; ; ++i )
    {
      if ( i >= v10 )
        goto LABEL_44;
      if ( v22 )
      {
        BcdCloseObject();
        v22 = 0;
      }
      v12 = (char *)pv + 16 * i;
      v13 = BcdOpenObject(v24, v12, &v22);
      if ( v13 < 0 )
      {
        v4 = 0;
        LastError = WIN32_FROM_NTSTATUS((unsigned int)v13);
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v20 = BcdOpenObject(v24, v12, &v22);
          WPP_SF_Ds(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            44,
            (unsigned int)WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids,
            v20,
            "::BcdOpenObject( hSysStore, &pRecoverySequence[dwIndex], &hObject )");
        }
        goto LABEL_44;
      }
      CoTaskMemFree(v2);
      v14 = 0;
      v25 = 0;
      v23 = 0;
      ElementData = _GetElementData(v22, 0x46000010u, &v25, &v23);
      v2 = v25;
      if ( ElementData )
      {
        if ( *(_BYTE *)v25 && (unsigned int)_GetWinREDevPath(v24, v22, &v28, v16) )
          break;
      }
LABEL_40:
      v10 = v26;
    }
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x100000000LL) != 0 )
    {
      WPP_SF_S(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        10,
        WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids,
        L"_IsValidWinRePath");
    }
    if ( GetVolumeNameFromDeviceName(&v28, a1, 0x104u) )
    {
      v17 = 0;
      v14 = 1;
    }
    else
    {
      v17 = GetLastError();
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control )
      {
LABEL_36:
        SetLastError(v17);
        if ( v14 && *a1 )
        {
          v2 = v25;
          goto LABEL_44;
        }
        v2 = v25;
        *a1 = 0;
        goto LABEL_40;
      }
      if ( (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
      {
LABEL_33:
        if ( v18 != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (v18->Gpt.StartingUsableOffset.QuadPart & 0x100000000LL) != 0 )
        {
          WPP_SF_S(
            *(_QWORD *)v18->Gpt.DiskId.Data4,
            11,
            WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids,
            L"_IsValidWinRePath");
        }
        goto LABEL_36;
      }
      v19 = GetLastError();
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        47,
        (unsigned int)WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids,
        v19,
        "GetLastError()");
    }
    v18 = WPP_GLOBAL_Control;
    goto LABEL_33;
  }
  v4 = 0;
  LastError = 87;
  if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
  {
    goto LABEL_48;
  }
  WPP_SF_Ds(
    *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
    40,
    (unsigned int)WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids,
    87,
    "pwszVolumeGuid");
LABEL_44:
  if ( v22 )
  {
    BcdCloseObject();
    v22 = 0;
  }
  if ( v24 )
  {
    BcdCloseStore();
    v24 = 0;
  }
LABEL_48:
  CoTaskMemFree(pv);
  CoTaskMemFree(v2);
  TraceFunctionExit(L"BootGetWinREVolGuid");
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x1400229e4  push    rbp
0x1400229e6  push    rbx
0x1400229e7  push    rsi
0x1400229e8  push    rdi
0x1400229e9  push    r12
0x1400229eb  push    r13
0x1400229ed  push    r14
0x1400229ef  push    r15
0x1400229f1  lea     rbp, [rsp-188h]
0x1400229f9  sub     rsp, 288h
0x140022a00  mov     rax, cs:__security_cookie
0x140022a07  xor     rax, rsp
0x140022a0a  mov     [rbp+1C0h+var_50], rax
0x140022a11  mov     r14, rcx
0x140022a14  lea     rcx, aBootgetwinrevo; "BootGetWinREVolGuid"
0x140022a1b  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x140022a20  xor     r12d, r12d
0x140022a23  lea     rcx, [rsp+2C0h+var_25E]; void *
0x140022a28  xor     edx, edx; Val
0x140022a2a  mov     [rsp+2C0h+var_280], r12
0x140022a2f  mov     r8d, 206h; Size
0x140022a35  mov     [rsp+2C0h+var_290], r12
0x140022a3a  mov     [rsp+2C0h+var_288], r12d
0x140022a3f  mov     r13d, r12d
0x140022a42  mov     [rsp+2C0h+pv], r12
0x140022a47  mov     [rsp+2C0h+var_260], r12w
0x140022a4d  call    memset_0
0x140022a52  test    r14, r14
0x140022a55  jz      loc_140022E8A
0x140022a5b  lea     r8, [rsp+2C0h+var_280]
0x140022a60  mov     [r14], r12w
0x140022a64  xor     edx, edx
0x140022a66  xor     ecx, ecx
0x140022a68  call    cs:__imp_BcdOpenStore
0x140022a6e  test    eax, eax
0x140022a70  jns     short loc_140022ADE
0x140022a72  mov     ecx, eax
0x140022a74  mov     ebx, r12d
0x140022a77  call    WIN32_FROM_NTSTATUS
0x140022a7c  mov     esi, eax
0x140022a7e  mov     rax, cs:WPP_GLOBAL_Control
0x140022a85  lea     rdi, WPP_GLOBAL_Control
0x140022a8c  cmp     rax, rdi
0x140022a8f  jz      loc_140022E13
0x140022a95  test    byte ptr [rax+1Ch], 8
0x140022a99  jz      loc_140022E13
0x140022a9f  lea     r8, [rsp+2C0h+var_280]
0x140022aa4  xor     edx, edx
0x140022aa6  xor     ecx, ecx
0x140022aa8  call    cs:__imp_BcdOpenStore
0x140022aae  lea     edx, [r12+29h]
0x140022ab3  lea     rcx, aBcdopenstoreNu; "::BcdOpenStore(NULL, 0, &hSysStore )"
0x140022aba  mov     [rsp+2C0h+var_2A0], rcx
0x140022abf  lea     r8, WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids
0x140022ac6  mov     rcx, cs:WPP_GLOBAL_Control
0x140022acd  mov     r9d, eax
0x140022ad0  mov     rcx, [rcx+10h]
0x140022ad4  call    WPP_SF_Ds
0x140022ad9  jmp     loc_140022E13
0x140022ade  mov     rcx, [rsp+2C0h+var_280]
0x140022ae3  lea     r8, [rsp+2C0h+var_290]
0x140022ae8  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x140022aef  call    cs:__imp_BcdOpenObject
0x140022af5  test    eax, eax
0x140022af7  jns     short loc_140022B4E
0x140022af9  mov     ecx, eax
0x140022afb  mov     ebx, r12d
0x140022afe  call    WIN32_FROM_NTSTATUS
0x140022b03  mov     esi, eax
0x140022b05  mov     rax, cs:WPP_GLOBAL_Control
0x140022b0c  lea     rdi, WPP_GLOBAL_Control
0x140022b13  cmp     rax, rdi
0x140022b16  jz      loc_140022E13
0x140022b1c  test    byte ptr [rax+1Ch], 8
0x140022b20  jz      loc_140022E13
0x140022b26  mov     rcx, [rsp+2C0h+var_280]
0x140022b2b  lea     r8, [rsp+2C0h+var_290]
0x140022b30  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x140022b37  call    cs:__imp_BcdOpenObject
0x140022b3d  mov     edx, 2Ah ; '*'
0x140022b42  lea     rcx, aBcdopenobjectH_1; "::BcdOpenObject( hSysStore, &GUID_CURRE"...
0x140022b49  jmp     loc_140022ABA
0x140022b4e  xor     ecx, ecx; pv
0x140022b50  call    cs:__imp_CoTaskMemFree
0x140022b56  mov     rcx, [rsp+2C0h+var_290]; void *
0x140022b5b  lea     r9, [rsp+2C0h+var_288]; unsigned int *
0x140022b60  lea     r8, [rsp+2C0h+pv]; void **
0x140022b65  mov     edx, 14000008h; unsigned int
0x140022b6a  call    ?_GetElementData@@YAHPEAXKPEAPEAXPEAK@Z; _GetElementData(void *,ulong,void * *,ulong *)
0x140022b6f  test    eax, eax
0x140022b71  jnz     short loc_140022BEF
0x140022b73  call    cs:__imp_GetLastError
0x140022b79  cmp     eax, 490h
0x140022b7e  jnz     short loc_140022B8D
0x140022b80  mov     ebx, 1
0x140022b85  mov     esi, r12d
0x140022b88  jmp     loc_140022E13
0x140022b8d  mov     ebx, r12d
0x140022b90  call    cs:__imp_GetLastError
0x140022b96  mov     esi, eax
0x140022b98  mov     rax, cs:WPP_GLOBAL_Control
0x140022b9f  lea     rdi, WPP_GLOBAL_Control
0x140022ba6  cmp     rax, rdi
0x140022ba9  jz      loc_140022E13
0x140022baf  test    byte ptr [rax+1Ch], 8
0x140022bb3  jz      loc_140022E13
0x140022bb9  call    cs:__imp_GetLastError
0x140022bbf  lea     rcx, aBret; "bRet"
0x140022bc6  mov     edx, 2Bh ; '+'
0x140022bcb  mov     [rsp+2C0h+var_2A0], rcx
0x140022bd0  mov     r9d, eax
0x140022bd3  mov     rcx, cs:WPP_GLOBAL_Control
0x140022bda  mov     rcx, [rcx+10h]
0x140022bde  lea     r8, WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids
0x140022be5  call    WPP_SF_Ds
0x140022bea  jmp     loc_140022E13
0x140022bef  mov     eax, [rsp+2C0h+var_288]
0x140022bf3  lea     rdi, WPP_GLOBAL_Control
0x140022bfa  shr     eax, 4
0x140022bfd  mov     esi, r12d
0x140022c00  mov     [rsp+2C0h+var_270], eax
0x140022c04  mov     ebx, 1
0x140022c09  mov     r15d, r12d
0x140022c0c  cmp     r15d, eax
0x140022c0f  jnb     loc_140022E13
0x140022c15  mov     rcx, [rsp+2C0h+var_290]
0x140022c1a  test    rcx, rcx
0x140022c1d  jz      short loc_140022C2A
0x140022c1f  call    cs:__imp_BcdCloseObject
0x140022c25  mov     [rsp+2C0h+var_290], r12
0x140022c2a  mov     rcx, [rsp+2C0h+var_280]
0x140022c2f  lea     r8, [rsp+2C0h+var_290]
0x140022c34  mov     r12d, r15d
0x140022c37  shl     r12, 4
0x140022c3b  add     r12, [rsp+2C0h+pv]
0x140022c40  mov     rdx, r12
0x140022c43  call    cs:__imp_BcdOpenObject
0x140022c49  xor     ecx, ecx
0x140022c4b  test    eax, eax
0x140022c4d  js      loc_140022DB5
0x140022c53  mov     rcx, r13; pv
0x140022c56  call    cs:__imp_CoTaskMemFree
0x140022c5c  mov     rcx, [rsp+2C0h+var_290]; void *
0x140022c61  lea     r9, [rsp+2C0h+var_288]; unsigned int *
0x140022c66  xor     r12d, r12d
0x140022c69  lea     r8, [rsp+2C0h+var_278]; void **
0x140022c6e  mov     edx, 46000010h; unsigned int
0x140022c73  mov     [rsp+2C0h+var_278], r12
0x140022c78  mov     [rsp+2C0h+var_288], r12d
0x140022c7d  call    ?_GetElementData@@YAHPEAXKPEAPEAXPEAK@Z; _GetElementData(void *,ulong,void * *,ulong *)
0x140022c82  mov     r13, [rsp+2C0h+var_278]
0x140022c87  mov     [rsp+2C0h+var_278], r13
0x140022c8c  test    eax, eax
0x140022c8e  jz      loc_140022DA9
0x140022c94  cmp     [r13+0], r12b
0x140022c98  jz      loc_140022DA9
0x140022c9e  mov     rdx, [rsp+2C0h+var_290]; void *
0x140022ca3  lea     r8, [rsp+2C0h+var_260]; unsigned __int16 *
0x140022ca8  mov     rcx, [rsp+2C0h+var_280]; void *
0x140022cad  call    ?_GetWinREDevPath@@YAHPEAX0PEAGK@Z; _GetWinREDevPath(void *,void *,ushort *,ulong)
0x140022cb2  test    eax, eax
0x140022cb4  jz      loc_140022DA9
0x140022cba  mov     rcx, cs:WPP_GLOBAL_Control
0x140022cc1  cmp     rcx, rdi
0x140022cc4  jz      short loc_140022CE7
0x140022cc6  test    [rcx+1Ch], bl
0x140022cc9  jz      short loc_140022CE7
0x140022ccb  mov     rcx, [rcx+10h]
0x140022ccf  lea     edx, [r12+0Ah]
0x140022cd4  lea     r9, aIsvalidwinrepa; "_IsValidWinRePath"
0x140022cdb  lea     r8, WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids
0x140022ce2  call    WPP_SF_S
0x140022ce7  mov     r8d, 104h; unsigned int
0x140022ced  lea     rcx, [rsp+2C0h+var_260]; unsigned __int16 *
0x140022cf2  mov     rdx, r14; unsigned __int16 *
0x140022cf5  call    ?GetVolumeNameFromDeviceName@@YAHPEBGPEAGK@Z; GetVolumeNameFromDeviceName(ushort const *,ushort *,ulong)
0x140022cfa  test    eax, eax
0x140022cfc  jnz     short loc_140022D4C
0x140022cfe  call    cs:__imp_GetLastError
0x140022d04  mov     r13d, eax
0x140022d07  mov     rcx, cs:WPP_GLOBAL_Control
0x140022d0e  cmp     rcx, rdi
0x140022d11  jz      short loc_140022D7F
0x140022d13  test    byte ptr [rcx+1Ch], 8
0x140022d17  jz      short loc_140022D59
0x140022d19  call    cs:__imp_GetLastError
0x140022d1f  lea     rcx, aGetlasterror_1; "GetLastError()"
0x140022d26  mov     edx, 2Fh ; '/'
0x140022d2b  mov     [rsp+2C0h+var_2A0], rcx
0x140022d30  lea     r8, WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids
0x140022d37  mov     rcx, cs:WPP_GLOBAL_Control
0x140022d3e  mov     r9d, eax
0x140022d41  mov     rcx, [rcx+10h]
0x140022d45  call    WPP_SF_Ds
0x140022d4a  jmp     short loc_140022D52
0x140022d4c  mov     r13d, r12d
0x140022d4f  mov     r12d, ebx
0x140022d52  mov     rcx, cs:WPP_GLOBAL_Control
0x140022d59  cmp     rcx, rdi
0x140022d5c  jz      short loc_140022D7F
0x140022d5e  test    [rcx+1Ch], bl
0x140022d61  jz      short loc_140022D7F
0x140022d63  mov     rcx, [rcx+10h]
0x140022d67  lea     r9, aIsvalidwinrepa; "_IsValidWinRePath"
0x140022d6e  mov     edx, 0Bh
0x140022d73  lea     r8, WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids
0x140022d7a  call    WPP_SF_S
0x140022d7f  mov     ecx, r13d; dwErrCode
0x140022d82  call    cs:__imp_SetLastError
0x140022d88  test    r12d, r12d
0x140022d8b  jz      short loc_140022D9D
0x140022d8d  xor     r12d, r12d
0x140022d90  cmp     [r14], r12w
0x140022d94  jz      short loc_140022DA0
0x140022d96  mov     r13, [rsp+2C0h+var_278]
0x140022d9b  jmp     short loc_140022E13
0x140022d9d  xor     r12d, r12d
0x140022da0  mov     r13, [rsp+2C0h+var_278]
0x140022da5  mov     [r14], r12w
0x140022da9  mov     eax, [rsp+2C0h+var_270]
0x140022dad  add     r15d, ebx
0x140022db0  jmp     loc_140022C0C
0x140022db5  mov     ebx, ecx
0x140022db7  mov     ecx, eax
0x140022db9  call    WIN32_FROM_NTSTATUS
0x140022dbe  mov     esi, eax
0x140022dc0  mov     rax, cs:WPP_GLOBAL_Control
0x140022dc7  cmp     rax, rdi
0x140022dca  jz      short loc_140022E10
0x140022dcc  test    byte ptr [rax+1Ch], 8
0x140022dd0  jz      short loc_140022E10
0x140022dd2  mov     rcx, [rsp+2C0h+var_280]
0x140022dd7  lea     r8, [rsp+2C0h+var_290]
0x140022ddc  mov     rdx, r12
0x140022ddf  call    cs:__imp_BcdOpenObject
0x140022de5  lea     rcx, aBcdopenobjectH_0; "::BcdOpenObject( hSysStore, &pRecoveryS"...
0x140022dec  mov     edx, 2Ch ; ','
0x140022df1  mov     [rsp+2C0h+var_2A0], rcx
0x140022df6  lea     r8, WPP_124d85f99f08373ac6969d47c4dffa15_Traceguids
0x140022dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140022e04  mov     r9d, eax
0x140022e07  mov     rcx, [rcx+10h]
0x140022e0b  call    WPP_SF_Ds
0x140022e10  xor     r12d, r12d
0x140022e13  mov     rcx, [rsp+2C0h+var_290]
0x140022e18  test    rcx, rcx
0x140022e1b  jz      short loc_140022E28
0x140022e1d  call    cs:__imp_BcdCloseObject
0x140022e23  mov     [rsp+2C0h+var_290], r12
0x140022e28  mov     rcx, [rsp+2C0h+var_280]
0x140022e2d  test    rcx, rcx
0x140022e30  jz      short loc_140022E3D
0x140022e32  call    cs:__imp_BcdCloseStore
0x140022e38  mov     [rsp+2C0h+var_280], r12
0x140022e3d  mov     rcx, [rsp+2C0h+pv]; pv
0x140022e42  call    cs:__imp_CoTaskMemFree
0x140022e48  mov     rcx, r13; pv
0x140022e4b  call    cs:__imp_CoTaskMemFree
0x140022e51  lea     rcx, aBootgetwinrevo; "BootGetWinREVolGuid"
0x140022e58  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x140022e5d  mov     ecx, esi; dwErrCode
0x140022e5f  call    cs:__imp_SetLastError
0x140022e65  mov     eax, ebx
0x140022e67  mov     rcx, [rbp+1C0h+var_50]
0x140022e6e  xor     rcx, rsp; StackCookie
0x140022e71  call    __security_check_cookie
0x140022e76  add     rsp, 288h
0x140022e7d  pop     r15
0x140022e7f  pop     r14
0x140022e81  pop     r13
0x140022e83  pop     r12
0x140022e85  pop     rdi
0x140022e86  pop     rsi
0x140022e87  pop     rbx
0x140022e88  pop     rbp
0x140022e89  retn
0x140022e8a  mov     ebx, r12d
0x140022e8d  mov     esi, 57h ; 'W'
0x140022e92  mov     rcx, cs:WPP_GLOBAL_Control
0x140022e99  lea     rdi, WPP_GLOBAL_Control
0x140022ea0  cmp     rcx, rdi
0x140022ea3  jz      short loc_140022E3D
0x140022ea5  test    byte ptr [rcx+1Ch], 8
0x140022ea9  jz      short loc_140022E3D
0x140022eab  lea     rax, aPwszvolumeguid; "pwszVolumeGuid"
0x140022eb2  mov     r9d, esi
0x140022eb5  mov     [rsp+2C0h+var_2A0], rax
0x140022eba  lea     edx, [rsi-2Fh]
0x140022ebd  jmp     loc_140022BDA
```
