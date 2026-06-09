# ConfigureMiniports

- ea: `0x1800067b4`
- end: `0x180006959`
- name: `ConfigureMiniports`
- size: `421`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1800056e0`
- `0x180005e30`
- `0x180006290`

## callees

- `0x180006290`
- `0x1800067b4`
- `0x180006e88`
- `0x180007ae4`
- `0x180008ac0`
- `0x180017740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006858`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006858`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180006830`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180006830`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000692a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000692a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006844`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006939`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006939`

## pseudocode

```c
__int64 __fastcall ConfigureMiniports(int a1, int a2, _QWORD *a3, LPVOID *a4)
{
  int v5; // eax
  int v6; // edx
  int updated; // eax
  unsigned int MiniportDevices; // ebx
  HANDLE MutexW; // rax
  void *v13; // r15
  signed int v14; // eax
  unsigned int v15; // r14d
  unsigned int v16; // ecx
  unsigned int inited; // eax
  void *v18; // r12
  void *v20; // [rsp+20h] [rbp-58h] BYREF
  __int64 v21[10]; // [rsp+28h] [rbp-50h] BYREF

  v21[0] = 0;
  v20 = 0;
  v5 = a2 & 0x10;
  v6 = 8;
  if ( (a2 & 8) != 0 && v5 )
    goto LABEL_3;
  if ( (a2 & 1) != 0 && v5 )
  {
    v6 = 1;
LABEL_3:
    updated = UpdateMiniportsEnabledRegistry(a1, v6);
    goto LABEL_4;
  }
  MutexW = CreateMutexW(0, 0, L"Global\\RasMpDevices");
  v13 = MutexW;
  if ( MutexW )
  {
    v14 = WaitForSingleObject(MutexW, 0xFFFFFFFF);
    MiniportDevices = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        MiniportDevices = (unsigned __int16)v14 | 0x80070000;
      goto LABEL_34;
    }
    MiniportDevices = 0;
    if ( (a2 & 2) != 0 )
    {
      if ( a2 == 2 )
      {
        CloseMiniportDevices(a3);
        if ( a4 )
          ClosePDeviceEntry(*a4);
      }
      else
      {
        MiniportDevices = -2147024809;
      }
      goto LABEL_33;
    }
    if ( (a2 & 1) != 0 )
    {
      v15 = 0;
      v16 = a1;
      if ( a1 )
      {
        do
        {
          v15 += v16 & 1;
          v16 >>= 1;
        }
        while ( v16 );
      }
      inited = InitRrasRootEnum(&v20);
      v18 = v20;
      MiniportDevices = inited;
      if ( inited )
      {
        if ( inited != -2147024713 )
          goto LABEL_33;
      }
      else if ( !v20 )
      {
LABEL_28:
        MiniportDevices = 1;
        goto LABEL_33;
      }
      MiniportDevices = CreateMiniportDevices(a1, v15, a2, v21);
      if ( !MiniportDevices )
      {
        if ( v21[0] )
        {
          if ( a3 )
            *a3 = v21[0];
          if ( a4 )
            *a4 = v18;
          goto LABEL_33;
        }
        goto LABEL_28;
      }
    }
LABEL_33:
    ReleaseMutex(v13);
LABEL_34:
    CloseHandle(v13);
    return MiniportDevices;
  }
  updated = GetLastError();
LABEL_4:
  MiniportDevices = updated;
  if ( updated > 0 )
    return (unsigned __int16)updated | 0x80070000;
  return MiniportDevices;
}

```

## disassembly

```asm
0x1800067b4  push    rbx
0x1800067b6  push    rbp
0x1800067b7  push    rsi
0x1800067b8  push    rdi
0x1800067b9  push    r12
0x1800067bb  push    r13
0x1800067bd  push    r14
0x1800067bf  push    r15
0x1800067c1  sub     rsp, 38h
0x1800067c5  mov     eax, edx
0x1800067c7  mov     [rsp+78h+var_50], 0
0x1800067d0  mov     esi, edx
0x1800067d2  mov     [rsp+78h+var_58], 0
0x1800067db  and     eax, 10h
0x1800067de  mov     edx, 8
0x1800067e3  mov     rdi, r9
0x1800067e6  mov     r13, r8
0x1800067e9  mov     ebp, ecx
0x1800067eb  test    dl, sil
0x1800067ee  jz      short loc_180006811
0x1800067f0  test    eax, eax
0x1800067f2  jz      short loc_180006811
0x1800067f4  call    UpdateMiniportsEnabledRegistry
0x1800067f9  mov     ebx, eax
0x1800067fb  test    eax, eax
0x1800067fd  jle     loc_180006945
0x180006803  movzx   ebx, ax
0x180006806  or      ebx, 80070000h
0x18000680c  jmp     loc_180006945
0x180006811  mov     r14d, esi
0x180006814  and     r14d, 1
0x180006818  jz      short loc_180006825
0x18000681a  test    eax, eax
0x18000681c  jz      short loc_180006825
0x18000681e  mov     edx, 1
0x180006823  jmp     short loc_1800067F4
0x180006825  lea     r8, Name; "Global\\RasMpDevices"
0x18000682c  xor     edx, edx; bInitialOwner
0x18000682e  xor     ecx, ecx; lpMutexAttributes
0x180006830  call    cs:__imp_CreateMutexW
0x180006837  nop     dword ptr [rax+rax+00h]
0x18000683c  mov     r15, rax
0x18000683f  test    rax, rax
0x180006842  jnz     short loc_180006852
0x180006844  call    cs:__imp_GetLastError
0x18000684b  nop     dword ptr [rax+rax+00h]
0x180006850  jmp     short loc_1800067F9
0x180006852  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006855  mov     rcx, r15; hHandle
0x180006858  call    cs:__imp_WaitForSingleObject
0x18000685f  nop     dword ptr [rax+rax+00h]
0x180006864  mov     ebx, eax
0x180006866  test    eax, eax
0x180006868  jz      short loc_18000687E
0x18000686a  jle     loc_180006936
0x180006870  movzx   ebx, ax
0x180006873  or      ebx, 80070000h
0x180006879  jmp     loc_180006936
0x18000687e  xor     ebx, ebx
0x180006880  test    sil, 2
0x180006884  jz      short loc_1800068B0
0x180006886  cmp     esi, 2
0x180006889  jz      short loc_180006895
0x18000688b  mov     ebx, 80070057h
0x180006890  jmp     loc_180006927
0x180006895  mov     rcx, r13
0x180006898  call    CloseMiniportDevices
0x18000689d  test    rdi, rdi
0x1800068a0  jz      loc_180006927
0x1800068a6  mov     rcx, [rdi]; lpMem
0x1800068a9  call    ClosePDeviceEntry
0x1800068ae  jmp     short loc_180006927
0x1800068b0  test    r14d, r14d
0x1800068b3  jz      short loc_180006927
0x1800068b5  xor     r14d, r14d
0x1800068b8  mov     ecx, ebp
0x1800068ba  test    ebp, ebp
0x1800068bc  jz      short loc_1800068CA
0x1800068be  mov     eax, ecx
0x1800068c0  and     eax, 1
0x1800068c3  add     r14d, eax
0x1800068c6  shr     ecx, 1
0x1800068c8  jnz     short loc_1800068BE
0x1800068ca  lea     rcx, [rsp+78h+var_58]
0x1800068cf  call    InitRrasRootEnum
0x1800068d4  mov     r12, [rsp+78h+var_58]
0x1800068d9  mov     ebx, eax
0x1800068db  test    eax, eax
0x1800068dd  jnz     short loc_1800068E6
0x1800068df  test    r12, r12
0x1800068e2  jz      short loc_18000690F
0x1800068e4  jmp     short loc_1800068ED
0x1800068e6  cmp     eax, 800700B7h
0x1800068eb  jnz     short loc_180006927
0x1800068ed  lea     r9, [rsp+78h+var_50]
0x1800068f2  mov     r8d, esi
0x1800068f5  mov     edx, r14d
0x1800068f8  mov     ecx, ebp
0x1800068fa  call    CreateMiniportDevices
0x1800068ff  mov     ebx, eax
0x180006901  test    eax, eax
0x180006903  jnz     short loc_180006927
0x180006905  mov     rax, [rsp+78h+var_50]
0x18000690a  test    rax, rax
0x18000690d  jnz     short loc_180006916
0x18000690f  mov     ebx, 1
0x180006914  jmp     short loc_180006927
0x180006916  test    r13, r13
0x180006919  jz      short loc_18000691F
0x18000691b  mov     [r13+0], rax
0x18000691f  test    rdi, rdi
0x180006922  jz      short loc_180006927
0x180006924  mov     [rdi], r12
0x180006927  mov     rcx, r15; hMutex
0x18000692a  call    cs:__imp_ReleaseMutex
0x180006931  nop     dword ptr [rax+rax+00h]
0x180006936  mov     rcx, r15; hObject
0x180006939  call    cs:__imp_CloseHandle
0x180006940  nop     dword ptr [rax+rax+00h]
0x180006945  mov     eax, ebx
0x180006947  add     rsp, 38h
0x18000694b  pop     r15
0x18000694d  pop     r14
0x18000694f  pop     r13
0x180006951  pop     r12
0x180006953  pop     rdi
0x180006954  pop     rsi
0x180006955  pop     rbp
0x180006956  pop     rbx
0x180006957  retn
```
