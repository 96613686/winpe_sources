# WinSetupMonCreateProcessNotificationCallback

- ea: `0x14001f5e0`
- end: `0x14001f6a3`
- name: `WinSetupMonCreateProcessNotificationCallback`
- size: `195`
- prototype: `void __stdcall(HANDLE ParentId, HANDLE ProcessId, BOOLEAN Create)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update`

## callees

- `0x14000d82c`
- `0x14000d880`
- `0x14001f130`
- `0x14001f5e0`

## import_xrefs

- `FLTMGR!FltQueueGenericWorkItem` at `0x14001f651`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14001f651`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14001f60e`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14001f60e`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14001f672`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14001f672`

## string_xrefs

- `0x14001f627`: `WinSetupMonCreateProcessNotificationCallback: Failed FltAllocateGenericWorkItem`
- `0x14001f68d`: `WinSetupMonCreateProcessNotificationCallback: Failed FltAllocateGenericWorkItem`
- `0x14001f663`: `WinSetupMonCreateProcessNotificationCallback: Failed FltQueueGenericWorkItem`

## pseudocode

```c
void __fastcall WinSetupMonCreateProcessNotificationCallback(
        unsigned __int64 ParentId,
        unsigned __int64 ProcessId,
        BOOLEAN Create)
{
  unsigned __int64 *v6; // rax
  unsigned __int64 *Context; // rbx
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // rax
  struct _FLT_GENERIC_WORKITEM *v9; // rdi
  NTSTATUS v10; // eax

  v6 = (unsigned __int64 *)operator new(ParentId);
  Context = v6;
  if ( v6 )
  {
    *v6 = ParentId;
    v6[1] = ProcessId;
    *((_BYTE *)v6 + 16) = Create;
    GenericWorkItem = FltAllocateGenericWorkItem();
    v9 = GenericWorkItem;
    if ( GenericWorkItem )
    {
      v10 = FltQueueGenericWorkItem(GenericWorkItem, FilterHandle, UpdateProcessMap, DelayedWorkQueue, Context);
      if ( v10 >= 0 )
        return;
      TraceError("WinSetupMonCreateProcessNotificationCallback: Failed FltQueueGenericWorkItem", (unsigned int)v10);
      FltFreeGenericWorkItem(v9);
    }
    else
    {
      TraceError("WinSetupMonCreateProcessNotificationCallback: Failed FltAllocateGenericWorkItem", 3221225626LL);
    }
    operator delete(Context);
  }
  else
  {
    TraceError("WinSetupMonCreateProcessNotificationCallback: Failed FltAllocateGenericWorkItem", 3221225626LL);
  }
}

```

## disassembly

```asm
0x14001f5e0  push    rbx
0x14001f5e2  push    rbp
0x14001f5e3  push    rsi
0x14001f5e4  push    rdi
0x14001f5e5  sub     rsp, 38h
0x14001f5e9  mov     dil, r8b
0x14001f5ec  mov     rsi, rdx
0x14001f5ef  mov     rbp, rcx
0x14001f5f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001f5f7  mov     rbx, rax
0x14001f5fa  test    rax, rax
0x14001f5fd  jz      loc_14001F688
0x14001f603  mov     [rax], rbp
0x14001f606  mov     [rax+8], rsi
0x14001f60a  mov     [rax+10h], dil
0x14001f60e  call    cs:__imp_FltAllocateGenericWorkItem
0x14001f615  nop     dword ptr [rax+rax+00h]
0x14001f61a  mov     rdi, rax
0x14001f61d  test    rax, rax
0x14001f620  jnz     short loc_14001F635
0x14001f622  mov     edx, 0C000009Ah
0x14001f627  lea     rcx, aWinsetupmoncre; "WinSetupMonCreateProcessNotificationCal"...
0x14001f62e  call    TraceError
0x14001f633  jmp     short loc_14001F67E
0x14001f635  mov     rdx, cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA; FltObject
0x14001f63c  lea     r8, UpdateProcessMap; WorkerRoutine
0x14001f643  mov     r9d, 1; QueueType
0x14001f649  mov     [rsp+58h+Context], rbx; Context
0x14001f64e  mov     rcx, rdi; FltWorkItem
0x14001f651  call    cs:__imp_FltQueueGenericWorkItem
0x14001f658  nop     dword ptr [rax+rax+00h]
0x14001f65d  test    eax, eax
0x14001f65f  jns     short loc_14001F699
0x14001f661  mov     edx, eax
0x14001f663  lea     rcx, aWinsetupmoncre_0; "WinSetupMonCreateProcessNotificationCal"...
0x14001f66a  call    TraceError
0x14001f66f  mov     rcx, rdi; FltWorkItem
0x14001f672  call    cs:__imp_FltFreeGenericWorkItem
0x14001f679  nop     dword ptr [rax+rax+00h]
0x14001f67e  mov     rcx, rbx; void *
0x14001f681  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001f686  jmp     short loc_14001F699
0x14001f688  mov     edx, 0C000009Ah
0x14001f68d  lea     rcx, aWinsetupmoncre; "WinSetupMonCreateProcessNotificationCal"...
0x14001f694  call    TraceError
0x14001f699  add     rsp, 38h
0x14001f69d  pop     rdi
0x14001f69e  pop     rsi
0x14001f69f  pop     rbp
0x14001f6a0  pop     rbx
0x14001f6a1  retn
```
