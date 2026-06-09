# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x1400050b8`
- end: `0x14000527a`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `450`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004c94`
- `0x140005280`
- `0x140005300`
- `0x140005b00`
- `0x140005bb0`

## callees

- `0x140001014`
- `0x1400050b8`
- `0x140005ee4`
- `0x14000f010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140005206`
- `KERNEL32!LeaveCriticalSection` at `0x140005267`
- `KERNEL32!LeaveCriticalSection` at `0x140005206`
- `KERNEL32!LeaveCriticalSection` at `0x140005267`
- `KERNEL32!EnterCriticalSection` at `0x1400050e9`
- `KERNEL32!EnterCriticalSection` at `0x1400051e7`
- `KERNEL32!EnterCriticalSection` at `0x1400050e9`
- `KERNEL32!EnterCriticalSection` at `0x1400051e7`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x140005116`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x140005116`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  HRESULT NameCache; // esi
  WORD v6; // r8
  WORD v7; // dx
  const GUID *v8; // rcx
  __int64 v9; // rdx
  int (__fastcall ***v10)(_QWORD, GUID *, _QWORD *); // rcx
  int (__fastcall ***v11)(_QWORD, GUID *, _QWORD *); // rbx
  int (__fastcall ***v12)(_QWORD, GUID *, _QWORD *); // r14
  _QWORD *v13; // rbx
  struct ITypeInfo *v14; // rdx
  int (__fastcall ***v15)(_QWORD, GUID *, _QWORD *); // [rsp+60h] [rbp+30h] BYREF
  int (__fastcall ***v16)(_QWORD, GUID *, _QWORD *); // [rsp+70h] [rbp+40h] BYREF
  ITypeLib *pptlib; // [rsp+78h] [rbp+48h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  NameCache = 0;
  EnterCriticalSection(&Buf1);
  if ( !*((_QWORD *)this + 3) )
  {
    v6 = *((_WORD *)this + 9);
    v7 = *((_WORD *)this + 8);
    v8 = (const GUID *)*((_QWORD *)this + 1);
    pptlib = 0;
    NameCache = LoadRegTypeLib(v8, v7, v6, lcid, &pptlib);
    if ( NameCache >= 0 )
    {
      v9 = *(_QWORD *)this;
      v15 = 0;
      NameCache = ((__int64 (__fastcall *)(ITypeLib *, __int64, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                    pptlib,
                    v9,
                    &v15);
      if ( NameCache >= 0 )
      {
        v10 = v15;
        v11 = v15;
        if ( v15 )
        {
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v15)[1])(v15);
          v10 = v15;
        }
        v16 = 0;
        if ( (**v10)(v10, &GUID_00020412_0000_0000_c000_000000000046, &v16) >= 0 )
        {
          v12 = v16;
          if ( v16 )
            ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v16)[1])(v16);
          if ( v11 )
            ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v11)[2])(v11);
          v11 = v12;
        }
        *((_QWORD *)this + 3) = v11;
        v13 = operator new(0x18u);
        if ( v13 )
        {
          v13[1] = this;
          *v13 = ATL::CComTypeInfoHolder::Cleanup;
          EnterCriticalSection(&Buf1);
          v13[2] = qword_140015498;
          qword_140015498 = v13;
          LeaveCriticalSection(&Buf1);
        }
        if ( v16 )
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v16)[2])(v16);
      }
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
      if ( v15 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v15)[2])(v15);
    }
  }
  v14 = (struct ITypeInfo *)*((_QWORD *)this + 3);
  if ( v14 )
  {
    if ( !*((_QWORD *)this + 5) )
      NameCache = ATL::CComTypeInfoHolder::LoadNameCache(this, v14);
  }
  LeaveCriticalSection(&Buf1);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x1400050b8  push    rbp
0x1400050ba  push    rbx
0x1400050bb  push    rsi
0x1400050bc  push    rdi
0x1400050bd  push    r14
0x1400050bf  mov     rbp, rsp
0x1400050c2  sub     rsp, 30h
0x1400050c6  cmp     qword ptr [rcx+18h], 0
0x1400050cb  mov     ebx, edx
0x1400050cd  mov     rdi, rcx
0x1400050d0  jz      short loc_1400050E0
0x1400050d2  cmp     qword ptr [rcx+28h], 0
0x1400050d7  jz      short loc_1400050E0
0x1400050d9  xor     eax, eax
0x1400050db  jmp     loc_14000526F
0x1400050e0  lea     rcx, Buf1; lpCriticalSection
0x1400050e7  xor     esi, esi
0x1400050e9  call    cs:__imp_EnterCriticalSection
0x1400050ef  cmp     [rdi+18h], rsi
0x1400050f3  jnz     loc_140005246
0x1400050f9  movzx   r8d, word ptr [rdi+12h]; wVerMinor
0x1400050fe  lea     rax, [rbp+arg_18]
0x140005102  movzx   edx, word ptr [rdi+10h]; wVerMajor
0x140005106  mov     r9d, ebx; lcid
0x140005109  mov     rcx, [rdi+8]; rguid
0x14000510d  mov     [rsp+30h+pptlib], rax; pptlib
0x140005112  mov     [rbp+arg_18], rsi
0x140005116  call    cs:__imp_LoadRegTypeLib
0x14000511c  mov     esi, eax
0x14000511e  test    eax, eax
0x140005120  js      loc_140005246
0x140005126  mov     rcx, [rbp+arg_18]
0x14000512a  lea     r8, [rbp+arg_0]
0x14000512e  mov     rdx, [rdi]
0x140005131  mov     [rbp+arg_0], 0
0x140005139  mov     rax, [rcx]
0x14000513c  mov     rax, [rax+30h]
0x140005140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005145  mov     esi, eax
0x140005147  test    eax, eax
0x140005149  js      loc_140005221
0x14000514f  mov     rcx, [rbp+arg_0]
0x140005153  mov     rbx, rcx
0x140005156  test    rcx, rcx
0x140005159  jz      short loc_14000516B
0x14000515b  mov     rax, [rcx]
0x14000515e  mov     rax, [rax+8]
0x140005162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005167  mov     rcx, [rbp+arg_0]
0x14000516b  mov     [rbp+arg_10], 0
0x140005173  lea     r8, [rbp+arg_10]
0x140005177  mov     rax, [rcx]
0x14000517a  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x140005181  mov     rax, [rax]
0x140005184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005189  test    eax, eax
0x14000518b  js      short loc_1400051BC
0x14000518d  mov     r14, [rbp+arg_10]
0x140005191  test    r14, r14
0x140005194  jz      short loc_1400051A5
0x140005196  mov     rax, [r14]
0x140005199  mov     rcx, r14
0x14000519c  mov     rax, [rax+8]
0x1400051a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051a5  test    rbx, rbx
0x1400051a8  jz      short loc_1400051B9
0x1400051aa  mov     rax, [rbx]
0x1400051ad  mov     rcx, rbx
0x1400051b0  mov     rax, [rax+10h]
0x1400051b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051b9  mov     rbx, r14
0x1400051bc  mov     ecx, 18h; Size
0x1400051c1  mov     [rdi+18h], rbx
0x1400051c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400051ca  mov     rbx, rax
0x1400051cd  test    rax, rax
0x1400051d0  jz      short loc_14000520C
0x1400051d2  lea     rax, ?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z; ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)
0x1400051d9  mov     [rbx+8], rdi
0x1400051dd  lea     rcx, Buf1; lpCriticalSection
0x1400051e4  mov     [rbx], rax
0x1400051e7  call    cs:__imp_EnterCriticalSection
0x1400051ed  mov     rcx, cs:qword_140015498
0x1400051f4  mov     [rbx+10h], rcx
0x1400051f8  lea     rcx, Buf1; lpCriticalSection
0x1400051ff  mov     cs:qword_140015498, rbx
0x140005206  call    cs:__imp_LeaveCriticalSection
0x14000520c  mov     rcx, [rbp+arg_10]
0x140005210  test    rcx, rcx
0x140005213  jz      short loc_140005221
0x140005215  mov     rax, [rcx]
0x140005218  mov     rax, [rax+10h]
0x14000521c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005221  mov     rcx, [rbp+arg_18]
0x140005225  mov     rax, [rcx]
0x140005228  mov     rax, [rax+10h]
0x14000522c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005231  mov     rcx, [rbp+arg_0]
0x140005235  test    rcx, rcx
0x140005238  jz      short loc_140005246
0x14000523a  mov     rax, [rcx]
0x14000523d  mov     rax, [rax+10h]
0x140005241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005246  mov     rdx, [rdi+18h]; struct ITypeInfo *
0x14000524a  test    rdx, rdx
0x14000524d  jz      short loc_140005260
0x14000524f  cmp     qword ptr [rdi+28h], 0
0x140005254  jnz     short loc_140005260
0x140005256  mov     rcx, rdi; this
0x140005259  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x14000525e  mov     esi, eax
0x140005260  lea     rcx, Buf1; lpCriticalSection
0x140005267  call    cs:__imp_LeaveCriticalSection
0x14000526d  mov     eax, esi
0x14000526f  add     rsp, 30h
0x140005273  pop     r14
0x140005275  pop     rdi
0x140005276  pop     rsi
0x140005277  pop     rbx
0x140005278  pop     rbp
0x140005279  retn
```
