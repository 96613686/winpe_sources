# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180061ed8`
- end: `0x180062186`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@44444@Z`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004aab0`

## callees

- `0x180061ed8`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180062105`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180062105`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x1800620ec`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x1800620ec`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180062169`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180062169`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006202e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800620dc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180062132`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006202e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800620dc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180062132`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800620c9`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800620c9`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180062142`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180062142`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18006208e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18006208e`

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
  UserData.Ptr = (ULONGLONG)off_180166008;
  v31 = v12;
  v33 = 0;
  v30 = 4;
  v28 = 8;
  UserData.Size = *(unsigned __int16 *)off_180166008;
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
    if ( dword_1801675C4 != 2 )
    {
      LOBYTE(v16) = dword_1801675C4 == 1;
      goto LABEL_9;
    }
    DWORD = IEConfiguration_GetDWORD(268435501);
    if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
    {
      if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
      {
        v16 = LCIEIsCurrentProcessInPrivate();
        if ( DWORD != 3 )
          dword_1801675C4 = v16;
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
0x180061ed8  push    rbp
0x180061eda  push    rbx
0x180061edb  push    rsi
0x180061edc  push    rdi
0x180061edd  lea     rbp, [rsp-18h]
0x180061ee2  sub     rsp, 118h
0x180061ee9  mov     rax, cs:__security_cookie
0x180061ef0  xor     rax, rsp
0x180061ef3  mov     [rbp+30h+var_30], rax
0x180061ef7  mov     rax, [rbp+30h+arg_58]
0x180061efe  xor     esi, esi
0x180061f00  mov     [rbp+30h+var_40], rax
0x180061f04  mov     rax, [rbp+30h+arg_50]
0x180061f0b  mov     [rbp+30h+var_50], rax
0x180061f0f  mov     rax, [rbp+30h+arg_48]
0x180061f16  mov     [rbp+30h+var_60], rax
0x180061f1a  mov     rax, [rbp+30h+arg_40]
0x180061f21  mov     [rbp+30h+var_70], rax
0x180061f25  mov     rax, [rbp+30h+arg_38]
0x180061f29  mov     [rbp+30h+var_80], rax
0x180061f2d  mov     rax, [rbp+30h+arg_30]
0x180061f31  mov     [rbp+30h+var_38], 4
0x180061f39  mov     [rbp+30h+var_48], 4
0x180061f41  mov     [rbp+30h+var_58], 4
0x180061f49  mov     rcx, [rax]
0x180061f4c  mov     [rbp+30h+var_68], 4
0x180061f54  mov     [rbp+30h+var_78], 4
0x180061f5c  test    rcx, rcx
0x180061f5f  jz      loc_1800620B3
0x180061f65  or      rax, 0FFFFFFFFFFFFFFFFh
0x180061f69  inc     rax
0x180061f6c  cmp     [rcx+rax*2], si
0x180061f70  jnz     short loc_180061F69
0x180061f72  lea     eax, ds:2[rax*2]
0x180061f79  mov     [rbp+30h+var_88], eax
0x180061f7c  mov     edi, esi
0x180061f7e  mov     rax, [rbp+30h+arg_28]
0x180061f82  mov     [rbp+30h+var_A0], rax
0x180061f86  mov     rax, [rbp+30h+arg_20]
0x180061f8a  mov     [rbp+30h+var_B0], rax
0x180061f8e  movzx   eax, byte ptr [rdx]
0x180061f91  shl     eax, 18h
0x180061f94  mov     dword ptr [rsp+130h+EventDescriptor.Id], eax
0x180061f98  movzx   eax, word ptr [rdx+1]
0x180061f9c  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x180061fa0  mov     rax, [rdx+3]
0x180061fa4  mov     [rsp+130h+EventDescriptor.Keyword], rax
0x180061fa9  mov     rax, cs:off_180166008
0x180061fb0  mov     [rsp+130h+var_D0.Ptr], rax
0x180061fb5  mov     [rbp+30h+var_90], rcx
0x180061fb9  lea     rcx, [rdx+0Bh]
0x180061fbd  mov     [rbp+30h+var_84], esi
0x180061fc0  mov     [rbp+30h+var_98], 4
0x180061fc8  mov     [rbp+30h+var_A8], 8
0x180061fd0  movzx   eax, word ptr [rax]
0x180061fd3  mov     [rsp+130h+var_D0.Size], eax
0x180061fd7  movzx   eax, word ptr [rcx]
0x180061fda  mov     [rsp+130h+var_B8], eax
0x180061fde  lea     rax, _TraceLoggingMetadataEnd
0x180061fe5  mov     [rsp+130h+var_C0], rcx
0x180061fea  lea     rcx, _TraceLoggingMetadata
0x180061ff1  sub     eax, ecx
0x180061ff3  mov     dword ptr [rsp+130h+var_D0.0Ch], 2
0x180061ffb  mov     ecx, cs:_tls_index
0x180062001  mov     [rsp+130h+var_B4], 1
0x180062009  mov     [rsp+130h+var_EC], eax
0x18006200d  mov     eax, [rsp+130h+var_EC]
0x180062011  mov     rax, gs:58h
0x18006201a  mov     edx, 8
0x18006201f  mov     rax, [rax+rcx*8]
0x180062023  cmp     [rdx+rax], sil
0x180062027  jnz     short loc_180062060
0x180062029  mov     ecx, 20000019h
0x18006202e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180062035  nop     dword ptr [rax+rax+00h]
0x18006203a  test    al, al
0x18006203c  jz      loc_18006217C
0x180062042  mov     eax, cs:dword_1801675C4
0x180062048  mov     [rsp+130h+var_F0], 1
0x18006204d  cmp     eax, 2
0x180062050  jz      short loc_1800620C4
0x180062052  cmp     eax, 1
0x180062055  setz    cl
0x180062058  test    cl, cl
0x18006205a  jnz     loc_18006217C
0x180062060  mov     rcx, cs:RegHandle; RegHandle
0x180062067  lea     rax, [rsp+130h+var_D0]
0x18006206c  mov     [rsp+130h+UserData], rax; UserData
0x180062071  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x180062076  mov     [rsp+130h+UserDataCount], 0Ah; UserDataCount
0x18006207e  mov     r9d, edi; Flags
0x180062081  mov     [rsp+130h+RelatedActivityId], rsi; RelatedActivityId
0x180062086  xor     r8d, r8d; Filter
0x180062089  mov     [rsp+130h+ActivityId], rsi; ActivityId
0x18006208e  call    cs:__imp_EventWriteEx
0x180062095  nop     dword ptr [rax+rax+00h]
0x18006209a  mov     rcx, [rbp+30h+var_30]
0x18006209e  xor     rcx, rsp; StackCookie
0x1800620a1  call    __security_check_cookie
0x1800620a6  add     rsp, 118h
0x1800620ad  pop     rdi
0x1800620ae  pop     rsi
0x1800620af  pop     rbx
0x1800620b0  pop     rbp
0x1800620b1  retn
0x1800620b3  lea     rcx, pszFormat
0x1800620ba  mov     eax, 2
0x1800620bf  jmp     loc_180061F79
0x1800620c4  mov     ecx, 1000002Dh
0x1800620c9  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1800620d0  nop     dword ptr [rax+rax+00h]
0x1800620d5  mov     ecx, 20000002h
0x1800620da  mov     ebx, eax
0x1800620dc  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800620e3  nop     dword ptr [rax+rax+00h]
0x1800620e8  test    al, al
0x1800620ea  jz      short loc_180062128
0x1800620ec  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x1800620f3  nop     dword ptr [rax+rax+00h]
0x1800620f8  test    al, al
0x1800620fa  jnz     short loc_180062105
0x1800620fc  mov     cl, [rsp+130h+var_F0]
0x180062100  jmp     loc_180062058
0x180062105  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x18006210c  nop     dword ptr [rax+rax+00h]
0x180062111  movzx   ecx, al
0x180062114  cmp     ebx, 3
0x180062117  jz      loc_180062058
0x18006211d  mov     cs:dword_1801675C4, ecx
0x180062123  jmp     loc_180062058
0x180062128  cmp     ebx, 2
0x18006212b  jnz     short loc_1800620EC
0x18006212d  mov     ecx, 10000038h
0x180062132  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180062139  nop     dword ptr [rax+rax+00h]
0x18006213e  test    al, al
0x180062140  jnz     short loc_180062169
0x180062142  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x180062149  nop     dword ptr [rax+rax+00h]
0x18006214e  mov     r8, rax
0x180062151  lea     rdx, [rsp+130h+var_F0]
0x180062156  mov     rcx, [rax]
0x180062159  mov     rax, [rcx+78h]
0x18006215d  mov     rcx, r8
0x180062160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062165  test    eax, eax
0x180062167  jns     short loc_1800620FC
0x180062169  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x180062170  nop     dword ptr [rax+rax+00h]
0x180062175  mov     cl, al
0x180062177  jmp     loc_180062058
0x18006217c  mov     edi, 2
0x180062181  jmp     loc_180062060
```
