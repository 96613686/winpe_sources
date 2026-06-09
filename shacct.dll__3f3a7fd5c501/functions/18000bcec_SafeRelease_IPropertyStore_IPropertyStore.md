# SafeRelease<IPropertyStore>(IPropertyStore * *)

- ea: `0x18000bcec`
- end: `0x18000bd13`
- name: `??$SafeRelease@UIPropertyStore@@@@YAXPEAPEAUIPropertyStore@@@Z`
- size: `39`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180009900`
- `0x18000d994`
- `0x18000d9f8`
- `0x180011e80`

## callees

- `0x18000bcec`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall SafeRelease<IPropertyStore>(__int64 *a1)
{
  __int64 v1; // rdx
  __int64 result; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18000bcec  sub     rsp, 28h
0x18000bcf0  mov     rdx, [rcx]
0x18000bcf3  mov     qword ptr [rcx], 0
0x18000bcfa  test    rdx, rdx
0x18000bcfd  jz      short loc_18000BD0E
0x18000bcff  mov     rax, [rdx]
0x18000bd02  mov     rcx, rdx
0x18000bd05  mov     rax, [rax+10h]
0x18000bd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd0e  add     rsp, 28h
0x18000bd12  retn
```
