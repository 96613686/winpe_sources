# CCorrAPO::FreeNotificationStuff(void)

- ea: `0x180009850`
- end: `0x1800098e1`
- name: `?FreeNotificationStuff@CCorrAPO@@QEAAXXZ`
- size: `145`
- prototype: `void __fastcall(CCorrAPO *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800090e0`
- `0x1800097cc`

## callees

- `0x180009850`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000988d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000988d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009867`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009867`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009879`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009879`

## pseudocode

```c
void __fastcall CCorrAPO::FreeNotificationStuff(CCorrAPO *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  void *v3; // rcx
  _QWORD *v4; // rdi
  __int64 v5; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 416);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 416));
  v3 = (void *)*((_QWORD *)this + 58);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 58) = 0;
  }
  LeaveCriticalSection(v1);
  v4 = (_QWORD *)((char *)this + 456);
  v5 = *((_QWORD *)this + 57);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v5 + 56LL))(
      v5,
      ((unsigned __int64)this + 408) & -(__int64)(this != 0));
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 16LL))(*v4);
    *v4 = 0;
  }
}

```

## disassembly

```asm
0x180009850  mov     [rsp+arg_0], rbx
0x180009855  push    rdi
0x180009856  sub     rsp, 20h
0x18000985a  lea     rdi, [rcx+1A0h]
0x180009861  mov     rbx, rcx
0x180009864  mov     rcx, rdi; lpCriticalSection
0x180009867  call    cs:__imp_EnterCriticalSection
0x18000986d  mov     rcx, [rbx+1D0h]; pv
0x180009874  test    rcx, rcx
0x180009877  jz      short loc_18000988A
0x180009879  call    cs:__imp_CoTaskMemFree
0x18000987f  mov     qword ptr [rbx+1D0h], 0
0x18000988a  mov     rcx, rdi; lpCriticalSection
0x18000988d  call    cs:__imp_LeaveCriticalSection
0x180009893  lea     rdi, [rbx+1C8h]
0x18000989a  mov     rcx, [rdi]
0x18000989d  test    rcx, rcx
0x1800098a0  jnz     short loc_1800098AD
0x1800098a2  mov     rbx, [rsp+28h+arg_0]
0x1800098a7  add     rsp, 20h
0x1800098ab  pop     rdi
0x1800098ac  retn
0x1800098ad  mov     r8, [rcx]
0x1800098b0  lea     rax, [rbx+198h]
0x1800098b7  neg     rbx
0x1800098ba  sbb     rdx, rdx
0x1800098bd  and     rdx, rax
0x1800098c0  mov     rax, [r8+38h]
0x1800098c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098c9  mov     rcx, [rdi]
0x1800098cc  mov     rax, [rcx]
0x1800098cf  mov     rax, [rax+10h]
0x1800098d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098d8  mov     qword ptr [rdi], 0
0x1800098df  jmp     short loc_1800098A2
```
