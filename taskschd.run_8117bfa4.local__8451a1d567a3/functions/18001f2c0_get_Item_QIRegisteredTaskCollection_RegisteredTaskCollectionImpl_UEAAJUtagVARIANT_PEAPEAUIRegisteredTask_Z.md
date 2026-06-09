# ?get_Item@?QIRegisteredTaskCollection@@RegisteredTaskCollectionImpl@@UEAAJUtagVARIANT@@PEAPEAUIRegisteredTask@@@Z

- ea: `0x18001f2c0`
- end: `0x18001f84b`
- name: `?get_Item@?QIRegisteredTaskCollection@@RegisteredTaskCollectionImpl@@UEAAJUtagVARIANT@@PEAPEAUIRegisteredTask@@@Z`
- size: `1419`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x18001f16c`
- `0x18001f240`
- `0x18001f2c0`
- `0x18001fe20`
- `0x1800200f0`
- `0x1800205c0`
- `0x180020c10`
- `0x180020cc0`
- `0x180021f70`
- `0x18003e88c`
- `0x18005260b`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001f2f8`
- `OLEAUT32!__imp_VariantInit` at `0x18001f2f8`
- `OLEAUT32!__imp_VariantClear` at `0x18001f429`
- `OLEAUT32!__imp_VariantClear` at `0x18001f4d9`
- `OLEAUT32!__imp_VariantClear` at `0x18001f50d`
- `OLEAUT32!__imp_VariantClear` at `0x18001f616`
- `OLEAUT32!__imp_VariantClear` at `0x18001f772`
- `OLEAUT32!__imp_VariantClear` at `0x18001f78a`
- `OLEAUT32!__imp_VariantClear` at `0x18001f7a5`
- `OLEAUT32!__imp_VariantClear` at `0x18001f429`
- `OLEAUT32!__imp_VariantClear` at `0x18001f4d9`
- `OLEAUT32!__imp_VariantClear` at `0x18001f50d`
- `OLEAUT32!__imp_VariantClear` at `0x18001f616`
- `OLEAUT32!__imp_VariantClear` at `0x18001f772`
- `OLEAUT32!__imp_VariantClear` at `0x18001f78a`
- `OLEAUT32!__imp_VariantClear` at `0x18001f7a5`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001f316`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001f753`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001f316`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001f753`

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
            v42 = &qword_18007B2F0;
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
0x18001f2c0  push    rbx
0x18001f2c2  push    rsi
0x18001f2c3  push    rdi
0x18001f2c4  push    r14
0x18001f2c6  push    r15
0x18001f2c8  sub     rsp, 4D0h
0x18001f2cf  mov     rax, cs:__security_cookie
0x18001f2d6  xor     rax, rsp
0x18001f2d9  mov     [rsp+4F8h+var_38], rax
0x18001f2e1  mov     r15, r8
0x18001f2e4  mov     rdi, rdx
0x18001f2e7  mov     r14, rcx
0x18001f2ea  test    r8, r8
0x18001f2ed  jz      loc_18001F43F
0x18001f2f3  lea     rcx, [rsp+4F8h+pvarg]; pvarg
0x18001f2f8  call    cs:__imp_VariantInit
0x18001f2ff  nop     dword ptr [rax+rax+00h]
0x18001f304  nop
0x18001f305  mov     r9d, 3; vt
0x18001f30b  xor     r8d, r8d; wFlags
0x18001f30e  mov     rdx, rdi; pvarSrc
0x18001f311  lea     rcx, [rsp+4F8h+pvarg]; pvargDest
0x18001f316  call    cs:__imp_VariantChangeType
0x18001f31d  nop     dword ptr [rax+rax+00h]
0x18001f322  mov     ebx, eax
0x18001f324  mov     [rsp+4F8h+var_4C8], eax
0x18001f328  test    eax, eax
0x18001f32a  js      loc_18001F742
0x18001f330  movzx   eax, word ptr [rsp+4F8h+pvarg]
0x18001f335  cmp     eax, 3
0x18001f338  jnz     loc_18001F5A9
0x18001f33e  mov     rdi, qword ptr [rsp+4F8h+pvarg+8]
0x18001f343  cmp     edi, 1
0x18001f346  jl      loc_18001F508
0x18001f34c  mov     rbx, [r14+78h]
0x18001f350  mov     ecx, [rbx+10h]
0x18001f353  xor     esi, esi
0x18001f355  test    ecx, ecx
0x18001f357  jz      loc_18001F59A
0x18001f35d  cmp     ecx, 1
0x18001f360  jnz     loc_18001F592
0x18001f366  mov     rax, [rbx+18h]
0x18001f36a  mov     eax, [rax+8]
0x18001f36d  cmp     edi, eax
0x18001f36f  ja      loc_18001F508
0x18001f375  xor     edx, edx; Val
0x18001f377  mov     r8d, 20Ah; Size
0x18001f37d  lea     rcx, [rsp+4F8h+Src]; void *
0x18001f385  call    memset_0
0x18001f38a  mov     ecx, [rbx+10h]
0x18001f38d  mov     eax, ecx
0x18001f38f  test    ecx, ecx
0x18001f391  jz      short loc_18001F3B1
0x18001f393  cmp     eax, 1
0x18001f396  jnz     loc_18001F5A1
0x18001f39c  mov     rax, [rbx+18h]
0x18001f3a0  mov     eax, [rax+8]
0x18001f3a3  dec     edi
0x18001f3a5  cmp     edi, eax
0x18001f3a7  jnb     short loc_18001F3B1
0x18001f3a9  test    ecx, ecx
0x18001f3ab  jnz     loc_18001F520
0x18001f3b1  mov     r10, rsi
0x18001f3b4  lea     r8, [r14+40h]
0x18001f3b8  cmp     qword ptr [r8+18h], 8
0x18001f3bd  jb      short loc_18001F3C2
0x18001f3bf  mov     r8, [r8]; unsigned __int16 *
0x18001f3c2  test    r8, r8
0x18001f3c5  jz      short loc_18001F424
0x18001f3c7  lea     rax, [rsp+4F8h+Src]
0x18001f3cf  cmp     rax, r10
0x18001f3d2  jz      short loc_18001F424
0x18001f3d4  cmp     word ptr [r8], 0
0x18001f3d9  jz      short loc_18001F3EC
0x18001f3db  lea     rax, [rsp+4F8h+Src]
0x18001f3e3  cmp     rax, r8
0x18001f3e6  jnz     loc_18001F573
0x18001f3ec  test    r10, r10
0x18001f3ef  jz      loc_18001F472
0x18001f3f5  movzx   edx, word ptr [r10]
0x18001f3f9  test    dx, dx
0x18001f3fc  jz      short loc_18001F472
0x18001f3fe  mov     ecx, 105h
0x18001f403  lea     rax, [rsp+4F8h+Src]
0x18001f40b  nop     dword ptr [rax+rax+00h]
0x18001f410  cmp     word ptr [rax], 0
0x18001f414  jz      loc_18001F69A
0x18001f41a  add     rax, 2
0x18001f41e  sub     rcx, 1
0x18001f422  jnz     short loc_18001F410
0x18001f424  lea     rcx, [rsp+4F8h+pvarg]; pvarg
0x18001f429  call    cs:__imp_VariantClear
0x18001f430  nop     dword ptr [rax+rax+00h]
0x18001f435  mov     eax, 8000FFFFh
0x18001f43a  jmp     loc_18001F4E8
0x18001f43f  mov     eax, 80004003h
0x18001f444  jmp     loc_18001F4E8
0x18001f449  lea     rax, [r9-2]
0x18001f44d  test    rcx, rcx
0x18001f450  cmovnz  rax, r9
0x18001f454  mov     [rax], si
0x18001f457  jz      short loc_18001F424
0x18001f459  mov     r8, r10; unsigned __int16 *
0x18001f45c  mov     edx, 105h; unsigned __int64
0x18001f461  lea     rcx, [rsp+4F8h+Src]; unsigned __int16 *
0x18001f469  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f46e  test    eax, eax
0x18001f470  js      short loc_18001F424
0x18001f472  mov     [rsp+4F8h+var_4C0], rsi
0x18001f477  mov     [rsp+4F8h+var_4A0], rsi
0x18001f47c  lea     rcx, [rsp+4F8h+var_4A0]
0x18001f481  call    ?CreateInstance@?$CComObject@VRegisteredTaskImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<RegisteredTaskImpl>::CreateInstance(ATL::CComObject<RegisteredTaskImpl> * *)
0x18001f486  mov     ebx, eax
0x18001f488  test    eax, eax
0x18001f48a  js      loc_18001F833
0x18001f490  mov     rdi, [rsp+4F8h+var_4A0]
0x18001f495  mov     rax, [rdi]
0x18001f498  lea     r8, [rsp+4F8h+var_4C0]
0x18001f49d  lea     rdx, _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e
0x18001f4a4  mov     rcx, rdi
0x18001f4a7  mov     rax, [rax]
0x18001f4aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4af  mov     ebx, eax
0x18001f4b1  test    eax, eax
0x18001f4b3  jns     loc_18001F545
0x18001f4b9  mov     rcx, [rsp+4F8h+var_4C0]
0x18001f4be  test    rcx, rcx
0x18001f4c1  jz      short loc_18001F4D0
0x18001f4c3  mov     rax, [rcx]
0x18001f4c6  mov     rax, [rax+10h]
0x18001f4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4cf  nop
0x18001f4d0  mov     [rsp+4F8h+var_4C8], ebx
0x18001f4d4  lea     rcx, [rsp+4F8h+pvarg]; pvarg
0x18001f4d9  call    cs:__imp_VariantClear
0x18001f4e0  nop     dword ptr [rax+rax+00h]
0x18001f4e5  nop
0x18001f4e6  mov     eax, ebx
0x18001f4e8  mov     rcx, [rsp+4F8h+var_38]
0x18001f4f0  xor     rcx, rsp; StackCookie
0x18001f4f3  call    __security_check_cookie
0x18001f4f8  add     rsp, 4D0h
0x18001f4ff  pop     r15
0x18001f501  pop     r14
0x18001f503  pop     rdi
0x18001f504  pop     rsi
0x18001f505  pop     rbx
0x18001f506  retn
0x18001f508  lea     rcx, [rsp+4F8h+pvarg]; pvarg
0x18001f50d  call    cs:__imp_VariantClear
0x18001f514  nop     dword ptr [rax+rax+00h]
0x18001f519  mov     eax, 80070057h
0x18001f51e  jmp     short loc_18001F4E8
0x18001f520  cmp     ecx, 1
0x18001f523  jnz     loc_18001F62C
0x18001f529  mov     rax, [rbx+18h]
0x18001f52d  cmp     edi, [rax+8]
0x18001f530  jnb     loc_18001F7DD
0x18001f536  lfence
0x18001f539  mov     rax, [rax]
0x18001f53c  mov     r10, [rax+rdi*8]
0x18001f540  jmp     loc_18001F3B4
0x18001f545  lea     rdx, [r14+60h]
0x18001f549  lea     rcx, [rdi+80h]
0x18001f550  call    ??4UniSession@@QEAAAEAV0@AEBV0@@Z; UniSession::operator=(UniSession const &)
0x18001f555  lea     rcx, [rdi+50h]; void *
0x18001f559  lea     rdx, [rsp+4F8h+Src]; Src
0x18001f561  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001f566  mov     rax, [rsp+4F8h+var_4C0]
0x18001f56b  mov     [r15], rax
0x18001f56e  jmp     loc_18001F4D0
0x18001f573  mov     edx, 105h; unsigned __int64
0x18001f578  lea     rcx, [rsp+4F8h+Src]; unsigned __int16 *
0x18001f580  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f585  test    eax, eax
0x18001f587  jns     loc_18001F3EC
0x18001f58d  jmp     loc_18001F424
0x18001f592  mov     eax, [rbx+28h]
0x18001f595  jmp     loc_18001F36D
0x18001f59a  mov     eax, esi
0x18001f59c  jmp     loc_18001F36D
0x18001f5a1  mov     eax, [rbx+28h]
0x18001f5a4  jmp     loc_18001F3A3
0x18001f5a9  cmp     eax, 8
0x18001f5ac  jnz     loc_18001F4D4
0x18001f5b2  mov     rbx, qword ptr [rsp+4F8h+pvarg+8]
0x18001f5b7  test    rbx, rbx
0x18001f5ba  jz      loc_18001F785
0x18001f5c0  xor     edx, edx; Val
0x18001f5c2  mov     r8d, 20Ah; Size
0x18001f5c8  lea     rcx, [rsp+4F8h+var_248]; void *
0x18001f5d0  call    memset_0
0x18001f5d5  lea     r8, [r14+40h]
0x18001f5d9  cmp     qword ptr [r8+18h], 8
0x18001f5de  jb      short loc_18001F5E3
0x18001f5e0  mov     r8, [r8]; unsigned int
0x18001f5e3  mov     r9, rbx; unsigned __int16 *
0x18001f5e6  lea     rcx, [rsp+4F8h+var_248]; this
0x18001f5ee  call    ?SafePathAppend@tsched@@YAJPEAGKPEBG1@Z; tsched::SafePathAppend(ushort *,ulong,ushort const *,ushort const *)
0x18001f5f3  test    eax, eax
0x18001f5f5  js      loc_18001F7A0
0x18001f5fb  mov     rdx, qword ptr [rsp+4F8h+pvarg+8]; unsigned __int16 *
0x18001f600  mov     rcx, [r14+78h]; this
0x18001f604  call    ?Exists@RpcFolderSnapshot@@QEBA_NPEBG@Z; RpcFolderSnapshot::Exists(ushort const *)
0x18001f609  test    al, al
0x18001f60b  jnz     loc_18001F7BB
0x18001f611  lea     rcx, [rsp+4F8h+pvarg]; pvarg
0x18001f616  call    cs:__imp_VariantClear
0x18001f61d  nop     dword ptr [rax+rax+00h]
0x18001f622  mov     eax, 80070003h
0x18001f627  jmp     loc_18001F4E8
0x18001f62c  mov     r8, [rbx+20h]
0x18001f630  mov     rax, [r8]
0x18001f633  cmp     rax, r8
0x18001f636  jz      loc_18001F3B1
0x18001f63c  test    edi, edi
0x18001f63e  jz      short loc_18001F691
0x18001f640  dec     edi
0x18001f642  cmp     byte ptr [rax+19h], 0
0x18001f646  jnz     short loc_18001F633
0x18001f648  mov     rcx, [rax+10h]
0x18001f64c  cmp     byte ptr [rcx+19h], 0
0x18001f650  jz      short loc_18001F671
0x18001f652  mov     rcx, [rax+8]
0x18001f656  cmp     byte ptr [rcx+19h], 0
0x18001f65a  jnz     short loc_18001F67A
0x18001f65c  cmp     rax, [rcx+10h]
0x18001f660  jnz     short loc_18001F67A
0x18001f662  mov     rax, rcx
0x18001f665  mov     rcx, [rcx+8]
0x18001f669  cmp     byte ptr [rcx+19h], 0
0x18001f66d  jz      short loc_18001F65C
0x18001f66f  jmp     short loc_18001F67A
0x18001f671  mov     rdx, [rcx]
0x18001f674  cmp     byte ptr [rdx+19h], 0
0x18001f678  jz      short loc_18001F680
0x18001f67a  mov     rax, rcx
0x18001f67d  jmp     short loc_18001F633
0x18001f680  mov     rax, rdx
0x18001f683  mov     rcx, [rdx]
0x18001f686  mov     rdx, rcx
0x18001f689  cmp     byte ptr [rcx+19h], 0
0x18001f68d  jz      short loc_18001F680
0x18001f68f  jmp     short loc_18001F633
0x18001f691  mov     r10, [rax+20h]
0x18001f695  jmp     loc_18001F3B4
0x18001f69a  lea     rax, [rcx+rcx]
0x18001f69e  lea     rcx, [rsp+4F8h+var_250]
0x18001f6a6  sub     rcx, rax
0x18001f6a9  cmp     word ptr [rcx], 5Ch ; '\'
0x18001f6ad  jz      short loc_18001F6DB
0x18001f6af  cmp     dx, 5Ch ; '\'
0x18001f6b3  jz      loc_18001F459
0x18001f6b9  mov     ecx, 105h
0x18001f6be  lea     rax, [rsp+4F8h+Src]
0x18001f6c6  cmp     word ptr [rax], 0
0x18001f6ca  jz      short loc_18001F6EE
0x18001f6cc  add     rax, 2
0x18001f6d0  sub     rcx, 1
0x18001f6d4  jnz     short loc_18001F6C6
0x18001f6d6  jmp     loc_18001F424
0x18001f6db  cmp     dx, 5Ch ; '\'
0x18001f6df  jnz     loc_18001F459
0x18001f6e5  add     r10, 2
0x18001f6e9  jmp     loc_18001F459
0x18001f6ee  mov     edx, 7FFFFFFEh
0x18001f6f3  lea     r8, asc_18007B230; "\\"
0x18001f6fa  lea     rax, [rcx+rcx]
0x18001f6fe  lea     r9, [rsp+4F8h+var_24E]
0x18001f706  sub     r9, rax
0x18001f709  test    rcx, rcx
0x18001f70c  jz      loc_18001F449
0x18001f712  test    rdx, rdx
0x18001f715  jz      loc_18001F449
0x18001f71b  movzx   eax, word ptr [r8]
0x18001f71f  test    ax, ax
0x18001f722  jz      loc_18001F449
0x18001f728  add     r8, 2
0x18001f72c  mov     [r9], ax
0x18001f730  add     r9, 2
0x18001f734  dec     rdx
0x18001f737  sub     rcx, 1
0x18001f73b  jnz     short loc_18001F712
0x18001f73d  jmp     loc_18001F449
0x18001f742  mov     r9d, 8; vt
0x18001f748  xor     r8d, r8d; wFlags
0x18001f74b  mov     rdx, rdi; pvarSrc
0x18001f74e  lea     rcx, [rsp+4F8h+pvarg]; pvargDest
0x18001f753  call    cs:__imp_VariantChangeType
0x18001f75a  nop     dword ptr [rax+rax+00h]
0x18001f75f  mov     ebx, eax
0x18001f761  mov     [rsp+4F8h+var_4C8], eax
0x18001f765  test    eax, eax
0x18001f767  jns     loc_18001F330
0x18001f76d  lea     rcx, [rsp+4F8h+pvarg]; pvarg
0x18001f772  call    cs:__imp_VariantClear
0x18001f779  nop     dword ptr [rax+rax+00h]
0x18001f77e  mov     eax, ebx
0x18001f780  jmp     loc_18001F4E8
0x18001f785  lea     rcx, [rsp+4F8h+pvarg]; pvarg
  ... truncated ...
```
