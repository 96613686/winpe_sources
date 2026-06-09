# ContentDirectoryErrors::SetCDErrorInfo(long)

- ea: `0x140065d94`
- end: `0x14006608f`
- name: `?SetCDErrorInfo@ContentDirectoryErrors@@SAXJ@Z`
- size: `763`
- prototype: `void __fastcall(int)`
- caller_count: `12`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400368a0`
- `0x140037954`
- `0x1400595f8`
- `0x14005a420`
- `0x14005a950`
- `0x14005aa40`
- `0x14005af60`
- `0x14005c458`
- `0x14005c690`
- `0x14005d2a8`
- `0x140060a28`
- `0x140060dcc`

## callees

- `0x14000b3b0`
- `0x14000c920`
- `0x140018df0`
- `0x140024688`
- `0x14003f17c`
- `0x140047798`
- `0x14004a834`
- `0x140054490`
- `0x14005480c`
- `0x140065b64`
- `0x140065c74`
- `0x140065d94`
- `0x14009e010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x140066005`
- `OLEAUT32!__imp_SetErrorInfo` at `0x140066005`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x140065e39`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x140065e39`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ContentDirectoryErrors::SetCDErrorInfo(unsigned int a1)
{
  unsigned int CDError; // esi
  HRESULT v3; // eax
  int v4; // ebx
  PVOID *v5; // r10
  __int64 v6; // rbx
  int v7; // eax
  int v8; // edi
  ICreateErrorInfo *v9; // rdi
  HRESULT (__stdcall *SetDescription)(ICreateErrorInfo *, LPOLESTR); // rbx
  _QWORD *ErrorMessage; // rax
  int v12; // ebx
  int v13; // eax
  int v14; // ebx
  HRESULT v15; // eax
  ICreateErrorInfo *pperrinfo; // [rsp+68h] [rbp+38h] BYREF
  IErrorInfo *perrinfo; // [rsp+70h] [rbp+40h] BYREF
  __int64 v18; // [rsp+78h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_5e71f589136237853900a3ba677616c5_Traceguids, a1);
  }
  pperrinfo = 0;
  perrinfo = 0;
  CDError = ContentDirectoryErrors::GetCDError(a1);
  if ( CDError == -1 )
    goto LABEL_34;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_5e71f589136237853900a3ba677616c5_Traceguids, a1);
  }
  v3 = CreateErrorInfo(&pperrinfo);
  v4 = v3;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v3 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_5e71f589136237853900a3ba677616c5_Traceguids,
      (unsigned int)v3,
      pperrinfo);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 < 0 )
    goto LABEL_35;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v18);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
    &v18,
    L"%d",
    CDError);
  v6 = v18;
  v7 = ((__int64 (__fastcall *)(ICreateErrorInfo *, __int64))pperrinfo->lpVtbl->SetSource)(pperrinfo, v18);
  v8 = v7;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v7 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)WPP_5e71f589136237853900a3ba677616c5_Traceguids,
      v7,
      v6);
  }
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v18);
  if ( v8 < 0 )
    goto LABEL_34;
  v9 = pperrinfo;
  SetDescription = pperrinfo->lpVtbl->SetDescription;
  ErrorMessage = (_QWORD *)ContentDirectoryErrors::GetErrorMessage(&v18, CDError);
  v12 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _QWORD))SetDescription)(v9, *ErrorMessage);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v18);
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v12 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_5e71f589136237853900a3ba677616c5_Traceguids,
      (unsigned int)v12);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 >= 0 )
  {
    v13 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
            pperrinfo,
            &GUID_1cf2b120_547d_101b_8e65_08002b2bd119,
            &perrinfo);
    v14 = v13;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v13 >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_dq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_5e71f589136237853900a3ba677616c5_Traceguids,
        (unsigned int)v13,
        perrinfo);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v14 >= 0 )
    {
      v15 = SetErrorInfo(0, perrinfo);
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_38;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v15 >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          WPP_5e71f589136237853900a3ba677616c5_Traceguids,
          (unsigned int)v15);
LABEL_34:
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
LABEL_35:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 )
    WPP_SF_(v5[2], 24, WPP_5e71f589136237853900a3ba677616c5_Traceguids);
LABEL_38:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&perrinfo);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pperrinfo);
}

```

## disassembly

```asm
0x140065d94  mov     [rsp-28h+arg_0], rbx
0x140065d99  push    rbp
0x140065d9a  push    rsi
0x140065d9b  push    rdi
0x140065d9c  push    r12
0x140065d9e  push    r14
0x140065da0  mov     rbp, rsp
0x140065da3  sub     rsp, 30h
0x140065da7  mov     ebx, ecx
0x140065da9  lea     r12, WPP_GLOBAL_Control
0x140065db0  lea     r14, WPP_5e71f589136237853900a3ba677616c5_Traceguids
0x140065db7  mov     rcx, cs:WPP_GLOBAL_Control
0x140065dbe  cmp     rcx, r12
0x140065dc1  jz      short loc_140065DE3
0x140065dc3  test    byte ptr [rcx+1Ch], 1
0x140065dc7  jz      short loc_140065DE3
0x140065dc9  cmp     byte ptr [rcx+19h], 5
0x140065dcd  jb      short loc_140065DE3
0x140065dcf  mov     edx, 11h
0x140065dd4  mov     r9d, ebx
0x140065dd7  mov     r8, r14
0x140065dda  mov     rcx, [rcx+10h]
0x140065dde  call    WPP_SF_d
0x140065de3  mov     [rbp+pperrinfo], 0
0x140065deb  mov     [rbp+perrinfo], 0
0x140065df3  mov     ecx, ebx; int
0x140065df5  call    ?GetCDError@ContentDirectoryErrors@@SAKJ@Z; ContentDirectoryErrors::GetCDError(long)
0x140065dfa  mov     esi, eax
0x140065dfc  cmp     eax, 0FFFFFFFFh
0x140065dff  jz      loc_140066046
0x140065e05  mov     rcx, cs:WPP_GLOBAL_Control
0x140065e0c  cmp     rcx, r12
0x140065e0f  jz      short loc_140065E35
0x140065e11  test    byte ptr [rcx+1Ch], 2
0x140065e15  jz      short loc_140065E35
0x140065e17  cmp     byte ptr [rcx+19h], 5
0x140065e1b  jb      short loc_140065E35
0x140065e1d  mov     edx, 12h
0x140065e22  mov     dword ptr [rsp+30h+var_10], eax
0x140065e26  mov     r9d, ebx
0x140065e29  mov     r8, r14
0x140065e2c  mov     rcx, [rcx+10h]
0x140065e30  call    WPP_SF_Dd
0x140065e35  lea     rcx, [rbp+pperrinfo]; pperrinfo
0x140065e39  call    cs:__imp_CreateErrorInfo
0x140065e3f  mov     ebx, eax
0x140065e41  mov     r10, cs:WPP_GLOBAL_Control
0x140065e48  cmp     r10, r12
0x140065e4b  jz      short loc_140065E8C
0x140065e4d  test    byte ptr [r10+1Ch], 2
0x140065e52  jz      short loc_140065E8C
0x140065e54  mov     edx, eax
0x140065e56  sar     edx, 1Fh
0x140065e59  and     edx, 0FFFFFFFDh
0x140065e5c  add     edx, 5
0x140065e5f  movzx   eax, byte ptr [r10+19h]
0x140065e64  cmp     eax, edx
0x140065e66  jb      short loc_140065E8C
0x140065e68  mov     edx, 13h
0x140065e6d  mov     rax, [rbp+pperrinfo]
0x140065e71  mov     [rsp+30h+var_10], rax
0x140065e76  mov     r9d, ebx
0x140065e79  mov     r8, r14
0x140065e7c  mov     rcx, [r10+10h]
0x140065e80  call    WPP_SF_dq
0x140065e85  mov     r10, cs:WPP_GLOBAL_Control
0x140065e8c  test    ebx, ebx
0x140065e8e  js      loc_14006604D
0x140065e94  lea     rcx, [rbp+arg_18]
0x140065e98  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140065e9d  nop
0x140065e9e  mov     r8d, esi
0x140065ea1  lea     rdx, aD; "%d"
0x140065ea8  lea     rcx, [rbp+arg_18]
0x140065eac  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x140065eb1  mov     rcx, [rbp+pperrinfo]
0x140065eb5  mov     rax, [rcx]
0x140065eb8  mov     rbx, [rbp+arg_18]
0x140065ebc  mov     rdx, rbx
0x140065ebf  mov     rax, [rax+20h]
0x140065ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065ec8  mov     edi, eax
0x140065eca  mov     rcx, cs:WPP_GLOBAL_Control
0x140065ed1  cmp     rcx, r12
0x140065ed4  jz      short loc_140065F09
0x140065ed6  test    byte ptr [rcx+1Ch], 2
0x140065eda  jz      short loc_140065F09
0x140065edc  mov     edx, eax
0x140065ede  sar     edx, 1Fh
0x140065ee1  and     edx, 0FFFFFFFDh
0x140065ee4  add     edx, 5
0x140065ee7  movzx   eax, byte ptr [rcx+19h]
0x140065eeb  cmp     eax, edx
0x140065eed  jb      short loc_140065F09
0x140065eef  mov     edx, 14h
0x140065ef4  mov     [rsp+30h+var_10], rbx
0x140065ef9  mov     r9d, edi
0x140065efc  mov     r8, r14
0x140065eff  mov     rcx, [rcx+10h]
0x140065f03  call    WPP_SF_dS
0x140065f08  nop
0x140065f09  lea     rcx, [rbp+arg_18]
0x140065f0d  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140065f12  test    edi, edi
0x140065f14  js      loc_140066046
0x140065f1a  mov     rdi, [rbp+pperrinfo]
0x140065f1e  mov     rax, [rdi]
0x140065f21  mov     rbx, [rax+28h]
0x140065f25  mov     edx, esi
0x140065f27  lea     rcx, [rbp+arg_18]
0x140065f2b  call    ?GetErrorMessage@ContentDirectoryErrors@@SA?BV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@I@Z; ContentDirectoryErrors::GetErrorMessage(uint)
0x140065f30  nop
0x140065f31  mov     rdx, [rax]
0x140065f34  mov     rcx, rdi
0x140065f37  mov     rax, rbx
0x140065f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065f3f  mov     ebx, eax
0x140065f41  lea     rcx, [rbp+arg_18]
0x140065f45  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140065f4a  mov     r10, cs:WPP_GLOBAL_Control
0x140065f51  cmp     r10, r12
0x140065f54  jz      short loc_140065F8C
0x140065f56  test    byte ptr [r10+1Ch], 2
0x140065f5b  jz      short loc_140065F8C
0x140065f5d  mov     ecx, ebx
0x140065f5f  sar     ecx, 1Fh
0x140065f62  and     ecx, 0FFFFFFFDh
0x140065f65  add     ecx, 5
0x140065f68  movzx   eax, byte ptr [r10+19h]
0x140065f6d  cmp     eax, ecx
0x140065f6f  jb      short loc_140065F8C
0x140065f71  mov     edx, 15h
0x140065f76  mov     r9d, ebx
0x140065f79  mov     r8, r14
0x140065f7c  mov     rcx, [r10+10h]
0x140065f80  call    WPP_SF_d
0x140065f85  mov     r10, cs:WPP_GLOBAL_Control
0x140065f8c  test    ebx, ebx
0x140065f8e  js      loc_14006604D
0x140065f94  mov     rcx, [rbp+pperrinfo]
0x140065f98  mov     rax, [rcx]
0x140065f9b  lea     r8, [rbp+perrinfo]
0x140065f9f  lea     rdx, _GUID_1cf2b120_547d_101b_8e65_08002b2bd119
0x140065fa6  mov     rax, [rax]
0x140065fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065fae  mov     ebx, eax
0x140065fb0  mov     r10, cs:WPP_GLOBAL_Control
0x140065fb7  cmp     r10, r12
0x140065fba  jz      short loc_140065FFB
0x140065fbc  test    byte ptr [r10+1Ch], 2
0x140065fc1  jz      short loc_140065FFB
0x140065fc3  mov     ecx, eax
0x140065fc5  sar     ecx, 1Fh
0x140065fc8  and     ecx, 0FFFFFFFDh
0x140065fcb  add     ecx, 5
0x140065fce  movzx   eax, byte ptr [r10+19h]
0x140065fd3  cmp     eax, ecx
0x140065fd5  jb      short loc_140065FFB
0x140065fd7  mov     edx, 16h
0x140065fdc  mov     rax, [rbp+perrinfo]
0x140065fe0  mov     [rsp+30h+var_10], rax
0x140065fe5  mov     r9d, ebx
0x140065fe8  mov     r8, r14
0x140065feb  mov     rcx, [r10+10h]
0x140065fef  call    WPP_SF_dq
0x140065ff4  mov     r10, cs:WPP_GLOBAL_Control
0x140065ffb  test    ebx, ebx
0x140065ffd  js      short loc_14006604D
0x140065fff  mov     rdx, [rbp+perrinfo]; perrinfo
0x140066003  xor     ecx, ecx; dwReserved
0x140066005  call    cs:__imp_SetErrorInfo
0x14006600b  mov     r9d, eax
0x14006600e  mov     r10, cs:WPP_GLOBAL_Control
0x140066015  cmp     r10, r12
0x140066018  jz      short loc_14006606B
0x14006601a  test    byte ptr [r10+1Ch], 2
0x14006601f  jz      short loc_14006604D
0x140066021  mov     ecx, eax
0x140066023  sar     ecx, 1Fh
0x140066026  and     ecx, 0FFFFFFFDh
0x140066029  add     ecx, 5
0x14006602c  movzx   eax, byte ptr [r10+19h]
0x140066031  cmp     eax, ecx
0x140066033  jb      short loc_14006604D
0x140066035  mov     edx, 17h
0x14006603a  mov     r8, r14
0x14006603d  mov     rcx, [r10+10h]
0x140066041  call    WPP_SF_d
0x140066046  mov     r10, cs:WPP_GLOBAL_Control
0x14006604d  cmp     r10, r12
0x140066050  jz      short loc_14006606B
0x140066052  test    byte ptr [r10+1Ch], 1
0x140066057  jz      short loc_14006606B
0x140066059  mov     edx, 18h
0x14006605e  mov     r8, r14
0x140066061  mov     rcx, [r10+10h]
0x140066065  call    WPP_SF_
0x14006606a  nop
0x14006606b  lea     rcx, [rbp+perrinfo]
0x14006606f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140066074  nop
0x140066075  lea     rcx, [rbp+pperrinfo]
0x140066079  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14006607e  mov     rbx, [rsp+30h+arg_0]
0x140066083  add     rsp, 30h
0x140066087  pop     r14
0x140066089  pop     r12
0x14006608b  pop     rdi
0x14006608c  pop     rsi
0x14006608d  pop     rbp
0x14006608e  retn
```
