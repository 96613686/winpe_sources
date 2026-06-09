# ?get_Item@?QITaskFolderCollection@@TaskFolderCollectionImpl@@UEAAJUtagVARIANT@@PEAPEAUITaskFolder@@@Z

- ea: `0x180021bb0`
- end: `0x180021f3a`
- name: `?get_Item@?QITaskFolderCollection@@TaskFolderCollectionImpl@@UEAAJUtagVARIANT@@PEAPEAUITaskFolder@@@Z`
- size: `906`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x18000c550`
- `0x18001f16c`
- `0x180021bb0`
- `0x180021f40`
- `0x180021f70`
- `0x18003e88c`
- `0x18005260b`
- `0x180052640`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180021be9`
- `OLEAUT32!__imp_VariantInit` at `0x180021be9`
- `OLEAUT32!__imp_VariantClear` at `0x180021cd1`
- `OLEAUT32!__imp_VariantClear` at `0x180021d10`
- `OLEAUT32!__imp_VariantClear` at `0x180021d46`
- `OLEAUT32!__imp_VariantClear` at `0x180021ded`
- `OLEAUT32!__imp_VariantClear` at `0x180021e1c`
- `OLEAUT32!__imp_VariantClear` at `0x180021e51`
- `OLEAUT32!__imp_VariantClear` at `0x180021e7e`
- `OLEAUT32!__imp_VariantClear` at `0x180021cd1`
- `OLEAUT32!__imp_VariantClear` at `0x180021d10`
- `OLEAUT32!__imp_VariantClear` at `0x180021d46`
- `OLEAUT32!__imp_VariantClear` at `0x180021ded`
- `OLEAUT32!__imp_VariantClear` at `0x180021e1c`
- `OLEAUT32!__imp_VariantClear` at `0x180021e51`
- `OLEAUT32!__imp_VariantClear` at `0x180021e7e`
- `OLEAUT32!__imp_VariantChangeType` at `0x180021c07`
- `OLEAUT32!__imp_VariantChangeType` at `0x180021dce`
- `OLEAUT32!__imp_VariantChangeType` at `0x180021c07`
- `OLEAUT32!__imp_VariantChangeType` at `0x180021dce`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall _get_Item__QITaskFolderCollection__TaskFolderCollectionImpl__UEAAJUtagVARIANT__PEAPEAUITaskFolder___Z(
        __int64 a1,
        const VARIANTARG *a2,
        __int64 a3)
{
  HRESULT NewObject; // ebx
  __int64 v7; // rbx
  unsigned int v8; // eax
  unsigned int v9; // r8d
  __int64 v10; // rdi
  unsigned __int16 *v11; // rdx
  int v12; // ecx
  const unsigned __int16 *v13; // r9
  _QWORD *v14; // r8
  __int64 v16; // rax
  unsigned __int16 **v17; // r8
  unsigned __int16 *v18; // rax
  __int64 i; // rcx
  const unsigned __int16 *bstrVal; // rbx
  unsigned __int16 *v21; // rdx
  _QWORD *v22; // r8
  const unsigned __int16 *v23; // [rsp+20h] [rbp-2A8h]
  VARIANTARG pvarg; // [rsp+38h] [rbp-290h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-278h] BYREF
  char v26; // [rsp+58h] [rbp-270h]
  __int64 *v27; // [rsp+60h] [rbp-268h]
  __int64 v28; // [rsp+68h] [rbp-260h]
  __int64 v29; // [rsp+70h] [rbp-258h]
  __int64 v30; // [rsp+78h] [rbp-250h]
  int v31; // [rsp+80h] [rbp-248h]
  _BYTE v32[528]; // [rsp+90h] [rbp-238h] BYREF

  if ( !a3 )
    return 2147500035LL;
  VariantInit(&pvarg);
  NewObject = VariantChangeType(&pvarg, a2, 0, 3u);
  if ( NewObject < 0 )
  {
    NewObject = VariantChangeType(&pvarg, a2, 0, 8u);
    if ( NewObject < 0 )
      goto LABEL_37;
  }
  if ( pvarg.vt == 3 )
  {
    if ( pvarg.lVal >= 1 )
    {
      v7 = *(_QWORD *)(a1 + 128);
      v8 = RpcFolderSnapshot::Count((RpcFolderSnapshot *)v7);
      if ( v9 <= v8 )
      {
        v10 = v9 - 1;
        memset_0(v32, 0, 0x20Au);
        if ( (unsigned int)v10 >= RpcFolderSnapshot::Count((RpcFolderSnapshot *)v7) || (v12 = *(_DWORD *)(v7 + 16)) == 0 )
        {
LABEL_8:
          v13 = 0;
          goto LABEL_9;
        }
        if ( v12 == 1 )
        {
          v16 = *(_QWORD *)(v7 + 24);
          if ( (unsigned int)v10 >= *(_DWORD *)(v16 + 8) )
          {
            v26 = 0;
            pExceptionObject = &wmi::GenericException::`vftable';
            v27 = &qword_18007B2F0;
            v28 = 0;
            v29 = 0;
            v30 = -2147024809;
            v31 = -1;
            throw (wmi::GenericException *)&pExceptionObject;
          }
          v13 = *(const unsigned __int16 **)(*(_QWORD *)v16 + 8 * v10);
LABEL_9:
          v14 = (_QWORD *)(a1 + 64);
          if ( *(_QWORD *)(a1 + 88) >= 8u )
            v14 = (_QWORD *)*v14;
          NewObject = tsched::SafePathAppend((tsched *)v32, v11, (unsigned int)v14, v13, v23);
          if ( NewObject < 0 )
            goto LABEL_37;
          goto LABEL_12;
        }
        v17 = *(unsigned __int16 ***)(v7 + 32);
        v18 = *v17;
        while ( 1 )
        {
          do
          {
            if ( v18 == (unsigned __int16 *)v17 )
              goto LABEL_8;
            if ( !(_DWORD)v10 )
            {
              v13 = (const unsigned __int16 *)*((_QWORD *)v18 + 4);
              goto LABEL_9;
            }
            LODWORD(v10) = v10 - 1;
          }
          while ( *((_BYTE *)v18 + 25) );
          i = *((_QWORD *)v18 + 2);
          if ( *(_BYTE *)(i + 25) )
          {
            for ( i = *((_QWORD *)v18 + 1);
                  !*(_BYTE *)(i + 25) && v18 == *(unsigned __int16 **)(i + 16);
                  i = *(_QWORD *)(i + 8) )
            {
              v18 = (unsigned __int16 *)i;
            }
LABEL_24:
            v18 = (unsigned __int16 *)i;
          }
          else
          {
            v11 = *(unsigned __int16 **)i;
            if ( *(_BYTE *)(*(_QWORD *)i + 25LL) )
              goto LABEL_24;
            do
            {
              v18 = v11;
              v11 = *(unsigned __int16 **)v11;
            }
            while ( !*((_BYTE *)v11 + 25) );
          }
        }
      }
    }
LABEL_35:
    VariantClear(&pvarg);
    return 2147942487LL;
  }
  if ( pvarg.vt != 8 )
    goto LABEL_37;
  bstrVal = pvarg.bstrVal;
  if ( !pvarg.llVal )
    goto LABEL_35;
  memset_0(v32, 0, 0x20Au);
  v22 = (_QWORD *)(a1 + 64);
  if ( *(_QWORD *)(a1 + 88) >= 8u )
    v22 = (_QWORD *)*v22;
  NewObject = tsched::SafePathAppend((tsched *)v32, v21, (unsigned int)v22, bstrVal, v23);
  if ( NewObject < 0 )
    goto LABEL_37;
  if ( RpcFolderSnapshot::Exists(*(RpcFolderSnapshot **)(a1 + 128), pvarg.bstrVal) )
  {
LABEL_12:
    NewObject = TaskFolderImpl::CreateNewObject(a1 + 120, v32, a3);
LABEL_37:
    VariantClear(&pvarg);
    return (unsigned int)NewObject;
  }
  VariantClear(&pvarg);
  return 2147942403LL;
}

```

## disassembly

```asm
0x180021bb0  mov     [rsp+arg_18], rbx
0x180021bb5  push    rsi
0x180021bb6  push    rdi
0x180021bb7  push    r14
0x180021bb9  sub     rsp, 2B0h
0x180021bc0  mov     rax, cs:__security_cookie
0x180021bc7  xor     rax, rsp
0x180021bca  mov     [rsp+2C8h+var_28], rax
0x180021bd2  mov     r14, r8
0x180021bd5  mov     rdi, rdx
0x180021bd8  mov     rsi, rcx
0x180021bdb  test    r8, r8
0x180021bde  jz      loc_180021CE1
0x180021be4  lea     rcx, [rsp+2C8h+pvarg]; pvarg
0x180021be9  call    cs:__imp_VariantInit
0x180021bf0  nop     dword ptr [rax+rax+00h]
0x180021bf5  nop
0x180021bf6  mov     r9d, 3; vt
0x180021bfc  xor     r8d, r8d; wFlags
0x180021bff  mov     rdx, rdi; pvarSrc
0x180021c02  lea     rcx, [rsp+2C8h+pvarg]; pvargDest
0x180021c07  call    cs:__imp_VariantChangeType
0x180021c0e  nop     dword ptr [rax+rax+00h]
0x180021c13  mov     ebx, eax
0x180021c15  mov     [rsp+2C8h+var_298], eax
0x180021c19  test    eax, eax
0x180021c1b  js      loc_180021DBD
0x180021c21  movzx   eax, word ptr [rsp+2C8h+pvarg]
0x180021c26  cmp     eax, 3
0x180021c29  jnz     loc_180021E00
0x180021c2f  mov     r8, qword ptr [rsp+2C8h+pvarg+8]
0x180021c34  cmp     r8d, 1
0x180021c38  jl      loc_180021D0B
0x180021c3e  mov     rbx, [rsi+80h]
0x180021c45  mov     rcx, rbx; this
0x180021c48  call    ?Count@RpcFolderSnapshot@@QEBAKXZ; RpcFolderSnapshot::Count(void)
0x180021c4d  cmp     r8d, eax
0x180021c50  ja      loc_180021D0B
0x180021c56  lea     edi, [r8-1]
0x180021c5a  xor     edx, edx; Val
0x180021c5c  mov     r8d, 20Ah; Size
0x180021c62  lea     rcx, [rsp+2C8h+var_238]; void *
0x180021c6a  call    memset_0
0x180021c6f  mov     rcx, rbx; this
0x180021c72  call    ?Count@RpcFolderSnapshot@@QEBAKXZ; RpcFolderSnapshot::Count(void)
0x180021c77  cmp     edi, eax
0x180021c79  jnb     short loc_180021C86
0x180021c7b  mov     ecx, [rbx+10h]
0x180021c7e  test    ecx, ecx
0x180021c80  jnz     loc_180021D23
0x180021c86  xor     r9d, r9d; unsigned __int16 *
0x180021c89  lea     r8, [rsi+40h]
0x180021c8d  cmp     qword ptr [r8+18h], 8
0x180021c92  jb      short loc_180021C97
0x180021c94  mov     r8, [r8]; unsigned int
0x180021c97  lea     rcx, [rsp+2C8h+var_238]; this
0x180021c9f  call    ?SafePathAppend@tsched@@YAJPEAGKPEBG1@Z; tsched::SafePathAppend(ushort *,ulong,ushort const *,ushort const *)
0x180021ca4  mov     ebx, eax
0x180021ca6  mov     [rsp+2C8h+var_298], eax
0x180021caa  test    eax, eax
0x180021cac  js      loc_180021D41
0x180021cb2  lea     rcx, [rsi+78h]
0x180021cb6  mov     r8, r14
0x180021cb9  lea     rdx, [rsp+2C8h+var_238]
0x180021cc1  call    ?CreateNewObject@TaskFolderImpl@@SAJAEBV?$AutoRef@VTaskServiceImpl@@@wmi@@PEBGPEAPEAUITaskFolder@@@Z; TaskFolderImpl::CreateNewObject(wmi::AutoRef<TaskServiceImpl> const &,ushort const *,ITaskFolder * *)
0x180021cc6  mov     ebx, eax
0x180021cc8  mov     [rsp+2C8h+var_298], eax
0x180021ccc  lea     rcx, [rsp+2C8h+pvarg]; pvarg
0x180021cd1  call    cs:__imp_VariantClear
0x180021cd8  nop     dword ptr [rax+rax+00h]
0x180021cdd  mov     eax, ebx
0x180021cdf  jmp     short loc_180021CE6
0x180021ce1  mov     eax, 80004003h
0x180021ce6  mov     rcx, [rsp+2C8h+var_28]
0x180021cee  xor     rcx, rsp; StackCookie
0x180021cf1  call    __security_check_cookie
0x180021cf6  mov     rbx, [rsp+2C8h+arg_18]
0x180021cfe  add     rsp, 2B0h
0x180021d05  pop     r14
0x180021d07  pop     rdi
0x180021d08  pop     rsi
0x180021d09  retn
0x180021d0b  lea     rcx, [rsp+2C8h+pvarg]; pvarg
0x180021d10  call    cs:__imp_VariantClear
0x180021d17  nop     dword ptr [rax+rax+00h]
0x180021d1c  mov     eax, 80070057h
0x180021d21  jmp     short loc_180021CE6
0x180021d23  cmp     ecx, 1
0x180021d26  jnz     short loc_180021D56
0x180021d28  mov     rax, [rbx+18h]
0x180021d2c  cmp     edi, [rax+8]
0x180021d2f  jnb     loc_180021EDB
0x180021d35  mov     rax, [rax]
0x180021d38  mov     r9, [rax+rdi*8]
0x180021d3c  jmp     loc_180021C89
0x180021d41  lea     rcx, [rsp+2C8h+pvarg]; pvarg
0x180021d46  call    cs:__imp_VariantClear
0x180021d4d  nop     dword ptr [rax+rax+00h]
0x180021d52  mov     eax, ebx
0x180021d54  jmp     short loc_180021CE6
0x180021d56  mov     r8, [rbx+20h]
0x180021d5a  mov     rax, [r8]
0x180021d5d  cmp     rax, r8
0x180021d60  jz      loc_180021C86
0x180021d66  test    edi, edi
0x180021d68  jz      short loc_180021DB4
0x180021d6a  dec     edi
0x180021d6c  cmp     byte ptr [rax+19h], 0
0x180021d70  jnz     short loc_180021D5D
0x180021d72  mov     rcx, [rax+10h]
0x180021d76  cmp     byte ptr [rcx+19h], 0
0x180021d7a  jz      short loc_180021D8B
0x180021d7c  mov     rcx, [rax+8]
0x180021d80  cmp     byte ptr [rcx+19h], 0
0x180021d84  jz      short loc_180021DA5
0x180021d86  mov     rax, rcx
0x180021d89  jmp     short loc_180021D5D
0x180021d8b  mov     rdx, [rcx]
0x180021d8e  cmp     byte ptr [rdx+19h], 0
0x180021d92  jnz     short loc_180021D86
0x180021d94  mov     rax, rdx
0x180021d97  mov     rcx, [rdx]
0x180021d9a  mov     rdx, rcx
0x180021d9d  cmp     byte ptr [rcx+19h], 0
0x180021da1  jz      short loc_180021D94
0x180021da3  jmp     short loc_180021D5D
0x180021da5  cmp     rax, [rcx+10h]
0x180021da9  jnz     short loc_180021D86
0x180021dab  mov     rax, rcx
0x180021dae  mov     rcx, [rcx+8]
0x180021db2  jmp     short loc_180021D80
0x180021db4  mov     r9, [rax+20h]
0x180021db8  jmp     loc_180021C89
0x180021dbd  mov     r9d, 8; vt
0x180021dc3  xor     r8d, r8d; wFlags
0x180021dc6  mov     rdx, rdi; pvarSrc
0x180021dc9  lea     rcx, [rsp+2C8h+pvarg]; pvargDest
0x180021dce  call    cs:__imp_VariantChangeType
0x180021dd5  nop     dword ptr [rax+rax+00h]
0x180021dda  mov     ebx, eax
0x180021ddc  mov     [rsp+2C8h+var_298], eax
0x180021de0  test    eax, eax
0x180021de2  jns     loc_180021C21
0x180021de8  lea     rcx, [rsp+2C8h+pvarg]; pvarg
0x180021ded  call    cs:__imp_VariantClear
0x180021df4  nop     dword ptr [rax+rax+00h]
0x180021df9  mov     eax, ebx
0x180021dfb  jmp     loc_180021CE6
0x180021e00  cmp     eax, 8
0x180021e03  jnz     loc_180021CCC
0x180021e09  mov     rbx, qword ptr [rsp+2C8h+pvarg+8]
0x180021e0e  test    rbx, rbx
0x180021e11  jnz     loc_180021EAF
0x180021e17  lea     rcx, [rsp+2C8h+pvarg]; pvarg
0x180021e1c  call    cs:__imp_VariantClear
0x180021e23  nop     dword ptr [rax+rax+00h]
0x180021e28  mov     eax, 80070057h
0x180021e2d  jmp     loc_180021CE6
0x180021e32  mov     r9, rbx; unsigned __int16 *
0x180021e35  lea     rcx, [rsp+2C8h+var_238]; this
0x180021e3d  call    ?SafePathAppend@tsched@@YAJPEAGKPEBG1@Z; tsched::SafePathAppend(ushort *,ulong,ushort const *,ushort const *)
0x180021e42  mov     ebx, eax
0x180021e44  mov     [rsp+2C8h+var_298], eax
0x180021e48  test    eax, eax
0x180021e4a  jns     short loc_180021E64
0x180021e4c  lea     rcx, [rsp+2C8h+pvarg]; pvarg
0x180021e51  call    cs:__imp_VariantClear
0x180021e58  nop     dword ptr [rax+rax+00h]
0x180021e5d  mov     eax, ebx
0x180021e5f  jmp     loc_180021CE6
0x180021e64  mov     rdx, qword ptr [rsp+2C8h+pvarg+8]; unsigned __int16 *
0x180021e69  mov     rcx, [rsi+80h]; this
0x180021e70  call    ?Exists@RpcFolderSnapshot@@QEBA_NPEBG@Z; RpcFolderSnapshot::Exists(ushort const *)
0x180021e75  test    al, al
0x180021e77  jnz     short loc_180021E94
0x180021e79  lea     rcx, [rsp+2C8h+pvarg]; pvarg
0x180021e7e  call    cs:__imp_VariantClear
0x180021e85  nop     dword ptr [rax+rax+00h]
0x180021e8a  mov     eax, 80070003h
0x180021e8f  jmp     loc_180021CE6
0x180021e94  lea     rcx, [rsi+78h]
0x180021e98  mov     r8, r14
0x180021e9b  lea     rdx, [rsp+2C8h+var_238]
0x180021ea3  call    ?CreateNewObject@TaskFolderImpl@@SAJAEBV?$AutoRef@VTaskServiceImpl@@@wmi@@PEBGPEAPEAUITaskFolder@@@Z; TaskFolderImpl::CreateNewObject(wmi::AutoRef<TaskServiceImpl> const &,ushort const *,ITaskFolder * *)
0x180021ea8  mov     ebx, eax
0x180021eaa  jmp     loc_180021CC8
0x180021eaf  xor     edx, edx; Val
0x180021eb1  mov     r8d, 20Ah; Size
0x180021eb7  lea     rcx, [rsp+2C8h+var_238]; void *
0x180021ebf  call    memset_0
0x180021ec4  lea     r8, [rsi+40h]; unsigned int
0x180021ec8  cmp     qword ptr [r8+18h], 8
0x180021ecd  jb      loc_180021E32
0x180021ed3  mov     r8, [r8]
0x180021ed6  jmp     loc_180021E32
0x180021edb  mov     [rsp+2C8h+var_270], 0
0x180021ee0  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180021ee7  mov     [rsp+2C8h+pExceptionObject], rax
0x180021eec  lea     rax, qword_18007B2F0
0x180021ef3  mov     [rsp+2C8h+var_268], rax
0x180021ef8  mov     [rsp+2C8h+var_260], 0
0x180021f01  mov     [rsp+2C8h+var_258], 0
0x180021f0a  mov     [rsp+2C8h+var_250], 0FFFFFFFF80070057h
0x180021f13  mov     [rsp+2C8h+var_248], 0FFFFFFFFh
0x180021f1e  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180021f25  lea     rcx, [rsp+2C8h+pExceptionObject]; pExceptionObject
0x180021f2a  call    _CxxThrowException_0
0x180021f30  mov     ebx, [rsp+2C8h+var_298]
0x180021f34  jmp     loc_180021CCC
```
