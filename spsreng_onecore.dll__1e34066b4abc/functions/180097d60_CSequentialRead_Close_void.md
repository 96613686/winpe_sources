# CSequentialRead::Close(void)

- ea: `0x180097d60`
- end: `0x180097d9b`
- name: `?Close@CSequentialRead@@UEAAXXZ`
- size: `59`
- prototype: `void __fastcall(CSequentialRead *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180097db0`
- `0x18009f0bc`
- `0x1800b6c90`

## callees

- `0x180097d60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097d78`

## pseudocode

```c
void __fastcall CSequentialRead::Close(CSequentialRead *this)
{
  void *v2; // rcx

  if ( *((_DWORD *)this + 6) )
  {
    v2 = (void *)*((_QWORD *)this + 1);
    if ( v2 )
      CoTaskMemFree(v2);
  }
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x180097d60  push    rbx
0x180097d62  sub     rsp, 20h
0x180097d66  cmp     dword ptr [rcx+18h], 0
0x180097d6a  mov     rbx, rcx
0x180097d6d  jz      short loc_180097D7E
0x180097d6f  mov     rcx, [rcx+8]; pv
0x180097d73  test    rcx, rcx
0x180097d76  jz      short loc_180097D7E
0x180097d78  call    cs:__imp_CoTaskMemFree
0x180097d7e  mov     qword ptr [rbx+8], 0
0x180097d86  mov     qword ptr [rbx+10h], 0
0x180097d8e  mov     dword ptr [rbx+18h], 0
0x180097d95  add     rsp, 20h
0x180097d99  pop     rbx
0x180097d9a  retn
```
