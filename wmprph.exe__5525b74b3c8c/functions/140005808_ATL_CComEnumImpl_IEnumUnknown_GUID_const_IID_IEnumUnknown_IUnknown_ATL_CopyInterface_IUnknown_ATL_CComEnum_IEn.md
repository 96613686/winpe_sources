# ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::Init(IUnknown * *,IUnknown * *,IUnknown *,ATL::CComEnumFlags)

- ea: `0x140005808`
- end: `0x1400058fc`
- name: `?Init@?$CComEnumImpl@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@V?$CComEnum@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@QEAAJPEAPEAUIUnknown@@0PEAU3@W4CComEnumFlags@2@@Z`
- size: `244`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000310c`
- `0x140004360`

## callees

- `0x140001054`
- `0x140005808`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::Init(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  __int64 **v5; // rsi
  __int64 v7; // rbp
  __int64 *v8; // rdi
  __int64 v10; // r15
  __int64 *v11; // rax
  __int64 result; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rdi

  v5 = (__int64 **)(a1 + 32);
  v7 = a3;
  v8 = a2;
  if ( a5 == 3 )
  {
    v10 = (a3 - (__int64)a2) >> 3;
    v11 = (__int64 *)operator new[](saturated_mul((unsigned int)v10, 8u));
    *(_QWORD *)(a1 + 16) = v11;
    *v5 = v11;
    if ( !v11 )
      return 2147942414LL;
    while ( v8 != (__int64 *)v7 )
    {
      v13 = *v8;
      *v11 = *v8;
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
      v11 = *v5 + 1;
      *v5 = v11;
      ++v8;
    }
    v7 = *(_QWORD *)(a1 + 16) + 8 * v10;
  }
  else
  {
    *(_QWORD *)(a1 + 16) = a2;
  }
  v14 = (_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 24) = v7;
  if ( a1 != -8 )
  {
    if ( a4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4);
    if ( *v14 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 16LL))(*v14);
    *v14 = a4;
  }
  *v5 = *(__int64 **)(a1 + 16);
  result = 0;
  *(_DWORD *)(a1 + 40) = a5;
  return result;
}

```

## disassembly

```asm
0x140005808  push    rbx
0x14000580a  push    rbp
0x14000580b  push    rsi
0x14000580c  push    rdi
0x14000580d  push    r12
0x14000580f  push    r14
0x140005811  push    r15
0x140005813  sub     rsp, 20h
0x140005817  mov     r12d, [rsp+58h+arg_20]
0x14000581f  lea     rsi, [rcx+20h]
0x140005823  mov     r14, r9
0x140005826  mov     rbp, r8
0x140005829  mov     rdi, rdx
0x14000582c  mov     rbx, rcx
0x14000582f  cmp     r12d, 3
0x140005833  jnz     short loc_1400058A4
0x140005835  mov     r15, r8
0x140005838  lea     eax, [r12+5]
0x14000583d  sub     r15, rdx
0x140005840  sar     r15, 3
0x140005844  mov     ecx, r15d
0x140005847  mul     rcx
0x14000584a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140005851  cmovb   rax, rcx
0x140005855  mov     rcx, rax; unsigned __int64
0x140005858  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000585d  mov     [rbx+10h], rax
0x140005861  mov     [rsi], rax
0x140005864  test    rax, rax
0x140005867  jnz     short loc_140005895
0x140005869  mov     eax, 8007000Eh
0x14000586e  jmp     short loc_1400058ED
0x140005870  mov     rcx, [rdi]
0x140005873  mov     [rax], rcx
0x140005876  test    rcx, rcx
0x140005879  jz      short loc_140005887
0x14000587b  mov     rax, [rcx]
0x14000587e  mov     rax, [rax+8]
0x140005882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005887  mov     rax, [rsi]
0x14000588a  add     rax, 8
0x14000588e  mov     [rsi], rax
0x140005891  add     rdi, 8
0x140005895  cmp     rdi, rbp
0x140005898  jnz     short loc_140005870
0x14000589a  mov     rax, [rbx+10h]
0x14000589e  lea     rbp, [rax+r15*8]
0x1400058a2  jmp     short loc_1400058A8
0x1400058a4  mov     [rcx+10h], rdi
0x1400058a8  lea     rdi, [rbx+8]
0x1400058ac  mov     [rbx+18h], rbp
0x1400058b0  test    rdi, rdi
0x1400058b3  jz      short loc_1400058E0
0x1400058b5  test    r14, r14
0x1400058b8  jz      short loc_1400058C9
0x1400058ba  mov     rax, [r14]
0x1400058bd  mov     rcx, r14
0x1400058c0  mov     rax, [rax+8]
0x1400058c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058c9  mov     rcx, [rdi]
0x1400058cc  test    rcx, rcx
0x1400058cf  jz      short loc_1400058DD
0x1400058d1  mov     rax, [rcx]
0x1400058d4  mov     rax, [rax+10h]
0x1400058d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058dd  mov     [rdi], r14
0x1400058e0  mov     rax, [rbx+10h]
0x1400058e4  mov     [rsi], rax
0x1400058e7  xor     eax, eax
0x1400058e9  mov     [rbx+28h], r12d
0x1400058ed  add     rsp, 20h
0x1400058f1  pop     r15
0x1400058f3  pop     r14
0x1400058f5  pop     r12
0x1400058f7  pop     rdi
0x1400058f8  pop     rsi
0x1400058f9  pop     rbp
0x1400058fa  pop     rbx
0x1400058fb  retn
```
