# CVolumeManager::RemoveVolumeFromLinkedList(CVolume const *)

- ea: `0x180001500`
- end: `0x180001581`
- name: `?RemoveVolumeFromLinkedList@CVolumeManager@@QEAAXPEBVCVolume@@@Z`
- size: `129`
- prototype: `void __fastcall(CVolumeManager *__hidden this, const struct CVolume *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001448`

## callees

- `0x180001500`
- `0x1800066c0`
- `0x18000db28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001524`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001524`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000156b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000156b`

## pseudocode

```c
void __fastcall CVolumeManager::RemoveVolumeFromLinkedList(CVolumeManager *this, const struct CVolume *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  _QWORD *v5; // rax
  __int64 i; // rbx

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 208);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  v5 = (_QWORD *)((char *)this + 200);
  for ( i = *((_QWORD *)this + 25); i; i = *(_QWORD *)(i + 8) )
  {
    if ( a2 == *(const struct CVolume **)i )
    {
      *v5 = *(_QWORD *)(i + 8);
      PLogFileNotify::Release(*(PLogFileNotify **)i);
      operator delete((void *)i);
      break;
    }
    v5 = (_QWORD *)(i + 8);
  }
  LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x180001500  mov     [rsp+arg_8], rbx
0x180001505  mov     [rsp+arg_10], rsi
0x18000150a  push    rdi
0x18000150b  sub     rsp, 30h
0x18000150f  mov     rsi, rdx
0x180001512  mov     rbx, rcx
0x180001515  lea     rdi, [rcx+0D0h]
0x18000151c  mov     [rsp+38h+arg_0], rdi
0x180001521  mov     rcx, rdi; lpCriticalSection
0x180001524  call    cs:__imp_EnterCriticalSection
0x18000152a  nop
0x18000152b  lea     rax, [rbx+0C8h]
0x180001532  mov     rbx, [rax]
0x180001535  test    rbx, rbx
0x180001538  jz      short loc_180001561
0x18000153a  mov     rdx, [rbx+8]
0x18000153e  cmp     rsi, [rbx]
0x180001541  jnz     short loc_180001558
0x180001543  mov     [rax], rdx
0x180001546  mov     rcx, [rbx]; this
0x180001549  call    ?Release@PLogFileNotify@@QEAAKXZ; PLogFileNotify::Release(void)
0x18000154e  mov     rcx, rbx; Block
0x180001551  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001556  jmp     short loc_180001561
0x180001558  lea     rax, [rbx+8]
0x18000155c  mov     rbx, rdx
0x18000155f  jmp     short loc_180001535
0x180001561  jmp     short loc_180001568
0x180001563  mov     rdi, [rsp+38h+arg_0]
0x180001568  mov     rcx, rdi; lpCriticalSection
0x18000156b  call    cs:__imp_LeaveCriticalSection
0x180001571  mov     rbx, [rsp+38h+arg_8]
0x180001576  mov     rsi, [rsp+38h+arg_10]
0x18000157b  add     rsp, 30h
0x18000157f  pop     rdi
0x180001580  retn
0x180011111  push    rbp
0x180011113  sub     rsp, 20h
0x180011117  mov     rbp, rdx
0x18001111a  mov     eax, 1
0x18001111f  add     rsp, 20h
0x180011123  pop     rbp
0x180011124  retn
```
