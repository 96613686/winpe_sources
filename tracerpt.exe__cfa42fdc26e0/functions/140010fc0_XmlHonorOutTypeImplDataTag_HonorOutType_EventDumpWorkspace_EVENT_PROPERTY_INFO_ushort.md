# XmlHonorOutTypeImplDataTag::HonorOutType(EventDumpWorkspace *,_EVENT_PROPERTY_INFO *,ushort *)

- ea: `0x140010fc0`
- end: `0x14001101b`
- name: `?HonorOutType@XmlHonorOutTypeImplDataTag@@UEAAHPEAVEventDumpWorkspace@@PEAU_EVENT_PROPERTY_INFO@@PEAG@Z`
- size: `91`
- prototype: `__int64 __fastcall(XmlHonorOutTypeImplDataTag *__hidden this, struct EventDumpWorkspace *, struct _EVENT_PROPERTY_INFO *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140010fc0`

## pseudocode

```c
__int64 __fastcall XmlHonorOutTypeImplDataTag::HonorOutType(
        XmlHonorOutTypeImplDataTag *this,
        struct EventDumpWorkspace *a2,
        struct _EVENT_PROPERTY_INFO *a3,
        unsigned __int16 *a4)
{
  __int64 result; // rax

  if ( (*(_WORD *)(*(_QWORD *)a2 + 4LL) & 0x100) == 0 && (*((_DWORD *)g_TraceContext + 1604) & 0x12000000) != 0 )
  {
    result = 0;
    *a4 = 0;
    return result;
  }
  if ( (unsigned __int16)(a3->nonStructType.OutType - 30) <= 2u )
  {
    *a4 = 18;
  }
  else
  {
    result = 1;
    if ( (unsigned __int16)(a3->nonStructType.InType - 17) > 1u )
      return result;
    *a4 = 33;
  }
  return 0;
}

```

## disassembly

```asm
0x140010fc0  mov     rax, [rdx]
0x140010fc3  mov     ecx, 100h
0x140010fc8  test    [rax+4], cx
0x140010fcc  jnz     short loc_140010FE8
0x140010fce  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140010fd5  test    dword ptr [rax+1910h], 12000000h
0x140010fdf  jz      short loc_140010FE8
0x140010fe1  xor     eax, eax
0x140010fe3  mov     [r9], ax
0x140010fe7  retn
0x140010fe8  movzx   eax, word ptr [r8+0Ah]
0x140010fed  sub     ax, 1Eh
0x140010ff1  cmp     ax, 2
0x140010ff5  jbe     short loc_140011012
0x140010ff7  movzx   ecx, word ptr [r8+8]
0x140010ffc  mov     eax, 1
0x140011001  sub     cx, 11h
0x140011005  cmp     cx, ax
0x140011008  ja      short locret_14001101A
0x14001100a  mov     word ptr [r9], 21h ; '!'
0x140011010  jmp     short loc_140011018
0x140011012  mov     word ptr [r9], 12h
0x140011018  xor     eax, eax
0x14001101a  retn
```
