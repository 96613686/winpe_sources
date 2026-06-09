# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)

- ea: `0x180063d8c`
- end: `0x180063f5d`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `465`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64)`
- caller_count: `23`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f214`
- `0x180040134`
- `0x18006e2a4`
- `0x18007f4fc`
- `0x18008acac`
- `0x180094a50`
- `0x180095e80`
- `0x1800960cc`
- `0x1800961d0`
- `0x180096450`
- `0x180097a60`
- `0x180097e00`
- `0x1800990c0`
- `0x1800ddf10`
- `0x1800de170`
- `0x1800de4e0`
- `0x1800df438`
- `0x1800e1f54`
- `0x1800e2240`
- `0x1800e2400`
- `0x1800e9394`
- `0x1800ee740`
- `0x1800ee960`

## callees

- `0x180063d8c`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180063ef5`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180063ef5`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180063ee3`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180063ee3`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180063f46`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180063f46`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180063e41`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180063ed9`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180063f1c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180063e41`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180063ed9`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180063f1c`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180063ecc`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180063ecc`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180063f26`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180063f26`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180063ea0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180063ea0`

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
  BOOL v6; // ecx
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
  UserData.Ptr = (ULONGLONG)off_180159008;
  v18 = 8;
  UserData.Size = *(unsigned __int16 *)off_180159008;
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
    if ( dword_18015A4CC != 2 )
    {
      LOBYTE(v6) = dword_18015A4CC == 1;
      goto LABEL_5;
    }
    DWORD = IEConfiguration_GetDWORD(268435501);
    if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
    {
      if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
      {
        v6 = LCIEIsCurrentProcessInPrivate();
        if ( DWORD != 3 )
          dword_18015A4CC = v6;
LABEL_5:
        if ( !v6 )
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
0x180063d8c  mov     [rsp-8+arg_0], rbx
0x180063d91  mov     [rsp-8+arg_8], rdi
0x180063d96  push    rbp
0x180063d97  lea     rbp, [rsp-4Fh]
0x180063d9c  sub     rsp, 90h
0x180063da3  mov     rax, cs:__security_cookie
0x180063daa  xor     rax, rsp
0x180063dad  mov     [rbp+4Fh+var_8], rax
0x180063db1  mov     rax, [rbp+4Fh+arg_20]
0x180063db5  lea     rcx, [rdx+0Bh]
0x180063db9  mov     [rbp+4Fh+var_18], rax
0x180063dbd  xor     edi, edi
0x180063dbf  movzx   eax, byte ptr [rdx]
0x180063dc2  shl     eax, 18h
0x180063dc5  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], eax
0x180063dc8  movzx   eax, word ptr [rdx+1]
0x180063dcc  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x180063dcf  mov     rax, [rdx+3]
0x180063dd3  mov     [rbp+4Fh+EventDescriptor.Keyword], rax
0x180063dd7  mov     rax, cs:off_180159008
0x180063dde  mov     [rbp+4Fh+var_38.Ptr], rax
0x180063de2  mov     [rbp+4Fh+var_10], 8
0x180063dea  mov     edx, 8
0x180063def  movzx   eax, word ptr [rax]
0x180063df2  mov     [rbp+4Fh+var_38.Size], eax
0x180063df5  movzx   eax, word ptr [rcx]
0x180063df8  mov     [rbp+4Fh+var_20], eax
0x180063dfb  lea     rax, _TraceLoggingMetadataEnd
0x180063e02  mov     [rbp+4Fh+var_28], rcx
0x180063e06  lea     rcx, _TraceLoggingMetadata
0x180063e0d  sub     eax, ecx
0x180063e0f  mov     dword ptr [rbp+4Fh+var_38.0Ch], 2
0x180063e16  mov     ecx, cs:_tls_index
0x180063e1c  mov     [rbp+4Fh+var_1C], 1
0x180063e23  mov     [rbp+4Fh+var_4C], eax
0x180063e26  mov     eax, [rbp+4Fh+var_4C]
0x180063e29  mov     rax, gs:58h
0x180063e32  mov     rcx, [rax+rcx*8]
0x180063e36  cmp     [rdx+rcx], dil
0x180063e3a  jnz     short loc_180063E6C
0x180063e3c  mov     ecx, 20000019h
0x180063e41  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180063e47  test    al, al
0x180063e49  jz      loc_180063F53
0x180063e4f  mov     eax, cs:dword_18015A4CC
0x180063e55  mov     [rbp+4Fh+var_50], 1
0x180063e59  cmp     eax, 2
0x180063e5c  jz      short loc_180063EC7
0x180063e5e  cmp     eax, 1
0x180063e61  setz    cl
0x180063e64  test    cl, cl
0x180063e66  jnz     loc_180063F53
0x180063e6c  mov     rcx, cs:RegHandle; RegHandle
0x180063e73  lea     rax, [rbp+4Fh+var_38]
0x180063e77  mov     [rsp+90h+UserData], rax; UserData
0x180063e7c  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x180063e80  mov     [rsp+90h+UserDataCount], 3; UserDataCount
0x180063e88  mov     r9d, edi; Flags
0x180063e8b  mov     [rsp+90h+RelatedActivityId], 0; RelatedActivityId
0x180063e94  xor     r8d, r8d; Filter
0x180063e97  mov     [rsp+90h+ActivityId], 0; ActivityId
0x180063ea0  call    cs:__imp_EventWriteEx
0x180063ea6  mov     rcx, [rbp+4Fh+var_8]
0x180063eaa  xor     rcx, rsp; StackCookie
0x180063ead  call    __security_check_cookie
0x180063eb2  lea     r11, [rsp+90h+var_s0]
0x180063eba  mov     rbx, [r11+10h]
0x180063ebe  mov     rdi, [r11+18h]
0x180063ec2  mov     rsp, r11
0x180063ec5  pop     rbp
0x180063ec6  retn
0x180063ec7  mov     ecx, 1000002Dh
0x180063ecc  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180063ed2  mov     ecx, 20000002h
0x180063ed7  mov     ebx, eax
0x180063ed9  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180063edf  test    al, al
0x180063ee1  jz      short loc_180063F12
0x180063ee3  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x180063ee9  test    al, al
0x180063eeb  jnz     short loc_180063EF5
0x180063eed  mov     cl, [rbp+4Fh+var_50]
0x180063ef0  jmp     loc_180063E64
0x180063ef5  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x180063efb  movzx   ecx, al
0x180063efe  cmp     ebx, 3
0x180063f01  jz      loc_180063E64
0x180063f07  mov     cs:dword_18015A4CC, ecx
0x180063f0d  jmp     loc_180063E64
0x180063f12  cmp     ebx, 2
0x180063f15  jnz     short loc_180063EE3
0x180063f17  mov     ecx, 10000038h
0x180063f1c  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180063f22  test    al, al
0x180063f24  jnz     short loc_180063F46
0x180063f26  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x180063f2c  mov     r8, rax
0x180063f2f  lea     rdx, [rbp+4Fh+var_50]
0x180063f33  mov     rcx, [rax]
0x180063f36  mov     rax, [rcx+78h]
0x180063f3a  mov     rcx, r8
0x180063f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f42  test    eax, eax
0x180063f44  jns     short loc_180063EED
0x180063f46  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x180063f4c  mov     cl, al
0x180063f4e  jmp     loc_180063E64
0x180063f53  mov     edi, 2
0x180063f58  jmp     loc_180063E6C
```
