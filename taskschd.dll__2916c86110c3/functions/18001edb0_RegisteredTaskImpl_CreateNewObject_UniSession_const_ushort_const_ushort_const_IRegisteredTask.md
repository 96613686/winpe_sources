# RegisteredTaskImpl::CreateNewObject(UniSession const &,ushort const *,ushort const *,IRegisteredTask * *)

- ea: `0x18001edb0`
- end: `0x18001f069`
- name: `?CreateNewObject@RegisteredTaskImpl@@SAJAEBVUniSession@@PEBG1PEAPEAUIRegisteredTask@@@Z`
- size: `697`
- prototype: `static int(const struct UniSession *, const unsigned __int16 *, const unsigned __int16 *, struct IRegisteredTask **)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e4d0`
- `0x18001e2c0`
- `0x1800439a0`

## callees

- `0x1800017f0`
- `0x180009a30`
- `0x18001edb0`
- `0x18001f070`
- `0x18001f808`
- `0x180039524`
- `0x18003a9b0`
- `0x18003b536`
- `0x180044410`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001ef7e`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ef7e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ef75`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ef75`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegisteredTaskImpl::CreateNewObject(
        const struct UniSession *a1,
        const unsigned __int16 *a2,
        OLECHAR *a3,
        struct IRegisteredTask **a4)
{
  int v8; // ebx
  _QWORD *v9; // rsi
  int v10; // ebp
  __int64 v12; // rbx
  _QWORD *v13; // rbx
  __int64 v14; // r14
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rax
  __int64 v18; // rcx
  void *v19; // rcx
  _QWORD *v20; // rcx
  OLECHAR *v21; // rcx
  BSTR v22; // rax
  _WORD *v23; // rcx
  struct IRegisteredTask *v24; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v25; // [rsp+28h] [rbp-50h] BYREF

  v24 = 0;
  v25 = 0;
  v8 = ATL::CComObject<RegisteredTaskImpl>::CreateInstance(&v25);
  if ( v8 >= 0 )
  {
    v9 = v25;
    v10 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IRegisteredTask **))*v25)(
            v25,
            &GUID_9c86f320_dee3_4dd1_b972_a303f26b061e,
            &v24);
    if ( v10 < 0 )
    {
      if ( v24 )
        ((void (__fastcall *)(struct IRegisteredTask *))v24->lpVtbl->Release)(v24);
      return (unsigned int)v10;
    }
    *((_DWORD *)v9 + 32) = *(_DWORD *)a1;
    *((_DWORD *)v9 + 33) = *((_DWORD *)a1 + 1);
    v12 = *((_QWORD *)a1 + 1);
    if ( v12 )
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
    wmi::AutoRef<RpcFolderSnapshot>::Release(v9 + 17);
    v9[17] = v12;
    v13 = v9 + 18;
    v14 = *((_QWORD *)a1 + 2);
    if ( v9[18] != v14 && v9 != (_QWORD *)-144LL )
    {
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      if ( *v13 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 16LL))(*v13);
      *v13 = v14;
    }
    if ( a2 )
    {
      if ( *a2 )
      {
        v15 = -1;
        do
          ++v15;
        while ( a2[v15] );
      }
      else
      {
        v15 = 0;
      }
      v16 = v9[13];
      if ( v16 < 8 )
        v17 = (unsigned __int64)(v9 + 10);
      else
        v17 = v9[10];
      if ( (unsigned __int64)a2 >= v17 )
      {
        v18 = v16 < 8 ? (__int64)(v9 + 10) : v9[10];
        if ( v18 + 2LL * v9[12] > (unsigned __int64)a2 )
        {
          std::wstring::assign(v9 + 10);
          goto LABEL_33;
        }
      }
      if ( v15 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlength_error("string too long");
      if ( v16 < v15 )
      {
        std::wstring::_Copy(v9 + 10, v15, v9[12]);
        if ( !v15 )
          goto LABEL_33;
        goto LABEL_28;
      }
      if ( v15 )
      {
LABEL_28:
        if ( v9[13] < 8u )
          v19 = v9 + 10;
        else
          v19 = (void *)v9[10];
        memcpy_0(v19, a2, 2 * v15);
        if ( v9[13] < 8u )
          v20 = v9 + 10;
        else
          v20 = (_QWORD *)v9[10];
        v9[12] = v15;
        *((_WORD *)v20 + v15) = 0;
        goto LABEL_33;
      }
      if ( v16 < 8 )
        v23 = v9 + 10;
      else
        v23 = (_WORD *)v9[10];
      v9[12] = 0;
      *v23 = 0;
    }
LABEL_33:
    if ( a3 )
    {
      v21 = (OLECHAR *)v9[14];
      if ( a3 != v21 )
      {
        SysFreeString(v21);
        v22 = SysAllocString(a3);
        v9[14] = v22;
        if ( !v22 )
          ATL::PrivateAtlThrow(-2147024882);
      }
    }
    *a4 = v24;
    return (unsigned int)v10;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v24);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001edb0  push    rbx
0x18001edb2  push    rbp
0x18001edb3  push    rsi
0x18001edb4  push    rdi
0x18001edb5  push    r12
0x18001edb7  push    r13
0x18001edb9  push    r14
0x18001edbb  push    r15
0x18001edbd  sub     rsp, 38h
0x18001edc1  mov     r12, r9
0x18001edc4  mov     r15, r8
0x18001edc7  mov     rdi, rdx
0x18001edca  mov     r14, rcx
0x18001edcd  xor     eax, eax
0x18001edcf  mov     [rsp+78h+var_58], rax
0x18001edd4  mov     [rsp+78h+var_50], rax
0x18001edd9  lea     rcx, [rsp+78h+var_50]
0x18001edde  call    ?CreateInstance@?$CComObject@VRegisteredTaskImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<RegisteredTaskImpl>::CreateInstance(ATL::CComObject<RegisteredTaskImpl> * *)
0x18001ede3  mov     ebx, eax
0x18001ede5  test    eax, eax
0x18001ede7  js      loc_18001F006
0x18001eded  mov     rsi, [rsp+78h+var_50]
0x18001edf2  mov     rax, [rsi]
0x18001edf5  lea     r8, [rsp+78h+var_58]
0x18001edfa  lea     rdx, _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e
0x18001ee01  mov     rcx, rsi
0x18001ee04  mov     rax, [rax]
0x18001ee07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee0c  mov     ebp, eax
0x18001ee0e  test    eax, eax
0x18001ee10  jns     short loc_18001EE3C
0x18001ee12  mov     rcx, [rsp+78h+var_58]
0x18001ee17  test    rcx, rcx
0x18001ee1a  jz      short loc_18001EE29
0x18001ee1c  mov     rdx, [rcx]
0x18001ee1f  mov     rax, [rdx+10h]
0x18001ee23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee28  nop
0x18001ee29  mov     eax, ebp
0x18001ee2b  add     rsp, 38h
0x18001ee2f  pop     r15
0x18001ee31  pop     r14
0x18001ee33  pop     r13
0x18001ee35  pop     r12
0x18001ee37  pop     rdi
0x18001ee38  pop     rsi
0x18001ee39  pop     rbp
0x18001ee3a  pop     rbx
0x18001ee3b  retn
0x18001ee3c  mov     eax, [r14]
0x18001ee3f  mov     [rsi+80h], eax
0x18001ee45  mov     eax, [r14+4]
0x18001ee49  mov     [rsi+84h], eax
0x18001ee4f  mov     rbx, [r14+8]
0x18001ee53  test    rbx, rbx
0x18001ee56  jnz     loc_18001EFB9
0x18001ee5c  lea     rcx, [rsi+88h]
0x18001ee63  call    ?Release@?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAXXZ; wmi::AutoRef<RpcFolderSnapshot>::Release(void)
0x18001ee68  mov     [rsi+88h], rbx
0x18001ee6f  lea     rbx, [rsi+90h]
0x18001ee76  mov     r14, [r14+10h]
0x18001ee7a  cmp     [rbx], r14
0x18001ee7d  jz      short loc_18001EEA4
0x18001ee7f  test    rbx, rbx
0x18001ee82  jz      short loc_18001EEA4
0x18001ee84  test    r14, r14
0x18001ee87  jnz     loc_18001F017
0x18001ee8d  mov     rcx, [rbx]
0x18001ee90  test    rcx, rcx
0x18001ee93  jz      short loc_18001EEA1
0x18001ee95  mov     rax, [rcx]
0x18001ee98  mov     rax, [rax+10h]
0x18001ee9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eea1  mov     [rbx], r14
0x18001eea4  test    rdi, rdi
0x18001eea7  jz      loc_18001EF59
0x18001eead  cmp     word ptr [rdi], 0
0x18001eeb1  jz      loc_18001EF98
0x18001eeb7  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001eebe  xchg    ax, ax
0x18001eec0  inc     rbx
0x18001eec3  cmp     word ptr [rdi+rbx*2], 0
0x18001eec8  jnz     short loc_18001EEC0
0x18001eeca  mov     rdx, [rsi+68h]
0x18001eece  cmp     rdx, 8
0x18001eed2  jb      loc_18001F02B
0x18001eed8  mov     rax, [rsi+50h]
0x18001eedc  cmp     rdi, rax
0x18001eedf  jb      short loc_18001EF00
0x18001eee1  cmp     rdx, 8
0x18001eee5  jb      loc_18001F034
0x18001eeeb  mov     rcx, [rsi+50h]
0x18001eeef  mov     rax, [rsi+60h]
0x18001eef3  lea     rcx, [rcx+rax*2]
0x18001eef7  cmp     rcx, rdi
0x18001eefa  ja      loc_18001EFC2
0x18001ef00  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001ef0a  cmp     rbx, rax
0x18001ef0d  ja      loc_18001F043
0x18001ef13  cmp     rdx, rbx
0x18001ef16  jb      loc_18001EF9F
0x18001ef1c  test    rbx, rbx
0x18001ef1f  jz      loc_18001EFEA
0x18001ef25  cmp     qword ptr [rsi+68h], 8
0x18001ef2a  jb      loc_18001F056
0x18001ef30  mov     rcx, [rsi+50h]; void *
0x18001ef34  lea     r8, [rbx+rbx]; Size
0x18001ef38  mov     rdx, rdi; Src
0x18001ef3b  call    memcpy_0
0x18001ef40  cmp     qword ptr [rsi+68h], 8
0x18001ef45  jb      loc_18001F05F
0x18001ef4b  mov     rcx, [rsi+50h]
0x18001ef4f  mov     [rsi+60h], rbx
0x18001ef53  xor     eax, eax
0x18001ef55  mov     [rcx+rbx*2], ax
0x18001ef59  test    r15, r15
0x18001ef5c  jnz     short loc_18001EF6C
0x18001ef5e  mov     rax, [rsp+78h+var_58]
0x18001ef63  mov     [r12], rax
0x18001ef67  jmp     loc_18001EE29
0x18001ef6c  mov     rcx, [rsi+70h]; bstrString
0x18001ef70  cmp     r15, rcx
0x18001ef73  jz      short loc_18001EF5E
0x18001ef75  call    cs:__imp_SysFreeString
0x18001ef7b  mov     rcx, r15; psz
0x18001ef7e  call    cs:__imp_SysAllocString
0x18001ef84  mov     [rsi+70h], rax
0x18001ef88  test    rax, rax
0x18001ef8b  jnz     short loc_18001EF5E
0x18001ef8d  mov     ecx, 8007000Eh; int
0x18001ef92  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18001ef98  xor     ebx, ebx
0x18001ef9a  jmp     loc_18001EECA
0x18001ef9f  mov     r8, [rsi+60h]
0x18001efa3  mov     rdx, rbx
0x18001efa6  lea     rcx, [rsi+50h]
0x18001efaa  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18001efaf  test    rbx, rbx
0x18001efb2  jz      short loc_18001EF59
0x18001efb4  jmp     loc_18001EF25
0x18001efb9  lock inc dword ptr [rbx+8]
0x18001efbd  jmp     loc_18001EE5C
0x18001efc2  cmp     rdx, 8
0x18001efc6  jb      short loc_18001F03D
0x18001efc8  mov     rax, [rsi+50h]
0x18001efcc  sub     rdi, rax
0x18001efcf  sar     rdi, 1
0x18001efd2  mov     r9, rbx
0x18001efd5  mov     r8, rdi
0x18001efd8  lea     rdx, [rsi+50h]
0x18001efdc  lea     rcx, [rsi+50h]; void *
0x18001efe0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001efe5  jmp     loc_18001EF59
0x18001efea  cmp     rdx, 8
0x18001efee  jb      short loc_18001F050
0x18001eff0  mov     rcx, [rsi+50h]
0x18001eff4  mov     qword ptr [rsi+60h], 0
0x18001effc  xor     eax, eax
0x18001effe  mov     [rcx], ax
0x18001f001  jmp     loc_18001EF59
0x18001f006  lea     rcx, [rsp+78h+var_58]
0x18001f00b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001f010  mov     eax, ebx
0x18001f012  jmp     loc_18001EE2B
0x18001f017  mov     rax, [r14]
0x18001f01a  mov     rcx, r14
0x18001f01d  mov     rax, [rax+8]
0x18001f021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f026  jmp     loc_18001EE8D
0x18001f02b  lea     rax, [rsi+50h]
0x18001f02f  jmp     loc_18001EEDC
0x18001f034  lea     rcx, [rsi+50h]
0x18001f038  jmp     loc_18001EEEF
0x18001f03d  lea     rax, [rsi+50h]
0x18001f041  jmp     short loc_18001EFCC
0x18001f043  lea     rcx, aStringTooLong; "string too long"
0x18001f04a  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001f050  lea     rcx, [rsi+50h]
0x18001f054  jmp     short loc_18001EFF4
0x18001f056  lea     rcx, [rsi+50h]
0x18001f05a  jmp     loc_18001EF34
0x18001f05f  lea     rcx, [rsi+50h]
0x18001f063  jmp     loc_18001EF4F
```
