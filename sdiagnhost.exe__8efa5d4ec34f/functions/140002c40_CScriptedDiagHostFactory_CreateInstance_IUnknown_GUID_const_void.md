# CScriptedDiagHostFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140002c40`
- end: `0x140002d22`
- name: `?CreateInstance@CScriptedDiagHostFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `226`
- prototype: `__int64 __fastcall(CScriptedDiagHostFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001174`
- `0x140002c40`
- `0x140005964`
- `0x140008010`

## string_xrefs

- `0x140002cd3`: `CScriptedDiagHostFactory::CreateInstance`
- `0x140002cfe`: `CScriptedDiagHostFactory::CreateInstance`

## pseudocode

```c
__int64 __fastcall CScriptedDiagHostFactory::CreateInstance(
        CScriptedDiagHostFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // edi
  _DWORD *v7; // rbx
  int v8; // eax
  unsigned int v9; // ecx

  if ( !a4 )
  {
    v6 = -2147024809;
LABEL_10:
    SdpDebugTrace((unsigned int)this, L"CScriptedDiagHostFactory::CreateInstance", 36, v6);
    return v6;
  }
  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    goto LABEL_10;
  }
  v7 = operator new(0x18u);
  if ( !v7 )
  {
    v6 = -2147024882;
    goto LABEL_10;
  }
  v7[2] = 1;
  *(_QWORD *)v7 = &CScriptedDiagNativeHost::`vftable';
  *((_QWORD *)v7 + 2) = 0;
  _InterlockedIncrement(&g_Count);
  v8 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v7)(v7, a3, a4);
  v6 = v8;
  if ( v8 < 0 )
    SdpDebugTrace(v9, L"CScriptedDiagHostFactory::CreateInstance", 36, v8);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  return v6;
}

```

## disassembly

```asm
0x140002c40  mov     [rsp+arg_0], rbx
0x140002c45  mov     [rsp+arg_8], rsi
0x140002c4a  push    rdi
0x140002c4b  sub     rsp, 20h
0x140002c4f  mov     rdi, r9
0x140002c52  mov     rsi, r8
0x140002c55  test    r9, r9
0x140002c58  jnz     short loc_140002C64
0x140002c5a  mov     edi, 80070057h
0x140002c5f  jmp     loc_140002CFB
0x140002c64  mov     qword ptr [r9], 0
0x140002c6b  test    rdx, rdx
0x140002c6e  jz      short loc_140002C7A
0x140002c70  mov     edi, 80040110h
0x140002c75  jmp     loc_140002CFB
0x140002c7a  mov     ecx, 18h; Size
0x140002c7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002c84  mov     [rsp+28h+arg_18], rax
0x140002c89  mov     rbx, rax
0x140002c8c  test    rax, rax
0x140002c8f  jz      short loc_140002CF6
0x140002c91  lea     rax, ??_7CScriptedDiagNativeHost@@6B@; const CScriptedDiagNativeHost::`vftable'
0x140002c98  mov     dword ptr [rbx+8], 1
0x140002c9f  mov     [rbx], rax
0x140002ca2  mov     qword ptr [rbx+10h], 0
0x140002caa  lock inc cs:?g_Count@@3JA; long g_Count
0x140002cb1  test    rbx, rbx
0x140002cb4  jz      short loc_140002CF6
0x140002cb6  mov     rax, [rbx]
0x140002cb9  mov     r8, rdi
0x140002cbc  mov     rdx, rsi
0x140002cbf  mov     rcx, rbx
0x140002cc2  mov     rax, [rax]
0x140002cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cca  mov     edi, eax
0x140002ccc  test    eax, eax
0x140002cce  jns     short loc_140002CE5
0x140002cd0  mov     r9d, eax; int
0x140002cd3  lea     rdx, aCscripteddiagh_0; "CScriptedDiagHostFactory::CreateInstanc"...
0x140002cda  mov     r8d, 24h ; '$'; int
0x140002ce0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x140002ce5  mov     rax, [rbx]
0x140002ce8  mov     rcx, rbx
0x140002ceb  mov     rax, [rax+10h]
0x140002cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cf4  jmp     short loc_140002D10
0x140002cf6  mov     edi, 8007000Eh
0x140002cfb  mov     r9d, edi; int
0x140002cfe  lea     rdx, aCscripteddiagh_0; "CScriptedDiagHostFactory::CreateInstanc"...
0x140002d05  mov     r8d, 24h ; '$'; int
0x140002d0b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x140002d10  mov     rbx, [rsp+28h+arg_0]
0x140002d15  mov     eax, edi
0x140002d17  mov     rsi, [rsp+28h+arg_8]
0x140002d1c  add     rsp, 20h
0x140002d20  pop     rdi
0x140002d21  retn
```
