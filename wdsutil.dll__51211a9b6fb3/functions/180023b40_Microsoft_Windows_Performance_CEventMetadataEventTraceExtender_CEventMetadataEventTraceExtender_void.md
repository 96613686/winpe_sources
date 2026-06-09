# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(void)

- ea: `0x180023b40`
- end: `0x180023cf5`
- name: `??0CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `437`
- prototype: `Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024dc0`

## callees

- `0x18001e0a8`
- `0x180023b40`
- `0x180028384`
- `0x1800283d0`
- `0x180034010`

## string_xrefs

- `0x180023bc2`: `tdh.dll`
- `0x180023bb7`: `api-ms-win-eventing-tdh-l1-1-0.dll`
- `0x180023c5a`: `ext-ms-win-eventing-tdh-ext-l1-1-0.dll`
- `0x180023cb4`: `TdhLoadManifestFromBinary`

## pseudocode

```c
Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)
{
  __int64 v2; // rcx

  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::`vftable';
  *((_BYTE *)this + 32) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 5) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::_Buyheadnode(this);
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = L"api-ms-win-eventing-tdh-l1-1-0.dll";
  *((_QWORD *)this + 17) = L"tdh.dll";
  *((_BYTE *)this + 144) = 0;
  *((_QWORD *)this + 19) = (char *)this + 120;
  *((_QWORD *)this + 20) = "TdhQueryProviderFieldInformation";
  *((_QWORD *)this + 21) = 0;
  *((_BYTE *)this + 176) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 26) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>>>::_Buyheadnode(v2);
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = L"api-ms-win-eventing-tdh-l1-1-0.dll";
  *((_QWORD *)this + 30) = L"tdh.dll";
  *((_BYTE *)this + 248) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = L"ext-ms-win-eventing-tdh-ext-l1-1-0.dll";
  *((_QWORD *)this + 34) = L"tdh.dll";
  *((_BYTE *)this + 280) = 0;
  *((_QWORD *)this + 36) = (char *)this + 224;
  *((_QWORD *)this + 37) = "TdhGetEventInformation";
  *((_QWORD *)this + 38) = 0;
  *((_BYTE *)this + 312) = 0;
  *((_QWORD *)this + 40) = (char *)this + 224;
  *((_QWORD *)this + 41) = "TdhGetEventMapInformation";
  *((_QWORD *)this + 42) = 0;
  *((_BYTE *)this + 344) = 0;
  *((_QWORD *)this + 44) = (char *)this + 256;
  *((_QWORD *)this + 45) = "TdhLoadManifestFromBinary";
  *((_QWORD *)this + 46) = 0;
  *((_BYTE *)this + 376) = 0;
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 288) )
    *((_BYTE *)this + 32) = 1;
  return this;
}

```

## disassembly

```asm
0x180023b40  mov     rax, rsp
0x180023b43  mov     [rax+8], rcx
0x180023b47  push    rsi
0x180023b48  push    rdi
0x180023b49  push    r14
0x180023b4b  sub     rsp, 30h
0x180023b4f  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180023b57  mov     [rax+18h], rbx
0x180023b5b  mov     [rax+20h], rbp
0x180023b5f  mov     rdi, rcx
0x180023b62  xor     r14d, r14d
0x180023b65  mov     [rcx+18h], r14d
0x180023b69  mov     [rcx+8], r14
0x180023b6d  mov     [rcx+10h], r14
0x180023b71  lea     rax, ??_7CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::`vftable'
0x180023b78  mov     [rcx], rax
0x180023b7b  mov     [rcx+20h], r14b
0x180023b7f  mov     [rcx+28h], r14
0x180023b83  mov     [rcx+30h], r14
0x180023b87  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::_Buyheadnode(void)
0x180023b8c  mov     [rdi+28h], rax
0x180023b90  mov     [rdi+38h], r14
0x180023b94  mov     [rdi+40h], r14d
0x180023b98  mov     [rdi+48h], r14
0x180023b9c  mov     [rdi+50h], r14d
0x180023ba0  mov     [rdi+58h], r14
0x180023ba4  mov     [rdi+60h], r14d
0x180023ba8  mov     [rdi+68h], r14
0x180023bac  mov     [rdi+70h], r14
0x180023bb0  lea     rax, [rdi+78h]
0x180023bb4  mov     [rax], r14
0x180023bb7  lea     rsi, aApiMsWinEventi; "api-ms-win-eventing-tdh-l1-1-0.dll"
0x180023bbe  mov     [rax+8], rsi
0x180023bc2  lea     rbp, aTdhDll; "tdh.dll"
0x180023bc9  mov     [rax+10h], rbp
0x180023bcd  mov     [rax+18h], r14b
0x180023bd1  mov     [rdi+98h], rax
0x180023bd8  lea     rax, aTdhqueryprovid; "TdhQueryProviderFieldInformation"
0x180023bdf  mov     [rdi+0A0h], rax
0x180023be6  mov     [rdi+0A8h], r14
0x180023bed  mov     [rdi+0B0h], r14b
0x180023bf4  mov     [rdi+0B8h], r14
0x180023bfb  mov     [rdi+0C0h], r14
0x180023c02  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180023c09  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180023c10  mov     rax, [rax+18h]
0x180023c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c19  add     rax, 18h
0x180023c1d  mov     [rdi+0C8h], rax
0x180023c24  lea     rbx, [rdi+0D0h]
0x180023c2b  mov     [rbx], r14
0x180023c2e  mov     [rbx+8], r14
0x180023c32  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBU_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>>>::_Buyheadnode(void)
0x180023c37  mov     [rbx], rax
0x180023c3a  lea     rdx, [rdi+0E0h]
0x180023c41  mov     [rdx], r14
0x180023c44  mov     [rdx+8], rsi
0x180023c48  mov     [rdx+10h], rbp
0x180023c4c  mov     [rdx+18h], r14b
0x180023c50  lea     rax, [rdi+100h]
0x180023c57  mov     [rax], r14
0x180023c5a  lea     rcx, aExtMsWinEventi; "ext-ms-win-eventing-tdh-ext-l1-1-0.dll"
0x180023c61  mov     [rax+8], rcx
0x180023c65  mov     [rax+10h], rbp
0x180023c69  mov     [rax+18h], r14b
0x180023c6d  lea     rcx, [rdi+120h]
0x180023c74  mov     [rcx], rdx
0x180023c77  lea     r8, aTdhgeteventinf; "TdhGetEventInformation"
0x180023c7e  mov     [rcx+8], r8
0x180023c82  mov     [rcx+10h], r14
0x180023c86  mov     [rcx+18h], r14b
0x180023c8a  mov     [rdi+140h], rdx
0x180023c91  lea     rdx, aTdhgeteventmap; "TdhGetEventMapInformation"
0x180023c98  mov     [rdi+148h], rdx
0x180023c9f  mov     [rdi+150h], r14
0x180023ca6  mov     [rdi+158h], r14b
0x180023cad  mov     [rdi+160h], rax
0x180023cb4  lea     rax, aTdhloadmanifes_0; "TdhLoadManifestFromBinary"
0x180023cbb  mov     [rdi+168h], rax
0x180023cc2  mov     [rdi+170h], r14
0x180023cc9  mov     [rdi+178h], r14b
0x180023cd0  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180023cd5  test    rax, rax
0x180023cd8  jnz     short loc_180023CDE
0x180023cda  mov     byte ptr [rdi+20h], 1
0x180023cde  mov     rax, rdi
0x180023ce1  mov     rbx, [rsp+48h+arg_10]
0x180023ce6  mov     rbp, [rsp+48h+arg_18]
0x180023ceb  add     rsp, 30h
0x180023cef  pop     r14
0x180023cf1  pop     rdi
0x180023cf2  pop     rsi
0x180023cf3  retn
```
