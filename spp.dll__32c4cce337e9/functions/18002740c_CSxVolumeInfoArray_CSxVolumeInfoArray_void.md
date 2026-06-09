# CSxVolumeInfoArray::~CSxVolumeInfoArray(void)

- ea: `0x18002740c`
- end: `0x180027471`
- name: `??1CSxVolumeInfoArray@@AEAA@XZ`
- size: `101`
- prototype: `void __fastcall(CSxVolumeInfoArray *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e3cc`

## callees

- `0x18000e38c`
- `0x18002740c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002744d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002744d`

## pseudocode

```c
void __fastcall CSxVolumeInfoArray::~CSxVolumeInfoArray(CSxVolumeInfoArray *this)
{
  __int64 i; // rsi
  void *v3; // rcx

  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
  {
    CSxVolumeInfo::Release(*(CSxVolumeInfo **)(*(_QWORD *)this + 8 * i));
    *(_QWORD *)(*(_QWORD *)this + 8 * i) = 0;
  }
  v3 = *(void **)this;
  *((_DWORD *)this + 2) = 0;
  CoTaskMemFree(v3);
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x18002740c  mov     [rsp+arg_0], rbx
0x180027411  mov     [rsp+arg_8], rsi
0x180027416  push    rdi
0x180027417  sub     rsp, 20h
0x18002741b  xor     esi, esi
0x18002741d  mov     rdi, rcx
0x180027420  cmp     [rcx+8], esi
0x180027423  jbe     short loc_180027443
0x180027425  mov     rcx, [rdi]
0x180027428  mov     rcx, [rcx+rsi*8]; this
0x18002742c  call    ?Release@CSxVolumeInfo@@QEAAKXZ; CSxVolumeInfo::Release(void)
0x180027431  mov     rax, [rdi]
0x180027434  mov     qword ptr [rax+rsi*8], 0
0x18002743c  inc     esi
0x18002743e  cmp     esi, [rdi+8]
0x180027441  jb      short loc_180027425
0x180027443  mov     rcx, [rdi]; pv
0x180027446  mov     dword ptr [rdi+8], 0
0x18002744d  call    cs:__imp_CoTaskMemFree
0x180027453  mov     rbx, [rsp+28h+arg_0]
0x180027458  mov     rsi, [rsp+28h+arg_8]
0x18002745d  mov     qword ptr [rdi], 0
0x180027464  mov     dword ptr [rdi+0Ch], 0
0x18002746b  add     rsp, 20h
0x18002746f  pop     rdi
0x180027470  retn
```
