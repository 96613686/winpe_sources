# CLoadImageAsync::~CLoadImageAsync(void)

- ea: `0x18000bb0c`
- end: `0x18000bb50`
- name: `??1CLoadImageAsync@@MEAA@XZ`
- size: `68`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bb58`
- `0x18000bc00`

## callees

- `0x18000bb0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bb49`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000bb28`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000bb28`

## pseudocode

```c
void __fastcall CLoadImageAsync::~CLoadImageAsync(struct _RTL_CRITICAL_SECTION *this)
{
  void *v2; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CLoadImageAsync::`vftable';
  v2 = *(void **)&this[2].LockCount;
  if ( v2 )
  {
    DeleteObject(v2);
    *(_QWORD *)&this[2].LockCount = 0;
  }
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CPrivateNotificationWindow::`vftable';
  DeleteCriticalSection(this + 1);
}

```

## disassembly

```asm
0x18000bb0c  push    rbx
0x18000bb0e  sub     rsp, 20h
0x18000bb12  lea     rax, ??_7CLoadImageAsync@@6B@; const CLoadImageAsync::`vftable'
0x18000bb19  mov     rbx, rcx
0x18000bb1c  mov     [rcx], rax
0x18000bb1f  mov     rcx, [rcx+58h]; ho
0x18000bb23  test    rcx, rcx
0x18000bb26  jz      short loc_18000BB36
0x18000bb28  call    cs:__imp_DeleteObject
0x18000bb2e  mov     qword ptr [rbx+58h], 0
0x18000bb36  lea     rax, ??_7CPrivateNotificationWindow@@6B@; const CPrivateNotificationWindow::`vftable'
0x18000bb3d  lea     rcx, [rbx+28h]
0x18000bb41  mov     [rbx], rax
0x18000bb44  add     rsp, 20h
0x18000bb48  pop     rbx
0x18000bb49  jmp     cs:__imp_DeleteCriticalSection
```
