# ScriptDllMain

- ea: `0x18003d5fc`
- end: `0x18003d701`
- name: `ScriptDllMain`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18003d5f0`

## callees

- `0x1800358d4`
- `0x180038148`
- `0x180038254`
- `0x180039b7c`
- `0x18003ba7c`
- `0x18003ce80`
- `0x18003d5fc`
- `0x180045490`
- `0x180071874`

## import_xrefs

- `KERNEL32!TlsAlloc` at `0x18003d66c`
- `KERNEL32!TlsAlloc` at `0x18003d66c`
- `KERNEL32!TlsSetValue` at `0x18003d637`
- `KERNEL32!TlsSetValue` at `0x18003d637`
- `KERNEL32!TlsGetValue` at `0x18003d6d5`
- `KERNEL32!TlsGetValue` at `0x18003d6d5`

## pseudocode

```c
__int64 __fastcall ScriptDllMain(HMODULE a1, int a2)
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
    goto LABEL_17;
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
LABEL_17:
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
  g_luTls = TlsAlloc();
  if ( g_luTls == -1 )
  {
    v8 = 0;
    if ( g_pTraceLoggingClient )
    {
      TraceLoggingClient::`scalar deleting destructor'(g_pTraceLoggingClient, v7);
      g_pTraceLoggingClient = 0;
    }
  }
  else
  {
    rtIntlInit();
    g_hInstance = a1;
    InitializeProtectedPolicy();
    return 1;
  }
  return v8;
}

```

## disassembly

```asm
0x18003d5fc  mov     [rsp+arg_0], rbx
0x18003d601  push    rdi
0x18003d602  sub     rsp, 20h
0x18003d606  mov     ebx, edx
0x18003d608  mov     rdi, rcx
0x18003d60b  mov     eax, edx
0x18003d60d  test    edx, edx
0x18003d60f  jz      loc_18003D6B3
0x18003d615  sub     eax, 1
0x18003d618  jz      short loc_18003D642
0x18003d61a  sub     eax, 1
0x18003d61d  jz      short loc_18003D62F
0x18003d61f  cmp     eax, 1
0x18003d622  jz      loc_18003D6CF
0x18003d628  xor     eax, eax
0x18003d62a  jmp     loc_18003D6F6
0x18003d62f  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18003d635  xor     edx, edx; lpTlsValue
0x18003d637  call    cs:__imp_TlsSetValue
0x18003d63d  jmp     loc_18003D6F1
0x18003d642  mov     ecx, 1B70h; Size
0x18003d647  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d64c  mov     rbx, rax
0x18003d64f  test    rax, rax
0x18003d652  jz      short loc_18003D663
0x18003d654  mov     rcx, rax; this
0x18003d657  call    ??0RegistryBasedThrottle@@QEAA@XZ; RegistryBasedThrottle::RegistryBasedThrottle(void)
0x18003d65c  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18003d661  jmp     short loc_18003D665
0x18003d663  xor     ebx, ebx
0x18003d665  mov     cs:g_pTraceLoggingClient, rbx
0x18003d66c  call    cs:__imp_TlsAlloc
0x18003d672  mov     cs:?g_luTls@@3KA, eax; ulong g_luTls
0x18003d678  cmp     eax, 0FFFFFFFFh
0x18003d67b  jnz     short loc_18003D699
0x18003d67d  mov     rcx, cs:g_pTraceLoggingClient; this
0x18003d684  xor     ebx, ebx
0x18003d686  test    rcx, rcx
0x18003d689  jz      short loc_18003D6AF
0x18003d68b  call    ??_GTraceLoggingClient@@QEAAPEAXI@Z; TraceLoggingClient::`scalar deleting destructor'(uint)
0x18003d690  mov     cs:g_pTraceLoggingClient, rbx
0x18003d697  jmp     short loc_18003D6AF
0x18003d699  call    ?rtIntlInit@@YAXXZ; rtIntlInit(void)
0x18003d69e  mov     cs:?g_hInstance@@3PEAXEA, rdi; void * g_hInstance
0x18003d6a5  call    InitializeProtectedPolicy
0x18003d6aa  mov     ebx, 1
0x18003d6af  mov     eax, ebx
0x18003d6b1  jmp     short loc_18003D6F6
0x18003d6b3  mov     rcx, cs:g_pTraceLoggingClient; this
0x18003d6ba  test    rcx, rcx
0x18003d6bd  jz      short loc_18003D6CF
0x18003d6bf  call    ??_GTraceLoggingClient@@QEAAPEAXI@Z; TraceLoggingClient::`scalar deleting destructor'(uint)
0x18003d6c4  mov     cs:g_pTraceLoggingClient, 0
0x18003d6cf  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18003d6d5  call    cs:__imp_TlsGetValue
0x18003d6db  test    rax, rax
0x18003d6de  jz      short loc_18003D6E8
0x18003d6e0  mov     rcx, rax; this
0x18003d6e3  call    ??_GThreadGlobals@@AEAAPEAXI@Z; ThreadGlobals::`scalar deleting destructor'(uint)
0x18003d6e8  test    ebx, ebx
0x18003d6ea  jnz     short loc_18003D6F1
0x18003d6ec  call    DetachProcess
0x18003d6f1  mov     eax, 1
0x18003d6f6  mov     rbx, [rsp+28h+arg_0]
0x18003d6fb  add     rsp, 20h
0x18003d6ff  pop     rdi
0x18003d700  retn
```
