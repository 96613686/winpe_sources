# ?GetTask@?QITaskFolder@@TaskFolderImpl@@UEAAJPEAGPEAPEAUIRegisteredTask@@@Z

- ea: `0x18001f8c0`
- end: `0x18001fe18`
- name: `?GetTask@?QITaskFolder@@TaskFolderImpl@@UEAAJPEAGPEAPEAUIRegisteredTask@@@Z`
- size: `1368`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x18000a100`
- `0x18001f240`
- `0x18001f8c0`
- `0x1800200f0`
- `0x1800205c0`
- `0x180020ad0`
- `0x180020c10`
- `0x180020ddc`
- `0x1800391c0`
- `0x18003c664`
- `0x18003e88c`
- `0x18004c7d8`
- `0x18005260b`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fa5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fb28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fd31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fa5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fb28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fd31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fa4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fb14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fa4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fb14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd1d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001fbc1`
- `OLEAUT32!__imp_SysAllocString` at `0x18001fbc1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fbb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fcfc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fde4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fbb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fcfc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fde4`
- `OLEAUT32!__imp_SysStringLen` at `0x18001fd47`
- `OLEAUT32!__imp_SysStringLen` at `0x18001fdc2`
- `OLEAUT32!__imp_SysStringLen` at `0x18001fd47`
- `OLEAUT32!__imp_SysStringLen` at `0x18001fdc2`

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
              v46 = &qword_18007B2F0;
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
0x18001f8c0  push    rbx
0x18001f8c2  push    rsi
0x18001f8c3  push    rdi
0x18001f8c4  push    r12
0x18001f8c6  push    r13
0x18001f8c8  push    r14
0x18001f8ca  push    r15
0x18001f8cc  sub     rsp, 2B0h
0x18001f8d3  mov     rax, cs:__security_cookie
0x18001f8da  xor     rax, rsp
0x18001f8dd  mov     [rsp+2E8h+var_48], rax
0x18001f8e5  mov     r13, r8
0x18001f8e8  mov     rbx, rdx
0x18001f8eb  mov     rsi, rcx
0x18001f8ee  test    rdx, rdx
0x18001f8f1  jnz     short loc_18001F91C
0x18001f8f3  mov     eax, 80070057h
0x18001f8f8  mov     rcx, [rsp+2E8h+var_48]
0x18001f900  xor     rcx, rsp; StackCookie
0x18001f903  call    __security_check_cookie
0x18001f908  add     rsp, 2B0h
0x18001f90f  pop     r15
0x18001f911  pop     r14
0x18001f913  pop     r13
0x18001f915  pop     r12
0x18001f917  pop     rdi
0x18001f918  pop     rsi
0x18001f919  pop     rbx
0x18001f91a  retn
0x18001f91c  test    r13, r13
0x18001f91f  jz      loc_18001FC8F
0x18001f925  xor     r15d, r15d
0x18001f928  mov     [rsp+2E8h+var_2B8], r15d
0x18001f92d  xor     edx, edx; Val
0x18001f92f  mov     r8d, 20Ah; Size
0x18001f935  lea     rcx, [rsp+2E8h+Src]; void *
0x18001f93d  call    memset_0
0x18001f942  mov     rax, [rsi+70h]
0x18001f946  test    rax, rax
0x18001f949  jz      short loc_18001F9A4
0x18001f94b  lea     rcx, [rsp+2E8h+Src]
0x18001f953  cmp     rcx, rbx
0x18001f956  jz      short loc_18001F9A4
0x18001f958  cmp     [rax], r15w
0x18001f95c  jz      short loc_18001F96B
0x18001f95e  lea     rcx, [rsp+2E8h+Src]
0x18001f966  cmp     rcx, rax
0x18001f969  jnz     short loc_18001F9AE
0x18001f96b  mov     r9d, 7FFFFFFEh
0x18001f971  movzx   edx, word ptr [rbx]
0x18001f974  test    dx, dx
0x18001f977  jz      loc_18001FA2D
0x18001f97d  mov     ecx, 105h
0x18001f982  lea     rax, [rsp+2E8h+Src]
0x18001f98a  nop     word ptr [rax+rax+00h]
0x18001f990  cmp     word ptr [rax], 0
0x18001f994  jz      loc_18001FBEA
0x18001f99a  add     rax, 2
0x18001f99e  sub     rcx, 1
0x18001f9a2  jnz     short loc_18001F990
0x18001f9a4  mov     eax, 80070057h
0x18001f9a9  jmp     loc_18001F8F8
0x18001f9ae  mov     r9d, 7FFFFFFEh
0x18001f9b4  mov     ecx, r9d
0x18001f9b7  mov     edx, 105h
0x18001f9bc  lea     r8, [rsp+2E8h+Src]
0x18001f9c4  test    rcx, rcx
0x18001f9c7  jz      short loc_18001F9E8
0x18001f9c9  movzx   r10d, word ptr [rax]
0x18001f9cd  test    r10w, r10w
0x18001f9d1  jz      short loc_18001F9E8
0x18001f9d3  add     rax, 2
0x18001f9d7  mov     [r8], r10w
0x18001f9db  add     r8, 2
0x18001f9df  dec     rcx
0x18001f9e2  sub     rdx, 1
0x18001f9e6  jnz     short loc_18001F9C4
0x18001f9e8  lea     rcx, [r8-2]
0x18001f9ec  test    rdx, rdx
0x18001f9ef  cmovnz  rcx, r8
0x18001f9f3  mov     [rcx], r15w
0x18001f9f7  jnz     loc_18001F971
0x18001f9fd  jmp     short loc_18001F9A4
0x18001f9ff  lea     rcx, [r8-2]
0x18001fa03  test    rdx, rdx
0x18001fa06  cmovnz  rcx, r8
0x18001fa0a  mov     [rcx], r15w
0x18001fa0e  jz      short loc_18001F9A4
0x18001fa10  mov     r8, rbx; unsigned __int16 *
0x18001fa13  mov     edx, 105h; unsigned __int64
0x18001fa18  lea     rcx, [rsp+2E8h+Src]; unsigned __int16 *
0x18001fa20  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001fa25  test    eax, eax
0x18001fa27  js      loc_18001F9A4
0x18001fa2d  mov     [rsp+2E8h+lpMem], r15
0x18001fa32  mov     [rsp+2E8h+var_298], r15d
0x18001fa37  cmp     dword ptr [rsi+50h], 0
0x18001fa3b  jnz     short loc_18001FA72
0x18001fa3d  mov     edi, 800704E3h
0x18001fa42  mov     [rsp+2E8h+var_2B8], edi
0x18001fa46  mov     rbx, [rsp+2E8h+lpMem]
0x18001fa4b  call    cs:__imp_GetProcessHeap
0x18001fa52  nop     dword ptr [rax+rax+00h]
0x18001fa57  mov     r8, rbx; lpMem
0x18001fa5a  xor     edx, edx; dwFlags
0x18001fa5c  mov     rcx, rax; hHeap
0x18001fa5f  call    cs:__imp_HeapFree
0x18001fa66  nop     dword ptr [rax+rax+00h]
0x18001fa6b  mov     eax, edi
0x18001fa6d  jmp     loc_18001F8F8
0x18001fa72  mov     rcx, [rsi+58h]; this
0x18001fa76  test    rcx, rcx
0x18001fa79  jz      loc_18001FC99
0x18001fa7f  lea     rax, [rsp+2E8h+lpMem]
0x18001fa84  mov     [rsp+2E8h+var_2C8], rax; struct RpcString *
0x18001fa89  lea     r9, [rsp+2E8h+var_298]; unsigned int *
0x18001fa8e  lea     r8, Src; unsigned __int16 *
0x18001fa95  lea     rdx, [rsp+2E8h+Src]; unsigned __int16 *
0x18001fa9d  call    ?RetrieveTask@RpcSession@@QEBAJPEBG0PEAKAEAVRpcString@@@Z; RpcSession::RetrieveTask(ushort const *,ushort const *,ulong *,RpcString &)
0x18001faa2  mov     edi, eax
0x18001faa4  mov     [rsp+2E8h+var_2B8], eax
0x18001faa8  test    eax, eax
0x18001faaa  js      short loc_18001FA46
0x18001faac  mov     r14, [rsp+2E8h+lpMem]
0x18001fab1  mov     [rsp+2E8h+var_2B0], r15
0x18001fab6  mov     [rsp+2E8h+bstrString], r15
0x18001fabb  lea     rcx, [rsp+2E8h+bstrString]
0x18001fac0  call    ?CreateInstance@?$CComObject@VRegisteredTaskImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<RegisteredTaskImpl>::CreateInstance(ATL::CComObject<RegisteredTaskImpl> * *)
0x18001fac5  mov     edi, eax
0x18001fac7  test    eax, eax
0x18001fac9  js      loc_18001FE00
0x18001facf  mov     rbx, [rsp+2E8h+bstrString]
0x18001fad4  mov     rax, [rbx]
0x18001fad7  lea     r8, [rsp+2E8h+var_2B0]
0x18001fadc  lea     rdx, _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e
0x18001fae3  mov     rcx, rbx
0x18001fae6  mov     rax, [rax]
0x18001fae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001faee  mov     edi, eax
0x18001faf0  test    eax, eax
0x18001faf2  jns     short loc_18001FB3C
0x18001faf4  mov     rcx, [rsp+2E8h+var_2B0]
0x18001faf9  test    rcx, rcx
0x18001fafc  jz      short loc_18001FB0B
0x18001fafe  mov     rax, [rcx]
0x18001fb01  mov     rax, [rax+10h]
0x18001fb05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb0a  nop
0x18001fb0b  mov     [rsp+2E8h+var_2B8], edi
0x18001fb0f  mov     rbx, [rsp+2E8h+lpMem]
0x18001fb14  call    cs:__imp_GetProcessHeap
0x18001fb1b  nop     dword ptr [rax+rax+00h]
0x18001fb20  mov     r8, rbx; lpMem
0x18001fb23  xor     edx, edx; dwFlags
0x18001fb25  mov     rcx, rax; hHeap
0x18001fb28  call    cs:__imp_HeapFree
0x18001fb2f  nop     dword ptr [rax+rax+00h]
0x18001fb34  nop
0x18001fb35  mov     eax, edi
0x18001fb37  jmp     loc_18001F8F8
0x18001fb3c  mov     eax, [rsi+50h]
0x18001fb3f  mov     [rbx+80h], eax
0x18001fb45  mov     eax, [rsi+54h]
0x18001fb48  mov     [rbx+84h], eax
0x18001fb4e  mov     r15, [rsi+58h]
0x18001fb52  test    r15, r15
0x18001fb55  jnz     loc_18001FBE0
0x18001fb5b  lea     rcx, [rbx+88h]
0x18001fb62  call    ?Release@?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAXXZ; wmi::AutoRef<RpcFolderSnapshot>::Release(void)
0x18001fb67  mov     [rbx+88h], r15
0x18001fb6e  lea     rcx, [rbx+90h]; struct IUnknown **
0x18001fb75  mov     rdx, [rsi+60h]; struct IUnknown *
0x18001fb79  cmp     [rcx], rdx
0x18001fb7c  jnz     short loc_18001FBA2
0x18001fb7e  lea     rcx, [rbx+50h]; void *
0x18001fb82  lea     rdx, [rsp+2E8h+Src]; Src
0x18001fb8a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001fb8f  test    r14, r14
0x18001fb92  jnz     short loc_18001FBA9
0x18001fb94  mov     rax, [rsp+2E8h+var_2B0]
0x18001fb99  mov     [r13+0], rax
0x18001fb9d  jmp     loc_18001FB0B
0x18001fba2  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001fba7  jmp     short loc_18001FB7E
0x18001fba9  mov     rcx, [rbx+70h]; bstrString
0x18001fbad  cmp     r14, rcx
0x18001fbb0  jz      short loc_18001FB94
0x18001fbb2  call    cs:__imp_SysFreeString
0x18001fbb9  nop     dword ptr [rax+rax+00h]
0x18001fbbe  mov     rcx, r14; psz
0x18001fbc1  call    cs:__imp_SysAllocString
0x18001fbc8  nop     dword ptr [rax+rax+00h]
0x18001fbcd  mov     [rbx+70h], rax
0x18001fbd1  test    rax, rax
0x18001fbd4  jnz     short loc_18001FB94
0x18001fbd6  mov     ecx, 8007000Eh; int
0x18001fbdb  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18001fbe0  lock inc dword ptr [r15+8]
0x18001fbe5  jmp     loc_18001FB5B
0x18001fbea  lea     rax, [rcx+rcx]
0x18001fbee  lea     rcx, [rsp+2E8h+var_50]
0x18001fbf6  sub     rcx, rax
0x18001fbf9  cmp     word ptr [rcx], 5Ch ; '\'
0x18001fbfd  jz      short loc_18001FC2B
0x18001fbff  cmp     dx, 5Ch ; '\'
0x18001fc03  jz      loc_18001FA10
0x18001fc09  mov     edx, 105h
0x18001fc0e  lea     rax, [rsp+2E8h+Src]
0x18001fc16  cmp     word ptr [rax], 0
0x18001fc1a  jz      short loc_18001FC3E
0x18001fc1c  add     rax, 2
0x18001fc20  sub     rdx, 1
0x18001fc24  jnz     short loc_18001FC16
0x18001fc26  jmp     loc_18001F9A4
0x18001fc2b  cmp     dx, 5Ch ; '\'
0x18001fc2f  jnz     loc_18001FA10
0x18001fc35  add     rbx, 2
0x18001fc39  jmp     loc_18001FA10
0x18001fc3e  lea     rcx, asc_18007B230; "\\"
0x18001fc45  lea     rax, [rdx+rdx]
0x18001fc49  lea     r8, [rsp+2E8h+var_4E]
0x18001fc51  sub     r8, rax
0x18001fc54  test    rdx, rdx
0x18001fc57  jz      loc_18001F9FF
0x18001fc5d  nop     dword ptr [rax]
0x18001fc60  test    r9, r9
0x18001fc63  jz      loc_18001F9FF
0x18001fc69  movzx   eax, word ptr [rcx]
0x18001fc6c  test    ax, ax
0x18001fc6f  jz      loc_18001F9FF
0x18001fc75  add     rcx, 2
0x18001fc79  mov     [r8], ax
0x18001fc7d  add     r8, 2
0x18001fc81  dec     r9
0x18001fc84  sub     rdx, 1
0x18001fc88  jnz     short loc_18001FC60
0x18001fc8a  jmp     loc_18001F9FF
0x18001fc8f  mov     eax, 80004003h
0x18001fc94  jmp     loc_18001F8F8
0x18001fc99  lea     rdx, [rsp+2E8h+var_256]
0x18001fca1  lea     rax, [rsp+2E8h+Src]
0x18001fca9  cmp     [rsp+2E8h+Src], 5Ch ; '\'
0x18001fcb2  cmovnz  rdx, rax
0x18001fcb6  mov     [rsp+2E8h+var_2B0], r15
0x18001fcbb  mov     rcx, [rsi+60h]
0x18001fcbf  mov     rax, [rcx]
0x18001fcc2  lea     r9, [rsp+2E8h+var_2B0]
0x18001fcc7  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x18001fcce  mov     rax, [rax+30h]
0x18001fcd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcd7  mov     edi, eax
0x18001fcd9  test    eax, eax
0x18001fcdb  js      short loc_18001FD09
0x18001fcdd  mov     [rsp+2E8h+bstrString], r15
0x18001fce2  lea     rdx, [rsp+2E8h+bstrString]; struct ATL::CComBSTR *
0x18001fce7  mov     rcx, [rsp+2E8h+var_2B0]; struct ITask *
0x18001fcec  call    ?GenerateXmlLegacy@UniSession@@CAJPEAUITask@@AEAVCComBSTR@ATL@@@Z; UniSession::GenerateXmlLegacy(ITask *,ATL::CComBSTR &)
0x18001fcf1  mov     edi, eax
0x18001fcf3  test    eax, eax
0x18001fcf5  jns     short loc_18001FD18
0x18001fcf7  mov     rcx, [rsp+2E8h+bstrString]; bstrString
0x18001fcfc  call    cs:__imp_SysFreeString
0x18001fd03  nop     dword ptr [rax+rax+00h]
0x18001fd08  nop
0x18001fd09  lea     rcx, [rsp+2E8h+var_2B0]
0x18001fd0e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001fd13  jmp     loc_18001FA42
0x18001fd18  mov     rbx, [rsp+2E8h+lpMem]
0x18001fd1d  call    cs:__imp_GetProcessHeap
0x18001fd24  nop     dword ptr [rax+rax+00h]
0x18001fd29  mov     r8, rbx; lpMem
0x18001fd2c  xor     edx, edx; dwFlags
0x18001fd2e  mov     rcx, rax; hHeap
0x18001fd31  call    cs:__imp_HeapFree
0x18001fd38  nop     dword ptr [rax+rax+00h]
0x18001fd3d  mov     [rsp+2E8h+lpMem], r15
0x18001fd42  mov     rcx, [rsp+2E8h+bstrString]; pbstr
0x18001fd47  call    cs:__imp_SysStringLen
0x18001fd4e  nop     dword ptr [rax+rax+00h]
0x18001fd53  lea     ecx, [rax+1]
0x18001fd56  add     rcx, rcx; size
0x18001fd59  call    MIDL_user_allocate
0x18001fd5e  mov     [rsp+2E8h+lpMem], rax
0x18001fd63  test    rax, rax
0x18001fd66  jnz     short loc_18001FDB6
0x18001fd68  mov     [rsp+2E8h+var_288], al
0x18001fd6c  lea     rax, qword_18007B2F0
0x18001fd73  mov     [rsp+2E8h+var_280], rax
0x18001fd78  mov     [rsp+2E8h+var_278], r15
0x18001fd7d  mov     [rsp+2E8h+var_270], r15
0x18001fd82  mov     [rsp+2E8h+var_268], 0Eh
0x18001fd8d  mov     [rsp+2E8h+var_264], 0FFFFFFFFFFFFFFFFh
0x18001fd99  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001fda0  mov     [rsp+2E8h+pExceptionObject], rax
0x18001fda5  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001fdac  lea     rcx, [rsp+2E8h+pExceptionObject]; pExceptionObject
0x18001fdb1  call    _CxxThrowException_0
0x18001fdb6  mov     [rax], r15w
0x18001fdba  mov     rbx, [rsp+2E8h+bstrString]
0x18001fdbf  mov     rcx, rbx; pbstr
  ... truncated ...
```
