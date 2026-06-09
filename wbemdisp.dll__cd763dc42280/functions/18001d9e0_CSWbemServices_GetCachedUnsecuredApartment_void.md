# CSWbemServices::GetCachedUnsecuredApartment(void)

- ea: `0x18001d9e0`
- end: `0x18001da3a`
- name: `?GetCachedUnsecuredApartment@CSWbemServices@@QEAAPEAUIUnsecuredApartment@@XZ`
- size: `90`
- prototype: `struct IUnsecuredApartment *__fastcall(CSWbemServices *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800287bc`

## callees

- `0x18001d9e0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001da0c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001da0c`

## pseudocode

```c
struct IUnsecuredApartment *__fastcall CSWbemServices::GetCachedUnsecuredApartment(CSWbemServices *this)
{
  _QWORD *v1; // rbx

  v1 = (_QWORD *)((char *)this + 152);
  if ( !*((_QWORD *)this + 19)
    && CoCreateInstance(&CLSID_UnsecuredApartment, 0, 0x17u, &IID_IUnsecuredApartment, (LPVOID *)this + 19) < 0 )
  {
    *v1 = 0;
  }
  if ( *v1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v1 + 8LL))(*v1);
  return (struct IUnsecuredApartment *)*v1;
}

```

## disassembly

```asm
0x18001d9e0  push    rbx
0x18001d9e2  sub     rsp, 30h
0x18001d9e6  lea     rbx, [rcx+98h]
0x18001d9ed  cmp     qword ptr [rbx], 0
0x18001d9f1  jnz     short loc_18001DA1D
0x18001d9f3  xor     edx, edx; pUnkOuter
0x18001d9f5  mov     [rsp+38h+ppv], rbx; ppv
0x18001d9fa  lea     r9, IID_IUnsecuredApartment; riid
0x18001da01  lea     rcx, CLSID_UnsecuredApartment; rclsid
0x18001da08  lea     r8d, [rdx+17h]; dwClsContext
0x18001da0c  call    cs:__imp_CoCreateInstance
0x18001da12  test    eax, eax
0x18001da14  jns     short loc_18001DA1D
0x18001da16  mov     qword ptr [rbx], 0
0x18001da1d  mov     rcx, [rbx]
0x18001da20  test    rcx, rcx
0x18001da23  jz      short loc_18001DA31
0x18001da25  mov     rdx, [rcx]
0x18001da28  mov     rax, [rdx+8]
0x18001da2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da31  mov     rax, [rbx]
0x18001da34  add     rsp, 30h
0x18001da38  pop     rbx
0x18001da39  retn
```
