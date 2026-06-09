# CSimpleRegistryWatcher::StopUpdateWatcher(void)

- ea: `0x1800896b0`
- end: `0x18008983a`
- name: `?StopUpdateWatcher@CSimpleRegistryWatcher@@IEAAJXZ`
- size: `394`
- prototype: `__int64 __fastcall(CSimpleRegistryWatcher *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180074d30`
- `0x180088eac`

## callees

- `0x1800105a4`
- `0x1800896b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180089712`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180089712`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800896d3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800896d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800897ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800897ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089781`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008978f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008979d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800897ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800897b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089781`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008978f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008979d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800897ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800897b9`
- `KERNEL32!TerminateThread` at `0x18008974e`
- `KERNEL32!TerminateThread` at `0x18008974e`

## pseudocode

```c
__int64 __fastcall CSimpleRegistryWatcher::StopUpdateWatcher(HANDLE *this)
{
  unsigned int v1; // edi
  signed int LastError; // eax

  v1 = 0;
  if ( this[1] )
  {
    if ( !SetEvent(this[3]) && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids);
    if ( WaitForSingleObject(this[1], 0xFAu) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids);
      v1 = -2147418113;
      if ( !TerminateThread(this[1], 0)
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids);
      }
    }
    if ( !CloseHandle(this[2])
      || !CloseHandle(this[3])
      || !CloseHandle(this[4])
      || !CloseHandle(this[5])
      || !CloseHandle(this[1]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids);
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
    }
    this[1] = 0;
    this[2] = 0;
    this[3] = 0;
    this[4] = 0;
    this[5] = 0;
  }
  return v1;
}

```

## disassembly

```asm
0x1800896b0  mov     [rsp+arg_0], rbx
0x1800896b5  mov     [rsp+arg_8], rdi
0x1800896ba  push    r14
0x1800896bc  sub     rsp, 20h
0x1800896c0  xor     edi, edi
0x1800896c2  mov     rbx, rcx
0x1800896c5  cmp     [rcx+8], rdi
0x1800896c9  jz      loc_180089827
0x1800896cf  mov     rcx, [rcx+18h]; hEvent
0x1800896d3  call    cs:__imp_SetEvent
0x1800896d9  lea     r14, WPP_GLOBAL_Control
0x1800896e0  test    eax, eax
0x1800896e2  jnz     short loc_180089709
0x1800896e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800896eb  cmp     rcx, r14
0x1800896ee  jz      short loc_180089709
0x1800896f0  cmp     byte ptr [rcx+19h], 2
0x1800896f4  jb      short loc_180089709
0x1800896f6  mov     rcx, [rcx+10h]
0x1800896fa  lea     edx, [rdi+15h]
0x1800896fd  lea     r8, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids
0x180089704  call    WPP_SF_
0x180089709  mov     rcx, [rbx+8]; hHandle
0x18008970d  mov     edx, 0FAh; dwMilliseconds
0x180089712  call    cs:__imp_WaitForSingleObject
0x180089718  test    eax, eax
0x18008971a  jz      short loc_18008977D
0x18008971c  mov     rcx, cs:WPP_GLOBAL_Control
0x180089723  cmp     rcx, r14
0x180089726  jz      short loc_180089743
0x180089728  cmp     byte ptr [rcx+19h], 2
0x18008972c  jb      short loc_180089743
0x18008972e  mov     rcx, [rcx+10h]
0x180089732  lea     r8, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids
0x180089739  mov     edx, 16h
0x18008973e  call    WPP_SF_
0x180089743  mov     rcx, [rbx+8]; hThread
0x180089747  xor     edx, edx; dwExitCode
0x180089749  mov     edi, 8000FFFFh
0x18008974e  call    cs:__imp_TerminateThread
0x180089754  test    eax, eax
0x180089756  jnz     short loc_18008977D
0x180089758  mov     rcx, cs:WPP_GLOBAL_Control
0x18008975f  cmp     rcx, r14
0x180089762  jz      short loc_18008977D
0x180089764  cmp     byte ptr [rcx+19h], 2
0x180089768  jb      short loc_18008977D
0x18008976a  mov     rcx, [rcx+10h]
0x18008976e  lea     edx, [rax+17h]
0x180089771  lea     r8, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids
0x180089778  call    WPP_SF_
0x18008977d  mov     rcx, [rbx+10h]; hObject
0x180089781  call    cs:__imp_CloseHandle
0x180089787  test    eax, eax
0x180089789  jz      short loc_1800897C3
0x18008978b  mov     rcx, [rbx+18h]; hObject
0x18008978f  call    cs:__imp_CloseHandle
0x180089795  test    eax, eax
0x180089797  jz      short loc_1800897C3
0x180089799  mov     rcx, [rbx+20h]; hObject
0x18008979d  call    cs:__imp_CloseHandle
0x1800897a3  test    eax, eax
0x1800897a5  jz      short loc_1800897C3
0x1800897a7  mov     rcx, [rbx+28h]; hObject
0x1800897ab  call    cs:__imp_CloseHandle
0x1800897b1  test    eax, eax
0x1800897b3  jz      short loc_1800897C3
0x1800897b5  mov     rcx, [rbx+8]; hObject
0x1800897b9  call    cs:__imp_CloseHandle
0x1800897bf  test    eax, eax
0x1800897c1  jnz     short loc_1800897FF
0x1800897c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800897ca  cmp     rcx, r14
0x1800897cd  jz      short loc_1800897EA
0x1800897cf  cmp     byte ptr [rcx+19h], 2
0x1800897d3  jb      short loc_1800897EA
0x1800897d5  mov     rcx, [rcx+10h]
0x1800897d9  lea     r8, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids
0x1800897e0  mov     edx, 18h
0x1800897e5  call    WPP_SF_
0x1800897ea  call    cs:__imp_GetLastError
0x1800897f0  mov     edi, eax
0x1800897f2  test    eax, eax
0x1800897f4  jle     short loc_1800897FF
0x1800897f6  movzx   edi, ax
0x1800897f9  or      edi, 80070000h
0x1800897ff  mov     qword ptr [rbx+8], 0
0x180089807  mov     qword ptr [rbx+10h], 0
0x18008980f  mov     qword ptr [rbx+18h], 0
0x180089817  mov     qword ptr [rbx+20h], 0
0x18008981f  mov     qword ptr [rbx+28h], 0
0x180089827  mov     rbx, [rsp+28h+arg_0]
0x18008982c  mov     eax, edi
0x18008982e  mov     rdi, [rsp+28h+arg_8]
0x180089833  add     rsp, 20h
0x180089837  pop     r14
0x180089839  retn
```
