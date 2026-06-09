# BaseConnection::Cleanup(void)

- ea: `0x18005d958`
- end: `0x18005d9a5`
- name: `?Cleanup@BaseConnection@@IEAAXXZ`
- size: `77`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18005d134`
- `0x18005d7f4`

## callees

- `0x18005d958`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005d992`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005d992`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall BaseConnection::Cleanup(struct _RTL_CRITICAL_SECTION *this)
{
  void (__fastcall ***SpinCount)(_QWORD, __int64); // rcx

  SpinCount = (void (__fastcall ***)(_QWORD, __int64))this[2].SpinCount;
  if ( SpinCount )
  {
    (**SpinCount)(SpinCount, 1);
    this[2].SpinCount = 0;
  }
  if ( LOBYTE(this[5].DebugInfo) )
  {
    DeleteCriticalSection(this + 4);
    LOBYTE(this[5].DebugInfo) = 0;
  }
}

```

## disassembly

```asm
0x18005d958  push    rbx
0x18005d95a  sub     rsp, 20h
0x18005d95e  mov     rbx, rcx
0x18005d961  mov     rcx, [rcx+70h]
0x18005d965  test    rcx, rcx
0x18005d968  jz      short loc_18005D982
0x18005d96a  mov     rax, [rcx]
0x18005d96d  mov     edx, 1
0x18005d972  mov     rax, [rax]
0x18005d975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d97a  mov     qword ptr [rbx+70h], 0
0x18005d982  cmp     byte ptr [rbx+0C8h], 0
0x18005d989  jz      short loc_18005D99F
0x18005d98b  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x18005d992  call    cs:__imp_DeleteCriticalSection
0x18005d998  mov     byte ptr [rbx+0C8h], 0
0x18005d99f  add     rsp, 20h
0x18005d9a3  pop     rbx
0x18005d9a4  retn
```
