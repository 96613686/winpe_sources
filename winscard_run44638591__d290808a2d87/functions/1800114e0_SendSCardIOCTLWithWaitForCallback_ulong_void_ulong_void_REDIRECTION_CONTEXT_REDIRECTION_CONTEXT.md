# _SendSCardIOCTLWithWaitForCallback(ulong,void *,ulong,void (*)(_REDIRECTION_CONTEXT *),_REDIRECTION_CONTEXT *)

- ea: `0x1800114e0`
- end: `0x180011754`
- name: `?_SendSCardIOCTLWithWaitForCallback@@YAJKPEAXKP6AXPEAU_REDIRECTION_CONTEXT@@@Z1@Z`
- size: `628`
- prototype: `__int64 __usercall@<rax>(ULONG IoControlCode@<ecx>, void *@<rdx>, unsigned int@<r8d>, void (*)(struct _REDIRECTION_CONTEXT *)@<r9>, struct _REDIRECTION_CONTEXT *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180016d20`
- `0x18002e010`

## callees

- `0x180007bc0`
- `0x18000f860`
- `0x1800114e0`
- `0x180017b70`
- `0x18001991c`
- `0x180020d68`
- `0x18002e3a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180011614`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180011614`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800115a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800115a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800116fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800116fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800115c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800115c1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800116e9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800116e9`
- `ntdll!NtDeviceIoControlFile` at `0x180011665`
- `ntdll!NtDeviceIoControlFile` at `0x180011665`
- `ntdll!RtlDllShutdownInProgress` at `0x180011503`
- `ntdll!RtlDllShutdownInProgress` at `0x180011503`

## pseudocode

```c
__int64 __fastcall _SendSCardIOCTLWithWaitForCallback(
        ULONG IoControlCode,
        void *a2,
        ULONG a3,
        void (*a4)(struct _REDIRECTION_CONTEXT *),
        struct _REDIRECTION_CONTEXT *lpCriticalSection)
{
  __int64 v7; // rcx
  int v8; // r9d
  int v10; // r9d
  unsigned int RdpdrHandle; // ebx
  __int64 v12; // rcx
  int v13; // r9d
  NTSTATUS v14; // eax
  __int64 v15; // rcx
  int v16; // r9d
  __int64 v17; // rcx
  int v18; // r8d
  int v19; // r9d

  if ( RtlDllShutdownInProgress() )
  {
    WppTraceIndent(v7, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids,
        v8,
        IoControlCode);
    }
    return 3221225760LL;
  }
  else
  {
    WppTraceIndent(v7, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids,
        v10,
        IoControlCode);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
    RdpdrHandle = RedirectionContextCreateRdpdrHandle((LPCRITICAL_SECTION)lpCriticalSection);
    if ( !RdpdrHandle )
    {
      if ( WaitForSingleObject(*((HANDLE *)lpCriticalSection + 7), 0) )
      {
        ResetEvent(*((HANDLE *)lpCriticalSection + 21));
        v14 = NtDeviceIoControlFile(
                *((HANDLE *)lpCriticalSection + 10),
                *((HANDLE *)lpCriticalSection + 21),
                0,
                0,
                (PIO_STATUS_BLOCK)((char *)lpCriticalSection + 200),
                IoControlCode,
                a2,
                a3,
                (char *)lpCriticalSection + 216,
                0x100u);
        RdpdrHandle = v14;
        if ( v14 == 259 )
        {
          WppTraceIndent(v15, 2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              20,
              (unsigned int)WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids,
              v16,
              IoControlCode);
          }
          RdpdrHandle = RedirectionContextSetupAsynchIO(lpCriticalSection, a4);
          if ( !RdpdrHandle )
          {
            RdpdrHandle = 259;
            RedirectionContextAddRef((LPCRITICAL_SECTION)lpCriticalSection);
          }
        }
        else if ( v14 )
        {
          SetEvent(*((HANDLE *)lpCriticalSection + 21));
          *((_DWORD *)lpCriticalSection + 118) = 0;
        }
        else
        {
          *((_DWORD *)lpCriticalSection + 118) = *((_DWORD *)lpCriticalSection + 52);
        }
      }
      else
      {
        WppTraceIndent(v12, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            (unsigned int)WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids,
            v13,
            IoControlCode);
        }
        RdpdrHandle = -1073741536;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
    WppTraceIndent(v17, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sld(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v18, v19, IoControlCode, RdpdrHandle);
    }
    return RdpdrHandle;
  }
}

```

## disassembly

```asm
0x1800114e0  mov     rax, rsp
0x1800114e3  mov     [rax+8], rbx
0x1800114e7  mov     [rax+20h], rdi
0x1800114eb  mov     [rax+18h], r8d
0x1800114ef  mov     [rax+10h], rdx
0x1800114f3  push    r12
0x1800114f5  push    r13
0x1800114f7  push    r15
0x1800114f9  sub     rsp, 50h
0x1800114fd  mov     r13, r9
0x180011500  mov     r12d, ecx
0x180011503  call    cs:__imp_RtlDllShutdownInProgress
0x180011509  mov     edx, 2
0x18001150e  test    al, al
0x180011510  jz      short loc_18001155A
0x180011512  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180011517  mov     rcx, cs:WPP_GLOBAL_Control
0x18001151e  lea     r15, WPP_GLOBAL_Control
0x180011525  cmp     rcx, r15
0x180011528  jz      short loc_180011550
0x18001152a  test    byte ptr [rcx+1Ch], 8
0x18001152e  jz      short loc_180011550
0x180011530  cmp     byte ptr [rcx+19h], 4
0x180011534  jb      short loc_180011550
0x180011536  mov     rcx, [rcx+10h]
0x18001153a  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x180011541  mov     edx, 11h
0x180011546  mov     dword ptr [rsp+68h+IoStatusBlock], r12d
0x18001154b  call    WPP_SF_sd
0x180011550  mov     eax, 0C0000120h
0x180011555  jmp     loc_18001173D
0x18001155a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001155f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011566  lea     r15, WPP_GLOBAL_Control
0x18001156d  cmp     rcx, r15
0x180011570  jz      short loc_180011598
0x180011572  test    byte ptr [rcx+1Ch], 8
0x180011576  jz      short loc_180011598
0x180011578  cmp     byte ptr [rcx+19h], 4
0x18001157c  jb      short loc_180011598
0x18001157e  mov     rcx, [rcx+10h]
0x180011582  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x180011589  mov     edx, 12h
0x18001158e  mov     dword ptr [rsp+68h+IoStatusBlock], r12d
0x180011593  call    WPP_SF_sd
0x180011598  mov     rdi, [rsp+68h+lpCriticalSection]
0x1800115a0  mov     rcx, rdi; lpCriticalSection
0x1800115a3  call    cs:__imp_EnterCriticalSection
0x1800115a9  mov     rcx, rdi; lpCriticalSection
0x1800115ac  call    ?RedirectionContextCreateRdpdrHandle@@YAJPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextCreateRdpdrHandle(_REDIRECTION_CONTEXT *)
0x1800115b1  mov     ebx, eax
0x1800115b3  test    eax, eax
0x1800115b5  jnz     loc_1800116F9
0x1800115bb  mov     rcx, [rdi+38h]; hHandle
0x1800115bf  xor     edx, edx; dwMilliseconds
0x1800115c1  call    cs:__imp_WaitForSingleObject
0x1800115c7  test    eax, eax
0x1800115c9  jnz     short loc_18001160D
0x1800115cb  lea     edx, [rbx+2]
0x1800115ce  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800115d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115da  cmp     rcx, r15
0x1800115dd  jz      short loc_180011603
0x1800115df  test    byte ptr [rcx+1Ch], 8
0x1800115e3  jz      short loc_180011603
0x1800115e5  cmp     byte ptr [rcx+19h], 4
0x1800115e9  jb      short loc_180011603
0x1800115eb  mov     rcx, [rcx+10h]
0x1800115ef  lea     edx, [rbx+13h]
0x1800115f2  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x1800115f9  mov     dword ptr [rsp+68h+IoStatusBlock], r12d
0x1800115fe  call    WPP_SF_sd
0x180011603  mov     ebx, 0C0000120h
0x180011608  jmp     loc_1800116F9
0x18001160d  mov     rcx, [rdi+0A8h]; hEvent
0x180011614  call    cs:__imp_ResetEvent
0x18001161a  mov     rdx, [rdi+0A8h]; Event
0x180011621  lea     rax, [rdi+0D8h]
0x180011628  mov     [rsp+68h+OutputBufferLength], 100h; OutputBufferLength
0x180011630  lea     rcx, [rdi+0C8h]
0x180011637  mov     [rsp+68h+OutputBuffer], rax; OutputBuffer
0x18001163c  xor     r9d, r9d; ApcContext
0x18001163f  mov     eax, [rsp+68h+arg_10]
0x180011646  xor     r8d, r8d; ApcRoutine
0x180011649  mov     [rsp+68h+InputBufferLength], eax; InputBufferLength
0x18001164d  mov     rax, [rsp+68h+arg_8]
0x180011652  mov     [rsp+68h+InputBuffer], rax; InputBuffer
0x180011657  mov     [rsp+68h+IoControlCode], r12d; IoControlCode
0x18001165c  mov     [rsp+68h+IoStatusBlock], rcx; IoStatusBlock
0x180011661  mov     rcx, [rdi+50h]; FileHandle
0x180011665  call    cs:__imp_NtDeviceIoControlFile
0x18001166b  mov     ebx, eax
0x18001166d  cmp     eax, 103h
0x180011672  jnz     short loc_1800116D0
0x180011674  mov     edx, 2
0x180011679  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001167e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011685  cmp     rcx, r15
0x180011688  jz      short loc_1800116B0
0x18001168a  test    byte ptr [rcx+1Ch], 8
0x18001168e  jz      short loc_1800116B0
0x180011690  cmp     byte ptr [rcx+19h], 4
0x180011694  jb      short loc_1800116B0
0x180011696  mov     rcx, [rcx+10h]
0x18001169a  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x1800116a1  mov     edx, 14h
0x1800116a6  mov     dword ptr [rsp+68h+IoStatusBlock], r12d
0x1800116ab  call    WPP_SF_sd
0x1800116b0  mov     rdx, r13; void (*)(struct _REDIRECTION_CONTEXT *)
0x1800116b3  mov     rcx, rdi; struct _REDIRECTION_CONTEXT *
0x1800116b6  call    ?RedirectionContextSetupAsynchIO@@YAJPEAU_REDIRECTION_CONTEXT@@P6AX0@Z@Z; RedirectionContextSetupAsynchIO(_REDIRECTION_CONTEXT *,void (*)(_REDIRECTION_CONTEXT *))
0x1800116bb  mov     ebx, eax
0x1800116bd  test    eax, eax
0x1800116bf  jnz     short loc_1800116F9
0x1800116c1  mov     rcx, rdi; lpCriticalSection
0x1800116c4  mov     ebx, 103h
0x1800116c9  call    ?RedirectionContextAddRef@@YAXPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextAddRef(_REDIRECTION_CONTEXT *)
0x1800116ce  jmp     short loc_1800116F9
0x1800116d0  test    eax, eax
0x1800116d2  jnz     short loc_1800116E2
0x1800116d4  mov     eax, [rdi+0D0h]
0x1800116da  mov     [rdi+1D8h], eax
0x1800116e0  jmp     short loc_1800116F9
0x1800116e2  mov     rcx, [rdi+0A8h]; hEvent
0x1800116e9  call    cs:__imp_SetEvent
0x1800116ef  mov     dword ptr [rdi+1D8h], 0
0x1800116f9  mov     rcx, rdi; lpCriticalSection
0x1800116fc  call    cs:__imp_LeaveCriticalSection
0x180011702  mov     edx, 2
0x180011707  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001170c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011713  cmp     rcx, r15
0x180011716  jz      short loc_18001173B
0x180011718  test    byte ptr [rcx+1Ch], 8
0x18001171c  jz      short loc_18001173B
0x18001171e  cmp     byte ptr [rcx+19h], 4
0x180011722  jb      short loc_18001173B
0x180011724  mov     rcx, [rcx+10h]
0x180011728  mov     edx, 15h
0x18001172d  mov     [rsp+68h+IoControlCode], ebx
0x180011731  mov     dword ptr [rsp+68h+IoStatusBlock], r12d
0x180011736  call    WPP_SF_sld
0x18001173b  mov     eax, ebx
0x18001173d  lea     r11, [rsp+68h+var_18]
0x180011742  mov     rbx, [r11+20h]
0x180011746  mov     rdi, [r11+38h]
0x18001174a  mov     rsp, r11
0x18001174d  pop     r15
0x18001174f  pop     r13
0x180011751  pop     r12
0x180011753  retn
```
