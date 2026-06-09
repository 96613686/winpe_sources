# _lambda_e087c5742fecdb49d630a755e1ac6f19_::_lambda_invoker_cdecl_(tagComCallData *)

- ea: `0x180006a90`
- end: `0x180006acd`
- name: `?_lambda_invoker_cdecl_@_lambda_e087c5742fecdb49d630a755e1ac6f19_@@CA@PEAUtagComCallData@@@Z`
- size: `61`
- prototype: `__int64 __fastcall(struct tagComCallData *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006a90`
- `0x180006c98`
- `0x180009044`

## string_xrefs

- `0x180006aad`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`

## pseudocode

```c
__int64 __fastcall _lambda_e087c5742fecdb49d630a755e1ac6f19_::_lambda_invoker_cdecl_(
        struct tagComCallData *a1,
        __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = Microsoft::WRL::Details::RegisterObjects<2>(*(_QWORD *)a1->pUserDefined, a2);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
      (const char *)(unsigned int)v2,
      v5);
  return v3;
}

```

## disassembly

```asm
0x180006a90  push    rbx; int
0x180006a92  sub     rsp, 20h
0x180006a96  mov     rcx, [rcx+8]
0x180006a9a  mov     rcx, [rcx]
0x180006a9d  call    ??$RegisterObjects@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBG@Z; Microsoft::WRL::Details::RegisterObjects<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x180006aa2  mov     ebx, eax
0x180006aa4  test    eax, eax
0x180006aa6  jns     short loc_180006AC3
0x180006aa8  mov     rcx, [rsp+28h]; this
0x180006aad  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x180006ab4  mov     r9d, eax; char *
0x180006ab7  mov     edx, 4Fh ; 'O'; void *
0x180006abc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ac1  jmp     short loc_180006AC5
0x180006ac3  xor     ebx, ebx
0x180006ac5  mov     eax, ebx
0x180006ac7  add     rsp, 20h
0x180006acb  pop     rbx
0x180006acc  retn
```
