# CloseHandle(_FLT_INSTANCE *,uchar,void *)

- ea: `0x14000d8a8`
- end: `0x14000d9bd`
- name: `?CloseHandle@@YAJPEAU_FLT_INSTANCE@@EPEAX@Z`
- size: `277`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, unsigned __int8, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140002488`
- `0x140002678`
- `0x140003780`
- `0x14000dd90`

## callees

- `0x14000d8a8`
- `0x14000f684`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000d8c6`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d8c6`
- `ntoskrnl!IoFileObjectType` at `0x14000d8ee`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000d916`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000d916`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d959`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d99e`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d959`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d99e`
- `FLTMGR!FltFlushBuffers` at `0x14000d939`
- `FLTMGR!FltFlushBuffers` at `0x14000d939`
- `FLTMGR!FltClose` at `0x14000d971`
- `FLTMGR!FltClose` at `0x14000d971`

## pseudocode

```c
__int64 __fastcall CloseHandle(PFLT_INSTANCE Instance, __int64 a2, void *a3)
{
  unsigned int v5; // ebx
  NTSTATUS v6; // eax
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  PVOID Object; // [rsp+58h] [rbp+20h] BYREF

  Object = 0;
  if ( KeGetCurrentIrql() )
  {
    v5 = -1073741637;
    WriteLog(0, "WinSetupMon::CloseHandle: [FlushBuffers] not called at PASSIVE_LEVEL, bailing");
  }
  else
  {
    v6 = ObReferenceObjectByHandle(a3, 0x10000000u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v7 = FltFlushBuffers(Instance, (PFILE_OBJECT)Object);
      v5 = v7;
      if ( v7 >= 0 )
      {
        ObfDereferenceObject(Object);
        Object = 0;
        v8 = FltClose(a3);
        v5 = v8;
        if ( v8 < 0 )
          WriteLog(0, "WinSetupMon::CloseHandle: Failed FltClose (0x%08X)", (unsigned int)v8);
      }
      else
      {
        WriteLog(0, "WinSetupMon::CloseHandle: Failed FltFlushBuffers (0x%08X)", (unsigned int)v7);
      }
    }
    else
    {
      WriteLog(0, "WinSetupMon::CloseHandle: Failed ObReferenceObjectByHandle (0x%08X)", (unsigned int)v6);
    }
  }
  if ( Object )
    ObfDereferenceObject(Object);
  return v5;
}

```

## disassembly

```asm
0x14000d8a8  mov     [rsp+arg_0], rbx
0x14000d8ad  mov     [rsp+arg_8], rsi
0x14000d8b2  push    rdi
0x14000d8b3  sub     rsp, 30h
0x14000d8b7  mov     rdi, r8
0x14000d8ba  mov     [rsp+38h+arg_18], 0
0x14000d8c3  mov     rsi, rcx
0x14000d8c6  call    cs:__imp_KeGetCurrentIrql
0x14000d8cd  nop     dword ptr [rax+rax+00h]
0x14000d8d2  test    al, al
0x14000d8d4  jz      short loc_14000D8EE
0x14000d8d6  lea     rdx, aWinsetupmonClo; "WinSetupMon::CloseHandle: [FlushBuffers"...
0x14000d8dd  xor     ecx, ecx
0x14000d8df  mov     ebx, 0C00000BBh
0x14000d8e4  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000d8e9  jmp     loc_14000D994
0x14000d8ee  mov     r8, cs:__imp_IoFileObjectType
0x14000d8f5  lea     rax, [rsp+38h+arg_18]
0x14000d8fa  mov     [rsp+38h+HandleInformation], 0; HandleInformation
0x14000d903  xor     r9d, r9d; AccessMode
0x14000d906  mov     edx, 10000000h; DesiredAccess
0x14000d90b  mov     [rsp+38h+Object], rax; Object
0x14000d910  mov     rcx, rdi; Handle
0x14000d913  mov     r8, [r8]; ObjectType
0x14000d916  call    cs:__imp_ObReferenceObjectByHandle
0x14000d91d  nop     dword ptr [rax+rax+00h]
0x14000d922  mov     ebx, eax
0x14000d924  test    eax, eax
0x14000d926  jns     short loc_14000D931
0x14000d928  lea     rdx, aWinsetupmonClo_1; "WinSetupMon::CloseHandle: Failed ObRefe"...
0x14000d92f  jmp     short loc_14000D98A
0x14000d931  mov     rdx, [rsp+38h+arg_18]; FileObject
0x14000d936  mov     rcx, rsi; Instance
0x14000d939  call    cs:__imp_FltFlushBuffers
0x14000d940  nop     dword ptr [rax+rax+00h]
0x14000d945  mov     ebx, eax
0x14000d947  test    eax, eax
0x14000d949  jns     short loc_14000D954
0x14000d94b  lea     rdx, aWinsetupmonClo_0; "WinSetupMon::CloseHandle: Failed FltFlu"...
0x14000d952  jmp     short loc_14000D98A
0x14000d954  mov     rcx, [rsp+38h+arg_18]; Object
0x14000d959  call    cs:__imp_ObfDereferenceObject
0x14000d960  nop     dword ptr [rax+rax+00h]
0x14000d965  mov     rcx, rdi; FileHandle
0x14000d968  mov     [rsp+38h+arg_18], 0
0x14000d971  call    cs:__imp_FltClose
0x14000d978  nop     dword ptr [rax+rax+00h]
0x14000d97d  mov     ebx, eax
0x14000d97f  test    eax, eax
0x14000d981  jns     short loc_14000D994
0x14000d983  lea     rdx, aWinsetupmonClo_2; "WinSetupMon::CloseHandle: Failed FltClo"...
0x14000d98a  mov     r8d, eax
0x14000d98d  xor     ecx, ecx
0x14000d98f  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000d994  mov     rcx, [rsp+38h+arg_18]; Object
0x14000d999  test    rcx, rcx
0x14000d99c  jz      short loc_14000D9AA
0x14000d99e  call    cs:__imp_ObfDereferenceObject
0x14000d9a5  nop     dword ptr [rax+rax+00h]
0x14000d9aa  mov     rsi, [rsp+38h+arg_8]
0x14000d9af  mov     eax, ebx
0x14000d9b1  mov     rbx, [rsp+38h+arg_0]
0x14000d9b6  add     rsp, 30h
0x14000d9ba  pop     rdi
0x14000d9bb  retn
```
