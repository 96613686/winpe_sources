# WTL::CServerAppModule::MonitorProc(void *)

- ea: `0x140003990`
- end: `0x140003a0a`
- name: `?MonitorProc@CServerAppModule@WTL@@SAKPEAX@Z`
- size: `122`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400039a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400039b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400039a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400039b1`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x1400039c7`
- `api-ms-win-core-com-l1-1-0!CoSuspendClassObjects` at `0x1400039c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400039dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400039dd`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostThreadMessageW` at `0x1400039fc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostThreadMessageW` at `0x1400039fc`

## pseudocode

```c
__int64 __fastcall WTL::CServerAppModule::MonitorProc(void *a1)
{
  DWORD v2; // edx
  void *v3; // rcx

  while ( 1 )
  {
    WaitForSingleObject(*((HANDLE *)a1 + 13), 0xFFFFFFFF);
    do
    {
      v2 = *((_DWORD *)a1 + 29);
      v3 = (void *)*((_QWORD *)a1 + 13);
      *((_BYTE *)a1 + 112) = 0;
    }
    while ( !WaitForSingleObject(v3, v2) );
    if ( !*((_BYTE *)a1 + 112) && !*((_DWORD *)a1 + 3) )
    {
      CoSuspendClassObjects();
      if ( !*((_BYTE *)a1 + 112) && !*((_DWORD *)a1 + 3) )
        break;
    }
  }
  if ( CloseHandle(*((HANDLE *)a1 + 13)) )
    *((_QWORD *)a1 + 13) = 0;
  PostThreadMessageW(*((_DWORD *)a1 + 20), 0x12u, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140003990  push    rbx
0x140003992  sub     rsp, 20h
0x140003996  mov     rbx, rcx
0x140003999  mov     rcx, [rbx+68h]; hHandle
0x14000399d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400039a0  call    cs:__imp_WaitForSingleObject
0x1400039a6  mov     edx, [rbx+74h]; dwMilliseconds
0x1400039a9  mov     rcx, [rbx+68h]; hHandle
0x1400039ad  mov     byte ptr [rbx+70h], 0
0x1400039b1  call    cs:__imp_WaitForSingleObject
0x1400039b7  test    eax, eax
0x1400039b9  jz      short loc_1400039A6
0x1400039bb  cmp     byte ptr [rbx+70h], 0
0x1400039bf  jnz     short loc_140003999
0x1400039c1  cmp     dword ptr [rbx+0Ch], 0
0x1400039c5  jnz     short loc_140003999
0x1400039c7  call    cs:__imp_CoSuspendClassObjects
0x1400039cd  cmp     byte ptr [rbx+70h], 0
0x1400039d1  jnz     short loc_140003999
0x1400039d3  cmp     dword ptr [rbx+0Ch], 0
0x1400039d7  jnz     short loc_140003999
0x1400039d9  mov     rcx, [rbx+68h]; hObject
0x1400039dd  call    cs:__imp_CloseHandle
0x1400039e3  test    eax, eax
0x1400039e5  jz      short loc_1400039EF
0x1400039e7  mov     qword ptr [rbx+68h], 0
0x1400039ef  mov     ecx, [rbx+50h]; idThread
0x1400039f2  xor     r9d, r9d; lParam
0x1400039f5  xor     r8d, r8d; wParam
0x1400039f8  lea     edx, [r9+12h]; Msg
0x1400039fc  call    cs:__imp_PostThreadMessageW
0x140003a02  xor     eax, eax
0x140003a04  add     rsp, 20h
0x140003a08  pop     rbx
0x140003a09  retn
```
