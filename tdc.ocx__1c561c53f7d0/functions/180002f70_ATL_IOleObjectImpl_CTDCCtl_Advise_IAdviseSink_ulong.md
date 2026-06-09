# ATL::IOleObjectImpl<CTDCCtl>::Advise(IAdviseSink *,ulong *)

- ea: `0x180002f70`
- end: `0x180002fd0`
- name: `?Advise@?$IOleObjectImpl@VCTDCCtl@@@ATL@@UEAAJPEAUIAdviseSink@@PEAK@Z`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002f70`
- `0x180015010`

## import_xrefs

- `ole32!CreateOleAdviseHolder` at `0x180002fa1`
- `ole32!CreateOleAdviseHolder` at `0x180002fa1`

## pseudocode

```c
HRESULT __fastcall ATL::IOleObjectImpl<CTDCCtl>::Advise(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  HRESULT result; // eax

  v3 = a1 - 176;
  if ( !a1 )
    v3 = 24;
  if ( *(_QWORD *)v3 )
    return (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)v3 + 24LL))(*(_QWORD *)v3, a2, a3);
  result = CreateOleAdviseHolder((LPOLEADVISEHOLDER *)v3);
  if ( result >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)v3 + 24LL))(*(_QWORD *)v3, a2, a3);
  return result;
}

```

## disassembly

```asm
0x180002f70  mov     [rsp+arg_0], rbx
0x180002f75  mov     [rsp+arg_8], rsi
0x180002f7a  push    rdi
0x180002f7b  sub     rsp, 20h
0x180002f7f  test    rcx, rcx
0x180002f82  lea     rbx, [rcx-0B0h]
0x180002f89  mov     eax, 18h
0x180002f8e  mov     rdi, r8
0x180002f91  cmovz   rbx, rax
0x180002f95  mov     rsi, rdx
0x180002f98  cmp     qword ptr [rbx], 0
0x180002f9c  jnz     short loc_180002FAB
0x180002f9e  mov     rcx, rbx; ppOAHolder
0x180002fa1  call    cs:__imp_CreateOleAdviseHolder
0x180002fa7  test    eax, eax
0x180002fa9  js      short loc_180002FC0
0x180002fab  mov     rcx, [rbx]
0x180002fae  mov     r8, rdi
0x180002fb1  mov     rdx, rsi
0x180002fb4  mov     rax, [rcx]
0x180002fb7  mov     rax, [rax+18h]
0x180002fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fc0  mov     rbx, [rsp+28h+arg_0]
0x180002fc5  mov     rsi, [rsp+28h+arg_8]
0x180002fca  add     rsp, 20h
0x180002fce  pop     rdi
0x180002fcf  retn
```
