# CTDCArr::StartDataLoad(uchar,ushort *,ushort *,ulong,ATL::CComObject<CMyBindStatusCallback<CTDCCtl>> *,uchar,uchar)

- ea: `0x18000d0c0`
- end: `0x18000d1c4`
- name: `?StartDataLoad@CTDCArr@@UEAAJEPEAG0KPEAV?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@EE@Z`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000d0c0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CTDCArr::StartDataLoad(
        __int64 a1,
        char a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        char a7,
        char a8)
{
  char v8; // si
  __int64 v9; // r11
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // r8
  bool v15; // al
  __int64 v16; // rcx
  int v17; // eax

  v8 = a7;
  v9 = a4;
  if ( a7 )
  {
    v8 = *(_DWORD *)(a1 + 36) != 0 ? a7 : 0;
    if ( v8 )
    {
      if ( *(_DWORD *)(a1 + 36) == 3 && *(int *)(a1 + 104) >= 0 )
      {
        v12 = 2;
        goto LABEL_11;
      }
      return (unsigned int)-2147467259;
    }
  }
  if ( *(_DWORD *)(a1 + 36) || *(_DWORD *)(a1 + 104) != -1 || *(_DWORD *)(a1 + 108) != -1 || *(_DWORD *)(a1 + 112) )
    return (unsigned int)-2147467259;
  *(_BYTE *)(a1 + 48) = 1;
  v12 = 1;
LABEL_11:
  LOBYTE(a4) = a8;
  *(_DWORD *)(a1 + 36) = v12;
  v13 = 0;
  (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a3, v9, a4);
  *(_BYTE *)(a1 + 92) = a2;
  v15 = v8 && a2;
  v16 = *(_QWORD *)(a1 + 16);
  *(_BYTE *)(a1 + 93) = v15;
  v17 = *(_DWORD *)(a1 + 104) + 1;
  *(_DWORD *)(a1 + 100) = 1;
  *(_DWORD *)(a1 + 96) = v17;
  *(_DWORD *)(a1 + 44) = a5;
  if ( v16 )
  {
    LOBYTE(v14) = v8;
    return (*(unsigned int (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v16 + 112LL))(v16, a6, v14);
  }
  return v13;
}

```

## disassembly

```asm
0x18000d0c0  push    rbx
0x18000d0c2  push    rbp
0x18000d0c3  push    rsi
0x18000d0c4  push    rdi
0x18000d0c5  push    r14
0x18000d0c7  sub     rsp, 30h
0x18000d0cb  mov     sil, [rsp+58h+arg_30]
0x18000d0d3  mov     r11, r9
0x18000d0d6  mov     r14, r8
0x18000d0d9  mov     bpl, dl
0x18000d0dc  mov     rbx, rcx
0x18000d0df  test    sil, sil
0x18000d0e2  jz      short loc_18000D10F
0x18000d0e4  mov     eax, [rcx+24h]
0x18000d0e7  neg     eax
0x18000d0e9  sbb     r10b, r10b
0x18000d0ec  and     sil, r10b
0x18000d0ef  test    sil, sil
0x18000d0f2  jz      short loc_18000D10F
0x18000d0f4  cmp     dword ptr [rcx+24h], 3
0x18000d0f8  jnz     loc_18000D1B2
0x18000d0fe  cmp     dword ptr [rcx+68h], 0
0x18000d102  jl      loc_18000D1B2
0x18000d108  mov     eax, 2
0x18000d10d  jmp     short loc_18000D13C
0x18000d10f  cmp     dword ptr [rcx+24h], 0
0x18000d113  jnz     loc_18000D1B2
0x18000d119  cmp     dword ptr [rcx+68h], 0FFFFFFFFh
0x18000d11d  jnz     loc_18000D1B2
0x18000d123  cmp     dword ptr [rcx+6Ch], 0FFFFFFFFh
0x18000d127  jnz     loc_18000D1B2
0x18000d12d  cmp     dword ptr [rcx+70h], 0
0x18000d131  jnz     short loc_18000D1B2
0x18000d133  mov     byte ptr [rcx+30h], 1
0x18000d137  mov     eax, 1
0x18000d13c  mov     r9b, [rsp+58h+arg_38]
0x18000d144  mov     r8, r11
0x18000d147  mov     [rcx+24h], eax
0x18000d14a  mov     rdx, r14
0x18000d14d  mov     rax, [rcx]
0x18000d150  xor     edi, edi
0x18000d152  mov     rax, [rax+98h]
0x18000d159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d15e  mov     [rbx+5Ch], bpl
0x18000d162  test    sil, sil
0x18000d165  jz      short loc_18000D170
0x18000d167  test    bpl, bpl
0x18000d16a  jz      short loc_18000D170
0x18000d16c  mov     al, 1
0x18000d16e  jmp     short loc_18000D172
0x18000d170  xor     eax, eax
0x18000d172  mov     rcx, [rbx+10h]
0x18000d176  mov     [rbx+5Dh], al
0x18000d179  mov     eax, [rbx+68h]
0x18000d17c  inc     eax
0x18000d17e  mov     dword ptr [rbx+64h], 1
0x18000d185  mov     [rbx+60h], eax
0x18000d188  mov     eax, [rsp+58h+arg_20]
0x18000d18f  mov     [rbx+2Ch], eax
0x18000d192  test    rcx, rcx
0x18000d195  jz      short loc_18000D1B7
0x18000d197  mov     rax, [rcx]
0x18000d19a  mov     r8b, sil
0x18000d19d  mov     rdx, [rsp+58h+arg_28]
0x18000d1a5  mov     rax, [rax+70h]
0x18000d1a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1ae  mov     edi, eax
0x18000d1b0  jmp     short loc_18000D1B7
0x18000d1b2  mov     edi, 80004005h
0x18000d1b7  mov     eax, edi
0x18000d1b9  add     rsp, 30h
0x18000d1bd  pop     r14
0x18000d1bf  pop     rdi
0x18000d1c0  pop     rsi
0x18000d1c1  pop     rbp
0x18000d1c2  pop     rbx
0x18000d1c3  retn
```
