# ImageLogger::~ImageLogger(void)

- ea: `0x1800268b0`
- end: `0x1800268e7`
- name: `??1ImageLogger@@UEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ImageLogger *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800268f0`
- `0x18002bd50`

## callees

- `0x1800268b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800268e0`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800268cd`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800268cd`

## pseudocode

```c
void __fastcall ImageLogger::~ImageLogger(ImageLogger *this)
{
  bool v1; // zf

  v1 = *((_BYTE *)this + 48) == 0;
  *(_QWORD *)this = &ImageLogger::`vftable';
  if ( !v1 )
  {
    EventUnregister(*((_QWORD *)this + 5));
    *((_BYTE *)this + 48) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
}

```

## disassembly

```asm
0x1800268b0  push    rbx
0x1800268b2  sub     rsp, 20h
0x1800268b6  cmp     byte ptr [rcx+30h], 0
0x1800268ba  lea     rax, ??_7ImageLogger@@6B@; const ImageLogger::`vftable'
0x1800268c1  mov     [rcx], rax
0x1800268c4  mov     rbx, rcx
0x1800268c7  jz      short loc_1800268D7
0x1800268c9  mov     rcx, [rcx+28h]; RegHandle
0x1800268cd  call    cs:__imp_EventUnregister
0x1800268d3  mov     byte ptr [rbx+30h], 0
0x1800268d7  lea     rcx, [rbx+38h]
0x1800268db  add     rsp, 20h
0x1800268df  pop     rbx
0x1800268e0  jmp     cs:__imp_DeleteCriticalSection
```
