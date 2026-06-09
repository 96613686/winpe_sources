# mi::MiAsyncOperation::Join(void)

- ea: `0x1800280c0`
- end: `0x1800280f0`
- name: `?Join@MiAsyncOperation@mi@@QEAAXXZ`
- size: `48`
- prototype: `void __fastcall(mi::MiAsyncOperation::MiOperationArgs **this)`
- caller_count: `31`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a6a8`
- `0x18000cfa4`
- `0x180013a5c`
- `0x1800154a4`
- `0x1800162b8`
- `0x180016568`
- `0x18001935c`
- `0x18001da60`
- `0x18001decc`
- `0x18001e0d4`
- `0x18001e264`
- `0x18001e4a8`
- `0x18001e664`
- `0x18001e75c`
- `0x18001e8d8`
- `0x18001eaa0`
- `0x18001ec00`
- `0x18001ed90`
- `0x18001f058`
- `0x18001f220`
- `0x18001f3b0`
- `0x18001f540`
- `0x18001f6a0`
- `0x18001f910`
- `0x180021950`
- `0x180021a50`
- `0x1800225cc`
- `0x180022798`
- `0x18002295c`
- `0x180022b20`
- `0x180022ce4`

## callees

- `0x1800280c0`
- `0x1800280f8`

## pseudocode

```c
void __fastcall mi::MiAsyncOperation::Join(mi::MiAsyncOperation::MiOperationArgs **this)
{
  if ( this[7] )
    mi::MiAsyncOperation::MiOperationArgs::Join(this[9]);
}

```

## disassembly

```asm
0x1800280c0  sub     rsp, 28h
0x1800280c4  cmp     qword ptr [rcx+38h], 0
0x1800280c9  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800280d3  mov     [rsp+28h+arg_0], rax
0x1800280d8  jz      short loc_1800280EB
0x1800280da  mov     rcx, [rcx+48h]; this
0x1800280de  lea     rdx, [rsp+28h+arg_0]
0x1800280e3  mov     r8b, 1
0x1800280e6  call    ?Join@MiOperationArgs@MiAsyncOperation@mi@@QEAA_NAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_N@Z; mi::MiAsyncOperation::MiOperationArgs::Join(std::chrono::duration<__int64,std::ratio<1,1000>> const &,bool)
0x1800280eb  add     rsp, 28h
0x1800280ef  retn
```
