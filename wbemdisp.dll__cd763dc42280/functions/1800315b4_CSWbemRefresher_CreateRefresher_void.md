# CSWbemRefresher::CreateRefresher(void)

- ea: `0x1800315b4`
- end: `0x180031615`
- name: `?CreateRefresher@CSWbemRefresher@@AEAAXXZ`
- size: `97`
- prototype: `void __fastcall(CSWbemRefresher *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180031070`
- `0x180031250`

## callees

- `0x1800315b4`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800315e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800315e7`

## pseudocode

```c
void __fastcall CSWbemRefresher::CreateRefresher(CSWbemRefresher *this)
{
  _QWORD *v1; // rbx

  v1 = (_QWORD *)((char *)this + 128);
  if ( !*((_QWORD *)this + 16)
    && CoCreateInstance(&CLSID_WbemRefresher, 0, 1u, &IID_IWbemRefresher, (LPVOID *)this + 16) >= 0 )
  {
    (**(void (__fastcall ***)(_QWORD, GUID *, char *))*v1)(*v1, &IID_IWbemConfigureRefresher, (char *)this + 120);
  }
}

```

## disassembly

```asm
0x1800315b4  mov     [rsp+arg_0], rbx
0x1800315b9  push    rdi
0x1800315ba  sub     rsp, 30h
0x1800315be  lea     rbx, [rcx+80h]
0x1800315c5  mov     rdi, rcx
0x1800315c8  cmp     qword ptr [rbx], 0
0x1800315cc  jnz     short loc_18003160A
0x1800315ce  xor     edx, edx; pUnkOuter
0x1800315d0  mov     [rsp+38h+ppv], rbx; ppv
0x1800315d5  lea     r9, IID_IWbemRefresher; riid
0x1800315dc  lea     rcx, CLSID_WbemRefresher; rclsid
0x1800315e3  lea     r8d, [rdx+1]; dwClsContext
0x1800315e7  call    cs:__imp_CoCreateInstance
0x1800315ed  test    eax, eax
0x1800315ef  js      short loc_18003160A
0x1800315f1  mov     rcx, [rbx]
0x1800315f4  lea     r8, [rdi+78h]
0x1800315f8  lea     rdx, IID_IWbemConfigureRefresher
0x1800315ff  mov     rax, [rcx]
0x180031602  mov     rax, [rax]
0x180031605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003160a  mov     rbx, [rsp+38h+arg_0]
0x18003160f  add     rsp, 30h
0x180031613  pop     rdi
0x180031614  retn
```
