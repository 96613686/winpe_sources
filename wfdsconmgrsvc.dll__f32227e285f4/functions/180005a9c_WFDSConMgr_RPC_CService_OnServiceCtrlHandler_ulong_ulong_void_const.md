# WFDSConMgr::RPC::CService::OnServiceCtrlHandler(ulong,ulong,void const *)

- ea: `0x180005a9c`
- end: `0x180005bf4`
- name: `?OnServiceCtrlHandler@CService@RPC@WFDSConMgr@@AEAAKKKPEBX@Z`
- size: `344`
- prototype: `unsigned int __fastcall(WFDSConMgr::RPC::CService *__hidden this, unsigned int, unsigned int, const void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180005c90`

## callees

- `0x180004870`
- `0x180005a9c`
- `0x180006780`
- `0x1800067d0`
- `0x18001c048`
- `0x18003510c`
- `0x18005dd90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b34`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005b2a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005b2a`

## pseudocode

```c
__int64 __fastcall WFDSConMgr::RPC::CService::OnServiceCtrlHandler(
        WFDSConMgr::RPC::CService *this,
        int a2,
        int a3,
        const void *a4)
{
  __int64 result; // rax
  int v7; // ebx
  int v8; // ebx
  __int64 v9; // r9
  DWORD LastError; // eax
  PVOID *v11; // rcx
  WFDSConMgr::CSessionManager *Instance; // rax
  __int64 v13; // r9

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_75b4082a698737eb13803f331f4b6971_Traceguids, this, a2, a3);
  }
  result = 0;
  v7 = a2 - 1;
  if ( v7 )
  {
    v8 = v7 - 3;
    if ( !v8 )
      return result;
    if ( v8 != 1 )
      return 120;
  }
  *((_DWORD *)this + 47) = 3;
  *((_DWORD *)this + 48) = 0;
  if ( SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 27), (LPSERVICE_STATUS)((char *)this + 184)) )
    goto LABEL_14;
  LastError = GetLastError();
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( !*((_BYTE *)WPP_GLOBAL_Control + 25) || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_15:
      if ( v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 25) >= 4u && (*((_BYTE *)v11 + 28) & 1) != 0 )
        WPP_SF_(v11[2], 114, &WPP_c137473c1b033305b2005e51d766ad85_Traceguids, v9);
      goto LABEL_19;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_75b4082a698737eb13803f331f4b6971_Traceguids, this, LastError);
LABEL_14:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_15;
  }
LABEL_19:
  Instance = WFDSConMgr::CSessionManager::GetInstance();
  WFDSConMgr::CSessionManager::Shutdown(Instance);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_c137473c1b033305b2005e51d766ad85_Traceguids, v13);
  }
  WFDSConMgr::CEventWrapper::Set((WFDSConMgr::RPC::CService *)((char *)this + 240));
  return 0;
}

```

## disassembly

```asm
0x180005a9c  mov     rax, rsp
0x180005a9f  mov     [rax+8], rbx
0x180005aa3  mov     [rax+10h], rdi
0x180005aa7  push    r14
0x180005aa9  sub     rsp, 30h
0x180005aad  mov     ebx, edx
0x180005aaf  mov     rdi, rcx
0x180005ab2  lea     r14, WPP_GLOBAL_Control
0x180005ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ac0  cmp     rcx, r14
0x180005ac3  jz      short loc_180005AF0
0x180005ac5  cmp     byte ptr [rcx+19h], 4
0x180005ac9  jb      short loc_180005AF0
0x180005acb  test    byte ptr [rcx+1Ch], 1
0x180005acf  jz      short loc_180005AF0
0x180005ad1  mov     edx, 15h
0x180005ad6  mov     [rax-10h], r8d
0x180005ada  mov     [rax-18h], ebx
0x180005add  mov     r9, rdi
0x180005ae0  lea     r8, WPP_75b4082a698737eb13803f331f4b6971_Traceguids
0x180005ae7  mov     rcx, [rcx+10h]
0x180005aeb  call    WPP_SF_qDD
0x180005af0  xor     eax, eax
0x180005af2  sub     ebx, 1
0x180005af5  jz      short loc_180005B0F
0x180005af7  sub     ebx, 3
0x180005afa  jz      loc_180005BE3
0x180005b00  cmp     ebx, 1
0x180005b03  jz      short loc_180005B0F
0x180005b05  mov     eax, 78h ; 'x'
0x180005b0a  jmp     loc_180005BE3
0x180005b0f  lea     rdx, [rdi+0B8h]; lpServiceStatus
0x180005b16  mov     dword ptr [rdx+4], 3
0x180005b1d  mov     [rdi+0C0h], eax
0x180005b23  mov     rcx, [rdi+0D8h]; hServiceStatus
0x180005b2a  call    cs:__imp_SetServiceStatus
0x180005b30  test    eax, eax
0x180005b32  jnz     short loc_180005B6E
0x180005b34  call    cs:__imp_GetLastError
0x180005b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b41  cmp     rcx, r14
0x180005b44  jz      short loc_180005B9B
0x180005b46  cmp     byte ptr [rcx+19h], 1
0x180005b4a  jb      short loc_180005B75
0x180005b4c  test    byte ptr [rcx+1Ch], 1
0x180005b50  jz      short loc_180005B75
0x180005b52  mov     edx, 16h
0x180005b57  mov     [rsp+38h+var_18], eax
0x180005b5b  mov     r9, rdi
0x180005b5e  lea     r8, WPP_75b4082a698737eb13803f331f4b6971_Traceguids
0x180005b65  mov     rcx, [rcx+10h]
0x180005b69  call    WPP_SF_qD
0x180005b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b75  cmp     rcx, r14
0x180005b78  jz      short loc_180005B9B
0x180005b7a  cmp     byte ptr [rcx+19h], 4
0x180005b7e  jb      short loc_180005B9B
0x180005b80  test    byte ptr [rcx+1Ch], 1
0x180005b84  jz      short loc_180005B9B
0x180005b86  mov     edx, 72h ; 'r'
0x180005b8b  lea     r8, WPP_c137473c1b033305b2005e51d766ad85_Traceguids
0x180005b92  mov     rcx, [rcx+10h]
0x180005b96  call    WPP_SF_
0x180005b9b  call    ?GetInstance@CSessionManager@WFDSConMgr@@SAAEAV12@XZ; WFDSConMgr::CSessionManager::GetInstance(void)
0x180005ba0  mov     rcx, rax; this
0x180005ba3  call    ?Shutdown@CSessionManager@WFDSConMgr@@QEAAXXZ; WFDSConMgr::CSessionManager::Shutdown(void)
0x180005ba8  mov     rcx, cs:WPP_GLOBAL_Control
0x180005baf  cmp     rcx, r14
0x180005bb2  jz      short loc_180005BD5
0x180005bb4  cmp     byte ptr [rcx+19h], 4
0x180005bb8  jb      short loc_180005BD5
0x180005bba  test    byte ptr [rcx+1Ch], 1
0x180005bbe  jz      short loc_180005BD5
0x180005bc0  mov     edx, 73h ; 's'
0x180005bc5  lea     r8, WPP_c137473c1b033305b2005e51d766ad85_Traceguids
0x180005bcc  mov     rcx, [rcx+10h]
0x180005bd0  call    WPP_SF_
0x180005bd5  lea     rcx, [rdi+0F0h]; this
0x180005bdc  call    ?Set@CEventWrapper@WFDSConMgr@@QEAAXXZ; WFDSConMgr::CEventWrapper::Set(void)
0x180005be1  xor     eax, eax
0x180005be3  mov     rbx, [rsp+38h+arg_0]
0x180005be8  mov     rdi, [rsp+38h+arg_8]
0x180005bed  add     rsp, 30h
0x180005bf1  pop     r14
0x180005bf3  retn
```
