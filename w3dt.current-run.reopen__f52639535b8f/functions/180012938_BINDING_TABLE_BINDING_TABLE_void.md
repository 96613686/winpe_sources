# BINDING_TABLE::~BINDING_TABLE(void)

- ea: `0x180012938`
- end: `0x1800129c2`
- name: `??1BINDING_TABLE@@UEAA@XZ`
- size: `138`
- prototype: `void __fastcall(BINDING_TABLE *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180014740`
- `0x180014790`

## callees

- `0x180012938`
- `0x180013084`

## import_xrefs

- `HTTPAPI!HttpCloseRequestQueue` at `0x180012957`
- `HTTPAPI!HttpCloseRequestQueue` at `0x180012957`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800129ac`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800129ac`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800129bb`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001297b`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180012988`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180012995`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800129a2`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x18001297b`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180012988`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180012995`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800129a2`

## pseudocode

```c
void __fastcall BINDING_TABLE::~BINDING_TABLE(BINDING_TABLE *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &BINDING_TABLE::`vftable';
  v2 = (void *)*((_QWORD *)this + 49);
  if ( v2 )
  {
    HttpCloseRequestQueue(v2);
    *((_QWORD *)this + 49) = 0;
  }
  HTTP_WRAPPER::~HTTP_WRAPPER((BINDING_TABLE *)((char *)this + 352));
  MULTISZ::~MULTISZ((BINDING_TABLE *)((char *)this + 296));
  MULTISZ::~MULTISZ((BINDING_TABLE *)((char *)this + 240));
  MULTISZ::~MULTISZ((BINDING_TABLE *)((char *)this + 184));
  MULTISZ::~MULTISZ((BINDING_TABLE *)((char *)this + 128));
  STRU::~STRU((BINDING_TABLE *)((char *)this + 72));
  STRU::~STRU((BINDING_TABLE *)((char *)this + 16));
}

```

## disassembly

```asm
0x180012938  push    rbx
0x18001293a  sub     rsp, 20h
0x18001293e  lea     rax, ??_7BINDING_TABLE@@6B@; const BINDING_TABLE::`vftable'
0x180012945  mov     rbx, rcx
0x180012948  mov     [rcx], rax
0x18001294b  mov     rcx, [rcx+188h]; RequestQueueHandle
0x180012952  test    rcx, rcx
0x180012955  jz      short loc_180012968
0x180012957  call    cs:__imp_HttpCloseRequestQueue
0x18001295d  mov     qword ptr [rbx+188h], 0
0x180012968  lea     rcx, [rbx+160h]; this
0x18001296f  call    ??1HTTP_WRAPPER@@UEAA@XZ; HTTP_WRAPPER::~HTTP_WRAPPER(void)
0x180012974  lea     rcx, [rbx+128h]
0x18001297b  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180012981  lea     rcx, [rbx+0F0h]
0x180012988  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18001298e  lea     rcx, [rbx+0B8h]
0x180012995  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18001299b  lea     rcx, [rbx+80h]
0x1800129a2  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x1800129a8  lea     rcx, [rbx+48h]
0x1800129ac  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800129b2  lea     rcx, [rbx+10h]
0x1800129b6  add     rsp, 20h
0x1800129ba  pop     rbx
0x1800129bb  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
