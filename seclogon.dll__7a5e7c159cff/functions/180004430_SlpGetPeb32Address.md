# SlpGetPeb32Address

- ea: `0x180004430`
- end: `0x18000447f`
- name: `SlpGetPeb32Address`
- size: `79`
- prototype: `__int64 __fastcall(void *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800028f0`

## callees

- `0x180004430`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x18000444f`
- `ntdll!NtQueryInformationProcess` at `0x18000444f`
- `ntdll!RtlNtStatusToDosError` at `0x18000445b`
- `ntdll!RtlNtStatusToDosError` at `0x180004471`
- `ntdll!RtlNtStatusToDosError` at `0x18000445b`
- `ntdll!RtlNtStatusToDosError` at `0x180004471`

## pseudocode

```c
__int64 __fastcall SlpGetPeb32Address(void *a1, _QWORD *a2)
{
  int InformationProcess; // eax

  InformationProcess = NtQueryInformationProcess(a1, ProcessWow64Information, a2, 8u, 0);
  if ( InformationProcess < 0 )
  {
    *a2 = 0;
    RtlNtStatusToDosError(InformationProcess);
    return 0;
  }
  else
  {
    RtlNtStatusToDosError(0);
    return 1;
  }
}

```

## disassembly

```asm
0x180004430  push    rbx
0x180004432  sub     rsp, 30h
0x180004436  mov     r9d, 8; ProcessInformationLength
0x18000443c  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x180004445  mov     rbx, rdx
0x180004448  mov     r8, rdx; ProcessInformation
0x18000444b  lea     edx, [r9+12h]; ProcessInformationClass
0x18000444f  call    cs:__imp_NtQueryInformationProcess
0x180004455  test    eax, eax
0x180004457  js      short loc_180004468
0x180004459  xor     ecx, ecx; Status
0x18000445b  call    cs:__imp_RtlNtStatusToDosError
0x180004461  mov     eax, 1
0x180004466  jmp     short loc_180004479
0x180004468  mov     ecx, eax; Status
0x18000446a  mov     qword ptr [rbx], 0
0x180004471  call    cs:__imp_RtlNtStatusToDosError
0x180004477  xor     eax, eax
0x180004479  add     rsp, 30h
0x18000447d  pop     rbx
0x18000447e  retn
```
