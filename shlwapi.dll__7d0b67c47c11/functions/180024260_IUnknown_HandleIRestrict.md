# IUnknown_HandleIRestrict

- ea: `0x180024260`
- end: `0x180024305`
- name: `IUnknown_HandleIRestrict`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012550`
- `0x180024260`
- `0x180037010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800242ad`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800242ad`

## pseudocode

```c
__int64 __fastcall IUnknown_HandleIRestrict(IUnknown *a1, __int64 a2, unsigned int a3, __int64 a4, _DWORD *a5)
{
  HRESULT v8; // ebx
  void *ppvOut; // [rsp+30h] [rbp-38h] BYREF

  ppvOut = 0;
  *a5 = 3;
  v8 = IUnknown_QueryService(
         a1,
         &GUID_d12f26b2_d90a_11d0_830d_00aa005b4383,
         &GUID_d12f26b1_d90a_11d0_830d_00aa005b4383,
         &ppvOut);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, __int64, _DWORD *))(*(_QWORD *)ppvOut + 24LL))(
           ppvOut,
           a2,
           a3,
           a4,
           a5);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180024260  push    rbx
0x180024262  push    rbp
0x180024263  push    rsi
0x180024264  push    rdi
0x180024265  push    r14
0x180024267  sub     rsp, 40h
0x18002426b  mov     rax, cs:__security_cookie
0x180024272  xor     rax, rsp
0x180024275  mov     [rsp+68h+var_30], rax
0x18002427a  mov     rdi, [rsp+68h+arg_20]
0x180024282  mov     r14, r9
0x180024285  mov     ebp, r8d
0x180024288  mov     [rsp+68h+ppvOut], 0
0x180024291  mov     rsi, rdx
0x180024294  lea     r9, [rsp+68h+ppvOut]; ppvOut
0x180024299  lea     r8, _GUID_d12f26b1_d90a_11d0_830d_00aa005b4383; riid
0x1800242a0  lea     rdx, _GUID_d12f26b2_d90a_11d0_830d_00aa005b4383; guidService
0x1800242a7  mov     dword ptr [rdi], 3
0x1800242ad  call    cs:__imp_IUnknown_QueryService
0x1800242b3  mov     ebx, eax
0x1800242b5  test    eax, eax
0x1800242b7  js      short loc_1800242EB
0x1800242b9  mov     rcx, [rsp+68h+ppvOut]
0x1800242be  mov     r9, r14
0x1800242c1  mov     r8d, ebp
0x1800242c4  mov     [rsp+68h+var_48], rdi
0x1800242c9  mov     rdx, rsi
0x1800242cc  mov     rax, [rcx]
0x1800242cf  mov     rax, [rax+18h]
0x1800242d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242d8  mov     rcx, [rsp+68h+ppvOut]
0x1800242dd  mov     ebx, eax
0x1800242df  mov     rax, [rcx]
0x1800242e2  mov     rax, [rax+10h]
0x1800242e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242eb  mov     eax, ebx
0x1800242ed  mov     rcx, [rsp+68h+var_30]
0x1800242f2  xor     rcx, rsp; StackCookie
0x1800242f5  call    __security_check_cookie
0x1800242fa  add     rsp, 40h
0x1800242fe  pop     r14
0x180024300  pop     rdi
0x180024301  pop     rsi
0x180024302  pop     rbp
0x180024303  pop     rbx
0x180024304  retn
```
