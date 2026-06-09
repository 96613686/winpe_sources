# RPCP_INTERFACE_GROUP::BeginActivity(void)

- ea: `0x180011344`
- end: `0x1800113e7`
- name: `?BeginActivity@RPCP_INTERFACE_GROUP@@QEAAXXZ`
- size: `163`
- prototype: `void __fastcall(RPCP_INTERFACE_GROUP *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000f4f4`
- `0x18006506c`

## callees

- `0x180011344`
- `0x180022e80`
- `0x18009d25c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800113db`
- `ntdll!RtlEnterCriticalSection` at `0x18001135b`
- `ntdll!RtlEnterCriticalSection` at `0x18001135b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800113b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800113b1`

## pseudocode

```c
void __fastcall RPCP_INTERFACE_GROUP::BeginActivity(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  PTP_TIMER *v3; // rcx
  int v4; // [rsp+28h] [rbp-20h]
  int v5; // [rsp+30h] [rbp-18h]

  v1 = this + 6;
  RtlEnterCriticalSection(this + 6);
  LogEvent(0x67u, 0x2Bu, this, 0, (int)++LODWORD(this[7].DebugInfo), v4, v5);
  if ( LODWORD(this[7].DebugInfo) == 1 && LODWORD(this[5].SpinCount) != 3 )
  {
    v3 = *(PTP_TIMER **)&this[7].LockCount;
    if ( v3 )
      SetThreadpoolTimer(*v3, 0, 0, 0);
    if ( LODWORD(this[7].OwningThread) )
      RPCP_INTERFACE_GROUP::PostIdleChangeNotification((RPCP_INTERFACE_GROUP *)this);
  }
  RtlLeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x180011344  mov     [rsp+arg_0], rbx
0x180011349  push    rdi
0x18001134a  sub     rsp, 40h
0x18001134e  lea     rdi, [rcx+0F0h]
0x180011355  mov     rbx, rcx
0x180011358  mov     rcx, rdi; CriticalSection
0x18001135b  call    cs:__imp_RtlEnterCriticalSection
0x180011362  nop     dword ptr [rax+rax+00h]
0x180011367  inc     dword ptr [rbx+118h]
0x18001136d  xor     r9d, r9d; void *
0x180011370  movsxd  rax, dword ptr [rbx+118h]
0x180011377  mov     r8, rbx; void *
0x18001137a  mov     dl, 2Bh ; '+'; unsigned __int8
0x18001137c  mov     [rsp+48h+var_28], rax; unsigned __int64
0x180011381  mov     cl, 67h ; 'g'; unsigned __int8
0x180011383  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180011388  cmp     dword ptr [rbx+118h], 1
0x18001138f  jnz     short loc_1800113CE
0x180011391  cmp     dword ptr [rbx+0E8h], 3
0x180011398  jz      short loc_1800113CE
0x18001139a  mov     rcx, [rbx+120h]
0x1800113a1  test    rcx, rcx
0x1800113a4  jz      short loc_1800113BD
0x1800113a6  mov     rcx, [rcx]; pti
0x1800113a9  xor     r9d, r9d; msWindowLength
0x1800113ac  xor     r8d, r8d; msPeriod
0x1800113af  xor     edx, edx; pftDueTime
0x1800113b1  call    cs:__imp_SetThreadpoolTimer
0x1800113b8  nop     dword ptr [rax+rax+00h]
0x1800113bd  cmp     dword ptr [rbx+128h], 0
0x1800113c4  jz      short loc_1800113CE
0x1800113c6  mov     rcx, rbx; this
0x1800113c9  call    ?PostIdleChangeNotification@RPCP_INTERFACE_GROUP@@AEAAXXZ; RPCP_INTERFACE_GROUP::PostIdleChangeNotification(void)
0x1800113ce  mov     rcx, rdi
0x1800113d1  mov     rbx, [rsp+48h+arg_0]
0x1800113d6  add     rsp, 40h
0x1800113da  pop     rdi
0x1800113db  jmp     cs:__imp_RtlLeaveCriticalSection
```
