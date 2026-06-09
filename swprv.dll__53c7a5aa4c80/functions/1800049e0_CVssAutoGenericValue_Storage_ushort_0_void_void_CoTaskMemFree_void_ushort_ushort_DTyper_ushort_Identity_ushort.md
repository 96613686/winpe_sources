# CVssAutoGenericValue_Storage<ushort *,0,void (*)(void *),&CoTaskMemFree(void *),ushort * & (*)(ushort * &),&DTyper<ushort *>::Identity(ushort * &)>::Close(void)

- ea: `0x1800049e0`
- end: `0x180004a06`
- name: `?Close@?$CVssAutoGenericValue_Storage@PEAG$0A@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6AAEAPEAGAEAPEAG@Z$1?Identity@?$DTyper@PEAG@@SAAEAPEAG1@Z@@QEAAXXZ`
- size: `38`
- prototype: `void __fastcall(__int64)`
- caller_count: `12`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003718`
- `0x180004a78`
- `0x18000e900`
- `0x180011178`
- `0x180015864`
- `0x18002e7ec`
- `0x180037f24`
- `0x180038118`
- `0x18003835c`
- `0x1800386cc`
- `0x180038704`
- `0x180039ac8`

## callees

- `0x1800049e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800049f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800049f2`

## pseudocode

```c
void __fastcall CVssAutoGenericValue_Storage<unsigned short *,0,void (*)(void *),&void CoTaskMemFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)(a1 + 8);
  if ( v2 )
    CoTaskMemFree(v2);
  *(_QWORD *)(a1 + 8) = 0;
}

```

## disassembly

```asm
0x1800049e0  push    rbx
0x1800049e2  sub     rsp, 20h
0x1800049e6  mov     rbx, rcx
0x1800049e9  mov     rcx, [rcx+8]; pv
0x1800049ed  test    rcx, rcx
0x1800049f0  jz      short loc_1800049F8
0x1800049f2  call    cs:__imp_CoTaskMemFree
0x1800049f8  mov     qword ptr [rbx+8], 0
0x180004a00  add     rsp, 20h
0x180004a04  pop     rbx
0x180004a05  retn
```
