# CWamAdminFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002930`
- end: `0x1800029d6`
- name: `?CreateInstance@CWamAdminFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `166`
- prototype: `__int64 __fastcall(CWamAdminFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001044`
- `0x180002930`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall CWamAdminFactory::CreateInstance(
        CWamAdminFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  unsigned int v9; // ebx

  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v7 = operator new(0x20u);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  v7[6] = 1;
  *(_QWORD *)v7 = &CWamAdmin::`vftable'{for `IWamAdmin2'};
  *((_QWORD *)v7 + 1) = &CWamAdmin::`vftable'{for `IMSAdminReplication'};
  *((_QWORD *)v7 + 2) = &CWamAdmin::`vftable'{for `IIISApplicationAdmin'};
  _InterlockedIncrement((volatile signed __int32 *)&g_dwRefCount);
  v9 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v7)(v7, a3, a4);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  return v9;
}

```

## disassembly

```asm
0x180002930  mov     [rsp+arg_0], rbx
0x180002935  mov     [rsp+arg_8], rsi
0x18000293a  push    rdi
0x18000293b  sub     rsp, 20h
0x18000293f  mov     qword ptr [r9], 0
0x180002946  mov     rbx, r9
0x180002949  mov     rsi, r8
0x18000294c  test    rdx, rdx
0x18000294f  jz      short loc_180002958
0x180002951  mov     eax, 80040110h
0x180002956  jmp     short loc_1800029C6
0x180002958  mov     ecx, 20h ; ' '; Size
0x18000295d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002962  mov     rdi, rax
0x180002965  test    rax, rax
0x180002968  jz      short loc_1800029C1
0x18000296a  lea     rax, ??_7CWamAdmin@@6BIWamAdmin2@@@; const CWamAdmin::`vftable'{for `IWamAdmin2'}
0x180002971  mov     dword ptr [rdi+18h], 1
0x180002978  mov     [rdi], rax
0x18000297b  lea     rax, ??_7CWamAdmin@@6BIMSAdminReplication@@@; const CWamAdmin::`vftable'{for `IMSAdminReplication'}
0x180002982  mov     [rdi+8], rax
0x180002986  lea     rax, ??_7CWamAdmin@@6BIIISApplicationAdmin@@@; const CWamAdmin::`vftable'{for `IIISApplicationAdmin'}
0x18000298d  mov     [rdi+10h], rax
0x180002991  lock inc cs:?g_dwRefCount@@3KA; ulong g_dwRefCount
0x180002998  mov     rcx, [rdi]
0x18000299b  mov     r8, rbx
0x18000299e  mov     rdx, rsi
0x1800029a1  mov     rax, [rcx]
0x1800029a4  mov     rcx, rdi
0x1800029a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ac  mov     rcx, [rdi]
0x1800029af  mov     ebx, eax
0x1800029b1  mov     rax, [rcx+10h]
0x1800029b5  mov     rcx, rdi
0x1800029b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029bd  mov     eax, ebx
0x1800029bf  jmp     short loc_1800029C6
0x1800029c1  mov     eax, 8007000Eh
0x1800029c6  mov     rbx, [rsp+28h+arg_0]
0x1800029cb  mov     rsi, [rsp+28h+arg_8]
0x1800029d0  add     rsp, 20h
0x1800029d4  pop     rdi
0x1800029d5  retn
```
