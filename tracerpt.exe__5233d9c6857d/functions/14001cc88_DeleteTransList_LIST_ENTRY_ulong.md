# DeleteTransList(_LIST_ENTRY *,ulong)

- ea: `0x14001cc88`
- end: `0x14001cd3a`
- name: `?DeleteTransList@@YAEPEAU_LIST_ENTRY@@K@Z`
- size: `178`
- prototype: `unsigned __int8 __fastcall(struct _LIST_ENTRY *, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14001cb70`
- `0x14001cc88`
- `0x14001fd7c`
- `0x140020310`
- `0x140020748`

## callees

- `0x14001cc88`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x14001cccf`
- `ntdll!RtlEnterCriticalSection` at `0x14001cccf`
- `ntdll!RtlLeaveCriticalSection` at `0x14001cd14`
- `ntdll!RtlLeaveCriticalSection` at `0x14001cd14`

## pseudocode

```c
unsigned __int8 __fastcall DeleteTransList(struct _LIST_ENTRY *a1, unsigned int a2)
{
  struct _LIST_ENTRY *Flink; // rbx
  unsigned int v4; // esi
  struct _LIST_ENTRY *v5; // rbp
  struct _LIST_ENTRY *v6; // rcx
  struct _LIST_ENTRY *Blink; // rax
  _QWORD *v8; // rax

  if ( !a1 || a2 > 0x20 )
    return 0;
  Flink = a1->Flink;
  if ( a1->Flink != a1 )
  {
    v4 = a2 + 1;
    do
    {
      v5 = Flink->Flink;
      DeleteTransList(Flink + 1, v4);
      RtlEnterCriticalSection(&TLCritSect);
      v6 = Flink->Flink;
      if ( Flink->Flink->Blink != Flink
        || (Blink = Flink->Blink, Blink->Flink != Flink)
        || (Blink->Flink = v6,
            v6->Blink = Blink,
            v8 = qword_140082248,
            *((LPVOID **)qword_140082248 + 1) != &qword_140082248) )
      {
        __fastfail(3u);
      }
      Flink->Flink = (struct _LIST_ENTRY *)qword_140082248;
      Flink->Blink = (struct _LIST_ENTRY *)&qword_140082248;
      v8[1] = Flink;
      qword_140082248 = Flink;
      RtlLeaveCriticalSection(&TLCritSect);
      Flink = v5;
    }
    while ( v5 != a1 );
  }
  return 1;
}

```

## disassembly

```asm
0x14001cc88  push    rbx
0x14001cc8a  push    rbp
0x14001cc8b  push    rsi
0x14001cc8c  push    rdi
0x14001cc8d  push    r14
0x14001cc8f  sub     rsp, 20h
0x14001cc93  mov     rdi, rcx
0x14001cc96  test    rcx, rcx
0x14001cc99  jz      loc_14001CD2D
0x14001cc9f  cmp     edx, 20h ; ' '
0x14001cca2  ja      loc_14001CD2D
0x14001cca8  mov     rbx, [rcx]
0x14001ccab  cmp     rbx, rcx
0x14001ccae  jz      short loc_14001CD22
0x14001ccb0  lea     esi, [rdx+1]
0x14001ccb3  lea     r14, qword_140082248
0x14001ccba  mov     rbp, [rbx]
0x14001ccbd  lea     rcx, [rbx+10h]; struct _LIST_ENTRY *
0x14001ccc1  mov     edx, esi; unsigned int
0x14001ccc3  call    ?DeleteTransList@@YAEPEAU_LIST_ENTRY@@K@Z; DeleteTransList(_LIST_ENTRY *,ulong)
0x14001ccc8  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x14001cccf  call    cs:__imp_RtlEnterCriticalSection
0x14001ccd5  mov     rcx, [rbx]
0x14001ccd8  cmp     [rcx+8], rbx
0x14001ccdc  jnz     short loc_14001CD26
0x14001ccde  mov     rax, [rbx+8]
0x14001cce2  cmp     [rax], rbx
0x14001cce5  jnz     short loc_14001CD26
0x14001cce7  mov     [rax], rcx
0x14001ccea  mov     [rcx+8], rax
0x14001ccee  mov     rax, cs:qword_140082248
0x14001ccf5  cmp     [rax+8], r14
0x14001ccf9  jnz     short loc_14001CD26
0x14001ccfb  mov     [rbx], rax
0x14001ccfe  lea     rcx, ?TLCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x14001cd05  mov     [rbx+8], r14
0x14001cd09  mov     [rax+8], rbx
0x14001cd0d  mov     cs:qword_140082248, rbx
0x14001cd14  call    cs:__imp_RtlLeaveCriticalSection
0x14001cd1a  mov     rbx, rbp
0x14001cd1d  cmp     rbp, rdi
0x14001cd20  jnz     short loc_14001CCBA
0x14001cd22  mov     al, 1
0x14001cd24  jmp     short loc_14001CD2F
0x14001cd26  mov     ecx, 3
0x14001cd2b  int     29h; Win8: RtlFailFast(ecx)
0x14001cd2d  xor     al, al
0x14001cd2f  add     rsp, 20h
0x14001cd33  pop     r14
0x14001cd35  pop     rdi
0x14001cd36  pop     rsi
0x14001cd37  pop     rbp
0x14001cd38  pop     rbx
0x14001cd39  retn
```
