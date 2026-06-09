# Service_AddRef(void)

- ea: `0x180003150`
- end: `0x1800031a1`
- name: `?Service_AddRef@@YAJXZ`
- size: `81`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800018c0`
- `0x18000e260`

## callees

- `0x180003150`
- `0x180007f28`

## pseudocode

```c
__int64 Service_AddRef(void)
{
  unsigned __int32 v0; // ebx

  v0 = _InterlockedIncrement(&g_RefCount);
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, v0);
  }
  return v0;
}

```

## disassembly

```asm
0x180003150  push    rbx
0x180003152  sub     rsp, 20h
0x180003156  mov     ebx, 1
0x18000315b  lock xadd cs:?g_RefCount@@3JA, ebx; long g_RefCount
0x180003163  inc     ebx
0x180003165  mov     rcx, cs:WPP_GLOBAL_Control
0x18000316c  lea     rax, WPP_GLOBAL_Control
0x180003173  cmp     rcx, rax
0x180003176  jz      short loc_180003199
0x180003178  test    dword ptr [rcx+1Ch], 200h
0x18000317f  jz      short loc_180003199
0x180003181  mov     rcx, [rcx+10h]
0x180003185  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x18000318c  mov     edx, 12h
0x180003191  mov     r9d, ebx
0x180003194  call    WPP_SF_d
0x180003199  mov     eax, ebx
0x18000319b  add     rsp, 20h
0x18000319f  pop     rbx
0x1800031a0  retn
```
