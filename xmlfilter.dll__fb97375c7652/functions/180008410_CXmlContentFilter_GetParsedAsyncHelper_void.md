# CXmlContentFilter::GetParsedAsyncHelper(void *)

- ea: `0x180008410`
- end: `0x180008489`
- name: `?GetParsedAsyncHelper@CXmlContentFilter@@SAKPEAX@Z`
- size: `121`
- prototype: `__int64 __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180008410`
- `0x18000d250`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000845a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008467`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000845a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008467`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CXmlContentFilter::GetParsedAsyncHelper(LPVOID lpThreadParameter)
{
  int v2; // eax
  void *v3; // rdx
  unsigned int v4; // r8d
  int v5; // edi
  void *v6; // rcx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (***((__int64 (__fastcall ****)(_QWORD, _QWORD))lpThreadParameter + 66))(
         *((_QWORD *)lpThreadParameter + 66),
         *((_QWORD *)lpThreadParameter + 10));
  v5 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(retaddr, v3, v4, (const char *)(unsigned int)v2, v8);
    v6 = (void *)*((_QWORD *)lpThreadParameter + 63);
    *((_DWORD *)lpThreadParameter + 128) = v5;
    *((_BYTE *)lpThreadParameter + 128) = 1;
    SetEvent(v6);
    SetEvent(*((HANDLE *)lpThreadParameter + 62));
  }
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)lpThreadParameter + 16LL))(lpThreadParameter);
  return 0;
}

```

## disassembly

```asm
0x180008410  mov     [rsp+arg_0], rbx
0x180008415  push    rdi; int
0x180008416  sub     rsp, 20h
0x18000841a  mov     rbx, rcx
0x18000841d  mov     rcx, [rcx+210h]
0x180008424  mov     rax, [rcx]
0x180008427  mov     rdx, [rbx+50h]
0x18000842b  mov     rax, [rax]
0x18000842e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008433  mov     edi, eax
0x180008435  test    eax, eax
0x180008437  jns     short loc_18000846D
0x180008439  mov     rcx, [rsp+28h]; this
0x18000843e  mov     r9d, eax; char *
0x180008441  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008446  mov     rcx, [rbx+1F8h]; hEvent
0x18000844d  mov     [rbx+200h], edi
0x180008453  mov     byte ptr [rbx+80h], 1
0x18000845a  call    cs:__imp_SetEvent
0x180008460  mov     rcx, [rbx+1F0h]; hEvent
0x180008467  call    cs:__imp_SetEvent
0x18000846d  mov     rax, [rbx]
0x180008470  mov     rcx, rbx
0x180008473  mov     rax, [rax+10h]
0x180008477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000847c  mov     rbx, [rsp+28h+arg_0]
0x180008481  xor     eax, eax
0x180008483  add     rsp, 20h
0x180008487  pop     rdi
0x180008488  retn
```
