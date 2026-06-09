# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(IUnknown *,ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger> * *)

- ea: `0x18000afd0`
- end: `0x18000b143`
- name: `?CreateInstance@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@SAJPEAUIUnknown@@PEAPEAV12@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ac30`

## callees

- `0x180001374`
- `0x18000afd0`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(
        char *a1,
        _QWORD *a2)
{
  _QWORD *v2; // rsi
  unsigned int v5; // r14d
  char *v6; // rax
  char *v7; // rbx
  char *v8; // rcx
  int v9; // ecx
  char *v11; // [rsp+78h] [rbp+20h]

  v2 = a2;
  if ( !a2 )
    return 2147500035LL;
  try
  {
    *a2 = 0;
    v5 = -2147024882;
    v6 = (char *)operator new(0xC0u);
    v7 = v6;
    if ( v6 )
    {
      *((_DWORD *)v6 + 2) = 0;
      *(_QWORD *)v6 = &ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable';
      v8 = v6;
      if ( a1 )
        v8 = a1;
      *((_DWORD *)v6 + 8) = 0;
      *((_QWORD *)v6 + 5) = 0;
      *((_QWORD *)v6 + 6) = 0;
      *((_QWORD *)v6 + 7) = 0;
      *((_QWORD *)v6 + 8) = 0;
      *((_QWORD *)v6 + 9) = 0;
      *((_QWORD *)v6 + 10) = 0;
      *((_QWORD *)v6 + 11) = 0;
      *((_DWORD *)v6 + 24) = 0;
      *((_DWORD *)v6 + 26) = 0;
      *((_DWORD *)v6 + 27) = 2;
      *((_DWORD *)v6 + 28) = 50;
      *(_QWORD *)(v6 + 116) = 10;
      *((_WORD *)v6 + 62) = 256;
      *((_DWORD *)v6 + 32) = 0;
      *((_DWORD *)v6 + 33) = 7;
      *((_DWORD *)v6 + 34) = -1;
      *((_QWORD *)v6 + 18) = 0;
      *((_QWORD *)v6 + 19) = 0;
      v6[160] = 0;
      *((_DWORD *)v6 + 41) = 0;
      *((_DWORD *)v6 + 42) = -1;
      *((_QWORD *)v6 + 22) = 0;
      *((_QWORD *)v6 + 23) = 0;
      *((_QWORD *)v6 + 2) = &ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable';
      *((_QWORD *)v6 + 3) = v8;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v7 = 0;
    }
    v11 = v7;
  }
  catch ( ... )
  {
    v2 = a2;
    v5 = -2147024882;
    v7 = v11;
  }
  if ( v7 )
  {
    v9 = *((_DWORD *)v7 + 2);
    if ( v9 != 0x7FFFFFFF )
    {
      *((_DWORD *)v7 + 2) = v9 + 1;
      if ( v9 != 2147483646 )
        *((_DWORD *)v7 + 2) = v9;
    }
    v5 = 0;
  }
  *v2 = v7;
  return v5;
}

```

## disassembly

```asm
0x18000afd0  mov     [rsp+arg_8], rdx
0x18000afd5  push    rbx
0x18000afd6  push    rsi
0x18000afd7  push    rdi
0x18000afd8  push    r14
0x18000afda  push    r15
0x18000afdc  sub     rsp, 30h
0x18000afe0  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18000afe9  mov     rsi, rdx
0x18000afec  mov     r15, rcx
0x18000afef  xor     edi, edi
0x18000aff1  test    rdx, rdx
0x18000aff4  jnz     short loc_18000B000
0x18000aff6  mov     eax, 80004003h
0x18000affb  jmp     loc_18000B136
0x18000b000  mov     [rdx], rdi
0x18000b003  mov     r14d, 8007000Eh
0x18000b009  mov     [rsp+58h+arg_10], r14d
0x18000b00e  mov     [rsp+58h+arg_18], rdi
0x18000b013  mov     ecx, 0C0h; Size
0x18000b018  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b01d  mov     rbx, rax
0x18000b020  test    rax, rax
0x18000b023  jz      loc_18000B0F1
0x18000b029  mov     [rax+8], edi
0x18000b02c  lea     rax, ??_7?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x18000b033  mov     [rbx], rax
0x18000b036  mov     rcx, rbx
0x18000b039  test    r15, r15
0x18000b03c  cmovnz  rcx, r15
0x18000b040  mov     [rbx+20h], edi
0x18000b043  mov     [rbx+28h], rdi
0x18000b047  mov     [rbx+30h], rdi
0x18000b04b  mov     [rbx+38h], rdi
0x18000b04f  mov     [rbx+40h], rdi
0x18000b053  xor     eax, eax
0x18000b055  mov     [rbx+48h], rax
0x18000b059  mov     [rbx+50h], rdi
0x18000b05d  mov     [rbx+58h], rdi
0x18000b061  mov     [rbx+60h], edi
0x18000b064  mov     [rbx+68h], edi
0x18000b067  mov     dword ptr [rbx+6Ch], 2
0x18000b06e  mov     dword ptr [rbx+70h], 32h ; '2'
0x18000b075  mov     qword ptr [rbx+74h], 0Ah
0x18000b07d  mov     word ptr [rbx+7Ch], 100h
0x18000b083  mov     [rbx+80h], edi
0x18000b089  mov     dword ptr [rbx+84h], 7
0x18000b093  or      eax, 0FFFFFFFFh
0x18000b096  mov     [rbx+88h], eax
0x18000b09c  mov     [rbx+90h], rdi
0x18000b0a3  mov     [rbx+98h], rdi
0x18000b0aa  mov     [rbx+0A0h], dil
0x18000b0b1  mov     [rbx+0A4h], edi
0x18000b0b7  mov     [rbx+0A8h], eax
0x18000b0bd  xor     eax, eax
0x18000b0bf  mov     [rbx+0B0h], rax
0x18000b0c6  mov     [rbx+0B8h], rdi
0x18000b0cd  lea     rax, ??_7?$CComContainedObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComContainedObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x18000b0d4  mov     [rbx+10h], rax
0x18000b0d8  mov     [rbx+18h], rcx
0x18000b0dc  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b0e3  mov     rax, [rcx]
0x18000b0e6  mov     rax, [rax+8]
0x18000b0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0ef  jmp     short loc_18000B0F4
0x18000b0f1  mov     rbx, rdi
0x18000b0f4  mov     [rsp+58h+arg_18], rbx
0x18000b0f9  jmp     short loc_18000B10C
0x18000b0fb  xor     edi, edi
0x18000b0fd  mov     rsi, [rsp+58h+arg_8]
0x18000b102  mov     r14d, [rsp+58h+arg_10]
0x18000b107  mov     rbx, [rsp+58h+arg_18]
0x18000b10c  test    rbx, rbx
0x18000b10f  jz      short loc_18000B130
0x18000b111  mov     ecx, [rbx+8]
0x18000b114  cmp     ecx, 7FFFFFFFh
0x18000b11a  jz      short loc_18000B12D
0x18000b11c  lea     eax, [rcx+1]
0x18000b11f  mov     [rbx+8], eax
0x18000b122  cmp     ecx, 7FFFFFFEh
0x18000b128  jz      short loc_18000B12D
0x18000b12a  mov     [rbx+8], ecx
0x18000b12d  mov     r14d, edi
0x18000b130  mov     [rsi], rbx
0x18000b133  mov     eax, r14d
0x18000b136  add     rsp, 30h
0x18000b13a  pop     r15
0x18000b13c  pop     r14
0x18000b13e  pop     rdi
0x18000b13f  pop     rsi
0x18000b140  pop     rbx
0x18000b141  retn
```
