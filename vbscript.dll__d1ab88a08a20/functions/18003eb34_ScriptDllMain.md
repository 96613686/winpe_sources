# ScriptDllMain

- ea: `0x18003eb34`
- end: `0x18003ec2d`
- name: `ScriptDllMain`
- size: `249`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18003eb28`

## callees

- `0x180036e44`
- `0x180039c44`
- `0x180039d70`
- `0x18003cf74`
- `0x18003d1a4`
- `0x18003e24c`
- `0x18003eb34`
- `0x180046884`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x18003eb6f`
- `KERNEL32!TlsSetValue` at `0x18003eb6f`
- `KERNEL32!TlsGetValue` at `0x18003ebfa`
- `KERNEL32!TlsGetValue` at `0x18003ebfa`

## pseudocode

```c
__int64 __fastcall ScriptDllMain(__int64 a1, int a2)
{
  RegistryBasedThrottle *v5; // rax
  RegistryBasedThrottle *v6; // rbx
  unsigned int v7; // edx
  unsigned int v8; // ebx
  ThreadGlobals *Value; // rax
  unsigned int v10; // edx

  if ( !a2 )
  {
    if ( g_pTraceLoggingClient )
    {
      TraceLoggingClient::`scalar deleting destructor'(g_pTraceLoggingClient, 0);
      g_pTraceLoggingClient = 0;
    }
    goto LABEL_16;
  }
  if ( a2 != 1 )
  {
    if ( a2 == 2 )
    {
      TlsSetValue(g_luTls, 0);
      return 1;
    }
    if ( a2 != 3 )
      return 0;
LABEL_16:
    Value = (ThreadGlobals *)TlsGetValue(g_luTls);
    if ( Value )
      ThreadGlobals::`scalar deleting destructor'(Value, v10);
    if ( !a2 )
      DetachProcess();
    return 1;
  }
  v5 = (RegistryBasedThrottle *)operator new(0x1B70u);
  v6 = v5;
  if ( v5 )
  {
    RegistryBasedThrottle::RegistryBasedThrottle(v5);
    TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  }
  else
  {
    v6 = 0;
  }
  g_pTraceLoggingClient = v6;
  v8 = AttachProcess(a1);
  if ( !v8 && g_pTraceLoggingClient )
  {
    TraceLoggingClient::`scalar deleting destructor'(g_pTraceLoggingClient, v7);
    g_pTraceLoggingClient = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x18003eb34  mov     [rsp+arg_0], rbx
0x18003eb39  push    rdi
0x18003eb3a  sub     rsp, 20h
0x18003eb3e  mov     ebx, edx
0x18003eb40  mov     rdi, rcx
0x18003eb43  mov     eax, edx
0x18003eb45  test    edx, edx
0x18003eb47  jz      loc_18003EBD8
0x18003eb4d  sub     eax, 1
0x18003eb50  jz      short loc_18003EB80
0x18003eb52  sub     eax, 1
0x18003eb55  jz      short loc_18003EB67
0x18003eb57  cmp     eax, 1
0x18003eb5a  jz      loc_18003EBF4
0x18003eb60  xor     eax, eax
0x18003eb62  jmp     loc_18003EC21
0x18003eb67  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18003eb6d  xor     edx, edx; lpTlsValue
0x18003eb6f  call    cs:__imp_TlsSetValue
0x18003eb76  nop     dword ptr [rax+rax+00h]
0x18003eb7b  jmp     loc_18003EC1C
0x18003eb80  mov     ecx, 1B70h; Size
0x18003eb85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003eb8a  mov     rbx, rax
0x18003eb8d  test    rax, rax
0x18003eb90  jz      short loc_18003EBA1
0x18003eb92  mov     rcx, rax; this
0x18003eb95  call    ??0RegistryBasedThrottle@@QEAA@XZ; RegistryBasedThrottle::RegistryBasedThrottle(void)
0x18003eb9a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18003eb9f  jmp     short loc_18003EBA3
0x18003eba1  xor     ebx, ebx
0x18003eba3  mov     rcx, rdi
0x18003eba6  mov     cs:g_pTraceLoggingClient, rbx
0x18003ebad  call    AttachProcess
0x18003ebb2  mov     ebx, eax
0x18003ebb4  test    eax, eax
0x18003ebb6  jnz     short loc_18003EBD4
0x18003ebb8  mov     rcx, cs:g_pTraceLoggingClient; this
0x18003ebbf  test    rcx, rcx
0x18003ebc2  jz      short loc_18003EBD4
0x18003ebc4  call    ??_GTraceLoggingClient@@QEAAPEAXI@Z; TraceLoggingClient::`scalar deleting destructor'(uint)
0x18003ebc9  mov     cs:g_pTraceLoggingClient, 0
0x18003ebd4  mov     eax, ebx
0x18003ebd6  jmp     short loc_18003EC21
0x18003ebd8  mov     rcx, cs:g_pTraceLoggingClient; this
0x18003ebdf  test    rcx, rcx
0x18003ebe2  jz      short loc_18003EBF4
0x18003ebe4  call    ??_GTraceLoggingClient@@QEAAPEAXI@Z; TraceLoggingClient::`scalar deleting destructor'(uint)
0x18003ebe9  mov     cs:g_pTraceLoggingClient, 0
0x18003ebf4  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18003ebfa  call    cs:__imp_TlsGetValue
0x18003ec01  nop     dword ptr [rax+rax+00h]
0x18003ec06  test    rax, rax
0x18003ec09  jz      short loc_18003EC13
0x18003ec0b  mov     rcx, rax; this
0x18003ec0e  call    ??_GThreadGlobals@@AEAAPEAXI@Z; ThreadGlobals::`scalar deleting destructor'(uint)
0x18003ec13  test    ebx, ebx
0x18003ec15  jnz     short loc_18003EC1C
0x18003ec17  call    DetachProcess
0x18003ec1c  mov     eax, 1
0x18003ec21  mov     rbx, [rsp+28h+arg_0]
0x18003ec26  add     rsp, 20h
0x18003ec2a  pop     rdi
0x18003ec2b  retn
```
