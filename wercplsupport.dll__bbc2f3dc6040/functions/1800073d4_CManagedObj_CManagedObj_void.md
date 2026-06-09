# CManagedObj::CManagedObj(void)

- ea: `0x1800073d4`
- end: `0x180007440`
- name: `??0CManagedObj@@QEAA@XZ`
- size: `108`
- prototype: `CManagedObj *__fastcall(CManagedObj *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e70`
- `0x180006ce0`
- `0x180006fe0`
- `0x180008208`
- `0x180008420`
- `0x180008f54`
- `0x18000a650`
- `0x18000fb0c`
- `0x1800100b4`
- `0x1800102f8`
- `0x180010400`
- `0x180010c08`
- `0x180010e50`

## callees

- `0x1800073d4`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000742a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000742a`

## pseudocode

```c
CManagedObj *__fastcall CManagedObj::CManagedObj(CManagedObj *this)
{
  *(_QWORD *)this = &CManagedObj::`vftable';
  *((_QWORD *)this + 1) = 0;
  if ( CObjectManager::ms_instance )
  {
    EnterCriticalSection(&CriticalSection);
    (*(void (__fastcall **)(CManagedObj *))(*(_QWORD *)this + 8LL))(this);
    *((_QWORD *)this + 2) = qword_18001C960;
    qword_18001C960 = (__int64)this;
    LeaveCriticalSection(&CriticalSection);
  }
  _InterlockedIncrement(&dword_18001C958);
  return this;
}

```

## disassembly

```asm
0x1800073d4  push    rbx
0x1800073d6  sub     rsp, 20h
0x1800073da  lea     rax, ??_7CManagedObj@@6B@; const CManagedObj::`vftable'
0x1800073e1  mov     rbx, rcx
0x1800073e4  mov     [rcx], rax
0x1800073e7  xor     eax, eax
0x1800073e9  mov     [rcx+8], rax
0x1800073ed  cmp     cs:?ms_instance@CObjectManager@@1V1@A, eax; CObjectManager CObjectManager::ms_instance
0x1800073f3  jz      short loc_180007430
0x1800073f5  lea     rcx, CriticalSection; lpCriticalSection
0x1800073fc  call    cs:__imp_EnterCriticalSection
0x180007402  mov     rax, [rbx]
0x180007405  mov     rcx, rbx
0x180007408  mov     rax, [rax+8]
0x18000740c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007411  mov     rax, cs:qword_18001C960
0x180007418  lea     rcx, CriticalSection; lpCriticalSection
0x18000741f  mov     [rbx+10h], rax
0x180007423  mov     cs:qword_18001C960, rbx
0x18000742a  call    cs:__imp_LeaveCriticalSection
0x180007430  lock inc cs:dword_18001C958
0x180007437  mov     rax, rbx
0x18000743a  add     rsp, 20h
0x18000743e  pop     rbx
0x18000743f  retn
```
