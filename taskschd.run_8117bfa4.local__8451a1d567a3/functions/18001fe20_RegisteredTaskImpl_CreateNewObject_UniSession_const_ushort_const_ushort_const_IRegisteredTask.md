# RegisteredTaskImpl::CreateNewObject(UniSession const &,ushort const *,ushort const *,IRegisteredTask * *)

- ea: `0x18001fe20`
- end: `0x1800200e5`
- name: `?CreateNewObject@RegisteredTaskImpl@@SAJAEBVUniSession@@PEBG1PEAPEAUIRegisteredTask@@@Z`
- size: `709`
- prototype: `static int(const struct UniSession *, const unsigned __int16 *, const unsigned __int16 *, struct IRegisteredTask **)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e4f0`
- `0x18001f2c0`
- `0x1800471a0`

## callees

- `0x180001880`
- `0x18000a100`
- `0x18001fe20`
- `0x1800200f0`
- `0x180020890`
- `0x18003c664`
- `0x18003d08c`
- `0x18003dd20`
- `0x18003e8a6`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001fff4`
- `OLEAUT32!__imp_SysAllocString` at `0x18001fff4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ffe5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ffe5`

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
0x18001fe20  push    rbx
0x18001fe22  push    rbp
0x18001fe23  push    rsi
0x18001fe24  push    rdi
0x18001fe25  push    r12
0x18001fe27  push    r13
0x18001fe29  push    r14
0x18001fe2b  push    r15
0x18001fe2d  sub     rsp, 38h
0x18001fe31  mov     r12, r9
0x18001fe34  mov     r15, r8
0x18001fe37  mov     rdi, rdx
0x18001fe3a  mov     r14, rcx
0x18001fe3d  xor     eax, eax
0x18001fe3f  mov     [rsp+78h+var_58], rax
0x18001fe44  mov     [rsp+78h+var_50], rax
0x18001fe49  lea     rcx, [rsp+78h+var_50]
0x18001fe4e  call    ?CreateInstance@?$CComObject@VRegisteredTaskImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<RegisteredTaskImpl>::CreateInstance(ATL::CComObject<RegisteredTaskImpl> * *)
0x18001fe53  mov     ebx, eax
0x18001fe55  test    eax, eax
0x18001fe57  js      loc_180020082
0x18001fe5d  mov     rsi, [rsp+78h+var_50]
0x18001fe62  mov     rax, [rsi]
0x18001fe65  lea     r8, [rsp+78h+var_58]
0x18001fe6a  lea     rdx, _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e
0x18001fe71  mov     rcx, rsi
0x18001fe74  mov     rax, [rax]
0x18001fe77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe7c  mov     ebp, eax
0x18001fe7e  test    eax, eax
0x18001fe80  jns     short loc_18001FEAD
0x18001fe82  mov     rcx, [rsp+78h+var_58]
0x18001fe87  test    rcx, rcx
0x18001fe8a  jz      short loc_18001FE99
0x18001fe8c  mov     rdx, [rcx]
0x18001fe8f  mov     rax, [rdx+10h]
0x18001fe93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe98  nop
0x18001fe99  mov     eax, ebp
0x18001fe9b  add     rsp, 38h
0x18001fe9f  pop     r15
0x18001fea1  pop     r14
0x18001fea3  pop     r13
0x18001fea5  pop     r12
0x18001fea7  pop     rdi
0x18001fea8  pop     rsi
0x18001fea9  pop     rbp
0x18001feaa  pop     rbx
0x18001feab  retn
0x18001fead  mov     eax, [r14]
0x18001feb0  mov     [rsi+80h], eax
0x18001feb6  mov     eax, [r14+4]
0x18001feba  mov     [rsi+84h], eax
0x18001fec0  mov     rbx, [r14+8]
0x18001fec4  test    rbx, rbx
0x18001fec7  jnz     loc_180020035
0x18001fecd  lea     rcx, [rsi+88h]
0x18001fed4  call    ?Release@?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAXXZ; wmi::AutoRef<RpcFolderSnapshot>::Release(void)
0x18001fed9  mov     [rsi+88h], rbx
0x18001fee0  lea     rbx, [rsi+90h]
0x18001fee7  mov     r14, [r14+10h]
0x18001feeb  cmp     [rbx], r14
0x18001feee  jz      short loc_18001FF15
0x18001fef0  test    rbx, rbx
0x18001fef3  jz      short loc_18001FF15
0x18001fef5  test    r14, r14
0x18001fef8  jnz     loc_180020093
0x18001fefe  mov     rcx, [rbx]
0x18001ff01  test    rcx, rcx
0x18001ff04  jz      short loc_18001FF12
0x18001ff06  mov     rax, [rcx]
0x18001ff09  mov     rax, [rax+10h]
0x18001ff0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff12  mov     [rbx], r14
0x18001ff15  test    rdi, rdi
0x18001ff18  jz      loc_18001FFC9
0x18001ff1e  cmp     word ptr [rdi], 0
0x18001ff22  jz      loc_180020014
0x18001ff28  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001ff2f  nop
0x18001ff30  inc     rbx
0x18001ff33  cmp     word ptr [rdi+rbx*2], 0
0x18001ff38  jnz     short loc_18001FF30
0x18001ff3a  mov     rdx, [rsi+68h]
0x18001ff3e  cmp     rdx, 8
0x18001ff42  jb      loc_1800200A7
0x18001ff48  mov     rax, [rsi+50h]
0x18001ff4c  cmp     rdi, rax
0x18001ff4f  jb      short loc_18001FF70
0x18001ff51  cmp     rdx, 8
0x18001ff55  jb      loc_1800200B0
0x18001ff5b  mov     rcx, [rsi+50h]
0x18001ff5f  mov     rax, [rsi+60h]
0x18001ff63  lea     rcx, [rcx+rax*2]
0x18001ff67  cmp     rcx, rdi
0x18001ff6a  ja      loc_18002003E
0x18001ff70  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001ff7a  cmp     rbx, rax
0x18001ff7d  ja      loc_1800200BF
0x18001ff83  cmp     rdx, rbx
0x18001ff86  jb      loc_18002001B
0x18001ff8c  test    rbx, rbx
0x18001ff8f  jz      loc_180020066
0x18001ff95  cmp     qword ptr [rsi+68h], 8
0x18001ff9a  jb      loc_1800200D2
0x18001ffa0  mov     rcx, [rsi+50h]; void *
0x18001ffa4  lea     r8, [rbx+rbx]; Size
0x18001ffa8  mov     rdx, rdi; Src
0x18001ffab  call    memcpy_0
0x18001ffb0  cmp     qword ptr [rsi+68h], 8
0x18001ffb5  jb      loc_1800200DB
0x18001ffbb  mov     rcx, [rsi+50h]
0x18001ffbf  mov     [rsi+60h], rbx
0x18001ffc3  xor     eax, eax
0x18001ffc5  mov     [rcx+rbx*2], ax
0x18001ffc9  test    r15, r15
0x18001ffcc  jnz     short loc_18001FFDC
0x18001ffce  mov     rax, [rsp+78h+var_58]
0x18001ffd3  mov     [r12], rax
0x18001ffd7  jmp     loc_18001FE99
0x18001ffdc  mov     rcx, [rsi+70h]; bstrString
0x18001ffe0  cmp     r15, rcx
0x18001ffe3  jz      short loc_18001FFCE
0x18001ffe5  call    cs:__imp_SysFreeString
0x18001ffec  nop     dword ptr [rax+rax+00h]
0x18001fff1  mov     rcx, r15; psz
0x18001fff4  call    cs:__imp_SysAllocString
0x18001fffb  nop     dword ptr [rax+rax+00h]
0x180020000  mov     [rsi+70h], rax
0x180020004  test    rax, rax
0x180020007  jnz     short loc_18001FFCE
0x180020009  mov     ecx, 8007000Eh; int
0x18002000e  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180020014  xor     ebx, ebx
0x180020016  jmp     loc_18001FF3A
0x18002001b  mov     r8, [rsi+60h]
0x18002001f  mov     rdx, rbx
0x180020022  lea     rcx, [rsi+50h]
0x180020026  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18002002b  test    rbx, rbx
0x18002002e  jz      short loc_18001FFC9
0x180020030  jmp     loc_18001FF95
0x180020035  lock inc dword ptr [rbx+8]
0x180020039  jmp     loc_18001FECD
0x18002003e  cmp     rdx, 8
0x180020042  jb      short loc_1800200B9
0x180020044  mov     rax, [rsi+50h]
0x180020048  sub     rdi, rax
0x18002004b  sar     rdi, 1
0x18002004e  mov     r9, rbx
0x180020051  mov     r8, rdi
0x180020054  lea     rdx, [rsi+50h]
0x180020058  lea     rcx, [rsi+50h]; void *
0x18002005c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180020061  jmp     loc_18001FFC9
0x180020066  cmp     rdx, 8
0x18002006a  jb      short loc_1800200CC
0x18002006c  mov     rcx, [rsi+50h]
0x180020070  mov     qword ptr [rsi+60h], 0
0x180020078  xor     eax, eax
0x18002007a  mov     [rcx], ax
0x18002007d  jmp     loc_18001FFC9
0x180020082  lea     rcx, [rsp+78h+var_58]
0x180020087  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002008c  mov     eax, ebx
0x18002008e  jmp     loc_18001FE9B
0x180020093  mov     rax, [r14]
0x180020096  mov     rcx, r14
0x180020099  mov     rax, [rax+8]
0x18002009d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200a2  jmp     loc_18001FEFE
0x1800200a7  lea     rax, [rsi+50h]
0x1800200ab  jmp     loc_18001FF4C
0x1800200b0  lea     rcx, [rsi+50h]
0x1800200b4  jmp     loc_18001FF5F
0x1800200b9  lea     rax, [rsi+50h]
0x1800200bd  jmp     short loc_180020048
0x1800200bf  lea     rcx, aStringTooLong; "string too long"
0x1800200c6  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800200cc  lea     rcx, [rsi+50h]
0x1800200d0  jmp     short loc_180020070
0x1800200d2  lea     rcx, [rsi+50h]
0x1800200d6  jmp     loc_18001FFA4
0x1800200db  lea     rcx, [rsi+50h]
0x1800200df  jmp     loc_18001FFBF
```
