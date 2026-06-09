# MIME_MAP::~MIME_MAP(void)

- ea: `0x1800043d4`
- end: `0x180004410`
- name: `??1MIME_MAP@@UEAA@XZ`
- size: `60`
- prototype: `void __fastcall(MIME_MAP *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004418`
- `0x180004480`

## callees

- `0x1800043d4`
- `0x18000455c`
- `0x180005700`

## pseudocode

```c
void __fastcall MIME_MAP::~MIME_MAP(MIME_MAP *this)
{
  MIME_MAP_TABLE *v2; // rcx

  *(_QWORD *)this = &MIME_MAP::`vftable';
  v2 = (MIME_MAP_TABLE *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    MIME_MAP_TABLE::Dereference(v2);
    *((_QWORD *)this + 2) = 0;
  }
  if ( *((_DWORD *)this + 2) )
    MIME_MAP_TABLE::SetGlobalTable(0);
}

```

## disassembly

```asm
0x1800043d4  push    rbx
0x1800043d6  sub     rsp, 20h
0x1800043da  lea     rax, ??_7MIME_MAP@@6B@; const MIME_MAP::`vftable'
0x1800043e1  mov     rbx, rcx
0x1800043e4  mov     [rcx], rax
0x1800043e7  mov     rcx, [rcx+10h]; this
0x1800043eb  test    rcx, rcx
0x1800043ee  jz      short loc_1800043FD
0x1800043f0  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x1800043f5  mov     qword ptr [rbx+10h], 0
0x1800043fd  cmp     dword ptr [rbx+8], 0
0x180004401  jz      short loc_18000440A
0x180004403  xor     ecx, ecx; struct MIME_MAP_TABLE **
0x180004405  call    ?SetGlobalTable@MIME_MAP_TABLE@@SAXPEAPEAV1@@Z; MIME_MAP_TABLE::SetGlobalTable(MIME_MAP_TABLE * *)
0x18000440a  add     rsp, 20h
0x18000440e  pop     rbx
0x18000440f  retn
```
