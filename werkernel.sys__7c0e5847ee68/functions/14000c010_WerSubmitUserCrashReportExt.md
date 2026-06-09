# WerSubmitUserCrashReportExt

- ea: `0x14000c010`
- end: `0x14000c55e`
- name: `WerSubmitUserCrashReportExt`
- size: `1358`
- prototype: `__int64 __fastcall(void *, __int64, __int64, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400010e0`
- `0x140001368`
- `0x1400015b0`
- `0x140002c40`
- `0x14000c010`

## import_xrefs

- `ntoskrnl!ZwUnmapViewOfSection` at `0x14000c42a`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x14000c42a`
- `ntoskrnl!DbgPrintEx` at `0x14000c0b0`
- `ntoskrnl!DbgPrintEx` at `0x14000c155`
- `ntoskrnl!DbgPrintEx` at `0x14000c1d3`
- `ntoskrnl!DbgPrintEx` at `0x14000c24f`
- `ntoskrnl!DbgPrintEx` at `0x14000c2d0`
- `ntoskrnl!DbgPrintEx` at `0x14000c485`
- `ntoskrnl!DbgPrintEx` at `0x14000c52f`
- `ntoskrnl!DbgPrintEx` at `0x14000c0b0`
- `ntoskrnl!DbgPrintEx` at `0x14000c155`
- `ntoskrnl!DbgPrintEx` at `0x14000c1d3`
- `ntoskrnl!DbgPrintEx` at `0x14000c24f`
- `ntoskrnl!DbgPrintEx` at `0x14000c2d0`
- `ntoskrnl!DbgPrintEx` at `0x14000c485`
- `ntoskrnl!DbgPrintEx` at `0x14000c52f`
- `ntoskrnl!ZwDuplicateObject` at `0x14000c134`
- `ntoskrnl!ZwDuplicateObject` at `0x14000c22e`
- `ntoskrnl!ZwDuplicateObject` at `0x14000c134`
- `ntoskrnl!ZwDuplicateObject` at `0x14000c22e`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c50c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c50c`
- `ntoskrnl!ZwCreateSection` at `0x14000c1b2`
- `ntoskrnl!ZwCreateSection` at `0x14000c1b2`
- `ntoskrnl!ObCloseHandle` at `0x14000c1eb`
- `ntoskrnl!ObCloseHandle` at `0x14000c2e3`
- `ntoskrnl!ObCloseHandle` at `0x14000c4a6`
- `ntoskrnl!ObCloseHandle` at `0x14000c4cf`
- `ntoskrnl!ObCloseHandle` at `0x14000c1eb`
- `ntoskrnl!ObCloseHandle` at `0x14000c2e3`
- `ntoskrnl!ObCloseHandle` at `0x14000c4a6`
- `ntoskrnl!ObCloseHandle` at `0x14000c4cf`
- `ntoskrnl!ZwQueryInformationThread` at `0x14000c08f`
- `ntoskrnl!ZwQueryInformationThread` at `0x14000c08f`
- `ntoskrnl!ZwMapViewOfSection` at `0x14000c2af`
- `ntoskrnl!ZwMapViewOfSection` at `0x14000c2af`
- `ntoskrnl!ZwCreateEvent` at `0x14000c0f4`
- `ntoskrnl!ZwCreateEvent` at `0x14000c0f4`
- `ntoskrnl!ZwClose` at `0x14000c166`
- `ntoskrnl!ZwClose` at `0x14000c260`
- `ntoskrnl!ZwClose` at `0x14000c4b7`
- `ntoskrnl!ZwClose` at `0x14000c166`
- `ntoskrnl!ZwClose` at `0x14000c260`
- `ntoskrnl!ZwClose` at `0x14000c4b7`

## string_xrefs

- `0x14000c0a1`: `WERKERNELHOST: WerSubmitUserCrashReportExt: ZwQueryInformationThread/ThreadBasicInformation returned NTSTATUS %08X\n`
- `0x14000c106`: `WERKERNELHOST: WerSubmitUserCrashReportExt: ZwCreateEvent returned NTSTATUS %08X\n`
- `0x14000c149`: `WERKERNELHOST: WerSubmitUserCrashReportExt: ZwDuplicateObject/CompletionEvent returned NTSTATUS %08X\n`
- `0x14000c1c7`: `WERKERNELHOST: WerSubmitUserCrashReportExt: ZwCreateSection returned NTSTATUS %08X\n`

## pseudocode

```c
__int64 __fastcall WerSubmitUserCrashReportExt(void *a1, __int64 a2, __int64 a3, int a4, int a5)
{
  int v6; // r13d
  NTSTATUS InformationThread; // edi
  NTSTATUS v9; // eax
  void *v10; // rcx
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  NTSTATUS v13; // eax
  _DWORD *v14; // rsi
  int v15; // eax
  void *EventHandle; // [rsp+50h] [rbp-98h] BYREF
  void *TargetHandle; // [rsp+58h] [rbp-90h] BYREF
  void *SectionHandle; // [rsp+60h] [rbp-88h] BYREF
  PVOID BaseAddress; // [rsp+68h] [rbp-80h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-78h] BYREF
  ULONG_PTR ViewSize[2]; // [rsp+78h] [rbp-70h] BYREF
  _OWORD v22[3]; // [rsp+88h] [rbp-60h] BYREF
  PVOID Object; // [rsp+100h] [rbp+18h] BYREF
  int v24; // [rsp+108h] [rbp+20h]

  v24 = a4;
  memset(v22, 0, 44);
  SectionHandle = 0;
  Handle = 0;
  EventHandle = 0;
  TargetHandle = 0;
  BaseAddress = 0;
  ViewSize[0] = 0;
  if ( !a3 )
  {
    v6 = a5;
    if ( (a5 & 2) != 0 )
    {
      InformationThread = ZwQueryInformationThread(a1, ThreadBasicInformation, v22, 0x30u, 0);
      if ( InformationThread < 0 )
      {
        DbgPrintEx(
          5u,
          0,
          "WERKERNELHOST: WerSubmitUserCrashReportExt: ZwQueryInformationThread/ThreadBasicInformation returned NTSTATUS %08X\n",
          (unsigned int)InformationThread);
        return (unsigned int)InformationThread;
      }
      LODWORD(Object) = v6 & 1;
      if ( (v6 & 1) != 0 )
      {
        InformationThread = ZwCreateEvent(
                              &EventHandle,
                              0x100003u,
                              (POBJECT_ATTRIBUTES)&ObjectAttributes,
                              NotificationEvent,
                              0);
        if ( InformationThread < 0 )
        {
          DbgPrintEx(
            5u,
            0,
            "WERKERNELHOST: WerSubmitUserCrashReportExt: ZwCreateEvent returned NTSTATUS %08X\n",
            (unsigned int)InformationThread);
          return (unsigned int)InformationThread;
        }
        v9 = ZwDuplicateObject(
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               EventHandle,
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               &TargetHandle,
               0x100003u,
               2u,
               8u);
        InformationThread = v9;
        if ( v9 < 0 )
        {
          DbgPrintEx(
            5u,
            0,
            "WERKERNELHOST: WerSubmitUserCrashReportExt: ZwDuplicateObject/CompletionEvent returned NTSTATUS %08X\n",
            v9);
          v10 = EventHandle;
LABEL_11:
          ZwClose(v10);
          return (unsigned int)InformationThread;
        }
      }
      else
      {
        TargetHandle = 0;
        EventHandle = 0;
      }
      v11 = ZwCreateSection(
              &SectionHandle,
              0xF0007u,
              (POBJECT_ATTRIBUTES)&ObjectAttributes,
              (PLARGE_INTEGER)&MaximumSize,
              4u,
              0x8000000u,
              0);
      InformationThread = v11;
      if ( v11 >= 0 )
      {
        v12 = ZwDuplicateObject(
                (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                SectionHandle,
                (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                &Handle,
                6u,
                2u,
                8u);
        InformationThread = v12;
        if ( v12 >= 0 )
        {
          BaseAddress = 0;
          ViewSize[0] = 0;
          v13 = ZwMapViewOfSection(
                  SectionHandle,
                  (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                  &BaseAddress,
                  0,
                  0,
                  0,
                  ViewSize,
                  ViewUnmap,
                  0,
                  4u);
          InformationThread = v13;
          if ( v13 >= 0 )
          {
            v14 = BaseAddress;
            ViewSize[1] = (ULONG_PTR)BaseAddress;
            memset(BaseAddress, 0, 0xF8u);
            *v14 = 248;
            v14[1] = v22[1];
            v14[2] = DWORD2(v22[1]);
            v14[44] = 0;
            *((_QWORD *)v14 + 23) = 0;
            *((_QWORD *)v14 + 24) = 0;
            *((_QWORD *)v14 + 25) = 0;
            *((_QWORD *)v14 + 26) = (unsigned int)TargetHandle;
            *((_QWORD *)v14 + 28) = 0;
            v14[58] = -1073741637;
            v14[59] = v24 | 0x80000000;
            v14[60] = (MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24;
            if ( a2 )
            {
              *((_OWORD *)v14 + 1) = *(_OWORD *)a2;
              *((_OWORD *)v14 + 2) = *(_OWORD *)(a2 + 16);
              *((_OWORD *)v14 + 3) = *(_OWORD *)(a2 + 32);
              *((_OWORD *)v14 + 4) = *(_OWORD *)(a2 + 48);
              *((_OWORD *)v14 + 5) = *(_OWORD *)(a2 + 64);
              *((_OWORD *)v14 + 6) = *(_OWORD *)(a2 + 80);
              *((_OWORD *)v14 + 7) = *(_OWORD *)(a2 + 96);
              *((_OWORD *)v14 + 8) = *(_OWORD *)(a2 + 112);
              *((_OWORD *)v14 + 9) = *(_OWORD *)(a2 + 128);
              *((_QWORD *)v14 + 20) = *(_QWORD *)(a2 + 144);
            }
            ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
            Object = 0;
            v15 = WerpSendWersvcMessageWERSVC_REPORT_CRASH(
                    (unsigned int)&Object,
                    (_DWORD)Handle,
                    v6,
                    v22[1],
                    (__int64)TargetHandle);
            InformationThread = v15;
            if ( v15 < 0 || v15 == 258 )
            {
              DbgPrintEx(
                5u,
                0,
                "WERKERNELHOST: WerSubmitUserCrashReportExt: WerpSendWersvcMessageWERSVC_REPORT_CRASH returned NTSTATUS %08X\n",
                v15);
              if ( InformationThread == 258 )
                InformationThread = -1073741248;
            }
            ObCloseHandle(Handle, 1);
            ZwClose(SectionHandle);
            if ( TargetHandle )
              ObCloseHandle(TargetHandle, 1);
            if ( InformationThread >= 0 && Object && (v6 & 1) != 0 )
              WerpBlockOnReporting(Object, EventHandle);
            if ( Object )
              ObfDereferenceObject(Object);
LABEL_17:
            v10 = EventHandle;
            if ( !EventHandle )
              return (unsigned int)InformationThread;
            goto LABEL_11;
          }
          DbgPrintEx(
            5u,
            0,
            "WERKERNELHOST: WerSubmitUserCrashReportExt: ZwMapViewOfSection returned NTSTATUS %08X\n",
            v13);
          ObCloseHandle(Handle, 1);
        }
        else
        {
          DbgPrintEx(
            5u,
            0,
            "WERKERNELHOST: WerSubmitUserCrashReportExt: ZwDuplicateObject/Section returned NTSTATUS %08X\n",
            v12);
        }
        ZwClose(SectionHandle);
      }
      else
      {
        DbgPrintEx(5u, 0, "WERKERNELHOST: WerSubmitUserCrashReportExt: ZwCreateSection returned NTSTATUS %08X\n", v11);
      }
      if ( TargetHandle )
        ObCloseHandle(TargetHandle, 1);
      goto LABEL_17;
    }
  }
  DbgPrintEx(5u, 0, "WERKERNELHOST: I can only handle auto-context now. Failing with NTSTATUS %08X.\n", -1073741637);
  return 3221225659LL;
}

```

## disassembly

```asm
0x14000c010  mov     r11, rsp
0x14000c013  mov     [r11+8], rbx
0x14000c017  mov     [r11+10h], rsi
0x14000c01b  mov     [r11+20h], r9d
0x14000c01f  push    rdi
0x14000c020  push    r12
0x14000c022  push    r13
0x14000c024  push    r14
0x14000c026  push    r15
0x14000c028  sub     rsp, 0C0h
0x14000c02f  mov     r15, rdx
0x14000c032  xor     eax, eax
0x14000c034  xorps   xmm0, xmm0
0x14000c037  movups  xmmword ptr [r11-60h], xmm0
0x14000c03c  movups  xmmword ptr [r11-50h], xmm0
0x14000c041  movups  xmmword ptr [r11-44h], xmm0
0x14000c046  xor     ebx, ebx
0x14000c048  mov     [rsp+0E8h+SectionHandle], rbx
0x14000c04d  mov     [r11-78h], rbx
0x14000c051  mov     [rsp+0E8h+EventHandle], rbx
0x14000c056  mov     [rsp+0E8h+TargetHandle], rbx
0x14000c05b  mov     [r11-80h], rbx
0x14000c05f  mov     [r11-70h], rbx
0x14000c063  test    r8, r8
0x14000c066  jnz     loc_14000C51D
0x14000c06c  mov     r13d, [rsp+0E8h+arg_20]
0x14000c074  lea     esi, [rax+2]
0x14000c077  test    sil, r13b
0x14000c07a  jz      loc_14000C51D
0x14000c080  mov     [rsp+0E8h+ReturnLength], rbx; ReturnLength
0x14000c085  lea     r9d, [rax+30h]; ThreadInformationLength
0x14000c089  lea     r8, [r11-60h]; ThreadInformation
0x14000c08d  xor     edx, edx; ThreadInformationClass
0x14000c08f  call    cs:__imp_ZwQueryInformationThread
0x14000c096  nop     dword ptr [rax+rax+00h]
0x14000c09b  mov     edi, eax
0x14000c09d  test    eax, eax
0x14000c09f  jns     short loc_14000C0C3
0x14000c0a1  lea     r8, aWerkernelhostW_36; "WERKERNELHOST: WerSubmitUserCrashReport"...
0x14000c0a8  mov     r9d, edi
0x14000c0ab  xor     edx, edx; Level
0x14000c0ad  lea     ecx, [rdx+5]; ComponentId
0x14000c0b0  call    cs:__imp_DbgPrintEx
0x14000c0b7  nop     dword ptr [rax+rax+00h]
0x14000c0bc  mov     eax, edi
0x14000c0be  jmp     loc_14000C540
0x14000c0c3  mov     r12d, r13d
0x14000c0c6  and     r12d, 1
0x14000c0ca  mov     dword ptr [rsp+0E8h+Object], r12d
0x14000c0d2  jz      loc_14000C177
0x14000c0d8  mov     byte ptr [rsp+0E8h+ReturnLength], bl; InitialState
0x14000c0dc  xor     r9d, r9d; EventType
0x14000c0df  lea     r8, ObjectAttributes; ObjectAttributes
0x14000c0e6  mov     r14d, 100003h
0x14000c0ec  mov     edx, r14d; DesiredAccess
0x14000c0ef  lea     rcx, [rsp+0E8h+EventHandle]; EventHandle
0x14000c0f4  call    cs:__imp_ZwCreateEvent
0x14000c0fb  nop     dword ptr [rax+rax+00h]
0x14000c100  mov     edi, eax
0x14000c102  test    eax, eax
0x14000c104  jns     short loc_14000C10F
0x14000c106  lea     r8, aWerkernelhostW_7; "WERKERNELHOST: WerSubmitUserCrashReport"...
0x14000c10d  jmp     short loc_14000C0A8
0x14000c10f  mov     [rsp+0E8h+Options], 8; Options
0x14000c117  mov     [rsp+0E8h+HandleAttributes], esi; HandleAttributes
0x14000c11b  mov     dword ptr [rsp+0E8h+ReturnLength], r14d; DesiredAccess
0x14000c120  lea     r9, [rsp+0E8h+TargetHandle]; TargetHandle
0x14000c125  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000c129  mov     r8, r14; TargetProcessHandle
0x14000c12c  mov     rdx, [rsp+0E8h+EventHandle]; SourceHandle
0x14000c131  mov     rcx, r14; SourceProcessHandle
0x14000c134  call    cs:__imp_ZwDuplicateObject
0x14000c13b  nop     dword ptr [rax+rax+00h]
0x14000c140  mov     edi, eax
0x14000c142  test    eax, eax
0x14000c144  jns     short loc_14000C185
0x14000c146  mov     r9d, eax
0x14000c149  lea     r8, aWerkernelhostW_61; "WERKERNELHOST: WerSubmitUserCrashReport"...
0x14000c150  xor     edx, edx; Level
0x14000c152  lea     ecx, [rdx+5]; ComponentId
0x14000c155  call    cs:__imp_DbgPrintEx
0x14000c15c  nop     dword ptr [rax+rax+00h]
0x14000c161  mov     rcx, [rsp+0E8h+EventHandle]; Handle
0x14000c166  call    cs:__imp_ZwClose
0x14000c16d  nop     dword ptr [rax+rax+00h]
0x14000c172  jmp     loc_14000C0BC
0x14000c177  mov     [rsp+0E8h+TargetHandle], rbx
0x14000c17c  mov     [rsp+0E8h+EventHandle], rbx
0x14000c181  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000c185  mov     qword ptr [rsp+0E8h+Options], rbx; FileHandle
0x14000c18a  mov     [rsp+0E8h+HandleAttributes], 8000000h; AllocationAttributes
0x14000c192  mov     dword ptr [rsp+0E8h+ReturnLength], 4; SectionPageProtection
0x14000c19a  lea     r9, MaximumSize; MaximumSize
0x14000c1a1  lea     r8, ObjectAttributes; ObjectAttributes
0x14000c1a8  mov     edx, 0F0007h; DesiredAccess
0x14000c1ad  lea     rcx, [rsp+0E8h+SectionHandle]; SectionHandle
0x14000c1b2  call    cs:__imp_ZwCreateSection
0x14000c1b9  nop     dword ptr [rax+rax+00h]
0x14000c1be  mov     edi, eax
0x14000c1c0  test    eax, eax
0x14000c1c2  jns     short loc_14000C20A
0x14000c1c4  mov     r9d, eax
0x14000c1c7  lea     r8, aWerkernelhostW_25; "WERKERNELHOST: WerSubmitUserCrashReport"...
0x14000c1ce  xor     edx, edx; Level
0x14000c1d0  lea     ecx, [rdx+5]; ComponentId
0x14000c1d3  call    cs:__imp_DbgPrintEx
0x14000c1da  nop     dword ptr [rax+rax+00h]
0x14000c1df  mov     rcx, [rsp+0E8h+TargetHandle]; Handle
0x14000c1e4  test    rcx, rcx
0x14000c1e7  jz      short loc_14000C1F7
0x14000c1e9  mov     dl, 1; PreviousMode
0x14000c1eb  call    cs:__imp_ObCloseHandle
0x14000c1f2  nop     dword ptr [rax+rax+00h]
0x14000c1f7  mov     rcx, [rsp+0E8h+EventHandle]
0x14000c1fc  test    rcx, rcx
0x14000c1ff  jz      loc_14000C0BC
0x14000c205  jmp     loc_14000C166
0x14000c20a  mov     [rsp+0E8h+Options], 8; Options
0x14000c212  mov     [rsp+0E8h+HandleAttributes], esi; HandleAttributes
0x14000c216  mov     dword ptr [rsp+0E8h+ReturnLength], 6; DesiredAccess
0x14000c21e  lea     r9, [rsp+0E8h+Handle]; TargetHandle
0x14000c223  mov     r8, r14; TargetProcessHandle
0x14000c226  mov     rdx, [rsp+0E8h+SectionHandle]; SourceHandle
0x14000c22b  mov     rcx, r14; SourceProcessHandle
0x14000c22e  call    cs:__imp_ZwDuplicateObject
0x14000c235  nop     dword ptr [rax+rax+00h]
0x14000c23a  mov     edi, eax
0x14000c23c  test    eax, eax
0x14000c23e  jns     short loc_14000C271
0x14000c240  mov     r9d, eax
0x14000c243  lea     r8, aWerkernelhostW_62; "WERKERNELHOST: WerSubmitUserCrashReport"...
0x14000c24a  xor     edx, edx; Level
0x14000c24c  lea     ecx, [rdx+5]; ComponentId
0x14000c24f  call    cs:__imp_DbgPrintEx
0x14000c256  nop     dword ptr [rax+rax+00h]
0x14000c25b  mov     rcx, [rsp+0E8h+SectionHandle]; Handle
0x14000c260  call    cs:__imp_ZwClose
0x14000c267  nop     dword ptr [rax+rax+00h]
0x14000c26c  jmp     loc_14000C1DF
0x14000c271  mov     [rsp+0E8h+BaseAddress], rbx
0x14000c276  mov     [rsp+0E8h+ViewSize], rbx
0x14000c27b  mov     [rsp+0E8h+Win32Protect], 4; Win32Protect
0x14000c283  mov     [rsp+0E8h+AllocationType], ebx; AllocationType
0x14000c287  mov     [rsp+0E8h+InheritDisposition], esi; InheritDisposition
0x14000c28b  lea     rax, [rsp+0E8h+ViewSize]
0x14000c290  mov     qword ptr [rsp+0E8h+Options], rax; ViewSize
0x14000c295  mov     qword ptr [rsp+0E8h+HandleAttributes], rbx; SectionOffset
0x14000c29a  mov     [rsp+0E8h+ReturnLength], rbx; CommitSize
0x14000c29f  xor     r9d, r9d; ZeroBits
0x14000c2a2  lea     r8, [rsp+0E8h+BaseAddress]; BaseAddress
0x14000c2a7  mov     rdx, r14; ProcessHandle
0x14000c2aa  mov     rcx, [rsp+0E8h+SectionHandle]; SectionHandle
0x14000c2af  call    cs:__imp_ZwMapViewOfSection
0x14000c2b6  nop     dword ptr [rax+rax+00h]
0x14000c2bb  mov     edi, eax
0x14000c2bd  test    eax, eax
0x14000c2bf  jns     short loc_14000C2F4
0x14000c2c1  mov     r9d, eax
0x14000c2c4  lea     r8, aWerkernelhostW_47; "WERKERNELHOST: WerSubmitUserCrashReport"...
0x14000c2cb  xor     edx, edx; Level
0x14000c2cd  lea     ecx, [rdx+5]; ComponentId
0x14000c2d0  call    cs:__imp_DbgPrintEx
0x14000c2d7  nop     dword ptr [rax+rax+00h]
0x14000c2dc  mov     dl, 1; PreviousMode
0x14000c2de  mov     rcx, [rsp+0E8h+Handle]; Handle
0x14000c2e3  call    cs:__imp_ObCloseHandle
0x14000c2ea  nop     dword ptr [rax+rax+00h]
0x14000c2ef  jmp     loc_14000C25B
0x14000c2f4  mov     rsi, [rsp+0E8h+BaseAddress]
0x14000c2f9  mov     [rsp+0E8h+var_68], rsi
0x14000c301  mov     edi, ebx
0x14000c303  xor     edx, edx; Val
0x14000c305  mov     r8d, 0F8h; Size
0x14000c30b  mov     rcx, rsi; void *
0x14000c30e  call    memset
0x14000c313  mov     dword ptr [rsi], 0F8h
0x14000c319  mov     eax, [rsp+0E8h+var_50]
0x14000c320  mov     [rsi+4], eax
0x14000c323  mov     eax, [rsp+0E8h+var_48]
0x14000c32a  mov     [rsi+8], eax
0x14000c32d  mov     [rsi+0B0h], ebx
0x14000c333  mov     [rsi+0B8h], rbx
0x14000c33a  mov     [rsi+0C0h], rbx
0x14000c341  mov     [rsi+0C8h], rbx
0x14000c348  mov     eax, dword ptr [rsp+0E8h+TargetHandle]
0x14000c34c  mov     [rsi+0D0h], rax
0x14000c353  mov     [rsi+0E0h], rbx
0x14000c35a  mov     dword ptr [rsi+0E8h], 0C00000BBh
0x14000c364  mov     eax, [rsp+0E8h+arg_18]
0x14000c36b  bts     eax, 1Fh
0x14000c36f  mov     [rsi+0ECh], eax
0x14000c375  mov     rax, 0FFFFF78000000320h
0x14000c37f  mov     rax, [rax]
0x14000c382  mov     rcx, 0FFFFF78000000004h
0x14000c38c  mov     ecx, [rcx]
0x14000c38e  imul    rcx, rax
0x14000c392  shr     rcx, 18h
0x14000c396  mov     [rsi+0F0h], ecx
0x14000c39c  test    r15, r15
0x14000c39f  jz      short loc_14000C408
0x14000c3a1  movups  xmm0, xmmword ptr [r15]
0x14000c3a5  movups  xmmword ptr [rsi+10h], xmm0
0x14000c3a9  movups  xmm1, xmmword ptr [r15+10h]
0x14000c3ae  movups  xmmword ptr [rsi+20h], xmm1
0x14000c3b2  movups  xmm0, xmmword ptr [r15+20h]
0x14000c3b7  movups  xmmword ptr [rsi+30h], xmm0
0x14000c3bb  movups  xmm1, xmmword ptr [r15+30h]
0x14000c3c0  movups  xmmword ptr [rsi+40h], xmm1
0x14000c3c4  movups  xmm0, xmmword ptr [r15+40h]
0x14000c3c9  movups  xmmword ptr [rsi+50h], xmm0
0x14000c3cd  movups  xmm1, xmmword ptr [r15+50h]
0x14000c3d2  movups  xmmword ptr [rsi+60h], xmm1
0x14000c3d6  movups  xmm0, xmmword ptr [r15+60h]
0x14000c3db  movups  xmmword ptr [rsi+70h], xmm0
0x14000c3df  movups  xmm1, xmmword ptr [r15+70h]
0x14000c3e4  movups  xmmword ptr [rsi+80h], xmm1
0x14000c3eb  movups  xmm0, xmmword ptr [r15+80h]
0x14000c3f3  movups  xmmword ptr [rsi+90h], xmm0
0x14000c3fa  mov     rax, [r15+90h]
0x14000c401  mov     [rsi+0A0h], rax
0x14000c408  jmp     short loc_14000C422
0x14000c40a  mov     edi, eax
0x14000c40c  xor     ebx, ebx
0x14000c40e  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000c412  mov     r13d, [rsp+0E8h+arg_20]
0x14000c41a  mov     r12d, dword ptr [rsp+0E8h+Object]
0x14000c422  mov     rdx, [rsp+0E8h+BaseAddress]; BaseAddress
0x14000c427  mov     rcx, r14; ProcessHandle
0x14000c42a  call    cs:__imp_ZwUnmapViewOfSection
0x14000c431  nop     dword ptr [rax+rax+00h]
0x14000c436  mov     [rsp+0E8h+Object], rbx
0x14000c43e  test    edi, edi
0x14000c440  js      short loc_14000C49F
0x14000c442  mov     rax, [rsp+0E8h+TargetHandle]
0x14000c447  mov     [rsp+0E8h+ReturnLength], rax
0x14000c44c  mov     r9d, [rsp+0E8h+var_50]
0x14000c454  mov     r8d, r13d
0x14000c457  mov     rdx, [rsp+0E8h+Handle]
0x14000c45c  lea     rcx, [rsp+0E8h+Object]
0x14000c464  call    WerpSendWersvcMessageWERSVC_REPORT_CRASH
0x14000c469  mov     edi, eax
0x14000c46b  test    eax, eax
0x14000c46d  js      short loc_14000C476
0x14000c46f  cmp     eax, 102h
0x14000c474  jnz     short loc_14000C49F
0x14000c476  mov     r9d, edi
0x14000c479  lea     r8, aWerkernelhostW_49; "WERKERNELHOST: WerSubmitUserCrashReport"...
0x14000c480  xor     edx, edx; Level
0x14000c482  lea     ecx, [rdx+5]; ComponentId
0x14000c485  call    cs:__imp_DbgPrintEx
0x14000c48c  nop     dword ptr [rax+rax+00h]
0x14000c491  mov     eax, 0C0000240h
0x14000c496  cmp     edi, 102h
0x14000c49c  cmovz   edi, eax
0x14000c49f  mov     dl, 1; PreviousMode
0x14000c4a1  mov     rcx, [rsp+0E8h+Handle]; Handle
0x14000c4a6  call    cs:__imp_ObCloseHandle
0x14000c4ad  nop     dword ptr [rax+rax+00h]
0x14000c4b2  mov     rcx, [rsp+0E8h+SectionHandle]; Handle
0x14000c4b7  call    cs:__imp_ZwClose
0x14000c4be  nop     dword ptr [rax+rax+00h]
0x14000c4c3  mov     rcx, [rsp+0E8h+TargetHandle]; Handle
0x14000c4c8  test    rcx, rcx
0x14000c4cb  jz      short loc_14000C4DB
0x14000c4cd  mov     dl, 1; PreviousMode
0x14000c4cf  call    cs:__imp_ObCloseHandle
0x14000c4d6  nop     dword ptr [rax+rax+00h]
0x14000c4db  test    edi, edi
0x14000c4dd  js      short loc_14000C4FB
0x14000c4df  mov     rcx, [rsp+0E8h+Object]
0x14000c4e7  test    rcx, rcx
0x14000c4ea  jz      short loc_14000C4FB
0x14000c4ec  test    r12d, r12d
0x14000c4ef  jz      short loc_14000C4FB
0x14000c4f1  mov     rdx, [rsp+0E8h+EventHandle]
0x14000c4f6  call    WerpBlockOnReporting
0x14000c4fb  mov     rcx, [rsp+0E8h+Object]; Object
0x14000c503  test    rcx, rcx
0x14000c506  jz      loc_14000C1F7
0x14000c50c  call    cs:__imp_ObfDereferenceObject
0x14000c513  nop     dword ptr [rax+rax+00h]
0x14000c518  jmp     loc_14000C1F7
0x14000c51d  mov     r9d, 0C00000BBh
0x14000c523  lea     r8, aWerkernelhostI; "WERKERNELHOST: I can only handle auto-c"...
0x14000c52a  xor     edx, edx; Level
0x14000c52c  lea     ecx, [rdx+5]; ComponentId
0x14000c52f  call    cs:__imp_DbgPrintEx
0x14000c536  nop     dword ptr [rax+rax+00h]
0x14000c53b  mov     eax, 0C00000BBh
0x14000c540  lea     r11, [rsp+0E8h+var_28]
0x14000c548  mov     rbx, [r11+30h]
0x14000c54c  mov     rsi, [r11+38h]
0x14000c550  mov     rsp, r11
0x14000c553  pop     r15
0x14000c555  pop     r14
0x14000c557  pop     r13
0x14000c559  pop     r12
0x14000c55b  pop     rdi
0x14000c55c  retn
0x140010bba  push    rbp
  ... truncated ...
```
