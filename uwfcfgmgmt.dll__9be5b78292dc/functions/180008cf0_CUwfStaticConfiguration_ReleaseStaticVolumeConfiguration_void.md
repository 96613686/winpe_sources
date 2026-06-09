# CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)

- ea: `0x180008cf0`
- end: `0x180008d20`
- name: `?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ`
- size: `48`
- prototype: `void __fastcall(CUwfStaticConfiguration *__hidden this)`
- caller_count: `16`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005a90`
- `0x180007420`
- `0x180007ad0`
- `0x18000ac60`
- `0x18000b6b0`
- `0x18000b940`
- `0x180011130`
- `0x180014d80`
- `0x1800151b0`
- `0x180016468`
- `0x180016d84`
- `0x180017e90`
- `0x180018950`
- `0x1800193c0`
- `0x18001a620`
- `0x18001aa94`

## callees

- `0x180008cf0`
- `0x18001c010`

## pseudocode

```c
void __fastcall CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(CUwfStaticConfiguration *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx

  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 5);
  if ( v2 )
  {
    (**v2)(v2, 1);
    *((_QWORD *)this + 5) = 0;
  }
}

```

## disassembly

```asm
0x180008cf0  push    rbx
0x180008cf2  sub     rsp, 20h
0x180008cf6  mov     rbx, rcx
0x180008cf9  mov     rcx, [rcx+28h]
0x180008cfd  test    rcx, rcx
0x180008d00  jz      short loc_180008D1A
0x180008d02  mov     rax, [rcx]
0x180008d05  mov     edx, 1
0x180008d0a  mov     rax, [rax]
0x180008d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d12  mov     qword ptr [rbx+28h], 0
0x180008d1a  add     rsp, 20h
0x180008d1e  pop     rbx
0x180008d1f  retn
```
