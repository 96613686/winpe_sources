# CMediaServer::Initialize(ushort *,ushort *,ushort *)

- ea: `0x140055fb0`
- end: `0x1400561f7`
- name: `?Initialize@CMediaServer@@UEAAJPEAG00@Z`
- size: `583`
- prototype: `int(CMediaServer *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000c780`
- `0x140024688`
- `0x14003e5f4`
- `0x14003f17c`
- `0x14003fad8`
- `0x140055fb0`
- `0x14009e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140056156`
- `OLEAUT32!__imp_SysFreeString` at `0x140056161`
- `OLEAUT32!__imp_SysFreeString` at `0x140056156`
- `OLEAUT32!__imp_SysFreeString` at `0x140056161`
- `OLEAUT32!__imp_SysStringLen` at `0x140056021`
- `OLEAUT32!__imp_SysStringLen` at `0x140056021`
- `ole32!CoCreateInstance` at `0x14005604d`
- `ole32!CoCreateInstance` at `0x14005604d`

## pseudocode

```c
__int64 __fastcall CMediaServer::Initialize(
        CMediaServer *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  PVOID *v6; // r10
  HRESULT v7; // eax
  int v8; // ebx
  int v9; // eax
  LPVOID ppv; // [rsp+30h] [rbp-28h] BYREF
  BSTR bstrString[4]; // [rsp+38h] [rbp-20h] BYREF
  BSTR v13; // [rsp+70h] [rbp+18h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids, a3);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  ppv = 0;
  if ( a3 )
  {
    if ( SysStringLen(a3) )
    {
      v7 = CoCreateInstance(&CLSID_UPnPRegistrar, 0, 0x17u, &GUID_204810b6_73b2_11d4_bf42_00b0d0118b56, &ppv);
      v8 = v7;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v7 >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          &WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids,
          (unsigned int)v7);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 < 0 )
        goto LABEL_28;
      v13 = 0;
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"uuid:32d0d20f-2613-46a1-add3-5198c3d6a24d");
      v9 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, BSTR, BSTR *))(*(_QWORD *)ppv + 48LL))(
             ppv,
             a3,
             bstrString[0],
             &v13);
      v8 = v9;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v9 >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          &WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids,
          (unsigned int)v9);
      }
      if ( v8 >= 0 )
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 80, v13);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            &WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids,
            *((_QWORD *)this + 10));
        }
      }
      SysFreeString(bstrString[0]);
      SysFreeString(v13);
      goto LABEL_27;
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v8 = -2147024809;
  if ( v6 == &WPP_GLOBAL_Control )
    goto LABEL_32;
  if ( (*((_BYTE *)v6 + 28) & 2) != 0 && *((_BYTE *)v6 + 25) >= 2u )
  {
    WPP_SF_d(v6[2], 25, &WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids, 2147942487LL);
LABEL_27:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_28:
  if ( v6 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v6 + 28) & 1) != 0
    && *((unsigned __int8 *)v6 + 25) >= ((v8 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(v6[2], 29, &WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids, (unsigned int)v8);
  }
LABEL_32:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140055fb0  mov     [rsp+arg_0], rbx
0x140055fb5  mov     [rsp+arg_8], rbp
0x140055fba  push    rsi
0x140055fbb  push    r14
0x140055fbd  push    r15
0x140055fbf  sub     rsp, 40h
0x140055fc3  mov     rsi, r8
0x140055fc6  mov     rbp, rcx
0x140055fc9  mov     r10, cs:WPP_GLOBAL_Control
0x140055fd0  lea     r15, WPP_GLOBAL_Control
0x140055fd7  lea     r14, WPP_02c6dcd2c5d83623206397dda38e97d9_Traceguids
0x140055fde  cmp     r10, r15
0x140055fe1  jz      short loc_14005600C
0x140055fe3  test    byte ptr [r10+1Ch], 1
0x140055fe8  jz      short loc_14005600C
0x140055fea  cmp     byte ptr [r10+19h], 5
0x140055fef  jb      short loc_14005600C
0x140055ff1  mov     rcx, [r10+10h]
0x140055ff5  mov     r9, r8
0x140055ff8  mov     r8, r14
0x140055ffb  mov     edx, 18h
0x140056000  call    WPP_SF_S
0x140056005  mov     r10, cs:WPP_GLOBAL_Control
0x14005600c  mov     [rsp+58h+var_28], 0
0x140056015  test    rsi, rsi
0x140056018  jz      loc_140056170
0x14005601e  mov     rcx, rsi; pbstr
0x140056021  call    cs:__imp_SysStringLen
0x140056027  test    eax, eax
0x140056029  jz      loc_140056169
0x14005602f  xor     edx, edx; pUnkOuter
0x140056031  lea     rax, [rsp+58h+var_28]
0x140056036  lea     r9, _GUID_204810b6_73b2_11d4_bf42_00b0d0118b56; riid
0x14005603d  mov     [rsp+58h+ppv], rax; ppv
0x140056042  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x140056049  lea     r8d, [rdx+17h]; dwClsContext
0x14005604d  call    cs:__imp_CoCreateInstance
0x140056053  mov     ebx, eax
0x140056055  mov     r10, cs:WPP_GLOBAL_Control
0x14005605c  cmp     r10, r15
0x14005605f  jz      short loc_140056097
0x140056061  test    byte ptr [r10+1Ch], 2
0x140056066  jz      short loc_140056097
0x140056068  mov     ecx, eax
0x14005606a  movzx   eax, byte ptr [r10+19h]
0x14005606f  sar     ecx, 1Fh
0x140056072  and     ecx, 0FFFFFFFDh
0x140056075  add     ecx, 5
0x140056078  cmp     eax, ecx
0x14005607a  jb      short loc_140056097
0x14005607c  mov     rcx, [r10+10h]
0x140056080  mov     edx, 1Ah
0x140056085  mov     r9d, ebx
0x140056088  mov     r8, r14
0x14005608b  call    WPP_SF_d
0x140056090  mov     r10, cs:WPP_GLOBAL_Control
0x140056097  test    ebx, ebx
0x140056099  js      loc_1400561A3
0x14005609f  lea     rdx, aUuid32d0d20f26; "uuid:32d0d20f-2613-46a1-add3-5198c3d6a2"...
0x1400560a6  mov     [rsp+58h+arg_10], 0
0x1400560af  lea     rcx, [rsp+58h+bstrString]; this
0x1400560b4  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1400560b9  mov     rcx, [rsp+58h+var_28]
0x1400560be  lea     r9, [rsp+58h+arg_10]
0x1400560c3  mov     r8, [rsp+58h+bstrString]
0x1400560c8  mov     rdx, rsi
0x1400560cb  mov     rax, [rcx]
0x1400560ce  mov     rax, [rax+30h]
0x1400560d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400560d7  mov     ebx, eax
0x1400560d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400560e0  cmp     rcx, r15
0x1400560e3  jz      short loc_140056112
0x1400560e5  test    byte ptr [rcx+1Ch], 2
0x1400560e9  jz      short loc_140056112
0x1400560eb  mov     edx, eax
0x1400560ed  movzx   eax, byte ptr [rcx+19h]
0x1400560f1  sar     edx, 1Fh
0x1400560f4  and     edx, 0FFFFFFFDh
0x1400560f7  add     edx, 5
0x1400560fa  cmp     eax, edx
0x1400560fc  jb      short loc_140056112
0x1400560fe  mov     rcx, [rcx+10h]
0x140056102  mov     edx, 1Bh
0x140056107  mov     r9d, ebx
0x14005610a  mov     r8, r14
0x14005610d  call    WPP_SF_d
0x140056112  test    ebx, ebx
0x140056114  js      short loc_140056151
0x140056116  mov     rdx, [rsp+58h+arg_10]
0x14005611b  lea     rcx, [rbp+50h]
0x14005611f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x140056124  mov     rcx, cs:WPP_GLOBAL_Control
0x14005612b  cmp     rcx, r15
0x14005612e  jz      short loc_140056151
0x140056130  test    byte ptr [rcx+1Ch], 2
0x140056134  jz      short loc_140056151
0x140056136  cmp     byte ptr [rcx+19h], 5
0x14005613a  jb      short loc_140056151
0x14005613c  mov     r9, [rbp+50h]
0x140056140  mov     edx, 1Ch
0x140056145  mov     rcx, [rcx+10h]
0x140056149  mov     r8, r14
0x14005614c  call    WPP_SF_S
0x140056151  mov     rcx, [rsp+58h+bstrString]; bstrString
0x140056156  call    cs:__imp_SysFreeString
0x14005615c  mov     rcx, [rsp+58h+arg_10]; bstrString
0x140056161  call    cs:__imp_SysFreeString
0x140056167  jmp     short loc_14005619C
0x140056169  mov     r10, cs:WPP_GLOBAL_Control
0x140056170  mov     ebx, 80070057h
0x140056175  cmp     r10, r15
0x140056178  jz      short loc_1400561D7
0x14005617a  test    byte ptr [r10+1Ch], 2
0x14005617f  jz      short loc_1400561A3
0x140056181  cmp     byte ptr [r10+19h], 2
0x140056186  jb      short loc_1400561A3
0x140056188  mov     rcx, [r10+10h]
0x14005618c  mov     edx, 19h
0x140056191  mov     r9d, ebx
0x140056194  mov     r8, r14
0x140056197  call    WPP_SF_d
0x14005619c  mov     r10, cs:WPP_GLOBAL_Control
0x1400561a3  cmp     r10, r15
0x1400561a6  jz      short loc_1400561D7
0x1400561a8  test    byte ptr [r10+1Ch], 1
0x1400561ad  jz      short loc_1400561D7
0x1400561af  movzx   ecx, byte ptr [r10+19h]
0x1400561b4  mov     edx, ebx
0x1400561b6  sar     edx, 1Fh
0x1400561b9  and     edx, 0FFFFFFFDh
0x1400561bc  add     edx, 5
0x1400561bf  cmp     ecx, edx
0x1400561c1  jb      short loc_1400561D7
0x1400561c3  mov     rcx, [r10+10h]
0x1400561c7  mov     edx, 1Dh
0x1400561cc  mov     r9d, ebx
0x1400561cf  mov     r8, r14
0x1400561d2  call    WPP_SF_d
0x1400561d7  lea     rcx, [rsp+58h+var_28]
0x1400561dc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400561e1  mov     rbp, [rsp+58h+arg_8]
0x1400561e6  mov     eax, ebx
0x1400561e8  mov     rbx, [rsp+58h+arg_0]
0x1400561ed  add     rsp, 40h
0x1400561f1  pop     r15
0x1400561f3  pop     r14
0x1400561f5  pop     rsi
0x1400561f6  retn
```
