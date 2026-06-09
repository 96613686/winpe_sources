# Microsoft::WRL::SimpleClassFactory<CCreateObjectLocalServer,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140004210`
- end: `0x1400042a4`
- name: `?CreateInstance@?$SimpleClassFactory@VCCreateObjectLocalServer@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `148`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002b28`
- `0x140004210`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x14000423a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x14000423a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<CCreateObjectLocalServer,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  int v7; // eax
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD *); // rcx
  unsigned int v9; // eax
  __int64 (__fastcall ***v11)(_QWORD, __int64, _QWORD *); // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
  }
  else
  {
    v11 = 0;
    v7 = Microsoft::WRL::Details::MakeAndInitialize<CCreateObjectLocalServer,IUnknown,>(&v11);
    v8 = v11;
    v6 = v7;
    if ( v7 >= 0 )
    {
      v9 = (**v11)(v11, a3, a4);
      v8 = v11;
      v6 = v9;
    }
    if ( v8 )
    {
      v11 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v8)[2])(v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140004210  mov     [rsp+arg_0], rbx
0x140004215  mov     [rsp+arg_10], rsi
0x14000421a  push    rdi
0x14000421b  sub     rsp, 20h
0x14000421f  mov     qword ptr [r9], 0
0x140004226  mov     rdi, r9
0x140004229  mov     rsi, r8
0x14000422c  test    rdx, rdx
0x14000422f  jz      short loc_140004242
0x140004231  mov     ebx, 80040110h
0x140004236  xor     edx, edx
0x140004238  mov     ecx, ebx
0x14000423a  call    cs:__imp_RoOriginateError
0x140004240  jmp     short loc_140004292
0x140004242  lea     rcx, [rsp+28h+arg_8]
0x140004247  mov     [rsp+28h+arg_8], 0
0x140004250  call    ??$MakeAndInitialize@VCCreateObjectLocalServer@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CCreateObjectLocalServer,IUnknown,>(IUnknown * *)
0x140004255  mov     rcx, [rsp+28h+arg_8]
0x14000425a  mov     ebx, eax
0x14000425c  test    eax, eax
0x14000425e  js      short loc_140004278
0x140004260  mov     rax, [rcx]
0x140004263  mov     r8, rdi
0x140004266  mov     rdx, rsi
0x140004269  mov     rax, [rax]
0x14000426c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004271  mov     rcx, [rsp+28h+arg_8]
0x140004276  mov     ebx, eax
0x140004278  test    rcx, rcx
0x14000427b  jz      short loc_140004292
0x14000427d  mov     [rsp+28h+arg_8], 0
0x140004286  mov     rdx, [rcx]
0x140004289  mov     rax, [rdx+10h]
0x14000428d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004292  mov     rsi, [rsp+28h+arg_10]
0x140004297  mov     eax, ebx
0x140004299  mov     rbx, [rsp+28h+arg_0]
0x14000429e  add     rsp, 20h
0x1400042a2  pop     rdi
0x1400042a3  retn
```
