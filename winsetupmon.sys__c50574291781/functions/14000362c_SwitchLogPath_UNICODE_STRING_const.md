# SwitchLogPath(_UNICODE_STRING const *)

- ea: `0x14000362c`
- end: `0x140003777`
- name: `?SwitchLogPath@@YAJPEBU_UNICODE_STRING@@@Z`
- size: `331`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x14001e71c`

## callees

- `0x140001748`
- `0x140002488`
- `0x140002678`
- `0x14000362c`
- `0x140003944`
- `0x140003f48`
- `0x1400040b4`
- `0x14000e1d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400036e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000375d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400036e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000375d`
- `ntoskrnl!KeReleaseMutex` at `0x140003726`
- `ntoskrnl!KeReleaseMutex` at `0x140003742`
- `ntoskrnl!KeReleaseMutex` at `0x140003726`
- `ntoskrnl!KeReleaseMutex` at `0x140003742`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400036a9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400036a9`

## string_xrefs

- `0x140003680`: `Switching to log path %wZ`

## pseudocode

```c
__int64 __fastcall SwitchLogPath(const struct _UNICODE_STRING *a1)
{
  int NtPath; // ebx
  __int64 v3; // rdx
  __int64 v4; // rdx
  PVOID P[2]; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING v7; // [rsp+40h] [rbp-18h] BYREF

  *(_OWORD *)P = 0;
  v7 = 0;
  if ( FileHandle )
  {
    NtPath = GetNtPath(a1, (PUNICODE_STRING)P, &v7);
    if ( NtPath >= 0 )
    {
      WriteLogMessage(1, L"Switching to log path %wZ", P);
      WriteLogStop();
      KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
      LOBYTE(v3) = 1;
      NtPath = CloseLog(0, v3);
      if ( NtPath < 0 )
        goto LABEL_10;
      NtPath = PersistLogPath(a1);
      if ( NtPath < 0 )
        goto LABEL_10;
      if ( String2.Buffer )
        ExFreePoolWithTag(String2.Buffer, 0x6E6D7377u);
      LOBYTE(v4) = 1;
      String2 = *(UNICODE_STRING *)P;
      *(_OWORD *)P = 0;
      NtPath = OpenLog(0, v4, 0, &String2);
      if ( NtPath < 0 )
      {
LABEL_10:
        KeReleaseMutex(&Object, 0);
      }
      else
      {
        KeReleaseMutex(&Object, 0);
        WriteLogStart();
      }
    }
  }
  else
  {
    NtPath = -1073741809;
  }
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x6E6D7377u);
  return (unsigned int)NtPath;
}

```

## disassembly

```asm
0x14000362c  mov     [rsp+arg_0], rbx
0x140003631  push    rdi
0x140003632  sub     rsp, 50h
0x140003636  cmp     cs:FileHandle, 0
0x14000363e  xorps   xmm0, xmm0
0x140003641  xorps   xmm1, xmm1
0x140003644  mov     rdi, rcx
0x140003647  movups  xmmword ptr [rsp+58h+P], xmm0
0x14000364c  movups  xmmword ptr [rsp+58h+var_18.Length], xmm1
0x140003651  jnz     short loc_14000365D
0x140003653  mov     ebx, 0C000000Fh
0x140003658  jmp     loc_14000374E
0x14000365d  lea     r8, [rsp+58h+var_18]; struct _UNICODE_STRING *
0x140003662  lea     rdx, [rsp+58h+P]; DestinationString
0x140003667  call    ?GetNtPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14000366c  mov     ebx, eax
0x14000366e  test    eax, eax
0x140003670  js      loc_14000374E
0x140003676  lea     r8, [rsp+58h+P]
0x14000367b  mov     ecx, 1
0x140003680  lea     rdx, aSwitchingToLog; "Switching to log path %wZ"
0x140003687  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14000368c  call    ?WriteLogStop@@YAXXZ; WriteLogStop(void)
0x140003691  xor     r9d, r9d; Alertable
0x140003694  mov     [rsp+58h+Timeout], 0; Timeout
0x14000369d  xor     r8d, r8d; WaitMode
0x1400036a0  lea     rcx, Object; Object
0x1400036a7  xor     edx, edx; WaitReason
0x1400036a9  call    cs:__imp_KeWaitForSingleObject
0x1400036b0  nop     dword ptr [rax+rax+00h]
0x1400036b5  mov     dl, 1
0x1400036b7  xor     ecx, ecx
0x1400036b9  call    CloseLog
0x1400036be  mov     ebx, eax
0x1400036c0  test    eax, eax
0x1400036c2  js      short loc_140003739
0x1400036c4  mov     rcx, rdi; struct _UNICODE_STRING *
0x1400036c7  call    ?PersistLogPath@@YAJPEBU_UNICODE_STRING@@@Z; PersistLogPath(_UNICODE_STRING const *)
0x1400036cc  mov     ebx, eax
0x1400036ce  test    eax, eax
0x1400036d0  js      short loc_140003739
0x1400036d2  mov     rcx, cs:String2.Buffer; P
0x1400036d9  test    rcx, rcx
0x1400036dc  jz      short loc_1400036EF
0x1400036de  mov     edx, 6E6D7377h; Tag
0x1400036e3  call    cs:__imp_ExFreePoolWithTag
0x1400036ea  nop     dword ptr [rax+rax+00h]
0x1400036ef  movups  xmm0, xmmword ptr [rsp+58h+P]
0x1400036f4  lea     r9, String2
0x1400036fb  xor     r8d, r8d
0x1400036fe  xorps   xmm1, xmm1
0x140003701  mov     dl, 1
0x140003703  xor     ecx, ecx
0x140003705  movdqu  xmmword ptr cs:String2.Length, xmm0
0x14000370d  movups  xmmword ptr [rsp+58h+P], xmm1
0x140003712  call    OpenLog
0x140003717  mov     ebx, eax
0x140003719  test    eax, eax
0x14000371b  js      short loc_140003739
0x14000371d  xor     edx, edx; Wait
0x14000371f  lea     rcx, Object; Mutex
0x140003726  call    cs:__imp_KeReleaseMutex
0x14000372d  nop     dword ptr [rax+rax+00h]
0x140003732  call    ?WriteLogStart@@YAXXZ; WriteLogStart(void)
0x140003737  jmp     short loc_14000374E
0x140003739  xor     edx, edx; Wait
0x14000373b  lea     rcx, Object; Mutex
0x140003742  call    cs:__imp_KeReleaseMutex
0x140003749  nop     dword ptr [rax+rax+00h]
0x14000374e  mov     rcx, [rsp+58h+P+8]; P
0x140003753  test    rcx, rcx
0x140003756  jz      short loc_140003769
0x140003758  mov     edx, 6E6D7377h; Tag
0x14000375d  call    cs:__imp_ExFreePoolWithTag
0x140003764  nop     dword ptr [rax+rax+00h]
0x140003769  mov     eax, ebx
0x14000376b  mov     rbx, [rsp+58h+arg_0]
0x140003770  add     rsp, 50h
0x140003774  pop     rdi
0x140003775  retn
```
