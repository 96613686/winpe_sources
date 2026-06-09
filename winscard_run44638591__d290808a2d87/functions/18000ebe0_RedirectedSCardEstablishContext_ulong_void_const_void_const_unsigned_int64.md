# RedirectedSCardEstablishContext(ulong,void const *,void const *,unsigned __int64 *)

- ea: `0x18000ebe0`
- end: `0x18000f266`
- name: `?RedirectedSCardEstablishContext@@YAJKPEBX0PEA_K@Z`
- size: `1670`
- prototype: `int(unsigned int, const void *, const void *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007f40`

## callees

- `0x180007bc0`
- `0x18000ebe0`
- `0x18000f270`
- `0x18000ff10`
- `0x180011760`
- `0x180016ca4`
- `0x180016d20`
- `0x180017a38`
- `0x180017c48`
- `0x18001991c`
- `0x180019a14`
- `0x1800239b8`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000efb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000efb2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ef91`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ef91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ee99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ee99`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000f187`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000f187`
- `RPCRT4!NdrMesTypeDecode3` at `0x18000f02e`
- `RPCRT4!NdrMesTypeDecode3` at `0x18000f02e`
- `RPCRT4!NdrMesTypeEncode3` at `0x18000edbf`
- `RPCRT4!NdrMesTypeEncode3` at `0x18000edbf`
- `RPCRT4!NdrMesTypeFree3` at `0x18000ed40`
- `RPCRT4!NdrMesTypeFree3` at `0x18000ed40`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18000ed81`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18000ed81`
- `RPCRT4!MesHandleFree` at `0x18000ed53`
- `RPCRT4!MesHandleFree` at `0x18000ed53`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18000efe2`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18000efe2`

## pseudocode

```c
__int64 __fastcall RedirectedSCardEstablishContext(int a1, const void *a2, void *a3, void **a4)
{
  int v8; // r12d
  unsigned int SCardError; // ebx
  DWORD v10; // eax
  int ClientVersion; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v15; // rcx
  _QWORD *v16; // rax
  _QWORD *v17; // rdi
  int v18; // r9d
  handle_t Handle; // [rsp+40h] [rbp-78h] BYREF
  struct _BUFFER_LIST_STRUCT *v20; // [rsp+48h] [rbp-70h] BYREF
  int pObject; // [rsp+50h] [rbp-68h] BYREF
  DWORD Type; // [rsp+54h] [rbp-64h] BYREF
  unsigned int pEncodedSize; // [rsp+58h] [rbp-60h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-58h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-50h] BYREF
  char *pBuffer; // [rsp+70h] [rbp-48h] BYREF
  size_t Size[2]; // [rsp+78h] [rbp-40h] BYREF
  void *Src; // [rsp+88h] [rbp-30h]
  unsigned int Data; // [rsp+D0h] [rbp+18h] BYREF
  void **v30; // [rsp+D8h] [rbp+20h]

  v30 = a4;
  pBuffer = 0;
  pEncodedSize = 0;
  Handle = 0;
  v8 = 0;
  v20 = 0;
  pObject = 0;
  *(_OWORD *)Size = 0;
  Src = 0;
  if ( !a4 )
  {
    SCardError = -2146435068;
LABEL_3:
    Data = SCardError;
    goto LABEL_9;
  }
  *a4 = 0;
  if ( (a1 & 0xFFFFFFFD) != 0 )
  {
    SCardError = -2146435055;
    goto LABEL_3;
  }
  if ( MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &Handle) )
    goto LABEL_65;
  pObject = a1;
  NdrMesTypeEncode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 8u, &pObject);
  while ( 1 )
  {
    while ( 1 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl) )
      {
        phkResult = 0;
        Data = 5000;
        Type = 4;
        cbData = 4;
        if ( !RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SmartCardRedirection",
                0,
                0x20019u,
                &phkResult) )
        {
          if ( RegQueryValueExW(phkResult, L"TimeoutMs", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
            Data = 5000;
          RegCloseKey(phkResult);
        }
        v10 = Data;
        if ( Data < 0x64 )
        {
          v10 = 100;
        }
        else if ( Data > 0xEA60 )
        {
          v10 = 60000;
        }
      }
      else
      {
        v10 = -1;
      }
      ClientVersion = _SendSCardIOCTL(0x90014u, pBuffer, pEncodedSize, &v20, (LPCRITICAL_SECTION)a3, v10, 0x800u);
      if ( ClientVersion != -1073741536 )
        break;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl) )
      {
        SCardError = _MakeSCardError(-1073741536);
        Data = SCardError;
        goto LABEL_9;
      }
      WppTraceIndent(v13, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids);
      }
      if ( v20 )
        *((_DWORD *)v20 + 2) = 0;
    }
    if ( ClientVersion != -1073741667 )
    {
      if ( ClientVersion )
        goto LABEL_22;
      SafeMesHandleFree(&Handle);
      if ( !MesDecodeBufferHandleCreate(*((char **)v20 + 2), *((_DWORD *)v20 + 7), &Handle) )
      {
        *(_OWORD *)Size = 0;
        Src = 0;
        NdrMesTypeDecode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 9u, Size);
        v8 = 1;
        SCardError = Size[0];
        Data = Size[0];
        if ( LODWORD(Size[0]) )
        {
          if ( LODWORD(Size[0]) == -2146435043 )
          {
            WppTraceIndent(v15, 2);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                38,
                (unsigned int)WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids,
                v18,
                *((_DWORD *)a3 + 18));
            }
            ResetEvent(*((HANDLE *)a3 + 16));
            _SetStartedEventToCorrectState((struct _REDIRECTION_CONTEXT *)a3);
          }
          goto LABEL_10;
        }
        if ( LODWORD(Size[1]) <= 0x20 )
        {
          v16 = MIDL_user_allocate(LODWORD(Size[1]) + 32LL);
          v17 = v16;
          if ( !v16 )
          {
            SCardError = -2146435066;
            Data = -2146435066;
            goto LABEL_10;
          }
          *((_DWORD *)v16 + 2) = Size[1];
          v16[2] = v16 + 4;
          memcpy_0(v16 + 4, Src, LODWORD(Size[1]));
          v17[3] = a2;
          *v17 = a3;
          ClientVersion = RedirectionGetClientVersion((struct _REDIRECTION_CONTEXT *)a3);
          if ( !ClientVersion )
          {
            *a4 = v17;
            goto LABEL_10;
          }
LABEL_22:
          SCardError = _MakeSCardError(ClientVersion);
          Data = SCardError;
          goto LABEL_9;
        }
      }
LABEL_65:
      SCardError = -2146435041;
      goto LABEL_3;
    }
    if ( *((_BYTE *)a3 + 43) )
      break;
    WppTraceIndent(v12, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids);
    }
    _SendSCardIOCTL(0x90004u, 0, 0, &v20, (LPCRITICAL_SECTION)a3, 0x1388u, 0x800u);
    if ( v20 )
      *((_DWORD *)v20 + 2) = 0;
    *((_BYTE *)a3 + 43) = 1;
  }
  WppTraceIndent(v12, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids);
  }
  SCardError = _MakeSCardError(-1073741667);
  Data = SCardError;
LABEL_9:
  if ( a4 && *a4 )
  {
    MIDL_user_free(*a4);
    *a4 = 0;
  }
LABEL_10:
  if ( v8 )
    NdrMesTypeFree3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 9u, Size);
  if ( Handle )
  {
    MesHandleFree(Handle);
    Handle = 0;
  }
  MIDL_user_free(pBuffer);
  if ( v20 )
    *((_DWORD *)v20 + 2) = 0;
  return SCardError;
}

```

## disassembly

```asm
0x18000ebe0  mov     r11, rsp
0x18000ebe3  mov     [r11+8], rbx
0x18000ebe7  mov     [r11+10h], rsi
0x18000ebeb  mov     [r11+20h], r9
0x18000ebef  push    rdi
0x18000ebf0  push    r12
0x18000ebf2  push    r13
0x18000ebf4  push    r14
0x18000ebf6  push    r15
0x18000ebf8  sub     rsp, 90h
0x18000ebff  mov     r15, r9
0x18000ec02  mov     r14, r8
0x18000ec05  mov     r13, rdx
0x18000ec08  mov     ebx, ecx
0x18000ec0a  xor     esi, esi
0x18000ec0c  mov     [r11-48h], rsi
0x18000ec10  mov     [rsp+0B8h+pEncodedSize], esi
0x18000ec14  mov     [r11-78h], rsi
0x18000ec18  mov     r12d, esi
0x18000ec1b  mov     [r11-70h], rsi
0x18000ec1f  mov     [rsp+0B8h+var_68], esi
0x18000ec23  xorps   xmm0, xmm0
0x18000ec26  xor     eax, eax
0x18000ec28  movups  xmmword ptr [rsp+0B8h+Size], xmm0
0x18000ec2d  mov     [r11-30h], rax
0x18000ec31  test    r9, r9
0x18000ec34  jnz     loc_18000ED63
0x18000ec3a  mov     ebx, 80100004h
0x18000ec3f  mov     [rsp+0B8h+Data], ebx
0x18000ec46  jmp     short loc_18000ECC5
0x18000ec50  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock> `wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl(void)'::`2'::impl
0x18000ec57  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x18000ec5c  test    al, al
0x18000ec5e  jnz     loc_18000EE58
0x18000ec64  mov     eax, 0FFFFFFFFh
0x18000ec69  mov     [rsp+0B8h+var_88], 800h; unsigned int
0x18000ec71  mov     dword ptr [rsp+0B8h+pObject], eax; dwMilliseconds
0x18000ec75  mov     qword ptr [rsp+0B8h+nTypeIndex], r14; lpCriticalSection
0x18000ec7a  lea     r9, [rsp+0B8h+var_70]; struct _BUFFER_LIST_STRUCT **
0x18000ec7f  mov     r8d, [rsp+0B8h+pEncodedSize]; InputBufferLength
0x18000ec84  mov     rdx, [rsp+0B8h+pBuffer]; InputBuffer
0x18000ec89  mov     ecx, 90014h; IoControlCode
0x18000ec8e  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18000ec93  cmp     eax, 0C0000120h
0x18000ec98  jnz     loc_18000EE30
0x18000ec9e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock> `wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl(void)'::`2'::impl
0x18000eca5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x18000ecaa  test    al, al
0x18000ecac  jnz     loc_18000EECC
0x18000ecb2  mov     ecx, 0C0000120h; int
0x18000ecb7  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18000ecbc  mov     ebx, eax
0x18000ecbe  mov     [rsp+0B8h+Data], eax
0x18000ecc5  test    r15, r15
0x18000ecc8  jnz     loc_18000F245
0x18000ecce  test    r12d, r12d
0x18000ecd1  jnz     short loc_18000ED14
0x18000ecd3  mov     rcx, [rsp+0B8h+Handle]; Handle
0x18000ecd8  test    rcx, rcx
0x18000ecdb  jnz     short loc_18000ED53
0x18000ecdd  mov     rcx, [rsp+0B8h+pBuffer]; void *
0x18000ece2  call    MIDL_user_free
0x18000ece7  mov     rax, [rsp+0B8h+var_70]
0x18000ecec  test    rax, rax
0x18000ecef  jnz     loc_18000F25E
0x18000ecf5  mov     eax, ebx
0x18000ecf7  lea     r11, [rsp+0B8h+var_28]
0x18000ecff  mov     rbx, [r11+30h]
0x18000ed03  mov     rsi, [r11+38h]
0x18000ed07  mov     rsp, r11
0x18000ed0a  pop     r15
0x18000ed0c  pop     r14
0x18000ed0e  pop     r13
0x18000ed10  pop     r12
0x18000ed12  pop     rdi
0x18000ed13  retn
0x18000ed14  lea     rax, [rsp+0B8h+Size]
0x18000ed19  mov     [rsp+0B8h+pObject], rax; pObject
0x18000ed1e  mov     [rsp+0B8h+nTypeIndex], 9; nTypeIndex
0x18000ed26  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18000ed2d  lea     r8, pProxyInfo; pProxyInfo
0x18000ed34  lea     rdx, pPicklingInfo; pPicklingInfo
0x18000ed3b  mov     rcx, [rsp+0B8h+Handle]; Handle
0x18000ed40  call    cs:__imp_NdrMesTypeFree3
0x18000ed46  jmp     short loc_18000ECD3
0x18000ed48  xor     esi, esi
0x18000ed4a  mov     ebx, [rsp+0B8h+Data]
0x18000ed51  jmp     short loc_18000ECD3
0x18000ed53  call    cs:__imp_MesHandleFree
0x18000ed59  mov     [rsp+0B8h+Handle], rsi
0x18000ed5e  jmp     loc_18000ECDD
0x18000ed63  mov     [r9], rsi
0x18000ed66  test    ebx, 0FFFFFFFDh
0x18000ed6c  jnz     loc_18000EF5C
0x18000ed72  lea     r8, [rsp+0B8h+Handle]; pHandle
0x18000ed77  lea     rdx, [rsp+0B8h+pEncodedSize]; pEncodedSize
0x18000ed7c  lea     rcx, [rsp+0B8h+pBuffer]; pBuffer
0x18000ed81  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18000ed87  test    eax, eax
0x18000ed89  jnz     loc_18000F23B
0x18000ed8f  mov     [rsp+0B8h+var_68], ebx
0x18000ed93  lea     rax, [rsp+0B8h+var_68]
0x18000ed98  mov     [rsp+0B8h+pObject], rax; pObject
0x18000ed9d  mov     [rsp+0B8h+nTypeIndex], 8; nTypeIndex
0x18000eda5  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18000edac  lea     r8, pProxyInfo; pProxyInfo
0x18000edb3  lea     rdx, pPicklingInfo; pPicklingInfo
0x18000edba  mov     rcx, [rsp+0B8h+Handle]; Handle
0x18000edbf  call    cs:__imp_NdrMesTypeEncode3
0x18000edc5  jmp     short loc_18000EE24
0x18000edc7  mov     ebx, eax
0x18000edc9  mov     edx, 2
0x18000edce  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000edd3  lea     rax, WPP_GLOBAL_Control
0x18000edda  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ede1  cmp     rcx, rax
0x18000ede4  jz      short loc_18000EE0B
0x18000ede6  test    byte ptr [rcx+1Ch], 8
0x18000edea  jz      short loc_18000EE0B
0x18000edec  cmp     byte ptr [rcx+19h], 2
0x18000edf0  jb      short loc_18000EE0B
0x18000edf2  mov     edx, 21h ; '!'
0x18000edf7  mov     [rsp+0B8h+nTypeIndex], ebx
0x18000edfb  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18000ee02  mov     rcx, [rcx+10h]
0x18000ee06  call    WPP_SF_sd
0x18000ee0b  mov     [rsp+0B8h+Data], ebx
0x18000ee12  xor     esi, esi
0x18000ee14  mov     r15, [rsp+0B8h+arg_18]
0x18000ee1c  mov     r12d, esi
0x18000ee1f  jmp     loc_18000ECC5
0x18000ee24  lea     rdi, WPP_GLOBAL_Control
0x18000ee2b  jmp     loc_18000EC50
0x18000ee30  cmp     eax, 0C000009Dh
0x18000ee35  jz      loc_18000F19A
0x18000ee3b  test    eax, eax
0x18000ee3d  jz      loc_18000EFC7
0x18000ee43  mov     ecx, eax; int
0x18000ee45  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18000ee4a  mov     ebx, eax
0x18000ee4c  mov     [rsp+0B8h+Data], eax
0x18000ee53  jmp     loc_18000ECC5
0x18000ee58  mov     [rsp+0B8h+phkResult], rsi
0x18000ee5d  mov     [rsp+0B8h+Data], 1388h
0x18000ee68  mov     [rsp+0B8h+Type], 4
0x18000ee70  mov     [rsp+0B8h+cbData], 4
0x18000ee78  lea     rax, [rsp+0B8h+phkResult]
0x18000ee7d  mov     qword ptr [rsp+0B8h+nTypeIndex], rax; phkResult
0x18000ee82  mov     r9d, 20019h; samDesired
0x18000ee88  xor     r8d, r8d; ulOptions
0x18000ee8b  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000ee92  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ee99  call    cs:__imp_RegOpenKeyExW
0x18000ee9f  test    eax, eax
0x18000eea1  jz      loc_18000EF66
0x18000eea7  mov     eax, [rsp+0B8h+Data]
0x18000eeae  cmp     eax, 64h ; 'd'
0x18000eeb1  jb      loc_18000EFBD
0x18000eeb7  cmp     eax, 0EA60h
0x18000eebc  jbe     loc_18000EC69
0x18000eec2  mov     eax, 0EA60h
0x18000eec7  jmp     loc_18000EC69
0x18000eecc  mov     edx, 2
0x18000eed1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000eed6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eedd  cmp     rcx, rdi
0x18000eee0  jnz     short loc_18000EEF8
0x18000eee2  mov     rax, [rsp+0B8h+var_70]
0x18000eee7  test    rax, rax
0x18000eeea  jz      loc_18000EC50
0x18000eef0  mov     [rax+8], esi
0x18000eef3  jmp     loc_18000EC50
0x18000eef8  test    byte ptr [rcx+1Ch], 8
0x18000eefc  jz      short loc_18000EEE2
0x18000eefe  cmp     byte ptr [rcx+19h], 4
0x18000ef02  jb      short loc_18000EEE2
0x18000ef04  mov     edx, 24h ; '$'
0x18000ef09  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18000ef10  mov     rcx, [rcx+10h]
0x18000ef14  call    WPP_SF_s
0x18000ef19  jmp     short loc_18000EEE2
0x18000ef1b  mov     [rsp+0B8h+var_88], 800h; unsigned int
0x18000ef23  mov     dword ptr [rsp+0B8h+pObject], 1388h; dwMilliseconds
0x18000ef2b  mov     qword ptr [rsp+0B8h+nTypeIndex], r14; lpCriticalSection
0x18000ef30  lea     r9, [rsp+0B8h+var_70]; struct _BUFFER_LIST_STRUCT **
0x18000ef35  xor     r8d, r8d; InputBufferLength
0x18000ef38  xor     edx, edx; InputBuffer
0x18000ef3a  mov     ecx, 90004h; IoControlCode
0x18000ef3f  call    ?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z; _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)
0x18000ef44  mov     rax, [rsp+0B8h+var_70]
0x18000ef49  test    rax, rax
0x18000ef4c  jnz     loc_18000F1E9
0x18000ef52  mov     byte ptr [r14+2Bh], 1
0x18000ef57  jmp     loc_18000EC50
0x18000ef5c  mov     ebx, 80100011h
0x18000ef61  jmp     loc_18000EC3F
0x18000ef66  lea     rax, [rsp+0B8h+cbData]
0x18000ef6b  mov     [rsp+0B8h+pObject], rax; lpcbData
0x18000ef70  lea     rax, [rsp+0B8h+Data]
0x18000ef78  mov     qword ptr [rsp+0B8h+nTypeIndex], rax; lpData
0x18000ef7d  lea     r9, [rsp+0B8h+Type]; lpType
0x18000ef82  xor     r8d, r8d; lpReserved
0x18000ef85  lea     rdx, aTimeoutms; "TimeoutMs"
0x18000ef8c  mov     rcx, [rsp+0B8h+phkResult]; hKey
0x18000ef91  call    cs:__imp_RegQueryValueExW
0x18000ef97  test    eax, eax
0x18000ef99  jnz     short loc_18000EFA2
0x18000ef9b  cmp     [rsp+0B8h+Type], 4
0x18000efa0  jz      short loc_18000EFAD
0x18000efa2  mov     [rsp+0B8h+Data], 1388h
0x18000efad  mov     rcx, [rsp+0B8h+phkResult]; hKey
0x18000efb2  call    cs:__imp_RegCloseKey
0x18000efb8  jmp     loc_18000EEA7
0x18000efbd  mov     eax, 64h ; 'd'
0x18000efc2  jmp     loc_18000EC69
0x18000efc7  lea     rcx, [rsp+0B8h+Handle]; void **
0x18000efcc  call    ?SafeMesHandleFree@@YAXPEAPEAX@Z; SafeMesHandleFree(void * *)
0x18000efd1  lea     r8, [rsp+0B8h+Handle]; pHandle
0x18000efd6  mov     rcx, [rsp+0B8h+var_70]
0x18000efdb  mov     edx, [rcx+1Ch]; BufferSize
0x18000efde  mov     rcx, [rcx+10h]; Buffer
0x18000efe2  call    cs:__imp_MesDecodeBufferHandleCreate
0x18000efe8  test    eax, eax
0x18000efea  jnz     loc_18000F23B
0x18000eff0  xorps   xmm0, xmm0
0x18000eff3  xor     eax, eax
0x18000eff5  movups  xmmword ptr [rsp+0B8h+Size], xmm0
0x18000effa  mov     [rsp+0B8h+Src], rax
0x18000f002  lea     rax, [rsp+0B8h+Size]
0x18000f007  mov     [rsp+0B8h+pObject], rax; pObject
0x18000f00c  mov     [rsp+0B8h+nTypeIndex], 9; nTypeIndex
0x18000f014  lea     r9, ArrTypeOffset; ArrTypeOffset
0x18000f01b  lea     r8, pProxyInfo; pProxyInfo
0x18000f022  lea     rdx, pPicklingInfo; pPicklingInfo
0x18000f029  mov     rcx, [rsp+0B8h+Handle]; Handle
0x18000f02e  call    cs:__imp_NdrMesTypeDecode3
0x18000f034  jmp     short loc_18000F093
0x18000f036  mov     ebx, eax
0x18000f038  mov     edx, 2
0x18000f03d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f042  lea     rax, WPP_GLOBAL_Control
0x18000f049  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f050  cmp     rcx, rax
0x18000f053  jz      short loc_18000F07A
0x18000f055  test    byte ptr [rcx+1Ch], 8
0x18000f059  jz      short loc_18000F07A
0x18000f05b  cmp     byte ptr [rcx+19h], 2
0x18000f05f  jb      short loc_18000F07A
0x18000f061  mov     edx, 25h ; '%'
0x18000f066  mov     [rsp+0B8h+nTypeIndex], ebx
0x18000f06a  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18000f071  mov     rcx, [rcx+10h]
0x18000f075  call    WPP_SF_sd
0x18000f07a  mov     [rsp+0B8h+Data], ebx
0x18000f081  xor     esi, esi
0x18000f083  mov     r15, [rsp+0B8h+arg_18]
0x18000f08b  mov     r12d, esi
0x18000f08e  jmp     loc_18000ECC5
0x18000f093  mov     r12d, 1
0x18000f099  mov     ebx, dword ptr [rsp+0B8h+Size]
0x18000f09d  mov     [rsp+0B8h+Data], ebx
0x18000f0a4  test    ebx, ebx
0x18000f0a6  jnz     loc_18000F135
0x18000f0ac  mov     eax, dword ptr [rsp+0B8h+Size+8]
0x18000f0b3  cmp     eax, 20h ; ' '
0x18000f0b6  ja      loc_18000F23B
0x18000f0bc  lea     rcx, [rax+20h]; size
0x18000f0c0  call    MIDL_user_allocate
0x18000f0c5  mov     rdi, rax
0x18000f0c8  test    rax, rax
0x18000f0cb  jz      short loc_18000F124
0x18000f0cd  mov     edx, dword ptr [rsp+0B8h+Size+8]
0x18000f0d4  mov     [rax+8], edx
0x18000f0d7  lea     rcx, [rax+20h]; void *
0x18000f0db  mov     [rax+10h], rcx
0x18000f0df  mov     r8d, dword ptr [rsp+0B8h+Size+8]; Size
0x18000f0e7  mov     rdx, [rsp+0B8h+Src]; Src
0x18000f0ef  call    memcpy_0
0x18000f0f4  mov     [rdi+18h], r13
0x18000f0f8  mov     [rdi], r14
0x18000f0fb  mov     rcx, r14; struct _REDIRECTION_CONTEXT *
0x18000f0fe  call    ?RedirectionGetClientVersion@@YAKPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionGetClientVersion(_REDIRECTION_CONTEXT *)
0x18000f103  test    eax, eax
0x18000f105  jz      short loc_18000F11C
0x18000f107  mov     ecx, eax; int
0x18000f109  call    ?_MakeSCardError@@YAJJ@Z; _MakeSCardError(long)
0x18000f10e  mov     ebx, eax
0x18000f110  mov     [rsp+0B8h+Data], eax
0x18000f117  jmp     loc_18000ECC5
0x18000f11c  mov     [r15], rdi
0x18000f11f  jmp     loc_18000ECCE
0x18000f124  mov     ebx, 80100006h
0x18000f129  mov     [rsp+0B8h+Data], ebx
0x18000f130  jmp     loc_18000ECCE
0x18000f135  cmp     ebx, 8010001Dh
0x18000f13b  jnz     loc_18000ECCE
0x18000f141  mov     edx, 2
0x18000f146  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f14b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f152  cmp     rcx, rdi
  ... truncated ...
```
