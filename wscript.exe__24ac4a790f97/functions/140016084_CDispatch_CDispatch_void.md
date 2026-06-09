# CDispatch::~CDispatch(void)

- ea: `0x140016084`
- end: `0x1400160f8`
- name: `??1CDispatch@@UEAA@XZ`
- size: `116`
- prototype: `void __fastcall(CDispatch *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140011adc`
- `0x140011bd8`
- `0x140011c3c`
- `0x1400140ac`
- `0x140016100`

## callees

- `0x140016084`
- `0x140018010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400160ac`
- `KERNEL32!EnterCriticalSection` at `0x1400160ac`
- `KERNEL32!LeaveCriticalSection` at `0x1400160d6`
- `KERNEL32!LeaveCriticalSection` at `0x1400160d6`

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
0x140016084  mov     [rsp+arg_0], rbx
0x140016089  push    rdi
0x14001608a  sub     rsp, 20h
0x14001608e  cmp     byte ptr [rcx+30h], 0
0x140016092  lea     rax, ??_7CDispatch@@6B@; const CDispatch::`vftable'
0x140016099  mov     [rcx], rax
0x14001609c  mov     rbx, rcx
0x14001609f  jz      short loc_1400160DC
0x1400160a1  mov     rdi, [rcx+28h]
0x1400160a5  lea     rcx, ?s_oCS@CDispatch@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400160ac  call    cs:__imp_EnterCriticalSection
0x1400160b2  mov     rcx, [rdi+38h]
0x1400160b6  test    rcx, rcx
0x1400160b9  jz      short loc_1400160C7
0x1400160bb  mov     rax, [rcx]
0x1400160be  mov     rax, [rax+10h]
0x1400160c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400160c7  lea     rcx, ?s_oCS@CDispatch@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400160ce  mov     qword ptr [rdi+38h], 0
0x1400160d6  call    cs:__imp_LeaveCriticalSection
0x1400160dc  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x1400160e3  mov     [rbx], rax
0x1400160e6  lock dec cs:?g_cObjects@Global@@2JA; long Global::g_cObjects
0x1400160ed  mov     rbx, [rsp+28h+arg_0]
0x1400160f2  add     rsp, 20h
0x1400160f6  pop     rdi
0x1400160f7  retn
```
