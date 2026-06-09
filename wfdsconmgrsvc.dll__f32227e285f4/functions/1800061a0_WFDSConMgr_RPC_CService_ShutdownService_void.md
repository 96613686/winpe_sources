# WFDSConMgr::RPC::CService::ShutdownService(void)

- ea: `0x1800061a0`
- end: `0x18000633f`
- name: `?ShutdownService@CService@RPC@WFDSConMgr@@QEAAXXZ`
- size: `415`
- prototype: `void __fastcall(WFDSConMgr::RPC::CService *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180005d50`
- `0x180006090`
- `0x180006114`

## callees

- `0x1800059c0`
- `0x180005bfc`
- `0x1800061a0`
- `0x180006740`
- `0x18005c888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006294`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006329`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006329`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000628a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000628a`

## string_xrefs

- `0x1800062bd`: `onecoreuap\net\wlan\wfdsconmgr\server\src\service.cpp`
- `0x1800062ab`: `SetServiceStatus failed`
- `0x1800062c4`: `WFDSConMgr::RPC::CService::ShutdownService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WFDSConMgr::RPC::CService::ShutdownService(WFDSConMgr::RPC::CService *this)
{
  WFDSConMgr::RPC::CService *v1; // rbx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  char LastError; // al
  __int64 v5; // rax
  const std::exception *v6; // [rsp+30h] [rbp-18h] BYREF
  const WFDSConMgr::CException *v7; // [rsp+38h] [rbp-10h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp+10h] BYREF

  v1 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_75b4082a698737eb13803f331f4b6971_Traceguids, this);
  }
  WFDSConMgr::CriticalSection::Lock((char *)v1 + 24, &lpCriticalSection);
  if ( *((_DWORD *)v1 + 47) == 1 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_23;
    }
    v3 = 28;
    goto LABEL_22;
  }
  *((_DWORD *)v1 + 47) = 3;
  if ( *((_QWORD *)v1 + 27) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_75b4082a698737eb13803f331f4b6971_Traceguids, v1);
    }
    if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)v1 + 27), (LPSERVICE_STATUS)((char *)v1 + 184)) )
    {
      LastError = GetLastError();
      WFDSConMgr::CException::Throw(
        LastError,
        "WFDSConMgr::RPC::CService::ShutdownService",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\service.cpp",
        106,
        L"SetServiceStatus failed",
        v1);
    }
  }
  try
  {
    WFDSConMgr::RPC::CService::ServiceDeinit(v1);
  }
  catch ( std::bad_alloc )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_75b4082a698737eb13803f331f4b6971_Traceguids, this);
    }
    v1 = this;
  }
  catch ( const std::exception *v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v6 + 8LL))(v6);
      WPP_SF_qs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)WPP_75b4082a698737eb13803f331f4b6971_Traceguids,
        (_DWORD)this,
        v5);
    }
    v1 = this;
  }
  catch ( const WFDSConMgr::CException *v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_75b4082a698737eb13803f331f4b6971_Traceguids,
        this,
        *(_DWORD *)v7);
    }
    v1 = this;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v3 = 33;
LABEL_22:
    WPP_SF_q(v2[2], v3, WPP_75b4082a698737eb13803f331f4b6971_Traceguids, v1);
  }
LABEL_23:
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x1800061a0  mov     [rsp+arg_10], rbx
0x1800061a5  mov     [rsp+arg_18], rsi
0x1800061aa  mov     [rsp+arg_0], rcx
0x1800061af  push    rdi
0x1800061b0  sub     rsp, 40h
0x1800061b4  mov     rbx, rcx
0x1800061b7  lea     rdi, WPP_GLOBAL_Control
0x1800061be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061c5  cmp     rcx, rdi
0x1800061c8  jz      short loc_1800061EE
0x1800061ca  cmp     byte ptr [rcx+19h], 3
0x1800061ce  jb      short loc_1800061EE
0x1800061d0  test    byte ptr [rcx+1Ch], 1
0x1800061d4  jz      short loc_1800061EE
0x1800061d6  mov     edx, 1Bh
0x1800061db  mov     r9, rbx
0x1800061de  lea     r8, WPP_75b4082a698737eb13803f331f4b6971_Traceguids
0x1800061e5  mov     rcx, [rcx+10h]
0x1800061e9  call    WPP_SF_q
0x1800061ee  lea     rcx, [rbx+18h]
0x1800061f2  lea     rdx, [rsp+48h+lpCriticalSection]
0x1800061f7  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x1800061fc  nop
0x1800061fd  lea     rsi, [rbx+0B8h]
0x180006204  cmp     dword ptr [rsi+4], 1
0x180006208  jnz     short loc_180006238
0x18000620a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006211  cmp     rcx, rdi
0x180006214  jz      loc_18000631F
0x18000621a  cmp     byte ptr [rcx+19h], 4
0x18000621e  jb      loc_18000631F
0x180006224  test    byte ptr [rcx+1Ch], 1
0x180006228  jz      loc_18000631F
0x18000622e  mov     edx, 1Ch
0x180006233  jmp     loc_18000630B
0x180006238  mov     dword ptr [rbx+0BCh], 3
0x180006242  cmp     qword ptr [rbx+0D8h], 0
0x18000624a  jz      loc_1800062D3
0x180006250  mov     rcx, cs:WPP_GLOBAL_Control
0x180006257  cmp     rcx, rdi
0x18000625a  jz      short loc_180006280
0x18000625c  cmp     byte ptr [rcx+19h], 4
0x180006260  jb      short loc_180006280
0x180006262  test    byte ptr [rcx+1Ch], 1
0x180006266  jz      short loc_180006280
0x180006268  mov     edx, 1Dh
0x18000626d  mov     r9, rbx
0x180006270  lea     r8, WPP_75b4082a698737eb13803f331f4b6971_Traceguids
0x180006277  mov     rcx, [rcx+10h]
0x18000627b  call    WPP_SF_q
0x180006280  mov     rdx, rsi; lpServiceStatus
0x180006283  mov     rcx, [rbx+0D8h]; hServiceStatus
0x18000628a  call    cs:__imp_SetServiceStatus
0x180006290  test    eax, eax
0x180006292  jnz     short loc_1800062D3
0x180006294  call    cs:__imp_GetLastError
0x18000629a  test    eax, eax
0x18000629c  jle     short loc_1800062A6
0x18000629e  movzx   eax, ax
0x1800062a1  or      eax, 80070000h
0x1800062a6  mov     [rsp+48h+var_20], rbx; void *
0x1800062ab  lea     rcx, aSetservicestat; "SetServiceStatus failed"
0x1800062b2  mov     [rsp+48h+var_28], rcx; unsigned __int16 *
0x1800062b7  mov     r9d, 16Ah; char
0x1800062bd  lea     r8, aOnecoreuapNetW_28; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x1800062c4  lea     rdx, aWfdsconmgrRpcC_6; "WFDSConMgr::RPC::CService::ShutdownServ"...
0x1800062cb  mov     ecx, eax; char
0x1800062cd  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800062d3  mov     rcx, rbx; this
0x1800062d6  call    ?ServiceDeinit@CService@RPC@WFDSConMgr@@AEAAXXZ; WFDSConMgr::RPC::CService::ServiceDeinit(void)
0x1800062db  nop
0x1800062dc  jmp     short loc_1800062EE
0x1800062de  jmp     short loc_1800062E2
0x1800062e0  jmp     short $+2
0x1800062e2  lea     rdi, WPP_GLOBAL_Control
0x1800062e9  mov     rbx, [rsp+48h+arg_0]
0x1800062ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062f5  cmp     rcx, rdi
0x1800062f8  jz      short loc_18000631F
0x1800062fa  cmp     byte ptr [rcx+19h], 3
0x1800062fe  jb      short loc_18000631F
0x180006300  test    byte ptr [rcx+1Ch], 1
0x180006304  jz      short loc_18000631F
0x180006306  mov     edx, 21h ; '!'
0x18000630b  mov     r9, rbx
0x18000630e  lea     r8, WPP_75b4082a698737eb13803f331f4b6971_Traceguids
0x180006315  mov     rcx, [rcx+10h]
0x180006319  call    WPP_SF_q
0x18000631e  nop
0x18000631f  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x180006324  test    rcx, rcx
0x180006327  jz      short loc_18000632F
0x180006329  call    cs:__imp_LeaveCriticalSection
0x18000632f  mov     rbx, [rsp+48h+arg_10]
0x180006334  mov     rsi, [rsp+48h+arg_18]
0x180006339  add     rsp, 40h
0x18000633d  pop     rdi
0x18000633e  retn
```
