# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)

- ea: `0x18006894c`
- end: `0x180068b54`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `520`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64)`
- caller_count: `23`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800106e4`
- `0x18003564c`
- `0x180073eb4`
- `0x180084904`
- `0x180090e4c`
- `0x18009b0c0`
- `0x18009c5e0`
- `0x18009c860`
- `0x18009c960`
- `0x18009cbe0`
- `0x18009e2c0`
- `0x18009e670`
- `0x18009f980`
- `0x1800e7480`
- `0x1800e76e0`
- `0x1800e7a50`
- `0x1800e89e8`
- `0x1800eb948`
- `0x1800ebc40`
- `0x1800ebe00`
- `0x1800f3244`
- `0x1800f8880`
- `0x1800f8ab0`

## callees

- `0x18006894c`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180068ad4`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180068ad4`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180068abc`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180068abc`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180068b37`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180068b37`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180068a01`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180068aac`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180068b01`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180068a01`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180068aac`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180068b01`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180068a99`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180068a99`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180068b11`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180068b11`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180068a66`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180068a66`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  ULONG v5; // edi
  int v6; // ecx
  int DWORD; // ebx
  struct IEdgeBrowsingEnvironment *EdgeBrowsingEnvironment; // rax
  char v10[4]; // [rsp+40h] [rbp-1h] BYREF
  unsigned int v11; // [rsp+44h] [rbp+3h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp+7h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp+17h] BYREF
  unsigned __int8 *v14; // [rsp+68h] [rbp+27h]
  int v15; // [rsp+70h] [rbp+2Fh]
  int v16; // [rsp+74h] [rbp+33h]
  __int64 v17; // [rsp+78h] [rbp+37h]
  __int64 v18; // [rsp+80h] [rbp+3Fh]

  v17 = a5;
  v5 = 0;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180166008;
  v18 = 8;
  UserData.Size = *(unsigned __int16 *)off_180166008;
  v15 = *(unsigned __int16 *)(a2 + 11);
  v14 = a2 + 11;
  UserData.Reserved = 2;
  v16 = 1;
  v11 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  if ( !*(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL) )
  {
    if ( !(unsigned __int8)IEConfiguration_GetBool(536870937) )
      goto LABEL_16;
    v10[0] = 1;
    if ( dword_1801675C4 != 2 )
    {
      LOBYTE(v6) = dword_1801675C4 == 1;
      goto LABEL_5;
    }
    DWORD = IEConfiguration_GetDWORD(268435501);
    if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
    {
      if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
      {
        v6 = LCIEIsCurrentProcessInPrivate();
        if ( DWORD != 3 )
          dword_1801675C4 = v6;
LABEL_5:
        if ( !(_BYTE)v6 )
          return EventWriteEx(RegHandle, &EventDescriptor, 0, v5, 0, 0, 3u, &UserData);
LABEL_16:
        v5 = 2;
        return EventWriteEx(RegHandle, &EventDescriptor, 0, v5, 0, 0, 3u, &UserData);
      }
    }
    else if ( (unsigned __int8)IEConfiguration_GetBool(268435512)
           || (EdgeBrowsingEnvironment = GetEdgeBrowsingEnvironment(),
               (*(int (__fastcall **)(struct IEdgeBrowsingEnvironment *, char *))(*(_QWORD *)EdgeBrowsingEnvironment
                                                                                + 120LL))(
                 EdgeBrowsingEnvironment,
                 v10) < 0) )
    {
      LOBYTE(v6) = LCIEIsCurrentProcessUsingInPrivateComponents();
      goto LABEL_5;
    }
    LOBYTE(v6) = v10[0];
    goto LABEL_5;
  }
  return EventWriteEx(RegHandle, &EventDescriptor, 0, v5, 0, 0, 3u, &UserData);
}

```

## disassembly

```asm
0x18006894c  mov     [rsp-8+arg_0], rbx
0x180068951  mov     [rsp-8+arg_8], rdi
0x180068956  push    rbp
0x180068957  lea     rbp, [rsp-4Fh]
0x18006895c  sub     rsp, 90h
0x180068963  mov     rax, cs:__security_cookie
0x18006896a  xor     rax, rsp
0x18006896d  mov     [rbp+4Fh+var_8], rax
0x180068971  mov     rax, [rbp+4Fh+arg_20]
0x180068975  lea     rcx, [rdx+0Bh]
0x180068979  mov     [rbp+4Fh+var_18], rax
0x18006897d  xor     edi, edi
0x18006897f  movzx   eax, byte ptr [rdx]
0x180068982  shl     eax, 18h
0x180068985  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], eax
0x180068988  movzx   eax, word ptr [rdx+1]
0x18006898c  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x18006898f  mov     rax, [rdx+3]
0x180068993  mov     [rbp+4Fh+EventDescriptor.Keyword], rax
0x180068997  mov     rax, cs:off_180166008
0x18006899e  mov     [rbp+4Fh+var_38.Ptr], rax
0x1800689a2  mov     [rbp+4Fh+var_10], 8
0x1800689aa  mov     edx, 8
0x1800689af  movzx   eax, word ptr [rax]
0x1800689b2  mov     [rbp+4Fh+var_38.Size], eax
0x1800689b5  movzx   eax, word ptr [rcx]
0x1800689b8  mov     [rbp+4Fh+var_20], eax
0x1800689bb  lea     rax, _TraceLoggingMetadataEnd
0x1800689c2  mov     [rbp+4Fh+var_28], rcx
0x1800689c6  lea     rcx, _TraceLoggingMetadata
0x1800689cd  sub     eax, ecx
0x1800689cf  mov     dword ptr [rbp+4Fh+var_38.0Ch], 2
0x1800689d6  mov     ecx, cs:_tls_index
0x1800689dc  mov     [rbp+4Fh+var_1C], 1
0x1800689e3  mov     [rbp+4Fh+var_4C], eax
0x1800689e6  mov     eax, [rbp+4Fh+var_4C]
0x1800689e9  mov     rax, gs:58h
0x1800689f2  mov     rcx, [rax+rcx*8]
0x1800689f6  cmp     [rdx+rcx], dil
0x1800689fa  jnz     short loc_180068A32
0x1800689fc  mov     ecx, 20000019h
0x180068a01  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180068a08  nop     dword ptr [rax+rax+00h]
0x180068a0d  test    al, al
0x180068a0f  jz      loc_180068B4A
0x180068a15  mov     eax, cs:dword_1801675C4
0x180068a1b  mov     [rbp+4Fh+var_50], 1
0x180068a1f  cmp     eax, 2
0x180068a22  jz      short loc_180068A94
0x180068a24  cmp     eax, 1
0x180068a27  setz    cl
0x180068a2a  test    cl, cl
0x180068a2c  jnz     loc_180068B4A
0x180068a32  mov     rcx, cs:RegHandle; RegHandle
0x180068a39  lea     rax, [rbp+4Fh+var_38]
0x180068a3d  mov     [rsp+90h+UserData], rax; UserData
0x180068a42  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x180068a46  mov     [rsp+90h+UserDataCount], 3; UserDataCount
0x180068a4e  mov     r9d, edi; Flags
0x180068a51  mov     [rsp+90h+RelatedActivityId], 0; RelatedActivityId
0x180068a5a  xor     r8d, r8d; Filter
0x180068a5d  mov     [rsp+90h+ActivityId], 0; ActivityId
0x180068a66  call    cs:__imp_EventWriteEx
0x180068a6d  nop     dword ptr [rax+rax+00h]
0x180068a72  mov     rcx, [rbp+4Fh+var_8]
0x180068a76  xor     rcx, rsp; StackCookie
0x180068a79  call    __security_check_cookie
0x180068a7e  lea     r11, [rsp+90h+var_s0]
0x180068a86  mov     rbx, [r11+10h]
0x180068a8a  mov     rdi, [r11+18h]
0x180068a8e  mov     rsp, r11
0x180068a91  pop     rbp
0x180068a92  retn
0x180068a94  mov     ecx, 1000002Dh
0x180068a99  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180068aa0  nop     dword ptr [rax+rax+00h]
0x180068aa5  mov     ecx, 20000002h
0x180068aaa  mov     ebx, eax
0x180068aac  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180068ab3  nop     dword ptr [rax+rax+00h]
0x180068ab8  test    al, al
0x180068aba  jz      short loc_180068AF7
0x180068abc  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x180068ac3  nop     dword ptr [rax+rax+00h]
0x180068ac8  test    al, al
0x180068aca  jnz     short loc_180068AD4
0x180068acc  mov     cl, [rbp+4Fh+var_50]
0x180068acf  jmp     loc_180068A2A
0x180068ad4  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x180068adb  nop     dword ptr [rax+rax+00h]
0x180068ae0  movzx   ecx, al
0x180068ae3  cmp     ebx, 3
0x180068ae6  jz      loc_180068A2A
0x180068aec  mov     cs:dword_1801675C4, ecx
0x180068af2  jmp     loc_180068A2A
0x180068af7  cmp     ebx, 2
0x180068afa  jnz     short loc_180068ABC
0x180068afc  mov     ecx, 10000038h
0x180068b01  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180068b08  nop     dword ptr [rax+rax+00h]
0x180068b0d  test    al, al
0x180068b0f  jnz     short loc_180068B37
0x180068b11  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x180068b18  nop     dword ptr [rax+rax+00h]
0x180068b1d  mov     r8, rax
0x180068b20  lea     rdx, [rbp+4Fh+var_50]
0x180068b24  mov     rcx, [rax]
0x180068b27  mov     rax, [rcx+78h]
0x180068b2b  mov     rcx, r8
0x180068b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068b33  test    eax, eax
0x180068b35  jns     short loc_180068ACC
0x180068b37  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x180068b3e  nop     dword ptr [rax+rax+00h]
0x180068b43  mov     cl, al
0x180068b45  jmp     loc_180068A2A
0x180068b4a  mov     edi, 2
0x180068b4f  jmp     loc_180068A32
```
