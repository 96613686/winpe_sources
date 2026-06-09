# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180067664`
- end: `0x1800678e2`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55@Z`
- size: `638`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, __int64, __int64, const OLECHAR **, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180090e4c`
- `0x1800934ec`

## callees

- `0x180067664`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180067861`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180067861`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180067848`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180067848`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x1800678c5`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x1800678c5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006778a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180067838`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006788e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006778a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180067838`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006788e`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180067825`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180067825`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18006789e`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18006789e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x1800677ea`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x1800677ea`

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
  int v14; // ecx
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
  UserData.Ptr = (ULONGLONG)off_180166008;
  v29 = v10;
  v31 = 0;
  v28 = 8;
  v26 = 8;
  UserData.Size = *(unsigned __int16 *)off_180166008;
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
    if ( dword_1801675C4 != 2 )
    {
      LOBYTE(v14) = dword_1801675C4 == 1;
      goto LABEL_9;
    }
    DWORD = IEConfiguration_GetDWORD(268435501);
    if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
    {
      if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
      {
        v14 = LCIEIsCurrentProcessInPrivate();
        if ( DWORD != 3 )
          dword_1801675C4 = v14;
LABEL_9:
        if ( !(_BYTE)v14 )
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
0x180067664  push    rbp
0x180067666  push    rbx
0x180067667  push    rsi
0x180067668  push    rdi
0x180067669  lea     rbp, [rsp-0Fh]
0x18006766e  sub     rsp, 0F8h
0x180067675  mov     rax, cs:__security_cookie
0x18006767c  xor     rax, rsp
0x18006767f  mov     [rbp+27h+var_30], rax
0x180067683  mov     rax, [rbp+27h+arg_48]
0x180067687  xor     esi, esi
0x180067689  mov     [rbp+27h+var_40], rax
0x18006768d  mov     rax, [rbp+27h+arg_40]
0x180067691  mov     [rbp+27h+var_50], rax
0x180067695  mov     rax, [rbp+27h+arg_38]
0x180067699  mov     [rbp+27h+var_60], rax
0x18006769d  mov     rax, [rbp+27h+arg_30]
0x1800676a1  mov     [rbp+27h+var_38], 4
0x1800676a9  mov     [rbp+27h+var_48], 4
0x1800676b1  mov     [rbp+27h+var_58], 4
0x1800676b9  mov     rcx, [rax]
0x1800676bc  test    rcx, rcx
0x1800676bf  jz      loc_18006780F
0x1800676c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800676c9  inc     rax
0x1800676cc  cmp     [rcx+rax*2], si
0x1800676d0  jnz     short loc_1800676C9
0x1800676d2  lea     eax, ds:2[rax*2]
0x1800676d9  mov     [rbp+27h+var_68], eax
0x1800676dc  mov     edi, esi
0x1800676de  mov     rax, [rbp+27h+arg_28]
0x1800676e2  mov     [rbp+27h+var_80], rax
0x1800676e6  mov     rax, [rbp+27h+arg_20]
0x1800676ea  mov     [rbp+27h+var_90], rax
0x1800676ee  movzx   eax, byte ptr [rdx]
0x1800676f1  shl     eax, 18h
0x1800676f4  mov     dword ptr [rsp+110h+EventDescriptor.Id], eax
0x1800676f8  movzx   eax, word ptr [rdx+1]
0x1800676fc  mov     dword ptr [rsp+110h+EventDescriptor.Level], eax
0x180067700  mov     rax, [rdx+3]
0x180067704  mov     [rsp+110h+EventDescriptor.Keyword], rax
0x180067709  mov     rax, cs:off_180166008
0x180067710  mov     [rsp+110h+var_B0.Ptr], rax
0x180067715  mov     [rbp+27h+var_70], rcx
0x180067719  lea     rcx, [rdx+0Bh]
0x18006771d  mov     [rbp+27h+var_64], esi
0x180067720  mov     [rbp+27h+var_78], 8
0x180067728  mov     [rbp+27h+var_88], 8
0x180067730  movzx   eax, word ptr [rax]
0x180067733  mov     [rsp+110h+var_B0.Size], eax
0x180067737  movzx   eax, word ptr [rcx]
0x18006773a  mov     [rbp+27h+var_98], eax
0x18006773d  lea     rax, _TraceLoggingMetadataEnd
0x180067744  mov     [rbp+27h+var_A0], rcx
0x180067748  lea     rcx, _TraceLoggingMetadata
0x18006774f  sub     eax, ecx
0x180067751  mov     dword ptr [rbp+27h+var_B0.0Ch], 2
0x180067758  mov     ecx, cs:_tls_index
0x18006775e  mov     [rbp+27h+var_94], 1
0x180067765  mov     [rsp+110h+var_CC], eax
0x180067769  mov     eax, [rsp+110h+var_CC]
0x18006776d  mov     rax, gs:58h
0x180067776  mov     edx, 8
0x18006777b  mov     rax, [rax+rcx*8]
0x18006777f  cmp     [rdx+rax], sil
0x180067783  jnz     short loc_1800677BC
0x180067785  mov     ecx, 20000019h
0x18006778a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180067791  nop     dword ptr [rax+rax+00h]
0x180067796  test    al, al
0x180067798  jz      loc_1800678D8
0x18006779e  mov     eax, cs:dword_1801675C4
0x1800677a4  mov     [rsp+110h+var_D0], 1
0x1800677a9  cmp     eax, 2
0x1800677ac  jz      short loc_180067820
0x1800677ae  cmp     eax, 1
0x1800677b1  setz    cl
0x1800677b4  test    cl, cl
0x1800677b6  jnz     loc_1800678D8
0x1800677bc  mov     rcx, cs:RegHandle; RegHandle
0x1800677c3  lea     rax, [rsp+110h+var_B0]
0x1800677c8  mov     [rsp+110h+UserData], rax; UserData
0x1800677cd  lea     rdx, [rsp+110h+EventDescriptor]; EventDescriptor
0x1800677d2  mov     [rsp+110h+UserDataCount], 8; UserDataCount
0x1800677da  mov     r9d, edi; Flags
0x1800677dd  mov     [rsp+110h+RelatedActivityId], rsi; RelatedActivityId
0x1800677e2  xor     r8d, r8d; Filter
0x1800677e5  mov     [rsp+110h+ActivityId], rsi; ActivityId
0x1800677ea  call    cs:__imp_EventWriteEx
0x1800677f1  nop     dword ptr [rax+rax+00h]
0x1800677f6  mov     rcx, [rbp+27h+var_30]
0x1800677fa  xor     rcx, rsp; StackCookie
0x1800677fd  call    __security_check_cookie
0x180067802  add     rsp, 0F8h
0x180067809  pop     rdi
0x18006780a  pop     rsi
0x18006780b  pop     rbx
0x18006780c  pop     rbp
0x18006780d  retn
0x18006780f  lea     rcx, pszFormat
0x180067816  mov     eax, 2
0x18006781b  jmp     loc_1800676D9
0x180067820  mov     ecx, 1000002Dh
0x180067825  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18006782c  nop     dword ptr [rax+rax+00h]
0x180067831  mov     ecx, 20000002h
0x180067836  mov     ebx, eax
0x180067838  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18006783f  nop     dword ptr [rax+rax+00h]
0x180067844  test    al, al
0x180067846  jz      short loc_180067884
0x180067848  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x18006784f  nop     dword ptr [rax+rax+00h]
0x180067854  test    al, al
0x180067856  jnz     short loc_180067861
0x180067858  mov     cl, [rsp+110h+var_D0]
0x18006785c  jmp     loc_1800677B4
0x180067861  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x180067868  nop     dword ptr [rax+rax+00h]
0x18006786d  movzx   ecx, al
0x180067870  cmp     ebx, 3
0x180067873  jz      loc_1800677B4
0x180067879  mov     cs:dword_1801675C4, ecx
0x18006787f  jmp     loc_1800677B4
0x180067884  cmp     ebx, 2
0x180067887  jnz     short loc_180067848
0x180067889  mov     ecx, 10000038h
0x18006788e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180067895  nop     dword ptr [rax+rax+00h]
0x18006789a  test    al, al
0x18006789c  jnz     short loc_1800678C5
0x18006789e  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x1800678a5  nop     dword ptr [rax+rax+00h]
0x1800678aa  mov     r8, rax
0x1800678ad  lea     rdx, [rsp+110h+var_D0]
0x1800678b2  mov     rcx, [rax]
0x1800678b5  mov     rax, [rcx+78h]
0x1800678b9  mov     rcx, r8
0x1800678bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800678c1  test    eax, eax
0x1800678c3  jns     short loc_180067858
0x1800678c5  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x1800678cc  nop     dword ptr [rax+rax+00h]
0x1800678d1  mov     cl, al
0x1800678d3  jmp     loc_1800677B4
0x1800678d8  mov     edi, 2
0x1800678dd  jmp     loc_1800677BC
```
