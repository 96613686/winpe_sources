# CSvcCtrlInterface::ServiceHandler(ulong,ulong,void *,void *)

- ea: `0x1800017e0`
- end: `0x18000193a`
- name: `?ServiceHandler@CSvcCtrlInterface@@CAKKKPEAX0@Z`
- size: `346`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, unsigned int *lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x1800017e0`
- `0x180001940`
- `0x180011000`
- `0x180012010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800018a9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800018a9`

## pseudocode

```c
__int64 __fastcall CSvcCtrlInterface::ServiceHandler(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        unsigned int *lpContext)
{
  int v8; // eax
  unsigned int v10; // esi
  unsigned int v11; // r9d
  DWORD v12; // r8d
  DWORD v13; // edx
  SERVICE_STATUS_HANDLE v14; // rcx
  DWORD v15; // ecx
  DWORD v16; // ebx
  _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-58h] BYREF

  if ( dwControl == 1 || dwControl == 5 )
  {
    CSvcCtrlInterface::SetServiceStatus((CSvcCtrlInterface *)lpContext, 3u, 0, (unsigned int)lpContext);
    v8 = 1;
    CSvcCtrlInterface::_fStoppedOrStopping = 1;
  }
  else
  {
    v8 = CSvcCtrlInterface::_fStoppedOrStopping;
  }
  if ( dwControl == 11 && v8 )
    return 0;
  v10 = (***((__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD, LPVOID, unsigned int *))lpContext + 1))(
          *((_QWORD *)lpContext + 1),
          dwControl,
          dwEventType,
          lpEventData,
          lpContext);
  if ( dwControl == 4 )
  {
    v12 = lpContext[6];
    v13 = lpContext[4];
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    lpContext[4] = v13;
    lpContext[6] = v12;
    if ( v13 - 2 <= 1 )
    {
      v15 = lpContext[5];
      lpContext[5] = v15 + 1;
      ServiceStatus.dwCheckPoint = v15;
      ServiceStatus.dwWaitHint = 30000;
    }
    else
    {
      lpContext[5] = 0;
      *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
    }
    ServiceStatus.dwServiceType = 48;
    ServiceStatus.dwCurrentState = v13;
    ServiceStatus.dwControlsAccepted = v12;
    *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
    v14 = (SERVICE_STATUS_HANDLE)*((_QWORD *)lpContext + 4);
    if ( v14 )
      SetServiceStatus(v14, &ServiceStatus);
  }
  else
  {
    v16 = dwControl - 2;
    if ( v16 )
    {
      if ( v16 == 1 )
        CSvcCtrlInterface::SetServiceStatus((CSvcCtrlInterface *)lpContext, 4u, lpContext[6], v11);
    }
    else
    {
      CSvcCtrlInterface::SetServiceStatus((CSvcCtrlInterface *)lpContext, 7u, lpContext[6], v11);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800017e0  push    rbx
0x1800017e2  push    rsi
0x1800017e3  push    rdi
0x1800017e4  push    r14
0x1800017e6  sub     rsp, 78h
0x1800017ea  mov     rax, cs:__security_cookie
0x1800017f1  xor     rax, rsp
0x1800017f4  mov     [rsp+98h+var_38], rax
0x1800017f9  mov     rdi, r9
0x1800017fc  mov     r14, r8
0x1800017ff  mov     esi, edx
0x180001801  mov     ebx, ecx
0x180001803  mov     eax, ecx
0x180001805  sub     eax, 1
0x180001808  jz      loc_18000191A
0x18000180e  cmp     eax, 4
0x180001811  jz      loc_18000191A
0x180001817  mov     eax, cs:?_fStoppedOrStopping@CSvcCtrlInterface@@0HA; int CSvcCtrlInterface::_fStoppedOrStopping
0x18000181d  cmp     ebx, 0Bh
0x180001820  jnz     short loc_18000182D
0x180001822  test    eax, eax
0x180001824  jz      short loc_18000182D
0x180001826  xor     eax, eax
0x180001828  jmp     loc_180001903
0x18000182d  mov     rcx, [rdi+8]
0x180001831  mov     rax, [rcx]
0x180001834  mov     [rsp+98h+var_78], rdi
0x180001839  mov     r9, r14
0x18000183c  mov     r8d, esi
0x18000183f  mov     edx, ebx
0x180001841  mov     rax, [rax]
0x180001844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001849  mov     esi, eax
0x18000184b  mov     [rsp+98h+var_68], eax
0x18000184f  cmp     ebx, 4
0x180001852  jnz     short loc_1800018C8
0x180001854  mov     r8d, [rdi+18h]
0x180001858  mov     edx, [rdi+10h]
0x18000185b  xorps   xmm0, xmm0
0x18000185e  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x180001863  movups  xmmword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], xmm0
0x180001868  mov     [rdi+10h], edx
0x18000186b  mov     [rdi+18h], r8d
0x18000186f  lea     eax, [rdx-2]
0x180001872  cmp     eax, 1
0x180001875  jbe     short loc_1800018B1
0x180001877  xor     eax, eax
0x180001879  mov     [rdi+14h], eax
0x18000187c  mov     qword ptr [rsp+98h+ServiceStatus.dwCheckPoint], rax
0x180001881  mov     [rsp+98h+ServiceStatus.dwServiceType], 30h ; '0'
0x180001889  mov     [rsp+98h+ServiceStatus.dwCurrentState], edx
0x18000188d  mov     [rsp+98h+ServiceStatus.dwControlsAccepted], r8d
0x180001892  mov     qword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], 0
0x18000189b  mov     rcx, [rdi+20h]; hServiceStatus
0x18000189f  test    rcx, rcx
0x1800018a2  jz      short loc_1800018F6
0x1800018a4  lea     rdx, [rsp+98h+ServiceStatus]; lpServiceStatus
0x1800018a9  call    cs:__imp_SetServiceStatus
0x1800018af  jmp     short loc_1800018F6
0x1800018b1  mov     ecx, [rdi+14h]
0x1800018b4  lea     eax, [rcx+1]
0x1800018b7  mov     [rdi+14h], eax
0x1800018ba  mov     [rsp+98h+ServiceStatus.dwCheckPoint], ecx
0x1800018be  mov     [rsp+98h+ServiceStatus.dwWaitHint], 7530h
0x1800018c6  jmp     short loc_180001881
0x1800018c8  sub     ebx, 2
0x1800018cb  jz      short loc_1800018E5
0x1800018cd  cmp     ebx, 1
0x1800018d0  jnz     short loc_1800018F6
0x1800018d2  mov     r8d, [rdi+18h]; unsigned int
0x1800018d6  mov     edx, 4; unsigned int
0x1800018db  mov     rcx, rdi; this
0x1800018de  call    ?SetServiceStatus@CSvcCtrlInterface@@QEAAXKKK@Z; CSvcCtrlInterface::SetServiceStatus(ulong,ulong,ulong)
0x1800018e3  jmp     short loc_1800018F6
0x1800018e5  mov     r8d, [rdi+18h]; unsigned int
0x1800018e9  mov     edx, 7; unsigned int
0x1800018ee  mov     rcx, rdi; this
0x1800018f1  call    ?SetServiceStatus@CSvcCtrlInterface@@QEAAXKKK@Z; CSvcCtrlInterface::SetServiceStatus(ulong,ulong,ulong)
0x1800018f6  jmp     short loc_180001901
0x1800018f8  mov     esi, 428h
0x1800018fd  mov     [rsp+98h+var_68], esi
0x180001901  mov     eax, esi
0x180001903  mov     rcx, [rsp+98h+var_38]
0x180001908  xor     rcx, rsp; StackCookie
0x18000190b  call    __security_check_cookie
0x180001910  add     rsp, 78h
0x180001914  pop     r14
0x180001916  pop     rdi
0x180001917  pop     rsi
0x180001918  pop     rbx
0x180001919  retn
0x18000191a  xor     r8d, r8d; unsigned int
0x18000191d  mov     edx, 3; unsigned int
0x180001922  mov     rcx, rdi; this
0x180001925  call    ?SetServiceStatus@CSvcCtrlInterface@@QEAAXKKK@Z; CSvcCtrlInterface::SetServiceStatus(ulong,ulong,ulong)
0x18000192a  mov     eax, 1
0x18000192f  mov     cs:?_fStoppedOrStopping@CSvcCtrlInterface@@0HA, eax; int CSvcCtrlInterface::_fStoppedOrStopping
0x180001935  jmp     loc_18000181D
0x180011150  push    rbp
0x180011152  sub     rsp, 30h
0x180011156  mov     rbp, rdx
0x180011159  mov     eax, 1
0x18001115e  add     rsp, 30h
0x180011162  pop     rbp
0x180011163  retn
```
