# CPNPPropertyStore::Terminate(void)

- ea: `0x180043a90`
- end: `0x180043b02`
- name: `?Terminate@CPNPPropertyStore@@UEAAJXZ`
- size: `114`
- prototype: `__int64 __fastcall(CPNPPropertyStore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a180`

## callees

- `0x180007da0`
- `0x18000ab84`
- `0x18000b3d0`
- `0x180043a90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043adc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043adc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180043ad3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180043ad3`

## pseudocode

```c
__int64 __fastcall CPNPPropertyStore::Terminate(CPNPPropertyStore *this)
{
  CTSCriticalSection *v1; // rbx
  void **v3; // r14
  PROPVARIANT *v4; // rsi
  PROPVARIANT *v5; // rax
  _QWORD *v6; // rdx
  char *v8; // [rsp+50h] [rbp+8h] BYREF

  *((_DWORD *)this + 5) |= 4u;
  v1 = (CPNPPropertyStore *)((char *)this + 40);
  v8 = (char *)this + 40;
  CTSCriticalSection::Lock((CPNPPropertyStore *)((char *)this + 40));
  v3 = (void **)((char *)this + 64);
  while ( 1 )
  {
    v4 = (PROPVARIANT *)*v3;
    if ( *v3 == v3 )
      break;
    --*((_DWORD *)this + 14);
    v5 = (PROPVARIANT *)v4[1];
    v6 = *v4;
    *v5 = *v4;
    v6[1] = v5;
    PropVariantClear(v4 + 5);
    CoTaskMemFree(v4);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v8);
  CTSCriticalSection::Terminate(v1);
  return 0;
}

```

## disassembly

```asm
0x180043a90  push    rbx
0x180043a92  push    rsi
0x180043a93  push    rdi
0x180043a94  push    r14
0x180043a96  sub     rsp, 28h
0x180043a9a  or      dword ptr [rcx+14h], 4
0x180043a9e  lea     rbx, [rcx+28h]
0x180043aa2  mov     rdi, rcx
0x180043aa5  mov     [rsp+48h+arg_0], rbx
0x180043aaa  mov     rcx, rbx; this
0x180043aad  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180043ab2  lea     r14, [rdi+40h]
0x180043ab6  mov     rsi, [r14]
0x180043ab9  cmp     rsi, r14
0x180043abc  jz      short loc_180043AE4
0x180043abe  dec     dword ptr [rdi+38h]
0x180043ac1  lea     rcx, [rsi+28h]; pvar
0x180043ac5  mov     rax, [rsi+8]
0x180043ac9  mov     rdx, [rsi]
0x180043acc  mov     [rax], rdx
0x180043acf  mov     [rdx+8], rax
0x180043ad3  call    cs:__imp_PropVariantClear
0x180043ad9  mov     rcx, rsi; pv
0x180043adc  call    cs:__imp_CoTaskMemFree
0x180043ae2  jmp     short loc_180043AB6
0x180043ae4  lea     rcx, [rsp+48h+arg_0]; this
0x180043ae9  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180043aee  mov     rcx, rbx; this
0x180043af1  call    ?Terminate@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Terminate(void)
0x180043af6  xor     eax, eax
0x180043af8  add     rsp, 28h
0x180043afc  pop     r14
0x180043afe  pop     rdi
0x180043aff  pop     rsi
0x180043b00  pop     rbx
0x180043b01  retn
```
