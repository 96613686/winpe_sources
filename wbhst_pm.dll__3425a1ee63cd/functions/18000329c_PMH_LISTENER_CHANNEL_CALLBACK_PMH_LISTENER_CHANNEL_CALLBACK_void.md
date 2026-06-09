# PMH_LISTENER_CHANNEL_CALLBACK::~PMH_LISTENER_CHANNEL_CALLBACK(void)

- ea: `0x18000329c`
- end: `0x1800032d9`
- name: `??1PMH_LISTENER_CHANNEL_CALLBACK@@AEAA@XZ`
- size: `61`
- prototype: `void __fastcall(PMH_LISTENER_CHANNEL_CALLBACK *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800034e0`

## callees

- `0x18000329c`
- `0x180005010`

## pseudocode

```c
void __fastcall PMH_LISTENER_CHANNEL_CALLBACK::~PMH_LISTENER_CHANNEL_CALLBACK(PMH_LISTENER_CHANNEL_CALLBACK *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &PMH_LISTENER_CHANNEL_CALLBACK::`vftable';
  v2 = *((_QWORD *)this + 3);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    *((_QWORD *)this + 3) = 0;
  }
  *((_DWORD *)this + 4) = 1483499632;
}

```

## disassembly

```asm
0x18000329c  push    rbx
0x18000329e  sub     rsp, 20h
0x1800032a2  lea     rax, ??_7PMH_LISTENER_CHANNEL_CALLBACK@@6B@; const PMH_LISTENER_CHANNEL_CALLBACK::`vftable'
0x1800032a9  mov     rbx, rcx
0x1800032ac  mov     [rcx], rax
0x1800032af  mov     rcx, [rcx+18h]
0x1800032b3  test    rcx, rcx
0x1800032b6  jz      short loc_1800032CC
0x1800032b8  mov     rax, [rcx]
0x1800032bb  mov     rax, [rax+8]
0x1800032bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032c4  mov     qword ptr [rbx+18h], 0
0x1800032cc  mov     dword ptr [rbx+10h], 586C6870h
0x1800032d3  add     rsp, 20h
0x1800032d7  pop     rbx
0x1800032d8  retn
```
