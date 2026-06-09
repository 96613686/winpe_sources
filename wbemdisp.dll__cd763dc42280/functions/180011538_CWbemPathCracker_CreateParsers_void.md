# CWbemPathCracker::CreateParsers(void)

- ea: `0x180011538`
- end: `0x180011584`
- name: `?CreateParsers@CWbemPathCracker@@AEAAXXZ`
- size: `76`
- prototype: `void __fastcall(CWbemPathCracker *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800045c0`
- `0x18001148c`
- `0x1800114f0`
- `0x180032c08`

## callees

- `0x180011538`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011563`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011563`

## pseudocode

```c
void __fastcall CWbemPathCracker::CreateParsers(CWbemPathCracker *this)
{
  LPVOID *ppv; // rbx
  __int64 v2; // rcx

  ppv = (LPVOID *)((char *)this + 8);
  v2 = *((_QWORD *)this + 1);
  if ( v2 )
  {
    *ppv = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  CoCreateInstance(&CLSID_WbemDefPath, 0, 1u, &IID_IWbemPath, ppv);
}

```

## disassembly

```asm
0x180011538  push    rbx
0x18001153a  sub     rsp, 30h
0x18001153e  lea     rbx, [rcx+8]
0x180011542  mov     rcx, [rbx]
0x180011545  test    rcx, rcx
0x180011548  jnz     short loc_18001156F
0x18001154a  xor     edx, edx; pUnkOuter
0x18001154c  mov     [rsp+38h+ppv], rbx; ppv
0x180011551  lea     r9, IID_IWbemPath; riid
0x180011558  lea     rcx, CLSID_WbemDefPath; rclsid
0x18001155f  lea     r8d, [rdx+1]; dwClsContext
0x180011563  call    cs:__imp_CoCreateInstance
0x180011569  add     rsp, 30h
0x18001156d  pop     rbx
0x18001156e  retn
0x18001156f  mov     qword ptr [rbx], 0
0x180011576  mov     rax, [rcx]
0x180011579  mov     rax, [rax+10h]
0x18001157d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011582  jmp     short loc_18001154A
```
