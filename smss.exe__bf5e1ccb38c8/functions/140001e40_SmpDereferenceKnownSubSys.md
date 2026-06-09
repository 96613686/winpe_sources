# SmpDereferenceKnownSubSys

- ea: `0x140001e40`
- end: `0x140001f50`
- name: `SmpDereferenceKnownSubSys`
- size: `272`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `10`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140001630`
- `0x140001880`
- `0x140001f60`
- `0x1400027a0`
- `0x1400036d0`
- `0x140005f64`
- `0x140008210`
- `0x1400151e0`
- `0x140017954`
- `0x140017f58`

## callees

- `0x140001e40`
- `0x140017d5c`
- `0x140017ff0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140001f10`
- `ntdll!RtlInitUnicodeString` at `0x140001f10`
- `ntdll!NtClose` at `0x140001e77`
- `ntdll!NtClose` at `0x140001e8c`
- `ntdll!NtClose` at `0x140001e77`
- `ntdll!NtClose` at `0x140001e8c`
- `ntdll!RtlFreeHeap` at `0x140001ea4`
- `ntdll!RtlFreeHeap` at `0x140001ea4`

## pseudocode

```c
void __fastcall SmpDereferenceKnownSubSys(_BYTE *BaseAddress)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  __int64 v5; // rax
  _QWORD *v6; // rbx
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 Parameters[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( BaseAddress && _InterlockedExchangeAdd((volatile signed __int32 *)BaseAddress, 0xFFFFFFFF) == 1 )
  {
    if ( (BaseAddress[8] & 4) != 0
      && *((_DWORD *)BaseAddress + 6) == 2
      && *((_DWORD *)BaseAddress + 16) == *(_DWORD *)SmpCoreProcessIds )
    {
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"Core Windows subsystem terminated");
      Parameters[1] = -1073741823;
      Parameters[0] = (unsigned __int64)&DestinationString;
      SmpTerminate(Parameters, 1u, 2u);
    }
    v2 = (void *)*((_QWORD *)BaseAddress + 2);
    if ( v2 )
      SmpDisposeSubSysSynch(v2);
    v3 = (void *)*((_QWORD *)BaseAddress + 5);
    if ( v3 )
      NtClose(v3);
    if ( (BaseAddress[8] & 8) != 0 )
    {
      v5 = SmpOverflowSubSysList;
      if ( *(__int64 **)(SmpOverflowSubSysList + 8) != &SmpOverflowSubSysList )
        __fastfail(3u);
      v6 = BaseAddress + 72;
      *v6 = SmpOverflowSubSysList;
      v6[1] = &SmpOverflowSubSysList;
      *(_QWORD *)(v5 + 8) = v6;
      SmpOverflowSubSysList = (__int64)v6;
    }
    else
    {
      v4 = (void *)*((_QWORD *)BaseAddress + 4);
      if ( v4 )
        NtClose(v4);
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, BaseAddress);
    }
  }
}

```

## disassembly

```asm
0x140001e40  test    rcx, rcx
0x140001e43  jz      short locret_140001EAF
0x140001e45  push    rbx
0x140001e46  sub     rsp, 40h
0x140001e4a  mov     rbx, rcx
0x140001e4d  mov     eax, 0FFFFFFFFh
0x140001e52  lock xadd [rcx], eax
0x140001e56  cmp     eax, 1
0x140001e59  jnz     short loc_140001EAA
0x140001e5b  test    byte ptr [rcx+8], 4
0x140001e5f  jnz     short loc_140001EE0
0x140001e61  mov     rcx, [rbx+10h]; BaseAddress
0x140001e65  test    rcx, rcx
0x140001e68  jnz     loc_140001F3F
0x140001e6e  mov     rcx, [rbx+28h]; Handle
0x140001e72  test    rcx, rcx
0x140001e75  jz      short loc_140001E7D
0x140001e77  call    cs:__imp_NtClose
0x140001e7d  test    byte ptr [rbx+8], 8
0x140001e81  jnz     short loc_140001EB0
0x140001e83  mov     rcx, [rbx+20h]; Handle
0x140001e87  test    rcx, rcx
0x140001e8a  jz      short loc_140001E92
0x140001e8c  call    cs:__imp_NtClose
0x140001e92  mov     rcx, gs:60h
0x140001e9b  mov     r8, rbx; BaseAddress
0x140001e9e  xor     edx, edx; Flags
0x140001ea0  mov     rcx, [rcx+30h]; HeapHandle
0x140001ea4  call    cs:__imp_RtlFreeHeap
0x140001eaa  add     rsp, 40h
0x140001eae  pop     rbx
0x140001eaf  retn
0x140001eb0  mov     rax, cs:SmpOverflowSubSysList
0x140001eb7  lea     rcx, SmpOverflowSubSysList
0x140001ebe  cmp     [rax+8], rcx
0x140001ec2  jnz     loc_140001F49
0x140001ec8  add     rbx, 48h ; 'H'
0x140001ecc  mov     [rbx], rax
0x140001ecf  mov     [rbx+8], rcx
0x140001ed3  mov     [rax+8], rbx
0x140001ed7  mov     cs:SmpOverflowSubSysList, rbx
0x140001ede  jmp     short loc_140001EAA
0x140001ee0  cmp     dword ptr [rcx+18h], 2
0x140001ee4  jnz     loc_140001E61
0x140001eea  mov     rax, cs:SmpCoreProcessIds
0x140001ef1  mov     ecx, [rax]
0x140001ef3  cmp     [rbx+40h], ecx
0x140001ef6  jnz     loc_140001E61
0x140001efc  xorps   xmm0, xmm0
0x140001eff  lea     rdx, SourceString; "Core Windows subsystem terminated"
0x140001f06  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x140001f0b  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x140001f10  call    cs:__imp_RtlInitUnicodeString
0x140001f16  lea     rax, [rsp+48h+DestinationString]
0x140001f1b  mov     [rsp+48h+var_10], 0FFFFFFFFC0000001h
0x140001f24  mov     edx, 1; UnicodeStringParameterMask
0x140001f29  mov     [rsp+48h+Parameters], rax
0x140001f2e  mov     r8d, 2; NumberOfParameters
0x140001f34  lea     rcx, [rsp+48h+Parameters]; Parameters
0x140001f39  call    SmpTerminate
0x140001f3f  call    SmpDisposeSubSysSynch
0x140001f44  jmp     loc_140001E6E
0x140001f49  mov     ecx, 3
0x140001f4e  int     29h; Win8: RtlFailFast(ecx)
```
