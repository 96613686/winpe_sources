# CThumbnailMoniker::_NormalizeNonUNCPathUrl(IPropertyStore *,ushort const *,ushort const *,ushort * *)

- ea: `0x180022040`
- end: `0x18002251b`
- name: `?_NormalizeNonUNCPathUrl@CThumbnailMoniker@@CAJPEAUIPropertyStore@@PEBG1PEAPEAG@Z`
- size: `1243`
- prototype: `static int(struct IPropertyStore *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180021e40`

## callees

- `0x180003624`
- `0x18000b3c0`
- `0x180022040`
- `0x180022524`
- `0x1800275f8`
- `0x180035830`
- `0x1800364ac`
- `0x180049010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18002242e`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18002242e`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800220d3`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800220d3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180022498`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180022498`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800220b1`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800220b1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x180022106`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x180022106`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800220f5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800220f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800221af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800221cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800221cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CThumbnailMoniker::_NormalizeNonUNCPathUrl(
        struct IPropertyStore *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  LPWSTR v7; // rdi
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // rax
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rsi
  _WORD *v15; // r15
  unsigned __int64 v16; // r14
  int v17; // ebx
  _WORD *v18; // rax
  _WORD *v19; // rsi
  int v20; // r11d
  __int16 *v21; // rax
  __int64 v22; // rdx
  unsigned __int64 v23; // r8
  _WORD *v24; // r9
  __int64 v25; // r10
  __int16 v26; // cx
  __int64 v27; // rdx
  _WORD *v28; // rcx
  _WORD *v29; // rcx
  unsigned __int64 v30; // rax
  unsigned __int16 *v31; // rax
  HRESULT (__stdcall *QueryInterface)(IPropertyStore *, const IID *const, void **); // rbx
  int FileId; // ebx
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, const PROPERTYKEY *, __int64, _QWORD, GUID *, __int64 *); // rbx
  __int64 v36; // rcx
  unsigned __int64 v37; // rax
  GUID fmtid; // [rsp+40h] [rbp-C0h] BYREF
  _WORD *v39; // [rsp+50h] [rbp-B0h]
  const wchar_t *v40; // [rsp+58h] [rbp-A8h]
  LPWSTR v41; // [rsp+60h] [rbp-A0h]
  DWORD VolumeSerialNumber; // [rsp+70h] [rbp-90h] BYREF
  __int64 v43; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v45; // [rsp+88h] [rbp-78h] BYREF
  _WORD v46[12]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v47[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v48; // [rsp+C8h] [rbp-38h]
  WCHAR FileSystemNameBuffer[32]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR VolumeNameBuffer[268]; // [rsp+110h] [rbp+10h] BYREF

  *a4 = 0;
  VolumeSerialNumber = 0;
  if ( !GetVolumeInformationW(a3, VolumeNameBuffer, 0x104u, &VolumeSerialNumber, 0, 0, FileSystemNameBuffer, 0x20u) )
    return ResultFromKnownLastError();
  _o__ultow_s(VolumeSerialNumber, v46, 9, 16);
  memset(v47, 0, sizeof(v47));
  v48 = 0;
  if ( StrCmpICW(FileSystemNameBuffer, L"NTFS") )
  {
    v7 = PathSkipRootW(a2);
  }
  else
  {
    v45 = 0;
    if ( a1 )
    {
      v44 = 0;
      v43 = 0;
      QueryInterface = a1->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
      FileId = ((__int64 (__fastcall *)(struct IPropertyStore *, GUID *, __int64 *))QueryInterface)(
                 a1,
                 &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
                 &v43);
      if ( FileId >= 0 )
      {
        v34 = v43;
        v35 = *(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v43 + 80LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
        FileId = v35(v34, &PKEY_FileFRN, 1, 0, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v44);
      }
      v36 = v43;
      if ( v43 )
      {
        v43 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      }
      if ( FileId >= 0 )
      {
        fmtid = PKEY_FileFRN.fmtid;
        LODWORD(v39) = PKEY_FileFRN.pid;
        FileId = wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt64<_tagpropertykey>(&v44, &fmtid, &v45);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
      if ( FileId >= 0 )
        goto LABEL_55;
    }
    FileId = GetFileId(a2, &v45);
    if ( FileId >= 0 )
    {
LABEL_55:
      _o__ui64tow_s(v45, v47, 17, 16);
      v7 = (LPWSTR)v47;
    }
    else
    {
      v7 = 0;
      OutputDebugStringW(L"Unable to get NTFS id\n");
    }
    if ( FileId < 0 )
      return (unsigned int)FileId;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( VolumeNameBuffer[v9] );
  v10 = v9 + 4;
  if ( v9 >= 0xFFFFFFFFFFFFFFFCuLL )
    return 2147942934LL;
  v11 = -1;
  do
    ++v11;
  while ( v46[v11] );
  v12 = v11 + v10;
  if ( v11 + v10 < v10 )
    return 2147942934LL;
  if ( v7 )
  {
    do
      ++v8;
    while ( v7[v8] );
  }
  else
  {
    v8 = 0;
  }
  v13 = v12 + v8;
  if ( v12 + v8 < v12 )
    return 2147942934LL;
  v15 = 0;
  v16 = v13 + 1;
  if ( v13 + 1 >= v13 && (v15 = 0, is_mul_ok(v16, 2u)) )
  {
    v18 = CoTaskMemAlloc(2 * v16);
    v15 = v18;
    if ( v18 )
      v17 = 0;
    else
      v17 = -2147024882;
    if ( v17 >= 0 )
    {
      if ( (v18 || v13 == -1) && v16 <= 0x7FFFFFFF )
      {
        if ( v13 >= 0x7FFFFFFF )
        {
          if ( v13 != -1 )
            *v18 = 0;
        }
        else
        {
          *v18 = 0;
          v37 = v13 + 1;
          if ( v16 > 1 && 2 * v37 > 2 )
            memset_0(v15 + 1, 0, 2 * v37 - 2);
        }
      }
      else
      {
        *v18 = 0;
      }
      v19 = v15;
      v17 = 0;
      *(_QWORD *)&fmtid.Data1 = VolumeNameBuffer;
      *(_QWORD *)fmtid.Data4 = L"?";
      v39 = v46;
      v40 = L"?";
      v41 = v7;
      v20 = 0;
      while ( v17 >= 0 )
      {
        v21 = (__int16 *)*((_QWORD *)&fmtid.Data1 + v20);
        if ( v21 )
        {
          if ( !v16 )
          {
            v29 = 0;
            v30 = 0;
            v17 = -2147024809;
LABEL_41:
            if ( v17 >= 0 )
            {
              v19 = v29;
              v16 = v30;
            }
            goto LABEL_43;
          }
          if ( v16 <= 0x7FFFFFFF )
          {
            v22 = 2147483646;
            v23 = v16;
            v24 = v19;
            v25 = 0;
            do
            {
              if ( !v22 )
                break;
              v26 = *v21;
              if ( !*v21 )
                break;
              ++v21;
              *v24++ = v26;
              --v22;
              ++v25;
              --v23;
            }
            while ( v23 );
            v27 = v25 - 1;
            if ( v23 )
              v27 = v25;
            v28 = v24 - 1;
            if ( v23 )
              v28 = v24;
            *v28 = 0;
            v17 = -2147024774;
            if ( v23 )
              v17 = 0;
            v29 = &v19[v27];
            v30 = v16 - v27;
            goto LABEL_41;
          }
          *v19 = 0;
          v17 = -2147024809;
        }
LABEL_43:
        if ( (unsigned int)++v20 >= 5 )
        {
          if ( v17 >= 0 )
          {
            v31 = v15;
            v15 = 0;
            *a4 = v31;
          }
          break;
        }
      }
    }
  }
  else
  {
    v17 = -2147024362;
  }
  CoTaskMemFree(v15);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180022040  push    rbp
0x180022042  push    rbx
0x180022043  push    rsi
0x180022044  push    rdi
0x180022045  push    r12
0x180022047  push    r13
0x180022049  push    r14
0x18002204b  push    r15
0x18002204d  lea     rbp, [rsp-238h]
0x180022055  sub     rsp, 338h
0x18002205c  mov     rax, cs:__security_cookie
0x180022063  xor     rax, rsp
0x180022066  mov     [rbp+270h+var_48], rax
0x18002206d  mov     r12, r9
0x180022070  mov     rax, r8
0x180022073  mov     rsi, rdx
0x180022076  mov     rdi, rcx
0x180022079  xor     r13d, r13d
0x18002207c  mov     [r9], r13
0x18002207f  mov     [rsp+370h+VolumeSerialNumber], r13d
0x180022084  mov     [rsp+370h+nFileSystemNameSize], 20h ; ' '; nFileSystemNameSize
0x18002208c  lea     rcx, [rbp+270h+FileSystemNameBuffer]
0x180022090  mov     [rsp+370h+lpFileSystemNameBuffer], rcx; lpFileSystemNameBuffer
0x180022095  mov     [rsp+370h+lpFileSystemFlags], r13; lpFileSystemFlags
0x18002209a  mov     [rsp+370h+lpMaximumComponentLength], r13; lpMaximumComponentLength
0x18002209f  lea     r9, [rsp+370h+VolumeSerialNumber]; lpVolumeSerialNumber
0x1800220a4  mov     r8d, 104h; nVolumeNameSize
0x1800220aa  lea     rdx, [rbp+270h+VolumeNameBuffer]; lpVolumeNameBuffer
0x1800220ae  mov     rcx, rax; lpRootPathName
0x1800220b1  call    cs:__imp_GetVolumeInformationW
0x1800220b7  test    eax, eax
0x1800220b9  jz      loc_180022511
0x1800220bf  mov     r9d, 10h
0x1800220c5  mov     r8d, 9
0x1800220cb  lea     rdx, [rbp+270h+var_2E0]
0x1800220cf  mov     ecx, [rsp+370h+VolumeSerialNumber]
0x1800220d3  call    cs:__imp__o__ultow_s
0x1800220d9  xorps   xmm0, xmm0
0x1800220dc  xor     eax, eax
0x1800220de  movups  [rbp+270h+var_2C8], xmm0
0x1800220e2  movups  [rbp+270h+var_2B8], xmm0
0x1800220e6  mov     [rbp+270h+var_2A8], ax
0x1800220ea  lea     rdx, pszStr2; "NTFS"
0x1800220f1  lea     rcx, [rbp+270h+FileSystemNameBuffer]; pszStr1
0x1800220f5  call    cs:__imp_StrCmpICW
0x1800220fb  test    eax, eax
0x1800220fd  jz      loc_18002234D
0x180022103  mov     rcx, rsi; pszPath
0x180022106  call    cs:__imp_PathSkipRootW
0x18002210c  mov     rdi, rax
0x18002210f  lea     rax, [rbp+270h+VolumeNameBuffer]
0x180022113  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002211a  mov     rdx, rcx
0x18002211d  nop     dword ptr [rax]
0x180022120  lea     rdx, [rdx+1]
0x180022124  cmp     word ptr [rax+rdx*2], 0
0x180022129  jnz     short loc_180022120
0x18002212b  lea     r8, [rdx+4]
0x18002212f  cmp     r8, 4
0x180022133  jb      short loc_180022173
0x180022135  lea     rdx, [rbp+270h+var_2E0]
0x180022139  mov     rax, rcx
0x18002213c  nop     dword ptr [rax+00h]
0x180022140  lea     rax, [rax+1]
0x180022144  cmp     word ptr [rdx+rax*2], 0
0x180022149  jnz     short loc_180022140
0x18002214b  lea     rdx, [rax+r8]
0x18002214f  cmp     rdx, r8
0x180022152  jb      short loc_180022173
0x180022154  test    rdi, rdi
0x180022157  jz      loc_180022486
0x18002215d  nop     dword ptr [rax]
0x180022160  inc     rcx
0x180022163  cmp     word ptr [rdi+rcx*2], 0
0x180022168  jnz     short loc_180022160
0x18002216a  lea     rsi, [rdx+rcx]
0x18002216e  cmp     rsi, rdx
0x180022171  jnb     short loc_18002219B
0x180022173  mov     eax, 80070216h
0x180022178  mov     rcx, [rbp+270h+var_48]
0x18002217f  xor     rcx, rsp; StackCookie
0x180022182  call    __security_check_cookie
0x180022187  add     rsp, 338h
0x18002218e  pop     r15
0x180022190  pop     r14
0x180022192  pop     r13
0x180022194  pop     r12
0x180022196  pop     rdi
0x180022197  pop     rsi
0x180022198  pop     rbx
0x180022199  pop     rbp
0x18002219a  retn
0x18002219b  mov     r15, r13
0x18002219e  lea     r14, [rsi+1]
0x1800221a2  cmp     r14, rsi
0x1800221a5  jnb     short loc_1800221B9
0x1800221a7  mov     ebx, 80070216h
0x1800221ac  mov     rcx, r15; pv
0x1800221af  call    cs:__imp_CoTaskMemFree
0x1800221b5  mov     eax, ebx
0x1800221b7  jmp     short loc_180022178
0x1800221b9  mov     r15, r13
0x1800221bc  mov     eax, 2
0x1800221c1  mul     r14
0x1800221c4  test    rdx, rdx
0x1800221c7  jnz     short loc_1800221A7
0x1800221c9  mov     rcx, rax; cb
0x1800221cc  call    cs:__imp_CoTaskMemAlloc
0x1800221d2  mov     r15, rax
0x1800221d5  test    rax, rax
0x1800221d8  jz      loc_18002247C
0x1800221de  mov     ebx, r13d
0x1800221e1  test    ebx, ebx
0x1800221e3  js      short loc_1800221AC
0x1800221e5  test    r15, r15
0x1800221e8  jz      loc_1800224CF
0x1800221ee  cmp     r14, 7FFFFFFFh
0x1800221f5  ja      loc_1800224D8
0x1800221fb  cmp     rsi, 7FFFFFFFh
0x180022202  jnb     loc_1800224E1
0x180022208  test    r14, r14
0x18002220b  jz      short loc_180022264
0x18002220d  mov     rcx, r13
0x180022210  lea     r8, unk_1800509F8
0x180022217  mov     rdx, r14
0x18002221a  mov     r10, r13
0x18002221d  nop     dword ptr [rax]
0x180022220  test    rcx, rcx
0x180022223  jz      short loc_180022247
0x180022225  movzx   r9d, word ptr [r8]
0x180022229  test    r9w, r9w
0x18002222d  jz      short loc_180022247
0x18002222f  add     r8, 2
0x180022233  mov     [rax], r9w
0x180022237  add     rax, 2
0x18002223b  dec     rcx
0x18002223e  inc     r10
0x180022241  sub     rdx, 1
0x180022245  jnz     short loc_180022220
0x180022247  lea     r9, [r10-1]
0x18002224b  test    rdx, rdx
0x18002224e  cmovnz  r9, r10
0x180022252  lea     rcx, [rax-2]
0x180022256  cmovnz  rcx, rax
0x18002225a  mov     [rcx], r13w
0x18002225e  jnz     loc_180022447
0x180022264  mov     rsi, r15
0x180022267  mov     ebx, r13d
0x18002226a  lea     rax, [rbp+270h+VolumeNameBuffer]
0x18002226e  mov     qword ptr [rsp+370h+var_330], rax
0x180022273  lea     rcx, asc_180050704; "?"
0x18002227a  mov     qword ptr [rsp+370h+var_330+8], rcx
0x18002227f  lea     rax, [rbp+270h+var_2E0]
0x180022283  mov     [rsp+370h+var_320], rax
0x180022288  mov     [rsp+370h+var_318], rcx
0x18002228d  mov     [rsp+370h+var_310], rdi
0x180022292  mov     r11d, r13d
0x180022295  test    ebx, ebx
0x180022297  js      loc_1800221AC
0x18002229d  movsxd  rax, r11d
0x1800222a0  mov     rax, qword ptr [rsp+rax*8+370h+var_330]
0x1800222a5  test    rax, rax
0x1800222a8  jz      short loc_180022329
0x1800222aa  test    r14, r14
0x1800222ad  jz      loc_180022501
0x1800222b3  cmp     r14, 7FFFFFFFh
0x1800222ba  ja      loc_1800224F3
0x1800222c0  mov     edx, 7FFFFFFEh
0x1800222c5  mov     r8, r14
0x1800222c8  mov     r9, rsi
0x1800222cb  mov     r10, r13
0x1800222ce  xchg    ax, ax
0x1800222d0  test    rdx, rdx
0x1800222d3  jz      short loc_1800222F5
0x1800222d5  movzx   ecx, word ptr [rax]
0x1800222d8  test    cx, cx
0x1800222db  jz      short loc_1800222F5
0x1800222dd  add     rax, 2
0x1800222e1  mov     [r9], cx
0x1800222e5  add     r9, 2
0x1800222e9  dec     rdx
0x1800222ec  inc     r10
0x1800222ef  sub     r8, 1
0x1800222f3  jnz     short loc_1800222D0
0x1800222f5  lea     rdx, [r10-1]
0x1800222f9  test    r8, r8
0x1800222fc  cmovnz  rdx, r10
0x180022300  lea     rcx, [r9-2]
0x180022304  cmovnz  rcx, r9
0x180022308  mov     [rcx], r13w
0x18002230c  mov     ebx, 8007007Ah
0x180022311  cmovnz  ebx, r13d
0x180022315  lea     rcx, [rsi+rdx*2]
0x180022319  mov     rax, r14
0x18002231c  sub     rax, rdx
0x18002231f  test    ebx, ebx
0x180022321  js      short loc_180022329
0x180022323  mov     rsi, rcx
0x180022326  mov     r14, rax
0x180022329  inc     r11d
0x18002232c  cmp     r11d, 5
0x180022330  jb      loc_180022295
0x180022336  test    ebx, ebx
0x180022338  js      loc_1800221AC
0x18002233e  mov     rax, r15
0x180022341  mov     r15, r13
0x180022344  mov     [r12], rax
0x180022348  jmp     loc_1800221AC
0x18002234d  mov     [rbp+270h+var_2E8], r13
0x180022351  test    rdi, rdi
0x180022354  jz      loc_180022408
0x18002235a  mov     [rbp+270h+var_2F0], r13
0x18002235e  mov     [rsp+370h+var_2F8], r13
0x180022363  mov     rax, [rdi]
0x180022366  mov     rbx, [rax]
0x180022369  lea     rcx, [rsp+370h+var_2F8]
0x18002236e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022373  lea     r8, [rsp+370h+var_2F8]
0x180022378  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x18002237f  mov     rcx, rdi
0x180022382  mov     rax, rbx
0x180022385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002238a  mov     ebx, eax
0x18002238c  test    eax, eax
0x18002238e  js      short loc_1800223D7
0x180022390  mov     rdi, [rsp+370h+var_2F8]
0x180022395  mov     rax, [rdi]
0x180022398  mov     rbx, [rax+50h]
0x18002239c  lea     rcx, [rbp+270h+var_2F0]
0x1800223a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800223a5  lea     rax, [rbp+270h+var_2F0]
0x1800223a9  mov     [rsp+370h+lpFileSystemFlags], rax
0x1800223ae  lea     rax, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1800223b5  mov     [rsp+370h+lpMaximumComponentLength], rax
0x1800223ba  xor     r9d, r9d
0x1800223bd  mov     r8d, 1
0x1800223c3  lea     rdx, PKEY_FileFRN
0x1800223ca  mov     rcx, rdi
0x1800223cd  mov     rax, rbx
0x1800223d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223d5  mov     ebx, eax
0x1800223d7  mov     rcx, [rsp+370h+var_2F8]
0x1800223dc  test    rcx, rcx
0x1800223df  jz      short loc_1800223F3
0x1800223e1  mov     [rsp+370h+var_2F8], r13
0x1800223e6  mov     rax, [rcx]
0x1800223e9  mov     rax, [rax+10h]
0x1800223ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223f2  nop
0x1800223f3  test    ebx, ebx
0x1800223f5  jns     loc_1800224A0
0x1800223fb  lea     rcx, [rbp+270h+var_2F0]
0x1800223ff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022404  test    ebx, ebx
0x180022406  jns     short loc_18002241A
0x180022408  lea     rdx, [rbp+270h+var_2E8]; unsigned __int64 *
0x18002240c  mov     rcx, rsi; unsigned __int16 *
0x18002240f  call    ?GetFileId@@YAJPEBGPEA_K@Z; GetFileId(ushort const *,unsigned __int64 *)
0x180022414  mov     ebx, eax
0x180022416  test    eax, eax
0x180022418  js      short loc_18002248E
0x18002241a  mov     r9d, 10h
0x180022420  mov     r8d, 11h
0x180022426  lea     rdx, [rbp+270h+var_2C8]
0x18002242a  mov     rcx, [rbp+270h+var_2E8]
0x18002242e  call    cs:__imp__o__ui64tow_s
0x180022434  lea     rdi, [rbp+270h+var_2C8]
0x180022438  test    ebx, ebx
0x18002243a  jns     loc_18002210F
0x180022440  mov     eax, ebx
0x180022442  jmp     loc_180022178
0x180022447  mov     rax, r14
0x18002244a  sub     rax, r9
0x18002244d  cmp     rax, 1
0x180022451  jbe     loc_180022264
0x180022457  lea     r8, [rax+rax]
0x18002245b  cmp     r8, 2
0x18002245f  jbe     loc_180022264
0x180022465  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180022469  inc     r9
0x18002246c  lea     rcx, [r15+r9*2]; void *
0x180022470  xor     edx, edx; Val
0x180022472  call    memset_0
0x180022477  jmp     loc_180022264
0x18002247c  mov     ebx, 8007000Eh
0x180022481  jmp     loc_1800221E1
0x180022486  mov     rcx, r13
0x180022489  jmp     loc_18002216A
0x18002248e  mov     rdi, r13
0x180022491  lea     rcx, aUnableToGetNtf; "Unable to get NTFS id\n"
0x180022498  call    cs:__imp_OutputDebugStringW
0x18002249e  jmp     short loc_180022438
0x1800224a0  movups  xmm0, xmmword ptr cs:PKEY_FileFRN.fmtid.Data1
0x1800224a7  movaps  [rsp+370h+var_330], xmm0
0x1800224ac  mov     eax, cs:PKEY_FileFRN.pid
0x1800224b2  mov     dword ptr [rsp+370h+var_320], eax
0x1800224b6  lea     r8, [rbp+270h+var_2E8]
0x1800224ba  lea     rdx, [rsp+370h+var_330]
0x1800224bf  lea     rcx, [rbp+270h+var_2F0]
0x1800224c3  call    ??$GetUInt64@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEA_K@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt64<_tagpropertykey>(_tagpropertykey,unsigned __int64 *)
  ... truncated ...
```
