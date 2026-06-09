# ProcessDetach

- ea: `0x18000fac0`
- end: `0x18000fb95`
- name: `ProcessDetach`
- size: `213`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180011614`

## callees

- `0x180001008`
- `0x18000fac0`
- `0x180010684`
- `0x180013498`
- `0x18001632c`

## import_xrefs

- `ntdll!RtlDestroyHeap` at `0x18000fb61`
- `ntdll!RtlDestroyHeap` at `0x18000fb61`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fb27`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fb27`

## pseudocode

```c
__int64 ProcessDetach()
{
  unsigned int v0; // eax
  int v1; // ecx

  PnpInitialization &= ~0x8000000u;
  TraceLoggingUnregister_EtwEventUnregister();
  v0 = PnpInitialization;
  if ( (PnpInitialization & 2) != 0 )
  {
    TermInstallation();
    v0 = PnpInitialization & 0xFFFFFFFD;
    PnpInitialization &= ~2u;
  }
  if ( (v0 & 4) != 0 )
  {
    pSetupUninitializeUtils();
    v0 = PnpInitialization & 0xFFFFFFFB;
    PnpInitialization &= ~4u;
  }
  v1 = PnpCritSecInitCount;
  if ( PnpCritSecInitCount > 0 )
  {
    do
    {
      PnpCritSecInitCount = v1 - 1;
      DeleteCriticalSection(PnpCritSecInitList[v1 - 1]);
      v1 = PnpCritSecInitCount;
    }
    while ( PnpCritSecInitCount > 0 );
    v0 = PnpInitialization;
  }
  if ( (v0 & 1) != 0 )
  {
    if ( PnpHeapHandle )
    {
      if ( PnpHeapHandle != NtCurrentPeb()->ProcessHeap )
        RtlDestroyHeap(PnpHeapHandle);
      v0 = PnpInitialization;
    }
    PnpHeapHandle = 0;
    PnpInitialization = v0 & 0xFFFFFFFE;
  }
  PnpDllModuleHandle = 0;
  return WppCleanupUm();
}

```

## disassembly

```asm
0x18000fac0  sub     rsp, 28h
0x18000fac4  btr     cs:PnpInitialization, 1Bh
0x18000facc  call    TraceLoggingUnregister_EtwEventUnregister
0x18000fad1  mov     eax, cs:PnpInitialization
0x18000fad7  test    al, 2
0x18000fad9  jz      short loc_18000FAEF
0x18000fadb  call    TermInstallation
0x18000fae0  mov     eax, cs:PnpInitialization
0x18000fae6  and     eax, 0FFFFFFFDh
0x18000fae9  mov     cs:PnpInitialization, eax
0x18000faef  test    al, 4
0x18000faf1  jz      short loc_18000FB07
0x18000faf3  call    pSetupUninitializeUtils
0x18000faf8  mov     eax, cs:PnpInitialization
0x18000fafe  and     eax, 0FFFFFFFBh
0x18000fb01  mov     cs:PnpInitialization, eax
0x18000fb07  mov     ecx, cs:PnpCritSecInitCount
0x18000fb0d  test    ecx, ecx
0x18000fb0f  jle     short loc_18000FB3D
0x18000fb11  dec     ecx
0x18000fb13  lea     rax, PnpCritSecInitList
0x18000fb1a  mov     cs:PnpCritSecInitCount, ecx
0x18000fb20  movsxd  rcx, ecx
0x18000fb23  mov     rcx, [rax+rcx*8]; lpCriticalSection
0x18000fb27  call    cs:__imp_DeleteCriticalSection
0x18000fb2d  mov     ecx, cs:PnpCritSecInitCount
0x18000fb33  test    ecx, ecx
0x18000fb35  jg      short loc_18000FB11
0x18000fb37  mov     eax, cs:PnpInitialization
0x18000fb3d  test    al, 1
0x18000fb3f  jz      short loc_18000FB81
0x18000fb41  cmp     cs:PnpHeapHandle, 0
0x18000fb49  jz      short loc_18000FB6D
0x18000fb4b  mov     rax, gs:60h
0x18000fb54  mov     rcx, cs:PnpHeapHandle; Heap
0x18000fb5b  cmp     rcx, [rax+30h]
0x18000fb5f  jz      short loc_18000FB67
0x18000fb61  call    cs:__imp_RtlDestroyHeap
0x18000fb67  mov     eax, cs:PnpInitialization
0x18000fb6d  and     eax, 0FFFFFFFEh
0x18000fb70  mov     cs:PnpHeapHandle, 0
0x18000fb7b  mov     cs:PnpInitialization, eax
0x18000fb81  mov     cs:PnpDllModuleHandle, 0
0x18000fb8c  add     rsp, 28h
0x18000fb90  jmp     WppCleanupUm
```
