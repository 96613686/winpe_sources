# PnpServiceTerminateInstallOperations

- ea: `0x1800142c4`
- end: `0x180014328`
- name: `PnpServiceTerminateInstallOperations`
- size: `100`
- prototype: `void()`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x18000ea20`

## callees

- `0x1800142c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800142fb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800142fb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800142da`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014311`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800142da`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014311`

## pseudocode

```c
void PnpServiceTerminateInstallOperations()
{
  unsigned int v0; // ebx
  unsigned int i; // ebx

  v0 = 0;
  while ( PnpServiceOutstandingInstalls )
  {
    Sleep(0x64u);
    v0 += 100;
    if ( v0 >= 0xEA60 )
    {
      if ( PnpServiceOutstandingInstalls )
      {
        SetEvent(PnpServiceShutdownAbortEvent);
        for ( i = 0; i < 0x7530; i += 100 )
        {
          if ( !PnpServiceOutstandingInstalls )
            break;
          Sleep(0x64u);
        }
      }
      return;
    }
  }
}

```

## disassembly

```asm
0x1800142c4  push    rbx
0x1800142c6  sub     rsp, 20h
0x1800142ca  xor     ebx, ebx
0x1800142cc  cmp     cs:PnpServiceOutstandingInstalls, 0
0x1800142d3  jz      short loc_180014322
0x1800142d5  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800142da  call    cs:__imp_Sleep
0x1800142e0  add     ebx, 64h ; 'd'
0x1800142e3  cmp     ebx, 0EA60h
0x1800142e9  jb      short loc_1800142CC
0x1800142eb  cmp     cs:PnpServiceOutstandingInstalls, 0
0x1800142f2  jz      short loc_180014322
0x1800142f4  mov     rcx, cs:PnpServiceShutdownAbortEvent; hEvent
0x1800142fb  call    cs:__imp_SetEvent
0x180014301  xor     ebx, ebx
0x180014303  cmp     cs:PnpServiceOutstandingInstalls, 0
0x18001430a  jz      short loc_180014322
0x18001430c  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180014311  call    cs:__imp_Sleep
0x180014317  add     ebx, 64h ; 'd'
0x18001431a  cmp     ebx, 7530h
0x180014320  jb      short loc_180014303
0x180014322  add     rsp, 20h
0x180014326  pop     rbx
0x180014327  retn
```
