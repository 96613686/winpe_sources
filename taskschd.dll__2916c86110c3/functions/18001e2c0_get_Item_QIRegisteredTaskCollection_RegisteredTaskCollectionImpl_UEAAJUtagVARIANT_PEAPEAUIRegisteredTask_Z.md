# ?get_Item@?QIRegisteredTaskCollection@@RegisteredTaskCollectionImpl@@UEAAJUtagVARIANT@@PEAPEAUIRegisteredTask@@@Z

- ea: `0x18001e2c0`
- end: `0x18001e813`
- name: `?get_Item@?QIRegisteredTaskCollection@@RegisteredTaskCollectionImpl@@UEAAJUtagVARIANT@@PEAPEAUIRegisteredTask@@@Z`
- size: `1363`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x18000dd10`
- `0x18001e18c`
- `0x18001e240`
- `0x18001e2c0`
- `0x18001edb0`
- `0x18001f070`
- `0x18001f540`
- `0x18001fb70`
- `0x18001fc20`
- `0x18003b51c`
- `0x18004e90f`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001e2f8`
- `OLEAUT32!__imp_VariantInit` at `0x18001e2f8`
- `OLEAUT32!__imp_VariantClear` at `0x18001e419`
- `OLEAUT32!__imp_VariantClear` at `0x18001e4bf`
- `OLEAUT32!__imp_VariantClear` at `0x18001e4ec`
- `OLEAUT32!__imp_VariantClear` at `0x18001e5ef`
- `OLEAUT32!__imp_VariantClear` at `0x18001e74c`
- `OLEAUT32!__imp_VariantClear` at `0x18001e75e`
- `OLEAUT32!__imp_VariantClear` at `0x18001e773`
- `OLEAUT32!__imp_VariantClear` at `0x18001e419`
- `OLEAUT32!__imp_VariantClear` at `0x18001e4bf`
- `OLEAUT32!__imp_VariantClear` at `0x18001e4ec`
- `OLEAUT32!__imp_VariantClear` at `0x18001e5ef`
- `OLEAUT32!__imp_VariantClear` at `0x18001e74c`
- `OLEAUT32!__imp_VariantClear` at `0x18001e75e`
- `OLEAUT32!__imp_VariantClear` at `0x18001e773`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001e310`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001e733`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001e310`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001e733`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall _get_Item__QIRegisteredTaskCollection__RegisteredTaskCollectionImpl__UEAAJUtagVARIANT__PEAPEAUIRegisteredTask___Z(
        __int64 a1,
        const VARIANTARG *a2,
        struct IRegisteredTask **a3)
{
  HRESULT NewObject; // ebx
  LONG lVal; // edi
  __int64 v8; // rbx
  int v9; // ecx
  unsigned int v10; // eax
  int v11; // ecx
  unsigned int v12; // eax
  __int64 v13; // rdi
  unsigned __int16 *v14; // r10
  unsigned __int16 *v15; // r8
  unsigned __int16 v16; // dx
  __int64 v17; // rcx
  unsigned __int16 *v18; // rax
  unsigned __int16 *v20; // rax
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v22; // rax
  const unsigned __int16 *bstrVal; // rbx
  unsigned __int16 *v24; // rdx
  _QWORD *v25; // r8
  __int64 *v26; // r8
  __int64 *v27; // rax
  __int64 *i; // rcx
  __int64 *v29; // rdx
  __int64 v30; // rcx
  unsigned __int16 *v31; // rax
  __int64 v32; // rdx
  const unsigned __int16 *v33; // r8
  unsigned __int16 *v34; // r9
  unsigned __int16 v35; // ax
  const unsigned __int16 *v36; // [rsp+20h] [rbp-4D8h]
  struct IRegisteredTask *v37; // [rsp+38h] [rbp-4C0h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-4B8h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-4A0h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-498h] BYREF
  char v41; // [rsp+68h] [rbp-490h]
  __int64 *v42; // [rsp+70h] [rbp-488h]
  __int64 v43; // [rsp+78h] [rbp-480h]
  __int64 v44; // [rsp+80h] [rbp-478h]
  __int64 v45; // [rsp+88h] [rbp-470h]
  int v46; // [rsp+90h] [rbp-468h]
  unsigned __int16 Src[260]; // [rsp+A0h] [rbp-458h] BYREF
  _BYTE v48[2]; // [rsp+2A8h] [rbp-250h]
  unsigned __int16 v50[264]; // [rsp+2B0h] [rbp-248h] BYREF

  if ( !a3 )
    return 2147500035LL;
  VariantInit(&pvarg);
  NewObject = VariantChangeType(&pvarg, a2, 0, 3u);
  if ( NewObject < 0 )
  {
    NewObject = VariantChangeType(&pvarg, a2, 0, 8u);
    if ( NewObject < 0 )
    {
      VariantClear(&pvarg);
      return (unsigned int)NewObject;
    }
  }
  if ( pvarg.vt == 3 )
  {
    lVal = pvarg.lVal;
    if ( pvarg.lVal >= 1 )
    {
      v8 = *(_QWORD *)(a1 + 120);
      v9 = *(_DWORD *)(v8 + 16);
      if ( v9 )
        v10 = v9 == 1 ? *(_DWORD *)(*(_QWORD *)(v8 + 24) + 8LL) : *(_DWORD *)(v8 + 40);
      else
        v10 = 0;
      if ( pvarg.lVal <= v10 )
      {
        memset_0(Src, 0, 0x20Au);
        v11 = *(_DWORD *)(v8 + 16);
        if ( !v11
          || (v11 != 1 ? (v12 = *(_DWORD *)(v8 + 40)) : (v12 = *(_DWORD *)(*(_QWORD *)(v8 + 24) + 8LL)),
              v13 = (unsigned int)(lVal - 1),
              (unsigned int)v13 >= v12) )
        {
LABEL_13:
          v14 = 0;
          goto LABEL_14;
        }
        if ( v11 == 1 )
        {
          v22 = *(_QWORD *)(v8 + 24);
          if ( (unsigned int)v13 >= *(_DWORD *)(v22 + 8) )
          {
            v41 = 0;
            pExceptionObject = &wmi::GenericException::`vftable';
            v42 = &qword_180077320;
            v43 = 0;
            v44 = 0;
            v45 = -2147024809;
            v46 = -1;
            throw (wmi::GenericException *)&pExceptionObject;
          }
          _mm_lfence();
          v14 = *(unsigned __int16 **)(*(_QWORD *)v22 + 8 * v13);
LABEL_14:
          v15 = (unsigned __int16 *)(a1 + 64);
          if ( *(_QWORD *)(a1 + 88) >= 8u )
            v15 = *(unsigned __int16 **)v15;
          if ( !v15 || Src == v14 || *v15 && Src != v15 && (int)StringCchCopyW(Src, 0x105u, v15) < 0 )
            goto LABEL_25;
          if ( v14 )
          {
            v16 = *v14;
            if ( *v14 )
            {
              v17 = 261;
              v18 = Src;
              while ( *v18 )
              {
                ++v18;
                if ( !--v17 )
                  goto LABEL_25;
              }
              if ( *(_WORD *)&v48[-2 * v17] == 92 )
              {
                if ( v16 == 92 )
                  ++v14;
              }
              else if ( v16 != 92 )
              {
                v30 = 261;
                v31 = Src;
                while ( *v31 )
                {
                  ++v31;
                  if ( !--v30 )
                    goto LABEL_25;
                }
                v32 = 2147483646;
                v33 = L"\\";
                v34 = v50 - v30 + 2;
                do
                {
                  if ( !v32 )
                    break;
                  v35 = *v33;
                  if ( !*v33 )
                    break;
                  ++v33;
                  *v34++ = v35;
                  --v32;
                  --v30;
                }
                while ( v30 );
                v20 = v34 - 1;
                if ( v30 )
                  v20 = v34;
                *v20 = 0;
                if ( !v30 )
                  goto LABEL_25;
              }
              if ( (int)StringCchCatW(Src, 0x105u, v14) < 0 )
              {
LABEL_25:
                VariantClear(&pvarg);
                return 2147549183LL;
              }
            }
          }
          v37 = 0;
          v39 = 0;
          NewObject = ATL::CComObject<RegisteredTaskImpl>::CreateInstance(&v39);
          if ( NewObject < 0 )
          {
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v37);
          }
          else
          {
            v21 = v39;
            NewObject = (**v39)(v39, &GUID_9c86f320_dee3_4dd1_b972_a303f26b061e, (__int64 *)&v37);
            if ( NewObject >= 0 )
            {
              UniSession::operator=(v21 + 16, a1 + 96);
              std::wstring::assign(v21 + 10, Src);
              *a3 = v37;
            }
            else if ( v37 )
            {
              ((void (__fastcall *)(struct IRegisteredTask *))v37->lpVtbl->Release)(v37);
            }
          }
LABEL_35:
          VariantClear(&pvarg);
          return (unsigned int)NewObject;
        }
        v26 = *(__int64 **)(v8 + 32);
        v27 = (__int64 *)*v26;
        while ( 1 )
        {
          do
          {
            if ( v27 == v26 )
              goto LABEL_13;
            if ( !(_DWORD)v13 )
            {
              v14 = (unsigned __int16 *)v27[4];
              goto LABEL_14;
            }
            LODWORD(v13) = v13 - 1;
          }
          while ( *((_BYTE *)v27 + 25) );
          i = (__int64 *)v27[2];
          if ( *((_BYTE *)i + 25) )
          {
            for ( i = (__int64 *)v27[1]; !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
            {
              if ( v27 != (__int64 *)i[2] )
                break;
              v27 = i;
            }
LABEL_62:
            v27 = i;
          }
          else
          {
            v29 = (__int64 *)*i;
            if ( *(_BYTE *)(*i + 25) )
              goto LABEL_62;
            do
            {
              v27 = v29;
              v29 = (__int64 *)*v29;
            }
            while ( !*((_BYTE *)v29 + 25) );
          }
        }
      }
    }
  }
  else
  {
    if ( pvarg.vt != 8 )
      goto LABEL_35;
    bstrVal = pvarg.bstrVal;
    if ( pvarg.llVal )
    {
      memset_0(v50, 0, 0x20Au);
      v25 = (_QWORD *)(a1 + 64);
      if ( *(_QWORD *)(a1 + 88) >= 8u )
        v25 = (_QWORD *)*v25;
      if ( (int)tsched::SafePathAppend((tsched *)v50, v24, (unsigned int)v25, bstrVal, v36) >= 0 )
      {
        if ( !RpcFolderSnapshot::Exists(*(RpcFolderSnapshot **)(a1 + 120), pvarg.bstrVal) )
        {
          VariantClear(&pvarg);
          return 2147942403LL;
        }
        NewObject = RegisteredTaskImpl::CreateNewObject((const struct UniSession *)(a1 + 96), v50, 0, a3);
        goto LABEL_35;
      }
    }
  }
  VariantClear(&pvarg);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001e2c0  push    rbx
0x18001e2c2  push    rsi
0x18001e2c3  push    rdi
0x18001e2c4  push    r14
0x18001e2c6  push    r15
0x18001e2c8  sub     rsp, 4D0h
0x18001e2cf  mov     rax, cs:__security_cookie
0x18001e2d6  xor     rax, rsp
0x18001e2d9  mov     [rsp+4F8h+var_38], rax
0x18001e2e1  mov     r15, r8
0x18001e2e4  mov     rdi, rdx
0x18001e2e7  mov     r14, rcx
0x18001e2ea  test    r8, r8
0x18001e2ed  jz      loc_18001E429
0x18001e2f3  lea     rcx, [rsp+4F8h+pvarg]; pvarg
0x18001e2f8  call    cs:__imp_VariantInit
0x18001e2fe  nop
0x18001e2ff  mov     r9d, 3; vt
0x18001e305  xor     r8d, r8d; wFlags
0x18001e308  mov     rdx, rdi; pvarSrc
0x18001e30b  lea     rcx, [rsp+4F8h+pvarg]; pvargDest
0x18001e310  call    cs:__imp_VariantChangeType
0x18001e316  mov     ebx, eax
0x18001e318  mov     [rsp+4F8h+var_4C8], eax
0x18001e31c  test    eax, eax
0x18001e31e  js      loc_18001E722
0x18001e324  movzx   eax, word ptr [rsp+4F8h+pvarg]
0x18001e329  cmp     eax, 3
0x18001e32c  jnz     loc_18001E582
0x18001e332  mov     rdi, qword ptr [rsp+4F8h+pvarg+8]
0x18001e337  cmp     edi, 1
0x18001e33a  jl      loc_18001E4E7
0x18001e340  mov     rbx, [r14+78h]
0x18001e344  mov     ecx, [rbx+10h]
0x18001e347  xor     esi, esi
0x18001e349  test    ecx, ecx
0x18001e34b  jz      loc_18001E573
0x18001e351  cmp     ecx, 1
0x18001e354  jnz     loc_18001E56B
0x18001e35a  mov     rax, [rbx+18h]
0x18001e35e  mov     eax, [rax+8]
0x18001e361  cmp     edi, eax
0x18001e363  ja      loc_18001E4E7
0x18001e369  xor     edx, edx; Val
0x18001e36b  mov     r8d, 20Ah; Size
0x18001e371  lea     rcx, [rsp+4F8h+Src]; void *
0x18001e379  call    memset_0
0x18001e37e  mov     ecx, [rbx+10h]
0x18001e381  mov     eax, ecx
0x18001e383  test    ecx, ecx
0x18001e385  jz      short loc_18001E3A5
0x18001e387  cmp     eax, 1
0x18001e38a  jnz     loc_18001E57A
0x18001e390  mov     rax, [rbx+18h]
0x18001e394  mov     eax, [rax+8]
0x18001e397  dec     edi
0x18001e399  cmp     edi, eax
0x18001e39b  jnb     short loc_18001E3A5
0x18001e39d  test    ecx, ecx
0x18001e39f  jnz     loc_18001E4F9
0x18001e3a5  mov     r10, rsi
0x18001e3a8  lea     r8, [r14+40h]
0x18001e3ac  cmp     qword ptr [r8+18h], 8
0x18001e3b1  jb      short loc_18001E3B6
0x18001e3b3  mov     r8, [r8]; unsigned __int16 *
0x18001e3b6  test    r8, r8
0x18001e3b9  jz      short loc_18001E414
0x18001e3bb  lea     rax, [rsp+4F8h+Src]
0x18001e3c3  cmp     rax, r10
0x18001e3c6  jz      short loc_18001E414
0x18001e3c8  cmp     word ptr [r8], 0
0x18001e3cd  jz      short loc_18001E3E0
0x18001e3cf  lea     rax, [rsp+4F8h+Src]
0x18001e3d7  cmp     rax, r8
0x18001e3da  jnz     loc_18001E54C
0x18001e3e0  test    r10, r10
0x18001e3e3  jz      short loc_18001E45C
0x18001e3e5  movzx   edx, word ptr [r10]
0x18001e3e9  test    dx, dx
0x18001e3ec  jz      short loc_18001E45C
0x18001e3ee  mov     ecx, 105h
0x18001e3f3  lea     rax, [rsp+4F8h+Src]
0x18001e3fb  nop     dword ptr [rax+rax+00h]
0x18001e400  cmp     word ptr [rax], 0
0x18001e404  jz      loc_18001E67A
0x18001e40a  add     rax, 2
0x18001e40e  sub     rcx, 1
0x18001e412  jnz     short loc_18001E400
0x18001e414  lea     rcx, [rsp+4F8h+pvarg]; pvarg
0x18001e419  call    cs:__imp_VariantClear
0x18001e41f  mov     eax, 8000FFFFh
0x18001e424  jmp     loc_18001E4C8
0x18001e429  mov     eax, 80004003h
0x18001e42e  jmp     loc_18001E4C8
0x18001e433  lea     rax, [r9-2]
0x18001e437  test    rcx, rcx
0x18001e43a  cmovnz  rax, r9
0x18001e43e  mov     [rax], si
0x18001e441  jz      short loc_18001E414
0x18001e443  mov     r8, r10; unsigned __int16 *
0x18001e446  mov     edx, 105h; unsigned __int64
0x18001e44b  lea     rcx, [rsp+4F8h+Src]; unsigned __int16 *
0x18001e453  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001e458  test    eax, eax
0x18001e45a  js      short loc_18001E414
0x18001e45c  mov     [rsp+4F8h+var_4C0], rsi
0x18001e461  mov     [rsp+4F8h+var_4A0], rsi
0x18001e466  lea     rcx, [rsp+4F8h+var_4A0]
0x18001e46b  call    ?CreateInstance@?$CComObject@VRegisteredTaskImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<RegisteredTaskImpl>::CreateInstance(ATL::CComObject<RegisteredTaskImpl> * *)
0x18001e470  mov     ebx, eax
0x18001e472  test    eax, eax
0x18001e474  js      loc_18001E7FB
0x18001e47a  mov     rdi, [rsp+4F8h+var_4A0]
0x18001e47f  mov     rax, [rdi]
0x18001e482  lea     r8, [rsp+4F8h+var_4C0]
0x18001e487  lea     rdx, _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e
0x18001e48e  mov     rcx, rdi
0x18001e491  mov     rax, [rax]
0x18001e494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e499  mov     ebx, eax
0x18001e49b  test    eax, eax
0x18001e49d  jns     short loc_18001E51E
0x18001e49f  mov     rcx, [rsp+4F8h+var_4C0]
0x18001e4a4  test    rcx, rcx
0x18001e4a7  jz      short loc_18001E4B6
0x18001e4a9  mov     rax, [rcx]
0x18001e4ac  mov     rax, [rax+10h]
0x18001e4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4b5  nop
0x18001e4b6  mov     [rsp+4F8h+var_4C8], ebx
0x18001e4ba  lea     rcx, [rsp+4F8h+pvarg]; pvarg
0x18001e4bf  call    cs:__imp_VariantClear
0x18001e4c5  nop
0x18001e4c6  mov     eax, ebx
0x18001e4c8  mov     rcx, [rsp+4F8h+var_38]
0x18001e4d0  xor     rcx, rsp; StackCookie
0x18001e4d3  call    __security_check_cookie
0x18001e4d8  add     rsp, 4D0h
0x18001e4df  pop     r15
0x18001e4e1  pop     r14
0x18001e4e3  pop     rdi
0x18001e4e4  pop     rsi
0x18001e4e5  pop     rbx
0x18001e4e6  retn
0x18001e4e7  lea     rcx, [rsp+4F8h+pvarg]; pvarg
0x18001e4ec  call    cs:__imp_VariantClear
0x18001e4f2  mov     eax, 80070057h
0x18001e4f7  jmp     short loc_18001E4C8
0x18001e4f9  cmp     ecx, 1
0x18001e4fc  jnz     loc_18001E5FF
0x18001e502  mov     rax, [rbx+18h]
0x18001e506  cmp     edi, [rax+8]
0x18001e509  jnb     loc_18001E7A5
0x18001e50f  lfence
0x18001e512  mov     rax, [rax]
0x18001e515  mov     r10, [rax+rdi*8]
0x18001e519  jmp     loc_18001E3A8
0x18001e51e  lea     rdx, [r14+60h]
0x18001e522  lea     rcx, [rdi+80h]
0x18001e529  call    ??4UniSession@@QEAAAEAV0@AEBV0@@Z; UniSession::operator=(UniSession const &)
0x18001e52e  lea     rcx, [rdi+50h]; void *
0x18001e532  lea     rdx, [rsp+4F8h+Src]; Src
0x18001e53a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001e53f  mov     rax, [rsp+4F8h+var_4C0]
0x18001e544  mov     [r15], rax
0x18001e547  jmp     loc_18001E4B6
0x18001e54c  mov     edx, 105h; unsigned __int64
0x18001e551  lea     rcx, [rsp+4F8h+Src]; unsigned __int16 *
0x18001e559  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e55e  test    eax, eax
0x18001e560  jns     loc_18001E3E0
0x18001e566  jmp     loc_18001E414
0x18001e56b  mov     eax, [rbx+28h]
0x18001e56e  jmp     loc_18001E361
0x18001e573  mov     eax, esi
0x18001e575  jmp     loc_18001E361
0x18001e57a  mov     eax, [rbx+28h]
0x18001e57d  jmp     loc_18001E397
0x18001e582  cmp     eax, 8
0x18001e585  jnz     loc_18001E4BA
0x18001e58b  mov     rbx, qword ptr [rsp+4F8h+pvarg+8]
0x18001e590  test    rbx, rbx
0x18001e593  jz      loc_18001E759
0x18001e599  xor     edx, edx; Val
0x18001e59b  mov     r8d, 20Ah; Size
0x18001e5a1  lea     rcx, [rsp+4F8h+var_248]; void *
0x18001e5a9  call    memset_0
0x18001e5ae  lea     r8, [r14+40h]
0x18001e5b2  cmp     qword ptr [r8+18h], 8
0x18001e5b7  jb      short loc_18001E5BC
0x18001e5b9  mov     r8, [r8]; unsigned int
0x18001e5bc  mov     r9, rbx; unsigned __int16 *
0x18001e5bf  lea     rcx, [rsp+4F8h+var_248]; this
0x18001e5c7  call    ?SafePathAppend@tsched@@YAJPEAGKPEBG1@Z; tsched::SafePathAppend(ushort *,ulong,ushort const *,ushort const *)
0x18001e5cc  test    eax, eax
0x18001e5ce  js      loc_18001E76E
0x18001e5d4  mov     rdx, qword ptr [rsp+4F8h+pvarg+8]; unsigned __int16 *
0x18001e5d9  mov     rcx, [r14+78h]; this
0x18001e5dd  call    ?Exists@RpcFolderSnapshot@@QEBA_NPEBG@Z; RpcFolderSnapshot::Exists(ushort const *)
0x18001e5e2  test    al, al
0x18001e5e4  jnz     loc_18001E783
0x18001e5ea  lea     rcx, [rsp+4F8h+pvarg]; pvarg
0x18001e5ef  call    cs:__imp_VariantClear
0x18001e5f5  mov     eax, 80070003h
0x18001e5fa  jmp     loc_18001E4C8
0x18001e5ff  mov     r8, [rbx+20h]
0x18001e603  mov     rax, [r8]
0x18001e606  cmp     rax, r8
0x18001e609  jz      loc_18001E3A5
0x18001e60f  test    edi, edi
0x18001e611  jz      short loc_18001E671
0x18001e613  dec     edi
0x18001e615  cmp     byte ptr [rax+19h], 0
0x18001e619  jnz     short loc_18001E606
0x18001e61b  mov     rcx, [rax+10h]
0x18001e61f  cmp     byte ptr [rcx+19h], 0
0x18001e623  jz      short loc_18001E644
0x18001e625  mov     rcx, [rax+8]
0x18001e629  cmp     byte ptr [rcx+19h], 0
0x18001e62d  jnz     short loc_18001E64D
0x18001e62f  cmp     rax, [rcx+10h]
0x18001e633  jnz     short loc_18001E64D
0x18001e635  mov     rax, rcx
0x18001e638  mov     rcx, [rcx+8]
0x18001e63c  cmp     byte ptr [rcx+19h], 0
0x18001e640  jz      short loc_18001E62F
0x18001e642  jmp     short loc_18001E64D
0x18001e644  mov     rdx, [rcx]
0x18001e647  cmp     byte ptr [rdx+19h], 0
0x18001e64b  jz      short loc_18001E660
0x18001e64d  mov     rax, rcx
0x18001e650  jmp     short loc_18001E606
0x18001e660  mov     rax, rdx
0x18001e663  mov     rcx, [rdx]
0x18001e666  mov     rdx, rcx
0x18001e669  cmp     byte ptr [rcx+19h], 0
0x18001e66d  jz      short loc_18001E660
0x18001e66f  jmp     short loc_18001E606
0x18001e671  mov     r10, [rax+20h]
0x18001e675  jmp     loc_18001E3A8
0x18001e67a  lea     rax, [rcx+rcx]
0x18001e67e  lea     rcx, [rsp+4F8h+var_250]
0x18001e686  sub     rcx, rax
0x18001e689  cmp     word ptr [rcx], 5Ch ; '\'
0x18001e68d  jz      short loc_18001E6BB
0x18001e68f  cmp     dx, 5Ch ; '\'
0x18001e693  jz      loc_18001E443
0x18001e699  mov     ecx, 105h
0x18001e69e  lea     rax, [rsp+4F8h+Src]
0x18001e6a6  cmp     word ptr [rax], 0
0x18001e6aa  jz      short loc_18001E6CE
0x18001e6ac  add     rax, 2
0x18001e6b0  sub     rcx, 1
0x18001e6b4  jnz     short loc_18001E6A6
0x18001e6b6  jmp     loc_18001E414
0x18001e6bb  cmp     dx, 5Ch ; '\'
0x18001e6bf  jnz     loc_18001E443
0x18001e6c5  add     r10, 2
0x18001e6c9  jmp     loc_18001E443
0x18001e6ce  mov     edx, 7FFFFFFEh
0x18001e6d3  lea     r8, asc_180077260; "\\"
0x18001e6da  lea     rax, [rcx+rcx]
0x18001e6de  lea     r9, [rsp+4F8h+var_24E]
0x18001e6e6  sub     r9, rax
0x18001e6e9  test    rcx, rcx
0x18001e6ec  jz      loc_18001E433
0x18001e6f2  test    rdx, rdx
0x18001e6f5  jz      loc_18001E433
0x18001e6fb  movzx   eax, word ptr [r8]
0x18001e6ff  test    ax, ax
0x18001e702  jz      loc_18001E433
0x18001e708  add     r8, 2
0x18001e70c  mov     [r9], ax
0x18001e710  add     r9, 2
0x18001e714  dec     rdx
0x18001e717  sub     rcx, 1
0x18001e71b  jnz     short loc_18001E6F2
0x18001e71d  jmp     loc_18001E433
0x18001e722  mov     r9d, 8; vt
0x18001e728  xor     r8d, r8d; wFlags
0x18001e72b  mov     rdx, rdi; pvarSrc
0x18001e72e  lea     rcx, [rsp+4F8h+pvarg]; pvargDest
0x18001e733  call    cs:__imp_VariantChangeType
0x18001e739  mov     ebx, eax
0x18001e73b  mov     [rsp+4F8h+var_4C8], eax
0x18001e73f  test    eax, eax
0x18001e741  jns     loc_18001E324
0x18001e747  lea     rcx, [rsp+4F8h+pvarg]; pvarg
0x18001e74c  call    cs:__imp_VariantClear
0x18001e752  mov     eax, ebx
0x18001e754  jmp     loc_18001E4C8
0x18001e759  lea     rcx, [rsp+4F8h+pvarg]; pvarg
0x18001e75e  call    cs:__imp_VariantClear
0x18001e764  mov     eax, 80070057h
0x18001e769  jmp     loc_18001E4C8
0x18001e76e  lea     rcx, [rsp+4F8h+pvarg]; pvarg
0x18001e773  call    cs:__imp_VariantClear
0x18001e779  mov     eax, 80070057h
0x18001e77e  jmp     loc_18001E4C8
0x18001e783  lea     rcx, [r14+60h]; struct UniSession *
  ... truncated ...
```
