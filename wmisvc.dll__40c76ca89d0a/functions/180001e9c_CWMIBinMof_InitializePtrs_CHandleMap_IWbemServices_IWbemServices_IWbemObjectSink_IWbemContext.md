# CWMIBinMof::InitializePtrs(CHandleMap *,IWbemServices *,IWbemServices *,IWbemObjectSink *,IWbemContext *)

- ea: `0x180001e9c`
- end: `0x180001f66`
- name: `?InitializePtrs@CWMIBinMof@@QEAAJPEAVCHandleMap@@PEAUIWbemServices@@1PEAUIWbemObjectSink@@PEAUIWbemContext@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(CWMIBinMof *__hidden this, struct CHandleMap *, struct IWbemServices *, struct IWbemServices *, struct IWbemObjectSink *, struct IWbemContext *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001e40`
- `0x180001f6c`

## callees

- `0x180001e9c`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180001f5b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180001f5b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180001ed9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180001ed9`

## pseudocode

```c
__int64 __fastcall CWMIBinMof::InitializePtrs(
        CWMIBinMof *this,
        struct CHandleMap *a2,
        struct IWbemServices *a3,
        struct IWbemServices *a4,
        struct IWbemObjectSink *a5,
        struct IWbemContext *a6)
{
  unsigned int v10; // edi
  void *v11; // rcx
  _QWORD *v12; // rax
  _QWORD *v13; // rcx

  v10 = -2147217407;
  v11 = (void *)*((_QWORD *)this + 3);
  if ( v11 )
    CWin32DefaultArena::WbemMemFree(v11);
  *((_QWORD *)this + 3) = 0;
  v12 = CWin32DefaultArena::WbemMemAlloc(0x28u);
  v13 = v12;
  if ( v12 )
  {
    *v12 = 0;
    v12[1] = 0;
    v12[2] = 0;
    v12[3] = 0;
    v12[4] = 0;
  }
  else
  {
    v13 = 0;
  }
  *((_QWORD *)this + 3) = v13;
  if ( v13 )
  {
    v13[4] = a2;
    v13[1] = a3;
    v13[2] = a4;
    *v13 = a5;
    v13[3] = a6;
    *((_DWORD *)this + 3) = 2;
    return 0;
  }
  return v10;
}

```

## disassembly

```asm
0x180001e9c  mov     [rsp+arg_8], rbx
0x180001ea1  mov     [rsp+arg_10], rbp
0x180001ea6  push    rsi
0x180001ea7  push    rdi
0x180001ea8  push    r14
0x180001eaa  sub     rsp, 20h
0x180001eae  mov     rsi, r9
0x180001eb1  mov     rbp, r8
0x180001eb4  mov     r14, rdx
0x180001eb7  mov     rbx, rcx
0x180001eba  mov     edi, 80041001h
0x180001ebf  mov     rcx, [rcx+18h]
0x180001ec3  test    rcx, rcx
0x180001ec6  jnz     loc_180001F5B
0x180001ecc  mov     qword ptr [rbx+18h], 0
0x180001ed4  mov     ecx, 28h ; '('
0x180001ed9  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180001edf  mov     rcx, rax
0x180001ee2  mov     [rsp+38h+arg_0], rax
0x180001ee7  test    rax, rax
0x180001eea  jz      short loc_180001F57
0x180001eec  mov     qword ptr [rax], 0
0x180001ef3  mov     qword ptr [rax+8], 0
0x180001efb  mov     qword ptr [rax+10h], 0
0x180001f03  mov     qword ptr [rax+18h], 0
0x180001f0b  mov     qword ptr [rax+20h], 0
0x180001f13  mov     [rbx+18h], rcx
0x180001f17  test    rcx, rcx
0x180001f1a  jz      short loc_180001F42
0x180001f1c  mov     [rcx+20h], r14
0x180001f20  mov     [rcx+8], rbp
0x180001f24  mov     [rcx+10h], rsi
0x180001f28  mov     rax, [rsp+38h+arg_20]
0x180001f2d  mov     [rcx], rax
0x180001f30  mov     rax, [rsp+38h+arg_28]
0x180001f35  mov     [rcx+18h], rax
0x180001f39  mov     dword ptr [rbx+0Ch], 2
0x180001f40  xor     edi, edi
0x180001f42  mov     eax, edi
0x180001f44  mov     rbx, [rsp+38h+arg_8]
0x180001f49  mov     rbp, [rsp+38h+arg_10]
0x180001f4e  add     rsp, 20h
0x180001f52  pop     r14
0x180001f54  pop     rdi
0x180001f55  pop     rsi
0x180001f56  retn
0x180001f57  xor     ecx, ecx
0x180001f59  jmp     short loc_180001F13
0x180001f5b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180001f61  jmp     loc_180001ECC
```
