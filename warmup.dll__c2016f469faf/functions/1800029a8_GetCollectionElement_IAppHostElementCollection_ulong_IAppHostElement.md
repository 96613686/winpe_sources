# GetCollectionElement(IAppHostElementCollection *,ulong,IAppHostElement * *)

- ea: `0x1800029a8`
- end: `0x1800029e9`
- name: `?GetCollectionElement@@YAJPEAUIAppHostElementCollection@@KPEAPEAUIAppHostElement@@@Z`
- size: `65`
- prototype: `__int64 __fastcall(struct IAppHostElementCollection *, unsigned int, struct IAppHostElement **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003818`
- `0x180003c74`

## callees

- `0x180006010`

## pseudocode

```c
__int64 __fastcall GetCollectionElement(struct IAppHostElementCollection *a1, int a2, struct IAppHostElement **a3)
{
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+30h] [rbp-18h]

  v4 = 0;
  DWORD2(v4) = a2;
  v5 = 0;
  LOWORD(v4) = 19;
  return ((__int64 (__fastcall *)(struct IAppHostElementCollection *, __int128 *, struct IAppHostElement **))a1->lpVtbl->get_Item)(
           a1,
           &v4,
           a3);
}

```

## disassembly

```asm
0x1800029a8  sub     rsp, 48h
0x1800029ac  xor     r9d, r9d
0x1800029af  xorps   xmm0, xmm0
0x1800029b2  movups  [rsp+48h+var_28], xmm0
0x1800029b7  mov     dword ptr [rsp+48h+var_28+8], edx
0x1800029bb  lea     rdx, [rsp+48h+var_28]
0x1800029c0  mov     [rsp+48h+var_18], r9
0x1800029c5  lea     eax, [r9+13h]
0x1800029c9  mov     word ptr [rsp+48h+var_28], ax
0x1800029ce  mov     rax, [rcx]
0x1800029d1  movups  xmm0, [rsp+48h+var_28]
0x1800029d6  mov     rax, [rax+20h]
0x1800029da  movaps  [rsp+48h+var_28], xmm0
0x1800029df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029e4  add     rsp, 48h
0x1800029e8  retn
```
