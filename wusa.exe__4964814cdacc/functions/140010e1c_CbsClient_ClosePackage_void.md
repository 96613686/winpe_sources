# CbsClient::ClosePackage(void)

- ea: `0x140010e1c`
- end: `0x140010e82`
- name: `?ClosePackage@CbsClient@@AEAAXXZ`
- size: `102`
- prototype: `void __fastcall(CbsClient *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140010c28`
- `0x140010e88`
- `0x140011190`

## callees

- `0x140010e1c`
- `0x140015010`

## import_xrefs

- `ServicingCommon!SczFree` at `0x140010e4e`
- `ServicingCommon!SczFree` at `0x140010e4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010e31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010e31`

## pseudocode

```c
void __fastcall CbsClient::ClosePackage(CbsClient *this, __int64 a2, __int64 a3)
{
  void *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v4 = (void *)*((_QWORD *)this + 67);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 67) = 0;
  }
  v5 = *((_QWORD *)this + 68);
  if ( v5 )
  {
    SczFree(v5, a2, a3);
    *((_QWORD *)this + 68) = 0;
  }
  v6 = *((_QWORD *)this + 1);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x140010e1c  push    rbx
0x140010e1e  sub     rsp, 20h
0x140010e22  mov     rbx, rcx
0x140010e25  mov     rcx, [rcx+218h]; pv
0x140010e2c  test    rcx, rcx
0x140010e2f  jz      short loc_140010E42
0x140010e31  call    cs:__imp_CoTaskMemFree
0x140010e37  mov     qword ptr [rbx+218h], 0
0x140010e42  mov     rcx, [rbx+220h]
0x140010e49  test    rcx, rcx
0x140010e4c  jz      short loc_140010E5F
0x140010e4e  call    cs:__imp_SczFree
0x140010e54  mov     qword ptr [rbx+220h], 0
0x140010e5f  mov     rcx, [rbx+8]
0x140010e63  test    rcx, rcx
0x140010e66  jz      short loc_140010E7C
0x140010e68  mov     rax, [rcx]
0x140010e6b  mov     rax, [rax+10h]
0x140010e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010e74  mov     qword ptr [rbx+8], 0
0x140010e7c  add     rsp, 20h
0x140010e80  pop     rbx
0x140010e81  retn
```
