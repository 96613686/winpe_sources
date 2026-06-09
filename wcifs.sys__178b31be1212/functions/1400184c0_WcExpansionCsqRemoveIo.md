# WcExpansionCsqRemoveIo

- ea: `0x1400184c0`
- end: `0x1400184e6`
- name: `WcExpansionCsqRemoveIo`
- size: `38`
- prototype: `void __fastcall(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400184c0`

## pseudocode

```c
void __fastcall WcExpansionCsqRemoveIo(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)
{
  union _FLT_CALLBACK_DATA::$312C66EF40AEDAF2A3A5D4554FF51F28 *p_QueueLinks; // rdx
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *Blink; // rax

  p_QueueLinks = (union _FLT_CALLBACK_DATA::$312C66EF40AEDAF2A3A5D4554FF51F28 *)&Cbd->QueueLinks;
  Flink = p_QueueLinks->QueueLinks.Flink;
  if ( (union _FLT_CALLBACK_DATA::$312C66EF40AEDAF2A3A5D4554FF51F28 *)p_QueueLinks->QueueLinks.Flink->Blink != p_QueueLinks
    || (Blink = p_QueueLinks->QueueLinks.Blink,
        (union _FLT_CALLBACK_DATA::$312C66EF40AEDAF2A3A5D4554FF51F28 *)Blink->Flink != p_QueueLinks) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
}

```

## disassembly

```asm
0x1400184c0  add     rdx, 30h ; '0'
0x1400184c4  mov     rcx, [rdx]
0x1400184c7  cmp     [rcx+8], rdx
0x1400184cb  jnz     short loc_1400184DF
0x1400184cd  mov     rax, [rdx+8]
0x1400184d1  cmp     [rax], rdx
0x1400184d4  jnz     short loc_1400184DF
0x1400184d6  mov     [rax], rcx
0x1400184d9  mov     [rcx+8], rax
0x1400184dd  retn
0x1400184df  mov     ecx, 3
0x1400184e4  int     29h; Win8: RtlFailFast(ecx)
```
