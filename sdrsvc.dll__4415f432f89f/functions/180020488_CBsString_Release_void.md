# CBsString::_Release(void)

- ea: `0x180020488`
- end: `0x1800204c0`
- name: `?_Release@CBsString@@AEAAXXZ`
- size: `56`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `32`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008b74`
- `0x18000b868`
- `0x180010c80`
- `0x180011224`
- `0x1800120dc`
- `0x1800121bc`
- `0x1800148dc`
- `0x1800151b4`
- `0x1800152c0`
- `0x1800153b8`
- `0x1800160c8`
- `0x180016400`
- `0x180016520`
- `0x18001698c`
- `0x180016a78`
- `0x180016f68`
- `0x180017330`
- `0x1800190bc`
- `0x180019ca0`
- `0x180019e58`
- `0x18001a898`
- `0x18001c924`
- `0x18001cd6c`
- `0x18001cfc8`
- `0x18001d4dc`
- `0x18001dc74`
- `0x18001e2dc`
- `0x18001fd3c`
- `0x180020b18`
- `0x180020ddc`
- `0x180021068`
- `0x1800212e4`

## callees

- `0x180020488`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800204a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800204a4`

## pseudocode

```c
void __fastcall CBsString::_Release(LPVOID *this)
{
  if ( *this != qword_180028260 )
    CoTaskMemFree(*this);
  *this = qword_180028260;
  this[1] = 0;
}

```

## disassembly

```asm
0x180020488  mov     [rsp+arg_0], rbx
0x18002048d  push    rdi
0x18002048e  sub     rsp, 20h
0x180020492  lea     rdi, qword_180028260
0x180020499  mov     rbx, rcx
0x18002049c  cmp     [rcx], rdi
0x18002049f  jz      short loc_1800204AA
0x1800204a1  mov     rcx, [rcx]; pv
0x1800204a4  call    cs:__imp_CoTaskMemFree
0x1800204aa  mov     [rbx], rdi
0x1800204ad  mov     qword ptr [rbx+8], 0
0x1800204b5  mov     rbx, [rsp+28h+arg_0]
0x1800204ba  add     rsp, 20h
0x1800204be  pop     rdi
0x1800204bf  retn
```
