# XmlHonorOutTypeImpl::HonorOutType(EventDumpWorkspace *,_EVENT_PROPERTY_INFO *,ushort *)

- ea: `0x140010f80`
- end: `0x140010fae`
- name: `?HonorOutType@XmlHonorOutTypeImpl@@UEAAHPEAVEventDumpWorkspace@@PEAU_EVENT_PROPERTY_INFO@@PEAG@Z`
- size: `46`
- prototype: `__int64 __fastcall(XmlHonorOutTypeImpl *__hidden this, struct EventDumpWorkspace *, struct _EVENT_PROPERTY_INFO *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140010f80`

## pseudocode

```c
__int64 __fastcall XmlHonorOutTypeImpl::HonorOutType(
        XmlHonorOutTypeImpl *this,
        struct EventDumpWorkspace *a2,
        struct _EVENT_PROPERTY_INFO *a3,
        unsigned __int16 *a4)
{
  __int64 result; // rax

  if ( (*(_WORD *)(*(_QWORD *)a2 + 4LL) & 0x100) != 0 || (*((_DWORD *)g_TraceContext + 1604) & 0x12000000) == 0 )
    return 1;
  result = 0;
  *a4 = 0;
  return result;
}

```

## disassembly

```asm
0x140010f80  mov     rax, [rdx]
0x140010f83  mov     ecx, 100h
0x140010f88  test    [rax+4], cx
0x140010f8c  jnz     short loc_140010FA8
0x140010f8e  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140010f95  test    dword ptr [rax+1910h], 12000000h
0x140010f9f  jz      short loc_140010FA8
0x140010fa1  xor     eax, eax
0x140010fa3  mov     [r9], ax
0x140010fa7  retn
0x140010fa8  mov     eax, 1
0x140010fad  retn
```
