# CEnumInst::CEnumInst(CEnumInfo *,long,ushort *,IWbemServices *,CImpDyn *,IWbemContext *)

- ea: `0x180003f64`
- end: `0x1800040c1`
- name: `??0CEnumInst@@QEAA@PEAVCEnumInfo@@JPEAGPEAUIWbemServices@@PEAVCImpDyn@@PEAUIWbemContext@@@Z`
- size: `349`
- prototype: `CEnumInst *__fastcall(CEnumInst *this, struct CEnumInfo *, int, unsigned __int16 *, struct IWbemServices *, struct CImpDyn *, struct IWbemContext *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003190`
- `0x18000da00`

## callees

- `0x180002e10`
- `0x180003f64`
- `0x1800042ac`
- `0x18000b178`
- `0x180017010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003fdf`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180003fdf`

## pseudocode

```c
CEnumInst *__fastcall CEnumInst::CEnumInst(
        CEnumInst *this,
        struct CEnumInfo *a2,
        int a3,
        unsigned __int16 *a4,
        struct IWbemServices *a5,
        struct CImpDyn *a6,
        struct IWbemContext *a7)
{
  __int64 v11; // rax
  unsigned int v12; // esi
  unsigned __int16 *v13; // rax
  CImpDyn *v14; // rcx
  struct IWbemClassObject *v16; // [rsp+40h] [rbp-48h] BYREF

  *(_QWORD *)this = &CEnumInst::`vftable';
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 9) = 0;
  CIndexCache::CIndexCache((CEnumInst *)((char *)this + 80));
  v11 = -1;
  do
    ++v11;
  while ( a4[v11] );
  v12 = v11 + 1;
  v13 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v11 + 1), 2u));
  *((_QWORD *)this + 3) = v13;
  if ( v13 )
  {
    StringCchCopyW(v13, v12, a4);
    *((_QWORD *)this + 6) = a5;
    ((void (__fastcall *)(struct IWbemServices *))a5->lpVtbl->AddRef)(a5);
    *((_QWORD *)this + 7) = a6;
    (*(void (__fastcall **)(struct CImpDyn *))(*(_QWORD *)a6 + 8LL))(a6);
    *((_DWORD *)this + 8) = a3;
    *((_QWORD *)this + 2) = a2;
    _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
    *((_QWORD *)this + 5) = a7;
    if ( a7 )
      ((void (__fastcall *)(struct IWbemContext *))a7->lpVtbl->AddRef)(a7);
    _InterlockedIncrement(&lObj);
    v16 = 0;
    if ( (*(int (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, _QWORD, struct IWbemClassObject **, _QWORD))(**((_QWORD **)this + 6) + 48LL))(
           *((_QWORD *)this + 6),
           a4,
           0,
           *((_QWORD *)this + 5),
           &v16,
           0) >= 0 )
    {
      *((_QWORD *)this + 9) = CImpDyn::GetKeyName(v14, v16);
      ((void (__fastcall *)(struct IWbemClassObject *))v16->lpVtbl->Release)(v16);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180003f64  mov     [rsp+arg_0], rcx
0x180003f69  push    rbx
0x180003f6a  push    rbp
0x180003f6b  push    rsi
0x180003f6c  push    rdi
0x180003f6d  push    r14
0x180003f6f  push    r15
0x180003f71  sub     rsp, 58h
0x180003f75  mov     rdi, r9
0x180003f78  mov     r14d, r8d
0x180003f7b  mov     rbp, rdx
0x180003f7e  mov     rbx, rcx
0x180003f81  lea     rax, ??_7CEnumInst@@6B@; const CEnumInst::`vftable'
0x180003f88  mov     [rcx], rax
0x180003f8b  xor     r15d, r15d
0x180003f8e  mov     [rcx+8], r15d
0x180003f92  mov     [rcx+10h], r15
0x180003f96  mov     [rcx+18h], r15
0x180003f9a  mov     [rcx+20h], r15d
0x180003f9e  mov     [rcx+28h], r15
0x180003fa2  mov     [rcx+30h], r15
0x180003fa6  mov     [rcx+38h], r15
0x180003faa  mov     [rcx+40h], r15d
0x180003fae  mov     [rcx+48h], r15
0x180003fb2  add     rcx, 50h ; 'P'; this
0x180003fb6  call    ??0CIndexCache@@QEAA@XZ; CIndexCache::CIndexCache(void)
0x180003fbb  nop
0x180003fbc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180003fc0  mov     rax, rcx
0x180003fc3  inc     rax
0x180003fc6  cmp     [rdi+rax*2], r15w
0x180003fcb  jnz     short loc_180003FC3
0x180003fcd  lea     esi, [rax+1]
0x180003fd0  mov     eax, 2
0x180003fd5  mul     rsi
0x180003fd8  cmovb   rax, rcx
0x180003fdc  mov     rcx, rax
0x180003fdf  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180003fe5  mov     [rbx+18h], rax
0x180003fe9  test    rax, rax
0x180003fec  jz      loc_1800040B1
0x180003ff2  mov     r8, rdi; unsigned __int16 *
0x180003ff5  mov     edx, esi; unsigned __int64
0x180003ff7  mov     rcx, rax; unsigned __int16 *
0x180003ffa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003fff  mov     rcx, [rsp+88h+arg_20]
0x180004007  mov     [rbx+30h], rcx
0x18000400b  mov     rax, [rcx]
0x18000400e  mov     rax, [rax+8]
0x180004012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004017  mov     rcx, [rsp+88h+arg_28]
0x18000401f  mov     [rbx+38h], rcx
0x180004023  mov     rax, [rcx]
0x180004026  mov     rax, [rax+8]
0x18000402a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000402f  mov     [rbx+20h], r14d
0x180004033  mov     [rbx+10h], rbp
0x180004037  lock inc dword ptr [rbp+8]
0x18000403b  mov     rcx, [rsp+88h+arg_30]
0x180004043  mov     [rbx+28h], rcx
0x180004047  test    rcx, rcx
0x18000404a  jz      short loc_180004058
0x18000404c  mov     rax, [rcx]
0x18000404f  mov     rax, [rax+8]
0x180004053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004058  lock inc cs:?lObj@@3JA; long lObj
0x18000405f  mov     [rsp+88h+var_48], r15
0x180004064  mov     rcx, [rbx+30h]
0x180004068  mov     rax, [rcx]
0x18000406b  mov     [rsp+88h+var_60], r15
0x180004070  lea     rdx, [rsp+88h+var_48]
0x180004075  mov     [rsp+88h+var_68], rdx
0x18000407a  mov     r9, [rbx+28h]
0x18000407e  xor     r8d, r8d
0x180004081  mov     rdx, rdi
0x180004084  mov     rax, [rax+30h]
0x180004088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000408d  test    eax, eax
0x18000408f  js      short loc_1800040B1
0x180004091  mov     rdx, [rsp+88h+var_48]; struct IWbemClassObject *
0x180004096  call    ?GetKeyName@CImpDyn@@QEAAPEAGPEAUIWbemClassObject@@@Z; CImpDyn::GetKeyName(IWbemClassObject *)
0x18000409b  mov     [rbx+48h], rax
0x18000409f  mov     rcx, [rsp+88h+var_48]
0x1800040a4  mov     rax, [rcx]
0x1800040a7  mov     rax, [rax+10h]
0x1800040ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040b0  nop
0x1800040b1  mov     rax, rbx
0x1800040b4  add     rsp, 58h
0x1800040b8  pop     r15
0x1800040ba  pop     r14
0x1800040bc  pop     rdi
0x1800040bd  pop     rsi
0x1800040be  pop     rbp
0x1800040bf  pop     rbx
0x1800040c0  retn
```
