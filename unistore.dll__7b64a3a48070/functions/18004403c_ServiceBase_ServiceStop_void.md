# ServiceBase::ServiceStop(void)

- ea: `0x18004403c`
- end: `0x18004410d`
- name: `?ServiceStop@ServiceBase@@QEAAXXZ`
- size: `209`
- prototype: `void __fastcall(ServiceBase *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180044030`
- `0x18007397c`

## callees

- `0x180043ddc`
- `0x18004403c`
- `0x180044550`
- `0x1800c3db0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044106`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x180044081`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x180044081`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800440b0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800440b0`

## pseudocode

```c
void __fastcall ServiceBase::ServiceStop(ServiceBase *this)
{
  __int64 v2; // rax
  __int64 v3; // rax

  if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context,
      ServiceBaseServiceShuttingDown,
      (char *)this + 8);
  if ( *((_DWORD *)this + 31) )
  {
    (*(void (__fastcall **)(ServiceBase *, _QWORD))(*(_QWORD *)this + 16LL))(this, *((unsigned int *)this + 33));
    if ( *((_DWORD *)this + 33) )
      ServiceBase::_SetShutdownRegistryKey(this);
  }
  ServiceBase::_ServiceUnInit(this);
  CoFreeUnusedLibrariesEx(0x7530u, 0);
  v2 = *(_QWORD *)this;
  *((_DWORD *)this + 25) = 1;
  *((_DWORD *)this + 29) = 0;
  if ( (*(unsigned int (__fastcall **)(ServiceBase *))(v2 + 80))(this) )
  {
    v3 = *(_QWORD *)this;
    *((_DWORD *)this + 27) = 1066;
    *((_DWORD *)this + 28) = (*(__int64 (__fastcall **)(ServiceBase *))(v3 + 80))(this);
  }
  if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 9), (LPSERVICE_STATUS)((char *)this + 96)) )
    GetLastError();
}

```

## disassembly

```asm
0x18004403c  push    rbx
0x18004403e  sub     rsp, 20h
0x180044042  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 8
0x180044049  mov     rbx, rcx
0x18004404c  jnz     short loc_1800440C0
0x18004404e  cmp     dword ptr [rbx+7Ch], 0
0x180044052  jz      short loc_180044072
0x180044054  mov     rax, [rbx]
0x180044057  mov     rcx, rbx
0x18004405a  mov     edx, [rbx+84h]
0x180044060  mov     rax, [rax+10h]
0x180044064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044069  cmp     dword ptr [rbx+84h], 0
0x180044070  jnz     short loc_1800440DC
0x180044072  mov     rcx, rbx; this
0x180044075  call    ?_ServiceUnInit@ServiceBase@@AEAAXXZ; ServiceBase::_ServiceUnInit(void)
0x18004407a  xor     edx, edx; dwReserved
0x18004407c  mov     ecx, 7530h; dwUnloadDelay
0x180044081  call    cs:__imp_CoFreeUnusedLibrariesEx
0x180044087  mov     rax, [rbx]
0x18004408a  mov     rcx, rbx
0x18004408d  mov     dword ptr [rbx+64h], 1
0x180044094  mov     dword ptr [rbx+74h], 0
0x18004409b  mov     rax, [rax+50h]
0x18004409f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440a4  test    eax, eax
0x1800440a6  jnz     short loc_1800440E6
0x1800440a8  mov     rcx, [rbx+48h]; hServiceStatus
0x1800440ac  lea     rdx, [rbx+60h]; lpServiceStatus
0x1800440b0  call    cs:__imp_SetServiceStatus
0x1800440b6  test    eax, eax
0x1800440b8  jz      short loc_180044101
0x1800440ba  add     rsp, 20h
0x1800440be  pop     rbx
0x1800440bf  retn
0x1800440c0  lea     r8, [rcx+8]
0x1800440c4  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context
0x1800440cb  lea     rdx, ServiceBaseServiceShuttingDown
0x1800440d2  call    McTemplateU0z_EventWriteTransfer
0x1800440d7  jmp     loc_18004404E
0x1800440dc  mov     rcx, rbx; this
0x1800440df  call    ?_SetShutdownRegistryKey@ServiceBase@@AEAAJXZ; ServiceBase::_SetShutdownRegistryKey(void)
0x1800440e4  jmp     short loc_180044072
0x1800440e6  mov     rax, [rbx]
0x1800440e9  mov     rcx, rbx
0x1800440ec  mov     dword ptr [rbx+6Ch], 42Ah
0x1800440f3  mov     rax, [rax+50h]
0x1800440f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440fc  mov     [rbx+70h], eax
0x1800440ff  jmp     short loc_1800440A8
0x180044101  add     rsp, 20h
0x180044105  pop     rbx
0x180044106  jmp     cs:__imp_GetLastError
```
