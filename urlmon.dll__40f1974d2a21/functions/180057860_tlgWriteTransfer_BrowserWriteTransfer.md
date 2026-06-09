# _tlgWriteTransfer_BrowserWriteTransfer

- ea: `0x180057860`
- end: `0x180057a3d`
- name: `_tlgWriteTransfer_BrowserWriteTransfer`
- size: `477`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `25`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001008`
- `0x180001b70`
- `0x180001c1c`
- `0x180001d3c`
- `0x180001dfc`
- `0x180001e98`
- `0x180001f30`
- `0x180001f94`
- `0x180002048`
- `0x18000236c`
- `0x1800026c0`
- `0x180002770`
- `0x1800461d0`
- `0x180057510`
- `0x18005758c`
- `0x180057680`
- `0x180057754`
- `0x18007a210`
- `0x1800836a0`
- `0x180092990`
- `0x180092e90`
- `0x180093b00`
- `0x180094ea0`
- `0x180098360`
- `0x180113118`

## callees

- `0x180057860`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1800579c0`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1800579c0`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x1800579a9`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x1800579a9`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x1800579f3`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180057a25`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x1800579f3`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180057a25`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005790e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005799f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800579e9`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005790e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18005799f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1800579e9`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180057991`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180057991`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180057a01`
- `iertutil!__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ` at `0x180057a01`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180057970`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteEx` at `0x180057970`

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
  unsigned __int16 *v12; // rdx
  int v13; // ecx
  int DWORD; // r15d
  struct IEdgeBrowsingEnvironment *EdgeBrowsingEnvironment; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-28h] BYREF

  UserData = a6;
  v8 = 0;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v11 = *(_QWORD *)(a2 + 3);
  v12 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v11;
  a6->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData[1].Ptr = (ULONGLONG)v12;
  UserData->Reserved = 2;
  UserData[1].Size = *v12;
  UserData[1].Reserved = 1;
  LODWORD(a6) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  if ( !*(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL) )
  {
    if ( !(unsigned __int8)IEConfiguration_GetBool(536870937) )
      goto LABEL_17;
    LOBYTE(a6) = 1;
    if ( dword_18015A4CC != 2 )
    {
      LOBYTE(v13) = dword_18015A4CC == 1;
      goto LABEL_5;
    }
    DWORD = IEConfiguration_GetDWORD(268435501);
    if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
    {
      if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
      {
        v13 = LCIEIsCurrentProcessInPrivate();
        if ( DWORD != 3 )
          dword_18015A4CC = v13;
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
0x180057860  mov     [rsp+arg_8], rbx
0x180057865  mov     [rsp+arg_10], rbp
0x18005786a  push    rsi
0x18005786b  push    rdi
0x18005786c  push    r14
0x18005786e  sub     rsp, 50h
0x180057872  movzx   eax, byte ptr [rdx]
0x180057875  mov     rdi, rcx
0x180057878  mov     rbx, [rsp+68h+arg_28]
0x180057880  xor     esi, esi
0x180057882  shl     eax, 18h
0x180057885  mov     rbp, r9
0x180057888  mov     dword ptr [rsp+68h+EventDescriptor.Id], eax
0x18005788c  mov     r14, r8
0x18005788f  movzx   eax, word ptr [rdx+1]
0x180057893  mov     dword ptr [rsp+68h+EventDescriptor.Level], eax
0x180057897  mov     rax, [rdx+3]
0x18005789b  add     rdx, 0Bh
0x18005789f  mov     [rsp+68h+EventDescriptor.Keyword], rax
0x1800578a4  mov     rax, [rcx+8]
0x1800578a8  mov     [rbx], rax
0x1800578ab  mov     rax, [rcx+8]
0x1800578af  movzx   ecx, word ptr [rax]
0x1800578b2  mov     [rbx+8], ecx
0x1800578b5  lea     rcx, _TraceLoggingMetadata
0x1800578bc  mov     [rbx+10h], rdx
0x1800578c0  mov     dword ptr [rbx+0Ch], 2
0x1800578c7  movzx   eax, word ptr [rdx]
0x1800578ca  mov     [rbx+18h], eax
0x1800578cd  lea     rax, _TraceLoggingMetadataEnd
0x1800578d4  sub     eax, ecx
0x1800578d6  mov     dword ptr [rbx+1Ch], 1
0x1800578dd  mov     ecx, cs:_tls_index
0x1800578e3  mov     dword ptr [rsp+68h+arg_28], eax
0x1800578ea  mov     eax, dword ptr [rsp+68h+arg_28]
0x1800578f1  mov     rax, gs:58h
0x1800578fa  mov     edx, 8
0x1800578ff  mov     rax, [rax+rcx*8]
0x180057903  cmp     [rdx+rax], sil
0x180057907  jnz     short loc_180057947
0x180057909  mov     ecx, 20000019h
0x18005790e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180057914  test    al, al
0x180057916  jz      loc_180057A33
0x18005791c  mov     eax, cs:dword_18015A4CC
0x180057922  mov     [rsp+68h+arg_0], r15
0x180057927  mov     byte ptr [rsp+68h+arg_28], 1
0x18005792f  cmp     eax, 2
0x180057932  jz      short loc_18005798C
0x180057934  cmp     eax, 1
0x180057937  setz    cl
0x18005793a  mov     r15, [rsp+68h+arg_0]
0x18005793f  test    cl, cl
0x180057941  jnz     loc_180057A33
0x180057947  mov     eax, [rsp+68h+arg_20]
0x18005794e  lea     rdx, [rsp+68h+EventDescriptor]; EventDescriptor
0x180057953  mov     rcx, [rdi+20h]; RegHandle
0x180057957  mov     r9d, esi; Flags
0x18005795a  mov     [rsp+68h+UserData], rbx; UserData
0x18005795f  xor     r8d, r8d; Filter
0x180057962  mov     [rsp+68h+UserDataCount], eax; UserDataCount
0x180057966  mov     [rsp+68h+RelatedActivityId], rbp; RelatedActivityId
0x18005796b  mov     [rsp+68h+ActivityId], r14; ActivityId
0x180057970  call    cs:__imp_EventWriteEx
0x180057976  mov     rbx, [rsp+68h+arg_8]
0x18005797b  mov     rbp, [rsp+68h+arg_10]
0x180057983  add     rsp, 50h
0x180057987  pop     r14
0x180057989  pop     rdi
0x18005798a  pop     rsi
0x18005798b  retn
0x18005798c  mov     ecx, 1000002Dh
0x180057991  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180057997  mov     ecx, 20000002h
0x18005799c  mov     r15d, eax
0x18005799f  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800579a5  test    al, al
0x1800579a7  jz      short loc_1800579DE
0x1800579a9  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x1800579af  test    al, al
0x1800579b1  jnz     short loc_1800579C0
0x1800579b3  movzx   ecx, byte ptr [rsp+68h+arg_28]
0x1800579bb  jmp     loc_18005793A
0x1800579c0  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x1800579c6  movzx   ecx, al
0x1800579c9  cmp     r15d, 3
0x1800579cd  jz      loc_18005793A
0x1800579d3  mov     cs:dword_18015A4CC, ecx
0x1800579d9  jmp     loc_18005793A
0x1800579de  cmp     r15d, 2
0x1800579e2  jnz     short loc_1800579A9
0x1800579e4  mov     ecx, 10000038h
0x1800579e9  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800579ef  test    al, al
0x1800579f1  jz      short loc_180057A01
0x1800579f3  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x1800579f9  movzx   ecx, al
0x1800579fc  jmp     loc_18005793A
0x180057a01  call    cs:__imp_?GetEdgeBrowsingEnvironment@@YAPEAUIEdgeBrowsingEnvironment@@XZ; GetEdgeBrowsingEnvironment(void)
0x180057a07  mov     r8, rax
0x180057a0a  lea     rdx, [rsp+68h+arg_28]
0x180057a12  mov     rcx, [rax]
0x180057a15  mov     rax, [rcx+78h]
0x180057a19  mov     rcx, r8
0x180057a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a21  test    eax, eax
0x180057a23  jns     short loc_1800579B3
0x180057a25  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x180057a2b  movzx   ecx, al
0x180057a2e  jmp     loc_18005793A
0x180057a33  mov     esi, 2
0x180057a38  jmp     loc_180057947
```
