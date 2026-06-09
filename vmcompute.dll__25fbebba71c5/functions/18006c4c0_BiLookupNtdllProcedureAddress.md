# BiLookupNtdllProcedureAddress

- ea: `0x18006c4c0`
- end: `0x18006c579`
- name: `BiLookupNtdllProcedureAddress`
- size: `185`
- prototype: `__int64 __fastcall(PCSZ SourceString)`
- caller_count: `13`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18006abe4`
- `0x18006b590`
- `0x18006c714`
- `0x18006cd94`
- `0x18006e000`
- `0x18006e0ac`
- `0x18006e228`
- `0x18006e4a8`
- `0x18006f1cc`
- `0x18006f264`
- `0x18006f398`
- `0x18006f4d4`
- `0x18006f578`

## callees

- `0x18006c4c0`

## import_xrefs

- `ntdll!LdrGetProcedureAddress` at `0x18006c54d`
- `ntdll!LdrGetProcedureAddress` at `0x18006c54d`
- `ntdll!LdrGetDllHandle` at `0x18006c519`
- `ntdll!LdrGetDllHandle` at `0x18006c519`
- `ntdll!RtlInitAnsiString` at `0x18006c532`
- `ntdll!RtlInitAnsiString` at `0x18006c532`
- `ntdll!RtlInitUnicodeString` at `0x18006c501`
- `ntdll!RtlInitUnicodeString` at `0x18006c501`

## string_xrefs

- `0x18006c4eb`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall BiLookupNtdllProcedureAddress(PCSZ SourceString, PVOID *a2)
{
  NTSTATUS v4; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-20h] BYREF
  _STRING Name; // [rsp+30h] [rbp-10h] BYREF
  PVOID DllHandle; // [rsp+60h] [rbp+20h] BYREF
  PVOID ProcedureAddress; // [rsp+68h] [rbp+28h] BYREF

  ProcedureAddress = 0;
  DllHandle = 0;
  DestinationString = 0;
  Name = 0;
  RtlInitUnicodeString(&DestinationString, L"ntdll.dll");
  v4 = LdrGetDllHandle(0, 0, &DestinationString, &DllHandle);
  if ( v4 >= 0 )
  {
    RtlInitAnsiString(&Name, SourceString);
    v4 = LdrGetProcedureAddress(DllHandle, &Name, 0, &ProcedureAddress);
    if ( v4 >= 0 )
      *a2 = ProcedureAddress;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006c4c0  mov     [rsp-8+arg_0], rbx
0x18006c4c5  mov     [rsp-8+arg_8], rdi
0x18006c4ca  push    rbp
0x18006c4cb  mov     rbp, rsp
0x18006c4ce  sub     rsp, 40h
0x18006c4d2  mov     rbx, rdx
0x18006c4d5  mov     [rbp+ProcedureAddress], 0
0x18006c4dd  mov     rdi, rcx
0x18006c4e0  mov     [rbp+DllHandle], 0
0x18006c4e8  xorps   xmm0, xmm0
0x18006c4eb  lea     rdx, aNtdllDll_1; "ntdll.dll"
0x18006c4f2  xorps   xmm1, xmm1
0x18006c4f5  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006c4f9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18006c4fd  movups  xmmword ptr [rbp+Name.Length], xmm1
0x18006c501  call    cs:__imp_RtlInitUnicodeString
0x18006c508  nop     dword ptr [rax+rax+00h]
0x18006c50d  lea     r9, [rbp+DllHandle]; DllHandle
0x18006c511  xor     edx, edx; DllCharacteristics
0x18006c513  lea     r8, [rbp+DestinationString]; DllName
0x18006c517  xor     ecx, ecx; DllPath
0x18006c519  call    cs:__imp_LdrGetDllHandle
0x18006c520  nop     dword ptr [rax+rax+00h]
0x18006c525  mov     ecx, eax
0x18006c527  test    eax, eax
0x18006c529  js      short loc_18006C566
0x18006c52b  mov     rdx, rdi; SourceString
0x18006c52e  lea     rcx, [rbp+Name]; DestinationString
0x18006c532  call    cs:__imp_RtlInitAnsiString
0x18006c539  nop     dword ptr [rax+rax+00h]
0x18006c53e  mov     rcx, [rbp+DllHandle]; BaseAddress
0x18006c542  lea     r9, [rbp+ProcedureAddress]; ProcedureAddress
0x18006c546  xor     r8d, r8d; Ordinal
0x18006c549  lea     rdx, [rbp+Name]; Name
0x18006c54d  call    cs:__imp_LdrGetProcedureAddress
0x18006c554  nop     dword ptr [rax+rax+00h]
0x18006c559  mov     ecx, eax
0x18006c55b  test    eax, eax
0x18006c55d  js      short loc_18006C566
0x18006c55f  mov     rax, [rbp+ProcedureAddress]
0x18006c563  mov     [rbx], rax
0x18006c566  mov     rbx, [rsp+40h+arg_0]
0x18006c56b  mov     eax, ecx
0x18006c56d  mov     rdi, [rsp+40h+arg_8]
0x18006c572  add     rsp, 40h
0x18006c576  pop     rbp
0x18006c577  retn
```
