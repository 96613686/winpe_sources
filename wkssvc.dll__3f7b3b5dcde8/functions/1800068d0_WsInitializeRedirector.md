# WsInitializeRedirector

- ea: `0x1800068d0`
- end: `0x180006942`
- name: `WsInitializeRedirector`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800065c0`

## callees

- `0x180005dec`
- `0x1800068d0`
- `0x1800083cc`
- `0x18002c4d0`
- `0x18002c59c`

## import_xrefs

- `ntdll!DbgPrint` at `0x1800068ea`
- `ntdll!DbgPrint` at `0x180006906`
- `ntdll!DbgPrint` at `0x180006920`
- `ntdll!DbgPrint` at `0x18000692d`
- `ntdll!DbgPrint` at `0x1800068ea`
- `ntdll!DbgPrint` at `0x180006906`
- `ntdll!DbgPrint` at `0x180006920`
- `ntdll!DbgPrint` at `0x18000692d`

## string_xrefs

- `0x1800068e3`: `WKSSVC Open redirector returned %lx\n`
- `0x1800068ff`: `WKSSVC Open datagram receiver returned %lx\n`
- `0x180006919`: `WKSSVC Get workstation configuration returned %lx\n`

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
0x1800068d0  push    rbx
0x1800068d2  sub     rsp, 20h
0x1800068d6  call    WsOpenRedirector
0x1800068db  mov     ebx, eax
0x1800068dd  test    eax, eax
0x1800068df  jz      short loc_1800068F4
0x1800068e1  mov     edx, eax
0x1800068e3  lea     rcx, aWkssvcOpenRedi; "WKSSVC Open redirector returned %lx\n"
0x1800068ea  call    cs:__imp_DbgPrint
0x1800068f0  mov     eax, ebx
0x1800068f2  jmp     short loc_18000693C
0x1800068f4  call    WsOpenDgReceiver
0x1800068f9  test    eax, eax
0x1800068fb  jz      short loc_18000690C
0x1800068fd  mov     edx, eax
0x1800068ff  lea     rcx, aWkssvcOpenData; "WKSSVC Open datagram receiver returned "...
0x180006906  call    cs:__imp_DbgPrint
0x18000690c  call    WsGetWorkstationConfiguration
0x180006911  mov     ebx, eax
0x180006913  test    eax, eax
0x180006915  jz      short loc_18000693A
0x180006917  mov     edx, eax
0x180006919  lea     rcx, aWkssvcGetWorks; "WKSSVC Get workstation configuration re"...
0x180006920  call    cs:__imp_DbgPrint
0x180006926  lea     rcx, aWkssvcShutDown; "WKSSVC Shut down the redirector\n"
0x18000692d  call    cs:__imp_DbgPrint
0x180006933  call    WsShutdownRedirector
0x180006938  jmp     short loc_1800068F0
0x18000693a  xor     eax, eax
0x18000693c  add     rsp, 20h
0x180006940  pop     rbx
0x180006941  retn
```
