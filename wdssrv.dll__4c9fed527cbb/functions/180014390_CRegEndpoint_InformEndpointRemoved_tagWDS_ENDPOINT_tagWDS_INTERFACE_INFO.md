# CRegEndpoint::InformEndpointRemoved(tagWDS_ENDPOINT *,tagWDS_INTERFACE_INFO *)

- ea: `0x180014390`
- end: `0x18001444d`
- name: `?InformEndpointRemoved@CRegEndpoint@@UEAAXPEAUtagWDS_ENDPOINT@@PEAUtagWDS_INTERFACE_INFO@@@Z`
- size: `189`
- prototype: `void __fastcall(CRegEndpoint *__hidden this, struct tagWDS_ENDPOINT *, struct tagWDS_INTERFACE_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014c00`

## callees

- `0x180014390`
- `0x18001d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180014400`
- `KERNEL32!LeaveCriticalSection` at `0x180014427`
- `KERNEL32!LeaveCriticalSection` at `0x180014400`
- `KERNEL32!LeaveCriticalSection` at `0x180014427`
- `KERNEL32!EnterCriticalSection` at `0x1800143d3`
- `KERNEL32!EnterCriticalSection` at `0x1800143d3`

## pseudocode

```c
void __fastcall CRegEndpoint::InformEndpointRemoved(
        CRegEndpoint *this,
        struct tagWDS_ENDPOINT *a2,
        struct tagWDS_INTERFACE_INFO *a3)
{
  void (__fastcall *v3)(__int64, struct tagWDS_ENDPOINT *, struct tagWDS_INTERFACE_INFO *); // rbx
  __int64 v5; // r14
  struct tagWDS_ENDPOINT *v6; // rbp
  __int64 v7; // rdi

  v3 = (void (__fastcall *)(__int64, struct tagWDS_ENDPOINT *, struct tagWDS_INTERFACE_INFO *))*((_QWORD *)this + 151);
  v5 = *((_QWORD *)this + 152);
  v6 = a2;
  if ( !a2 )
    v6 = (CRegEndpoint *)((char *)this + 72);
  v7 = *((_QWORD *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 200));
  if ( (unsigned int)(_InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 32), 0) - 1) > 1 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 200));
  }
  else
  {
    if ( !v3 )
    {
      v3 = *(void (__fastcall **)(__int64, struct tagWDS_ENDPOINT *, struct tagWDS_INTERFACE_INFO *))(v7 + 120);
      v5 = *(_QWORD *)(v7 + 128);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 200));
    if ( v3 )
      v3(v5, v6, a3);
  }
}

```

## disassembly

```asm
0x180014390  mov     [rsp+arg_0], rbx
0x180014395  mov     [rsp+arg_8], rbp
0x18001439a  mov     [rsp+arg_10], rsi
0x18001439f  push    rdi
0x1800143a0  push    r14
0x1800143a2  push    r15
0x1800143a4  sub     rsp, 20h
0x1800143a8  mov     rbx, [rcx+4B8h]
0x1800143af  mov     r15, r8
0x1800143b2  mov     r14, [rcx+4C0h]
0x1800143b9  mov     rbp, rdx
0x1800143bc  test    rdx, rdx
0x1800143bf  jnz     short loc_1800143C5
0x1800143c1  lea     rbp, [rcx+48h]
0x1800143c5  mov     rdi, [rcx+40h]
0x1800143c9  lea     rsi, [rdi+0C8h]
0x1800143d0  mov     rcx, rsi; lpCriticalSection
0x1800143d3  call    cs:__imp_EnterCriticalSection
0x1800143da  nop     dword ptr [rax+rax+00h]
0x1800143df  xor     eax, eax
0x1800143e1  lock xadd [rdi+20h], eax
0x1800143e6  dec     eax
0x1800143e8  cmp     eax, 1
0x1800143eb  ja      short loc_180014424
0x1800143ed  test    rbx, rbx
0x1800143f0  jnz     short loc_1800143FD
0x1800143f2  mov     rbx, [rdi+78h]
0x1800143f6  mov     r14, [rdi+80h]
0x1800143fd  mov     rcx, rsi; lpCriticalSection
0x180014400  call    cs:__imp_LeaveCriticalSection
0x180014407  nop     dword ptr [rax+rax+00h]
0x18001440c  test    rbx, rbx
0x18001440f  jz      short loc_180014433
0x180014411  mov     r8, r15
0x180014414  mov     rdx, rbp
0x180014417  mov     rcx, r14
0x18001441a  mov     rax, rbx
0x18001441d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014422  jmp     short loc_180014433
0x180014424  mov     rcx, rsi; lpCriticalSection
0x180014427  call    cs:__imp_LeaveCriticalSection
0x18001442e  nop     dword ptr [rax+rax+00h]
0x180014433  mov     rbx, [rsp+38h+arg_0]
0x180014438  mov     rbp, [rsp+38h+arg_8]
0x18001443d  mov     rsi, [rsp+38h+arg_10]
0x180014442  add     rsp, 20h
0x180014446  pop     r15
0x180014448  pop     r14
0x18001444a  pop     rdi
0x18001444b  retn
```
