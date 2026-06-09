# WsInitializeRedirector

- ea: `0x180006e0c`
- end: `0x180006e97`
- name: `WsInitializeRedirector`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180006a98`

## callees

- `0x1800061d8`
- `0x180006e0c`
- `0x18000888c`
- `0x18002ed8c`
- `0x18002ee64`

## import_xrefs

- `ntdll!DbgPrint` at `0x180006e26`
- `ntdll!DbgPrint` at `0x180006e48`
- `ntdll!DbgPrint` at `0x180006e68`
- `ntdll!DbgPrint` at `0x180006e7b`
- `ntdll!DbgPrint` at `0x180006e26`
- `ntdll!DbgPrint` at `0x180006e48`
- `ntdll!DbgPrint` at `0x180006e68`
- `ntdll!DbgPrint` at `0x180006e7b`

## string_xrefs

- `0x180006e1f`: `WKSSVC Open redirector returned %lx\n`
- `0x180006e41`: `WKSSVC Open datagram receiver returned %lx\n`
- `0x180006e61`: `WKSSVC Get workstation configuration returned %lx\n`

## pseudocode

```c
__int64 WsInitializeRedirector()
{
  int v0; // eax
  unsigned int v1; // ebx
  int v3; // eax
  int WorkstationConfiguration; // eax

  v0 = WsOpenRedirector();
  v1 = v0;
  if ( v0 )
  {
    DbgPrint("WKSSVC Open redirector returned %lx\n", v0);
    return v1;
  }
  v3 = WsOpenDgReceiver();
  if ( v3 )
    DbgPrint("WKSSVC Open datagram receiver returned %lx\n", v3);
  WorkstationConfiguration = WsGetWorkstationConfiguration();
  v1 = WorkstationConfiguration;
  if ( WorkstationConfiguration )
  {
    DbgPrint("WKSSVC Get workstation configuration returned %lx\n", WorkstationConfiguration);
    DbgPrint("WKSSVC Shut down the redirector\n");
    WsShutdownRedirector();
    return v1;
  }
  return 0;
}

```

## disassembly

```asm
0x180006e0c  push    rbx
0x180006e0e  sub     rsp, 20h
0x180006e12  call    WsOpenRedirector
0x180006e17  mov     ebx, eax
0x180006e19  test    eax, eax
0x180006e1b  jz      short loc_180006E36
0x180006e1d  mov     edx, eax
0x180006e1f  lea     rcx, aWkssvcOpenRedi; "WKSSVC Open redirector returned %lx\n"
0x180006e26  call    cs:__imp_DbgPrint
0x180006e2d  nop     dword ptr [rax+rax+00h]
0x180006e32  mov     eax, ebx
0x180006e34  jmp     short loc_180006E90
0x180006e36  call    WsOpenDgReceiver
0x180006e3b  test    eax, eax
0x180006e3d  jz      short loc_180006E54
0x180006e3f  mov     edx, eax
0x180006e41  lea     rcx, aWkssvcOpenData; "WKSSVC Open datagram receiver returned "...
0x180006e48  call    cs:__imp_DbgPrint
0x180006e4f  nop     dword ptr [rax+rax+00h]
0x180006e54  call    WsGetWorkstationConfiguration
0x180006e59  mov     ebx, eax
0x180006e5b  test    eax, eax
0x180006e5d  jz      short loc_180006E8E
0x180006e5f  mov     edx, eax
0x180006e61  lea     rcx, aWkssvcGetWorks; "WKSSVC Get workstation configuration re"...
0x180006e68  call    cs:__imp_DbgPrint
0x180006e6f  nop     dword ptr [rax+rax+00h]
0x180006e74  lea     rcx, aWkssvcShutDown; "WKSSVC Shut down the redirector\n"
0x180006e7b  call    cs:__imp_DbgPrint
0x180006e82  nop     dword ptr [rax+rax+00h]
0x180006e87  call    WsShutdownRedirector
0x180006e8c  jmp     short loc_180006E32
0x180006e8e  xor     eax, eax
0x180006e90  add     rsp, 20h
0x180006e94  pop     rbx
0x180006e95  retn
```
