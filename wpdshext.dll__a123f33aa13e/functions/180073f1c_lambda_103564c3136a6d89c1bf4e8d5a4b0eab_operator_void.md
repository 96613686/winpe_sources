# _lambda_103564c3136a6d89c1bf4e8d5a4b0eab_::operator()(void)

- ea: `0x180073f1c`
- end: `0x180073fa1`
- name: `??R_lambda_103564c3136a6d89c1bf4e8d5a4b0eab_@@QEBA@XZ`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b504`

## callees

- `0x18002bab0`
- `0x18002bee4`
- `0x180073f1c`

## import_xrefs

- `ole32!CoInitializeEx` at `0x180073f38`
- `ole32!CoInitializeEx` at `0x180073f38`
- `api-ms-win-shcore-thread-l1-1-0!SHSetThreadRef` at `0x180073f81`
- `api-ms-win-shcore-thread-l1-1-0!SHSetThreadRef` at `0x180073f81`

## string_xrefs

- `0x180073f4e`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_103564c3136a6d89c1bf4e8d5a4b0eab_::operator()(__int64 a1)
{
  HRESULT v2; // ebx
  __int64 v3; // rdx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = CoInitializeEx(0, *(_DWORD *)(*(_QWORD *)a1 + 72LL) != 0 ? 2 : 0);
  if ( v2 < 0 )
  {
    v3 = 947;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)v2,
      v5);
    return (unsigned int)v2;
  }
  v2 = SetTlsSlotData((LPVOID)(*(_QWORD *)a1 + 128LL));
  if ( v2 < 0 )
  {
    v3 = 948;
    goto LABEL_3;
  }
  v2 = SHSetThreadRef(*(IUnknown **)(*(_QWORD *)a1 + 120LL));
  if ( v2 < 0 )
  {
    v3 = 949;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180073f1c  mov     [rsp+arg_0], rbx
0x180073f21  push    rdi; int
0x180073f22  sub     rsp, 20h
0x180073f26  mov     rax, [rcx]
0x180073f29  mov     rdi, rcx
0x180073f2c  mov     edx, [rax+48h]
0x180073f2f  neg     edx
0x180073f31  sbb     edx, edx
0x180073f33  xor     ecx, ecx; pvReserved
0x180073f35  and     edx, 2; dwCoInit
0x180073f38  call    cs:__imp_CoInitializeEx
0x180073f3e  mov     ebx, eax
0x180073f40  test    eax, eax
0x180073f42  jns     short loc_180073F61
0x180073f44  mov     edx, 3B3h; void *
0x180073f49  mov     rcx, [rsp+28h]; this
0x180073f4e  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x180073f55  mov     r9d, ebx; char *
0x180073f58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073f5d  mov     eax, ebx
0x180073f5f  jmp     short loc_180073F96
0x180073f61  mov     rcx, [rdi]
0x180073f64  sub     rcx, 0FFFFFFFFFFFFFF80h; lpTlsValue
0x180073f68  call    SetTlsSlotData
0x180073f6d  mov     ebx, eax
0x180073f6f  test    eax, eax
0x180073f71  jns     short loc_180073F7A
0x180073f73  mov     edx, 3B4h
0x180073f78  jmp     short loc_180073F49
0x180073f7a  mov     rcx, [rdi]
0x180073f7d  mov     rcx, [rcx+78h]; punk
0x180073f81  call    cs:__imp_SHSetThreadRef
0x180073f87  mov     ebx, eax
0x180073f89  test    eax, eax
0x180073f8b  jns     short loc_180073F94
0x180073f8d  mov     edx, 3B5h
0x180073f92  jmp     short loc_180073F49
0x180073f94  xor     eax, eax
0x180073f96  mov     rbx, [rsp+28h+arg_0]
0x180073f9b  add     rsp, 20h
0x180073f9f  pop     rdi
0x180073fa0  retn
```
