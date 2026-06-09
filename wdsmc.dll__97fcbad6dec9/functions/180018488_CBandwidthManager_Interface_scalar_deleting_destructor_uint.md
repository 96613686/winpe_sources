# CBandwidthManager::Interface::`scalar deleting destructor'(uint)

- ea: `0x180018488`
- end: `0x180018533`
- name: `??_GInterface@CBandwidthManager@@QEAAPEAXI@Z`
- size: `171`
- prototype: `void *__fastcall(CBandwidthManager::Interface *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180018240`
- `0x180018988`

## callees

- `0x180004ff8`
- `0x180018488`
- `0x18001a9a8`
- `0x1800227d4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800184e2`
- `KERNEL32!LeaveCriticalSection` at `0x1800184e2`
- `KERNEL32!EnterCriticalSection` at `0x1800184a7`
- `KERNEL32!EnterCriticalSection` at `0x1800184a7`
- `KERNEL32!DeleteCriticalSection` at `0x18001850c`
- `KERNEL32!DeleteCriticalSection` at `0x18001850c`

## pseudocode

```c
CBandwidthManager::Interface *__fastcall CBandwidthManager::Interface::`scalar deleting destructor'(
        CBandwidthManager::Interface *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  __int64 v3; // rdi
  CMulticastSessionGroup **v4; // r14
  int v5; // r9d

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v3 = *((_QWORD *)this + 4);
  while ( v3 )
  {
    v4 = (CMulticastSessionGroup **)v3;
    v3 = *(_QWORD *)(v3 + 16);
    if ( *v4 )
      CMulticastSessionGroup::`scalar deleting destructor'(*v4);
    operator delete(v4);
    --*((_DWORD *)this + 12);
  }
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  LeaveCriticalSection(v1);
  if ( *((_DWORD *)this + 12) )
    WdsAssert("internal\\onecorebase\\private\\inc\\ECO\\WDS\\ListPtr.h", 0xF3u, "m_uNodeCount == 0", v5, 0);
  DeleteCriticalSection(v1);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180018488  mov     [rsp+arg_0], rbx
0x18001848d  mov     [rsp+arg_8], rsi
0x180018492  mov     [rsp+arg_10], rdi
0x180018497  push    r14
0x180018499  sub     rsp, 30h
0x18001849d  lea     rsi, [rcx+38h]
0x1800184a1  mov     rbx, rcx
0x1800184a4  mov     rcx, rsi; lpCriticalSection
0x1800184a7  call    cs:__imp_EnterCriticalSection
0x1800184ad  mov     rdi, [rbx+20h]
0x1800184b1  jmp     short loc_1800184D2
0x1800184b3  mov     r14, rdi
0x1800184b6  mov     rdi, [rdi+10h]
0x1800184ba  mov     rcx, [r14]; this
0x1800184bd  test    rcx, rcx
0x1800184c0  jz      short loc_1800184C7
0x1800184c2  call    ??_GCMulticastSessionGroup@@QEAAPEAXI@Z; CMulticastSessionGroup::`scalar deleting destructor'(uint)
0x1800184c7  mov     rcx, r14; void *
0x1800184ca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800184cf  dec     dword ptr [rbx+30h]
0x1800184d2  test    rdi, rdi
0x1800184d5  jnz     short loc_1800184B3
0x1800184d7  and     [rbx+20h], rdi
0x1800184db  mov     rcx, rsi; lpCriticalSection
0x1800184de  and     [rbx+28h], rdi
0x1800184e2  call    cs:__imp_LeaveCriticalSection
0x1800184e8  cmp     [rbx+30h], edi
0x1800184eb  jz      short loc_180018509
0x1800184ed  and     [rsp+38h+var_18], edi
0x1800184f1  lea     r8, aMUnodecount0; "m_uNodeCount == 0"
0x1800184f8  mov     edx, 0F3h; unsigned int
0x1800184fd  lea     rcx, aInternalOnecor_4; "internal\\onecorebase\\private\\inc\\EC"...
0x180018504  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180018509  mov     rcx, rsi; lpCriticalSection
0x18001850c  call    cs:__imp_DeleteCriticalSection
0x180018512  mov     rcx, rbx; void *
0x180018515  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001851a  mov     rsi, [rsp+38h+arg_8]
0x18001851f  mov     rax, rbx
0x180018522  mov     rbx, [rsp+38h+arg_0]
0x180018527  mov     rdi, [rsp+38h+arg_10]
0x18001852c  add     rsp, 30h
0x180018530  pop     r14
0x180018532  retn
```
