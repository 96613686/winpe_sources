# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800629e4`
- end: `0x180062c2b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55@Z`
- size: `583`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008acac`
- `0x18008d1cc`

## callees

- `0x1800629e4`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180062bc2`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180062bc2`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180062baf`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180062baf`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180062c14`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180062c14`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180062b0a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180062ba5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180062be9`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180062b0a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180062ba5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180062be9`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180062b98`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180062b98`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180062bf3`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180062bf3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180062b64`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180062b64`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const OLECHAR **a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  const OLECHAR *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  ULONG v13; // edi
  BOOL v14; // ecx
  int DWORD; // ebx
  struct IEdgeBrowsingEnvironment *EdgeBrowsingEnvironment; // rax
  char v18[4]; // [rsp+40h] [rbp-A9h] BYREF
  unsigned int v19; // [rsp+44h] [rbp-A5h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-A1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-89h] BYREF
  unsigned __int8 *v22; // [rsp+70h] [rbp-79h]
  int v23; // [rsp+78h] [rbp-71h]
  int v24; // [rsp+7Ch] [rbp-6Dh]
  __int64 v25; // [rsp+80h] [rbp-69h]
  __int64 v26; // [rsp+88h] [rbp-61h]
  __int64 v27; // [rsp+90h] [rbp-59h]
  __int64 v28; // [rsp+98h] [rbp-51h]
  const OLECHAR *v29; // [rsp+A0h] [rbp-49h]
  int v30; // [rsp+A8h] [rbp-41h]
  int v31; // [rsp+ACh] [rbp-3Dh]
  __int64 v32; // [rsp+B0h] [rbp-39h]
  __int64 v33; // [rsp+B8h] [rbp-31h]
  __int64 v34; // [rsp+C0h] [rbp-29h]
  __int64 v35; // [rsp+C8h] [rbp-21h]
  __int64 v36; // [rsp+D0h] [rbp-19h]
  __int64 v37; // [rsp+D8h] [rbp-11h]

  v36 = a10;
  v34 = a9;
  v32 = a8;
  v37 = 4;
  v35 = 4;
  v33 = 4;
  v10 = *a7;
  if ( *a7 )
  {
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v10 = &pszFormat;
    v12 = 2;
  }
  v30 = v12;
  v13 = 0;
  v27 = a6;
  v25 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180159008;
  v29 = v10;
  v31 = 0;
  v28 = 8;
  v26 = 8;
  UserData.Size = *(unsigned __int16 *)off_180159008;
  v23 = *(unsigned __int16 *)(a2 + 11);
  v22 = a2 + 11;
  UserData.Reserved = 2;
  v24 = 1;
  v19 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  if ( !*(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL) )
  {
    if ( !(unsigned __int8)IEConfiguration_GetBool(536870937) )
      goto LABEL_21;
    v18[0] = 1;
    if ( dword_18015A4CC != 2 )
    {
      LOBYTE(v14) = dword_18015A4CC == 1;
      goto LABEL_9;
    }
    DWORD = IEConfiguration_GetDWORD(268435501);
    if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
    {
      if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
      {
        v14 = LCIEIsCurrentProcessInPrivate();
        if ( DWORD != 3 )
          dword_18015A4CC = v14;
LABEL_9:
        if ( !v14 )
          return EventWriteEx(RegHandle, &EventDescriptor, 0, v13, 0, 0, 8u, &UserData);
LABEL_21:
        v13 = 2;
        return EventWriteEx(RegHandle, &EventDescriptor, 0, v13, 0, 0, 8u, &UserData);
      }
    }
    else if ( (unsigned __int8)IEConfiguration_GetBool(268435512)
           || (EdgeBrowsingEnvironment = GetEdgeBrowsingEnvironment(),
               (*(int (__fastcall **)(struct IEdgeBrowsingEnvironment *, char *))(*(_QWORD *)EdgeBrowsingEnvironment
                                                                                + 120LL))(
                 EdgeBrowsingEnvironment,
                 v18) < 0) )
    {
      LOBYTE(v14) = LCIEIsCurrentProcessUsingInPrivateComponents();
      goto LABEL_9;
    }
    LOBYTE(v14) = v18[0];
    goto LABEL_9;
  }
  return EventWriteEx(RegHandle, &EventDescriptor, 0, v13, 0, 0, 8u, &UserData);
}

```

## disassembly

```asm
0x1800629e4  push    rbp
0x1800629e6  push    rbx
0x1800629e7  push    rsi
0x1800629e8  push    rdi
0x1800629e9  lea     rbp, [rsp-0Fh]
0x1800629ee  sub     rsp, 0F8h
0x1800629f5  mov     rax, cs:__security_cookie
0x1800629fc  xor     rax, rsp
0x1800629ff  mov     [rbp+27h+var_30], rax
0x180062a03  mov     rax, [rbp+27h+arg_48]
0x180062a07  xor     esi, esi
0x180062a09  mov     [rbp+27h+var_40], rax
0x180062a0d  mov     rax, [rbp+27h+arg_40]
0x180062a11  mov     [rbp+27h+var_50], rax
0x180062a15  mov     rax, [rbp+27h+arg_38]
0x180062a19  mov     [rbp+27h+var_60], rax
0x180062a1d  mov     rax, [rbp+27h+arg_30]
0x180062a21  mov     [rbp+27h+var_38], 4
0x180062a29  mov     [rbp+27h+var_48], 4
0x180062a31  mov     [rbp+27h+var_58], 4
0x180062a39  mov     rcx, [rax]
0x180062a3c  test    rcx, rcx
0x180062a3f  jz      loc_180062B82
0x180062a45  or      rax, 0FFFFFFFFFFFFFFFFh
0x180062a49  inc     rax
0x180062a4c  cmp     [rcx+rax*2], si
0x180062a50  jnz     short loc_180062A49
0x180062a52  lea     eax, ds:2[rax*2]
0x180062a59  mov     [rbp+27h+var_68], eax
0x180062a5c  mov     edi, esi
0x180062a5e  mov     rax, [rbp+27h+arg_28]
0x180062a62  mov     [rbp+27h+var_80], rax
0x180062a66  mov     rax, [rbp+27h+arg_20]
0x180062a6a  mov     [rbp+27h+var_90], rax
0x180062a6e  movzx   eax, byte ptr [rdx]
0x180062a71  shl     eax, 18h
0x180062a74  mov     dword ptr [rsp+110h+EventDescriptor.Id], eax
0x180062a78  movzx   eax, word ptr [rdx+1]
0x180062a7c  mov     dword ptr [rsp+110h+EventDescriptor.Level], eax
0x180062a80  mov     rax, [rdx+3]
0x180062a84  mov     [rsp+110h+EventDescriptor.Keyword], rax
0x180062a89  mov     rax, cs:off_180159008
0x180062a90  mov     [rsp+110h+var_B0.Ptr], rax
0x180062a95  mov     [rbp+27h+var_70], rcx
0x180062a99  lea     rcx, [rdx+0Bh]
0x180062a9d  mov     [rbp+27h+var_64], esi
0x180062aa0  mov     [rbp+27h+var_78], 8
0x180062aa8  mov     [rbp+27h+var_88], 8
0x180062ab0  movzx   eax, word ptr [rax]
0x180062ab3  mov     [rsp+110h+var_B0.Size], eax
0x180062ab7  movzx   eax, word ptr [rcx]
0x180062aba  mov     [rbp+27h+var_98], eax
0x180062abd  lea     rax, _TraceLoggingMetadataEnd
0x180062ac4  mov     [rbp+27h+var_A0], rcx
0x180062ac8  lea     rcx, _TraceLoggingMetadata
0x180062acf  sub     eax, ecx
0x180062ad1  mov     dword ptr [rbp+27h+var_B0.0Ch], 2
0x180062ad8  mov     ecx, cs:_tls_index
0x180062ade  mov     [rbp+27h+var_94], 1
0x180062ae5  mov     [rsp+110h+var_CC], eax
0x180062ae9  mov     eax, [rsp+110h+var_CC]
0x180062aed  mov     rax, gs:58h
0x180062af6  mov     edx, 8
0x180062afb  mov     rax, [rax+rcx*8]
0x180062aff  cmp     [rdx+rax], sil
0x180062b03  jnz     short loc_180062B36
0x180062b05  mov     ecx, 20000019h
0x180062b0a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180062b10  test    al, al
0x180062b12  jz      loc_180062C21
0x180062b18  mov     eax, cs:dword_18015A4CC
0x180062b1e  mov     [rsp+110h+var_D0], 1
0x180062b23  cmp     eax, 2
0x180062b26  jz      short loc_180062B93
0x180062b28  cmp     eax, 1
0x180062b2b  setz    cl
0x180062b2e  test    cl, cl
0x180062b30  jnz     loc_180062C21
0x180062b36  mov     rcx, cs:RegHandle; RegHandle
0x180062b3d  lea     rax, [rsp+110h+var_B0]
0x180062b42  mov     [rsp+110h+UserData], rax; UserData
0x180062b47  lea     rdx, [rsp+110h+EventDescriptor]; EventDescriptor
0x180062b4c  mov     [rsp+110h+UserDataCount], 8; UserDataCount
0x180062b54  mov     r9d, edi; Flags
0x180062b57  mov     [rsp+110h+RelatedActivityId], rsi; RelatedActivityId
0x180062b5c  xor     r8d, r8d; Filter
0x180062b5f  mov     [rsp+110h+ActivityId], rsi; ActivityId
0x180062b64  call    cs:__imp_EventWriteEx
0x180062b6a  mov     rcx, [rbp+27h+var_30]
0x180062b6e  xor     rcx, rsp; StackCookie
0x180062b71  call    __security_check_cookie
0x180062b76  add     rsp, 0F8h
0x180062b7d  pop     rdi
0x180062b7e  pop     rsi
0x180062b7f  pop     rbx
0x180062b80  pop     rbp
0x180062b81  retn
0x180062b82  lea     rcx, pszFormat
0x180062b89  mov     eax, 2
0x180062b8e  jmp     loc_180062A59
0x180062b93  mov     ecx, 1000002Dh
0x180062b98  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180062b9e  mov     ecx, 20000002h
0x180062ba3  mov     ebx, eax
0x180062ba5  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180062bab  test    al, al
0x180062bad  jz      short loc_180062BDF
0x180062baf  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x180062bb5  test    al, al
0x180062bb7  jnz     short loc_180062BC2
0x180062bb9  mov     cl, [rsp+110h+var_D0]
0x180062bbd  jmp     loc_180062B2E
0x180062bc2  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x180062bc8  movzx   ecx, al
0x180062bcb  cmp     ebx, 3
0x180062bce  jz      loc_180062B2E
0x180062bd4  mov     cs:dword_18015A4CC, ecx
0x180062bda  jmp     loc_180062B2E
0x180062bdf  cmp     ebx, 2
0x180062be2  jnz     short loc_180062BAF
0x180062be4  mov     ecx, 10000038h
0x180062be9  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180062bef  test    al, al
0x180062bf1  jnz     short loc_180062C14
0x180062bf3  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x180062bf9  mov     r8, rax
0x180062bfc  lea     rdx, [rsp+110h+var_D0]
0x180062c01  mov     rcx, [rax]
0x180062c04  mov     rax, [rcx+78h]
0x180062c08  mov     rcx, r8
0x180062c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062c10  test    eax, eax
0x180062c12  jns     short loc_180062BB9
0x180062c14  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x180062c1a  mov     cl, al
0x180062c1c  jmp     loc_180062B2E
0x180062c21  mov     edi, 2
0x180062c26  jmp     loc_180062B36
```
