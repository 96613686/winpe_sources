# CPxeRogueDetection::UpdateSettings(void)

- ea: `0x1800104f4`
- end: `0x1800105fa`
- name: `?UpdateSettings@CPxeRogueDetection@@QEAAKXZ`
- size: `262`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180003050`

## callees

- `0x18000d13c`
- `0x18000f8b8`
- `0x1800104f4`
- `0x180010f8c`
- `0x180011068`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010556`
- `KERNEL32!GetLastError` at `0x180010556`
- `KERNEL32!EnterCriticalSection` at `0x180010506`
- `KERNEL32!EnterCriticalSection` at `0x180010506`
- `KERNEL32!LeaveCriticalSection` at `0x1800105db`
- `KERNEL32!LeaveCriticalSection` at `0x1800105db`
- `KERNEL32!SetEvent` at `0x180010534`
- `KERNEL32!SetEvent` at `0x180010534`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180010598`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800105bb`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180010598`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800105bb`

## pseudocode

```c
__int64 __fastcall CPxeRogueDetection::UpdateSettings(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int Parameters; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  DWORD LastError; // edi
  BOOL v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  LONG v9; // esi

  EnterCriticalSection(lpCriticalSection);
  Parameters = CPxeRogueDetection::ReadParameters(lpCriticalSection);
  LastError = ElValidateWin32_4(Parameters, v3, v4, 473);
  if ( !LastError )
  {
    v6 = SetEvent(lpCriticalSection[6].LockSemaphore);
    if ( (unsigned int)ElValidateGleTrue_0(!v6, v7, v8, 481) )
      LastError = GetLastError();
  }
  v9 = LastError != 0;
  if ( HIDWORD(lpCriticalSection[1].LockSemaphore) != v9 )
  {
    if ( !HIDWORD(lpCriticalSection[1].LockSemaphore) && LastError )
    {
      HIDWORD(lpCriticalSection[1].LockSemaphore) = v9;
      CEventLog::Log((CEventLog *)qword_18001CC40, 0xC1070306, 1);
LABEL_10:
      CPxeRogueDetection::SetAuthState((CPxeRogueDetection *)lpCriticalSection, 0);
      goto LABEL_11;
    }
    HIDWORD(lpCriticalSection[1].LockSemaphore) = v9;
    CEventLog::Log((CEventLog *)qword_18001CC40, 0x41070307u, 0, 0);
  }
  if ( LastError )
    goto LABEL_10;
LABEL_11:
  lpCriticalSection[1].LockCount = v9;
  LeaveCriticalSection(lpCriticalSection);
  return LastError;
}

```

## disassembly

```asm
0x1800104f4  mov     [rsp+arg_0], rbx
0x1800104f9  mov     [rsp+arg_8], rsi
0x1800104fe  push    rdi
0x1800104ff  sub     rsp, 30h
0x180010503  mov     rbx, rcx
0x180010506  call    cs:__imp_EnterCriticalSection
0x18001050d  nop     dword ptr [rax+rax+00h]
0x180010512  mov     rcx, rbx; lpCriticalSection
0x180010515  call    ?ReadParameters@CPxeRogueDetection@@AEAAKXZ; CPxeRogueDetection::ReadParameters(void)
0x18001051a  mov     ecx, eax
0x18001051c  mov     r9d, 1D9h
0x180010522  call    ElValidateWin32_4
0x180010527  mov     edi, eax
0x180010529  test    eax, eax
0x18001052b  jnz     short loc_180010564
0x18001052d  mov     rcx, [rbx+108h]; hEvent
0x180010534  call    cs:__imp_SetEvent
0x18001053b  nop     dword ptr [rax+rax+00h]
0x180010540  xor     ecx, ecx
0x180010542  mov     r9d, 1E1h
0x180010548  test    eax, eax
0x18001054a  setz    cl
0x18001054d  call    ElValidateGleTrue_0
0x180010552  test    eax, eax
0x180010554  jz      short loc_180010564
0x180010556  call    cs:__imp_GetLastError
0x18001055d  nop     dword ptr [rax+rax+00h]
0x180010562  mov     edi, eax
0x180010564  xor     esi, esi
0x180010566  test    edi, edi
0x180010568  setnz   sil
0x18001056c  cmp     [rbx+44h], esi
0x18001056f  jz      short loc_1800105C7
0x180010571  cmp     dword ptr [rbx+44h], 0
0x180010575  jnz     short loc_1800105A6
0x180010577  test    edi, edi
0x180010579  jz      short loc_1800105A6
0x18001057b  mov     r9d, 5
0x180010581  mov     [rbx+44h], esi
0x180010584  mov     edx, 0C1070306h
0x180010589  mov     [rsp+38h+var_18], edi
0x18001058d  lea     rcx, qword_18001CC40
0x180010594  lea     r8d, [r9-4]
0x180010598  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18001059f  nop     dword ptr [rax+rax+00h]
0x1800105a4  jmp     short loc_1800105CB
0x1800105a6  xor     r9d, r9d
0x1800105a9  mov     [rbx+44h], esi
0x1800105ac  xor     r8d, r8d
0x1800105af  lea     rcx, qword_18001CC40
0x1800105b6  mov     edx, 41070307h
0x1800105bb  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x1800105c2  nop     dword ptr [rax+rax+00h]
0x1800105c7  test    edi, edi
0x1800105c9  jz      short loc_1800105D5
0x1800105cb  xor     edx, edx; int
0x1800105cd  mov     rcx, rbx; this
0x1800105d0  call    ?SetAuthState@CPxeRogueDetection@@AEAAXH@Z; CPxeRogueDetection::SetAuthState(int)
0x1800105d5  mov     rcx, rbx; lpCriticalSection
0x1800105d8  mov     [rbx+30h], esi
0x1800105db  call    cs:__imp_LeaveCriticalSection
0x1800105e2  nop     dword ptr [rax+rax+00h]
0x1800105e7  mov     rbx, [rsp+38h+arg_0]
0x1800105ec  mov     eax, edi
0x1800105ee  mov     rsi, [rsp+38h+arg_8]
0x1800105f3  add     rsp, 30h
0x1800105f7  pop     rdi
0x1800105f8  retn
```
