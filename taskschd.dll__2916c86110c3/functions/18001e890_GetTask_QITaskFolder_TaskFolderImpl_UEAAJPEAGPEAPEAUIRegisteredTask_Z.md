# ?GetTask@?QITaskFolder@@TaskFolderImpl@@UEAAJPEAGPEAPEAUIRegisteredTask@@@Z

- ea: `0x18001e890`
- end: `0x18001ed9b`
- name: `?GetTask@?QITaskFolder@@TaskFolderImpl@@UEAAJPEAGPEAPEAUIRegisteredTask@@@Z`
- size: `1291`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x180009a30`
- `0x18001e240`
- `0x18001e890`
- `0x18001f070`
- `0x18001f540`
- `0x18001fa40`
- `0x18001fb70`
- `0x18001fd3c`
- `0x180036290`
- `0x180039524`
- `0x18003b51c`
- `0x180048cb0`
- `0x18004e90f`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ea29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001eae6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001eccc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ea29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001eae6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001eccc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ead8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ecbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ead8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ecbe`
- `OLEAUT32!__imp_SysAllocString` at `0x18001eb6f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001eb6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001eb66`
- `OLEAUT32!__imp_SysFreeString` at `0x18001eca3`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ed6d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001eb66`
- `OLEAUT32!__imp_SysFreeString` at `0x18001eca3`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ed6d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ecdc`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ed51`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ecdc`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ed51`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall _GetTask__QITaskFolder__TaskFolderImpl__UEAAJPEAGPEAPEAUIRegisteredTask___Z(
        __int64 a1,
        const unsigned __int16 *a2,
        struct ITask **a3)
{
  const unsigned __int16 *v4; // rbx
  unsigned __int16 *v7; // rax
  __int64 v8; // r9
  unsigned __int16 v9; // dx
  __int64 v10; // rcx
  unsigned __int16 *i; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  unsigned __int16 *p_Src; // r8
  unsigned __int16 v15; // r10
  unsigned __int16 *v16; // rcx
  unsigned __int16 *v17; // rcx
  int XmlLegacy; // edi
  void *v19; // rbx
  HANDLE ProcessHeap; // rax
  RpcSession *v21; // rcx
  const OLECHAR *v22; // r14
  BSTR v23; // rbx
  __int64 v24; // r15
  struct IUnknown *v25; // rdx
  OLECHAR *v26; // rcx
  BSTR v27; // rax
  __int64 v28; // rdx
  unsigned __int16 *j; // rax
  const unsigned __int16 *v30; // rcx
  unsigned __int16 *v31; // r8
  unsigned __int16 v32; // ax
  unsigned __int16 *v33; // rdx
  void *v34; // rbx
  HANDLE v35; // rax
  UINT v36; // eax
  _WORD *v37; // rax
  const unsigned __int16 *v38; // rbx
  UINT v39; // eax
  struct ITask *v40; // [rsp+38h] [rbp-2B0h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-2A8h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-2A0h] BYREF
  unsigned int v43; // [rsp+50h] [rbp-298h] BYREF
  void **pExceptionObject; // [rsp+58h] [rbp-290h] BYREF
  char v45; // [rsp+60h] [rbp-288h]
  __int64 *v46; // [rsp+68h] [rbp-280h]
  __int64 v47; // [rsp+70h] [rbp-278h]
  __int64 v48; // [rsp+78h] [rbp-270h]
  int v49; // [rsp+80h] [rbp-268h]
  __int64 v50; // [rsp+84h] [rbp-264h]
  unsigned __int16 Src; // [rsp+90h] [rbp-258h] BYREF
  char v52; // [rsp+92h] [rbp-256h] BYREF
  _BYTE v54[6]; // [rsp+29Ah] [rbp-4Eh] BYREF

  v4 = a2;
  if ( !a2 )
    return 2147942487LL;
  if ( a3 )
  {
    memset_0(&Src, 0, 0x20Au);
    v7 = *(unsigned __int16 **)(a1 + 112);
    if ( v7 && &Src != v4 )
    {
      if ( *v7 && &Src != v7 )
      {
        v8 = 2147483646;
        v12 = 2147483646;
        v13 = 261;
        p_Src = &Src;
        do
        {
          if ( !v12 )
            break;
          v15 = *v7;
          if ( !*v7 )
            break;
          ++v7;
          *p_Src++ = v15;
          --v12;
          --v13;
        }
        while ( v13 );
        v16 = p_Src - 1;
        if ( v13 )
          v16 = p_Src;
        *v16 = 0;
        if ( !v13 )
          return 2147942487LL;
      }
      else
      {
        v8 = 2147483646;
      }
      v9 = *v4;
      if ( !*v4 )
        goto LABEL_26;
      v10 = 261;
      for ( i = &Src; *i; ++i )
      {
        if ( !--v10 )
          return 2147942487LL;
      }
      if ( *(_WORD *)&v54[-2 * v10] == 92 )
      {
        if ( v9 == 92 )
          ++v4;
      }
      else if ( v9 != 92 )
      {
        v28 = 261;
        for ( j = &Src; *j; ++j )
        {
          if ( !--v28 )
            return 2147942487LL;
        }
        v30 = L"\\";
        v31 = (unsigned __int16 *)&v54[-2 * v28];
        do
        {
          if ( !v8 )
            break;
          v32 = *v30;
          if ( !*v30 )
            break;
          ++v30;
          *v31++ = v32;
          --v8;
          --v28;
        }
        while ( v28 );
        v17 = v31 - 1;
        if ( v28 )
          v17 = v31;
        *v17 = 0;
        if ( !v28 )
          return 2147942487LL;
      }
      if ( (int)StringCchCatW(&Src, 0x105u, v4) >= 0 )
      {
LABEL_26:
        lpMem = 0;
        v43 = 0;
        if ( !*(_DWORD *)(a1 + 80) )
        {
          XmlLegacy = -2147023645;
LABEL_28:
          v19 = lpMem;
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v19);
          return (unsigned int)XmlLegacy;
        }
        v21 = *(RpcSession **)(a1 + 88);
        if ( v21 )
        {
          XmlLegacy = RpcSession::RetrieveTask(v21, &Src, &::Src, &v43, (struct RpcString *)&lpMem);
          if ( XmlLegacy < 0 )
            goto LABEL_28;
          goto LABEL_31;
        }
        v33 = (unsigned __int16 *)&v52;
        if ( Src != 92 )
          v33 = &Src;
        v40 = 0;
        XmlLegacy = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, GUID *, struct ITask **))(**(_QWORD **)(a1 + 96) + 48LL))(
                      *(_QWORD *)(a1 + 96),
                      v33,
                      &GUID_148bd524_a2ab_11ce_b11f_00aa00530503,
                      &v40);
        if ( XmlLegacy >= 0 )
        {
          bstrString = 0;
          XmlLegacy = UniSession::GenerateXmlLegacy(v40, (struct ATL::CComBSTR *)&bstrString);
          if ( XmlLegacy >= 0 )
          {
            v34 = lpMem;
            v35 = GetProcessHeap();
            HeapFree(v35, 0, v34);
            lpMem = 0;
            v36 = SysStringLen(bstrString);
            v37 = MIDL_user_allocate(2LL * (v36 + 1));
            lpMem = v37;
            if ( !v37 )
            {
              v45 = 0;
              v46 = &qword_180077320;
              v47 = 0;
              v48 = 0;
              v49 = 14;
              v50 = -1;
              pExceptionObject = &wmi::GenericException::`vftable';
              throw (wmi::OutOfMemoryException *)&pExceptionObject;
            }
            *v37 = 0;
            v38 = bstrString;
            v39 = SysStringLen(bstrString);
            StringCchCopyW((unsigned __int16 *)lpMem, v39 + 1, v38);
            SysFreeString(bstrString);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v40);
LABEL_31:
            v22 = (const OLECHAR *)lpMem;
            v40 = 0;
            bstrString = 0;
            XmlLegacy = ATL::CComObject<RegisteredTaskImpl>::CreateInstance(&bstrString);
            if ( XmlLegacy >= 0 )
            {
              v23 = bstrString;
              XmlLegacy = (**(__int64 (__fastcall ***)(BSTR, GUID *, struct ITask **))bstrString)(
                            bstrString,
                            &GUID_9c86f320_dee3_4dd1_b972_a303f26b061e,
                            &v40);
              if ( XmlLegacy >= 0 )
              {
                *((_DWORD *)v23 + 32) = *(_DWORD *)(a1 + 80);
                *((_DWORD *)v23 + 33) = *(_DWORD *)(a1 + 84);
                v24 = *(_QWORD *)(a1 + 88);
                if ( v24 )
                  _InterlockedIncrement((volatile signed __int32 *)(v24 + 8));
                wmi::AutoRef<RpcFolderSnapshot>::Release(v23 + 68);
                *((_QWORD *)v23 + 17) = v24;
                v25 = *(struct IUnknown **)(a1 + 96);
                if ( *((struct IUnknown **)v23 + 18) != v25 )
                  ATL::AtlComPtrAssign((struct IUnknown **)v23 + 18, v25);
                std::wstring::assign(v23 + 40, &Src);
                if ( v22 )
                {
                  v26 = (OLECHAR *)*((_QWORD *)v23 + 14);
                  if ( v22 != v26 )
                  {
                    SysFreeString(v26);
                    v27 = SysAllocString(v22);
                    *((_QWORD *)v23 + 14) = v27;
                    if ( !v27 )
                      ATL::PrivateAtlThrow(-2147024882);
                  }
                }
                *a3 = v40;
              }
              else if ( v40 )
              {
                ((void (__fastcall *)(struct ITask *))v40->lpVtbl->Release)(v40);
              }
              goto LABEL_28;
            }
            goto LABEL_63;
          }
          SysFreeString(bstrString);
        }
LABEL_63:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v40);
        goto LABEL_28;
      }
    }
    return 2147942487LL;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18001e890  push    rbx
0x18001e892  push    rsi
0x18001e893  push    rdi
0x18001e894  push    r12
0x18001e896  push    r13
0x18001e898  push    r14
0x18001e89a  push    r15
0x18001e89c  sub     rsp, 2B0h
0x18001e8a3  mov     rax, cs:__security_cookie
0x18001e8aa  xor     rax, rsp
0x18001e8ad  mov     [rsp+2E8h+var_48], rax
0x18001e8b5  mov     r13, r8
0x18001e8b8  mov     rbx, rdx
0x18001e8bb  mov     rsi, rcx
0x18001e8be  test    rdx, rdx
0x18001e8c1  jnz     short loc_18001E8EB
0x18001e8c3  mov     eax, 80070057h
0x18001e8c8  mov     rcx, [rsp+2E8h+var_48]
0x18001e8d0  xor     rcx, rsp; StackCookie
0x18001e8d3  call    __security_check_cookie
0x18001e8d8  add     rsp, 2B0h
0x18001e8df  pop     r15
0x18001e8e1  pop     r14
0x18001e8e3  pop     r13
0x18001e8e5  pop     r12
0x18001e8e7  pop     rdi
0x18001e8e8  pop     rsi
0x18001e8e9  pop     rbx
0x18001e8ea  retn
0x18001e8eb  test    r13, r13
0x18001e8ee  jz      loc_18001EC36
0x18001e8f4  xor     r15d, r15d
0x18001e8f7  mov     [rsp+2E8h+var_2B8], r15d
0x18001e8fc  xor     edx, edx; Val
0x18001e8fe  mov     r8d, 20Ah; Size
0x18001e904  lea     rcx, [rsp+2E8h+Src]; void *
0x18001e90c  call    memset_0
0x18001e911  mov     rax, [rsi+70h]
0x18001e915  test    rax, rax
0x18001e918  jz      short loc_18001E974
0x18001e91a  lea     rcx, [rsp+2E8h+Src]
0x18001e922  cmp     rcx, rbx
0x18001e925  jz      short loc_18001E974
0x18001e927  cmp     [rax], r15w
0x18001e92b  jz      short loc_18001E93A
0x18001e92d  lea     rcx, [rsp+2E8h+Src]
0x18001e935  cmp     rcx, rax
0x18001e938  jnz     short loc_18001E97E
0x18001e93a  mov     r9d, 7FFFFFFEh
0x18001e940  movzx   edx, word ptr [rbx]
0x18001e943  test    dx, dx
0x18001e946  jz      loc_18001E9FD
0x18001e94c  mov     ecx, 105h
0x18001e951  lea     rax, [rsp+2E8h+Src]
0x18001e959  nop     dword ptr [rax+00000000h]
0x18001e960  cmp     word ptr [rax], 0
0x18001e964  jz      loc_18001EB8F
0x18001e96a  add     rax, 2
0x18001e96e  sub     rcx, 1
0x18001e972  jnz     short loc_18001E960
0x18001e974  mov     eax, 80070057h
0x18001e979  jmp     loc_18001E8C8
0x18001e97e  mov     r9d, 7FFFFFFEh
0x18001e984  mov     ecx, r9d
0x18001e987  mov     edx, 105h
0x18001e98c  lea     r8, [rsp+2E8h+Src]
0x18001e994  test    rcx, rcx
0x18001e997  jz      short loc_18001E9B8
0x18001e999  movzx   r10d, word ptr [rax]
0x18001e99d  test    r10w, r10w
0x18001e9a1  jz      short loc_18001E9B8
0x18001e9a3  add     rax, 2
0x18001e9a7  mov     [r8], r10w
0x18001e9ab  add     r8, 2
0x18001e9af  dec     rcx
0x18001e9b2  sub     rdx, 1
0x18001e9b6  jnz     short loc_18001E994
0x18001e9b8  lea     rcx, [r8-2]
0x18001e9bc  test    rdx, rdx
0x18001e9bf  cmovnz  rcx, r8
0x18001e9c3  mov     [rcx], r15w
0x18001e9c7  jnz     loc_18001E940
0x18001e9cd  jmp     short loc_18001E974
0x18001e9cf  lea     rcx, [r8-2]
0x18001e9d3  test    rdx, rdx
0x18001e9d6  cmovnz  rcx, r8
0x18001e9da  mov     [rcx], r15w
0x18001e9de  jz      short loc_18001E974
0x18001e9e0  mov     r8, rbx; unsigned __int16 *
0x18001e9e3  mov     edx, 105h; unsigned __int64
0x18001e9e8  lea     rcx, [rsp+2E8h+Src]; unsigned __int16 *
0x18001e9f0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001e9f5  test    eax, eax
0x18001e9f7  js      loc_18001E974
0x18001e9fd  mov     [rsp+2E8h+lpMem], r15
0x18001ea02  mov     [rsp+2E8h+var_298], r15d
0x18001ea07  cmp     dword ptr [rsi+50h], 0
0x18001ea0b  jnz     short loc_18001EA36
0x18001ea0d  mov     edi, 800704E3h
0x18001ea12  mov     [rsp+2E8h+var_2B8], edi
0x18001ea16  mov     rbx, [rsp+2E8h+lpMem]
0x18001ea1b  call    cs:__imp_GetProcessHeap
0x18001ea21  mov     r8, rbx; lpMem
0x18001ea24  xor     edx, edx; dwFlags
0x18001ea26  mov     rcx, rax; hHeap
0x18001ea29  call    cs:__imp_HeapFree
0x18001ea2f  mov     eax, edi
0x18001ea31  jmp     loc_18001E8C8
0x18001ea36  mov     rcx, [rsi+58h]; this
0x18001ea3a  test    rcx, rcx
0x18001ea3d  jz      loc_18001EC40
0x18001ea43  lea     rax, [rsp+2E8h+lpMem]
0x18001ea48  mov     [rsp+2E8h+var_2C8], rax; struct RpcString *
0x18001ea4d  lea     r9, [rsp+2E8h+var_298]; unsigned int *
0x18001ea52  lea     r8, Src; unsigned __int16 *
0x18001ea59  lea     rdx, [rsp+2E8h+Src]; unsigned __int16 *
0x18001ea61  call    ?RetrieveTask@RpcSession@@QEBAJPEBG0PEAKAEAVRpcString@@@Z; RpcSession::RetrieveTask(ushort const *,ushort const *,ulong *,RpcString &)
0x18001ea66  mov     edi, eax
0x18001ea68  mov     [rsp+2E8h+var_2B8], eax
0x18001ea6c  test    eax, eax
0x18001ea6e  js      short loc_18001EA16
0x18001ea70  mov     r14, [rsp+2E8h+lpMem]
0x18001ea75  mov     [rsp+2E8h+var_2B0], r15
0x18001ea7a  mov     [rsp+2E8h+bstrString], r15
0x18001ea7f  lea     rcx, [rsp+2E8h+bstrString]
0x18001ea84  call    ?CreateInstance@?$CComObject@VRegisteredTaskImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<RegisteredTaskImpl>::CreateInstance(ATL::CComObject<RegisteredTaskImpl> * *)
0x18001ea89  mov     edi, eax
0x18001ea8b  test    eax, eax
0x18001ea8d  js      loc_18001ED83
0x18001ea93  mov     rbx, [rsp+2E8h+bstrString]
0x18001ea98  mov     rax, [rbx]
0x18001ea9b  lea     r8, [rsp+2E8h+var_2B0]
0x18001eaa0  lea     rdx, _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e
0x18001eaa7  mov     rcx, rbx
0x18001eaaa  mov     rax, [rax]
0x18001eaad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eab2  mov     edi, eax
0x18001eab4  test    eax, eax
0x18001eab6  jns     short loc_18001EAF4
0x18001eab8  mov     rcx, [rsp+2E8h+var_2B0]
0x18001eabd  test    rcx, rcx
0x18001eac0  jz      short loc_18001EACF
0x18001eac2  mov     rax, [rcx]
0x18001eac5  mov     rax, [rax+10h]
0x18001eac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eace  nop
0x18001eacf  mov     [rsp+2E8h+var_2B8], edi
0x18001ead3  mov     rbx, [rsp+2E8h+lpMem]
0x18001ead8  call    cs:__imp_GetProcessHeap
0x18001eade  mov     r8, rbx; lpMem
0x18001eae1  xor     edx, edx; dwFlags
0x18001eae3  mov     rcx, rax; hHeap
0x18001eae6  call    cs:__imp_HeapFree
0x18001eaec  nop
0x18001eaed  mov     eax, edi
0x18001eaef  jmp     loc_18001E8C8
0x18001eaf4  mov     eax, [rsi+50h]
0x18001eaf7  mov     [rbx+80h], eax
0x18001eafd  mov     eax, [rsi+54h]
0x18001eb00  mov     [rbx+84h], eax
0x18001eb06  mov     r15, [rsi+58h]
0x18001eb0a  test    r15, r15
0x18001eb0d  jnz     short loc_18001EB88
0x18001eb0f  lea     rcx, [rbx+88h]
0x18001eb16  call    ?Release@?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAXXZ; wmi::AutoRef<RpcFolderSnapshot>::Release(void)
0x18001eb1b  mov     [rbx+88h], r15
0x18001eb22  lea     rcx, [rbx+90h]; struct IUnknown **
0x18001eb29  mov     rdx, [rsi+60h]; struct IUnknown *
0x18001eb2d  cmp     [rcx], rdx
0x18001eb30  jnz     short loc_18001EB56
0x18001eb32  lea     rcx, [rbx+50h]; void *
0x18001eb36  lea     rdx, [rsp+2E8h+Src]; Src
0x18001eb3e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001eb43  test    r14, r14
0x18001eb46  jnz     short loc_18001EB5D
0x18001eb48  mov     rax, [rsp+2E8h+var_2B0]
0x18001eb4d  mov     [r13+0], rax
0x18001eb51  jmp     loc_18001EACF
0x18001eb56  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001eb5b  jmp     short loc_18001EB32
0x18001eb5d  mov     rcx, [rbx+70h]; bstrString
0x18001eb61  cmp     r14, rcx
0x18001eb64  jz      short loc_18001EB48
0x18001eb66  call    cs:__imp_SysFreeString
0x18001eb6c  mov     rcx, r14; psz
0x18001eb6f  call    cs:__imp_SysAllocString
0x18001eb75  mov     [rbx+70h], rax
0x18001eb79  test    rax, rax
0x18001eb7c  jnz     short loc_18001EB48
0x18001eb7e  mov     ecx, 8007000Eh; int
0x18001eb83  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18001eb88  lock inc dword ptr [r15+8]
0x18001eb8d  jmp     short loc_18001EB0F
0x18001eb8f  lea     rax, [rcx+rcx]
0x18001eb93  lea     rcx, [rsp+2E8h+var_50]
0x18001eb9b  sub     rcx, rax
0x18001eb9e  cmp     word ptr [rcx], 5Ch ; '\'
0x18001eba2  jz      short loc_18001EBD5
0x18001eba4  cmp     dx, 5Ch ; '\'
0x18001eba8  jz      loc_18001E9E0
0x18001ebae  mov     edx, 105h
0x18001ebb3  lea     rax, [rsp+2E8h+Src]
0x18001ebbb  nop     dword ptr [rax+rax+00h]
0x18001ebc0  cmp     word ptr [rax], 0
0x18001ebc4  jz      short loc_18001EBE8
0x18001ebc6  add     rax, 2
0x18001ebca  sub     rdx, 1
0x18001ebce  jnz     short loc_18001EBC0
0x18001ebd0  jmp     loc_18001E974
0x18001ebd5  cmp     dx, 5Ch ; '\'
0x18001ebd9  jnz     loc_18001E9E0
0x18001ebdf  add     rbx, 2
0x18001ebe3  jmp     loc_18001E9E0
0x18001ebe8  lea     rcx, asc_180077260; "\\"
0x18001ebef  lea     rax, [rdx+rdx]
0x18001ebf3  lea     r8, [rsp+2E8h+var_4E]
0x18001ebfb  sub     r8, rax
0x18001ebfe  test    rdx, rdx
0x18001ec01  jz      loc_18001E9CF
0x18001ec07  test    r9, r9
0x18001ec0a  jz      loc_18001E9CF
0x18001ec10  movzx   eax, word ptr [rcx]
0x18001ec13  test    ax, ax
0x18001ec16  jz      loc_18001E9CF
0x18001ec1c  add     rcx, 2
0x18001ec20  mov     [r8], ax
0x18001ec24  add     r8, 2
0x18001ec28  dec     r9
0x18001ec2b  sub     rdx, 1
0x18001ec2f  jnz     short loc_18001EC07
0x18001ec31  jmp     loc_18001E9CF
0x18001ec36  mov     eax, 80004003h
0x18001ec3b  jmp     loc_18001E8C8
0x18001ec40  lea     rdx, [rsp+2E8h+var_256]
0x18001ec48  lea     rax, [rsp+2E8h+Src]
0x18001ec50  cmp     [rsp+2E8h+Src], 5Ch ; '\'
0x18001ec59  cmovnz  rdx, rax
0x18001ec5d  mov     [rsp+2E8h+var_2B0], r15
0x18001ec62  mov     rcx, [rsi+60h]
0x18001ec66  mov     rax, [rcx]
0x18001ec69  lea     r9, [rsp+2E8h+var_2B0]
0x18001ec6e  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x18001ec75  mov     rax, [rax+30h]
0x18001ec79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec7e  mov     edi, eax
0x18001ec80  test    eax, eax
0x18001ec82  js      short loc_18001ECAA
0x18001ec84  mov     [rsp+2E8h+bstrString], r15
0x18001ec89  lea     rdx, [rsp+2E8h+bstrString]; struct ATL::CComBSTR *
0x18001ec8e  mov     rcx, [rsp+2E8h+var_2B0]; struct ITask *
0x18001ec93  call    ?GenerateXmlLegacy@UniSession@@CAJPEAUITask@@AEAVCComBSTR@ATL@@@Z; UniSession::GenerateXmlLegacy(ITask *,ATL::CComBSTR &)
0x18001ec98  mov     edi, eax
0x18001ec9a  test    eax, eax
0x18001ec9c  jns     short loc_18001ECB9
0x18001ec9e  mov     rcx, [rsp+2E8h+bstrString]; bstrString
0x18001eca3  call    cs:__imp_SysFreeString
0x18001eca9  nop
0x18001ecaa  lea     rcx, [rsp+2E8h+var_2B0]
0x18001ecaf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ecb4  jmp     loc_18001EA12
0x18001ecb9  mov     rbx, [rsp+2E8h+lpMem]
0x18001ecbe  call    cs:__imp_GetProcessHeap
0x18001ecc4  mov     r8, rbx; lpMem
0x18001ecc7  xor     edx, edx; dwFlags
0x18001ecc9  mov     rcx, rax; hHeap
0x18001eccc  call    cs:__imp_HeapFree
0x18001ecd2  mov     [rsp+2E8h+lpMem], r15
0x18001ecd7  mov     rcx, [rsp+2E8h+bstrString]; pbstr
0x18001ecdc  call    cs:__imp_SysStringLen
0x18001ece2  lea     ecx, [rax+1]
0x18001ece5  add     rcx, rcx; size
0x18001ece8  call    MIDL_user_allocate
0x18001eced  mov     [rsp+2E8h+lpMem], rax
0x18001ecf2  test    rax, rax
0x18001ecf5  jnz     short loc_18001ED45
0x18001ecf7  mov     [rsp+2E8h+var_288], al
0x18001ecfb  lea     rax, qword_180077320
0x18001ed02  mov     [rsp+2E8h+var_280], rax
0x18001ed07  mov     [rsp+2E8h+var_278], r15
0x18001ed0c  mov     [rsp+2E8h+var_270], r15
0x18001ed11  mov     [rsp+2E8h+var_268], 0Eh
0x18001ed1c  mov     [rsp+2E8h+var_264], 0FFFFFFFFFFFFFFFFh
0x18001ed28  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001ed2f  mov     [rsp+2E8h+pExceptionObject], rax
0x18001ed34  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001ed3b  lea     rcx, [rsp+2E8h+pExceptionObject]; pExceptionObject
0x18001ed40  call    _CxxThrowException_0
0x18001ed45  mov     [rax], r15w
0x18001ed49  mov     rbx, [rsp+2E8h+bstrString]
0x18001ed4e  mov     rcx, rbx; pbstr
0x18001ed51  call    cs:__imp_SysStringLen
0x18001ed57  lea     edx, [rax+1]; unsigned __int64
0x18001ed5a  mov     r8, rbx; unsigned __int16 *
0x18001ed5d  mov     rcx, [rsp+2E8h+lpMem]; unsigned __int16 *
0x18001ed62  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ed67  nop
0x18001ed68  mov     rcx, [rsp+2E8h+bstrString]; bstrString
0x18001ed6d  call    cs:__imp_SysFreeString
0x18001ed73  nop
0x18001ed74  lea     rcx, [rsp+2E8h+var_2B0]
  ... truncated ...
```
