# CWSHRemote::CreateScript(ushort *,IUnknown *)

- ea: `0x140002240`
- end: `0x140002309`
- name: `?CreateScript@CWSHRemote@@UEAAJPEAGPEAUIUnknown@@@Z`
- size: `201`
- prototype: `int(CWSHRemote *__hidden this, unsigned __int16 *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002240`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400022ac`
- `OLEAUT32!__imp_SysAllocString` at `0x1400022ac`
- `KERNEL32!GetCurrentThreadId` at `0x140002255`
- `KERNEL32!GetCurrentThreadId` at `0x140002255`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x1400022d2`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x1400022d2`

## pseudocode

```c
__int64 __fastcall CWSHRemote::CreateScript(CWSHRemote *this, unsigned __int16 *a2, struct IUnknown *a3)
{
  int v3; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT v9; // ebx
  BSTR v10; // rax
  LPUNKNOWN pUnk; // [rsp+50h] [rbp+8h] BYREF

  v3 = *((_DWORD *)this + 10);
  if ( GetCurrentThreadId() != v3 || !a3 )
    return 2147549183LL;
  if ( *((_BYTE *)this + 56) )
    return 2147500037LL;
  *((_BYTE *)this + 56) = 1;
  lpVtbl = a3->lpVtbl;
  pUnk = 0;
  v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, LPUNKNOWN *))lpVtbl->QueryInterface)(
         a3,
         &IID_IMoniker,
         &pUnk);
  if ( v9 >= 0 )
  {
    v10 = SysAllocString(a2);
    *((_QWORD *)this + 12) = v10;
    if ( v10 )
    {
      v9 = CoMarshalInterThreadInterfaceInStream(&IID_IMoniker, pUnk, (LPSTREAM *)this + 14);
      if ( v9 >= 0 )
        v9 = 0;
    }
    else
    {
      v9 = -2147024882;
    }
  }
  if ( pUnk )
    ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140002240  push    rbx
0x140002242  push    rbp
0x140002243  push    rsi
0x140002244  push    rdi
0x140002245  sub     rsp, 28h
0x140002249  mov     ebx, [rcx+28h]
0x14000224c  mov     rsi, r8
0x14000224f  mov     rbp, rdx
0x140002252  mov     rdi, rcx
0x140002255  call    cs:__imp_GetCurrentThreadId
0x14000225b  cmp     eax, ebx
0x14000225d  jnz     loc_1400022FB
0x140002263  test    rsi, rsi
0x140002266  jz      loc_1400022FB
0x14000226c  cmp     byte ptr [rdi+38h], 0
0x140002270  jz      short loc_14000227C
0x140002272  mov     eax, 80004005h
0x140002277  jmp     loc_140002300
0x14000227c  mov     byte ptr [rdi+38h], 1
0x140002280  lea     r8, [rsp+48h+pUnk]
0x140002285  mov     rax, [rsi]
0x140002288  lea     rdx, IID_IMoniker
0x14000228f  mov     rcx, rsi
0x140002292  mov     [rsp+48h+pUnk], 0
0x14000229b  mov     rax, [rax]
0x14000229e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400022a3  mov     ebx, eax
0x1400022a5  test    eax, eax
0x1400022a7  js      short loc_1400022E1
0x1400022a9  mov     rcx, rbp; psz
0x1400022ac  call    cs:__imp_SysAllocString
0x1400022b2  mov     [rdi+60h], rax
0x1400022b6  test    rax, rax
0x1400022b9  jnz     short loc_1400022C2
0x1400022bb  mov     ebx, 8007000Eh
0x1400022c0  jmp     short loc_1400022E1
0x1400022c2  mov     rdx, [rsp+48h+pUnk]; pUnk
0x1400022c7  lea     r8, [rdi+70h]; ppStm
0x1400022cb  lea     rcx, IID_IMoniker; riid
0x1400022d2  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x1400022d8  mov     ebx, eax
0x1400022da  xor     eax, eax
0x1400022dc  test    ebx, ebx
0x1400022de  cmovns  ebx, eax
0x1400022e1  mov     rcx, [rsp+48h+pUnk]
0x1400022e6  test    rcx, rcx
0x1400022e9  jz      short loc_1400022F7
0x1400022eb  mov     rax, [rcx]
0x1400022ee  mov     rax, [rax+10h]
0x1400022f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400022f7  mov     eax, ebx
0x1400022f9  jmp     short loc_140002300
0x1400022fb  mov     eax, 8000FFFFh
0x140002300  add     rsp, 28h
0x140002304  pop     rdi
0x140002305  pop     rsi
0x140002306  pop     rbp
0x140002307  pop     rbx
0x140002308  retn
```
