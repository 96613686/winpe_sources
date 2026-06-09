# ?get_Item@?QITaskFolderCollection@@TaskFolderCollectionImpl@@UEAAJUtagVARIANT@@PEAPEAUITaskFolder@@@Z

- ea: `0x18000d9a0`
- end: `0x18000dd04`
- name: `?get_Item@?QITaskFolderCollection@@TaskFolderCollectionImpl@@UEAAJUtagVARIANT@@PEAPEAUITaskFolder@@@Z`
- size: `868`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x18000bff0`
- `0x18000d9a0`
- `0x18000dd10`
- `0x18000df00`
- `0x18001e18c`
- `0x18003b51c`
- `0x18004e90f`
- `0x18004e950`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000d9d8`
- `OLEAUT32!__imp_VariantInit` at `0x18000d9d8`
- `OLEAUT32!__imp_VariantClear` at `0x18000dac2`
- `OLEAUT32!__imp_VariantClear` at `0x18000daf5`
- `OLEAUT32!__imp_VariantClear` at `0x18000db34`
- `OLEAUT32!__imp_VariantClear` at `0x18000dbcf`
- `OLEAUT32!__imp_VariantClear` at `0x18000dbf8`
- `OLEAUT32!__imp_VariantClear` at `0x18000dc27`
- `OLEAUT32!__imp_VariantClear` at `0x18000dc4e`
- `OLEAUT32!__imp_VariantClear` at `0x18000dac2`
- `OLEAUT32!__imp_VariantClear` at `0x18000daf5`
- `OLEAUT32!__imp_VariantClear` at `0x18000db34`
- `OLEAUT32!__imp_VariantClear` at `0x18000dbcf`
- `OLEAUT32!__imp_VariantClear` at `0x18000dbf8`
- `OLEAUT32!__imp_VariantClear` at `0x18000dc27`
- `OLEAUT32!__imp_VariantClear` at `0x18000dc4e`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000d9f0`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000dbb6`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000d9f0`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000dbb6`

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
  int v8; // edi
  unsigned int v9; // eax
  __int64 v10; // rsi
  unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // r9
  _QWORD *v13; // r8
  __int64 v15; // rax
  unsigned __int16 **v16; // r8
  unsigned __int16 *v17; // rax
  __int64 i; // rcx
  const unsigned __int16 *bstrVal; // rbx
  unsigned __int16 *v20; // rdx
  _QWORD *v21; // r8
  const unsigned __int16 *v22; // [rsp+20h] [rbp-2B8h]
  VARIANTARG pvarg; // [rsp+38h] [rbp-2A0h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-288h] BYREF
  char v25; // [rsp+58h] [rbp-280h]
  __int64 *v26; // [rsp+60h] [rbp-278h]
  __int64 v27; // [rsp+68h] [rbp-270h]
  __int64 v28; // [rsp+70h] [rbp-268h]
  __int64 v29; // [rsp+78h] [rbp-260h]
  int v30; // [rsp+80h] [rbp-258h]
  _BYTE v31[528]; // [rsp+90h] [rbp-248h] BYREF

  if ( !a3 )
    return 2147500035LL;
  VariantInit(&pvarg);
  NewObject = VariantChangeType(&pvarg, a2, 0, 3u);
  if ( NewObject < 0 )
  {
    NewObject = VariantChangeType(&pvarg, a2, 0, 8u);
    if ( NewObject < 0 )
      goto LABEL_42;
  }
  if ( pvarg.vt == 3 )
  {
    if ( pvarg.lVal >= 1 )
    {
      v7 = *(_QWORD *)(a1 + 128);
      v8 = *(_DWORD *)(v7 + 16);
      if ( v8 )
        v9 = v8 == 1 ? *(_DWORD *)(*(_QWORD *)(v7 + 24) + 8LL) : *(_DWORD *)(v7 + 40);
      else
        v9 = 0;
      if ( pvarg.lVal <= v9 )
      {
        v10 = (unsigned int)(pvarg.lVal - 1);
        memset_0(v31, 0, 0x20Au);
        if ( (unsigned int)v10 >= RpcFolderSnapshot::Count((RpcFolderSnapshot *)v7) || !v8 )
        {
LABEL_11:
          v12 = 0;
          goto LABEL_12;
        }
        if ( v8 == 1 )
        {
          v15 = *(_QWORD *)(v7 + 24);
          if ( (unsigned int)v10 >= *(_DWORD *)(v15 + 8) )
          {
            v25 = 0;
            pExceptionObject = &wmi::GenericException::`vftable';
            v26 = &qword_180077320;
            v27 = 0;
            v28 = 0;
            v29 = -2147024809;
            v30 = -1;
            throw (wmi::GenericException *)&pExceptionObject;
          }
          v12 = *(const unsigned __int16 **)(*(_QWORD *)v15 + 8 * v10);
LABEL_12:
          v13 = (_QWORD *)(a1 + 64);
          if ( *(_QWORD *)(a1 + 88) >= 8u )
            v13 = (_QWORD *)*v13;
          NewObject = tsched::SafePathAppend((tsched *)v31, v11, (unsigned int)v13, v12, v22);
          if ( NewObject < 0 )
            goto LABEL_42;
          goto LABEL_15;
        }
        v16 = *(unsigned __int16 ***)(v7 + 32);
        v17 = *v16;
        while ( 1 )
        {
          do
          {
            if ( v17 == (unsigned __int16 *)v16 )
              goto LABEL_11;
            if ( !(_DWORD)v10 )
            {
              v12 = (const unsigned __int16 *)*((_QWORD *)v17 + 4);
              goto LABEL_12;
            }
            LODWORD(v10) = v10 - 1;
          }
          while ( *((_BYTE *)v17 + 25) );
          i = *((_QWORD *)v17 + 2);
          if ( *(_BYTE *)(i + 25) )
          {
            for ( i = *((_QWORD *)v17 + 1);
                  !*(_BYTE *)(i + 25) && v17 == *(unsigned __int16 **)(i + 16);
                  i = *(_QWORD *)(i + 8) )
            {
              v17 = (unsigned __int16 *)i;
            }
LABEL_29:
            v17 = (unsigned __int16 *)i;
          }
          else
          {
            v11 = *(unsigned __int16 **)i;
            if ( *(_BYTE *)(*(_QWORD *)i + 25LL) )
              goto LABEL_29;
            do
            {
              v17 = v11;
              v11 = *(unsigned __int16 **)v11;
            }
            while ( !*((_BYTE *)v11 + 25) );
          }
        }
      }
    }
LABEL_40:
    VariantClear(&pvarg);
    return 2147942487LL;
  }
  if ( pvarg.vt != 8 )
    goto LABEL_42;
  bstrVal = pvarg.bstrVal;
  if ( !pvarg.llVal )
    goto LABEL_40;
  memset_0(v31, 0, 0x20Au);
  v21 = (_QWORD *)(a1 + 64);
  if ( *(_QWORD *)(a1 + 88) >= 8u )
    v21 = (_QWORD *)*v21;
  NewObject = tsched::SafePathAppend((tsched *)v31, v20, (unsigned int)v21, bstrVal, v22);
  if ( NewObject < 0 )
    goto LABEL_42;
  if ( RpcFolderSnapshot::Exists(*(RpcFolderSnapshot **)(a1 + 128), pvarg.bstrVal) )
  {
LABEL_15:
    NewObject = TaskFolderImpl::CreateNewObject(a1 + 120, v31, a3);
LABEL_42:
    VariantClear(&pvarg);
    return (unsigned int)NewObject;
  }
  VariantClear(&pvarg);
  return 2147942403LL;
}

```

## disassembly

```asm
0x18000d9a0  push    rbx
0x18000d9a2  push    rsi
0x18000d9a3  push    rdi
0x18000d9a4  push    r14
0x18000d9a6  push    r15
0x18000d9a8  sub     rsp, 2B0h
0x18000d9af  mov     rax, cs:__security_cookie
0x18000d9b6  xor     rax, rsp
0x18000d9b9  mov     [rsp+2D8h+var_38], rax
0x18000d9c1  mov     r15, r8
0x18000d9c4  mov     rdi, rdx
0x18000d9c7  mov     r14, rcx
0x18000d9ca  test    r8, r8
0x18000d9cd  jz      loc_18000DACC
0x18000d9d3  lea     rcx, [rsp+2D8h+pvarg]; pvarg
0x18000d9d8  call    cs:__imp_VariantInit
0x18000d9de  nop
0x18000d9df  mov     r9d, 3; vt
0x18000d9e5  xor     r8d, r8d; wFlags
0x18000d9e8  mov     rdx, rdi; pvarSrc
0x18000d9eb  lea     rcx, [rsp+2D8h+pvarg]; pvargDest
0x18000d9f0  call    cs:__imp_VariantChangeType
0x18000d9f6  mov     ebx, eax
0x18000d9f8  mov     [rsp+2D8h+var_2A8], eax
0x18000d9fc  test    eax, eax
0x18000d9fe  js      loc_18000DBA5
0x18000da04  movzx   eax, word ptr [rsp+2D8h+pvarg]
0x18000da09  cmp     eax, 3
0x18000da0c  jnz     loc_18000DBDC
0x18000da12  mov     rsi, qword ptr [rsp+2D8h+pvarg+8]
0x18000da17  cmp     esi, 1
0x18000da1a  jl      loc_18000DAF0
0x18000da20  mov     rbx, [r14+80h]
0x18000da27  mov     edi, [rbx+10h]
0x18000da2a  mov     eax, edi
0x18000da2c  test    edi, edi
0x18000da2e  jz      loc_18000DB28
0x18000da34  cmp     eax, 1
0x18000da37  jnz     loc_18000DB20
0x18000da3d  mov     rax, [rbx+18h]
0x18000da41  mov     eax, [rax+8]
0x18000da44  cmp     esi, eax
0x18000da46  ja      loc_18000DAF0
0x18000da4c  dec     esi
0x18000da4e  xor     edx, edx; Val
0x18000da50  mov     r8d, 20Ah; Size
0x18000da56  lea     rcx, [rsp+2D8h+var_248]; void *
0x18000da5e  call    memset_0
0x18000da63  mov     rcx, rbx; this
0x18000da66  call    ?Count@RpcFolderSnapshot@@QEBAKXZ; RpcFolderSnapshot::Count(void)
0x18000da6b  cmp     esi, eax
0x18000da6d  jnb     short loc_18000DA77
0x18000da6f  test    edi, edi
0x18000da71  jnz     loc_18000DB02
0x18000da77  xor     r9d, r9d; unsigned __int16 *
0x18000da7a  lea     r8, [r14+40h]
0x18000da7e  cmp     qword ptr [r8+18h], 8
0x18000da83  jb      short loc_18000DA88
0x18000da85  mov     r8, [r8]; unsigned int
0x18000da88  lea     rcx, [rsp+2D8h+var_248]; this
0x18000da90  call    ?SafePathAppend@tsched@@YAJPEAGKPEBG1@Z; tsched::SafePathAppend(ushort *,ulong,ushort const *,ushort const *)
0x18000da95  mov     ebx, eax
0x18000da97  mov     [rsp+2D8h+var_2A8], eax
0x18000da9b  test    eax, eax
0x18000da9d  js      loc_18000DB2F
0x18000daa3  lea     rcx, [r14+78h]
0x18000daa7  mov     r8, r15
0x18000daaa  lea     rdx, [rsp+2D8h+var_248]
0x18000dab2  call    ?CreateNewObject@TaskFolderImpl@@SAJAEBV?$AutoRef@VTaskServiceImpl@@@wmi@@PEBGPEAPEAUITaskFolder@@@Z; TaskFolderImpl::CreateNewObject(wmi::AutoRef<TaskServiceImpl> const &,ushort const *,ITaskFolder * *)
0x18000dab7  mov     ebx, eax
0x18000dab9  mov     [rsp+2D8h+var_2A8], eax
0x18000dabd  lea     rcx, [rsp+2D8h+pvarg]; pvarg
0x18000dac2  call    cs:__imp_VariantClear
0x18000dac8  mov     eax, ebx
0x18000daca  jmp     short loc_18000DAD1
0x18000dacc  mov     eax, 80004003h
0x18000dad1  mov     rcx, [rsp+2D8h+var_38]
0x18000dad9  xor     rcx, rsp; StackCookie
0x18000dadc  call    __security_check_cookie
0x18000dae1  add     rsp, 2B0h
0x18000dae8  pop     r15
0x18000daea  pop     r14
0x18000daec  pop     rdi
0x18000daed  pop     rsi
0x18000daee  pop     rbx
0x18000daef  retn
0x18000daf0  lea     rcx, [rsp+2D8h+pvarg]; pvarg
0x18000daf5  call    cs:__imp_VariantClear
0x18000dafb  mov     eax, 80070057h
0x18000db00  jmp     short loc_18000DAD1
0x18000db02  cmp     edi, 1
0x18000db05  jnz     short loc_18000DB3E
0x18000db07  mov     rax, [rbx+18h]
0x18000db0b  cmp     esi, [rax+8]
0x18000db0e  jnb     loc_18000DCA5
0x18000db14  mov     rax, [rax]
0x18000db17  mov     r9, [rax+rsi*8]
0x18000db1b  jmp     loc_18000DA7A
0x18000db20  mov     eax, [rbx+28h]
0x18000db23  jmp     loc_18000DA44
0x18000db28  xor     eax, eax
0x18000db2a  jmp     loc_18000DA44
0x18000db2f  lea     rcx, [rsp+2D8h+pvarg]; pvarg
0x18000db34  call    cs:__imp_VariantClear
0x18000db3a  mov     eax, ebx
0x18000db3c  jmp     short loc_18000DAD1
0x18000db3e  mov     r8, [rbx+20h]
0x18000db42  mov     rax, [r8]
0x18000db45  cmp     rax, r8
0x18000db48  jz      loc_18000DA77
0x18000db4e  test    esi, esi
0x18000db50  jz      short loc_18000DB9C
0x18000db52  dec     esi
0x18000db54  cmp     byte ptr [rax+19h], 0
0x18000db58  jnz     short loc_18000DB45
0x18000db5a  mov     rcx, [rax+10h]
0x18000db5e  cmp     byte ptr [rcx+19h], 0
0x18000db62  jz      short loc_18000DB73
0x18000db64  mov     rcx, [rax+8]
0x18000db68  cmp     byte ptr [rcx+19h], 0
0x18000db6c  jz      short loc_18000DB8D
0x18000db6e  mov     rax, rcx
0x18000db71  jmp     short loc_18000DB45
0x18000db73  mov     rdx, [rcx]
0x18000db76  cmp     byte ptr [rdx+19h], 0
0x18000db7a  jnz     short loc_18000DB6E
0x18000db7c  mov     rax, rdx
0x18000db7f  mov     rcx, [rdx]
0x18000db82  mov     rdx, rcx
0x18000db85  cmp     byte ptr [rcx+19h], 0
0x18000db89  jz      short loc_18000DB7C
0x18000db8b  jmp     short loc_18000DB45
0x18000db8d  cmp     rax, [rcx+10h]
0x18000db91  jnz     short loc_18000DB6E
0x18000db93  mov     rax, rcx
0x18000db96  mov     rcx, [rcx+8]
0x18000db9a  jmp     short loc_18000DB68
0x18000db9c  mov     r9, [rax+20h]
0x18000dba0  jmp     loc_18000DA7A
0x18000dba5  mov     r9d, 8; vt
0x18000dbab  xor     r8d, r8d; wFlags
0x18000dbae  mov     rdx, rdi; pvarSrc
0x18000dbb1  lea     rcx, [rsp+2D8h+pvarg]; pvargDest
0x18000dbb6  call    cs:__imp_VariantChangeType
0x18000dbbc  mov     ebx, eax
0x18000dbbe  mov     [rsp+2D8h+var_2A8], eax
0x18000dbc2  test    eax, eax
0x18000dbc4  jns     loc_18000DA04
0x18000dbca  lea     rcx, [rsp+2D8h+pvarg]; pvarg
0x18000dbcf  call    cs:__imp_VariantClear
0x18000dbd5  mov     eax, ebx
0x18000dbd7  jmp     loc_18000DAD1
0x18000dbdc  cmp     eax, 8
0x18000dbdf  jnz     loc_18000DABD
0x18000dbe5  mov     rbx, qword ptr [rsp+2D8h+pvarg+8]
0x18000dbea  test    rbx, rbx
0x18000dbed  jnz     loc_18000DC79
0x18000dbf3  lea     rcx, [rsp+2D8h+pvarg]; pvarg
0x18000dbf8  call    cs:__imp_VariantClear
0x18000dbfe  mov     eax, 80070057h
0x18000dc03  jmp     loc_18000DAD1
0x18000dc08  mov     r9, rbx; unsigned __int16 *
0x18000dc0b  lea     rcx, [rsp+2D8h+var_248]; this
0x18000dc13  call    ?SafePathAppend@tsched@@YAJPEAGKPEBG1@Z; tsched::SafePathAppend(ushort *,ulong,ushort const *,ushort const *)
0x18000dc18  mov     ebx, eax
0x18000dc1a  mov     [rsp+2D8h+var_2A8], eax
0x18000dc1e  test    eax, eax
0x18000dc20  jns     short loc_18000DC34
0x18000dc22  lea     rcx, [rsp+2D8h+pvarg]; pvarg
0x18000dc27  call    cs:__imp_VariantClear
0x18000dc2d  mov     eax, ebx
0x18000dc2f  jmp     loc_18000DAD1
0x18000dc34  mov     rdx, qword ptr [rsp+2D8h+pvarg+8]; unsigned __int16 *
0x18000dc39  mov     rcx, [r14+80h]; this
0x18000dc40  call    ?Exists@RpcFolderSnapshot@@QEBA_NPEBG@Z; RpcFolderSnapshot::Exists(ushort const *)
0x18000dc45  test    al, al
0x18000dc47  jnz     short loc_18000DC5E
0x18000dc49  lea     rcx, [rsp+2D8h+pvarg]; pvarg
0x18000dc4e  call    cs:__imp_VariantClear
0x18000dc54  mov     eax, 80070003h
0x18000dc59  jmp     loc_18000DAD1
0x18000dc5e  lea     rcx, [r14+78h]
0x18000dc62  mov     r8, r15
0x18000dc65  lea     rdx, [rsp+2D8h+var_248]
0x18000dc6d  call    ?CreateNewObject@TaskFolderImpl@@SAJAEBV?$AutoRef@VTaskServiceImpl@@@wmi@@PEBGPEAPEAUITaskFolder@@@Z; TaskFolderImpl::CreateNewObject(wmi::AutoRef<TaskServiceImpl> const &,ushort const *,ITaskFolder * *)
0x18000dc72  mov     ebx, eax
0x18000dc74  jmp     loc_18000DAB9
0x18000dc79  xor     edx, edx; Val
0x18000dc7b  mov     r8d, 20Ah; Size
0x18000dc81  lea     rcx, [rsp+2D8h+var_248]; void *
0x18000dc89  call    memset_0
0x18000dc8e  lea     r8, [r14+40h]; unsigned int
0x18000dc92  cmp     qword ptr [r8+18h], 8
0x18000dc97  jb      loc_18000DC08
0x18000dc9d  mov     r8, [r8]
0x18000dca0  jmp     loc_18000DC08
0x18000dca5  mov     [rsp+2D8h+var_280], 0
0x18000dcaa  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000dcb1  mov     [rsp+2D8h+pExceptionObject], rax
0x18000dcb6  lea     rax, qword_180077320
0x18000dcbd  mov     [rsp+2D8h+var_278], rax
0x18000dcc2  mov     [rsp+2D8h+var_270], 0
0x18000dccb  mov     [rsp+2D8h+var_268], 0
0x18000dcd4  mov     [rsp+2D8h+var_260], 0FFFFFFFF80070057h
0x18000dcdd  mov     [rsp+2D8h+var_258], 0FFFFFFFFh
0x18000dce8  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000dcef  lea     rcx, [rsp+2D8h+pExceptionObject]; pExceptionObject
0x18000dcf4  call    _CxxThrowException_0
0x18000dcfa  mov     ebx, [rsp+2D8h+var_2A8]
0x18000dcfe  jmp     loc_18000DABD
```
