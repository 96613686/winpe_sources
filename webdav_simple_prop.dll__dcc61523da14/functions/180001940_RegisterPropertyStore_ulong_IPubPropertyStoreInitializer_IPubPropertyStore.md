# RegisterPropertyStore(ulong,IPubPropertyStoreInitializer *,IPubPropertyStore * *)

- ea: `0x180001940`
- end: `0x180001992`
- name: `?RegisterPropertyStore@@YAJKPEAVIPubPropertyStoreInitializer@@PEAPEAVIPubPropertyStore@@@Z`
- size: `82`
- prototype: `__int64 __fastcall(int, struct IPubPropertyStoreInitializer *, struct IPubPropertyStore **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001008`
- `0x180001940`

## pseudocode

```c
__int64 __fastcall RegisterPropertyStore(
        int a1,
        struct IPubPropertyStoreInitializer *a2,
        struct IPubPropertyStore **a3)
{
  struct IPubPropertyStore *v5; // rax

  *a3 = 0;
  if ( a1 != 1 )
    return 2147500033LL;
  v5 = (struct IPubPropertyStore *)operator new(0x10u);
  if ( v5 )
  {
    *((_QWORD *)v5 + 1) = 1;
    *(_QWORD *)v5 = &INI_STORE::`vftable';
  }
  *a3 = v5;
  return v5 == 0 ? 0x80070008 : 0;
}

```

## disassembly

```asm
0x180001940  push    rbx
0x180001942  sub     rsp, 20h
0x180001946  mov     qword ptr [r8], 0
0x18000194d  mov     rbx, r8
0x180001950  cmp     ecx, 1
0x180001953  jz      short loc_18000195C
0x180001955  mov     eax, 80004001h
0x18000195a  jmp     short loc_18000198C
0x18000195c  mov     ecx, 10h; Size
0x180001961  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001966  test    rax, rax
0x180001969  jz      short loc_18000197D
0x18000196b  lea     rcx, ??_7INI_STORE@@6B@; const INI_STORE::`vftable'
0x180001972  mov     qword ptr [rax+8], 1
0x18000197a  mov     [rax], rcx
0x18000197d  mov     [rbx], rax
0x180001980  neg     rax
0x180001983  sbb     eax, eax
0x180001985  not     eax
0x180001987  and     eax, 80070008h
0x18000198c  add     rsp, 20h
0x180001990  pop     rbx
0x180001991  retn
```
