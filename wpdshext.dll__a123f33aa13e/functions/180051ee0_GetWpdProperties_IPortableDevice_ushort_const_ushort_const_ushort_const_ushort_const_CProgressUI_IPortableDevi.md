# GetWpdProperties(IPortableDevice *,ushort const *,ushort const *,ushort const *,ushort const *,CProgressUI *,IPortableDeviceValues * *)

- ea: `0x180051ee0`
- end: `0x1800525cd`
- name: `?GetWpdProperties@@YAJPEAUIPortableDevice@@PEBG111PEAVCProgressUI@@PEAPEAUIPortableDeviceValues@@@Z`
- size: `1773`
- prototype: `__int64 __usercall@<rax>(struct IPortableDevice *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, struct CProgressUI *, struct IPortableDeviceValues **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800118d4`

## callees

- `0x1800285c8`
- `0x18002ab58`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180051ee0`
- `0x1800538c4`
- `0x180054524`
- `0x1800545c8`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180052413`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180052413`
- `KERNEL32!Sleep` at `0x180052232`
- `KERNEL32!Sleep` at `0x180052309`
- `KERNEL32!Sleep` at `0x180052232`
- `KERNEL32!Sleep` at `0x180052309`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetWpdProperties(
        struct IPortableDevice *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        wchar_t *a4,
        wchar_t *a5,
        struct CProgressUI *a6,
        struct IPortableDeviceValues **a7)
{
  wchar_t *v11; // r13
  unsigned int v12; // ebx
  int WpdProperties; // eax
  PVOID *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  int v17; // r15d
  int v18; // r14d
  int v19; // r12d
  int v20; // r14d
  int v21; // r15d
  int v22; // ebx
  unsigned int i; // ebx
  struct IPortableDeviceValues *v24; // rcx
  HRESULT (__stdcall *SetStringValue)(IPortableDeviceValues *, const PROPERTYKEY *const, LPCWSTR); // rax
  unsigned int v27; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *FullPath; // [rsp+68h] [rbp-98h]
  GUID v31; // [rsp+70h] [rbp-90h] BYREF
  __int128 Buf2; // [rsp+80h] [rbp-80h] BYREF
  int v33; // [rsp+90h] [rbp-70h]
  GUID v34; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v35[264]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Filename[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wchar_t Ext[264]; // [rsp+4D0h] [rbp+3D0h] BYREF

  FullPath = a4;
  v11 = a5;
  v27 = 0;
  Buf2 = 0;
  v33 = 0;
  v31 = WPD_OBJECT_FORMAT_UNSPECIFIED;
  v34 = 0;
  memset_0(v35, 0, 0x208u);
  memset_0(Filename, 0, 0x208u);
  memset_0(Ext, 0, 0x208u);
  v29 = 0;
  v28 = 0;
  if ( !a1 || !a2 || !a3 || !a4 )
  {
    v12 = -2147024809;
    goto LABEL_103;
  }
  if ( !a7 )
  {
    v12 = -2147467261;
LABEL_103:
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_104;
  }
  WpdProperties = _GetWpdProperties(a1, a2, a6, a7);
  v12 = WpdProperties;
  if ( WpdProperties < 0 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_107;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_104;
    v15 = 83;
    goto LABEL_101;
  }
  if ( !*a7 )
  {
    v12 = -2147418113;
    goto LABEL_103;
  }
  WpdProperties = ((__int64 (__fastcall *)(_QWORD, const PROPERTYKEY *))(*a7)->lpVtbl->RemoveValue)(
                    *a7,
                    &WPD_OBJECT_PERSISTENT_UNIQUE_ID);
  v12 = WpdProperties;
  if ( WpdProperties < 0 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_107;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_104;
    v15 = 84;
    goto LABEL_101;
  }
  WpdProperties = ((__int64 (__fastcall *)(_QWORD, const PROPERTYKEY *))(*a7)->lpVtbl->RemoveValue)(
                    *a7,
                    &WPD_OBJECT_NAME);
  v12 = WpdProperties;
  if ( WpdProperties < 0 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_107;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_104;
    v15 = 85;
    goto LABEL_101;
  }
  WpdProperties = ((__int64 (__fastcall *)(_QWORD, const PROPERTYKEY *))(*a7)->lpVtbl->RemoveValue)(
                    *a7,
                    &WPD_OBJECT_ORIGINAL_FILE_NAME);
  v12 = WpdProperties;
  if ( WpdProperties < 0 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_107;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_104;
    v15 = 86;
    goto LABEL_101;
  }
  WpdProperties = ((__int64 (__fastcall *)(_QWORD, const PROPERTYKEY *))(*a7)->lpVtbl->RemoveValue)(
                    *a7,
                    &WPD_OBJECT_NON_CONSUMABLE);
  v12 = WpdProperties;
  if ( WpdProperties < 0 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_107;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_104;
    v15 = 87;
    goto LABEL_101;
  }
  WpdProperties = ((__int64 (__fastcall *)(_QWORD, const PROPERTYKEY *, const unsigned __int16 *))(*a7)->lpVtbl->SetStringValue)(
                    *a7,
                    &WPD_OBJECT_PARENT_ID,
                    a3);
  v12 = WpdProperties;
  if ( WpdProperties < 0 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_107;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_104;
    v15 = 88;
    goto LABEL_101;
  }
  if ( a6 )
  {
    v17 = 0;
    v18 = 0;
    while ( !*((_DWORD *)a6 + 26) )
    {
      v12 = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))a1->lpVtbl->Capabilities)(a1, &v29);
      if ( v12 != -2147024726 )
        goto LABEL_50;
      if ( !v17 )
      {
        v17 = 1;
        v18 = 1;
        CProgressUI::_StartMarquee(a6);
      }
      if ( *((_DWORD *)a6 + 26) )
        break;
      Sleep(0x5DCu);
    }
    v12 = -2147023673;
LABEL_50:
    if ( v18 )
      CProgressUI::_StopMarquee(a6);
    if ( *((_DWORD *)a6 + 26) )
    {
      v12 = -2147023673;
      goto LABEL_38;
    }
  }
  else
  {
    v12 = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))a1->lpVtbl->Capabilities)(a1, &v29);
  }
  if ( (v12 & 0x80000000) != 0 )
  {
LABEL_38:
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_107;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_104;
    v15 = 89;
    v16 = v12;
    goto LABEL_102;
  }
  if ( ((int (__fastcall *)(_QWORD, const PROPERTYKEY *, GUID *))(*a7)->lpVtbl->GetGuidValue)(
         *a7,
         &WPD_OBJECT_FORMAT,
         &v34) >= 0 )
    v31 = v34;
  v19 = 0;
  if ( a6 )
  {
    v21 = 0;
    v22 = 0;
    while ( !*((_DWORD *)a6 + 26) )
    {
      v20 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v29 + 72LL))(v29, &v31, &v28);
      if ( v20 != -2147024726 )
        goto LABEL_67;
      if ( !v21 )
      {
        v21 = 1;
        v22 = 1;
        CProgressUI::_StartMarquee(a6);
      }
      if ( *((_DWORD *)a6 + 26) )
        break;
      Sleep(0x5DCu);
    }
    v20 = -2147023673;
LABEL_67:
    if ( v22 )
      CProgressUI::_StopMarquee(a6);
    if ( *((_DWORD *)a6 + 26) )
      goto LABEL_82;
  }
  else
  {
    v20 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v29 + 72LL))(v29, &v31, &v28);
  }
  if ( v20 >= 0 )
  {
    WpdProperties = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 24LL))(v28, &v27);
    v12 = WpdProperties;
    if ( WpdProperties < 0 )
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_107;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_104;
      v15 = 90;
      goto LABEL_101;
    }
    for ( i = 0; i < v27; ++i )
    {
      if ( (*(int (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v28 + 32LL))(v28, i, &Buf2) >= 0
        && v33 == 12
        && !memcmp_0(&WPD_OBJECT_ORIGINAL_FILE_NAME, &Buf2, 0x10u) )
      {
        v19 = 1;
        break;
      }
    }
  }
LABEL_82:
  if ( !a5 )
    v11 = FullPath;
  _wsplitpath_s(v11, 0, 0, 0, 0, Filename, 0x104u, Ext, 0x104u);
  StringCchPrintfW(v35, 0x104u, L"%ws%ws", Filename, Ext);
  v24 = *a7;
  SetStringValue = (*a7)->lpVtbl->SetStringValue;
  if ( v19 )
  {
    WpdProperties = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, unsigned __int16 *))SetStringValue)(
                      v24,
                      &WPD_OBJECT_ORIGINAL_FILE_NAME,
                      v35);
    v12 = WpdProperties;
    if ( WpdProperties >= 0 )
    {
      WpdProperties = ((__int64 (__fastcall *)(_QWORD, const PROPERTYKEY *, wchar_t *))(*a7)->lpVtbl->SetStringValue)(
                        *a7,
                        &WPD_OBJECT_NAME,
                        Filename);
      v12 = WpdProperties;
      if ( WpdProperties >= 0 )
        goto LABEL_107;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_107;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_104;
      v15 = 92;
    }
    else
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_107;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_104;
      v15 = 91;
    }
    goto LABEL_101;
  }
  WpdProperties = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, unsigned __int16 *))SetStringValue)(
                    v24,
                    &WPD_OBJECT_NAME,
                    v35);
  v12 = WpdProperties;
  if ( WpdProperties < 0 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_107;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_104;
    v15 = 93;
    goto LABEL_101;
  }
  WpdProperties = ((__int64 (__fastcall *)(_QWORD, const PROPERTYKEY *, unsigned __int16 *))(*a7)->lpVtbl->SetStringValue)(
                    *a7,
                    &WPD_OBJECT_ORIGINAL_FILE_NAME,
                    v35);
  v12 = WpdProperties;
  if ( WpdProperties >= 0 )
    goto LABEL_107;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_107;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v15 = 94;
LABEL_101:
    v16 = (unsigned int)WpdProperties;
LABEL_102:
    WPP_SF_d(v14[2], v15, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, v16);
    goto LABEL_103;
  }
LABEL_104:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 )
    WPP_SF_d(v14[2], 95, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, v12);
LABEL_107:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  return v12;
}

```

## disassembly

```asm
0x180051ee0  push    rbp
0x180051ee2  push    rbx
0x180051ee3  push    rsi
0x180051ee4  push    rdi
0x180051ee5  push    r12
0x180051ee7  push    r13
0x180051ee9  push    r14
0x180051eeb  push    r15
0x180051eed  lea     rbp, [rsp-5F8h]
0x180051ef5  sub     rsp, 6F8h
0x180051efc  mov     rax, cs:__security_cookie
0x180051f03  xor     rax, rsp
0x180051f06  mov     [rbp+630h+var_50], rax
0x180051f0d  mov     r15, r9
0x180051f10  mov     [rsp+730h+FullPath], r9
0x180051f15  mov     r14, r8
0x180051f18  mov     rbx, rdx
0x180051f1b  mov     r12, rcx
0x180051f1e  mov     r13, [rbp+630h+arg_20]
0x180051f25  mov     rdi, [rbp+630h+arg_28]
0x180051f2c  mov     rsi, [rbp+630h+arg_30]
0x180051f33  mov     [rsp+730h+var_6E0], 0
0x180051f3b  xorps   xmm0, xmm0
0x180051f3e  xor     eax, eax
0x180051f40  movups  [rbp+630h+Buf2], xmm0
0x180051f44  mov     [rbp+630h+var_6A0], eax
0x180051f47  movups  xmm1, xmmword ptr cs:WPD_OBJECT_FORMAT_UNSPECIFIED.Data1
0x180051f4e  movdqu  [rsp+730h+var_6C0], xmm1
0x180051f54  movups  [rbp+630h+var_690], xmm0
0x180051f58  xor     edx, edx; Val
0x180051f5a  mov     r8d, 208h; Size
0x180051f60  lea     rcx, [rbp+630h+var_680]; void *
0x180051f64  call    memset_0
0x180051f69  xor     edx, edx; Val
0x180051f6b  mov     r8d, 208h; Size
0x180051f71  lea     rcx, [rbp+630h+var_470]; void *
0x180051f78  call    memset_0
0x180051f7d  xor     edx, edx; Val
0x180051f7f  mov     r8d, 208h; Size
0x180051f85  lea     rcx, [rbp+630h+var_260]; void *
0x180051f8c  call    memset_0
0x180051f91  mov     [rsp+730h+var_6D0], 0
0x180051f9a  mov     [rsp+730h+var_6D8], 0
0x180051fa3  test    r12, r12
0x180051fa6  jnz     short loc_180051FB9
0x180051fa8  mov     ebx, 80070057h
0x180051fad  lea     rdi, WPP_GLOBAL_Control
0x180051fb4  jmp     loc_180052568
0x180051fb9  test    rbx, rbx
0x180051fbc  jz      short loc_180051FA8
0x180051fbe  test    r14, r14
0x180051fc1  jz      short loc_180051FA8
0x180051fc3  test    r15, r15
0x180051fc6  jz      short loc_180051FA8
0x180051fc8  test    rsi, rsi
0x180051fcb  jnz     short loc_180051FD4
0x180051fcd  mov     ebx, 80004003h
0x180051fd2  jmp     short loc_180051FAD
0x180051fd4  mov     r9, rsi; struct IPortableDeviceValues **
0x180051fd7  mov     r8, rdi; struct CProgressUI *
0x180051fda  mov     rdx, rbx; unsigned __int16 *
0x180051fdd  mov     rcx, r12; struct IPortableDevice *
0x180051fe0  call    ?_GetWpdProperties@@YAJPEAUIPortableDevice@@PEBGPEAVCProgressUI@@PEAPEAUIPortableDeviceValues@@@Z; _GetWpdProperties(IPortableDevice *,ushort const *,CProgressUI *,IPortableDeviceValues * *)
0x180051fe5  mov     ebx, eax
0x180051fe7  test    eax, eax
0x180051fe9  jns     short loc_180052016
0x180051feb  mov     rcx, cs:WPP_GLOBAL_Control
0x180051ff2  lea     rdi, WPP_GLOBAL_Control
0x180051ff9  cmp     rcx, rdi
0x180051ffc  jz      loc_180052593
0x180052002  test    byte ptr [rcx+1Ch], 2
0x180052006  jz      loc_18005256F
0x18005200c  mov     edx, 53h ; 'S'
0x180052011  jmp     loc_180052555
0x180052016  mov     rcx, [rsi]
0x180052019  test    rcx, rcx
0x18005201c  jnz     short loc_180052025
0x18005201e  mov     ebx, 8000FFFFh
0x180052023  jmp     short loc_180051FAD
0x180052025  mov     rax, [rcx]
0x180052028  lea     rdx, WPD_OBJECT_PERSISTENT_UNIQUE_ID
0x18005202f  mov     rax, [rax+138h]
0x180052036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005203b  mov     ebx, eax
0x18005203d  test    eax, eax
0x18005203f  jns     short loc_18005206C
0x180052041  mov     rcx, cs:WPP_GLOBAL_Control
0x180052048  lea     rdi, WPP_GLOBAL_Control
0x18005204f  cmp     rcx, rdi
0x180052052  jz      loc_180052593
0x180052058  test    byte ptr [rcx+1Ch], 2
0x18005205c  jz      loc_18005256F
0x180052062  mov     edx, 54h ; 'T'
0x180052067  jmp     loc_180052555
0x18005206c  mov     rcx, [rsi]
0x18005206f  mov     rax, [rcx]
0x180052072  lea     rdx, WPD_OBJECT_NAME
0x180052079  mov     rax, [rax+138h]
0x180052080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052085  mov     ebx, eax
0x180052087  test    eax, eax
0x180052089  jns     short loc_1800520B6
0x18005208b  mov     rcx, cs:WPP_GLOBAL_Control
0x180052092  lea     rdi, WPP_GLOBAL_Control
0x180052099  cmp     rcx, rdi
0x18005209c  jz      loc_180052593
0x1800520a2  test    byte ptr [rcx+1Ch], 2
0x1800520a6  jz      loc_18005256F
0x1800520ac  mov     edx, 55h ; 'U'
0x1800520b1  jmp     loc_180052555
0x1800520b6  mov     rcx, [rsi]
0x1800520b9  mov     rax, [rcx]
0x1800520bc  lea     rdx, WPD_OBJECT_ORIGINAL_FILE_NAME
0x1800520c3  mov     rax, [rax+138h]
0x1800520ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800520cf  mov     ebx, eax
0x1800520d1  test    eax, eax
0x1800520d3  jns     short loc_180052100
0x1800520d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800520dc  lea     rdi, WPP_GLOBAL_Control
0x1800520e3  cmp     rcx, rdi
0x1800520e6  jz      loc_180052593
0x1800520ec  test    byte ptr [rcx+1Ch], 2
0x1800520f0  jz      loc_18005256F
0x1800520f6  mov     edx, 56h ; 'V'
0x1800520fb  jmp     loc_180052555
0x180052100  mov     rcx, [rsi]
0x180052103  mov     rax, [rcx]
0x180052106  lea     rdx, WPD_OBJECT_NON_CONSUMABLE
0x18005210d  mov     rax, [rax+138h]
0x180052114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052119  mov     ebx, eax
0x18005211b  test    eax, eax
0x18005211d  jns     short loc_18005214A
0x18005211f  mov     rcx, cs:WPP_GLOBAL_Control
0x180052126  lea     rdi, WPP_GLOBAL_Control
0x18005212d  cmp     rcx, rdi
0x180052130  jz      loc_180052593
0x180052136  test    byte ptr [rcx+1Ch], 2
0x18005213a  jz      loc_18005256F
0x180052140  mov     edx, 57h ; 'W'
0x180052145  jmp     loc_180052555
0x18005214a  mov     rcx, [rsi]
0x18005214d  mov     rax, [rcx]
0x180052150  mov     r8, r14
0x180052153  lea     rdx, WPD_OBJECT_PARENT_ID
0x18005215a  mov     rax, [rax+38h]
0x18005215e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052163  mov     ebx, eax
0x180052165  test    eax, eax
0x180052167  jns     short loc_180052194
0x180052169  mov     rcx, cs:WPP_GLOBAL_Control
0x180052170  lea     rdi, WPP_GLOBAL_Control
0x180052177  cmp     rcx, rdi
0x18005217a  jz      loc_180052593
0x180052180  test    byte ptr [rcx+1Ch], 2
0x180052184  jz      loc_18005256F
0x18005218a  mov     edx, 58h ; 'X'
0x18005218f  jmp     loc_180052555
0x180052194  test    rdi, rdi
0x180052197  jnz     short loc_1800521E6
0x180052199  mov     rax, [r12]
0x18005219d  lea     rdx, [rsp+730h+var_6D0]
0x1800521a2  mov     rcx, r12
0x1800521a5  mov     rax, [rax+30h]
0x1800521a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800521ae  mov     ebx, eax
0x1800521b0  test    ebx, ebx
0x1800521b2  jns     loc_180052265
0x1800521b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800521bf  lea     rdi, WPP_GLOBAL_Control
0x1800521c6  cmp     rcx, rdi
0x1800521c9  jz      loc_180052593
0x1800521cf  test    byte ptr [rcx+1Ch], 2
0x1800521d3  jz      loc_18005256F
0x1800521d9  mov     edx, 59h ; 'Y'
0x1800521de  mov     r9d, ebx
0x1800521e1  jmp     loc_180052558
0x1800521e6  xor     r15d, r15d
0x1800521e9  xor     r14d, r14d
0x1800521ec  cmp     dword ptr [rdi+68h], 0
0x1800521f0  jnz     short loc_18005223F
0x1800521f2  mov     rax, [r12]
0x1800521f6  lea     rdx, [rsp+730h+var_6D0]
0x1800521fb  mov     rcx, r12
0x1800521fe  mov     rax, [rax+30h]
0x180052202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052207  mov     ebx, eax
0x180052209  cmp     eax, 800700AAh
0x18005220e  jnz     short loc_180052244
0x180052210  test    r15d, r15d
0x180052213  jnz     short loc_180052227
0x180052215  lea     eax, [r15+1]
0x180052219  mov     r15d, eax
0x18005221c  mov     r14d, eax
0x18005221f  mov     rcx, rdi; this
0x180052222  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x180052227  cmp     dword ptr [rdi+68h], 0
0x18005222b  jnz     short loc_18005223F
0x18005222d  mov     ecx, 5DCh; dwMilliseconds
0x180052232  call    cs:__imp_Sleep
0x180052238  test    r15d, r15d
0x18005223b  jz      short loc_180052244
0x18005223d  jmp     short loc_1800521EC
0x18005223f  mov     ebx, 800704C7h
0x180052244  test    r14d, r14d
0x180052247  jz      short loc_180052251
0x180052249  mov     rcx, rdi; this
0x18005224c  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x180052251  cmp     dword ptr [rdi+68h], 0
0x180052255  jz      loc_1800521B0
0x18005225b  mov     ebx, 800704C7h
0x180052260  jmp     loc_1800521B8
0x180052265  mov     rcx, [rsi]
0x180052268  mov     rax, [rcx]
0x18005226b  lea     r8, [rbp+630h+var_690]
0x18005226f  lea     rdx, WPD_OBJECT_FORMAT
0x180052276  mov     rax, [rax+0E0h]
0x18005227d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052282  test    eax, eax
0x180052284  js      short loc_180052290
0x180052286  movaps  xmm0, [rbp+630h+var_690]
0x18005228a  movdqa  [rsp+730h+var_6C0], xmm0
0x180052290  xor     r12d, r12d
0x180052293  test    rdi, rdi
0x180052296  jnz     short loc_1800522B8
0x180052298  mov     rcx, [rsp+730h+var_6D0]
0x18005229d  mov     rax, [rcx]
0x1800522a0  lea     r8, [rsp+730h+var_6D8]
0x1800522a5  lea     rdx, [rsp+730h+var_6C0]
0x1800522aa  mov     rax, [rax+48h]
0x1800522ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522b3  mov     r14d, eax
0x1800522b6  jmp     short loc_180052332
0x1800522b8  xor     r15d, r15d
0x1800522bb  xor     ebx, ebx
0x1800522bd  cmp     [rdi+68h], r12d
0x1800522c1  jnz     short loc_180052316
0x1800522c3  mov     rcx, [rsp+730h+var_6D0]
0x1800522c8  mov     rax, [rcx]
0x1800522cb  lea     r8, [rsp+730h+var_6D8]
0x1800522d0  lea     rdx, [rsp+730h+var_6C0]
0x1800522d5  mov     rax, [rax+48h]
0x1800522d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522de  mov     r14d, eax
0x1800522e1  cmp     eax, 800700AAh
0x1800522e6  jnz     short loc_18005231C
0x1800522e8  test    r15d, r15d
0x1800522eb  jnz     short loc_1800522FE
0x1800522ed  lea     eax, [r15+1]
0x1800522f1  mov     r15d, eax
0x1800522f4  mov     ebx, eax
0x1800522f6  mov     rcx, rdi; this
0x1800522f9  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x1800522fe  cmp     [rdi+68h], r12d
0x180052302  jnz     short loc_180052316
0x180052304  mov     ecx, 5DCh; dwMilliseconds
0x180052309  call    cs:__imp_Sleep
0x18005230f  test    r15d, r15d
0x180052312  jz      short loc_18005231C
0x180052314  jmp     short loc_1800522BD
0x180052316  mov     r14d, 800704C7h
0x18005231c  test    ebx, ebx
0x18005231e  jz      short loc_180052328
0x180052320  mov     rcx, rdi; this
0x180052323  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x180052328  cmp     [rdi+68h], r12d
0x18005232c  jnz     loc_1800523CF
0x180052332  test    r14d, r14d
0x180052335  js      loc_1800523CF
0x18005233b  mov     rcx, [rsp+730h+var_6D8]
0x180052340  mov     rax, [rcx]
0x180052343  lea     rdx, [rsp+730h+var_6E0]
0x180052348  mov     rax, [rax+18h]
0x18005234c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052351  mov     ebx, eax
0x180052353  test    eax, eax
0x180052355  jns     short loc_180052382
0x180052357  mov     rcx, cs:WPP_GLOBAL_Control
0x18005235e  lea     rdi, WPP_GLOBAL_Control
0x180052365  cmp     rcx, rdi
0x180052368  jz      loc_180052593
0x18005236e  test    byte ptr [rcx+1Ch], 2
0x180052372  jz      loc_18005256F
0x180052378  mov     edx, 5Ah ; 'Z'
0x18005237d  jmp     loc_180052555
0x180052382  xor     ebx, ebx
0x180052384  cmp     ebx, [rsp+730h+var_6E0]
0x180052388  jnb     short loc_1800523CF
0x18005238a  mov     rcx, [rsp+730h+var_6D8]
0x18005238f  mov     rax, [rcx]
0x180052392  lea     r8, [rbp+630h+Buf2]
0x180052396  mov     edx, ebx
0x180052398  mov     rax, [rax+20h]
0x18005239c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523a1  test    eax, eax
0x1800523a3  js      short loc_1800523C5
0x1800523a5  cmp     [rbp+630h+var_6A0], 0Ch
0x1800523a9  jnz     short loc_1800523C5
0x1800523ab  mov     r8d, 10h; Size
  ... truncated ...
```
