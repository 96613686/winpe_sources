# CRunDeliveryAgent::StartAgent(void)

- ea: `0x18000329c`
- end: `0x180003352`
- name: `?StartAgent@CRunDeliveryAgent@@QEAAJXZ`
- size: `182`
- prototype: `__int64 __fastcall(CRunDeliveryAgent *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004770`
- `0x18001e008`

## callees

- `0x18000329c`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800032f8`
- `ole32!CoCreateInstance` at `0x1800032f8`

## pseudocode

```c
__int64 __fastcall CRunDeliveryAgent::StartAgent(CRunDeliveryAgent *this)
{
  LPVOID *ppv; // rbx
  __int64 v3; // rax
  unsigned int v4; // ebx
  __int64 result; // rax

  if ( !*((_QWORD *)this + 1) )
    return 2147500037LL;
  if ( !*((_QWORD *)this + 3) )
    return 2147500037LL;
  ppv = (LPVOID *)((char *)this + 32);
  if ( *((_QWORD *)this + 4) )
    return 2147500037LL;
  (*(void (__fastcall **)(CRunDeliveryAgent *))(*(_QWORD *)this + 8LL))(this);
  *((_DWORD *)this + 10) = 790526;
  *((_DWORD *)this + 11) = 1;
  CoCreateInstance((const IID *const)this + 3, 0, 1u, &IID_ISubscriptionAgentControl, ppv);
  if ( *ppv )
    (*(void (__fastcall **)(LPVOID, _QWORD, CRunDeliveryAgent *))(*(_QWORD *)*ppv + 24LL))(
      *ppv,
      *((_QWORD *)this + 3),
      this);
  v3 = *(_QWORD *)this;
  v4 = *((_DWORD *)this + 10);
  *((_DWORD *)this + 11) = 0;
  (*(void (__fastcall **)(CRunDeliveryAgent *))(v3 + 16))(this);
  result = 2147483658LL;
  if ( v4 != 790526 )
    return v4;
  return result;
}

```

## disassembly

```asm
0x18000329c  mov     [rsp+arg_0], rbx
0x1800032a1  push    rdi
0x1800032a2  sub     rsp, 30h
0x1800032a6  cmp     qword ptr [rcx+8], 0
0x1800032ab  mov     rdi, rcx
0x1800032ae  jz      loc_180003342
0x1800032b4  cmp     qword ptr [rcx+18h], 0
0x1800032b9  jz      loc_180003342
0x1800032bf  lea     rbx, [rcx+20h]
0x1800032c3  cmp     qword ptr [rbx], 0
0x1800032c7  jnz     short loc_180003342
0x1800032c9  mov     rax, [rcx]
0x1800032cc  mov     rax, [rax+8]
0x1800032d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d5  mov     r8d, 1; dwClsContext
0x1800032db  mov     dword ptr [rdi+28h], 0C0FFEh
0x1800032e2  lea     rcx, [rdi+30h]; rclsid
0x1800032e6  mov     [rdi+2Ch], r8d
0x1800032ea  lea     r9, IID_ISubscriptionAgentControl; riid
0x1800032f1  mov     [rsp+38h+ppv], rbx; ppv
0x1800032f6  xor     edx, edx; pUnkOuter
0x1800032f8  call    cs:__imp_CoCreateInstance
0x1800032fe  mov     rcx, [rbx]
0x180003301  test    rcx, rcx
0x180003304  jz      short loc_180003319
0x180003306  mov     rax, [rcx]
0x180003309  mov     r8, rdi
0x18000330c  mov     rdx, [rdi+18h]
0x180003310  mov     rax, [rax+18h]
0x180003314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003319  mov     rax, [rdi]
0x18000331c  mov     rcx, rdi
0x18000331f  mov     ebx, [rdi+28h]
0x180003322  mov     dword ptr [rdi+2Ch], 0
0x180003329  mov     rax, [rax+10h]
0x18000332d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003332  cmp     ebx, 0C0FFEh
0x180003338  mov     eax, 8000000Ah
0x18000333d  cmovnz  eax, ebx
0x180003340  jmp     short loc_180003347
0x180003342  mov     eax, 80004005h
0x180003347  mov     rbx, [rsp+38h+arg_0]
0x18000334c  add     rsp, 30h
0x180003350  pop     rdi
0x180003351  retn
```
