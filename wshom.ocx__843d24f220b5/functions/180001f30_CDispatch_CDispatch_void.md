# CDispatch::~CDispatch(void)

- ea: `0x180001f30`
- end: `0x180001fa5`
- name: `??1CDispatch@@UEAA@XZ`
- size: `117`
- prototype: `void __fastcall(CDispatch *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180001e38`
- `0x180001ed0`
- `0x180007180`
- `0x180007b30`
- `0x18000b090`
- `0x18000b100`
- `0x18000d84c`
- `0x18000dde0`

## callees

- `0x180001f30`
- `0x180011010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180001f83`
- `KERNEL32!LeaveCriticalSection` at `0x180001f83`
- `KERNEL32!EnterCriticalSection` at `0x180001f59`
- `KERNEL32!EnterCriticalSection` at `0x180001f59`

## pseudocode

```c
void __fastcall CDispatch::~CDispatch(CDispatch *this)
{
  bool v1; // zf
  __int64 v3; // rdi
  __int64 v4; // rcx

  v1 = *((_BYTE *)this + 48) == 0;
  *(_QWORD *)this = &CDispatch::`vftable';
  if ( !v1 )
  {
    v3 = *((_QWORD *)this + 5);
    EnterCriticalSection(&CDispatch::s_oCS);
    v4 = *(_QWORD *)(v3 + 56);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *(_QWORD *)(v3 + 56) = 0;
    LeaveCriticalSection(&CDispatch::s_oCS);
  }
  *(_QWORD *)this = &CUnknown::`vftable';
  _InterlockedDecrement(&Global::g_cObjects);
}

```

## disassembly

```asm
0x180001f30  push    rbx
0x180001f32  sub     rsp, 20h
0x180001f36  cmp     byte ptr [rcx+30h], 0
0x180001f3a  lea     rax, ??_7CDispatch@@6B@; const CDispatch::`vftable'
0x180001f41  mov     [rcx], rax
0x180001f44  mov     rbx, rcx
0x180001f47  jz      short loc_180001F8E
0x180001f49  mov     [rsp+28h+arg_0], rdi
0x180001f4e  mov     rdi, [rcx+28h]
0x180001f52  lea     rcx, ?s_oCS@CDispatch@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001f59  call    cs:__imp_EnterCriticalSection
0x180001f5f  mov     rcx, [rdi+38h]
0x180001f63  test    rcx, rcx
0x180001f66  jz      short loc_180001F74
0x180001f68  mov     rax, [rcx]
0x180001f6b  mov     rax, [rax+10h]
0x180001f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f74  lea     rcx, ?s_oCS@CDispatch@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001f7b  mov     qword ptr [rdi+38h], 0
0x180001f83  call    cs:__imp_LeaveCriticalSection
0x180001f89  mov     rdi, [rsp+28h+arg_0]
0x180001f8e  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x180001f95  mov     [rbx], rax
0x180001f98  lock dec cs:?g_cObjects@Global@@2JA; long Global::g_cObjects
0x180001f9f  add     rsp, 20h
0x180001fa3  pop     rbx
0x180001fa4  retn
```
