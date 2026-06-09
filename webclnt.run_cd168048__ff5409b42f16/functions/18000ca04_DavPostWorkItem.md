# DavPostWorkItem

- ea: `0x18000ca04`
- end: `0x18000ca77`
- name: `DavPostWorkItem`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ce10`

## callees

- `0x18000b7dc`
- `0x18000ca04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca36`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000ca25`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000ca25`

## pseudocode

```c
__int64 __fastcall DavPostWorkItem(__int64 a1, _QWORD *a2)
{
  DWORD LastError; // ebx

  LastError = 0;
  a2[8] = a1;
  _InterlockedIncrement(&DavOutstandingWorkerRequests);
  if ( !TrySubmitThreadpoolCallback((PTP_SIMPLE_CALLBACK)DavRestartContext, a2, &DavCallbackEnviron) )
  {
    _InterlockedDecrement(&DavOutstandingWorkerRequests);
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000ca04  push    rbx
0x18000ca06  sub     rsp, 20h
0x18000ca0a  xor     ebx, ebx
0x18000ca0c  mov     [rdx+40h], rcx
0x18000ca10  lock inc cs:DavOutstandingWorkerRequests
0x18000ca17  lea     r8, DavCallbackEnviron; pcbe
0x18000ca1e  lea     rcx, DavRestartContext; pfns
0x18000ca25  call    cs:__imp_TrySubmitThreadpoolCallback
0x18000ca2b  test    eax, eax
0x18000ca2d  jnz     short loc_18000CA6F
0x18000ca2f  lock dec cs:DavOutstandingWorkerRequests
0x18000ca36  call    cs:__imp_GetLastError
0x18000ca3c  mov     ebx, eax
0x18000ca3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca45  lea     rax, WPP_GLOBAL_Control
0x18000ca4c  cmp     rcx, rax
0x18000ca4f  jz      short loc_18000CA6F
0x18000ca51  test    byte ptr [rcx+1Ch], 1
0x18000ca55  jz      short loc_18000CA6F
0x18000ca57  mov     rcx, [rcx+10h]
0x18000ca5b  lea     r8, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids
0x18000ca62  mov     edx, 16h
0x18000ca67  mov     r9d, ebx
0x18000ca6a  call    WPP_SF_d
0x18000ca6f  mov     eax, ebx
0x18000ca71  add     rsp, 20h
0x18000ca75  pop     rbx
0x18000ca76  retn
```
