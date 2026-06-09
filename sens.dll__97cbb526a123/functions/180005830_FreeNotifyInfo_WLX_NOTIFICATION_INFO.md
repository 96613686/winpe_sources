# FreeNotifyInfo(_WLX_NOTIFICATION_INFO *)

- ea: `0x180005830`
- end: `0x180005888`
- name: `?FreeNotifyInfo@@YAXPEAU_WLX_NOTIFICATION_INFO@@@Z`
- size: `88`
- prototype: `void __fastcall(struct _WLX_NOTIFICATION_INFO *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180004e00`
- `0x180004e70`
- `0x180004f10`
- `0x1800050b0`
- `0x1800051d0`
- `0x180005270`
- `0x180005da0`
- `0x180005f20`
- `0x180009840`
- `0x1800098a0`

## callees

- `0x180005830`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005842`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005842`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005855`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005868`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005855`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005868`

## pseudocode

```c
void __fastcall FreeNotifyInfo(struct _WLX_NOTIFICATION_INFO *a1)
{
  HANDLE hToken; // rcx

  hToken = a1->hToken;
  if ( hToken )
    CloseHandle(hToken);
  HeapFree(ghSensHeap, 0, a1->UserName);
  HeapFree(ghSensHeap, 0, a1->Domain);
  *(_OWORD *)&a1->Size = 0;
  *(_OWORD *)&a1->Domain = 0;
  *(_OWORD *)&a1->hToken = 0;
  a1->pStatusCallback = 0;
}

```

## disassembly

```asm
0x180005830  push    rbx
0x180005832  sub     rsp, 20h
0x180005836  mov     rbx, rcx
0x180005839  mov     rcx, [rcx+20h]; hObject
0x18000583d  test    rcx, rcx
0x180005840  jz      short loc_180005848
0x180005842  call    cs:__imp_CloseHandle
0x180005848  mov     r8, [rbx+8]; lpMem
0x18000584c  xor     edx, edx; dwFlags
0x18000584e  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180005855  call    cs:__imp_HeapFree
0x18000585b  mov     r8, [rbx+10h]; lpMem
0x18000585f  xor     edx, edx; dwFlags
0x180005861  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180005868  call    cs:__imp_HeapFree
0x18000586e  xorps   xmm0, xmm0
0x180005871  xor     eax, eax
0x180005873  movups  xmmword ptr [rbx], xmm0
0x180005876  movups  xmmword ptr [rbx+10h], xmm0
0x18000587a  movups  xmmword ptr [rbx+20h], xmm0
0x18000587e  mov     [rbx+30h], rax
0x180005882  add     rsp, 20h
0x180005886  pop     rbx
0x180005887  retn
```
