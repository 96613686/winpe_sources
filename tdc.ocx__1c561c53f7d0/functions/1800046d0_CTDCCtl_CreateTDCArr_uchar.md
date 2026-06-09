# CTDCCtl::CreateTDCArr(uchar)

- ea: `0x1800046d0`
- end: `0x180004800`
- name: `?CreateTDCArr@CTDCCtl@@EEAAJE@Z`
- size: `304`
- prototype: `__int64 __fastcall(CTDCCtl *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800011b8`
- `0x180003f70`
- `0x1800046d0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CTDCCtl::CreateTDCArr(CTDCCtl *this, __int64 a2)
{
  struct IUnknown **v2; // rbx
  char v3; // bp
  int v5; // edi
  struct IUnknown *v6; // rax
  __int64 v7; // r8
  __int64 v8; // rdx

  v2 = (struct IUnknown **)((char *)this + 520);
  v3 = a2;
  if ( !*((_QWORD *)this + 70) )
  {
    v5 = -2147467259;
    goto LABEL_7;
  }
  if ( !*v2 )
  {
    v6 = (struct IUnknown *)operator new(0xC8u);
    if ( !v6 )
    {
      *v2 = 0;
      v5 = -2147024882;
      goto LABEL_7;
    }
    LODWORD(v6[4].lpVtbl) = 1;
    v6->lpVtbl = (struct IUnknownVtbl *)&CTDCArr::`vftable'{for `OLEDBSimpleProvider'};
    v6[1].lpVtbl = (struct IUnknownVtbl *)&CTDCArr::`vftable'{for `CTDCFieldSink'};
    v6[16].lpVtbl = 0;
    v6[17].lpVtbl = 0;
    v6[18].lpVtbl = 0;
    v6[19].lpVtbl = 0;
    v6[20].lpVtbl = 0;
    v6[21].lpVtbl = 0;
    v6[22].lpVtbl = 0;
    v6[23].lpVtbl = 0;
    v6[24].lpVtbl = 0;
    v6[2].lpVtbl = 0;
    v6[7].lpVtbl = 0;
    v6[8].lpVtbl = 0;
    v6[9].lpVtbl = 0;
    v6[10].lpVtbl = 0;
    v7 = *((_QWORD *)this + 66);
    v8 = *((_QWORD *)this + 70);
    *v2 = v6;
    v5 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64))v6->lpVtbl[5].Release)(v6, v8, v7);
    if ( v5 < 0 )
      goto LABEL_7;
  }
  LOBYTE(a2) = v3;
  v5 = (*(__int64 (__fastcall **)(CTDCCtl *, __int64))(*(_QWORD *)this + 64LL))(this, a2);
  if ( !v5 )
  {
    LODWORD((*v2)[15].lpVtbl) = HIDWORD((*v2)[4].lpVtbl) != 3;
    return (unsigned int)v5;
  }
LABEL_7:
  if ( !v3 )
    ClearInterfaceFn(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800046d0  push    rbx
0x1800046d2  push    rbp
0x1800046d3  push    rsi
0x1800046d4  push    rdi
0x1800046d5  push    r14
0x1800046d7  sub     rsp, 20h
0x1800046db  xor     r14d, r14d
0x1800046de  lea     rbx, [rcx+208h]
0x1800046e5  mov     bpl, dl
0x1800046e8  mov     rsi, rcx
0x1800046eb  cmp     [rcx+230h], r14
0x1800046f2  jnz     short loc_1800046FE
0x1800046f4  mov     edi, 80004005h
0x1800046f9  jmp     loc_1800047CA
0x1800046fe  cmp     [rbx], r14
0x180004701  jnz     loc_1800047B2
0x180004707  mov     ecx, 0C8h; Size
0x18000470c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004711  mov     rcx, rax
0x180004714  test    rax, rax
0x180004717  jz      loc_1800047D9
0x18000471d  mov     dword ptr [rcx+20h], 1
0x180004724  lea     rax, ??_7CTDCArr@@6BOLEDBSimpleProvider@@@; const CTDCArr::`vftable'{for `OLEDBSimpleProvider'}
0x18000472b  mov     [rcx], rax
0x18000472e  lea     rax, ??_7CTDCArr@@6BCTDCFieldSink@@@; const CTDCArr::`vftable'{for `CTDCFieldSink'}
0x180004735  mov     [rcx+8], rax
0x180004739  mov     [rcx+80h], r14
0x180004740  mov     [rcx+88h], r14
0x180004747  mov     [rcx+90h], r14
0x18000474e  mov     [rcx+98h], r14
0x180004755  mov     [rcx+0A0h], r14
0x18000475c  mov     [rcx+0A8h], r14
0x180004763  mov     [rcx+0B0h], r14
0x18000476a  mov     [rcx+0B8h], r14
0x180004771  mov     [rcx+0C0h], r14
0x180004778  mov     [rcx+10h], r14
0x18000477c  mov     [rcx+38h], r14
0x180004780  mov     [rcx+40h], r14
0x180004784  mov     [rcx+48h], r14
0x180004788  mov     [rcx+50h], r14
0x18000478c  mov     r8, [rsi+210h]
0x180004793  mov     rdx, [rsi+230h]
0x18000479a  mov     [rbx], rcx
0x18000479d  mov     rax, [rcx]
0x1800047a0  mov     rax, [rax+88h]
0x1800047a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ac  mov     edi, eax
0x1800047ae  test    eax, eax
0x1800047b0  js      short loc_1800047CA
0x1800047b2  mov     rax, [rsi]
0x1800047b5  mov     dl, bpl
0x1800047b8  mov     rcx, rsi
0x1800047bb  mov     rax, [rax+40h]
0x1800047bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047c4  mov     edi, eax
0x1800047c6  test    eax, eax
0x1800047c8  jz      short loc_1800047E3
0x1800047ca  test    bpl, bpl
0x1800047cd  jnz     short loc_1800047F3
0x1800047cf  mov     rcx, rbx; struct IUnknown **
0x1800047d2  call    ?ClearInterfaceFn@@YAXPEAPEAUIUnknown@@@Z; ClearInterfaceFn(IUnknown * *)
0x1800047d7  jmp     short loc_1800047F3
0x1800047d9  mov     [rbx], r14
0x1800047dc  mov     edi, 8007000Eh
0x1800047e1  jmp     short loc_1800047CA
0x1800047e3  mov     rcx, [rbx]
0x1800047e6  mov     eax, r14d
0x1800047e9  cmp     dword ptr [rcx+24h], 3
0x1800047ed  setnz   al
0x1800047f0  mov     [rcx+78h], eax
0x1800047f3  mov     eax, edi
0x1800047f5  add     rsp, 20h
0x1800047f9  pop     r14
0x1800047fb  pop     rdi
0x1800047fc  pop     rsi
0x1800047fd  pop     rbp
0x1800047fe  pop     rbx
0x1800047ff  retn
```
