# WFDSConMgr::RPC::CService::StopService(void)

- ea: `0x180006400`
- end: `0x18000650e`
- name: `?StopService@CService@RPC@WFDSConMgr@@QEAAXXZ`
- size: `270`
- prototype: `void __fastcall(WFDSConMgr::RPC::CService *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180006090`

## callees

- `0x180005224`
- `0x180006400`
- `0x180006740`
- `0x18005c888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000646d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000646d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006463`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006463`

## string_xrefs

- `0x180006490`: `onecoreuap\net\wlan\wfdsconmgr\server\src\service.cpp`
- `0x18000647f`: `SetServiceStatus failed`
- `0x180006499`: `WFDSConMgr::RPC::CService::StopService`

## pseudocode

```c
void __fastcall WFDSConMgr::RPC::CService::StopService(WFDSConMgr::RPC::CService *this)
{
  SERVICE_STATUS_HANDLE v2; // rcx
  char LastError; // al
  __int64 v4; // rdx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_75b4082a698737eb13803f331f4b6971_Traceguids, this);
  }
  v2 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 27);
  *((_DWORD *)this + 47) = 1;
  *((_DWORD *)this + 49) = 0;
  if ( !SetServiceStatus(v2, (LPSERVICE_STATUS)((char *)this + 184)) )
  {
    LastError = GetLastError();
    WFDSConMgr::CException::Throw(
      LastError,
      "WFDSConMgr::RPC::CService::StopService",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\service.cpp",
      144,
      L"SetServiceStatus failed",
      this);
  }
  *((_QWORD *)this + 27) = 0;
  v4 = *((_QWORD *)this + 29);
  *((_QWORD *)this + 29) = 0;
  if ( v4 )
    WFDSConMgr::RPC::UnregisterWaitDeleter::operator()();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_75b4082a698737eb13803f331f4b6971_Traceguids, this);
  }
}

```

## disassembly

```asm
0x180006400  mov     [rsp+arg_0], rbx
0x180006405  push    rsi
0x180006406  sub     rsp, 30h
0x18000640a  mov     rbx, rcx
0x18000640d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006414  lea     rsi, WPP_GLOBAL_Control
0x18000641b  cmp     rcx, rsi
0x18000641e  jz      short loc_180006444
0x180006420  cmp     byte ptr [rcx+19h], 3
0x180006424  jb      short loc_180006444
0x180006426  test    byte ptr [rcx+1Ch], 1
0x18000642a  jz      short loc_180006444
0x18000642c  mov     rcx, [rcx+10h]
0x180006430  lea     r8, WPP_75b4082a698737eb13803f331f4b6971_Traceguids
0x180006437  mov     edx, 22h ; '"'
0x18000643c  mov     r9, rbx
0x18000643f  call    WPP_SF_q
0x180006444  mov     rcx, [rbx+0D8h]; hServiceStatus
0x18000644b  lea     rdx, [rbx+0B8h]; lpServiceStatus
0x180006452  mov     dword ptr [rdx+4], 1
0x180006459  mov     dword ptr [rbx+0C4h], 0
0x180006463  call    cs:__imp_SetServiceStatus
0x180006469  test    eax, eax
0x18000646b  jnz     short loc_1800064AC
0x18000646d  call    cs:__imp_GetLastError
0x180006473  test    eax, eax
0x180006475  jle     short loc_18000647F
0x180006477  movzx   eax, ax
0x18000647a  or      eax, 80070000h
0x18000647f  lea     rcx, aSetservicestat; "SetServiceStatus failed"
0x180006486  mov     [rsp+38h+var_10], rbx; void *
0x18000648b  mov     [rsp+38h+var_18], rcx; unsigned __int16 *
0x180006490  lea     r8, aOnecoreuapNetW_28; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x180006497  mov     ecx, eax; char
0x180006499  lea     rdx, aWfdsconmgrRpcC_7; "WFDSConMgr::RPC::CService::StopService"
0x1800064a0  mov     r9d, 190h; char
0x1800064a6  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800064ac  mov     qword ptr [rbx+0D8h], 0
0x1800064b7  mov     rdx, [rbx+0E8h]
0x1800064be  mov     qword ptr [rbx+0E8h], 0
0x1800064c9  test    rdx, rdx
0x1800064cc  jz      short loc_1800064D3
0x1800064ce  call    ??RUnregisterWaitDeleter@RPC@WFDSConMgr@@QEAAXPEAX@Z; WFDSConMgr::RPC::UnregisterWaitDeleter::operator()(void *)
0x1800064d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064da  cmp     rcx, rsi
0x1800064dd  jz      short loc_180006503
0x1800064df  cmp     byte ptr [rcx+19h], 3
0x1800064e3  jb      short loc_180006503
0x1800064e5  test    byte ptr [rcx+1Ch], 1
0x1800064e9  jz      short loc_180006503
0x1800064eb  mov     rcx, [rcx+10h]
0x1800064ef  lea     r8, WPP_75b4082a698737eb13803f331f4b6971_Traceguids
0x1800064f6  mov     edx, 23h ; '#'
0x1800064fb  mov     r9, rbx
0x1800064fe  call    WPP_SF_q
0x180006503  mov     rbx, [rsp+38h+arg_0]
0x180006508  add     rsp, 30h
0x18000650c  pop     rsi
0x18000650d  retn
```
