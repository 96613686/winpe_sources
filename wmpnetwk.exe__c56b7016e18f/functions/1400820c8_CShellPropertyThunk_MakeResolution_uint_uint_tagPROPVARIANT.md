# CShellPropertyThunk::MakeResolution(uint,uint,tagPROPVARIANT *)

- ea: `0x1400820c8`
- end: `0x14008213d`
- name: `?MakeResolution@CShellPropertyThunk@@CAJIIPEAUtagPROPVARIANT@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140032180`

## callees

- `0x14002e9cc`
- `0x1400820c8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14008211e`
- `ole32!CoTaskMemFree` at `0x14008211e`
- `ole32!CoTaskMemAlloc` at `0x1400820e3`
- `ole32!CoTaskMemAlloc` at `0x1400820e3`

## pseudocode

```c
__int64 __fastcall CShellPropertyThunk::MakeResolution(unsigned int a1, int a2, struct tagPROPVARIANT *a3)
{
  unsigned __int16 *v6; // rax
  int v7; // ebx

  v6 = (unsigned __int16 *)CoTaskMemAlloc(0x28u);
  a3->hVal.QuadPart = (LONGLONG)v6;
  if ( v6 )
  {
    v7 = StringCchPrintfW(v6, 0x14u, L"%ux%u", a1, a2);
    if ( v7 < 0 )
      CoTaskMemFree(a3->puuid);
    else
      a3->vt = 31;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400820c8  mov     [rsp+arg_0], rbx
0x1400820cd  mov     [rsp+arg_8], rsi
0x1400820d2  push    rdi
0x1400820d3  sub     rsp, 30h
0x1400820d7  mov     esi, ecx
0x1400820d9  mov     rdi, r8
0x1400820dc  mov     ecx, 28h ; '('; cb
0x1400820e1  mov     ebx, edx
0x1400820e3  call    cs:__imp_CoTaskMemAlloc
0x1400820e9  mov     [rdi+8], rax
0x1400820ed  test    rax, rax
0x1400820f0  jz      short loc_140082126
0x1400820f2  mov     r9d, esi
0x1400820f5  mov     [rsp+38h+var_18], ebx
0x1400820f9  lea     r8, aUxU; "%ux%u"
0x140082100  mov     edx, 14h; unsigned __int64
0x140082105  mov     rcx, rax; unsigned __int16 *
0x140082108  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14008210d  mov     ebx, eax
0x14008210f  test    eax, eax
0x140082111  js      short loc_14008211A
0x140082113  mov     word ptr [rdi], 1Fh
0x140082118  jmp     short loc_14008212B
0x14008211a  mov     rcx, [rdi+8]; pv
0x14008211e  call    cs:__imp_CoTaskMemFree
0x140082124  jmp     short loc_14008212B
0x140082126  mov     ebx, 8007000Eh
0x14008212b  mov     rsi, [rsp+38h+arg_8]
0x140082130  mov     eax, ebx
0x140082132  mov     rbx, [rsp+38h+arg_0]
0x140082137  add     rsp, 30h
0x14008213b  pop     rdi
0x14008213c  retn
```
