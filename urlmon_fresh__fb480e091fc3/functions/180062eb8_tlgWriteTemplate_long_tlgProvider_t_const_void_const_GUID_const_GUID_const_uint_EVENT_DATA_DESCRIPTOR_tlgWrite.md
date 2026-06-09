# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180062eb8`
- end: `0x1800630fa`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z`
- size: `578`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800891a0`
- `0x18009e670`
- `0x18009ebd0`

## callees

- `0x180062eb8`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18006307a`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18006307a`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180063062`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180063062`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x1800630dd`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x1800630dd`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180062fa7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180063052`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800630a7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180062fa7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180063052`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800630a7`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18006303f`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18006303f`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x1800630b7`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x1800630b7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180063004`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180063004`

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
  UserData.Ptr = (ULONGLONG)off_180166008;
  v26 = v7;
  v28 = 0;
  v25 = 4;
  v23 = 8;
  UserData.Size = *(unsigned __int16 *)off_180166008;
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
    if ( dword_1801675C4 != 2 )
    {
      LOBYTE(v11) = dword_1801675C4 == 1;
      goto LABEL_9;
    }
    DWORD = IEConfiguration_GetDWORD(268435501);
    if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
    {
      if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
      {
        v11 = LCIEIsCurrentProcessInPrivate();
        if ( DWORD != 3 )
          dword_1801675C4 = v11;
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
0x180062eb8  push    rbp
0x180062eba  push    rbx
0x180062ebb  push    rsi
0x180062ebc  push    rdi
0x180062ebd  lea     rbp, [rsp-27h]
0x180062ec2  sub     rsp, 0C8h
0x180062ec9  mov     rax, cs:__security_cookie
0x180062ed0  xor     rax, rsp
0x180062ed3  mov     [rbp+3Fh+var_30], rax
0x180062ed7  mov     rax, [rbp+3Fh+arg_30]
0x180062edb  xor     esi, esi
0x180062edd  mov     rcx, [rax]
0x180062ee0  test    rcx, rcx
0x180062ee3  jz      loc_180063029
0x180062ee9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180062eed  inc     rax
0x180062ef0  cmp     [rcx+rax*2], si
0x180062ef4  jnz     short loc_180062EED
0x180062ef6  lea     eax, ds:2[rax*2]
0x180062efd  mov     [rbp+3Fh+var_38], eax
0x180062f00  mov     edi, esi
0x180062f02  mov     rax, [rbp+3Fh+arg_28]
0x180062f06  mov     [rbp+3Fh+var_50], rax
0x180062f0a  mov     rax, [rbp+3Fh+arg_20]
0x180062f0e  mov     [rbp+3Fh+var_60], rax
0x180062f12  movzx   eax, byte ptr [rdx]
0x180062f15  shl     eax, 18h
0x180062f18  mov     dword ptr [rbp+3Fh+EventDescriptor.Id], eax
0x180062f1b  movzx   eax, word ptr [rdx+1]
0x180062f1f  mov     dword ptr [rbp+3Fh+EventDescriptor.Level], eax
0x180062f22  mov     rax, [rdx+3]
0x180062f26  mov     [rbp+3Fh+EventDescriptor.Keyword], rax
0x180062f2a  mov     rax, cs:off_180166008
0x180062f31  mov     [rbp+3Fh+var_80.Ptr], rax
0x180062f35  mov     [rbp+3Fh+var_40], rcx
0x180062f39  lea     rcx, [rdx+0Bh]
0x180062f3d  mov     [rbp+3Fh+var_34], esi
0x180062f40  mov     [rbp+3Fh+var_48], 4
0x180062f48  mov     [rbp+3Fh+var_58], 8
0x180062f50  movzx   eax, word ptr [rax]
0x180062f53  mov     [rbp+3Fh+var_80.Size], eax
0x180062f56  movzx   eax, word ptr [rcx]
0x180062f59  mov     [rbp+3Fh+var_68], eax
0x180062f5c  lea     rax, _TraceLoggingMetadataEnd
0x180062f63  mov     [rbp+3Fh+var_70], rcx
0x180062f67  lea     rcx, _TraceLoggingMetadata
0x180062f6e  sub     eax, ecx
0x180062f70  mov     dword ptr [rbp+3Fh+var_80.0Ch], 2
0x180062f77  mov     ecx, cs:_tls_index
0x180062f7d  mov     [rbp+3Fh+var_64], 1
0x180062f84  mov     [rbp+3Fh+var_9C], eax
0x180062f87  mov     eax, [rbp+3Fh+var_9C]
0x180062f8a  mov     rax, gs:58h
0x180062f93  mov     edx, 8
0x180062f98  mov     rax, [rax+rcx*8]
0x180062f9c  cmp     [rdx+rax], sil
0x180062fa0  jnz     short loc_180062FD8
0x180062fa2  mov     ecx, 20000019h
0x180062fa7  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180062fae  nop     dword ptr [rax+rax+00h]
0x180062fb3  test    al, al
0x180062fb5  jz      loc_1800630F0
0x180062fbb  mov     eax, cs:dword_1801675C4
0x180062fc1  mov     [rbp+3Fh+var_A0], 1
0x180062fc5  cmp     eax, 2
0x180062fc8  jz      short loc_18006303A
0x180062fca  cmp     eax, 1
0x180062fcd  setz    cl
0x180062fd0  test    cl, cl
0x180062fd2  jnz     loc_1800630F0
0x180062fd8  mov     rcx, cs:RegHandle; RegHandle
0x180062fdf  lea     rax, [rbp+3Fh+var_80]
0x180062fe3  mov     [rsp+0E0h+UserData], rax; UserData
0x180062fe8  lea     rdx, [rbp+3Fh+EventDescriptor]; EventDescriptor
0x180062fec  mov     [rsp+0E0h+UserDataCount], 5; UserDataCount
0x180062ff4  mov     r9d, edi; Flags
0x180062ff7  mov     [rsp+0E0h+RelatedActivityId], rsi; RelatedActivityId
0x180062ffc  xor     r8d, r8d; Filter
0x180062fff  mov     [rsp+0E0h+ActivityId], rsi; ActivityId
0x180063004  call    cs:__imp_EventWriteEx
0x18006300b  nop     dword ptr [rax+rax+00h]
0x180063010  mov     rcx, [rbp+3Fh+var_30]
0x180063014  xor     rcx, rsp; StackCookie
0x180063017  call    __security_check_cookie
0x18006301c  add     rsp, 0C8h
0x180063023  pop     rdi
0x180063024  pop     rsi
0x180063025  pop     rbx
0x180063026  pop     rbp
0x180063027  retn
0x180063029  lea     rcx, pszFormat
0x180063030  mov     eax, 2
0x180063035  jmp     loc_180062EFD
0x18006303a  mov     ecx, 1000002Dh
0x18006303f  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180063046  nop     dword ptr [rax+rax+00h]
0x18006304b  mov     ecx, 20000002h
0x180063050  mov     ebx, eax
0x180063052  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180063059  nop     dword ptr [rax+rax+00h]
0x18006305e  test    al, al
0x180063060  jz      short loc_18006309D
0x180063062  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x180063069  nop     dword ptr [rax+rax+00h]
0x18006306e  test    al, al
0x180063070  jnz     short loc_18006307A
0x180063072  mov     cl, [rbp+3Fh+var_A0]
0x180063075  jmp     loc_180062FD0
0x18006307a  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x180063081  nop     dword ptr [rax+rax+00h]
0x180063086  movzx   ecx, al
0x180063089  cmp     ebx, 3
0x18006308c  jz      loc_180062FD0
0x180063092  mov     cs:dword_1801675C4, ecx
0x180063098  jmp     loc_180062FD0
0x18006309d  cmp     ebx, 2
0x1800630a0  jnz     short loc_180063062
0x1800630a2  mov     ecx, 10000038h
0x1800630a7  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800630ae  nop     dword ptr [rax+rax+00h]
0x1800630b3  test    al, al
0x1800630b5  jnz     short loc_1800630DD
0x1800630b7  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x1800630be  nop     dword ptr [rax+rax+00h]
0x1800630c3  mov     r8, rax
0x1800630c6  lea     rdx, [rbp+3Fh+var_A0]
0x1800630ca  mov     rcx, [rax]
0x1800630cd  mov     rax, [rcx+78h]
0x1800630d1  mov     rcx, r8
0x1800630d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800630d9  test    eax, eax
0x1800630db  jns     short loc_180063072
0x1800630dd  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x1800630e4  nop     dword ptr [rax+rax+00h]
0x1800630e9  mov     cl, al
0x1800630eb  jmp     loc_180062FD0
0x1800630f0  mov     edi, 2
0x1800630f5  jmp     loc_180062FD8
```
