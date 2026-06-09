# TraceCleanUpServer(x)

- ea: `0x1000983c`
- end: `0x10009971`
- name: `_TraceCleanUpServer@4`
- size: `309`
- prototype: `int __thiscall(HGLOBAL hMem)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x10009b20`
- `0x10009e7c`

## callees

- `0x100023a6`
- `0x10002439`
- `0x1000983c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10009920`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10009947`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10009961`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10009920`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10009947`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10009961`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10009919`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10009940`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000995a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10009919`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x10009940`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000995a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000988d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100098a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100098bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000990e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000988d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100098a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100098bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1000990e`
- `api-ms-win-core-console-l1-2-0!FreeConsole` at `0x100098d0`
- `api-ms-win-core-console-l1-2-0!FreeConsole` at `0x100098d0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1000992b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1000992b`

## pseudocode

```c
int __thiscall TraceCleanUpServer(char *hMem)
{
  volatile __int32 *i; // edi
  bool v3; // zf
  int v4; // eax
  char *v5; // edi
  int v6; // edx
  char *v7; // eax
  char **v8; // ecx
  HANDLE ProcessHeap; // eax
  HANDLE v10; // eax
  HANDLE v11; // eax
  void *v13; // [esp+8h] [ebp-Ch]
  void *v14; // [esp+8h] [ebp-Ch]
  char *lpMem; // [esp+Ch] [ebp-8h]
  HANDLE hObject; // [esp+10h] [ebp-4h]

  if ( *((_DWORD *)hMem + 7) )
    DeleteReadWriteLock((LPCRITICAL_SECTION)hMem);
  for ( i = (volatile __int32 *)(hMem + 308); i < (volatile __int32 *)hMem + 137; ++i )
  {
    if ( *i )
      TraceDeleteClientA((int)hMem, i);
  }
  v3 = *((_DWORD *)hMem + 14) == 0;
  *((_DWORD *)hMem + 10) = 60;
  *((_DWORD *)hMem + 9) = 0;
  if ( !v3 )
  {
    CloseHandle(*((HANDLE *)hMem + 14));
    *((_DWORD *)hMem + 14) = 0;
  }
  if ( *((_DWORD *)hMem + 13) )
  {
    CloseHandle(*((HANDLE *)hMem + 13));
    *((_DWORD *)hMem + 13) = 0;
  }
  v4 = *((_DWORD *)hMem + 12);
  if ( v4 && v4 != -1 )
  {
    CloseHandle(*((HANDLE *)hMem + 12));
    *((_DWORD *)hMem + 12) = 0;
  }
  if ( *((_DWORD *)hMem + 11) == 1 )
  {
    FreeConsole();
    *((_DWORD *)hMem + 11) = 0;
  }
  *((_DWORD *)hMem + 8) = 0;
  v5 = (char *)*((_DWORD *)hMem + 15);
  while ( v5 != hMem + 60 )
  {
    v6 = *(_DWORD *)v5;
    hObject = (HANDLE)*((_DWORD *)v5 + 2);
    v7 = v5;
    lpMem = v5;
    v5 = (char *)v6;
    v8 = (char **)*((_DWORD *)lpMem + 1);
    if ( *(char **)(v6 + 4) != lpMem || *v8 != v7 )
      __fastfail(3u);
    *v8 = (char *)v6;
    *(_DWORD *)(v6 + 4) = v8;
    CloseHandle(hObject);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  GlobalFree(hMem);
  if ( g_FormatBuffer )
  {
    v13 = g_FormatBuffer;
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v13);
  }
  if ( g_PrintBuffer )
  {
    v14 = g_PrintBuffer;
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v14);
  }
  return 1;
}

```

## disassembly

```asm
0x1000983c  mov     edi, edi
0x1000983e  push    ebp
0x1000983f  mov     ebp, esp
0x10009841  push    ecx
0x10009842  push    ecx
0x10009843  push    ebx
0x10009844  push    esi
0x10009845  mov     esi, ecx
0x10009847  push    edi
0x10009848  cmp     dword ptr [esi+1Ch], 0
0x1000984c  jz      short loc_10009853
0x1000984e  call    _DeleteReadWriteLock@4; DeleteReadWriteLock(x)
0x10009853  lea     edi, [esi+134h]
0x10009859  lea     ebx, [edi+0F0h]
0x1000985f  jmp     short loc_10009872
0x10009861  cmp     dword ptr [edi], 0
0x10009864  jz      short loc_1000986F
0x10009866  mov     edx, edi
0x10009868  mov     ecx, esi
0x1000986a  call    _TraceDeleteClientA@8; TraceDeleteClientA(x,x)
0x1000986f  add     edi, 4
0x10009872  cmp     edi, ebx
0x10009874  jb      short loc_10009861
0x10009876  cmp     dword ptr [esi+38h], 0
0x1000987a  mov     dword ptr [esi+28h], 3Ch ; '<'
0x10009881  mov     dword ptr [esi+24h], 0
0x10009888  jz      short loc_1000989A
0x1000988a  push    dword ptr [esi+38h]; hObject
0x1000988d  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10009893  mov     dword ptr [esi+38h], 0
0x1000989a  cmp     dword ptr [esi+34h], 0
0x1000989e  jz      short loc_100098B0
0x100098a0  push    dword ptr [esi+34h]; hObject
0x100098a3  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100098a9  mov     dword ptr [esi+34h], 0
0x100098b0  mov     eax, [esi+30h]
0x100098b3  test    eax, eax
0x100098b5  jz      short loc_100098CA
0x100098b7  cmp     eax, 0FFFFFFFFh
0x100098ba  jz      short loc_100098CA
0x100098bc  push    eax; hObject
0x100098bd  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100098c3  mov     dword ptr [esi+30h], 0
0x100098ca  cmp     dword ptr [esi+2Ch], 1
0x100098ce  jnz     short loc_100098DD
0x100098d0  call    ds:__imp__FreeConsole@0; FreeConsole()
0x100098d6  mov     dword ptr [esi+2Ch], 0
0x100098dd  lea     ebx, [esi+3Ch]
0x100098e0  mov     dword ptr [esi+20h], 0
0x100098e7  mov     edi, [ebx]
0x100098e9  jmp     short loc_10009926
0x100098eb  mov     eax, [edi+8]
0x100098ee  mov     edx, [edi]
0x100098f0  mov     [ebp+hObject], eax
0x100098f3  mov     eax, edi
0x100098f5  mov     [ebp+lpMem], eax
0x100098f8  mov     edi, edx
0x100098fa  mov     ecx, [eax+4]
0x100098fd  cmp     [edx+4], eax
0x10009900  jnz     short loc_1000996C
0x10009902  cmp     [ecx], eax
0x10009904  jnz     short loc_1000996C
0x10009906  push    [ebp+hObject]; hObject
0x10009909  mov     [ecx], edx
0x1000990b  mov     [edx+4], ecx
0x1000990e  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10009914  push    [ebp+lpMem]; lpMem
0x10009917  push    0; dwFlags
0x10009919  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x1000991f  push    eax; hHeap
0x10009920  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10009926  cmp     edi, ebx
0x10009928  jnz     short loc_100098EB
0x1000992a  push    esi; hMem
0x1000992b  call    ds:__imp__GlobalFree@4; GlobalFree(x)
0x10009931  mov     eax, _g_FormatBuffer
0x10009936  pop     edi
0x10009937  pop     esi
0x10009938  pop     ebx
0x10009939  test    eax, eax
0x1000993b  jz      short loc_1000994D
0x1000993d  push    eax; lpMem
0x1000993e  push    0; dwFlags
0x10009940  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10009946  push    eax; hHeap
0x10009947  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x1000994d  mov     ecx, _g_PrintBuffer
0x10009953  test    ecx, ecx
0x10009955  jz      short loc_10009967
0x10009957  push    ecx; lpMem
0x10009958  push    0; dwFlags
0x1000995a  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10009960  push    eax; hHeap
0x10009961  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10009967  xor     eax, eax
0x10009969  inc     eax
0x1000996a  leave
0x1000996b  retn
0x1000996c  push    3
0x1000996e  pop     ecx
0x1000996f  int     29h; Win8: RtlFailFast(ecx)
```
