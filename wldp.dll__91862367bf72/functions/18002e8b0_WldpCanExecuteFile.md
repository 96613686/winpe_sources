# WldpCanExecuteFile

- ea: `0x18002e8b0`
- end: `0x18002ecb3`
- name: `WldpCanExecuteFile`
- size: `1027`
- prototype: `__int64 __fastcall(struct _GUID *Buf1, unsigned int, void *, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callees

- `0x180016f74`
- `0x18001e1d4`
- `0x18001fb3c`
- `0x1800201f4`
- `0x1800213bc`
- `0x180021ec0`
- `0x18002d870`
- `0x18002d8b8`
- `0x18002e248`
- `0x18002e47c`
- `0x18002e4d4`
- `0x18002e8b0`
- `0x18002f728`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e9de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e9de`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002ea57`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002ea57`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002e9d4`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002eb0c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002eb84`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002ec39`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002e9d4`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002eb0c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002eb84`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002ec39`

## string_xrefs

- `0x18002ebcd`: `onecore\base\ngscb\wldp\dll\canexecute.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WldpCanExecuteFile(struct _GUID *Buf1, unsigned int a2, void *a3, __int64 a4, _DWORD *a5)
{
  const char *v7; // r9
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  __int64 result; // rax
  signed int LastError; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  int IsFileTrusted2; // edi
  int v15; // ebx
  char v16; // al
  unsigned int v17; // ebx
  int v18; // [rsp+20h] [rbp-118h]
  unsigned __int8 v19[4]; // [rsp+30h] [rbp-108h] BYREF
  int v20; // [rsp+34h] [rbp-104h] BYREF
  unsigned int v21; // [rsp+38h] [rbp-100h] BYREF
  HANDLE hFile; // [rsp+40h] [rbp-F8h] BYREF
  unsigned int v23; // [rsp+48h] [rbp-F0h] BYREF
  unsigned int v24[2]; // [rsp+50h] [rbp-E8h]
  _DWORD *v25; // [rsp+58h] [rbp-E0h] BYREF
  HANDLE *v26; // [rsp+60h] [rbp-D8h] BYREF
  LARGE_INTEGER *v27; // [rsp+68h] [rbp-D0h]
  char v28; // [rsp+70h] [rbp-C8h]
  union _LARGE_INTEGER NewFilePointer; // [rsp+78h] [rbp-C0h] BYREF
  _BYTE v30[40]; // [rsp+80h] [rbp-B8h] BYREF
  char v31; // [rsp+A8h] [rbp-90h]
  LARGE_INTEGER liDistanceToMove; // [rsp+B0h] [rbp-88h]
  _QWORD v33[2]; // [rsp+C0h] [rbp-78h] BYREF
  _QWORD v34[5]; // [rsp+D0h] [rbp-68h] BYREF
  GUID ActivityId; // [rsp+F8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v23 = a2;
  hFile = a3;
  v25 = a5;
  try
  {
    v21 = 0;
    v20 = 0;
    ActivityId = 0;
    NewFilePointer.QuadPart = 0;
    liDistanceToMove.QuadPart = 0;
    *(_QWORD *)v24 = 0;
    v34[0] = Buf1;
    v34[1] = &hFile;
    v34[2] = &v25;
    v34[3] = &v23;
    v34[4] = &v20;
    wil::ScopeExit__lambda_0190a735e492111a26deea006884e309___(v30, v34);
    if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && (unsigned __int8)IsKnownHost(Buf1) )
    {
      GetSystemStateForHost(Buf1);
      v8 = v24[0];
      if ( (v24[0] & 4) == 0 )
      {
        *v25 = 1;
        v9 = v20;
        if ( v31 )
        {
          v31 = 0;
          lambda_0190a735e492111a26deea006884e309_::operator()(v30);
        }
        return v9;
      }
      if ( !SetFilePointerEx(hFile, liDistanceToMove, &NewFilePointer, 1u) )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        v20 = v12;
        if ( v31 )
        {
          v31 = 0;
          lambda_0190a735e492111a26deea006884e309_::operator()(v30);
        }
        return v12;
      }
      v33[0] = &hFile;
      v33[1] = &NewFilePointer;
      wil::ScopeExit__lambda_f65740bb5c304e219dcd2360e1897c56___(&v26, v33);
      EventActivityIdControl(3u, &ActivityId);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::GetImpl'::`2'::impl)
        || *(_QWORD *)&Buf1->Data1 != WLDP_HOST_MCPB
        || *(_QWORD *)Buf1->Data4 != 0x5FC1B7B9D6833AABLL
        || (v19[0] = 0, IsFileTrusted2 = WldpIsMcpbTrusted(hFile, v19, &v21), v20 = IsFileTrusted2, IsFileTrusted2 >= 0)
        && !v19[0] )
      {
        IsFileTrusted2 = WldpIsFileTrusted2(hFile, Buf1, v8, BYTE1(v24[1]) != 0, &ActivityId, &v21);
        v20 = IsFileTrusted2;
      }
      if ( IsFileTrusted2 < 0 )
      {
        if ( v28 )
        {
          v28 = 0;
          SetFilePointerEx(*v26, *v27, 0, 0);
        }
        if ( v31 )
        {
          v31 = 0;
          lambda_0190a735e492111a26deea006884e309_::operator()(v30);
        }
        return (unsigned int)IsFileTrusted2;
      }
      if ( v21 == 1 )
        goto LABEL_35;
      if ( v21 != 3 )
      {
        v15 = WldpRemapExecutionPolicy(Buf1, v13, v25);
        v20 = v15;
        if ( v15 < 0 )
        {
          if ( v28 )
          {
            v28 = 0;
            SetFilePointerEx(*v26, *v27, 0, 0);
          }
          if ( v31 )
          {
            v31 = 0;
            lambda_0190a735e492111a26deea006884e309_::operator()(v30);
          }
          return (unsigned int)v15;
        }
        goto LABEL_39;
      }
      v16 = 1;
      if ( (v8 & 8) != 0 )
LABEL_35:
        v16 = 0;
      if ( v16 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1FD,
          (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\canexecute.cpp",
          (const char *)0x8000FFFFLL,
          v18);
      *v25 = 1;
LABEL_39:
      WldpLogCanExecute(Buf1, v23, a4, 0, *v25, &ActivityId);
      v17 = v20;
      if ( v28 )
      {
        v28 = 0;
        SetFilePointerEx(*v26, *v27, 0, 0);
      }
      if ( v31 )
      {
        v31 = 0;
        lambda_0190a735e492111a26deea006884e309_::operator()(v30);
      }
      return v17;
    }
    v20 = -2147024809;
    if ( v31 )
    {
      v31 = 0;
      lambda_0190a735e492111a26deea006884e309_::operator()(v30);
    }
    result = 2147942487LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x211,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\canexecute.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18002e8b0  mov     r11, rsp
0x18002e8b3  push    rbx
0x18002e8b4  push    rsi
0x18002e8b5  push    rdi
0x18002e8b6  push    r14
0x18002e8b8  push    r15
0x18002e8ba  sub     rsp, 110h
0x18002e8c1  mov     rax, cs:__security_cookie
0x18002e8c8  xor     rax, rsp
0x18002e8cb  mov     [rsp+138h+var_30], rax
0x18002e8d3  mov     r14, r9
0x18002e8d6  mov     rsi, rcx
0x18002e8d9  mov     [rsp+138h+var_F0], edx
0x18002e8dd  mov     [rsp+138h+hFile], r8
0x18002e8e2  mov     rax, [rsp+138h+arg_20]
0x18002e8ea  mov     [rsp+138h+var_E0], rax
0x18002e8ef  xor     r15d, r15d
0x18002e8f2  mov     [rsp+138h+var_100], r15d
0x18002e8f7  mov     [rsp+138h+var_104], r15d
0x18002e8fc  xorps   xmm0, xmm0
0x18002e8ff  movups  xmmword ptr [r11-40h], xmm0
0x18002e904  mov     qword ptr [rsp+138h+NewFilePointer], r15
0x18002e909  mov     [r11-88h], r15
0x18002e910  mov     qword ptr [rsp+138h+var_E8], r15
0x18002e915  mov     [r11-68h], rcx
0x18002e919  lea     rax, [rsp+138h+hFile]
0x18002e91e  mov     [r11-60h], rax
0x18002e922  lea     rax, [rsp+138h+var_E0]
0x18002e927  mov     [r11-58h], rax
0x18002e92b  lea     rax, [rsp+138h+var_F0]
0x18002e930  mov     [r11-50h], rax
0x18002e934  lea     rax, [rsp+138h+var_104]
0x18002e939  mov     [r11-48h], rax
0x18002e93d  lea     rdx, [r11-68h]
0x18002e941  lea     rcx, [r11-0B8h]
0x18002e948  call    wil__ScopeExit__lambda_0190a735e492111a26deea006884e309___
0x18002e94d  nop
0x18002e94e  mov     rax, [rsp+138h+hFile]
0x18002e953  dec     rax
0x18002e956  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002e95a  ja      loc_18002EC63
0x18002e960  mov     rcx, rsi; Buf1
0x18002e963  call    IsKnownHost
0x18002e968  test    al, al
0x18002e96a  jz      loc_18002EC63
0x18002e970  lea     rdx, [rsp+138h+var_E8]
0x18002e975  mov     rcx, rsi; Buf1
0x18002e978  call    GetSystemStateForHost
0x18002e97d  mov     rbx, qword ptr [rsp+138h+var_E8]
0x18002e982  test    bl, 4
0x18002e985  jnz     short loc_18002E9BC
0x18002e987  mov     rax, [rsp+138h+var_E0]
0x18002e98c  mov     dword ptr [rax], 1
0x18002e992  mov     ebx, [rsp+138h+var_104]
0x18002e996  cmp     [rsp+138h+var_90], r15b
0x18002e99e  jz      short loc_18002E9B5
0x18002e9a0  mov     [rsp+138h+var_90], r15b
0x18002e9a8  lea     rcx, [rsp+138h+var_B8]
0x18002e9b0  call    _lambda_0190a735e492111a26deea006884e309___operator__
0x18002e9b5  mov     eax, ebx
0x18002e9b7  jmp     loc_18002EC93
0x18002e9bc  mov     r9d, 1; dwMoveMethod
0x18002e9c2  lea     r8, [rsp+138h+NewFilePointer]; lpNewFilePointer
0x18002e9c7  mov     rdx, qword ptr [rsp+138h+liDistanceToMove]; liDistanceToMove
0x18002e9cf  mov     rcx, [rsp+138h+hFile]; hFile
0x18002e9d4  call    cs:__imp_SetFilePointerEx
0x18002e9da  test    eax, eax
0x18002e9dc  jnz     short loc_18002EA1D
0x18002e9de  call    cs:__imp_GetLastError
0x18002e9e4  mov     ebx, eax
0x18002e9e6  test    eax, eax
0x18002e9e8  jle     short loc_18002E9F3
0x18002e9ea  movzx   ebx, ax
0x18002e9ed  or      ebx, 80070000h
0x18002e9f3  mov     [rsp+138h+var_104], ebx
0x18002e9f7  cmp     [rsp+138h+var_90], r15b
0x18002e9ff  jz      short loc_18002EA16
0x18002ea01  mov     [rsp+138h+var_90], r15b
0x18002ea09  lea     rcx, [rsp+138h+var_B8]
0x18002ea11  call    _lambda_0190a735e492111a26deea006884e309___operator__
0x18002ea16  mov     eax, ebx
0x18002ea18  jmp     loc_18002EC93
0x18002ea1d  lea     rax, [rsp+138h+hFile]
0x18002ea22  mov     [rsp+138h+var_78], rax
0x18002ea2a  lea     rax, [rsp+138h+NewFilePointer]
0x18002ea2f  mov     [rsp+138h+var_70], rax
0x18002ea37  lea     rdx, [rsp+138h+var_78]
0x18002ea3f  lea     rcx, [rsp+138h+var_D8]
0x18002ea44  call    wil__ScopeExit__lambda_f65740bb5c304e219dcd2360e1897c56___
0x18002ea49  nop
0x18002ea4a  lea     rdx, [rsp+138h+ActivityId]; ActivityId
0x18002ea52  mov     ecx, 3; ControlCode
0x18002ea57  call    cs:__imp_EventActivityIdControl
0x18002ea5d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime> `wil::Feature<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::GetImpl(void)'::`2'::impl
0x18002ea64  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::__private_IsEnabled(void)
0x18002ea69  test    al, al
0x18002ea6b  jz      short loc_18002EAB0
0x18002ea6d  mov     rax, [rsi]
0x18002ea70  cmp     rax, cs:WLDP_HOST_MCPB
0x18002ea77  jnz     short loc_18002EAB0
0x18002ea79  mov     rax, [rsi+8]
0x18002ea7d  cmp     rax, cs:qword_180048CC0
0x18002ea84  jnz     short loc_18002EAB0
0x18002ea86  mov     [rsp+138h+var_108], r15b
0x18002ea8b  lea     r8, [rsp+138h+var_100]; unsigned int *
0x18002ea90  lea     rdx, [rsp+138h+var_108]; unsigned __int8 *
0x18002ea95  mov     rcx, [rsp+138h+hFile]; hFile
0x18002ea9a  call    ?WldpIsMcpbTrusted@@YAJPEAXPEAEPEAK@Z; WldpIsMcpbTrusted(void *,uchar *,ulong *)
0x18002ea9f  mov     edi, eax
0x18002eaa1  mov     [rsp+138h+var_104], eax
0x18002eaa5  test    eax, eax
0x18002eaa7  js      short loc_18002EAE6
0x18002eaa9  cmp     [rsp+138h+var_108], r15b
0x18002eaae  jnz     short loc_18002EAE6
0x18002eab0  lea     rax, [rsp+138h+var_100]
0x18002eab5  mov     [rsp+138h+var_110], rax; unsigned int *
0x18002eaba  lea     rax, [rsp+138h+ActivityId]
0x18002eac2  cmp     byte ptr [rsp+138h+var_E8+5], r15b
0x18002eac7  mov     [rsp+138h+var_118], rax; int
0x18002eacc  setnz   r9b; bool
0x18002ead0  mov     r8d, ebx; unsigned int
0x18002ead3  mov     rdx, rsi; struct _GUID *
0x18002ead6  mov     rcx, [rsp+138h+hFile]; void *
0x18002eadb  call    ?WldpIsFileTrusted2@@YAJPEAXAEBU_GUID@@K_N1PEAK@Z; WldpIsFileTrusted2(void *,_GUID const &,ulong,bool,_GUID const &,ulong *)
0x18002eae0  mov     edi, eax
0x18002eae2  mov     [rsp+138h+var_104], eax
0x18002eae6  test    edi, edi
0x18002eae8  jns     short loc_18002EB39
0x18002eaea  cmp     [rsp+138h+var_C8], r15b
0x18002eaef  jz      short loc_18002EB13
0x18002eaf1  mov     [rsp+138h+var_C8], r15b
0x18002eaf6  xor     r9d, r9d; dwMoveMethod
0x18002eaf9  xor     r8d, r8d; lpNewFilePointer
0x18002eafc  mov     rdx, [rsp+138h+var_D0]
0x18002eb01  mov     rdx, [rdx]; liDistanceToMove
0x18002eb04  mov     rcx, [rsp+138h+var_D8]
0x18002eb09  mov     rcx, [rcx]; hFile
0x18002eb0c  call    cs:__imp_SetFilePointerEx
0x18002eb12  nop
0x18002eb13  cmp     [rsp+138h+var_90], r15b
0x18002eb1b  jz      short loc_18002EB32
0x18002eb1d  mov     [rsp+138h+var_90], r15b
0x18002eb25  lea     rcx, [rsp+138h+var_B8]
0x18002eb2d  call    _lambda_0190a735e492111a26deea006884e309___operator__
0x18002eb32  mov     eax, edi
0x18002eb34  jmp     loc_18002EC93
0x18002eb39  cmp     [rsp+138h+var_100], 1
0x18002eb3e  jz      short loc_18002EBB8
0x18002eb40  cmp     [rsp+138h+var_100], 3
0x18002eb45  jz      short loc_18002EBB1
0x18002eb47  mov     r8, [rsp+138h+var_E0]
0x18002eb4c  mov     rcx, rsi
0x18002eb4f  call    WldpRemapExecutionPolicy
0x18002eb54  mov     ebx, eax
0x18002eb56  mov     [rsp+138h+var_104], eax
0x18002eb5a  test    eax, eax
0x18002eb5c  jns     loc_18002EBE9
0x18002eb62  cmp     [rsp+138h+var_C8], r15b
0x18002eb67  jz      short loc_18002EB8B
0x18002eb69  mov     [rsp+138h+var_C8], r15b
0x18002eb6e  xor     r9d, r9d; dwMoveMethod
0x18002eb71  xor     r8d, r8d; lpNewFilePointer
0x18002eb74  mov     rdx, [rsp+138h+var_D0]
0x18002eb79  mov     rdx, [rdx]; liDistanceToMove
0x18002eb7c  mov     rcx, [rsp+138h+var_D8]
0x18002eb81  mov     rcx, [rcx]; hFile
0x18002eb84  call    cs:__imp_SetFilePointerEx
0x18002eb8a  nop
0x18002eb8b  cmp     [rsp+138h+var_90], r15b
0x18002eb93  jz      short loc_18002EBAA
0x18002eb95  mov     [rsp+138h+var_90], r15b
0x18002eb9d  lea     rcx, [rsp+138h+var_B8]
0x18002eba5  call    _lambda_0190a735e492111a26deea006884e309___operator__
0x18002ebaa  mov     eax, ebx
0x18002ebac  jmp     loc_18002EC93
0x18002ebb1  test    bl, 8
0x18002ebb4  mov     al, 1
0x18002ebb6  jz      short loc_18002EBBB
0x18002ebb8  mov     al, r15b
0x18002ebbb  mov     rcx, [rsp+138h]; this
0x18002ebc3  test    al, al
0x18002ebc5  jz      short loc_18002EBDE
0x18002ebc7  mov     r9d, 8000FFFFh; char *
0x18002ebcd  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\wldp\\dll\\canexe"...
0x18002ebd4  mov     edx, 1FDh; void *
0x18002ebd9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ebde  mov     rax, [rsp+138h+var_E0]
0x18002ebe3  mov     dword ptr [rax], 1
0x18002ebe9  lea     rax, [rsp+138h+ActivityId]
0x18002ebf1  mov     [rsp+138h+var_110], rax
0x18002ebf6  mov     rax, [rsp+138h+var_E0]
0x18002ebfb  mov     edx, [rax]
0x18002ebfd  mov     dword ptr [rsp+138h+var_118], edx
0x18002ec01  xor     r9d, r9d
0x18002ec04  mov     r8, r14
0x18002ec07  mov     edx, [rsp+138h+var_F0]
0x18002ec0b  mov     rcx, rsi
0x18002ec0e  call    ?WldpLogCanExecute@@YAXAEBU_GUID@@W4WLDP_EXECUTION_EVALUATION_OPTIONS@@PEBGW4_WLDP_SUBJECT_TYPE@@W4WLDP_EXECUTION_POLICY@@0@Z; WldpLogCanExecute(_GUID const &,WLDP_EXECUTION_EVALUATION_OPTIONS,ushort const *,_WLDP_SUBJECT_TYPE,WLDP_EXECUTION_POLICY,_GUID const &)
0x18002ec13  mov     ebx, [rsp+138h+var_104]
0x18002ec17  cmp     [rsp+138h+var_C8], r15b
0x18002ec1c  jz      short loc_18002EC40
0x18002ec1e  mov     [rsp+138h+var_C8], r15b
0x18002ec23  xor     r9d, r9d; dwMoveMethod
0x18002ec26  xor     r8d, r8d; lpNewFilePointer
0x18002ec29  mov     rdx, [rsp+138h+var_D0]
0x18002ec2e  mov     rdx, [rdx]; liDistanceToMove
0x18002ec31  mov     rcx, [rsp+138h+var_D8]
0x18002ec36  mov     rcx, [rcx]; hFile
0x18002ec39  call    cs:__imp_SetFilePointerEx
0x18002ec3f  nop
0x18002ec40  cmp     [rsp+138h+var_90], r15b
0x18002ec48  jz      short loc_18002EC5F
0x18002ec4a  mov     [rsp+138h+var_90], r15b
0x18002ec52  lea     rcx, [rsp+138h+var_B8]
0x18002ec5a  call    _lambda_0190a735e492111a26deea006884e309___operator__
0x18002ec5f  mov     eax, ebx
0x18002ec61  jmp     short loc_18002EC93
0x18002ec63  mov     ebx, 80070057h
0x18002ec68  mov     [rsp+138h+var_104], ebx
0x18002ec6c  cmp     [rsp+138h+var_90], r15b
0x18002ec74  jz      short loc_18002EC8B
0x18002ec76  mov     [rsp+138h+var_90], r15b
0x18002ec7e  lea     rcx, [rsp+138h+var_B8]
0x18002ec86  call    _lambda_0190a735e492111a26deea006884e309___operator__
0x18002ec8b  mov     eax, ebx
0x18002ec8d  jmp     short loc_18002EC93
0x18002ec8f  mov     eax, [rsp+138h+var_100]
0x18002ec93  mov     rcx, [rsp+138h+var_30]
0x18002ec9b  xor     rcx, rsp; StackCookie
0x18002ec9e  call    __security_check_cookie
0x18002eca3  add     rsp, 110h
0x18002ecaa  pop     r15
0x18002ecac  pop     r14
0x18002ecae  pop     rdi
0x18002ecaf  pop     rsi
0x18002ecb0  pop     rbx
0x18002ecb1  retn
```
