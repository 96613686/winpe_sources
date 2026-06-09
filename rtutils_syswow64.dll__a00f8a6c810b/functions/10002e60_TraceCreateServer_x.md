# TraceCreateServer(x)

- ea: `0x10002e60`
- end: `0x10002f07`
- name: `_TraceCreateServer@4`
- size: `167`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10002160`
- `0x10002470`
- `0x100030b0`

## callees

- `0x10002439`
- `0x10002e60`
- `0x10002f10`
- `0x10004567`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1000576e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x10005784`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1000576e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x10005784`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x10002e6a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x10002e6a`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *TraceCreateServer()
{
  struct _RTL_CRITICAL_SECTION *v0; // eax
  struct _RTL_CRITICAL_SECTION *v1; // esi
  signed __int32 v2; // edi

  v0 = (struct _RTL_CRITICAL_SECTION *)GlobalAlloc(0x40u, 0x224u);
  v1 = v0;
  if ( !v0 )
    return 0;
  v0[1].RecursionCount = 0;
  v0[2].LockSemaphore = &v0[2].OwningThread;
  v0[2].OwningThread = &v0[2].OwningThread;
  v0[2].DebugInfo = 0;
  v0[1].SpinCount = 0;
  v0[2].LockCount = 0;
  v0[2].RecursionCount = 0;
  v0[1].OwningThread = 0;
  v0[1].LockSemaphore = (HANDLE)60;
  memset(&v0[2].SpinCount, 0, 0xF0u);
  memset(&v1[12].SpinCount, 0, 0xF0u);
  if ( CreateReadWriteLock(v1) )
  {
    _InterlockedCompareExchange((volatile signed __int32 *)&g_server, 0, (signed __int32)v1);
    GlobalFree(v1);
    return 0;
  }
  v2 = _InterlockedCompareExchange((volatile signed __int32 *)&g_server, (signed __int32)v1, 0);
  if ( !v2 )
    return v1;
  if ( v1[1].LockCount )
    DeleteReadWriteLock(v1);
  GlobalFree(v1);
  return (struct _RTL_CRITICAL_SECTION *)v2;
}

```

## disassembly

```asm
0x10002e60  mov     edi, edi
0x10002e62  push    esi
0x10002e63  push    224h; dwBytes
0x10002e68  push    40h ; '@'; uFlags
0x10002e6a  call    ds:__imp__GlobalAlloc@8; GlobalAlloc(x,x)
0x10002e70  mov     esi, eax
0x10002e72  test    esi, esi
0x10002e74  jz      loc_10002F03
0x10002e7a  lea     eax, [esi+3Ch]
0x10002e7d  mov     dword ptr [esi+20h], 0
0x10002e84  push    0F0h; Size
0x10002e89  mov     [eax+4], eax
0x10002e8c  mov     [eax], eax
0x10002e8e  lea     eax, [esi+44h]
0x10002e91  push    0; Val
0x10002e93  push    eax; void *
0x10002e94  mov     dword ptr [esi+30h], 0
0x10002e9b  mov     dword ptr [esi+2Ch], 0
0x10002ea2  mov     dword ptr [esi+34h], 0
0x10002ea9  mov     dword ptr [esi+38h], 0
0x10002eb0  mov     dword ptr [esi+24h], 0
0x10002eb7  mov     dword ptr [esi+28h], 3Ch ; '<'
0x10002ebe  call    _memset
0x10002ec3  push    0F0h; Size
0x10002ec8  lea     eax, [esi+134h]
0x10002ece  push    0; Val
0x10002ed0  push    eax; void *
0x10002ed1  call    _memset
0x10002ed6  add     esp, 18h
0x10002ed9  mov     ecx, esi; lpCriticalSection
0x10002edb  call    _CreateReadWriteLock@4; CreateReadWriteLock(x)
0x10002ee0  mov     edx, offset _g_server
0x10002ee5  test    eax, eax
0x10002ee7  jnz     loc_1000577B
0x10002eed  push    edi
0x10002eee  mov     ecx, esi
0x10002ef0  lock cmpxchg [edx], ecx
0x10002ef4  mov     edi, eax
0x10002ef6  test    edi, edi
0x10002ef8  jnz     loc_10005760
0x10002efe  mov     eax, esi
0x10002f00  pop     edi
0x10002f01  pop     esi
0x10002f02  retn
0x10002f03  xor     eax, eax
0x10002f05  pop     esi
0x10002f06  retn
0x10005760  cmp     dword ptr [esi+1Ch], 0
0x10005764  jz      short loc_1000576D
0x10005766  mov     ecx, esi; lpCriticalSection
0x10005768  call    _DeleteReadWriteLock@4; DeleteReadWriteLock(x)
0x1000576d  push    esi; hMem
0x1000576e  call    ds:__imp__GlobalFree@4; GlobalFree(x)
0x10005774  mov     eax, edi
0x10005776  jmp     loc_10002F00
0x1000577b  xor     ecx, ecx
0x1000577d  mov     eax, esi
0x1000577f  lock cmpxchg [edx], ecx
0x10005783  push    esi; hMem
0x10005784  call    ds:__imp__GlobalFree@4; GlobalFree(x)
0x1000578a  jmp     loc_10002F03
```
