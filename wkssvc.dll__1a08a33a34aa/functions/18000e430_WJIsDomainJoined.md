# WJIsDomainJoined

- ea: `0x18000e430`
- end: `0x18000e50f`
- name: `WJIsDomainJoined`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012368`

## callees

- `0x18000e430`

## import_xrefs

- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18000e4b2`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18000e4b2`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18000e460`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18000e4f0`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18000e460`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18000e4f0`
- `netutils!NetApiBufferFree` at `0x18000e4d3`
- `netutils!NetApiBufferFree` at `0x18000e4d3`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpGetJoinInformation` at `0x18000e47e`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpGetJoinInformation` at `0x18000e47e`

## pseudocode

```c
__int64 __fastcall WJIsDomainJoined(_DWORD *a1)
{
  int JoinInformation; // eax
  unsigned int v3; // edi
  unsigned int v4; // ebx
  void *v5; // rcx
  int v7; // [rsp+30h] [rbp+8h] BYREF
  LPVOID Buffer; // [rsp+38h] [rbp+10h] BYREF

  Buffer = 0;
  v7 = 0;
  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: started", L"WJIsDomainJoined");
  *a1 = 0;
  JoinInformation = NetpGetJoinInformation(0, &Buffer, &v7);
  v3 = JoinInformation;
  if ( JoinInformation )
  {
    if ( JoinInformation > 0 )
      v4 = (unsigned __int16)JoinInformation | 0x80070000;
    else
      v4 = JoinInformation;
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: NetpGetJoinInformation failed with exit code 0x%08x",
      L"WJIsDomainJoined",
      v4);
  }
  else
  {
    v5 = Buffer;
    v4 = 0;
    *a1 = v7 == 3;
    NetApiBufferFree(v5);
  }
  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: finished - hr: 0x%08x", L"WJIsDomainJoined", v4);
  return v3;
}

```

## disassembly

```asm
0x18000e430  mov     rax, rsp
0x18000e433  mov     [rax+18h], rbx
0x18000e437  mov     [rax+20h], rsi
0x18000e43b  push    rdi
0x18000e43c  sub     rsp, 20h
0x18000e440  mov     rsi, rcx
0x18000e443  mov     qword ptr [rax+10h], 0
0x18000e44b  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18000e452  mov     dword ptr [rax+8], 0
0x18000e459  lea     rdx, aWjisdomainjoin; "WJIsDomainJoined"
0x18000e460  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18000e467  nop     dword ptr [rax+rax+00h]
0x18000e46c  lea     r8, [rsp+28h+arg_0]
0x18000e471  mov     dword ptr [rsi], 0
0x18000e477  lea     rdx, [rsp+28h+Buffer]
0x18000e47c  xor     ecx, ecx
0x18000e47e  call    cs:__imp_NetpGetJoinInformation
0x18000e485  nop     dword ptr [rax+rax+00h]
0x18000e48a  mov     edi, eax
0x18000e48c  test    eax, eax
0x18000e48e  jz      short loc_18000E4C0
0x18000e490  test    eax, eax
0x18000e492  jg      short loc_18000E498
0x18000e494  mov     ebx, eax
0x18000e496  jmp     short loc_18000E4A1
0x18000e498  movzx   ebx, di
0x18000e49b  or      ebx, 80070000h
0x18000e4a1  mov     r8d, ebx
0x18000e4a4  lea     rdx, aWjisdomainjoin; "WJIsDomainJoined"
0x18000e4ab  lea     rcx, aAutojoinsvcSNe; "AutoJoinSvc/%s: NetpGetJoinInformation "...
0x18000e4b2  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18000e4b9  nop     dword ptr [rax+rax+00h]
0x18000e4be  jmp     short loc_18000E4DF
0x18000e4c0  mov     rcx, [rsp+28h+Buffer]; Buffer
0x18000e4c5  xor     eax, eax
0x18000e4c7  xor     ebx, ebx
0x18000e4c9  cmp     [rsp+28h+arg_0], 3
0x18000e4ce  setz    al
0x18000e4d1  mov     [rsi], eax
0x18000e4d3  call    cs:__imp_NetApiBufferFree
0x18000e4da  nop     dword ptr [rax+rax+00h]
0x18000e4df  mov     r8d, ebx
0x18000e4e2  lea     rdx, aWjisdomainjoin; "WJIsDomainJoined"
0x18000e4e9  lea     rcx, aAutojoinsvcSFi_2; "AutoJoinSvc/%s: finished - hr: 0x%08x"
0x18000e4f0  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18000e4f7  nop     dword ptr [rax+rax+00h]
0x18000e4fc  mov     rbx, [rsp+28h+arg_10]
0x18000e501  mov     eax, edi
0x18000e503  mov     rsi, [rsp+28h+arg_18]
0x18000e508  add     rsp, 20h
0x18000e50c  pop     rdi
0x18000e50d  retn
```
