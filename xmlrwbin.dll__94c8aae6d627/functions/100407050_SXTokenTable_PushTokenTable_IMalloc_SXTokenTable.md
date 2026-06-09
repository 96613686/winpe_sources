# SXTokenTable::PushTokenTable(IMalloc *,SXTokenTable * *)

- ea: `0x100407050`
- end: `0x1004071bb`
- name: `?PushTokenTable@SXTokenTable@@SAXPEAUIMalloc@@PEAPEAV1@@Z`
- size: `363`
- prototype: `void __fastcall(struct IMalloc *, struct SXTokenTable **)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x1004045a0`
- `0x100404f80`
- `0x100407e10`
- `0x100408d00`
- `0x10040a3c0`
- `0x10040edb0`
- `0x10040f700`
- `0x1004101e0`

## callees

- `0x100401350`
- `0x100406550`
- `0x100406e70`
- `0x100407050`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1004070a1`
- `KERNEL32!HeapAlloc` at `0x1004070a1`

## pseudocode

```c
void __fastcall SXTokenTable::PushTokenTable(struct IMalloc *a1, struct SXTokenTable **a2)
{
  SXTokenTable *v2; // rbp
  struct IMalloc *v4; // rdi
  _QWORD *v5; // rax
  _QWORD *v6; // rbx

  v2 = *a2;
  v4 = a1;
  if ( a1 || (a1 = g_pMalloc) != 0 )
    v5 = (_QWORD *)((__int64 (__fastcall *)(struct IMalloc *, __int64))a1->lpVtbl->Alloc)(a1, 216);
  else
    v5 = HeapAlloc(g_hHeap, 0, 0xD8u);
  v6 = v5;
  if ( !v5 )
  {
    MXRRaiseException(-2147024882);
    JUMPOUT(0x1004071BALL);
  }
  v5[1] = v4;
  v5[3] = v4;
  v5[4] = 0;
  *v5 = &SXTokenTable::`vftable';
  v5[2] = &_xarray<RStringPtr,_xarray_item<RStringPtr>>::`vftable';
  v5[6] = &_htablesx::`vftable';
  v5[12] = &_xarray<Unitoken,_xarray_item<Unitoken>>::`vftable';
  v5[16] = &_htablesx::`vftable';
  v5[5] = 0;
  v5[7] = v4;
  v5[8] = 0;
  *((_DWORD *)v5 + 18) = 0;
  *(_QWORD *)((char *)v5 + 76) = 128;
  *((_DWORD *)v5 + 22) = 0;
  v5[13] = v4;
  v5[14] = 0;
  v5[15] = 0;
  v5[17] = v4;
  v5[18] = 0;
  *((_DWORD *)v5 + 38) = 0;
  *(_QWORD *)((char *)v5 + 156) = 128;
  v5[22] = 0;
  v5[23] = 0;
  v5[24] = 0;
  v5[21] = 0;
  RStringPtr::assign((RStringPtr *)(v5 + 22), rspNull);
  RStringPtr::assign((RStringPtr *)(v6 + 23), rspNull);
  RStringPtr::assign((RStringPtr *)(v6 + 24), rspNull);
  *a2 = (struct SXTokenTable *)v6;
  v6[21] = v2;
  SXTokenTable::Initialize(*a2);
}

```

## disassembly

```asm
0x100407050  mov     [rsp+arg_0], rbx
0x100407055  mov     [rsp+arg_8], rbp
0x10040705a  mov     [rsp+arg_10], rsi
0x10040705f  push    rdi
0x100407060  sub     rsp, 20h
0x100407064  mov     rbp, [rdx]
0x100407067  mov     rsi, rdx
0x10040706a  mov     rdi, rcx
0x10040706d  test    rcx, rcx
0x100407070  jz      short loc_100407086
0x100407072  mov     rax, [rcx]
0x100407075  mov     edx, 0D8h
0x10040707a  mov     rax, [rax+18h]
0x10040707e  call    cs:__guard_dispatch_icall_fptr
0x100407084  jmp     short loc_1004070A7
0x100407086  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040708d  test    rcx, rcx
0x100407090  jnz     short loc_100407072
0x100407092  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100407099  xor     edx, edx; dwFlags
0x10040709b  mov     r8d, 0D8h; dwBytes
0x1004070a1  call    cs:__imp_HeapAlloc
0x1004070a7  mov     rbx, rax
0x1004070aa  test    rax, rax
0x1004070ad  jz      loc_1004071B0
0x1004070b3  xor     edx, edx
0x1004070b5  mov     [rax+8], rdi
0x1004070b9  lea     rcx, [rbx+0B0h]; this
0x1004070c0  mov     [rbx+18h], rdi
0x1004070c4  lea     rax, ??_7SXTokenTable@@6B@; const SXTokenTable::`vftable'
0x1004070cb  mov     [rbx+20h], rdx
0x1004070cf  mov     [rbx], rax
0x1004070d2  lea     rax, ??_7?$_xarray@VRStringPtr@@V?$_xarray_item@VRStringPtr@@@@@@6B@; const _xarray<RStringPtr,_xarray_item<RStringPtr>>::`vftable'
0x1004070d9  mov     [rbx+10h], rax
0x1004070dd  lea     rax, ??_7_htablesx@@6B@; const _htablesx::`vftable'
0x1004070e4  mov     [rbx+30h], rax
0x1004070e8  lea     rax, ??_7?$_xarray@VUnitoken@@V?$_xarray_item@VUnitoken@@@@@@6B@; const _xarray<Unitoken,_xarray_item<Unitoken>>::`vftable'
0x1004070ef  mov     [rbx+60h], rax
0x1004070f3  lea     rax, ??_7_htablesx@@6B@; const _htablesx::`vftable'
0x1004070fa  mov     [rbx+80h], rax
0x100407101  mov     [rbx+28h], rdx
0x100407105  mov     [rbx+38h], rdi
0x100407109  mov     [rbx+40h], rdx
0x10040710d  mov     [rbx+48h], edx
0x100407110  mov     qword ptr [rbx+4Ch], 80h
0x100407118  mov     [rbx+58h], edx
0x10040711b  mov     [rbx+68h], rdi
0x10040711f  mov     [rbx+70h], rdx
0x100407123  mov     [rbx+78h], rdx
0x100407127  mov     [rbx+88h], rdi
0x10040712e  mov     [rbx+90h], rdx
0x100407135  mov     [rbx+98h], edx
0x10040713b  mov     qword ptr [rbx+9Ch], 80h
0x100407146  mov     [rcx], rdx
0x100407149  mov     [rcx+8], rdx
0x10040714d  mov     [rcx+10h], rdx
0x100407151  mov     [rbx+0A8h], rdx
0x100407158  mov     rdx, cs:?rspNull@@3VRStringPtr@@A; struct CStringPtr *
0x10040715f  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100407164  mov     rdx, cs:?rspNull@@3VRStringPtr@@A; struct CStringPtr *
0x10040716b  lea     rcx, [rbx+0B8h]; this
0x100407172  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100407177  mov     rdx, cs:?rspNull@@3VRStringPtr@@A; struct CStringPtr *
0x10040717e  lea     rcx, [rbx+0C0h]; this
0x100407185  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040718a  mov     [rsi], rbx
0x10040718d  mov     [rbx+0A8h], rbp
0x100407194  mov     rcx, [rsi]; this
0x100407197  mov     rbx, [rsp+28h+arg_0]
0x10040719c  mov     rbp, [rsp+28h+arg_8]
0x1004071a1  mov     rsi, [rsp+28h+arg_10]
0x1004071a6  add     rsp, 20h
0x1004071aa  pop     rdi
0x1004071ab  jmp     ?Initialize@SXTokenTable@@QEAAXXZ; SXTokenTable::Initialize(void)
0x1004071b0  mov     ecx, 8007000Eh; int
0x1004071b5  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
