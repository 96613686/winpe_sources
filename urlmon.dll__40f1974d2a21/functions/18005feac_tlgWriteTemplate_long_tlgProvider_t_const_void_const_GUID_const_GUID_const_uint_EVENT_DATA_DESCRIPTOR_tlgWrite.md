# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x18005feac`
- end: `0x1800600b7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `523`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64, const OLECHAR **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180097e00`
- `0x180098360`

## callees

- `0x18005feac`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18006004f`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18006004f`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x18006003d`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x18006003d`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x1800600a0`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x1800600a0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005ff9b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060033`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060076`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005ff9b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060033`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180060076`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180060026`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180060026`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180060080`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180060080`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18005fff2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18005fff2`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const OLECHAR **a7)
{
  const OLECHAR *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  ULONG v10; // edi
  BOOL v11; // ecx
  int DWORD; // ebx
  struct IEdgeBrowsingEnvironment *EdgeBrowsingEnvironment; // rax
  char v15[4]; // [rsp+40h] [rbp-61h] BYREF
  unsigned int v16; // [rsp+44h] [rbp-5Dh]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-41h] BYREF
  unsigned __int8 *v19; // [rsp+70h] [rbp-31h]
  int v20; // [rsp+78h] [rbp-29h]
  int v21; // [rsp+7Ch] [rbp-25h]
  __int64 v22; // [rsp+80h] [rbp-21h]
  __int64 v23; // [rsp+88h] [rbp-19h]
  __int64 v24; // [rsp+90h] [rbp-11h]
  __int64 v25; // [rsp+98h] [rbp-9h]
  const OLECHAR *v26; // [rsp+A0h] [rbp-1h]
  int v27; // [rsp+A8h] [rbp+7h]
  int v28; // [rsp+ACh] [rbp+Bh]

  v7 = *a7;
  if ( *a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v7 = &pszFormat;
    v9 = 2;
  }
  v27 = v9;
  v10 = 0;
  v24 = a6;
  v22 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180159008;
  v26 = v7;
  v28 = 0;
  v25 = 4;
  v23 = 8;
  UserData.Size = *(unsigned __int16 *)off_180159008;
  v20 = *(unsigned __int16 *)(a2 + 11);
  v19 = a2 + 11;
  UserData.Reserved = 2;
  v21 = 1;
  v16 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  if ( !*(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL) )
  {
    if ( !(unsigned __int8)IEConfiguration_GetBool(536870937) )
      goto LABEL_21;
    v15[0] = 1;
    if ( dword_18015A4CC != 2 )
    {
      LOBYTE(v11) = dword_18015A4CC == 1;
      goto LABEL_9;
    }
    DWORD = IEConfiguration_GetDWORD(268435501);
    if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
    {
      if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
      {
        v11 = LCIEIsCurrentProcessInPrivate();
        if ( DWORD != 3 )
          dword_18015A4CC = v11;
LABEL_9:
        if ( !v11 )
          return EventWriteEx(RegHandle, &EventDescriptor, 0, v10, 0, 0, 5u, &UserData);
LABEL_21:
        v10 = 2;
        return EventWriteEx(RegHandle, &EventDescriptor, 0, v10, 0, 0, 5u, &UserData);
      }
    }
    else if ( (unsigned __int8)IEConfiguration_GetBool(268435512)
           || (EdgeBrowsingEnvironment = GetEdgeBrowsingEnvironment(),
               (*(int (__fastcall **)(struct IEdgeBrowsingEnvironment *, char *))(*(_QWORD *)EdgeBrowsingEnvironment
                                                                                + 120LL))(
                 EdgeBrowsingEnvironment,
                 v15) < 0) )
    {
      LOBYTE(v11) = LCIEIsCurrentProcessUsingInPrivateComponents();
      goto LABEL_9;
    }
    LOBYTE(v11) = v15[0];
    goto LABEL_9;
  }
  return EventWriteEx(RegHandle, &EventDescriptor, 0, v10, 0, 0, 5u, &UserData);
}

```

## disassembly

```asm
0x18005feac  push    rbp
0x18005feae  push    rbx
0x18005feaf  push    rsi
0x18005feb0  push    rdi
0x18005feb1  lea     rbp, [rsp-27h]
0x18005feb6  sub     rsp, 0C8h
0x18005febd  mov     rax, cs:__security_cookie
0x18005fec4  xor     rax, rsp
0x18005fec7  mov     [rbp+3Fh+var_30], rax
0x18005fecb  mov     rax, [rbp+3Fh+arg_30]
0x18005fecf  xor     esi, esi
0x18005fed1  mov     rcx, [rax]
0x18005fed4  test    rcx, rcx
0x18005fed7  jz      loc_180060010
0x18005fedd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005fee1  inc     rax
0x18005fee4  cmp     [rcx+rax*2], si
0x18005fee8  jnz     short loc_18005FEE1
0x18005feea  lea     eax, ds:2[rax*2]
0x18005fef1  mov     [rbp+3Fh+var_38], eax
0x18005fef4  mov     edi, esi
0x18005fef6  mov     rax, [rbp+3Fh+arg_28]
0x18005fefa  mov     [rbp+3Fh+var_50], rax
0x18005fefe  mov     rax, [rbp+3Fh+arg_20]
0x18005ff02  mov     [rbp+3Fh+var_60], rax
0x18005ff06  movzx   eax, byte ptr [rdx]
0x18005ff09  shl     eax, 18h
0x18005ff0c  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], eax
0x18005ff0f  movzx   eax, word ptr [rdx+1]
0x18005ff13  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x18005ff16  mov     rax, [rdx+3]
0x18005ff1a  mov     [rbp+3Fh+EventDescriptor.Keyword], rax
0x18005ff1e  mov     rax, cs:off_180159008
0x18005ff25  mov     [rbp+3Fh+var_80.Ptr], rax
0x18005ff29  mov     [rbp+3Fh+var_40], rcx
0x18005ff2d  lea     rcx, [rdx+0Bh]
0x18005ff31  mov     [rbp+3Fh+var_34], esi
0x18005ff34  mov     [rbp+3Fh+var_48], 4
0x18005ff3c  mov     [rbp+3Fh+var_58], 8
0x18005ff44  movzx   eax, word ptr [rax]
0x18005ff47  mov     [rbp+3Fh+var_80.Size], eax
0x18005ff4a  movzx   eax, word ptr [rcx]
0x18005ff4d  mov     [rbp+3Fh+var_68], eax
0x18005ff50  lea     rax, _TraceLoggingMetadataEnd
0x18005ff57  mov     [rbp+3Fh+var_70], rcx
0x18005ff5b  lea     rcx, _TraceLoggingMetadata
0x18005ff62  sub     eax, ecx
0x18005ff64  mov     dword ptr [rbp+3Fh+var_80.0Ch], 2
0x18005ff6b  mov     ecx, cs:_tls_index
0x18005ff71  mov     [rbp+3Fh+var_64], 1
0x18005ff78  mov     [rbp+3Fh+var_9C], eax
0x18005ff7b  mov     eax, [rbp+3Fh+var_9C]
0x18005ff7e  mov     rax, gs:58h
0x18005ff87  mov     edx, 8
0x18005ff8c  mov     rax, [rax+rcx*8]
0x18005ff90  cmp     [rdx+rax], sil
0x18005ff94  jnz     short loc_18005FFC6
0x18005ff96  mov     ecx, 20000019h
0x18005ff9b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005ffa1  test    al, al
0x18005ffa3  jz      loc_1800600AD
0x18005ffa9  mov     eax, cs:dword_18015A4CC
0x18005ffaf  mov     [rbp+3Fh+var_A0], 1
0x18005ffb3  cmp     eax, 2
0x18005ffb6  jz      short loc_180060021
0x18005ffb8  cmp     eax, 1
0x18005ffbb  setz    cl
0x18005ffbe  test    cl, cl
0x18005ffc0  jnz     loc_1800600AD
0x18005ffc6  mov     rcx, cs:RegHandle; RegHandle
0x18005ffcd  lea     rax, [rbp+3Fh+var_80]
0x18005ffd1  mov     [rsp+0E0h+UserData], rax; UserData
0x18005ffd6  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x18005ffda  mov     [rsp+0E0h+UserDataCount], 5; UserDataCount
0x18005ffe2  mov     r9d, edi; Flags
0x18005ffe5  mov     [rsp+0E0h+RelatedActivityId], rsi; RelatedActivityId
0x18005ffea  xor     r8d, r8d; Filter
0x18005ffed  mov     [rsp+0E0h+ActivityId], rsi; ActivityId
0x18005fff2  call    cs:__imp_EventWriteEx
0x18005fff8  mov     rcx, [rbp+3Fh+var_30]
0x18005fffc  xor     rcx, rsp; StackCookie
0x18005ffff  call    __security_check_cookie
0x180060004  add     rsp, 0C8h
0x18006000b  pop     rdi
0x18006000c  pop     rsi
0x18006000d  pop     rbx
0x18006000e  pop     rbp
0x18006000f  retn
0x180060010  lea     rcx, pszFormat
0x180060017  mov     eax, 2
0x18006001c  jmp     loc_18005FEF1
0x180060021  mov     ecx, 1000002Dh
0x180060026  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18006002c  mov     ecx, 20000002h
0x180060031  mov     ebx, eax
0x180060033  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180060039  test    al, al
0x18006003b  jz      short loc_18006006C
0x18006003d  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x180060043  test    al, al
0x180060045  jnz     short loc_18006004F
0x180060047  mov     cl, [rbp+3Fh+var_A0]
0x18006004a  jmp     loc_18005FFBE
0x18006004f  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x180060055  movzx   ecx, al
0x180060058  cmp     ebx, 3
0x18006005b  jz      loc_18005FFBE
0x180060061  mov     cs:dword_18015A4CC, ecx
0x180060067  jmp     loc_18005FFBE
0x18006006c  cmp     ebx, 2
0x18006006f  jnz     short loc_18006003D
0x180060071  mov     ecx, 10000038h
0x180060076  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18006007c  test    al, al
0x18006007e  jnz     short loc_1800600A0
0x180060080  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x180060086  mov     r8, rax
0x180060089  lea     rdx, [rbp+3Fh+var_A0]
0x18006008d  mov     rcx, [rax]
0x180060090  mov     rax, [rcx+78h]
0x180060094  mov     rcx, r8
0x180060097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006009c  test    eax, eax
0x18006009e  jns     short loc_180060047
0x1800600a0  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x1800600a6  mov     cl, al
0x1800600a8  jmp     loc_18005FFBE
0x1800600ad  mov     edi, 2
0x1800600b2  jmp     loc_18005FFC6
```
