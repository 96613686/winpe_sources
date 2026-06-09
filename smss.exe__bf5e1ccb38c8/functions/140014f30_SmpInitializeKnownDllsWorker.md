# SmpInitializeKnownDllsWorker

- ea: `0x140014f30`
- end: `0x140014fbe`
- name: `SmpInitializeKnownDllsWorker`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14000d4c0`
- `0x14000eb40`
- `0x140014f30`
- `0x140017d5c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140014f62`
- `ntdll!RtlInitUnicodeString` at `0x140014f62`
- `ntdll!NtClose` at `0x140014fad`
- `ntdll!NtClose` at `0x140014fad`
- `ntdll!NtSetEvent` at `0x140014fa4`
- `ntdll!NtSetEvent` at `0x140014fa4`

## string_xrefs

- `0x140014f56`: `Failure in known dll worker.`
- `0x140014f7f`: `SmpInitializeKnownDllsWorker`

## pseudocode

```c
NTSTATUS __fastcall SmpInitializeKnownDllsWorker(__int64 a1, void *a2)
{
  int v3; // eax
  unsigned __int64 v4; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 Parameters[3]; // [rsp+30h] [rbp-18h] BYREF

  DestinationString = 0;
  v3 = SmpInitializeKnownDlls(3);
  v4 = v3;
  if ( v3 < 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Failure in known dll worker.");
    Parameters[1] = v4;
    Parameters[0] = (unsigned __int64)&DestinationString;
    SmpLogFailure("SmpInitializeKnownDllsWorker", 4100, (unsigned int)v4);
    SmpTerminate(Parameters, 1u, 2u);
  }
  NtSetEvent(a2, 0);
  return NtClose(a2);
}

```

## disassembly

```asm
0x140014f30  mov     [rsp+arg_0], rbx
0x140014f35  push    rdi
0x140014f36  sub     rsp, 40h
0x140014f3a  xorps   xmm0, xmm0
0x140014f3d  mov     ecx, 3
0x140014f42  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x140014f47  mov     rbx, rdx
0x140014f4a  call    SmpInitializeKnownDlls
0x140014f4f  movsxd  rdi, eax
0x140014f52  test    eax, eax
0x140014f54  jns     short loc_140014F9F
0x140014f56  lea     rdx, aFailureInKnown; "Failure in known dll worker."
0x140014f5d  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x140014f62  call    cs:__imp_RtlInitUnicodeString
0x140014f68  lea     rax, [rsp+48h+DestinationString]
0x140014f6d  mov     [rsp+48h+var_10], rdi
0x140014f72  mov     r8d, edi
0x140014f75  mov     [rsp+48h+Parameters], rax
0x140014f7a  mov     edx, 1004h
0x140014f7f  lea     rcx, aSmpinitializek_2; "SmpInitializeKnownDllsWorker"
0x140014f86  call    SmpLogFailure
0x140014f8b  mov     edx, 1; UnicodeStringParameterMask
0x140014f90  lea     rcx, [rsp+48h+Parameters]; Parameters
0x140014f95  lea     r8d, [rdx+1]; NumberOfParameters
0x140014f99  call    SmpTerminate
0x140014f9f  xor     edx, edx; PreviousState
0x140014fa1  mov     rcx, rbx; EventHandle
0x140014fa4  call    cs:__imp_NtSetEvent
0x140014faa  mov     rcx, rbx; Handle
0x140014fad  call    cs:__imp_NtClose
0x140014fb3  mov     rbx, [rsp+48h+arg_0]
0x140014fb8  add     rsp, 40h
0x140014fbc  pop     rdi
0x140014fbd  retn
```
