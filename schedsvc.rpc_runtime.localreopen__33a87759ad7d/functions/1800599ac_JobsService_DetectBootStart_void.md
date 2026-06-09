# JobsService::DetectBootStart(void)

- ea: `0x1800599ac`
- end: `0x180059a45`
- name: `?DetectBootStart@JobsService@@AEAAJXZ`
- size: `153`
- prototype: `__int64 __fastcall(JobsService *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18004f190`

## callees

- `0x180039d00`
- `0x180052584`
- `0x1800599ac`
- `0x18006d178`
- `0x18006d2a8`
- `0x18006d384`
- `0x18007a158`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800599f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800599f0`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800599d0`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800599d0`

## string_xrefs

- `0x1800599c7`: `Global\SC_AutoStartComplete`

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
0x1800599ac  mov     [rsp+arg_8], rbx
0x1800599b1  push    rdi
0x1800599b2  sub     rsp, 20h
0x1800599b6  mov     rbx, rcx
0x1800599b9  mov     word ptr [rcx+81h], 101h
0x1800599c2  mov     ecx, 100000h; dwDesiredAccess
0x1800599c7  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x1800599ce  xor     edx, edx; bInheritHandle
0x1800599d0  call    cs:__imp_OpenEventW
0x1800599d6  mov     [rsp+28h+arg_0], rax
0x1800599db  test    rax, rax
0x1800599de  jnz     short loc_1800599E9
0x1800599e0  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x1800599e5  mov     edi, eax
0x1800599e7  jmp     short loc_180059A2E
0x1800599e9  xor     edx, edx; dwMilliseconds
0x1800599eb  mov     rcx, rax; hHandle
0x1800599ee  xor     edi, edi
0x1800599f0  call    cs:__imp_WaitForSingleObject
0x1800599f6  test    eax, eax
0x1800599f8  jnz     short loc_180059A27
0x1800599fa  call    ?IsOOBEInProgress@JobStore@@SAHXZ; JobStore::IsOOBEInProgress(void)
0x1800599ff  test    eax, eax
0x180059a01  jnz     short loc_180059A27
0x180059a03  call    ?IsSystemSetupInProgress@JobStore@@SAHXZ; JobStore::IsSystemSetupInProgress(void)
0x180059a08  test    eax, eax
0x180059a0a  jnz     short loc_180059A27
0x180059a0c  call    ?IsWinPESetupInProgress@JobStore@@SAHXZ; JobStore::IsWinPESetupInProgress(void)
0x180059a11  test    eax, eax
0x180059a13  jnz     short loc_180059A27
0x180059a15  call    IsSystemUpgradeInProgress
0x180059a1a  test    eax, eax
0x180059a1c  jnz     short loc_180059A27
0x180059a1e  mov     [rbx+81h], dil
0x180059a25  jmp     short loc_180059A2E
0x180059a27  mov     byte ptr [rbx+81h], 1
0x180059a2e  lea     rcx, [rsp+28h+arg_0]; this
0x180059a33  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x180059a38  mov     rbx, [rsp+28h+arg_8]
0x180059a3d  mov     eax, edi
0x180059a3f  add     rsp, 20h
0x180059a43  pop     rdi
0x180059a44  retn
```
