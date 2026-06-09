# CWSHExtension::DragEnter(IDataObject *,ulong,_POINTL,ulong *)

- ea: `0x180006720`
- end: `0x1800067a1`
- name: `?DragEnter@CWSHExtension@@UEAAJPEAUIDataObject@@KU_POINTL@@PEAK@Z`
- size: `129`
- prototype: `__int64 __fastcall(CWSHExtension *__hidden this, struct IDataObject *, unsigned int, struct _POINTL, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180006720`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CWSHExtension::DragEnter(
        CWSHExtension *this,
        struct IDataObject *a2,
        __int64 a3,
        struct _POINTL a4,
        unsigned int *a5)
{
  struct IDataObjectVtbl *lpVtbl; // rax
  __int128 v7; // [rsp+20h] [rbp-48h] BYREF
  __int64 v8; // [rsp+30h] [rbp-38h]
  __int128 v9; // [rsp+38h] [rbp-30h] BYREF
  __int128 v10; // [rsp+48h] [rbp-20h]

  v8 = 0;
  v10 = 0;
  v9 = 0;
  LOWORD(v9) = 15;
  lpVtbl = a2->lpVtbl;
  *(_QWORD *)((char *)&v10 + 4) = 0x1FFFFFFFFLL;
  v7 = 0;
  LODWORD(v10) = 1;
  if ( ((int (__fastcall *)(struct IDataObject *, __int128 *, __int128 *, struct _POINTL))lpVtbl->GetData)(
         a2,
         &v9,
         &v7,
         a4) >= 0 )
  {
    *a5 = 1;
    return 0;
  }
  else
  {
    *a5 = 0;
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180006720  sub     rsp, 68h
0x180006724  xor     eax, eax
0x180006726  lea     r8, [rsp+68h+var_48]
0x18000672b  mov     [rsp+68h+var_38], rax
0x180006730  xorps   xmm1, xmm1
0x180006733  movups  [rsp+68h+var_20], xmm1
0x180006738  mov     eax, 0Fh
0x18000673d  mov     dword ptr [rsp+68h+var_20+8], 1
0x180006745  movups  [rsp+68h+var_30], xmm1
0x18000674a  mov     word ptr [rsp+68h+var_30], ax
0x18000674f  mov     rcx, rdx
0x180006752  mov     rax, [rdx]
0x180006755  xorps   xmm0, xmm0
0x180006758  lea     rdx, [rsp+68h+var_30]
0x18000675d  mov     dword ptr [rsp+68h+var_20+4], 0FFFFFFFFh
0x180006765  movups  [rsp+68h+var_48], xmm0
0x18000676a  mov     dword ptr [rsp+68h+var_20], 1
0x180006772  mov     rax, [rax+18h]
0x180006776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000677b  test    eax, eax
0x18000677d  mov     rax, [rsp+68h+arg_20]
0x180006785  jns     short loc_180006794
0x180006787  mov     dword ptr [rax], 0
0x18000678d  mov     eax, 80004005h
0x180006792  jmp     short loc_18000679C
0x180006794  mov     dword ptr [rax], 1
0x18000679a  xor     eax, eax
0x18000679c  add     rsp, 68h
0x1800067a0  retn
```
