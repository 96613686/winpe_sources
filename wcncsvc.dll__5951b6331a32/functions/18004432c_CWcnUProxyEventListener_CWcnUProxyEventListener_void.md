# CWcnUProxyEventListener::~CWcnUProxyEventListener(void)

- ea: `0x18004432c`
- end: `0x180044353`
- name: `??1CWcnUProxyEventListener@@QEAA@XZ`
- size: `39`
- prototype: `void __fastcall(CWcnUProxyEventListener *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800411a0`

## callees

- `0x18004432c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180044348`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180044348`

## pseudocode

```c
void __fastcall CWcnUProxyEventListener::~CWcnUProxyEventListener(CWcnUProxyEventListener *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rcx

  *(_QWORD *)this = &CWcnUProxyEventListener::`vftable';
  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  if ( LOBYTE(v1[1].DebugInfo) )
  {
    LOBYTE(v1[1].DebugInfo) = 0;
    DeleteCriticalSection(v1);
  }
}

```

## disassembly

```asm
0x18004432c  sub     rsp, 28h
0x180044330  lea     rax, ??_7CWcnUProxyEventListener@@6B@; const CWcnUProxyEventListener::`vftable'
0x180044337  mov     [rcx], rax
0x18004433a  add     rcx, 10h; lpCriticalSection
0x18004433e  cmp     byte ptr [rcx+28h], 0
0x180044342  jz      short loc_18004434E
0x180044344  mov     byte ptr [rcx+28h], 0
0x180044348  call    cs:__imp_DeleteCriticalSection
0x18004434e  add     rsp, 28h
0x180044352  retn
```
