# SendToArchive::Drop(IDataObject *,ulong,_POINTL,ulong *)

- ea: `0x18004e3d0`
- end: `0x18004e946`
- name: `?Drop@SendToArchive@@UEAAJPEAUIDataObject@@KU_POINTL@@PEAK@Z`
- size: `1398`
- prototype: `__int64 __fastcall(SendToArchive *this, struct IDataObject *, __int64, struct _POINTL, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180031e94`
- `0x18003519c`
- `0x18003534c`
- `0x180035394`
- `0x180036f50`
- `0x18004dca4`
- `0x18004dfcc`
- `0x18004e3d0`
- `0x18004f308`
- `0x18004f418`
- `0x18004f448`
- `0x18005d9e4`
- `0x180071010`

## import_xrefs

- `SHELL32!DragQueryFileW` at `0x18004e51f`
- `SHELL32!DragQueryFileW` at `0x18004e5a8`
- `SHELL32!DragQueryFileW` at `0x18004e62f`
- `SHELL32!DragQueryFileW` at `0x18004e51f`
- `SHELL32!DragQueryFileW` at `0x18004e5a8`
- `SHELL32!DragQueryFileW` at `0x18004e62f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e672`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e6d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e71b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e672`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e6d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e71b`
- `KERNEL32!GlobalLock` at `0x18004e4f4`
- `KERNEL32!GlobalLock` at `0x18004e4f4`
- `ole32!ReleaseStgMedium` at `0x18004e4dc`
- `ole32!ReleaseStgMedium` at `0x18004e561`
- `ole32!ReleaseStgMedium` at `0x18004e5f9`
- `ole32!ReleaseStgMedium` at `0x18004e69a`
- `ole32!ReleaseStgMedium` at `0x18004e743`
- `ole32!ReleaseStgMedium` at `0x18004e7d4`
- `ole32!ReleaseStgMedium` at `0x18004e8d1`
- `ole32!ReleaseStgMedium` at `0x18004e90a`
- `ole32!ReleaseStgMedium` at `0x18004e4dc`
- `ole32!ReleaseStgMedium` at `0x18004e561`
- `ole32!ReleaseStgMedium` at `0x18004e5f9`
- `ole32!ReleaseStgMedium` at `0x18004e69a`
- `ole32!ReleaseStgMedium` at `0x18004e743`
- `ole32!ReleaseStgMedium` at `0x18004e7d4`
- `ole32!ReleaseStgMedium` at `0x18004e8d1`
- `ole32!ReleaseStgMedium` at `0x18004e90a`
- `USER32!GetAsyncKeyState` at `0x18004e42c`
- `USER32!GetAsyncKeyState` at `0x18004e42c`

## pseudocode

```c
__int64 __fastcall SendToArchive::Drop(
        SendToArchive *this,
        struct IDataObject *a2,
        __int64 a3,
        struct _POINTL a4,
        unsigned int *a5)
{
  bool v8; // zf
  int v9; // eax
  unsigned int v10; // ebx
  HBITMAP hBitmap; // rbx
  HDROP v12; // rsi
  UINT FileW; // eax
  UINT v14; // r14d
  UINT i; // ebx
  UINT v16; // eax
  UINT v17; // edi
  LPWSTR v18; // rcx
  LPWSTR v19; // rcx
  LPWSTR v20; // rcx
  int v21; // eax
  unsigned int v22; // ebx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rax
  int ArchiveAsync; // eax
  unsigned int v28; // ebx
  int v29; // [rsp+20h] [rbp-F8h]
  int v30; // [rsp+20h] [rbp-F8h]
  SHORT AsyncKeyState; // [rsp+30h] [rbp-E8h]
  LPWSTR v32; // [rsp+38h] [rbp-E0h] BYREF
  _QWORD v33[2]; // [rsp+40h] [rbp-D8h] BYREF
  _QWORD v34[3]; // [rsp+50h] [rbp-C8h] BYREF
  _DWORD v35[2]; // [rsp+68h] [rbp-B0h] BYREF
  char v36; // [rsp+70h] [rbp-A8h]
  char v37; // [rsp+71h] [rbp-A7h]
  __int128 v38; // [rsp+78h] [rbp-A0h]
  __int16 v39; // [rsp+88h] [rbp-90h] BYREF
  int v40; // [rsp+8Ah] [rbp-8Eh]
  __int16 v41; // [rsp+8Eh] [rbp-8Ah]
  __int64 v42; // [rsp+90h] [rbp-88h]
  int v43; // [rsp+98h] [rbp-80h]
  int v44; // [rsp+9Ch] [rbp-7Ch]
  __int64 v45; // [rsp+A0h] [rbp-78h]
  LPWSTR lpszFile; // [rsp+A8h] [rbp-70h] BYREF
  __int128 v47; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v48; // [rsp+C0h] [rbp-58h]
  STGMEDIUM v49; // [rsp+C8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  if ( *((_BYTE *)this + 88) )
  {
    v8 = (*a5 & 3) == 0;
    *a5 &= 3u;
    if ( v8 )
    {
      return 0;
    }
    else
    {
      AsyncKeyState = GetAsyncKeyState(16);
      memset(&v49, 0, sizeof(v49));
      v39 = 15;
      v40 = 0;
      v41 = 0;
      v42 = 0;
      v43 = 1;
      v44 = -1;
      v45 = 1;
      v9 = ((__int64 (__fastcall *)(struct IDataObject *, __int16 *, STGMEDIUM *))a2->lpVtbl->GetData)(a2, &v39, &v49);
      v10 = v9;
      if ( v9 >= 0 )
      {
        hBitmap = v49.hBitmap;
        v12 = (HDROP)GlobalLock(v49.hBitmap);
        v33[1] = v12;
        v33[0] = (unsigned __int64)hBitmap & -(__int64)(v12 != 0);
        FileW = DragQueryFileW(v12, 0xFFFFFFFF, 0, 0);
        v14 = FileW;
        if ( FileW )
        {
          v47 = 0;
          v48 = 0;
          std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::reserve(
            &v47,
            FileW);
          for ( i = 0; ; ++i )
          {
            if ( i >= v14 )
            {
              lpszFile = 0;
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
                &lpszFile,
                0);
              v21 = SendToArchive::CreateTargetFile((char *)this - 8, a2, &v47, &lpszFile);
              v22 = v21;
              if ( v21 >= 0 )
              {
                v35[1] = 0;
                v38 = 0;
                v23 = *((_QWORD *)this + 6);
                v35[0] = *(_DWORD *)v23;
                v36 = *(_BYTE *)(v23 + 17);
                v37 = *(_BYTE *)(v23 + 16);
                v24 = v48;
                v48 = 0;
                v25 = *((_QWORD *)&v47 + 1);
                v26 = v47;
                v47 = 0u;
                v34[0] = v26;
                v34[1] = v25;
                v34[2] = v24;
                v32 = lpszFile;
                lpszFile = 0;
                ArchiveAsync = CreateArchiveAsync(
                                 (unsigned int)v35,
                                 (unsigned int)&v32,
                                 (unsigned int)v34,
                                 *((_QWORD *)this + 10),
                                 AsyncKeyState < 0);
                v28 = ArchiveAsync;
                if ( ArchiveAsync >= 0 )
                {
                  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&lpszFile);
                  std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Tidy(&v47);
                  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v33);
                  ReleaseStgMedium(&v49);
                  return 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xCD,
                    (unsigned int)"shell\\ext\\zip\\archive\\sendtoarchive.cpp",
                    (const char *)(unsigned int)ArchiveAsync,
                    v30);
                  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&lpszFile);
                  std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Tidy(&v47);
                  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v33);
                  ReleaseStgMedium(&v49);
                  return v28;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xC6,
                  (unsigned int)"shell\\ext\\zip\\archive\\sendtoarchive.cpp",
                  (const char *)(unsigned int)v21,
                  v29);
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&lpszFile);
                std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Tidy(&v47);
                wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v33);
                ReleaseStgMedium(&v49);
                return v22;
              }
            }
            v16 = DragQueryFileW(v12, i, 0, 0);
            v17 = v16 + 1;
            if ( !v16 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xBB,
                (unsigned int)"shell\\ext\\zip\\archive\\sendtoarchive.cpp",
                (const char *)0x8000FFFFLL,
                v29);
              std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Tidy(&v47);
              wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v33);
              ReleaseStgMedium(&v49);
              return 2147549183LL;
            }
            wil::make_unique_cotaskmem_nothrow<unsigned short [0]>(&lpszFile, v17);
            if ( !lpszFile )
              break;
            if ( !DragQueryFileW(v12, i, lpszFile, v17) )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC1,
                (unsigned int)"shell\\ext\\zip\\archive\\sendtoarchive.cpp",
                (const char *)0x8000FFFFLL,
                v29);
              v18 = lpszFile;
              lpszFile = 0;
              if ( v18 )
                CoTaskMemFree(v18);
              std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Tidy(&v47);
              wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v33);
              ReleaseStgMedium(&v49);
              return 2147549183LL;
            }
            std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::push_back(
              &v47,
              &lpszFile);
            v19 = lpszFile;
            lpszFile = 0;
            if ( v19 )
              CoTaskMemFree(v19);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBE,
            (unsigned int)"shell\\ext\\zip\\archive\\sendtoarchive.cpp",
            (const char *)0x8007000ELL,
            v29);
          v20 = lpszFile;
          lpszFile = 0;
          if ( v20 )
            CoTaskMemFree(v20);
          std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Tidy(&v47);
          wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v33);
          ReleaseStgMedium(&v49);
          return 2147942414LL;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB4,
            (unsigned int)"shell\\ext\\zip\\archive\\sendtoarchive.cpp",
            (const char *)0x8000FFFFLL,
            v29);
          wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v33);
          ReleaseStgMedium(&v49);
          return 2147549183LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAD,
          (unsigned int)"shell\\ext\\zip\\archive\\sendtoarchive.cpp",
          (const char *)(unsigned int)v9,
          v29);
        ReleaseStgMedium(&v49);
        return v10;
      }
    }
  }
  else
  {
    *a5 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x18004e3d0  mov     [rsp+arg_10], rbx
0x18004e3d5  mov     [rsp+arg_18], rsi
0x18004e3da  push    rdi
0x18004e3db  push    r12
0x18004e3dd  push    r13
0x18004e3df  push    r14
0x18004e3e1  push    r15
0x18004e3e3  sub     rsp, 0F0h
0x18004e3ea  mov     rax, cs:__security_cookie
0x18004e3f1  xor     rax, rsp
0x18004e3f4  mov     [rsp+118h+var_38], rax
0x18004e3fc  mov     r12, rdx
0x18004e3ff  mov     r13, rcx
0x18004e402  mov     rax, [rsp+118h+arg_20]
0x18004e40a  xor     edi, edi
0x18004e40c  cmp     [rcx+58h], dil
0x18004e410  jnz     short loc_18004E41B
0x18004e412  mov     [rax], edi
0x18004e414  xor     eax, eax
0x18004e416  jmp     loc_18004E918
0x18004e41b  and     dword ptr [rax], 3
0x18004e41e  jnz     short loc_18004E427
0x18004e420  xor     eax, eax
0x18004e422  jmp     loc_18004E918
0x18004e427  mov     ecx, 10h; vKey
0x18004e42c  call    cs:__imp_GetAsyncKeyState
0x18004e432  mov     [rsp+118h+var_E8], ax
0x18004e437  xorps   xmm0, xmm0
0x18004e43a  xor     eax, eax
0x18004e43c  movups  xmmword ptr [rsp+118h+var_50.tymed], xmm0
0x18004e444  mov     [rsp+118h+var_50.pUnkForRelease], rax
0x18004e44c  mov     eax, 0Fh
0x18004e451  mov     [rsp+118h+var_90], ax
0x18004e459  xor     eax, eax
0x18004e45b  mov     [rsp+118h+var_8E], eax
0x18004e462  mov     [rsp+118h+var_8A], ax
0x18004e46a  mov     [rsp+118h+var_88], rdi
0x18004e472  mov     eax, 1
0x18004e477  mov     [rsp+118h+var_80], eax
0x18004e47e  mov     [rsp+118h+var_7C], 0FFFFFFFFh
0x18004e489  mov     [rsp+118h+var_78], rax
0x18004e491  mov     rax, [r12]
0x18004e495  lea     r8, [rsp+118h+var_50]
0x18004e49d  lea     rdx, [rsp+118h+var_90]
0x18004e4a5  mov     rcx, r12
0x18004e4a8  mov     rax, [rax+18h]
0x18004e4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4b1  mov     ebx, eax
0x18004e4b3  test    eax, eax
0x18004e4b5  jns     short loc_18004E4E9
0x18004e4b7  mov     rcx, [rsp+118h]; this
0x18004e4bf  mov     r9d, eax; char *
0x18004e4c2  lea     r8, aShellExtZipArc_7; "shell\\ext\\zip\\archive\\sendtoarchive"...
0x18004e4c9  mov     edx, 0ADh; void *
0x18004e4ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e4d3  nop
0x18004e4d4  lea     rcx, [rsp+118h+var_50]; LPSTGMEDIUM
0x18004e4dc  call    cs:__imp_ReleaseStgMedium
0x18004e4e2  mov     eax, ebx
0x18004e4e4  jmp     loc_18004E918
0x18004e4e9  mov     rbx, qword ptr [rsp+118h+var_50.8]
0x18004e4f1  mov     rcx, rbx; hMem
0x18004e4f4  call    cs:__imp_GlobalLock
0x18004e4fa  mov     rsi, rax
0x18004e4fd  mov     [rsp+118h+var_D0], rax
0x18004e502  mov     rcx, rax
0x18004e505  neg     rcx
0x18004e508  sbb     rdx, rdx
0x18004e50b  and     rdx, rbx
0x18004e50e  mov     [rsp+118h+var_D8], rdx
0x18004e513  xor     r9d, r9d; cch
0x18004e516  xor     r8d, r8d; lpszFile
0x18004e519  or      edx, 0FFFFFFFFh; iFile
0x18004e51c  mov     rcx, rax; hDrop
0x18004e51f  call    cs:__imp_DragQueryFileW
0x18004e525  mov     r14d, eax
0x18004e528  test    eax, eax
0x18004e52a  jnz     short loc_18004E56E
0x18004e52c  mov     rcx, [rsp+118h]; this
0x18004e534  mov     ebx, 8000FFFFh
0x18004e539  mov     r9d, ebx; char *
0x18004e53c  lea     r8, aShellExtZipArc_7; "shell\\ext\\zip\\archive\\sendtoarchive"...
0x18004e543  mov     edx, 0B4h; void *
0x18004e548  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e54d  nop
0x18004e54e  lea     rcx, [rsp+118h+var_D8]
0x18004e553  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?GlobalUnlock@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004e558  nop
0x18004e559  lea     rcx, [rsp+118h+var_50]; LPSTGMEDIUM
0x18004e561  call    cs:__imp_ReleaseStgMedium
0x18004e567  mov     eax, ebx
0x18004e569  jmp     loc_18004E918
0x18004e56e  xorps   xmm0, xmm0
0x18004e571  movdqu  [rsp+118h+var_68], xmm0
0x18004e57a  mov     [rsp+118h+var_58], rdi
0x18004e582  mov     rdx, r14
0x18004e585  lea     rcx, [rsp+118h+var_68]
0x18004e58d  call    ?reserve@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@QEAAX_K@Z; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::reserve(unsigned __int64)
0x18004e592  mov     ebx, edi
0x18004e594  cmp     ebx, r14d
0x18004e597  jnb     loc_18004E750
0x18004e59d  xor     r9d, r9d; cch
0x18004e5a0  xor     r8d, r8d; lpszFile
0x18004e5a3  mov     edx, ebx; iFile
0x18004e5a5  mov     rcx, rsi; hDrop
0x18004e5a8  call    cs:__imp_DragQueryFileW
0x18004e5ae  lea     edi, [rax+1]
0x18004e5b1  cmp     edi, 1
0x18004e5b4  jnz     short loc_18004E606
0x18004e5b6  mov     rcx, [rsp+118h]; this
0x18004e5be  mov     ebx, 8000FFFFh
0x18004e5c3  mov     r9d, ebx; char *
0x18004e5c6  lea     r8, aShellExtZipArc_7; "shell\\ext\\zip\\archive\\sendtoarchive"...
0x18004e5cd  mov     edx, 0BBh; void *
0x18004e5d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e5d7  nop
0x18004e5d8  lea     rcx, [rsp+118h+var_68]
0x18004e5e0  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18004e5e5  nop
0x18004e5e6  lea     rcx, [rsp+118h+var_D8]
0x18004e5eb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?GlobalUnlock@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004e5f0  nop
0x18004e5f1  lea     rcx, [rsp+118h+var_50]; LPSTGMEDIUM
0x18004e5f9  call    cs:__imp_ReleaseStgMedium
0x18004e5ff  mov     eax, ebx
0x18004e601  jmp     loc_18004E918
0x18004e606  mov     edx, edi
0x18004e608  lea     rcx, [rsp+118h+lpszFile]
0x18004e610  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<ushort [0]>(unsigned __int64)
0x18004e615  nop
0x18004e616  mov     r8, [rsp+118h+lpszFile]; lpszFile
0x18004e61e  test    r8, r8
0x18004e621  jz      loc_18004E6E0
0x18004e627  mov     r9d, edi; cch
0x18004e62a  mov     edx, ebx; iFile
0x18004e62c  mov     rcx, rsi; hDrop
0x18004e62f  call    cs:__imp_DragQueryFileW
0x18004e635  xor     edi, edi
0x18004e637  test    eax, eax
0x18004e639  jnz     short loc_18004E6A7
0x18004e63b  mov     rcx, [rsp+118h]; this
0x18004e643  mov     ebx, 8000FFFFh
0x18004e648  mov     r9d, ebx; char *
0x18004e64b  lea     r8, aShellExtZipArc_7; "shell\\ext\\zip\\archive\\sendtoarchive"...
0x18004e652  mov     edx, 0C1h; void *
0x18004e657  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e65c  nop
0x18004e65d  mov     rcx, [rsp+118h+lpszFile]; pv
0x18004e665  mov     [rsp+118h+lpszFile], rdi
0x18004e66d  test    rcx, rcx
0x18004e670  jz      short loc_18004E679
0x18004e672  call    cs:__imp_CoTaskMemFree
0x18004e678  nop
0x18004e679  lea     rcx, [rsp+118h+var_68]
0x18004e681  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18004e686  nop
0x18004e687  lea     rcx, [rsp+118h+var_D8]
0x18004e68c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?GlobalUnlock@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004e691  nop
0x18004e692  lea     rcx, [rsp+118h+var_50]; LPSTGMEDIUM
0x18004e69a  call    cs:__imp_ReleaseStgMedium
0x18004e6a0  mov     eax, ebx
0x18004e6a2  jmp     loc_18004E918
0x18004e6a7  lea     rdx, [rsp+118h+lpszFile]
0x18004e6af  lea     rcx, [rsp+118h+var_68]
0x18004e6b7  call    ?push_back@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@QEAAX$$QEAV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::push_back(wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18004e6bc  nop
0x18004e6bd  mov     rcx, [rsp+118h+lpszFile]; pv
0x18004e6c5  mov     [rsp+118h+lpszFile], rdi
0x18004e6cd  test    rcx, rcx
0x18004e6d0  jz      short loc_18004E6D9
0x18004e6d2  call    cs:__imp_CoTaskMemFree
0x18004e6d8  nop
0x18004e6d9  inc     ebx
0x18004e6db  jmp     loc_18004E594
0x18004e6e0  mov     rcx, [rsp+118h]; this
0x18004e6e8  mov     ebx, 8007000Eh
0x18004e6ed  mov     r9d, ebx; char *
0x18004e6f0  lea     r8, aShellExtZipArc_7; "shell\\ext\\zip\\archive\\sendtoarchive"...
0x18004e6f7  mov     edx, 0BEh; void *
0x18004e6fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e701  nop
0x18004e702  mov     rcx, [rsp+118h+lpszFile]; pv
0x18004e70a  mov     [rsp+118h+lpszFile], 0
0x18004e716  test    rcx, rcx
0x18004e719  jz      short loc_18004E722
0x18004e71b  call    cs:__imp_CoTaskMemFree
0x18004e721  nop
0x18004e722  lea     rcx, [rsp+118h+var_68]
0x18004e72a  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18004e72f  nop
0x18004e730  lea     rcx, [rsp+118h+var_D8]
0x18004e735  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?GlobalUnlock@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004e73a  nop
0x18004e73b  lea     rcx, [rsp+118h+var_50]; LPSTGMEDIUM
0x18004e743  call    cs:__imp_ReleaseStgMedium
0x18004e749  mov     eax, ebx
0x18004e74b  jmp     loc_18004E918
0x18004e750  mov     [rsp+118h+lpszFile], rdi
0x18004e758  xor     edx, edx
0x18004e75a  lea     rcx, [rsp+118h+lpszFile]
0x18004e762  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004e767  lea     r9, [rsp+118h+lpszFile]
0x18004e76f  lea     r8, [rsp+118h+var_68]
0x18004e777  mov     rdx, r12
0x18004e77a  lea     rcx, [r13-8]
0x18004e77e  call    ?CreateTargetFile@SendToArchive@@AEAAJPEAUIDataObject@@AEBV?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@PEAPEAX@Z; SendToArchive::CreateTargetFile(IDataObject *,std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>> const &,void * *)
0x18004e783  mov     ebx, eax
0x18004e785  test    eax, eax
0x18004e787  jns     short loc_18004E7E1
0x18004e789  mov     rcx, [rsp+118h]; this
0x18004e791  mov     r9d, eax; char *
0x18004e794  lea     r8, aShellExtZipArc_7; "shell\\ext\\zip\\archive\\sendtoarchive"...
0x18004e79b  mov     edx, 0C6h; void *
0x18004e7a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e7a5  lea     rcx, [rsp+118h+lpszFile]
0x18004e7ad  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004e7b2  nop
0x18004e7b3  lea     rcx, [rsp+118h+var_68]
0x18004e7bb  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18004e7c0  nop
0x18004e7c1  lea     rcx, [rsp+118h+var_D8]
0x18004e7c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?GlobalUnlock@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004e7cb  nop
0x18004e7cc  lea     rcx, [rsp+118h+var_50]; LPSTGMEDIUM
0x18004e7d4  call    cs:__imp_ReleaseStgMedium
0x18004e7da  mov     eax, ebx
0x18004e7dc  jmp     loc_18004E918
0x18004e7e1  mov     [rsp+118h+var_AC], edi
0x18004e7e5  xorps   xmm0, xmm0
0x18004e7e8  movdqu  [rsp+118h+var_A0], xmm0
0x18004e7ee  mov     rcx, [r13+30h]
0x18004e7f2  mov     eax, [rcx]
0x18004e7f4  mov     [rsp+118h+var_B0], eax
0x18004e7f8  mov     al, [rcx+11h]
0x18004e7fb  mov     [rsp+118h+var_A8], al
0x18004e7ff  mov     al, [rcx+10h]
0x18004e802  mov     [rsp+118h+var_A7], al
0x18004e806  mov     rdx, [rsp+118h+var_58]
0x18004e80e  mov     [rsp+118h+var_58], rdi
0x18004e816  mov     rcx, qword ptr [rsp+118h+var_68+8]
0x18004e81e  mov     qword ptr [rsp+118h+var_68+8], rdi
0x18004e826  mov     rax, qword ptr [rsp+118h+var_68]
0x18004e82e  mov     qword ptr [rsp+118h+var_68], rdi
0x18004e836  mov     [rsp+118h+var_C8], rax
0x18004e83b  mov     [rsp+118h+var_C0], rcx
0x18004e840  mov     [rsp+118h+var_B8], rdx
0x18004e845  mov     rax, [rsp+118h+lpszFile]
0x18004e84d  mov     [rsp+118h+var_E0], rax
0x18004e852  mov     [rsp+118h+lpszFile], rdi
0x18004e85a  movzx   edi, [rsp+118h+var_E8]
0x18004e85f  shr     di, 0Fh
0x18004e863  mov     byte ptr [rsp+118h+var_F8], dil; int
0x18004e868  mov     r9, [r13+50h]
0x18004e86c  lea     r8, [rsp+118h+var_C8]
0x18004e871  lea     rdx, [rsp+118h+var_E0]
0x18004e876  lea     rcx, [rsp+118h+var_B0]
0x18004e87b  call    ?CreateArchiveAsync@@YAJAEBUCreateArchiveOptions@@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@PEAUIUnknown@@_N@Z; CreateArchiveAsync(CreateArchiveOptions const &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>,IUnknown *,bool)
0x18004e880  mov     ebx, eax
0x18004e882  test    eax, eax
0x18004e884  jns     short loc_18004E8DB
0x18004e886  mov     rcx, [rsp+118h]; this
0x18004e88e  mov     r9d, eax; char *
0x18004e891  lea     r8, aShellExtZipArc_7; "shell\\ext\\zip\\archive\\sendtoarchive"...
0x18004e898  mov     edx, 0CDh; void *
0x18004e89d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e8a2  lea     rcx, [rsp+118h+lpszFile]
0x18004e8aa  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004e8af  nop
0x18004e8b0  lea     rcx, [rsp+118h+var_68]
0x18004e8b8  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18004e8bd  nop
0x18004e8be  lea     rcx, [rsp+118h+var_D8]
0x18004e8c3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?GlobalUnlock@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004e8c8  nop
0x18004e8c9  lea     rcx, [rsp+118h+var_50]; LPSTGMEDIUM
0x18004e8d1  call    cs:__imp_ReleaseStgMedium
0x18004e8d7  mov     eax, ebx
0x18004e8d9  jmp     short loc_18004E918
0x18004e8db  lea     rcx, [rsp+118h+lpszFile]
0x18004e8e3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004e8e8  nop
0x18004e8e9  lea     rcx, [rsp+118h+var_68]
0x18004e8f1  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18004e8f6  nop
0x18004e8f7  lea     rcx, [rsp+118h+var_D8]
0x18004e8fc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?GlobalUnlock@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&GlobalUnlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004e901  nop
0x18004e902  lea     rcx, [rsp+118h+var_50]; LPSTGMEDIUM
0x18004e90a  call    cs:__imp_ReleaseStgMedium
0x18004e910  xor     eax, eax
0x18004e912  jmp     short loc_18004E918
0x18004e914  mov     eax, dword ptr [rsp+118h+var_E8]
0x18004e918  mov     rcx, [rsp+118h+var_38]
0x18004e920  xor     rcx, rsp; StackCookie
0x18004e923  call    __security_check_cookie
0x18004e928  lea     r11, [rsp+118h+var_28]
0x18004e930  mov     rbx, [r11+40h]
0x18004e934  mov     rsi, [r11+48h]
0x18004e938  mov     rsp, r11
  ... truncated ...
```
