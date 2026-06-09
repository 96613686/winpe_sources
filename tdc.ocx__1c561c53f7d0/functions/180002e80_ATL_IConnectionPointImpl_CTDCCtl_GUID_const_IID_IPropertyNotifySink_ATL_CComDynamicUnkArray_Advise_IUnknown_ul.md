# ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_IPropertyNotifySink,ATL::CComDynamicUnkArray>::Advise(IUnknown *,ulong *)

- ea: `0x180002e80`
- end: `0x180002f5c`
- name: `?Advise@?$IConnectionPointImpl@VCTDCCtl@@$1?IID_IPropertyNotifySink@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAUIUnknown@@PEAK@Z`
- size: `220`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002d38`
- `0x180002e80`
- `0x180014270`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_IPropertyNotifySink,ATL::CComDynamicUnkArray>::Advise(
        __int64 *a1,
        __int64 (__fastcall ***a2)(_QWORD, __int128 *, struct IUnknown **),
        _DWORD *a3)
{
  __int64 v6; // rax
  int v7; // ebx
  int v8; // eax
  struct IUnknown *v10; // [rsp+20h] [rbp-38h] BYREF
  __int128 v11; // [rsp+28h] [rbp-30h] BYREF

  v10 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a2 && a3 )
  {
    v6 = *a1;
    v11 = 0;
    (*(void (__fastcall **)(__int64 *, __int128 *))(v6 + 24))(a1, &v11);
    v7 = (**a2)(a2, &v11, &v10);
    if ( v7 < 0 )
    {
      if ( v7 == -2147467262 )
        v7 = -2147220990;
    }
    else
    {
      v8 = ATL::CComDynamicUnkArray::Add((ATL::CComDynamicUnkArray *)(a1 + 1), v10);
      *a3 = v8;
      if ( v8 )
        return 0;
      v7 = -2147220991;
      ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->Release)(v10);
    }
    *a3 = 0;
    return (unsigned int)v7;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180002e80  push    rbx
0x180002e82  push    rsi
0x180002e83  push    rdi
0x180002e84  sub     rsp, 40h
0x180002e88  mov     rax, cs:__security_cookie
0x180002e8f  xor     rax, rsp
0x180002e92  mov     [rsp+58h+var_20], rax
0x180002e97  mov     [rsp+58h+var_38], 0
0x180002ea0  mov     rdi, r8
0x180002ea3  mov     rbx, rdx
0x180002ea6  mov     rsi, rcx
0x180002ea9  test    r8, r8
0x180002eac  jz      short loc_180002EB5
0x180002eae  mov     dword ptr [r8], 0
0x180002eb5  test    rbx, rbx
0x180002eb8  jz      loc_180002F42
0x180002ebe  test    rdi, rdi
0x180002ec1  jz      short loc_180002F42
0x180002ec3  mov     rax, [rcx]
0x180002ec6  lea     rdx, [rsp+58h+var_30]
0x180002ecb  xorps   xmm0, xmm0
0x180002ece  movups  [rsp+58h+var_30], xmm0
0x180002ed3  mov     rax, [rax+18h]
0x180002ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002edc  mov     rax, [rbx]
0x180002edf  lea     r8, [rsp+58h+var_38]
0x180002ee4  lea     rdx, [rsp+58h+var_30]
0x180002ee9  mov     rcx, rbx
0x180002eec  mov     rax, [rax]
0x180002eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef4  mov     ebx, eax
0x180002ef6  test    eax, eax
0x180002ef8  js      short loc_180002F2A
0x180002efa  mov     rdx, [rsp+58h+var_38]; struct IUnknown *
0x180002eff  lea     rcx, [rsi+8]; this
0x180002f03  call    ?Add@CComDynamicUnkArray@ATL@@QEAAKPEAUIUnknown@@@Z; ATL::CComDynamicUnkArray::Add(IUnknown *)
0x180002f08  mov     [rdi], eax
0x180002f0a  test    eax, eax
0x180002f0c  jz      short loc_180002F12
0x180002f0e  xor     ebx, ebx
0x180002f10  jmp     short loc_180002F3E
0x180002f12  mov     rcx, [rsp+58h+var_38]
0x180002f17  mov     ebx, 80040201h
0x180002f1c  mov     rax, [rcx]
0x180002f1f  mov     rax, [rax+10h]
0x180002f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f28  jmp     short loc_180002F38
0x180002f2a  cmp     ebx, 80004002h
0x180002f30  mov     eax, 80040202h
0x180002f35  cmovz   ebx, eax
0x180002f38  mov     dword ptr [rdi], 0
0x180002f3e  mov     eax, ebx
0x180002f40  jmp     short loc_180002F47
0x180002f42  mov     eax, 80004003h
0x180002f47  mov     rcx, [rsp+58h+var_20]
0x180002f4c  xor     rcx, rsp; StackCookie
0x180002f4f  call    __security_check_cookie
0x180002f54  add     rsp, 40h
0x180002f58  pop     rdi
0x180002f59  pop     rsi
0x180002f5a  pop     rbx
0x180002f5b  retn
```
