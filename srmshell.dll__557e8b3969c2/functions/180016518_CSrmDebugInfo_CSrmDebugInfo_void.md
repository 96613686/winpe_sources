# CSrmDebugInfo::~CSrmDebugInfo(void)

- ea: `0x180016518`
- end: `0x18001655d`
- name: `??1CSrmDebugInfo@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(CSrmDebugInfo *__hidden this)`
- caller_count: `46`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001623c`
- `0x180016dd0`
- `0x1800180a0`
- `0x180018cbc`
- `0x180018f68`
- `0x1800193ec`
- `0x18001957c`
- `0x1800196f0`
- `0x1800198a0`
- `0x1800198e0`
- `0x180019be0`
- `0x18001b8e1`
- `0x18001baeb`
- `0x18001c2a4`
- `0x18001c454`
- `0x18001c48a`
- `0x18001c65e`
- `0x18001c700`
- `0x18001c818`
- `0x18001cd5c`
- `0x18001cf24`
- `0x18001d0f8`
- `0x18001d49c`
- `0x18001d679`
- `0x18001e9a4`
- `0x18001e9c8`
- `0x18001ea7e`
- `0x18001eaaa`
- `0x18001ead9`
- `0x18001ec92`
- `0x18001eca4`
- `0x18001ecb6`
- `0x18001ed20`
- `0x18001ed32`
- `0x18001ed56`
- `0x18001eeeb`
- `0x18001ef29`
- `0x18001ef4d`
- `0x18001ef71`
- `0x18001ef95`
- `0x18001efa7`
- `0x18001efcb`
- `0x18001efdd`
- `0x18001efef`
- `0x18001f025`
- `0x18001f037`

## callees

- `0x180016518`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001653a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001653a`

## pseudocode

```c
void __fastcall CSrmDebugInfo::~CSrmDebugInfo(CSrmDebugInfo *this)
{
  __int64 i; // rbx
  void *v3; // rcx

  if ( *((_BYTE *)this + 139) )
  {
    for ( i = 0; i != 12; ++i )
    {
      v3 = (void *)*((_QWORD *)this + i + 5);
      if ( v3 )
      {
        CoTaskMemFree(v3);
        *((_QWORD *)this + i + 5) = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x180016518  mov     [rsp+arg_0], rbx
0x18001651d  push    rdi
0x18001651e  sub     rsp, 20h
0x180016522  mov     rdi, rcx
0x180016525  cmp     byte ptr [rcx+8Bh], 0
0x18001652c  jz      short loc_180016552
0x18001652e  xor     ebx, ebx
0x180016530  mov     rcx, [rdi+rbx*8+28h]; pv
0x180016535  test    rcx, rcx
0x180016538  jz      short loc_180016549
0x18001653a  call    cs:__imp_CoTaskMemFree
0x180016540  mov     qword ptr [rdi+rbx*8+28h], 0
0x180016549  inc     rbx
0x18001654c  cmp     rbx, 0Ch
0x180016550  jnz     short loc_180016530
0x180016552  mov     rbx, [rsp+28h+arg_0]
0x180016557  add     rsp, 20h
0x18001655b  pop     rdi
0x18001655c  retn
```
