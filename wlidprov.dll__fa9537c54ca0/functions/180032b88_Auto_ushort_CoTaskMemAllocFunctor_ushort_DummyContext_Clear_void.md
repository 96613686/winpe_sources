# Auto<ushort *,CoTaskMemAllocFunctor<ushort *>,DummyContext>::Clear(void)

- ea: `0x180032b88`
- end: `0x180032bb4`
- name: `?Clear@?$Auto@PEAGV?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@QEAAXXZ`
- size: `44`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003056c`
- `0x180030b40`
- `0x180035690`

## callees

- `0x180032b88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032b99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032b99`

## pseudocode

```c
void __fastcall Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>::Clear(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180032b88  push    rbx
0x180032b8a  sub     rsp, 20h
0x180032b8e  mov     rbx, rcx
0x180032b91  mov     rcx, [rcx]; pv
0x180032b94  test    rcx, rcx
0x180032b97  jz      short loc_180032BAE
0x180032b99  call    cs:__imp_CoTaskMemFree
0x180032b9f  mov     qword ptr [rbx], 0
0x180032ba6  mov     qword ptr [rbx+8], 0
0x180032bae  add     rsp, 20h
0x180032bb2  pop     rbx
0x180032bb3  retn
```
