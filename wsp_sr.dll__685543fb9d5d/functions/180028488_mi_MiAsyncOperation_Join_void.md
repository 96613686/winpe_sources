# mi::MiAsyncOperation::Join(void)

- ea: `0x180028488`
- end: `0x1800284b9`
- name: `?Join@MiAsyncOperation@mi@@QEAAXXZ`
- size: `49`
- prototype: `void __fastcall(mi::MiAsyncOperation *__hidden this)`
- caller_count: `31`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a804`
- `0x18000cec8`
- `0x180013964`
- `0x180015358`
- `0x180016170`
- `0x180016424`
- `0x180019388`
- `0x18001db88`
- `0x18001dff4`
- `0x18001e200`
- `0x18001e390`
- `0x18001e5d4`
- `0x18001e790`
- `0x18001e88c`
- `0x18001ea08`
- `0x18001ebd0`
- `0x18001ed30`
- `0x18001eec0`
- `0x18001f18c`
- `0x18001f354`
- `0x18001f4e4`
- `0x18001f674`
- `0x18001f7d8`
- `0x18001fa48`
- `0x180021af0`
- `0x180021bf0`
- `0x180022788`
- `0x180022958`
- `0x180022b1c`
- `0x180022ce0`
- `0x180022ea4`

## callees

- `0x180028488`
- `0x1800284c0`

## pseudocode

```c
void __fastcall mi::MiAsyncOperation::Join(mi::MiAsyncOperation *this)
{
  bool v1; // zf
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 7) == 0;
  v2 = 0x7FFFFFFFFFFFFFFFLL;
  if ( !v1 )
    mi::MiAsyncOperation::MiOperationArgs::Join(*((RTL_SRWLOCK **)this + 9), (int *)&v2, 1);
}

```

## disassembly

```asm
0x180028488  sub     rsp, 28h
0x18002848c  cmp     qword ptr [rcx+38h], 0
0x180028491  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002849b  mov     [rsp+28h+arg_0], rax
0x1800284a0  jz      short loc_1800284B3
0x1800284a2  mov     rcx, [rcx+48h]; this
0x1800284a6  lea     rdx, [rsp+28h+arg_0]
0x1800284ab  mov     r8b, 1
0x1800284ae  call    ?Join@MiOperationArgs@MiAsyncOperation@mi@@QEAA_NAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_N@Z; mi::MiAsyncOperation::MiOperationArgs::Join(std::chrono::duration<__int64,std::ratio<1,1000>> const &,bool)
0x1800284b3  add     rsp, 28h
0x1800284b7  retn
```
