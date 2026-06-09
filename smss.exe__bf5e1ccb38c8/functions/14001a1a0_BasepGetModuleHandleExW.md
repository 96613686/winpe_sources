# BasepGetModuleHandleExW

- ea: `0x14001a1a0`
- end: `0x14001a217`
- name: `BasepGetModuleHandleExW`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001a220`

## callees

- `0x14001a1a0`
- `0x14001cabc`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14001a1cd`
- `ntdll!RtlInitUnicodeString` at `0x14001a1cd`
- `ntdll!LdrGetDllHandle` at `0x14001a1e1`
- `ntdll!LdrGetDllHandle` at `0x14001a1e1`

## string_xrefs

- `0x14001a1bb`: `ntdll.dll`

## pseudocode

```c
_BOOL8 __fastcall BasepGetModuleHandleExW(__int64 a1, __int64 a2, _QWORD *a3)
{
  NTSTATUS v4; // eax
  NTSTATUS v5; // ebx
  PVOID v6; // rax
  struct _UNICODE_STRING DllName; // [rsp+20h] [rbp-18h] BYREF
  PVOID DllHandle; // [rsp+48h] [rbp+10h] BYREF

  DllHandle = 0;
  DllName = 0;
  RtlInitUnicodeString(&DllName, L"ntdll.dll");
  v4 = LdrGetDllHandle(0, 0, &DllName, &DllHandle);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = DllHandle;
  }
  else
  {
    BaseSetLastNTError((unsigned int)v4);
    v6 = 0;
  }
  if ( a3 )
    *a3 = v6;
  return v5 >= 0;
}

```

## disassembly

```asm
0x14001a1a0  mov     rax, rsp
0x14001a1a3  mov     [rax+8], rbx
0x14001a1a7  mov     [rax+10h], rdx
0x14001a1ab  push    rdi
0x14001a1ac  sub     rsp, 30h
0x14001a1b0  xorps   xmm0, xmm0
0x14001a1b3  mov     qword ptr [rax+10h], 0
0x14001a1bb  lea     rdx, aNtdllDll_1; "ntdll.dll"
0x14001a1c2  mov     rdi, r8
0x14001a1c5  lea     rcx, [rax-18h]; DestinationString
0x14001a1c9  movups  xmmword ptr [rax-18h], xmm0
0x14001a1cd  call    cs:__imp_RtlInitUnicodeString
0x14001a1d3  lea     r9, [rsp+38h+DllHandle]; DllHandle
0x14001a1d8  xor     edx, edx; DllCharacteristics
0x14001a1da  lea     r8, [rsp+38h+DllName]; DllName
0x14001a1df  xor     ecx, ecx; DllPath
0x14001a1e1  call    cs:__imp_LdrGetDllHandle
0x14001a1e7  mov     ebx, eax
0x14001a1e9  test    eax, eax
0x14001a1eb  jns     short loc_14001A1F8
0x14001a1ed  mov     ecx, eax
0x14001a1ef  call    BaseSetLastNTError
0x14001a1f4  xor     eax, eax
0x14001a1f6  jmp     short loc_14001A1FD
0x14001a1f8  mov     rax, [rsp+38h+DllHandle]
0x14001a1fd  test    rdi, rdi
0x14001a200  jz      short loc_14001A205
0x14001a202  mov     [rdi], rax
0x14001a205  not     ebx
0x14001a207  shr     ebx, 1Fh
0x14001a20a  mov     eax, ebx
0x14001a20c  mov     rbx, [rsp+38h+arg_0]
0x14001a211  add     rsp, 30h
0x14001a215  pop     rdi
0x14001a216  retn
```
