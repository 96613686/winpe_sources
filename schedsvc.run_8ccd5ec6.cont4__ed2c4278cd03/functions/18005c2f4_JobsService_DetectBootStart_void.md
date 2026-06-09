# JobsService::DetectBootStart(void)

- ea: `0x18005c2f4`
- end: `0x18005c39a`
- name: `?DetectBootStart@JobsService@@AEAAJXZ`
- size: `166`
- prototype: `__int64 __fastcall(JobsService *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800519e0`

## callees

- `0x180024730`
- `0x180054c80`
- `0x18005c2f4`
- `0x180070838`
- `0x180070978`
- `0x180070a68`
- `0x18007e310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005c33e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005c33e`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18005c318`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18005c318`

## string_xrefs

- `0x18005c30f`: `Global\SC_AutoStartComplete`

## pseudocode

```c
__int64 __fastcall JobsService::DetectBootStart(JobsService *this)
{
  HANDLE v2; // rax
  int v3; // edx
  tsched *v4; // rcx
  unsigned int LastHrError; // edi
  HANDLE v7; // [rsp+30h] [rbp+8h] BYREF

  *(_WORD *)((char *)this + 129) = 257;
  v2 = OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
  v7 = v2;
  if ( v2 )
  {
    LastHrError = 0;
    *((_BYTE *)this + 129) = WaitForSingleObject(v2, 0)
                          || (unsigned int)JobStore::IsOOBEInProgress()
                          || (unsigned int)JobStore::IsSystemSetupInProgress()
                          || (unsigned int)JobStore::IsWinPESetupInProgress()
                          || (unsigned int)IsSystemUpgradeInProgress();
  }
  else
  {
    LastHrError = tsched::GetLastHrError(v4, v3);
  }
  wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)&v7);
  return LastHrError;
}

```

## disassembly

```asm
0x18005c2f4  mov     [rsp+arg_8], rbx
0x18005c2f9  push    rdi
0x18005c2fa  sub     rsp, 20h
0x18005c2fe  mov     rbx, rcx
0x18005c301  mov     word ptr [rcx+81h], 101h
0x18005c30a  mov     ecx, 100000h; dwDesiredAccess
0x18005c30f  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x18005c316  xor     edx, edx; bInheritHandle
0x18005c318  call    cs:__imp_OpenEventW
0x18005c31f  nop     dword ptr [rax+rax+00h]
0x18005c324  mov     [rsp+28h+arg_0], rax
0x18005c329  test    rax, rax
0x18005c32c  jnz     short loc_18005C337
0x18005c32e  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18005c333  mov     edi, eax
0x18005c335  jmp     short loc_18005C382
0x18005c337  xor     edx, edx; dwMilliseconds
0x18005c339  mov     rcx, rax; hHandle
0x18005c33c  xor     edi, edi
0x18005c33e  call    cs:__imp_WaitForSingleObject
0x18005c345  nop     dword ptr [rax+rax+00h]
0x18005c34a  test    eax, eax
0x18005c34c  jnz     short loc_18005C37B
0x18005c34e  call    ?IsOOBEInProgress@JobStore@@SAHXZ; JobStore::IsOOBEInProgress(void)
0x18005c353  test    eax, eax
0x18005c355  jnz     short loc_18005C37B
0x18005c357  call    ?IsSystemSetupInProgress@JobStore@@SAHXZ; JobStore::IsSystemSetupInProgress(void)
0x18005c35c  test    eax, eax
0x18005c35e  jnz     short loc_18005C37B
0x18005c360  call    ?IsWinPESetupInProgress@JobStore@@SAHXZ; JobStore::IsWinPESetupInProgress(void)
0x18005c365  test    eax, eax
0x18005c367  jnz     short loc_18005C37B
0x18005c369  call    IsSystemUpgradeInProgress
0x18005c36e  test    eax, eax
0x18005c370  jnz     short loc_18005C37B
0x18005c372  mov     [rbx+81h], dil
0x18005c379  jmp     short loc_18005C382
0x18005c37b  mov     byte ptr [rbx+81h], 1
0x18005c382  lea     rcx, [rsp+28h+arg_0]; this
0x18005c387  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18005c38c  mov     rbx, [rsp+28h+arg_8]
0x18005c391  mov     eax, edi
0x18005c393  add     rsp, 20h
0x18005c397  pop     rdi
0x18005c398  retn
```
