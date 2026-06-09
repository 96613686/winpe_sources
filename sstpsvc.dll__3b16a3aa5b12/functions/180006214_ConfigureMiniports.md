# ConfigureMiniports

- ea: `0x180006214`
- end: `0x18000639a`
- name: `ConfigureMiniports`
- size: `390`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180005280`
- `0x180005920`
- `0x180005d50`

## callees

- `0x180005d50`
- `0x180006214`
- `0x180006870`
- `0x1800073d8`
- `0x1800081c0`
- `0x180016514`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800062ac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800062ac`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180006290`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180006290`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006378`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000629e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000629e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006381`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006381`

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
0x180006214  push    rbx
0x180006216  push    rbp
0x180006217  push    rsi
0x180006218  push    rdi
0x180006219  push    r12
0x18000621b  push    r13
0x18000621d  push    r14
0x18000621f  push    r15
0x180006221  sub     rsp, 38h
0x180006225  mov     eax, edx
0x180006227  mov     [rsp+78h+var_50], 0
0x180006230  mov     esi, edx
0x180006232  mov     [rsp+78h+var_58], 0
0x18000623b  and     eax, 10h
0x18000623e  mov     edx, 8
0x180006243  mov     rdi, r9
0x180006246  mov     r13, r8
0x180006249  mov     ebp, ecx
0x18000624b  test    dl, sil
0x18000624e  jz      short loc_180006271
0x180006250  test    eax, eax
0x180006252  jz      short loc_180006271
0x180006254  call    UpdateMiniportsEnabledRegistry
0x180006259  mov     ebx, eax
0x18000625b  test    eax, eax
0x18000625d  jle     loc_180006387
0x180006263  movzx   ebx, ax
0x180006266  or      ebx, 80070000h
0x18000626c  jmp     loc_180006387
0x180006271  mov     r14d, esi
0x180006274  and     r14d, 1
0x180006278  jz      short loc_180006285
0x18000627a  test    eax, eax
0x18000627c  jz      short loc_180006285
0x18000627e  mov     edx, 1
0x180006283  jmp     short loc_180006254
0x180006285  lea     r8, Name; "Global\\RasMpDevices"
0x18000628c  xor     edx, edx; bInitialOwner
0x18000628e  xor     ecx, ecx; lpMutexAttributes
0x180006290  call    cs:__imp_CreateMutexW
0x180006296  mov     r15, rax
0x180006299  test    rax, rax
0x18000629c  jnz     short loc_1800062A6
0x18000629e  call    cs:__imp_GetLastError
0x1800062a4  jmp     short loc_180006259
0x1800062a6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800062a9  mov     rcx, r15; hHandle
0x1800062ac  call    cs:__imp_WaitForSingleObject
0x1800062b2  mov     ebx, eax
0x1800062b4  test    eax, eax
0x1800062b6  jz      short loc_1800062CC
0x1800062b8  jle     loc_18000637E
0x1800062be  movzx   ebx, ax
0x1800062c1  or      ebx, 80070000h
0x1800062c7  jmp     loc_18000637E
0x1800062cc  xor     ebx, ebx
0x1800062ce  test    sil, 2
0x1800062d2  jz      short loc_1800062FE
0x1800062d4  cmp     esi, 2
0x1800062d7  jz      short loc_1800062E3
0x1800062d9  mov     ebx, 80070057h
0x1800062de  jmp     loc_180006375
0x1800062e3  mov     rcx, r13
0x1800062e6  call    CloseMiniportDevices
0x1800062eb  test    rdi, rdi
0x1800062ee  jz      loc_180006375
0x1800062f4  mov     rcx, [rdi]; lpMem
0x1800062f7  call    ClosePDeviceEntry
0x1800062fc  jmp     short loc_180006375
0x1800062fe  test    r14d, r14d
0x180006301  jz      short loc_180006375
0x180006303  xor     r14d, r14d
0x180006306  mov     ecx, ebp
0x180006308  test    ebp, ebp
0x18000630a  jz      short loc_180006318
0x18000630c  mov     eax, ecx
0x18000630e  and     eax, 1
0x180006311  add     r14d, eax
0x180006314  shr     ecx, 1
0x180006316  jnz     short loc_18000630C
0x180006318  lea     rcx, [rsp+78h+var_58]
0x18000631d  call    InitRrasRootEnum
0x180006322  mov     r12, [rsp+78h+var_58]
0x180006327  mov     ebx, eax
0x180006329  test    eax, eax
0x18000632b  jnz     short loc_180006334
0x18000632d  test    r12, r12
0x180006330  jz      short loc_18000635D
0x180006332  jmp     short loc_18000633B
0x180006334  cmp     eax, 800700B7h
0x180006339  jnz     short loc_180006375
0x18000633b  lea     r9, [rsp+78h+var_50]
0x180006340  mov     r8d, esi
0x180006343  mov     edx, r14d
0x180006346  mov     ecx, ebp
0x180006348  call    CreateMiniportDevices
0x18000634d  mov     ebx, eax
0x18000634f  test    eax, eax
0x180006351  jnz     short loc_180006375
0x180006353  mov     rax, [rsp+78h+var_50]
0x180006358  test    rax, rax
0x18000635b  jnz     short loc_180006364
0x18000635d  mov     ebx, 1
0x180006362  jmp     short loc_180006375
0x180006364  test    r13, r13
0x180006367  jz      short loc_18000636D
0x180006369  mov     [r13+0], rax
0x18000636d  test    rdi, rdi
0x180006370  jz      short loc_180006375
0x180006372  mov     [rdi], r12
0x180006375  mov     rcx, r15; hMutex
0x180006378  call    cs:__imp_ReleaseMutex
0x18000637e  mov     rcx, r15; hObject
0x180006381  call    cs:__imp_CloseHandle
0x180006387  mov     eax, ebx
0x180006389  add     rsp, 38h
0x18000638d  pop     r15
0x18000638f  pop     r14
0x180006391  pop     r13
0x180006393  pop     r12
0x180006395  pop     rdi
0x180006396  pop     rsi
0x180006397  pop     rbp
0x180006398  pop     rbx
0x180006399  retn
```
