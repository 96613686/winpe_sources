# CReaderContext::Status(ulong *,ulong *,CBuffer &,CBuffer &)

- ea: `0x18000fd94`
- end: `0x18000fefc`
- name: `?Status@CReaderContext@@QEAAXPEAK0AEAVCBuffer@@1@Z`
- size: `360`
- prototype: `void(CReaderContext *__hidden this, unsigned int *, unsigned int *, struct CBuffer *, struct CBuffer *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18000fb40`
- `0x180018960`
- `0x180023820`

## callees

- `0x180005970`
- `0x180005a90`
- `0x18000fd94`
- `0x18000ff10`
- `0x18000ff40`
- `0x180010298`
- `0x18001b9b8`
- `0x18001ba04`
- `0x18002ef20`
- `0x18002ef38`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CReaderContext::Status(
        CReaderContext *this,
        unsigned int *a2,
        unsigned int *a3,
        struct CBuffer *a4,
        struct CBuffer *a5)
{
  int v6; // edi
  int v7; // esi
  CSCardSubcontext *v9; // r14
  int v10; // eax
  size_t v11; // rdi
  void *v12; // r12
  void *v13; // r15
  void *v14; // rcx
  int v15; // [rsp+38h] [rbp-50h]
  int pExceptionObject; // [rsp+40h] [rbp-48h] BYREF
  ulong v17; // [rsp+44h] [rbp-44h] BYREF
  void *Src; // [rsp+48h] [rbp-40h] BYREF
  unsigned __int16 *v19[2]; // [rsp+50h] [rbp-38h] BYREF
  size_t Size; // [rsp+90h] [rbp+8h] BYREF

  v6 = (int)a3;
  v7 = (int)a2;
  Src = 0;
  LODWORD(Size) = 0;
  v19[0] = 0;
  v9 = (CSCardSubcontext *)*((_QWORD *)this + 3);
  CSCardSubcontext::WaitForAvailable(v9);
  v19[1] = (unsigned __int16 *)v9;
  try
  {
    v10 = CalRpcStatus(
            *(_QWORD *)(*((_QWORD *)this + 3) + 112LL),
            *((_DWORD *)this + 8),
            v7,
            v6,
            (__int64)&Src,
            (__int64)&Size,
            (__int64)v19,
            v15,
            pExceptionObject,
            (int)Src,
            (int)v19[0]);
    if ( v10 )
    {
      pExceptionObject = v10;
      throw (ulong *)&pExceptionObject;
    }
    v11 = (unsigned int)Size;
    v12 = Src;
    if ( *((_DWORD *)a4 + 5) < (unsigned int)Size )
    {
      v13 = operator new[]((unsigned int)Size);
      if ( !v13 )
      {
        v17 = 14;
        throw &v17;
      }
      v14 = (void *)*((_QWORD *)a4 + 1);
      if ( v14 )
        operator delete(v14);
      *((_QWORD *)a4 + 1) = v13;
      *((_DWORD *)a4 + 5) = v11;
    }
    *((_DWORD *)a4 + 4) = 0;
    if ( (_DWORD)v11 )
      memcpy_0(*((void **)a4 + 1), v12, v11);
    *((_DWORD *)a4 + 4) = v11;
    ListReaderNames(*(unsigned int *)(*(_QWORD *)(*((_QWORD *)this + 3) + 40LL) + 28LL), v19[0], a5);
  }
  catch ( ... )
  {
    MIDL_user_free(Src);
    MIDL_user_free(v19[0]);
    throw;
  }
  MIDL_user_free(Src);
  MIDL_user_free(v19[0]);
  if ( v9 )
    CSCardSubcontext::ReleaseSubcontext(v9);
}

```

## disassembly

```asm
0x18000fd94  mov     rax, rsp
0x18000fd97  mov     [rax+10h], rbx
0x18000fd9b  mov     [rax+18h], rsi
0x18000fd9f  push    rdi
0x18000fda0  push    r12
0x18000fda2  push    r13
0x18000fda4  push    r14
0x18000fda6  push    r15
0x18000fda8  sub     rsp, 60h
0x18000fdac  mov     rbx, r9
0x18000fdaf  mov     rdi, r8
0x18000fdb2  mov     rsi, rdx
0x18000fdb5  mov     r13, rcx
0x18000fdb8  xor     r15d, r15d
0x18000fdbb  mov     [rax-40h], r15
0x18000fdbf  mov     [rax+8], r15d
0x18000fdc3  mov     [rax-38h], r15
0x18000fdc7  mov     r14, [rcx+18h]
0x18000fdcb  mov     [rax-30h], r15
0x18000fdcf  mov     rcx, r14; this
0x18000fdd2  call    ?WaitForAvailable@CSCardSubcontext@@QEAAXXZ; CSCardSubcontext::WaitForAvailable(void)
0x18000fdd7  mov     [rsp+88h+var_30], r14
0x18000fddc  mov     rcx, [r13+18h]
0x18000fde0  lea     rax, [rsp+88h+var_38]
0x18000fde5  mov     [rsp+88h+var_58], rax; __int64
0x18000fdea  lea     rax, [rsp+88h+Size]
0x18000fdf2  mov     [rsp+88h+var_60], rax; __int64
0x18000fdf7  lea     rax, [rsp+88h+Src]
0x18000fdfc  mov     [rsp+88h+var_68], rax; __int64
0x18000fe01  mov     r9, rdi; int
0x18000fe04  mov     r8, rsi; int
0x18000fe07  mov     edx, [r13+20h]; int
0x18000fe0b  mov     rcx, [rcx+70h]; int
0x18000fe0f  call    CalRpcStatus
0x18000fe14  test    eax, eax
0x18000fe16  jnz     loc_18000FECC
0x18000fe1c  mov     edi, dword ptr [rsp+88h+Size]
0x18000fe23  mov     r12, [rsp+88h+Src]
0x18000fe28  cmp     [rbx+14h], edi
0x18000fe2b  jnb     short loc_18000FE58
0x18000fe2d  mov     ecx, edi; unsigned __int64
0x18000fe2f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000fe34  mov     r15, rax
0x18000fe37  test    rax, rax
0x18000fe3a  jz      loc_18000FEE1
0x18000fe40  mov     rcx, [rbx+8]; void *
0x18000fe44  test    rcx, rcx
0x18000fe47  jz      short loc_18000FE4E
0x18000fe49  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fe4e  mov     [rbx+8], r15
0x18000fe52  mov     [rbx+14h], edi
0x18000fe55  xor     r15d, r15d
0x18000fe58  mov     [rbx+10h], r15d
0x18000fe5c  test    edi, edi
0x18000fe5e  jz      short loc_18000FE6F
0x18000fe60  mov     r8, rdi; Size
0x18000fe63  mov     rdx, r12; Src
0x18000fe66  mov     rcx, [rbx+8]; void *
0x18000fe6a  call    memcpy_0
0x18000fe6f  mov     [rbx+10h], edi
0x18000fe72  mov     rax, [r13+18h]
0x18000fe76  mov     rcx, [rax+28h]
0x18000fe7a  mov     r8, [rsp+88h+arg_20]; struct CBuffer *
0x18000fe82  mov     rdx, [rsp+88h+var_38]; unsigned __int16 *
0x18000fe87  mov     ecx, [rcx+1Ch]; unsigned int
0x18000fe8a  call    ?ListReaderNames@@YAXKPEBGAEAVCBuffer@@@Z; ListReaderNames(ulong,ushort const *,CBuffer &)
0x18000fe8f  nop
0x18000fe90  mov     rcx, [rsp+88h+Src]; void *
0x18000fe95  call    MIDL_user_free
0x18000fe9a  mov     rcx, [rsp+88h+var_38]; void *
0x18000fe9f  call    MIDL_user_free
0x18000fea4  nop
0x18000fea5  test    r14, r14
0x18000fea8  jz      short loc_18000FEB2
0x18000feaa  mov     rcx, r14; this
0x18000fead  call    ?ReleaseSubcontext@CSCardSubcontext@@QEAAXXZ; CSCardSubcontext::ReleaseSubcontext(void)
0x18000feb2  lea     r11, [rsp+88h+var_28]
0x18000feb7  mov     rbx, [r11+38h]
0x18000febb  mov     rsi, [r11+40h]
0x18000febf  mov     rsp, r11
0x18000fec2  pop     r15
0x18000fec4  pop     r14
0x18000fec6  pop     r13
0x18000fec8  pop     r12
0x18000feca  pop     rdi
0x18000fecb  retn
0x18000fecc  mov     [rsp+88h+pExceptionObject], eax
0x18000fed0  lea     rdx, _TI1K; pThrowInfo
0x18000fed7  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18000fedc  call    _CxxThrowException_0
0x18000fee1  mov     [rsp+88h+var_44], 0Eh
0x18000fee9  lea     rdx, _TI1K; pThrowInfo
0x18000fef0  lea     rcx, [rsp+88h+var_44]; pExceptionObject
0x18000fef5  call    _CxxThrowException_0
```
