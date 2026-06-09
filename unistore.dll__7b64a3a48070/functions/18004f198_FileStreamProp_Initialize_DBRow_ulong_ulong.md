# FileStreamProp::Initialize(DBRow *,ulong,ulong)

- ea: `0x18004f198`
- end: `0x18004f7d8`
- name: `?Initialize@FileStreamProp@@AEAAJPEAVDBRow@@KK@Z`
- size: `1600`
- prototype: `__int64 __fastcall(FileStreamProp *__hidden this, struct DBRow *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18004effc`

## callees

- `0x1800068f0`
- `0x180013524`
- `0x180014bd0`
- `0x180028ef4`
- `0x18002995c`
- `0x180032170`
- `0x180034128`
- `0x1800396c8`
- `0x180039898`
- `0x18003bf70`
- `0x180044ca8`
- `0x18004dc88`
- `0x18004e8f8`
- `0x18004f198`
- `0x180057ab4`
- `0x1800686ec`
- `0x1800b0274`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f53c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004f53c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f54f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f54f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f589`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18004f396`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18004f396`

## string_xrefs

- `0x18004f21e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x18004f409`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x18004f474`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x18004f56a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x18004f5f1`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x18004f67e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\streamprop.cpp`
- `0x18004f63f`: `TempId`

## pseudocode

```c
__int64 __fastcall FileStreamProp::Initialize(FileStreamProp *this, struct IUnknown *a2, unsigned int a3, int a4)
{
  int v4; // r14d
  _QWORD *v5; // r12
  __int64 v9; // rcx
  _QWORD *v10; // rdi
  unsigned int v11; // ebx
  __int64 v12; // r9
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // ecx
  int v19; // eax
  unsigned __int16 **v20; // rbx
  unsigned __int16 *v21; // rdi
  unsigned int v22; // esi
  unsigned int v23; // r14d
  unsigned int v24; // eax
  int v25; // eax
  __int64 v26; // r9
  unsigned __int16 **v27; // rbx
  unsigned int v28; // edi
  unsigned int v29; // esi
  unsigned int v30; // eax
  __int64 v31; // rcx
  unsigned int StreamValidProp; // eax
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, __int64, unsigned int *, void **, int *); // rbx
  void **v35; // rax
  int v36; // eax
  struct _SECURITY_ATTRIBUTES *v37; // r9
  int v38; // ebx
  unsigned int v39; // edi
  unsigned int v40; // eax
  HANDLE v41; // rbx
  signed int LastError; // eax
  __int64 v43; // rcx
  void *v44; // rax
  unsigned __int16 **v45; // rbx
  unsigned int v46; // edi
  unsigned int v47; // esi
  unsigned int v48; // eax
  int v49; // eax
  __int64 v50; // r9
  __int64 v51; // rcx
  int v52; // eax
  DWORD v53; // ebx
  unsigned __int16 *v54; // rdx
  DWORD v55; // edi
  int FileAndPath; // eax
  __int64 v57; // rdx
  __int64 v58; // rcx
  LPCWSTR v59; // rdx
  DWORD v61[2]; // [rsp+20h] [rbp-E0h]
  int v62[2]; // [rsp+28h] [rbp-D8h]
  unsigned __int16 **v63; // [rsp+30h] [rbp-D0h]
  int DefaultStreamRootPath; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR pszPath; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v66; // [rsp+60h] [rbp-A0h] BYREF
  int v67; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v68; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v69; // [rsp+70h] [rbp-90h] BYREF
  HANDLE EventW; // [rsp+78h] [rbp-88h] BYREF
  int v71; // [rsp+80h] [rbp-80h]
  _WORD *v72; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v73; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v74[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Name[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v4 = 0;
  v5 = (_QWORD *)((char *)this + 24);
  v68 = a3;
  DefaultStreamRootPath = 0;
  if ( *((struct IUnknown **)this + 3) != a2 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 3, a2);
  v9 = *v5;
  v10 = (_QWORD *)((char *)this + 64);
  *((_DWORD *)this + 8) = a3;
  *((_DWORD *)this + 14) = a4;
  DefaultStreamRootPath = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v9 + 24LL))(v9, (char *)this + 64);
  v11 = DefaultStreamRootPath;
  if ( DefaultStreamRootPath >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 56LL))(*v10);
    v14 = *v10;
    v73 = 0;
    v67 = v13;
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v14 + 56LL))(v14) )
    {
      DefaultStreamRootPath = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(*(_QWORD *)*v10 + 104LL))(
                                *v10,
                                &v73);
      v11 = DefaultStreamRootPath;
      if ( DefaultStreamRootPath < 0 )
      {
        v12 = 1176;
        goto LABEL_5;
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 136LL))(*v10);
    }
    v15 = *v5;
    v66 = -1;
    v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD))(*(_QWORD *)v15 + 120LL))(v15, &v66, 0);
    if ( (v11 & 0x80000000) != 0 )
    {
      v12 = 1184;
      goto LABEL_5;
    }
    DefaultStreamRootPath = StreamHelper::GetDefaultStreamRootPath(v74, v16, v17);
    v11 = DefaultStreamRootPath;
    if ( DefaultStreamRootPath < 0 )
    {
      v12 = 1188;
      goto LABEL_5;
    }
    if ( (a4 & 1) != 0 )
    {
      v18 = 1;
      v71 = 1;
    }
    else
    {
      v18 = 0;
      v19 = 0;
      v71 = 0;
      if ( (a4 & 0x40000000) == 0 )
        goto LABEL_18;
    }
    v19 = 1;
LABEL_18:
    *((_DWORD *)this + 4) = v19;
    pszPath = 0;
    if ( !v18 )
    {
      v20 = (unsigned __int16 **)tlx::replace<unsigned short,&void _LocalFreer<unsigned short>(unsigned short *)>(&pszPath);
      v21 = v73;
      v22 = *((_DWORD *)this + 8);
      v23 = v66;
      v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 32LL))(*v5);
      v25 = StreamHelper::BuildStreamPropertyFilePath(v74, v24, v23, v22, v21, 0, v20);
      v4 = 0;
      DefaultStreamRootPath = v25;
      v11 = v25;
      if ( v25 < 0 )
      {
        v26 = 1208;
LABEL_25:
        v31 = (unsigned int)v25;
LABEL_26:
        Log_UnistoreHREvent_0(
          v31,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
          v26);
LABEL_70:
        auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&pszPath);
        return v11;
      }
      if ( v67 )
      {
        if ( !PathFileExistsW(pszPath) )
        {
          auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&pszPath);
          pszPath = 0;
          v27 = (unsigned __int16 **)tlx::replace<unsigned short,&void _LocalFreer<unsigned short>(unsigned short *)>(&pszPath);
          v28 = *((_DWORD *)this + 8);
          v29 = v66;
          v30 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 32LL))(*v5);
          v25 = StreamHelper::BuildStreamPropertyFilePath(v74, v30, v29, v28, 0, 0, v27);
          DefaultStreamRootPath = v25;
          v11 = v25;
          if ( v25 < 0 )
          {
            v26 = 1223;
            goto LABEL_25;
          }
        }
      }
    }
    v67 = 0;
    StreamValidProp = GetStreamValidProp(v68);
    v33 = *v5;
    v68 = StreamValidProp;
    v72 = 0;
    v34 = *(__int64 (__fastcall **)(__int64, __int64, unsigned int *, void **, int *))(*(_QWORD *)v33 + 40LL);
    v35 = tlx::replace<_USPROPVALEx *,void * (*)(void *),&void * LocalFree(void *),0>((void **)&v72);
    v36 = v34(v33, 1, &v68, v35, &v67);
    DefaultStreamRootPath = v36;
    v11 = v36;
    if ( v36 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v36,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
        1236);
      auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v72);
      goto LABEL_70;
    }
    if ( (v72[3] & 0x100) == 0 && *((_DWORD *)v72 + 2) )
      v4 = 1;
    if ( !*((_DWORD *)this + 4) && !v4 )
    {
      auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v72);
      goto LABEL_35;
    }
    *((_DWORD *)this + 18) = v4;
    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v72);
    if ( *((_DWORD *)this + 4) )
    {
      v38 = *((_DWORD *)this + 8);
      v39 = v66;
      v40 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 32LL))(*v5);
      v62[0] = v38;
      v61[0] = v39;
      v25 = StringCchPrintfW(Name, 0x104u, L"UnifiedStoreStreamEvent_%08x%08x%08x", v40, *(_QWORD *)v61, *(_QWORD *)v62);
      v11 = v25;
      if ( v25 < 0 )
      {
        v26 = 1261;
        goto LABEL_25;
      }
      EventW = CreateEventW(0, 0, 0, Name);
      v41 = EventW;
      if ( !EventW )
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        Log_UnistoreHREvent_0(
          v11,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
          1264);
        goto LABEL_43;
      }
      if ( GetLastError() == 183 )
      {
        v43 = 2147942405LL;
        DefaultStreamRootPath = -2147024891;
        if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x20) != 0 )
        {
          v44 = _t_address();
          EtwTraceMessage(&ETWMESSAGE, v44, pszPath, -2, &DefaultStreamRootPath, 4, 0, -1);
          v43 = (unsigned int)DefaultStreamRootPath;
        }
        Log_UnistoreHREvent_0(
          v43,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
          1272);
        v11 = DefaultStreamRootPath;
        goto LABEL_43;
      }
      EventW = (HANDLE)*((_QWORD *)this + 10);
      *((_QWORD *)this + 10) = v41;
      v69 = 0;
      v45 = (unsigned __int16 **)tlx::replace<unsigned short,&void _LocalFreer<unsigned short>(unsigned short *)>(&v69);
      v46 = *((_DWORD *)this + 8);
      v47 = v66;
      v48 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 32LL))(*v5);
      v49 = StreamHelper::BuildStreamPropertyFilePath(v74, v48, v47, v46, L"TempId", 0, v45);
      DefaultStreamRootPath = v49;
      v11 = v49;
      if ( v49 < 0 )
      {
        v50 = 1289;
        v51 = (unsigned int)v49;
LABEL_50:
        Log_UnistoreHREvent_0(
          v51,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
          v50);
        auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v69);
LABEL_43:
        tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&EventW);
        goto LABEL_70;
      }
      if ( v71 || !v4 )
      {
        *((_DWORD *)this + 9) = 1;
        v53 = 2;
      }
      else
      {
        v52 = StreamHelper::CopyFileExW(pszPath, v69);
        DefaultStreamRootPath = v52;
        v11 = v52;
        if ( v52 < 0 )
        {
          if ( (unsigned int)(v52 + 2147024894) > 1 )
          {
            v50 = 1314;
            v51 = (unsigned int)v52;
            goto LABEL_50;
          }
          DefaultStreamRootPath = 0;
        }
        v53 = 4;
      }
      v54 = v69;
      v69 = 0;
      tlx::auto_xxx<unsigned char *,void (*)(unsigned char *),&void _LocalFreer<unsigned char>(unsigned char *),0>::reset(
        &pszPath,
        v54);
      v55 = -1073741824;
      auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&v69);
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&EventW);
    }
    else
    {
      v55 = 0x80000000;
      v53 = 3;
    }
    FileAndPath = StreamHelper::CreateFileAndPath(
                    pszPath,
                    v55,
                    7u,
                    v37,
                    v53,
                    v62[0],
                    v63,
                    *((_DWORD *)this + 4),
                    (void **)this + 1);
    DefaultStreamRootPath = FileAndPath;
    v11 = FileAndPath;
    if ( FileAndPath >= 0 )
    {
      if ( *((_QWORD *)this + 1) == -1 )
        Log_AssertionEvent_17(v58, v57, 1345);
      if ( *((_DWORD *)this + 4) )
      {
        v59 = pszPath;
        pszPath = 0;
        tlx::auto_xxx<unsigned char *,void (*)(unsigned char *),&void _LocalFreer<unsigned char>(unsigned char *),0>::reset(
          (char *)this + 40,
          v59);
      }
      v11 = DefaultStreamRootPath;
      goto LABEL_70;
    }
    if ( *((_DWORD *)this + 4) || (unsigned int)(FileAndPath + 2147024894) > 1 )
    {
      v26 = 1342;
      v31 = (unsigned int)FileAndPath;
      goto LABEL_26;
    }
LABEL_35:
    v11 = -2147023728;
    goto LABEL_70;
  }
  v12 = 1167;
LABEL_5:
  Log_UnistoreHREvent_0(
    v11,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\streamprop.cpp",
    v12);
  return v11;
}

```

## disassembly

```asm
0x18004f198  mov     [rsp-8+arg_18], rbx
0x18004f19d  push    rbp
0x18004f19e  push    rsi
0x18004f19f  push    rdi
0x18004f1a0  push    r12
0x18004f1a2  push    r13
0x18004f1a4  push    r14
0x18004f1a6  push    r15
0x18004f1a8  lea     rbp, [rsp-3D0h]
0x18004f1b0  sub     rsp, 4D0h
0x18004f1b7  mov     rax, cs:__security_cookie
0x18004f1be  xor     rax, rsp
0x18004f1c1  mov     [rbp+400h+var_40], rax
0x18004f1c8  xor     r14d, r14d
0x18004f1cb  lea     r12, [rcx+18h]
0x18004f1cf  mov     ebx, r8d
0x18004f1d2  mov     esi, r9d
0x18004f1d5  mov     r13, rcx
0x18004f1d8  mov     [rsp+500h+var_498], ebx
0x18004f1dc  mov     [rsp+500h+var_4B0], r14d
0x18004f1e1  cmp     [r12], rdx
0x18004f1e5  jz      short loc_18004F1EF
0x18004f1e7  mov     rcx, r12; struct IUnknown **
0x18004f1ea  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18004f1ef  mov     rcx, [r12]
0x18004f1f3  lea     rdi, [r13+40h]
0x18004f1f7  mov     [r13+20h], ebx
0x18004f1fb  mov     rdx, rdi
0x18004f1fe  mov     [r13+38h], esi
0x18004f202  mov     rax, [rcx]
0x18004f205  mov     rax, [rax+18h]
0x18004f209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f20e  mov     [rsp+500h+var_4B0], eax
0x18004f212  mov     ebx, eax
0x18004f214  test    eax, eax
0x18004f216  jns     short loc_18004F236
0x18004f218  mov     r9d, 48Fh
0x18004f21e  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004f225  mov     edx, 1
0x18004f22a  mov     ecx, ebx
0x18004f22c  call    Log_UnistoreHREvent_0
0x18004f231  jmp     loc_18004F7AC
0x18004f236  mov     rcx, [rdi]
0x18004f239  mov     rax, [rcx]
0x18004f23c  mov     rax, [rax+38h]
0x18004f240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f245  mov     rcx, [rdi]
0x18004f248  mov     [rbp+400h+var_470], r14
0x18004f24c  mov     [rsp+500h+var_49C], eax
0x18004f250  mov     rdx, [rcx]
0x18004f253  mov     rax, [rdx+38h]
0x18004f257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f25c  test    eax, eax
0x18004f25e  jz      short loc_18004F297
0x18004f260  mov     rcx, [rdi]
0x18004f263  mov     rdx, [rcx]
0x18004f266  mov     rax, [rdx+68h]
0x18004f26a  lea     rdx, [rbp+400h+var_470]
0x18004f26e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f273  mov     [rsp+500h+var_4B0], eax
0x18004f277  mov     ebx, eax
0x18004f279  test    eax, eax
0x18004f27b  jns     short loc_18004F285
0x18004f27d  mov     r9d, 498h
0x18004f283  jmp     short loc_18004F21E
0x18004f285  mov     rcx, [rdi]
0x18004f288  mov     rax, [rcx]
0x18004f28b  mov     rax, [rax+88h]
0x18004f292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f297  mov     rcx, [r12]
0x18004f29b  lea     rdx, [rsp+500h+var_4A0]
0x18004f2a0  mov     [rsp+500h+var_4A0], 0FFFFFFFFh
0x18004f2a8  xor     r8d, r8d
0x18004f2ab  mov     rax, [rcx]
0x18004f2ae  mov     rax, [rax+78h]
0x18004f2b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2b7  mov     [rsp+500h+var_4B0], eax
0x18004f2bb  mov     ebx, eax
0x18004f2bd  test    eax, eax
0x18004f2bf  jns     short loc_18004F2CC
0x18004f2c1  mov     r9d, 4A0h
0x18004f2c7  jmp     loc_18004F21E
0x18004f2cc  lea     rcx, [rbp+400h+var_460]; unsigned __int16 *
0x18004f2d0  call    ?GetDefaultStreamRootPath@StreamHelper@@SAJPEAGK@Z; StreamHelper::GetDefaultStreamRootPath(ushort *,ulong)
0x18004f2d5  mov     [rsp+500h+var_4B0], eax
0x18004f2d9  mov     ebx, eax
0x18004f2db  test    eax, eax
0x18004f2dd  jns     short loc_18004F2EA
0x18004f2df  mov     r9d, 4A4h
0x18004f2e5  jmp     loc_18004F21E
0x18004f2ea  mov     eax, esi
0x18004f2ec  mov     r15d, 1
0x18004f2f2  and     eax, r15d
0x18004f2f5  test    al, al
0x18004f2f7  jz      short loc_18004F301
0x18004f2f9  mov     ecx, r15d
0x18004f2fc  mov     [rbp+400h+var_480], ecx
0x18004f2ff  jmp     short loc_18004F310
0x18004f301  mov     ecx, r14d
0x18004f304  mov     eax, r14d
0x18004f307  mov     [rbp+400h+var_480], ecx
0x18004f30a  bt      esi, 1Eh
0x18004f30e  jnb     short loc_18004F313
0x18004f310  mov     eax, r15d
0x18004f313  mov     [r13+10h], eax
0x18004f317  mov     [rsp+500h+pszPath], r14
0x18004f31c  test    ecx, ecx
0x18004f31e  jnz     loc_18004F41A
0x18004f324  lea     rcx, [rsp+500h+pszPath]
0x18004f329  call    ??$replace@G$1??$_LocalFreer@G@@YAXPEAG@Z@tlx@@YAPEAPEAGAEAV?$auto_ptr@G$1??$_LocalFreer@G@@YAXPEAG@Z@0@@Z; tlx::replace<ushort,&_LocalFreer<ushort>(ushort *)>(tlx::auto_ptr<ushort,&_LocalFreer<ushort>(ushort *)> &)
0x18004f32e  mov     rcx, [r12]
0x18004f332  mov     rbx, rax
0x18004f335  mov     rdi, [rbp+400h+var_470]
0x18004f339  mov     esi, [r13+20h]
0x18004f33d  mov     r14d, [rsp+500h+var_4A0]
0x18004f342  mov     rdx, [rcx]
0x18004f345  mov     rax, [rdx+20h]
0x18004f349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f34e  mov     [rsp+500h+var_4D0], rbx; unsigned __int16 **
0x18004f353  lea     rcx, [rbp+400h+var_460]; unsigned __int16 *
0x18004f357  mov     [rsp+500h+var_4D8], 0; int
0x18004f35f  mov     r9d, esi; unsigned int
0x18004f362  mov     r8d, r14d; unsigned int
0x18004f365  mov     qword ptr [rsp+500h+var_4E0], rdi; unsigned __int16 *
0x18004f36a  mov     edx, eax; unsigned int
0x18004f36c  call    ?BuildStreamPropertyFilePath@StreamHelper@@SAJPEBGKKK0HPEAPEAG@Z; StreamHelper::BuildStreamPropertyFilePath(ushort const *,ulong,ulong,ulong,ushort const *,int,ushort * *)
0x18004f371  xor     r14d, r14d
0x18004f374  mov     [rsp+500h+var_4B0], eax
0x18004f378  mov     ebx, eax
0x18004f37a  test    eax, eax
0x18004f37c  jns     short loc_18004F386
0x18004f37e  mov     r9d, 4B8h
0x18004f384  jmp     short loc_18004F404
0x18004f386  cmp     [rsp+500h+var_49C], r14d
0x18004f38b  jz      loc_18004F41A
0x18004f391  mov     rcx, [rsp+500h+pszPath]; pszPath
0x18004f396  call    cs:__imp_PathFileExistsW
0x18004f39c  test    eax, eax
0x18004f39e  jnz     short loc_18004F41A
0x18004f3a0  lea     rcx, [rsp+500h+pszPath]
0x18004f3a5  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18004f3aa  lea     rcx, [rsp+500h+pszPath]
0x18004f3af  mov     [rsp+500h+pszPath], r14
0x18004f3b4  call    ??$replace@G$1??$_LocalFreer@G@@YAXPEAG@Z@tlx@@YAPEAPEAGAEAV?$auto_ptr@G$1??$_LocalFreer@G@@YAXPEAG@Z@0@@Z; tlx::replace<ushort,&_LocalFreer<ushort>(ushort *)>(tlx::auto_ptr<ushort,&_LocalFreer<ushort>(ushort *)> &)
0x18004f3b9  mov     rcx, [r12]
0x18004f3bd  mov     rbx, rax
0x18004f3c0  mov     edi, [r13+20h]
0x18004f3c4  mov     esi, [rsp+500h+var_4A0]
0x18004f3c8  mov     rdx, [rcx]
0x18004f3cb  mov     rax, [rdx+20h]
0x18004f3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f3d4  mov     [rsp+500h+var_4D0], rbx; unsigned __int16 **
0x18004f3d9  lea     rcx, [rbp+400h+var_460]; unsigned __int16 *
0x18004f3dd  mov     [rsp+500h+var_4D8], r14d; int
0x18004f3e2  mov     r9d, edi; unsigned int
0x18004f3e5  mov     r8d, esi; unsigned int
0x18004f3e8  mov     qword ptr [rsp+500h+var_4E0], r14; unsigned __int16 *
0x18004f3ed  mov     edx, eax; unsigned int
0x18004f3ef  call    ?BuildStreamPropertyFilePath@StreamHelper@@SAJPEBGKKK0HPEAPEAG@Z; StreamHelper::BuildStreamPropertyFilePath(ushort const *,ulong,ulong,ulong,ushort const *,int,ushort * *)
0x18004f3f4  mov     [rsp+500h+var_4B0], eax
0x18004f3f8  mov     ebx, eax
0x18004f3fa  test    eax, eax
0x18004f3fc  jns     short loc_18004F41A
0x18004f3fe  mov     r9d, 4C7h
0x18004f404  mov     ecx, eax
0x18004f406  mov     edx, r15d
0x18004f409  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004f410  call    Log_UnistoreHREvent_0
0x18004f415  jmp     loc_18004F7A2
0x18004f41a  mov     ecx, [rsp+500h+var_498]; unsigned int
0x18004f41e  mov     [rsp+500h+var_49C], r14d
0x18004f423  call    ?GetStreamValidProp@@YAKK@Z; GetStreamValidProp(ulong)
0x18004f428  mov     rdi, [r12]
0x18004f42c  lea     rcx, [rbp+400h+var_478]
0x18004f430  mov     [rsp+500h+var_498], eax
0x18004f434  mov     [rbp+400h+var_478], r14
0x18004f438  mov     rax, [rdi]
0x18004f43b  mov     rbx, [rax+28h]
0x18004f43f  call    ??$replace@PEAU_USPROPVALEx@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAU_USPROPVALEx@@AEAV?$auto_xxx@PEAU_USPROPVALEx@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<_USPROPVALEx *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<_USPROPVALEx *,void * (*)(void *),&LocalFree(void *),0> &)
0x18004f444  lea     rcx, [rsp+500h+var_49C]
0x18004f449  mov     r9, rax
0x18004f44c  mov     qword ptr [rsp+500h+var_4E0], rcx
0x18004f451  lea     r8, [rsp+500h+var_498]
0x18004f456  mov     rcx, rdi
0x18004f459  mov     edx, r15d
0x18004f45c  mov     rax, rbx
0x18004f45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f464  mov     [rsp+500h+var_4B0], eax
0x18004f468  mov     ebx, eax
0x18004f46a  test    eax, eax
0x18004f46c  jns     short loc_18004F493
0x18004f46e  mov     r9d, 4D4h
0x18004f474  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004f47b  mov     edx, r15d
0x18004f47e  mov     ecx, eax
0x18004f480  call    Log_UnistoreHREvent_0
0x18004f485  lea     rcx, [rbp+400h+var_478]
0x18004f489  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18004f48e  jmp     loc_18004F7A2
0x18004f493  mov     rax, [rbp+400h+var_478]
0x18004f497  mov     ecx, 100h
0x18004f49c  test    [rax+6], cx
0x18004f4a0  jnz     short loc_18004F4AB
0x18004f4a2  cmp     [rax+8], r14d
0x18004f4a6  jz      short loc_18004F4AB
0x18004f4a8  mov     r14d, r15d
0x18004f4ab  xor     esi, esi
0x18004f4ad  cmp     [r13+10h], esi
0x18004f4b1  jnz     short loc_18004F4CB
0x18004f4b3  test    r14d, r14d
0x18004f4b6  jnz     short loc_18004F4CB
0x18004f4b8  lea     rcx, [rbp+400h+var_478]
0x18004f4bc  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18004f4c1  mov     ebx, 80070490h
0x18004f4c6  jmp     loc_18004F7A2
0x18004f4cb  lea     rcx, [rbp+400h+var_478]
0x18004f4cf  mov     [r13+48h], r14d
0x18004f4d3  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18004f4d8  cmp     [r13+10h], esi
0x18004f4dc  jz      loc_18004F715
0x18004f4e2  mov     rcx, [r12]
0x18004f4e6  mov     ebx, [r13+20h]
0x18004f4ea  mov     edi, [rsp+500h+var_4A0]
0x18004f4ee  mov     rax, [rcx]
0x18004f4f1  mov     rax, [rax+20h]
0x18004f4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f4fa  mov     r9d, eax
0x18004f4fd  mov     [rsp+500h+var_4D8], ebx
0x18004f501  lea     r8, aUnifiedstorest; "UnifiedStoreStreamEvent_%08x%08x%08x"
0x18004f508  mov     [rsp+500h+var_4E0], edi
0x18004f50c  mov     edx, 104h; unsigned __int64
0x18004f511  lea     rcx, [rbp+400h+Name]; unsigned __int16 *
0x18004f518  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f51d  mov     ebx, eax
0x18004f51f  test    eax, eax
0x18004f521  jns     short loc_18004F52E
0x18004f523  mov     r9d, 4EDh
0x18004f529  jmp     loc_18004F404
0x18004f52e  lea     r9, [rbp+400h+Name]; lpName
0x18004f535  xor     r8d, r8d; bInitialState
0x18004f538  xor     edx, edx; bManualReset
0x18004f53a  xor     ecx, ecx; lpEventAttributes
0x18004f53c  call    cs:__imp_CreateEventW
0x18004f542  mov     [rsp+500h+var_488], rax
0x18004f547  mov     rbx, rax
0x18004f54a  test    rax, rax
0x18004f54d  jnz     short loc_18004F589
0x18004f54f  call    cs:__imp_GetLastError
0x18004f555  mov     ebx, eax
0x18004f557  test    eax, eax
0x18004f559  jle     short loc_18004F564
0x18004f55b  movzx   ebx, ax
0x18004f55e  or      ebx, 80070000h
0x18004f564  mov     r9d, 4F0h
0x18004f56a  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004f571  xor     edx, edx
0x18004f573  mov     ecx, ebx
0x18004f575  call    Log_UnistoreHREvent_0
0x18004f57a  lea     rcx, [rsp+500h+var_488]
0x18004f57f  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18004f584  jmp     loc_18004F7A2
0x18004f589  call    cs:__imp_GetLastError
0x18004f58f  cmp     eax, 0B7h
0x18004f594  jnz     short loc_18004F608
0x18004f596  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits, 20h
0x18004f59d  mov     ecx, 80070005h
0x18004f5a2  mov     [rsp+500h+var_4B0], ecx
0x18004f5a6  jz      short loc_18004F5EB
0x18004f5a8  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18004f5ad  mov     r8, [rsp+500h+pszPath]
0x18004f5b2  lea     rcx, [rsp+500h+var_4B0]
0x18004f5b7  mov     qword ptr [rsp+500h+var_4C8], 0FFFFFFFFFFFFFFFFh
0x18004f5c0  mov     ebx, 4
0x18004f5c5  mov     [rsp+500h+var_4D0], rsi
0x18004f5ca  mov     rdx, rax; void *
0x18004f5cd  mov     qword ptr [rsp+500h+var_4D8], rbx
0x18004f5d2  mov     qword ptr [rsp+500h+var_4E0], rcx
0x18004f5d7  lea     rcx, _ETWMESSAGE; EventDescriptor
0x18004f5de  lea     r9, [rbx-6]
0x18004f5e2  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x18004f5e7  mov     ecx, [rsp+500h+var_4B0]
0x18004f5eb  mov     r9d, 4F8h
0x18004f5f1  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004f5f8  xor     edx, edx
0x18004f5fa  call    Log_UnistoreHREvent_0
0x18004f5ff  mov     ebx, [rsp+500h+var_4B0]
0x18004f603  jmp     loc_18004F57A
0x18004f608  mov     rax, [r13+50h]
0x18004f60c  lea     rcx, [rsp+500h+var_490]
0x18004f611  mov     [rsp+500h+var_488], rax
0x18004f616  mov     [r13+50h], rbx
0x18004f61a  mov     [rsp+500h+var_490], rsi
0x18004f61f  call    ??$replace@G$1??$_LocalFreer@G@@YAXPEAG@Z@tlx@@YAPEAPEAGAEAV?$auto_ptr@G$1??$_LocalFreer@G@@YAXPEAG@Z@0@@Z; tlx::replace<ushort,&_LocalFreer<ushort>(ushort *)>(tlx::auto_ptr<ushort,&_LocalFreer<ushort>(ushort *)> &)
0x18004f624  mov     rcx, [r12]
0x18004f628  mov     rbx, rax
0x18004f62b  mov     edi, [r13+20h]
0x18004f62f  mov     esi, [rsp+500h+var_4A0]
0x18004f633  mov     rdx, [rcx]
0x18004f636  mov     rax, [rdx+20h]
0x18004f63a  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
