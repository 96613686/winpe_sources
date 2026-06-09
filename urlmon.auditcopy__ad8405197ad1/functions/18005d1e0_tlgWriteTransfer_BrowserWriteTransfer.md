# _tlgWriteTransfer_BrowserWriteTransfer

- ea: `0x18005d1e0`
- end: `0x18005d3fe`
- name: `_tlgWriteTransfer_BrowserWriteTransfer`
- size: `542`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `24`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001008`
- `0x180001b84`
- `0x180001c34`
- `0x180001d54`
- `0x180001e14`
- `0x180001eb0`
- `0x180001f4c`
- `0x180001fb4`
- `0x180002068`
- `0x18000238c`
- `0x1800026e4`
- `0x180002798`
- `0x18000eca0`
- `0x1800113b0`
- `0x18005ce90`
- `0x18005cf0c`
- `0x18005d000`
- `0x18005d0d4`
- `0x180098e50`
- `0x180099360`
- `0x18009a0c0`
- `0x18009b550`
- `0x18009ebd0`
- `0x18011f3dc`

## callees

- `0x18005d1e0`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18005d35f`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18005d35f`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x18005d342`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x18005d342`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x18005d39e`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x18005d3e0`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x18005d39e`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x18005d3e0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005d28e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005d332`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005d38e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005d28e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005d332`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005d38e`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18005d31e`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18005d31e`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18005d3b2`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x18005d3b2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18005d2f6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x18005d2f6`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_BrowserWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR a6)
{
  PEVENT_DATA_DESCRIPTOR UserData; // rbx
  ULONG v8; // esi
  ULONGLONG v11; // rax
  unsigned __int8 *v12; // rdx
  int v13; // ecx
  int DWORD; // r15d
  struct IEdgeBrowsingEnvironment *EdgeBrowsingEnvironment; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-28h] BYREF

  UserData = a6;
  v8 = 0;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v11 = *(_QWORD *)(a2 + 3);
  v12 = a2 + 11;
  EventDescriptor.Keyword = v11;
  a6->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData[1].Ptr = (ULONGLONG)v12;
  UserData->Reserved = 2;
  UserData[1].Size = *(unsigned __int16 *)v12;
  UserData[1].Reserved = 1;
  LODWORD(a6) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  if ( !*(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL) )
  {
    if ( !(unsigned __int8)IEConfiguration_GetBool(536870937) )
      goto LABEL_17;
    LOBYTE(a6) = 1;
    if ( dword_1801675C4 != 2 )
    {
      LOBYTE(v13) = dword_1801675C4 == 1;
      goto LABEL_5;
    }
    DWORD = IEConfiguration_GetDWORD(268435501);
    if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
    {
      if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
      {
        v13 = LCIEIsCurrentProcessInPrivate();
        if ( DWORD != 3 )
          dword_1801675C4 = v13;
LABEL_5:
        if ( !(_BYTE)v13 )
          return EventWriteEx(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, v8, a3, a4, UserDataCount, UserData);
LABEL_17:
        v8 = 2;
        return EventWriteEx(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, v8, a3, a4, UserDataCount, UserData);
      }
    }
    else if ( (unsigned __int8)IEConfiguration_GetBool(268435512)
           || (EdgeBrowsingEnvironment = GetEdgeBrowsingEnvironment(),
               (*(int (__fastcall **)(struct IEdgeBrowsingEnvironment *, PEVENT_DATA_DESCRIPTOR *))(*(_QWORD *)EdgeBrowsingEnvironment
                                                                                                  + 120LL))(
                 EdgeBrowsingEnvironment,
                 &a6) < 0) )
    {
      LOBYTE(v13) = LCIEIsCurrentProcessUsingInPrivateComponents();
      goto LABEL_5;
    }
    LOBYTE(v13) = (_BYTE)a6;
    goto LABEL_5;
  }
  return EventWriteEx(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, v8, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18005d1e0  mov     [rsp+arg_8], rbx
0x18005d1e5  mov     [rsp+arg_10], rbp
0x18005d1ea  push    rsi
0x18005d1eb  push    rdi
0x18005d1ec  push    r14
0x18005d1ee  sub     rsp, 50h
0x18005d1f2  movzx   eax, byte ptr [rdx]
0x18005d1f5  mov     rdi, rcx
0x18005d1f8  mov     rbx, [rsp+68h+arg_28]
0x18005d200  xor     esi, esi
0x18005d202  shl     eax, 18h
0x18005d205  mov     rbp, r9
0x18005d208  mov     dword ptr [rsp+68h+EventDescriptor.Id], eax
0x18005d20c  mov     r14, r8
0x18005d20f  movzx   eax, word ptr [rdx+1]
0x18005d213  mov     dword ptr [rsp+68h+EventDescriptor.Level], eax
0x18005d217  mov     rax, [rdx+3]
0x18005d21b  add     rdx, 0Bh
0x18005d21f  mov     [rsp+68h+EventDescriptor.Keyword], rax
0x18005d224  mov     rax, [rcx+8]
0x18005d228  mov     [rbx], rax
0x18005d22b  mov     rax, [rcx+8]
0x18005d22f  movzx   ecx, word ptr [rax]
0x18005d232  mov     [rbx+8], ecx
0x18005d235  lea     rcx, _TraceLoggingMetadata
0x18005d23c  mov     [rbx+10h], rdx
0x18005d240  mov     dword ptr [rbx+0Ch], 2
0x18005d247  movzx   eax, word ptr [rdx]
0x18005d24a  mov     [rbx+18h], eax
0x18005d24d  lea     rax, _TraceLoggingMetadataEnd
0x18005d254  sub     eax, ecx
0x18005d256  mov     dword ptr [rbx+1Ch], 1
0x18005d25d  mov     ecx, cs:_tls_index
0x18005d263  mov     dword ptr [rsp+68h+arg_28], eax
0x18005d26a  mov     eax, dword ptr [rsp+68h+arg_28]
0x18005d271  mov     rax, gs:58h
0x18005d27a  mov     edx, 8
0x18005d27f  mov     rax, [rax+rcx*8]
0x18005d283  cmp     [rdx+rax], sil
0x18005d287  jnz     short loc_18005D2CD
0x18005d289  mov     ecx, 20000019h
0x18005d28e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005d295  nop     dword ptr [rax+rax+00h]
0x18005d29a  test    al, al
0x18005d29c  jz      loc_18005D3F4
0x18005d2a2  mov     eax, cs:dword_1801675C4
0x18005d2a8  mov     [rsp+68h+arg_0], r15
0x18005d2ad  mov     byte ptr [rsp+68h+arg_28], 1
0x18005d2b5  cmp     eax, 2
0x18005d2b8  jz      short loc_18005D319
0x18005d2ba  cmp     eax, 1
0x18005d2bd  setz    cl
0x18005d2c0  mov     r15, [rsp+68h+arg_0]
0x18005d2c5  test    cl, cl
0x18005d2c7  jnz     loc_18005D3F4
0x18005d2cd  mov     eax, [rsp+68h+arg_20]
0x18005d2d4  lea     rdx, [rsp+68h+EventDescriptor]; EventDescriptor
0x18005d2d9  mov     rcx, [rdi+20h]; RegHandle
0x18005d2dd  mov     r9d, esi; Flags
0x18005d2e0  mov     [rsp+68h+UserData], rbx; UserData
0x18005d2e5  xor     r8d, r8d; Filter
0x18005d2e8  mov     [rsp+68h+UserDataCount], eax; UserDataCount
0x18005d2ec  mov     [rsp+68h+RelatedActivityId], rbp; RelatedActivityId
0x18005d2f1  mov     [rsp+68h+ActivityId], r14; ActivityId
0x18005d2f6  call    cs:__imp_EventWriteEx
0x18005d2fd  nop     dword ptr [rax+rax+00h]
0x18005d302  mov     rbx, [rsp+68h+arg_8]
0x18005d307  mov     rbp, [rsp+68h+arg_10]
0x18005d30f  add     rsp, 50h
0x18005d313  pop     r14
0x18005d315  pop     rdi
0x18005d316  pop     rsi
0x18005d317  retn
0x18005d319  mov     ecx, 1000002Dh
0x18005d31e  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18005d325  nop     dword ptr [rax+rax+00h]
0x18005d32a  mov     ecx, 20000002h
0x18005d32f  mov     r15d, eax
0x18005d332  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005d339  nop     dword ptr [rax+rax+00h]
0x18005d33e  test    al, al
0x18005d340  jz      short loc_18005D383
0x18005d342  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x18005d349  nop     dword ptr [rax+rax+00h]
0x18005d34e  test    al, al
0x18005d350  jnz     short loc_18005D35F
0x18005d352  movzx   ecx, byte ptr [rsp+68h+arg_28]
0x18005d35a  jmp     loc_18005D2C0
0x18005d35f  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x18005d366  nop     dword ptr [rax+rax+00h]
0x18005d36b  movzx   ecx, al
0x18005d36e  cmp     r15d, 3
0x18005d372  jz      loc_18005D2C0
0x18005d378  mov     cs:dword_1801675C4, ecx
0x18005d37e  jmp     loc_18005D2C0
0x18005d383  cmp     r15d, 2
0x18005d387  jnz     short loc_18005D342
0x18005d389  mov     ecx, 10000038h
0x18005d38e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18005d395  nop     dword ptr [rax+rax+00h]
0x18005d39a  test    al, al
0x18005d39c  jz      short loc_18005D3B2
0x18005d39e  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x18005d3a5  nop     dword ptr [rax+rax+00h]
0x18005d3aa  movzx   ecx, al
0x18005d3ad  jmp     loc_18005D2C0
0x18005d3b2  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x18005d3b9  nop     dword ptr [rax+rax+00h]
0x18005d3be  mov     r8, rax
0x18005d3c1  lea     rdx, [rsp+68h+arg_28]
0x18005d3c9  mov     rcx, [rax]
0x18005d3cc  mov     rax, [rcx+78h]
0x18005d3d0  mov     rcx, r8
0x18005d3d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3d8  test    eax, eax
0x18005d3da  jns     loc_18005D352
0x18005d3e0  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x18005d3e7  nop     dword ptr [rax+rax+00h]
0x18005d3ec  movzx   ecx, al
0x18005d3ef  jmp     loc_18005D2C0
0x18005d3f4  mov     esi, 2
0x18005d3f9  jmp     loc_18005D2CD
```
