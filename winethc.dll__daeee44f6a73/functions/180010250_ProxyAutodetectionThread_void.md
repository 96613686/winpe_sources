# ProxyAutodetectionThread(void *)

- ea: `0x180010250`
- end: `0x18001031d`
- name: `?ProxyAutodetectionThread@@YAKPEAX@Z`
- size: `205`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000de18`
- `0x18000f830`
- `0x180010250`
- `0x180012db0`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x18001029d`
- `ADVAPI32!EventActivityIdControl` at `0x18001029d`

## pseudocode

```c
__int64 __fastcall ProxyAutodetectionThread(unsigned int *Parameter)
{
  const struct _GUID *v3; // r9
  GUID ActivityId; // [rsp+30h] [rbp-28h] BYREF

  if ( !Parameter )
    return 2147942487LL;
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    *(_QWORD *)ActivityId.Data4 = *((_QWORD *)&Microsoft_Windows_Networking_ProviderId + 1);
    *(_QWORD *)&ActivityId.Data1 = Parameter;
    EventActivityIdControl(2u, &ActivityId);
  }
  Parameter[7] = GetAutoProxyInfo(
                   *(LPCWSTR *)Parameter,
                   *((WINHTTP_PROXY_INFO **)Parameter + 5),
                   *((WINHTTP_AUTOPROXY_OPTIONS **)Parameter + 6),
                   (int *)Parameter + 18);
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    *(_QWORD *)ActivityId.Data4 = *((_QWORD *)&Microsoft_Windows_Networking_ProviderId + 1);
    *(_QWORD *)&ActivityId.Data1 = Parameter;
    EtwEx_tidActivityInfo(Microsoft_Windows_Networking_CorrelationHandle, &ActivityStop, &ActivityId, v3, 2u);
  }
  return Parameter[7];
}

```

## disassembly

```asm
0x180010250  push    rbx
0x180010252  sub     rsp, 50h
0x180010256  mov     rax, cs:__security_cookie
0x18001025d  xor     rax, rsp
0x180010260  mov     [rsp+58h+var_18], rax
0x180010265  mov     rbx, rcx
0x180010268  test    rcx, rcx
0x18001026b  jnz     short loc_180010277
0x18001026d  mov     eax, 80070057h
0x180010272  jmp     loc_180010309
0x180010277  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18001027d  test    eax, eax
0x18001027f  jz      short loc_1800102A9
0x180010281  movups  xmm0, cs:Microsoft_Windows_Networking_ProviderId
0x180010288  lea     rdx, [rsp+58h+ActivityId]; ActivityId
0x18001028d  mov     ecx, 2; ControlCode
0x180010292  movdqu  xmmword ptr [rsp+58h+ActivityId.Data1], xmm0
0x180010298  mov     qword ptr [rsp+58h+ActivityId.Data1], rbx
0x18001029d  call    cs:__imp_EventActivityIdControl
0x1800102a4  nop     dword ptr [rax+rax+00h]
0x1800102a9  mov     r8, [rbx+30h]; pAutoProxyOptions
0x1800102ad  lea     r9, [rbx+48h]; int *
0x1800102b1  mov     rdx, [rbx+28h]; pProxyInfo
0x1800102b5  mov     rcx, [rbx]; lpcwszUrl
0x1800102b8  call    ?GetAutoProxyInfo@@YAJPEBGPEAU_WINHTTP_PROXY_INFO@@PEAU_WINHTTP_AUTOPROXY_OPTIONS@@PEAH@Z; GetAutoProxyInfo(ushort const *,_WINHTTP_PROXY_INFO *,_WINHTTP_AUTOPROXY_OPTIONS *,int *)
0x1800102bd  mov     [rbx+1Ch], eax
0x1800102c0  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1800102c6  test    eax, eax
0x1800102c8  jz      short loc_180010306
0x1800102ca  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1800102d0  test    eax, eax
0x1800102d2  jz      short loc_180010306
0x1800102d4  movups  xmm0, cs:Microsoft_Windows_Networking_ProviderId
0x1800102db  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x1800102e2  lea     r8, [rsp+58h+ActivityId]; struct _GUID *
0x1800102e7  lea     rdx, ActivityStop; EventDescriptor
0x1800102ee  mov     [rsp+58h+var_38], 2; unsigned int
0x1800102f6  movdqu  xmmword ptr [rsp+58h+ActivityId.Data1], xmm0
0x1800102fc  mov     qword ptr [rsp+58h+ActivityId.Data1], rbx
0x180010301  call    ?EtwEx_tidActivityInfo@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2K@Z; EtwEx_tidActivityInfo(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,ulong)
0x180010306  mov     eax, [rbx+1Ch]
0x180010309  mov     rcx, [rsp+58h+var_18]
0x18001030e  xor     rcx, rsp; StackCookie
0x180010311  call    __security_check_cookie
0x180010316  add     rsp, 50h
0x18001031a  pop     rbx
0x18001031b  retn
```
