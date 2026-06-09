# SleepWorkerCallback(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x140038560`
- end: `0x140038671`
- name: `?SleepWorkerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `273`
- prototype: `void(struct _TP_CALLBACK_INSTANCE *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140038454`

## callees

- `0x1400057f4`
- `0x140038560`
- `0x140041c34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140038660`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140038660`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140038652`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140038652`
- `ntdll!NtInitiatePowerAction` at `0x1400385cf`
- `ntdll!NtInitiatePowerAction` at `0x1400385cf`
- `ntdll!RtlAdjustPrivilege` at `0x140038580`
- `ntdll!RtlAdjustPrivilege` at `0x14003864c`
- `ntdll!RtlAdjustPrivilege` at `0x140038580`
- `ntdll!RtlAdjustPrivilege` at `0x14003864c`

## pseudocode

```c
void __fastcall SleepWorkerCallback(struct _TP_CALLBACK_INSTANCE *a1, void *a2)
{
  __int64 v3; // r9
  unsigned int v4; // eax
  __int64 v5; // r9
  HANDLE ProcessHeap; // rax
  unsigned __int8 OldValue; // [rsp+38h] [rbp+10h] BYREF

  OldValue = 0;
  if ( RtlAdjustPrivilege(0x13u, 1u, 0, &OldValue) >= 0 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_c5124d71a6b832b53ba1b0d505ab939a_Traceguids, v3);
    }
    v4 = NtInitiatePowerAction(*(POWER_ACTION *)a2, PowerSystemSleeping1, *((_DWORD *)a2 + 1), 0);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c5124d71a6b832b53ba1b0d505ab939a_Traceguids, v4);
      }
    }
    else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_c5124d71a6b832b53ba1b0d505ab939a_Traceguids, v5);
    }
    if ( !OldValue )
      RtlAdjustPrivilege(0x13u, 0, 0, &OldValue);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, a2);
  }
}

```

## disassembly

```asm
0x140038560  mov     [rsp+arg_0], rbx
0x140038565  push    rsi
0x140038566  sub     rsp, 20h
0x14003856a  xor     r8d, r8d; ForThread
0x14003856d  mov     [rsp+28h+OldValue], 0
0x140038572  mov     rbx, rdx
0x140038575  lea     r9, [rsp+28h+OldValue]; OldValue
0x14003857a  mov     dl, 1; NewValue
0x14003857c  lea     ecx, [r8+13h]; Privilege
0x140038580  call    cs:__imp_RtlAdjustPrivilege
0x140038586  test    eax, eax
0x140038588  js      loc_140038666
0x14003858e  mov     rcx, cs:WPP_GLOBAL_Control
0x140038595  lea     rsi, WPP_GLOBAL_Control
0x14003859c  cmp     rcx, rsi
0x14003859f  jz      short loc_1400385C2
0x1400385a1  test    byte ptr [rcx+1Ch], 1
0x1400385a5  jz      short loc_1400385C2
0x1400385a7  cmp     byte ptr [rcx+19h], 4
0x1400385ab  jb      short loc_1400385C2
0x1400385ad  mov     rcx, [rcx+10h]
0x1400385b1  lea     r8, WPP_c5124d71a6b832b53ba1b0d505ab939a_Traceguids
0x1400385b8  mov     edx, 0Ah
0x1400385bd  call    WPP_SF_
0x1400385c2  mov     r8d, [rbx+4]; Flags
0x1400385c6  xor     r9d, r9d; Asynchronous
0x1400385c9  mov     ecx, [rbx]; SystemAction
0x1400385cb  lea     edx, [r9+2]; MinSystemState
0x1400385cf  call    cs:__imp_NtInitiatePowerAction
0x1400385d5  test    eax, eax
0x1400385d7  jz      short loc_14003860B
0x1400385d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400385e0  cmp     rcx, rsi
0x1400385e3  jz      short loc_140038638
0x1400385e5  test    byte ptr [rcx+1Ch], 1
0x1400385e9  jz      short loc_140038638
0x1400385eb  cmp     byte ptr [rcx+19h], 2
0x1400385ef  jb      short loc_140038638
0x1400385f1  mov     rcx, [rcx+10h]
0x1400385f5  lea     r8, WPP_c5124d71a6b832b53ba1b0d505ab939a_Traceguids
0x1400385fc  mov     edx, 0Bh
0x140038601  mov     r9d, eax
0x140038604  call    WPP_SF_d
0x140038609  jmp     short loc_140038638
0x14003860b  mov     rcx, cs:WPP_GLOBAL_Control
0x140038612  cmp     rcx, rsi
0x140038615  jz      short loc_140038638
0x140038617  test    byte ptr [rcx+1Ch], 1
0x14003861b  jz      short loc_140038638
0x14003861d  cmp     byte ptr [rcx+19h], 4
0x140038621  jb      short loc_140038638
0x140038623  mov     rcx, [rcx+10h]
0x140038627  lea     r8, WPP_c5124d71a6b832b53ba1b0d505ab939a_Traceguids
0x14003862e  mov     edx, 0Ch
0x140038633  call    WPP_SF_
0x140038638  cmp     [rsp+28h+OldValue], 0
0x14003863d  jnz     short loc_140038652
0x14003863f  xor     edx, edx; NewValue
0x140038641  lea     r9, [rsp+28h+OldValue]; OldValue
0x140038646  xor     r8d, r8d; ForThread
0x140038649  lea     ecx, [rdx+13h]; Privilege
0x14003864c  call    cs:__imp_RtlAdjustPrivilege
0x140038652  call    cs:__imp_GetProcessHeap
0x140038658  mov     r8, rbx; lpMem
0x14003865b  xor     edx, edx; dwFlags
0x14003865d  mov     rcx, rax; hHeap
0x140038660  call    cs:__imp_HeapFree
0x140038666  mov     rbx, [rsp+28h+arg_0]
0x14003866b  add     rsp, 20h
0x14003866f  pop     rsi
0x140038670  retn
```
