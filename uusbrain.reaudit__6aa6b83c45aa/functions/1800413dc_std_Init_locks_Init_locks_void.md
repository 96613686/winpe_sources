# std::_Init_locks::~_Init_locks(void)

- ea: `0x1800413dc`
- end: `0x180041418`
- name: `??1_Init_locks@std@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(std::_Init_locks *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004dce0`
- `0x18004dd00`

## callees

- `0x1800413dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800413fc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800413fc`

## pseudocode

```c
void __fastcall std::_Init_locks::~_Init_locks(std::_Init_locks *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  if ( _InterlockedDecrement(&dword_180062238) < 0 )
  {
    v1 = &CriticalSection;
    do
      DeleteCriticalSection(v1++);
    while ( v1 != (struct _RTL_CRITICAL_SECTION *)&UusComponentMaps::Sessions );
  }
}

```

## disassembly

```asm
0x1800413dc  push    rbx
0x1800413de  sub     rsp, 20h
0x1800413e2  or      eax, 0FFFFFFFFh
0x1800413e5  lock xadd cs:dword_180062238, eax
0x1800413ed  cmp     eax, 1
0x1800413f0  jns     short loc_180041412
0x1800413f2  lea     rbx, CriticalSection
0x1800413f9  mov     rcx, rbx; lpCriticalSection
0x1800413fc  call    cs:__imp_DeleteCriticalSection
0x180041402  lea     rax, ?Sessions@UusComponentMaps@@2V?$map@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@B; std::map<std::wstring const,std::wstring> const UusComponentMaps::Sessions
0x180041409  add     rbx, 28h ; '('
0x18004140d  cmp     rbx, rax
0x180041410  jnz     short loc_1800413F9
0x180041412  add     rsp, 20h
0x180041416  pop     rbx
0x180041417  retn
```
