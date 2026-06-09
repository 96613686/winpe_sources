# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18005c564`
- end: `0x18005c7db`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@44444@Z`
- size: `631`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64, const OLECHAR **, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053950`

## callees

- `0x18005c564`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18005c772`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18005c772`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x18005c75f`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x18005c75f`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x18005c7c4`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x18005c7c4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005c6ba`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005c755`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005c799`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005c6ba`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005c755`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005c799`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18005c748`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18005c748`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18005c7a3`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18005c7a3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18005c714`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18005c714`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const OLECHAR **a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  const OLECHAR *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  ULONG v15; // edi
  BOOL v16; // ecx
  int DWORD; // ebx
  struct IEdgeBrowsingEnvironment *EdgeBrowsingEnvironment; // rax
  char v20[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-BCh]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 *v24; // [rsp+70h] [rbp-90h]
  int v25; // [rsp+78h] [rbp-88h]
  int v26; // [rsp+7Ch] [rbp-84h]
  __int64 v27; // [rsp+80h] [rbp-80h]
  __int64 v28; // [rsp+88h] [rbp-78h]
  __int64 v29; // [rsp+90h] [rbp-70h]
  __int64 v30; // [rsp+98h] [rbp-68h]
  const OLECHAR *v31; // [rsp+A0h] [rbp-60h]
  int v32; // [rsp+A8h] [rbp-58h]
  int v33; // [rsp+ACh] [rbp-54h]
  __int64 v34; // [rsp+B0h] [rbp-50h]
  __int64 v35; // [rsp+B8h] [rbp-48h]
  __int64 v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  __int64 v38; // [rsp+D0h] [rbp-30h]
  __int64 v39; // [rsp+D8h] [rbp-28h]
  __int64 v40; // [rsp+E0h] [rbp-20h]
  __int64 v41; // [rsp+E8h] [rbp-18h]
  __int64 v42; // [rsp+F0h] [rbp-10h]
  __int64 v43; // [rsp+F8h] [rbp-8h]

  v42 = a12;
  v40 = a11;
  v38 = a10;
  v36 = a9;
  v34 = a8;
  v43 = 4;
  v41 = 4;
  v39 = 4;
  v12 = *a7;
  v37 = 4;
  v35 = 4;
  if ( v12 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v12 = &pszFormat;
    v14 = 2;
  }
  v32 = v14;
  v15 = 0;
  v29 = a6;
  v27 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180159008;
  v31 = v12;
  v33 = 0;
  v30 = 4;
  v28 = 8;
  UserData.Size = *(unsigned __int16 *)off_180159008;
  v25 = *(unsigned __int16 *)(a2 + 11);
  v24 = a2 + 11;
  UserData.Reserved = 2;
  v26 = 1;
  v21 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  if ( !*(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL) )
  {
    if ( !(unsigned __int8)IEConfiguration_GetBool(536870937) )
      goto LABEL_21;
    v20[0] = 1;
    if ( dword_18015A4CC != 2 )
    {
      LOBYTE(v16) = dword_18015A4CC == 1;
      goto LABEL_9;
    }
    DWORD = IEConfiguration_GetDWORD(268435501);
    if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
    {
      if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
      {
        v16 = LCIEIsCurrentProcessInPrivate();
        if ( DWORD != 3 )
          dword_18015A4CC = v16;
LABEL_9:
        if ( !v16 )
          return EventWriteEx(RegHandle, &EventDescriptor, 0, v15, 0, 0, 0xAu, &UserData);
LABEL_21:
        v15 = 2;
        return EventWriteEx(RegHandle, &EventDescriptor, 0, v15, 0, 0, 0xAu, &UserData);
      }
    }
    else if ( (unsigned __int8)IEConfiguration_GetBool(268435512)
           || (EdgeBrowsingEnvironment = GetEdgeBrowsingEnvironment(),
               (*(int (__fastcall **)(struct IEdgeBrowsingEnvironment *, char *))(*(_QWORD *)EdgeBrowsingEnvironment
                                                                                + 120LL))(
                 EdgeBrowsingEnvironment,
                 v20) < 0) )
    {
      LOBYTE(v16) = LCIEIsCurrentProcessUsingInPrivateComponents();
      goto LABEL_9;
    }
    LOBYTE(v16) = v20[0];
    goto LABEL_9;
  }
  return EventWriteEx(RegHandle, &EventDescriptor, 0, v15, 0, 0, 0xAu, &UserData);
}

```

## disassembly

```asm
0x18005c564  push    rbp
0x18005c566  push    rbx
0x18005c567  push    rsi
0x18005c568  push    rdi
0x18005c569  lea     rbp, [rsp-18h]
0x18005c56e  sub     rsp, 118h
0x18005c575  mov     rax, cs:__security_cookie
0x18005c57c  xor     rax, rsp
0x18005c57f  mov     [rbp+30h+var_30], rax
0x18005c583  mov     rax, [rbp+30h+arg_58]
0x18005c58a  xor     esi, esi
0x18005c58c  mov     [rbp+30h+var_40], rax
0x18005c590  mov     rax, [rbp+30h+arg_50]
0x18005c597  mov     [rbp+30h+var_50], rax
0x18005c59b  mov     rax, [rbp+30h+arg_48]
0x18005c5a2  mov     [rbp+30h+var_60], rax
0x18005c5a6  mov     rax, [rbp+30h+arg_40]
0x18005c5ad  mov     [rbp+30h+var_70], rax
0x18005c5b1  mov     rax, [rbp+30h+arg_38]
0x18005c5b5  mov     [rbp+30h+var_80], rax
0x18005c5b9  mov     rax, [rbp+30h+arg_30]
0x18005c5bd  mov     [rbp+30h+var_38], 4
0x18005c5c5  mov     [rbp+30h+var_48], 4
0x18005c5cd  mov     [rbp+30h+var_58], 4
0x18005c5d5  mov     rcx, [rax]
0x18005c5d8  mov     [rbp+30h+var_68], 4
0x18005c5e0  mov     [rbp+30h+var_78], 4
0x18005c5e8  test    rcx, rcx
0x18005c5eb  jz      loc_18005C732
0x18005c5f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005c5f5  inc     rax
0x18005c5f8  cmp     [rcx+rax*2], si
0x18005c5fc  jnz     short loc_18005C5F5
0x18005c5fe  lea     eax, ds:2[rax*2]
0x18005c605  mov     [rbp+30h+var_88], eax
0x18005c608  mov     edi, esi
0x18005c60a  mov     rax, [rbp+30h+arg_28]
0x18005c60e  mov     [rbp+30h+var_A0], rax
0x18005c612  mov     rax, [rbp+30h+arg_20]
0x18005c616  mov     [rbp+30h+var_B0], rax
0x18005c61a  movzx   eax, byte ptr [rdx]
0x18005c61d  shl     eax, 18h
0x18005c620  mov     dword ptr [rsp+130h+EventDescriptor.Id], eax
0x18005c624  movzx   eax, word ptr [rdx+1]
0x18005c628  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x18005c62c  mov     rax, [rdx+3]
0x18005c630  mov     [rsp+130h+EventDescriptor.Keyword], rax
0x18005c635  mov     rax, cs:off_180159008
0x18005c63c  mov     [rsp+130h+var_D0.Ptr], rax
0x18005c641  mov     [rbp+30h+var_90], rcx
0x18005c645  lea     rcx, [rdx+0Bh]
0x18005c649  mov     [rbp+30h+var_84], esi
0x18005c64c  mov     [rbp+30h+var_98], 4
0x18005c654  mov     [rbp+30h+var_A8], 8
0x18005c65c  movzx   eax, word ptr [rax]
0x18005c65f  mov     [rsp+130h+var_D0.Size], eax
0x18005c663  movzx   eax, word ptr [rcx]
0x18005c666  mov     [rsp+130h+var_B8], eax
0x18005c66a  lea     rax, _TraceLoggingMetadataEnd
0x18005c671  mov     [rsp+130h+var_C0], rcx
0x18005c676  lea     rcx, _TraceLoggingMetadata
0x18005c67d  sub     eax, ecx
0x18005c67f  mov     dword ptr [rsp+130h+var_D0.0Ch], 2
0x18005c687  mov     ecx, cs:_tls_index
0x18005c68d  mov     [rsp+130h+var_B4], 1
0x18005c695  mov     [rsp+130h+var_EC], eax
0x18005c699  mov     eax, [rsp+130h+var_EC]
0x18005c69d  mov     rax, gs:58h
0x18005c6a6  mov     edx, 8
0x18005c6ab  mov     rax, [rax+rcx*8]
0x18005c6af  cmp     [rdx+rax], sil
0x18005c6b3  jnz     short loc_18005C6E6
0x18005c6b5  mov     ecx, 20000019h
0x18005c6ba  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005c6c0  test    al, al
0x18005c6c2  jz      loc_18005C7D1
0x18005c6c8  mov     eax, cs:dword_18015A4CC
0x18005c6ce  mov     [rsp+130h+var_F0], 1
0x18005c6d3  cmp     eax, 2
0x18005c6d6  jz      short loc_18005C743
0x18005c6d8  cmp     eax, 1
0x18005c6db  setz    cl
0x18005c6de  test    cl, cl
0x18005c6e0  jnz     loc_18005C7D1
0x18005c6e6  mov     rcx, cs:RegHandle; RegHandle
0x18005c6ed  lea     rax, [rsp+130h+var_D0]
0x18005c6f2  mov     [rsp+130h+UserData], rax; UserData
0x18005c6f7  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x18005c6fc  mov     [rsp+130h+UserDataCount], 0Ah; UserDataCount
0x18005c704  mov     r9d, edi; Flags
0x18005c707  mov     [rsp+130h+RelatedActivityId], rsi; RelatedActivityId
0x18005c70c  xor     r8d, r8d; Filter
0x18005c70f  mov     [rsp+130h+ActivityId], rsi; ActivityId
0x18005c714  call    cs:__imp_EventWriteEx
0x18005c71a  mov     rcx, [rbp+30h+var_30]
0x18005c71e  xor     rcx, rsp; StackCookie
0x18005c721  call    __security_check_cookie
0x18005c726  add     rsp, 118h
0x18005c72d  pop     rdi
0x18005c72e  pop     rsi
0x18005c72f  pop     rbx
0x18005c730  pop     rbp
0x18005c731  retn
0x18005c732  lea     rcx, pszFormat
0x18005c739  mov     eax, 2
0x18005c73e  jmp     loc_18005C605
0x18005c743  mov     ecx, 1000002Dh
0x18005c748  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18005c74e  mov     ecx, 20000002h
0x18005c753  mov     ebx, eax
0x18005c755  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005c75b  test    al, al
0x18005c75d  jz      short loc_18005C78F
0x18005c75f  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x18005c765  test    al, al
0x18005c767  jnz     short loc_18005C772
0x18005c769  mov     cl, [rsp+130h+var_F0]
0x18005c76d  jmp     loc_18005C6DE
0x18005c772  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x18005c778  movzx   ecx, al
0x18005c77b  cmp     ebx, 3
0x18005c77e  jz      loc_18005C6DE
0x18005c784  mov     cs:dword_18015A4CC, ecx
0x18005c78a  jmp     loc_18005C6DE
0x18005c78f  cmp     ebx, 2
0x18005c792  jnz     short loc_18005C75F
0x18005c794  mov     ecx, 10000038h
0x18005c799  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005c79f  test    al, al
0x18005c7a1  jnz     short loc_18005C7C4
0x18005c7a3  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x18005c7a9  mov     r8, rax
0x18005c7ac  lea     rdx, [rsp+130h+var_F0]
0x18005c7b1  mov     rcx, [rax]
0x18005c7b4  mov     rax, [rcx+78h]
0x18005c7b8  mov     rcx, r8
0x18005c7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c7c0  test    eax, eax
0x18005c7c2  jns     short loc_18005C769
0x18005c7c4  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x18005c7ca  mov     cl, al
0x18005c7cc  jmp     loc_18005C6DE
0x18005c7d1  mov     edi, 2
0x18005c7d6  jmp     loc_18005C6E6
```
