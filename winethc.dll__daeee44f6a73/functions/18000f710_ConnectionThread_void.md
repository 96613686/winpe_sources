# ConnectionThread(void *)

- ea: `0x18000f710`
- end: `0x18000f827`
- name: `?ConnectionThread@@YAKPEAX@Z`
- size: `279`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000d8bc`
- `0x18000f710`
- `0x18000f830`
- `0x180010880`
- `0x180012db0`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x18000f761`
- `ADVAPI32!EventActivityIdControl` at `0x18000f761`

## pseudocode

```c
__int64 __fastcall ConnectionThread(unsigned int *Parameter)
{
  int v2; // eax
  const struct _GUID *v3; // r9
  GUID ActivityId; // [rsp+40h] [rbp-28h] BYREF

  if ( !Parameter || !Parameter[6] )
    return 2147942487LL;
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    *(_QWORD *)ActivityId.Data4 = *((_QWORD *)&Microsoft_Windows_Networking_ProviderId + 1);
    *(_QWORD *)&ActivityId.Data1 = Parameter;
    EventActivityIdControl(2u, &ActivityId);
  }
  v2 = ResumeImpersonate((void **)Parameter + 10);
  if ( v2 > 0 )
    v2 = (unsigned __int16)v2 | 0x80070000;
  Parameter[7] = v2;
  if ( v2 >= 0 )
    Parameter[7] = ConnectToURLUsingWinHTTP(
                     *((const WCHAR **)Parameter + 1),
                     *(_QWORD *)Parameter,
                     *((_WORD *)Parameter + 10),
                     *((_QWORD **)Parameter + 5),
                     Parameter[4],
                     (int *)Parameter + 8,
                     Parameter + 9,
                     *((_BYTE **)Parameter + 8));
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    *(_QWORD *)ActivityId.Data4 = *((_QWORD *)&Microsoft_Windows_Networking_ProviderId + 1);
    *(_QWORD *)&ActivityId.Data1 = Parameter;
    EtwEx_tidActivityInfo(Microsoft_Windows_Networking_CorrelationHandle, &ActivityStop, &ActivityId, v3, 1u);
  }
  return Parameter[7];
}

```

## disassembly

```asm
0x18000f710  push    rbx
0x18000f712  sub     rsp, 60h
0x18000f716  mov     rax, cs:__security_cookie
0x18000f71d  xor     rax, rsp
0x18000f720  mov     [rsp+68h+var_18], rax
0x18000f725  mov     rbx, rcx
0x18000f728  test    rcx, rcx
0x18000f72b  jz      loc_18000F80E
0x18000f731  cmp     dword ptr [rcx+18h], 0
0x18000f735  jz      loc_18000F80E
0x18000f73b  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18000f741  test    eax, eax
0x18000f743  jz      short loc_18000F76D
0x18000f745  movups  xmm0, cs:Microsoft_Windows_Networking_ProviderId
0x18000f74c  lea     rdx, [rsp+68h+ActivityId]; ActivityId
0x18000f751  movdqu  xmmword ptr [rsp+68h+ActivityId.Data1], xmm0
0x18000f757  mov     qword ptr [rsp+68h+ActivityId.Data1], rcx
0x18000f75c  mov     ecx, 2; ControlCode
0x18000f761  call    cs:__imp_EventActivityIdControl
0x18000f768  nop     dword ptr [rax+rax+00h]
0x18000f76d  lea     rcx, [rbx+50h]; void **
0x18000f771  call    ?ResumeImpersonate@@YAKPEAPEAX@Z; ResumeImpersonate(void * *)
0x18000f776  test    eax, eax
0x18000f778  jle     short loc_18000F782
0x18000f77a  movzx   eax, ax
0x18000f77d  or      eax, 80070000h
0x18000f782  mov     [rbx+1Ch], eax
0x18000f785  test    eax, eax
0x18000f787  js      short loc_18000F7C3
0x18000f789  mov     rax, [rbx+40h]
0x18000f78d  lea     rcx, [rbx+24h]
0x18000f791  mov     r9, [rbx+28h]
0x18000f795  lea     rdx, [rbx+20h]
0x18000f799  movzx   r8d, word ptr [rbx+14h]
0x18000f79e  mov     [rsp+68h+var_30], rax
0x18000f7a3  mov     eax, [rbx+10h]
0x18000f7a6  mov     [rsp+68h+var_38], rcx
0x18000f7ab  mov     rcx, [rbx+8]
0x18000f7af  mov     [rsp+68h+var_40], rdx
0x18000f7b4  mov     rdx, [rbx]
0x18000f7b7  mov     [rsp+68h+var_48], eax
0x18000f7bb  call    ?ConnectToURLUsingWinHTTP@@YAJPEAG0GPEAU_WINHTTP_PROXY_INFO@@W4WHCInternetScheme@@PEAW4WHCConnectionErrors@@PEAKPEAUsockaddr@@@Z; ConnectToURLUsingWinHTTP(ushort *,ushort *,ushort,_WINHTTP_PROXY_INFO *,WHCInternetScheme,WHCConnectionErrors *,ulong *,sockaddr *)
0x18000f7c0  mov     [rbx+1Ch], eax
0x18000f7c3  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18000f7c9  test    eax, eax
0x18000f7cb  jz      short loc_18000F809
0x18000f7cd  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18000f7d3  test    eax, eax
0x18000f7d5  jz      short loc_18000F809
0x18000f7d7  movups  xmm0, cs:Microsoft_Windows_Networking_ProviderId
0x18000f7de  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x18000f7e5  lea     r8, [rsp+68h+ActivityId]; struct _GUID *
0x18000f7ea  lea     rdx, ActivityStop; EventDescriptor
0x18000f7f1  mov     [rsp+68h+var_48], 1; unsigned int
0x18000f7f9  movdqu  xmmword ptr [rsp+68h+ActivityId.Data1], xmm0
0x18000f7ff  mov     qword ptr [rsp+68h+ActivityId.Data1], rbx
0x18000f804  call    ?EtwEx_tidActivityInfo@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2K@Z; EtwEx_tidActivityInfo(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,ulong)
0x18000f809  mov     eax, [rbx+1Ch]
0x18000f80c  jmp     short loc_18000F813
0x18000f80e  mov     eax, 80070057h
0x18000f813  mov     rcx, [rsp+68h+var_18]
0x18000f818  xor     rcx, rsp; StackCookie
0x18000f81b  call    __security_check_cookie
0x18000f820  add     rsp, 60h
0x18000f824  pop     rbx
0x18000f825  retn
```
