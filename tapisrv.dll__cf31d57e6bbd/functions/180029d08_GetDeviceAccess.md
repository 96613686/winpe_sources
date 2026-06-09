# GetDeviceAccess

- ea: `0x180029d08`
- end: `0x18002a05d`
- name: `GetDeviceAccess`
- size: `853`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002b25c`

## callees

- `0x180029d08`
- `0x18002a064`
- `0x18002c8d4`
- `0x18003dc84`
- `0x180040010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180029d48`
- `KERNEL32!HeapAlloc` at `0x180029d6b`
- `KERNEL32!HeapAlloc` at `0x180029dfe`
- `KERNEL32!HeapAlloc` at `0x180029e26`
- `KERNEL32!HeapAlloc` at `0x180029f2b`
- `KERNEL32!HeapAlloc` at `0x180029f50`
- `KERNEL32!HeapAlloc` at `0x180029fce`
- `KERNEL32!HeapAlloc` at `0x180029ff3`
- `KERNEL32!HeapAlloc` at `0x180029d48`
- `KERNEL32!HeapAlloc` at `0x180029d6b`
- `KERNEL32!HeapAlloc` at `0x180029dfe`
- `KERNEL32!HeapAlloc` at `0x180029e26`
- `KERNEL32!HeapAlloc` at `0x180029f2b`
- `KERNEL32!HeapAlloc` at `0x180029f50`
- `KERNEL32!HeapAlloc` at `0x180029fce`
- `KERNEL32!HeapAlloc` at `0x180029ff3`

## string_xrefs

- `0x180029db6`: `Returned STRUCTURETOOSMALL, but specified less line devs in TAPICLINET_GETDEVICEACCESS`
- `0x180029dcd`: `Returned STRUCTURETOOSMALL, but specified less phone devs in TAPICLINET_GETDEVICEACCESS`
- `0x180029e92`: `GetDeviceAccess failed - error %lu`
- `0x180029ec6`: `Returned dwLineDevs greater that the buffer specified in TAPICLIENT_GETDEVICEACCESS`
- `0x180029ef0`: `Returned dwPhoneDevs greater that the buffer specified in TAPICLIENT_GETDEVICEACCESS`

## pseudocode

```c
__int64 __fastcall GetDeviceAccess(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // r14
  void *v6; // rsi
  LPVOID v7; // rax
  unsigned int v8; // r15d
  unsigned int v9; // r12d
  int v10; // eax
  unsigned int v11; // r14d
  void *v12; // rdi
  void *v13; // rcx
  void *v14; // rcx
  unsigned int v16; // eax
  LPVOID v17; // rax
  LPVOID v18; // rax
  __int64 v19; // r15
  __int64 i; // r14
  int DeviceIDFromPermanentID; // eax
  LPVOID v22; // rax
  LPVOID v23; // rax
  __int64 v24; // r14
  __int64 j; // rsi
  int v26; // eax
  unsigned int v27[4]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v29; // [rsp+A8h] [rbp+58h] BYREF

  v27[0] = 3;
  v5 = a1;
  v29 = 3;
  v6 = HeapAlloc(ghTapisrvHeap, 8u, 0x18u);
  if ( v6 )
  {
    v7 = HeapAlloc(ghTapisrvHeap, 8u, 8 * v29);
    while ( 1 )
    {
      v12 = v7;
      if ( !v7 )
        goto LABEL_11;
      v8 = v27[0];
      v9 = v29;
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, void *, unsigned int *, LPVOID, unsigned int *))(v5 + 48))(
              a3,
              a2,
              v6,
              v27,
              v7,
              &v29);
      v11 = v10;
      if ( v10 != -2147483571 )
        break;
      if ( v27[0] < v8 )
        TRACELogPrint(65538, "Returned STRUCTURETOOSMALL, but specified less line devs in TAPICLINET_GETDEVICEACCESS");
      if ( v29 < v9 )
        TRACELogPrint(65538, "Returned STRUCTURETOOSMALL, but specified less phone devs in TAPICLINET_GETDEVICEACCESS");
      ServerFree(v6);
      v6 = HeapAlloc(ghTapisrvHeap, 8u, 8 * v27[0]);
      if ( !v6 )
        goto LABEL_12;
      ServerFree(v12);
      v7 = HeapAlloc(ghTapisrvHeap, 8u, 8 * v29);
      v5 = a1;
    }
    if ( v10 )
    {
      TRACELogPrint(65538, "GetDeviceAccess failed - error %lu", v10);
      ServerFree(v6);
      ServerFree(v12);
      return v11;
    }
    v16 = v27[0];
    if ( v27[0] > v8 )
    {
      TRACELogPrint(65538, "Returned dwLineDevs greater that the buffer specified in TAPICLIENT_GETDEVICEACCESS");
      TRACELogPrint(65538, "   Will only use the number the buffer can hold");
      v16 = v8;
      v27[0] = v8;
    }
    if ( v29 > v9 )
    {
      TRACELogPrint(65538, "Returned dwPhoneDevs greater that the buffer specified in TAPICLIENT_GETDEVICEACCESS");
      TRACELogPrint(65538, "   Will only use the number the buffer can hold");
      v16 = v27[0];
      v29 = v9;
    }
    v17 = HeapAlloc(ghTapisrvHeap, 8u, 4 * v16);
    *(_QWORD *)(a2 + 88) = v17;
    if ( !v17 )
      goto LABEL_11;
    v18 = HeapAlloc(ghTapisrvHeap, 8u, 8 * v27[0]);
    *(_QWORD *)(a2 + 80) = v18;
    if ( !v18 )
      goto LABEL_11;
    v19 = 0;
    for ( i = 0; (unsigned int)i < v27[0]; i = (unsigned int)(i + 1) )
    {
      DeviceIDFromPermanentID = GetDeviceIDFromPermanentID(*((_QWORD *)v6 + i), 1);
      if ( DeviceIDFromPermanentID != -1 )
      {
        *(_DWORD *)(*(_QWORD *)(a2 + 88) + 4 * v19) = DeviceIDFromPermanentID;
        *(_DWORD *)(*(_QWORD *)(a2 + 80) + 8 * v19) = *((_DWORD *)v6 + 2 * i);
        *(_DWORD *)(*(_QWORD *)(a2 + 80) + 8 * v19 + 4) = *((_DWORD *)v6 + 2 * i + 1);
        v19 = (unsigned int)(v19 + 1);
      }
    }
    *(_DWORD *)(a2 + 96) = v19;
    ServerFree(v6);
    v22 = HeapAlloc(ghTapisrvHeap, 8u, 4 * v29);
    *(_QWORD *)(a2 + 112) = v22;
    if ( !v22 || (v23 = HeapAlloc(ghTapisrvHeap, 8u, 8 * v29), (*(_QWORD *)(a2 + 104) = v23) == 0) )
    {
LABEL_11:
      ServerFree(v6);
LABEL_12:
      if ( v12 )
        ServerFree(v12);
      goto LABEL_14;
    }
    v24 = 0;
    for ( j = 0; (unsigned int)j < v29; j = (unsigned int)(j + 1) )
    {
      v26 = GetDeviceIDFromPermanentID(*((_QWORD *)v12 + j), 0);
      if ( v26 != -1 )
      {
        *(_DWORD *)(*(_QWORD *)(a2 + 112) + 4 * v24) = v26;
        *(_DWORD *)(*(_QWORD *)(a2 + 104) + 8 * v24) = *((_DWORD *)v12 + 2 * j);
        *(_DWORD *)(*(_QWORD *)(a2 + 104) + 8 * v24 + 4) = *((_DWORD *)v12 + 2 * j + 1);
        v24 = (unsigned int)(v24 + 1);
      }
    }
    *(_DWORD *)(a2 + 120) = v24;
    ServerFree(v12);
    return 0;
  }
  else
  {
LABEL_14:
    v13 = *(void **)(a2 + 80);
    if ( v13 )
      ServerFree(v13);
    v14 = *(void **)(a2 + 104);
    if ( v14 )
      ServerFree(v14);
    return 2147483716LL;
  }
}

```

## disassembly

```asm
0x180029d08  mov     [rsp-38h+arg_8], rbx
0x180029d0d  mov     [rsp-38h+arg_0], rcx
0x180029d12  push    rbp
0x180029d13  push    rsi
0x180029d14  push    rdi
0x180029d15  push    r12
0x180029d17  push    r13
0x180029d19  push    r14
0x180029d1b  push    r15
0x180029d1d  mov     rbp, rsp
0x180029d20  sub     rsp, 50h
0x180029d24  mov     eax, 3
0x180029d29  mov     r13, r8
0x180029d2c  mov     rbx, rdx
0x180029d2f  mov     [rbp+var_10], eax
0x180029d32  mov     r14, rcx
0x180029d35  mov     [rbp+arg_18], eax
0x180029d38  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180029d3f  lea     edi, [rax+5]
0x180029d42  mov     edx, edi; dwFlags
0x180029d44  lea     r8d, [rax+15h]; dwBytes
0x180029d48  call    cs:__imp_HeapAlloc
0x180029d4e  mov     rsi, rax
0x180029d51  test    rax, rax
0x180029d54  jz      loc_180029E51
0x180029d5a  mov     r8d, [rbp+arg_18]
0x180029d5e  mov     edx, edi; dwFlags
0x180029d60  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180029d67  shl     r8d, 3; dwBytes
0x180029d6b  call    cs:__imp_HeapAlloc
0x180029d71  jmp     loc_180029E30
0x180029d76  mov     r15d, [rbp+var_10]
0x180029d7a  lea     rax, [rbp+arg_18]
0x180029d7e  mov     r12d, [rbp+arg_18]
0x180029d82  lea     r9, [rbp+var_10]
0x180029d86  mov     [rsp+50h+var_28], rax
0x180029d8b  mov     r8, rsi
0x180029d8e  mov     rax, [r14+30h]
0x180029d92  mov     rdx, rbx
0x180029d95  mov     rcx, r13
0x180029d98  mov     [rsp+50h+var_30], rdi
0x180029d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029da2  mov     r14d, eax
0x180029da5  cmp     eax, 8000004Dh
0x180029daa  jnz     loc_180029E8A
0x180029db0  cmp     [rbp+var_10], r15d
0x180029db4  jnb     short loc_180029DC7
0x180029db6  lea     rdx, aReturnedStruct_0; "Returned STRUCTURETOOSMALL, but specifi"...
0x180029dbd  mov     ecx, 10002h
0x180029dc2  call    TRACELogPrint
0x180029dc7  cmp     [rbp+arg_18], r12d
0x180029dcb  jnb     short loc_180029DDE
0x180029dcd  lea     rdx, aReturnedStruct; "Returned STRUCTURETOOSMALL, but specifi"...
0x180029dd4  mov     ecx, 10002h
0x180029dd9  call    TRACELogPrint
0x180029dde  mov     rcx, rsi; lpMem
0x180029de1  call    ServerFree
0x180029de6  mov     r8d, [rbp+var_10]
0x180029dea  mov     r14d, 8
0x180029df0  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180029df7  mov     edx, r14d; dwFlags
0x180029dfa  shl     r8d, 3; dwBytes
0x180029dfe  call    cs:__imp_HeapAlloc
0x180029e04  mov     rsi, rax
0x180029e07  test    rax, rax
0x180029e0a  jz      short loc_180029E44
0x180029e0c  mov     rcx, rdi; lpMem
0x180029e0f  call    ServerFree
0x180029e14  mov     r8d, [rbp+arg_18]
0x180029e18  mov     edx, r14d; dwFlags
0x180029e1b  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180029e22  shl     r8d, 3; dwBytes
0x180029e26  call    cs:__imp_HeapAlloc
0x180029e2c  mov     r14, [rbp+arg_0]
0x180029e30  mov     rdi, rax
0x180029e33  test    rax, rax
0x180029e36  jnz     loc_180029D76
0x180029e3c  mov     rcx, rsi; lpMem
0x180029e3f  call    ServerFree
0x180029e44  test    rdi, rdi
0x180029e47  jz      short loc_180029E51
0x180029e49  mov     rcx, rdi; lpMem
0x180029e4c  call    ServerFree
0x180029e51  mov     rcx, [rbx+50h]; lpMem
0x180029e55  test    rcx, rcx
0x180029e58  jz      short loc_180029E5F
0x180029e5a  call    ServerFree
0x180029e5f  mov     rcx, [rbx+68h]; lpMem
0x180029e63  test    rcx, rcx
0x180029e66  jz      short loc_180029E6D
0x180029e68  call    ServerFree
0x180029e6d  mov     eax, 80000044h
0x180029e72  mov     rbx, [rsp+50h+arg_8]
0x180029e7a  add     rsp, 50h
0x180029e7e  pop     r15
0x180029e80  pop     r14
0x180029e82  pop     r13
0x180029e84  pop     r12
0x180029e86  pop     rdi
0x180029e87  pop     rsi
0x180029e88  pop     rbp
0x180029e89  retn
0x180029e8a  test    r14d, r14d
0x180029e8d  jz      short loc_180029EB8
0x180029e8f  mov     r8d, r14d
0x180029e92  lea     rdx, aGetdeviceacces; "GetDeviceAccess failed - error %lu"
0x180029e99  mov     ecx, 10002h
0x180029e9e  call    TRACELogPrint
0x180029ea3  mov     rcx, rsi; lpMem
0x180029ea6  call    ServerFree
0x180029eab  mov     rcx, rdi; lpMem
0x180029eae  call    ServerFree
0x180029eb3  mov     eax, r14d
0x180029eb6  jmp     short loc_180029E72
0x180029eb8  mov     eax, [rbp+var_10]
0x180029ebb  mov     r14d, 10002h
0x180029ec1  cmp     eax, r15d
0x180029ec4  jbe     short loc_180029EEA
0x180029ec6  lea     rdx, aReturnedDwline; "Returned dwLineDevs greater that the bu"...
0x180029ecd  mov     ecx, r14d
0x180029ed0  call    TRACELogPrint
0x180029ed5  lea     rdx, aWillOnlyUseThe; "   Will only use the number the buffer "...
0x180029edc  mov     ecx, r14d
0x180029edf  call    TRACELogPrint
0x180029ee4  mov     eax, r15d
0x180029ee7  mov     [rbp+var_10], eax
0x180029eea  cmp     [rbp+arg_18], r12d
0x180029eee  jbe     short loc_180029F15
0x180029ef0  lea     rdx, aReturnedDwphon; "Returned dwPhoneDevs greater that the b"...
0x180029ef7  mov     ecx, r14d
0x180029efa  call    TRACELogPrint
0x180029eff  lea     rdx, aWillOnlyUseThe; "   Will only use the number the buffer "...
0x180029f06  mov     ecx, r14d
0x180029f09  call    TRACELogPrint
0x180029f0e  mov     eax, [rbp+var_10]
0x180029f11  mov     [rbp+arg_18], r12d
0x180029f15  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180029f1c  mov     r13d, 8
0x180029f22  shl     eax, 2
0x180029f25  mov     edx, r13d; dwFlags
0x180029f28  mov     r8d, eax; dwBytes
0x180029f2b  call    cs:__imp_HeapAlloc
0x180029f31  mov     [rbx+58h], rax
0x180029f35  test    rax, rax
0x180029f38  jz      loc_180029E3C
0x180029f3e  mov     r8d, [rbp+var_10]
0x180029f42  mov     edx, r13d; dwFlags
0x180029f45  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180029f4c  shl     r8d, 3; dwBytes
0x180029f50  call    cs:__imp_HeapAlloc
0x180029f56  mov     [rbx+50h], rax
0x180029f5a  test    rax, rax
0x180029f5d  jz      loc_180029E3C
0x180029f63  xor     r15d, r15d
0x180029f66  xor     r14d, r14d
0x180029f69  cmp     [rbp+var_10], r14d
0x180029f6d  jbe     short loc_180029FB0
0x180029f6f  mov     rcx, [rsi+r14*8]
0x180029f73  mov     edx, 1
0x180029f78  call    GetDeviceIDFromPermanentID
0x180029f7d  cmp     eax, 0FFFFFFFFh
0x180029f80  jz      short loc_180029FA7
0x180029f82  mov     rcx, [rbx+58h]
0x180029f86  mov     [rcx+r15*4], eax
0x180029f8a  mov     rcx, [rbx+50h]
0x180029f8e  mov     eax, [rsi+r14*8]
0x180029f92  mov     [rcx+r15*8], eax
0x180029f96  mov     rcx, [rbx+50h]
0x180029f9a  mov     eax, [rsi+r14*8+4]
0x180029f9f  mov     [rcx+r15*8+4], eax
0x180029fa4  inc     r15d
0x180029fa7  inc     r14d
0x180029faa  cmp     r14d, [rbp+var_10]
0x180029fae  jb      short loc_180029F6F
0x180029fb0  mov     rcx, rsi; lpMem
0x180029fb3  mov     [rbx+60h], r15d
0x180029fb7  call    ServerFree
0x180029fbc  mov     r8d, [rbp+arg_18]
0x180029fc0  mov     edx, r13d; dwFlags
0x180029fc3  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180029fca  shl     r8d, 2; dwBytes
0x180029fce  call    cs:__imp_HeapAlloc
0x180029fd4  mov     [rbx+70h], rax
0x180029fd8  test    rax, rax
0x180029fdb  jz      loc_180029E3C
0x180029fe1  mov     r8d, [rbp+arg_18]
0x180029fe5  mov     edx, r13d; dwFlags
0x180029fe8  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180029fef  shl     r8d, 3; dwBytes
0x180029ff3  call    cs:__imp_HeapAlloc
0x180029ff9  mov     [rbx+68h], rax
0x180029ffd  test    rax, rax
0x18002a000  jz      loc_180029E3C
0x18002a006  xor     r14d, r14d
0x18002a009  xor     esi, esi
0x18002a00b  cmp     [rbp+arg_18], esi
0x18002a00e  jbe     short loc_18002A04A
0x18002a010  mov     rcx, [rdi+rsi*8]
0x18002a014  xor     edx, edx
0x18002a016  call    GetDeviceIDFromPermanentID
0x18002a01b  cmp     eax, 0FFFFFFFFh
0x18002a01e  jz      short loc_18002A043
0x18002a020  mov     rcx, [rbx+70h]
0x18002a024  mov     [rcx+r14*4], eax
0x18002a028  mov     rcx, [rbx+68h]
0x18002a02c  mov     eax, [rdi+rsi*8]
0x18002a02f  mov     [rcx+r14*8], eax
0x18002a033  mov     rcx, [rbx+68h]
0x18002a037  mov     eax, [rdi+rsi*8+4]
0x18002a03b  mov     [rcx+r14*8+4], eax
0x18002a040  inc     r14d
0x18002a043  inc     esi
0x18002a045  cmp     esi, [rbp+arg_18]
0x18002a048  jb      short loc_18002A010
0x18002a04a  mov     rcx, rdi; lpMem
0x18002a04d  mov     [rbx+78h], r14d
0x18002a051  call    ServerFree
0x18002a056  xor     eax, eax
0x18002a058  jmp     loc_180029E72
```
