# CScriptedDiagFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800140c0`
- end: `0x1800141cd`
- name: `?CreateInstance@CScriptedDiagFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `269`
- prototype: `__int64 __fastcall(CScriptedDiagFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001264`
- `0x1800140c0`
- `0x180026fa0`
- `0x18002a010`

## string_xrefs

- `0x180014179`: `CScriptedDiagFactory::CreateInstance`
- `0x1800141a8`: `CScriptedDiagFactory::CreateInstance`

## pseudocode

```c
__int64 __fastcall CScriptedDiagFactory::CreateInstance(
        CScriptedDiagFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // edi
  _DWORD *v7; // rbx
  int v8; // eax

  if ( !a4 )
  {
    v6 = -2147024809;
LABEL_10:
    SdpDebugTrace(1u, L"CScriptedDiagFactory::CreateInstance", 37, v6);
    return v6;
  }
  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    goto LABEL_10;
  }
  v7 = operator new(0x38u);
  if ( !v7 )
  {
    v6 = -2147024882;
    goto LABEL_10;
  }
  v7[2] = 1;
  *(_QWORD *)v7 = &CScriptedDiag::`vftable';
  *((_QWORD *)v7 + 2) = 0;
  *((_QWORD *)v7 + 3) = 0;
  *((_QWORD *)v7 + 4) = 0;
  *((_QWORD *)v7 + 5) = 0;
  v7[12] = 0;
  _InterlockedIncrement(&g_Count);
  v8 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v7)(v7, a3, a4);
  v6 = v8;
  if ( v8 < 0 )
    SdpDebugTrace(1u, L"CScriptedDiagFactory::CreateInstance", 37, v8);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v6;
}

```

## disassembly

```asm
0x1800140c0  mov     [rsp+arg_0], rbx
0x1800140c5  mov     [rsp+arg_8], rbp
0x1800140ca  push    rdi
0x1800140cb  sub     rsp, 20h
0x1800140cf  mov     rdi, r9
0x1800140d2  mov     rbp, r8
0x1800140d5  test    r9, r9
0x1800140d8  jnz     short loc_1800140E4
0x1800140da  mov     edi, 80070057h
0x1800140df  jmp     loc_1800141A2
0x1800140e4  mov     qword ptr [r9], 0
0x1800140eb  test    rdx, rdx
0x1800140ee  jz      short loc_1800140FA
0x1800140f0  mov     edi, 80040110h
0x1800140f5  jmp     loc_1800141A2
0x1800140fa  mov     ecx, 38h ; '8'; Size
0x1800140ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014104  mov     [rsp+28h+arg_18], rax
0x180014109  mov     rbx, rax
0x18001410c  test    rax, rax
0x18001410f  jz      loc_18001419D
0x180014115  lea     rax, ??_7CScriptedDiag@@6B@; const CScriptedDiag::`vftable'
0x18001411c  mov     dword ptr [rbx+8], 1
0x180014123  mov     [rbx], rax
0x180014126  mov     qword ptr [rbx+10h], 0
0x18001412e  mov     qword ptr [rbx+18h], 0
0x180014136  mov     qword ptr [rbx+20h], 0
0x18001413e  mov     qword ptr [rbx+28h], 0
0x180014146  mov     dword ptr [rbx+30h], 0
0x18001414d  lock inc cs:?g_Count@@3JA; long g_Count
0x180014154  test    rbx, rbx
0x180014157  jz      short loc_18001419D
0x180014159  mov     rax, [rbx]
0x18001415c  mov     r8, rdi
0x18001415f  mov     rdx, rbp
0x180014162  mov     rcx, rbx
0x180014165  mov     rax, [rax]
0x180014168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001416d  mov     edi, eax
0x18001416f  test    eax, eax
0x180014171  jns     short loc_18001418C
0x180014173  mov     r8d, 25h ; '%'; int
0x180014179  lea     rdx, aCscripteddiagf; "CScriptedDiagFactory::CreateInstance"
0x180014180  mov     r9d, eax; int
0x180014183  lea     ecx, [r8-24h]; Level
0x180014187  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001418c  mov     rax, [rbx]
0x18001418f  mov     rcx, rbx
0x180014192  mov     rax, [rax+10h]
0x180014196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001419b  jmp     short loc_1800141BB
0x18001419d  mov     edi, 8007000Eh
0x1800141a2  mov     r8d, 25h ; '%'; int
0x1800141a8  lea     rdx, aCscripteddiagf; "CScriptedDiagFactory::CreateInstance"
0x1800141af  mov     r9d, edi; int
0x1800141b2  lea     ecx, [r8-24h]; Level
0x1800141b6  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800141bb  mov     rbx, [rsp+28h+arg_0]
0x1800141c0  mov     eax, edi
0x1800141c2  mov     rbp, [rsp+28h+arg_8]
0x1800141c7  add     rsp, 20h
0x1800141cb  pop     rdi
0x1800141cc  retn
```
