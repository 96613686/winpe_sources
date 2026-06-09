# DBRow::_GetStoreId(ulong *)

- ea: `0x180009b40`
- end: `0x180009f78`
- name: `?_GetStoreId@DBRow@@AEAAJPEAK@Z`
- size: `1080`
- prototype: `__int64 __fastcall(DBRow *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006ce0`
- `0x180008af0`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x18000866c`
- `0x1800086bc`
- `0x180009b40`
- `0x18000ab20`
- `0x18000b350`
- `0x180050150`
- `0x18006f180`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009cea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009cea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f0e`

## string_xrefs

- `0x180009de4`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180009e7a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180009eac`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180009eee`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180009f5a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x180009f1f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`
- `0x180009d39`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x180009dd2`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x180009e43`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x180009e63`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`

## pseudocode

```c
__int64 __fastcall DBRow::_GetStoreId(DBRow *this, unsigned int *a2)
{
  unsigned int v2; // esi
  __int64 v5; // rax
  int v6; // eax
  unsigned int v7; // edi
  int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned int v12; // edi
  int v13; // eax
  unsigned int v14; // edi
  int v15; // eax
  int v16; // eax
  int v17; // eax
  HLOCAL v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r9
  __int64 v27; // r9
  __int64 v28; // rcx
  __int64 v29; // [rsp+30h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-28h] BYREF
  __int64 v31; // [rsp+40h] [rbp-20h] BYREF
  __int64 v32; // [rsp+48h] [rbp-18h]
  struct TableHandleInfo *v33; // [rsp+50h] [rbp-10h] BYREF
  __int64 v34; // [rsp+58h] [rbp-8h]
  unsigned int v35; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v36; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v37; // [rsp+A8h] [rbp+48h] BYREF

  v2 = -1;
  if ( *((_DWORD *)this + 7) != -1 )
  {
LABEL_41:
    if ( a2 )
      *a2 = *((_DWORD *)this + 7);
    return 0;
  }
  v5 = *(_QWORD *)this;
  v29 = 0;
  v6 = (*(__int64 (__fastcall **)(DBRow *, __int64 *))(v5 + 24))(this, &v29);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v31 = 0;
    v32 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 160LL))(v29, &v31);
    v9 = v8;
    if ( v8 < 0 )
    {
      v27 = 834;
      v28 = (unsigned int)v8;
    }
    else
    {
      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 32LL))(v31);
      if ( g_breakOnJetError == -1912 )
        Log_AssertionEvent(
          v10,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
          25);
      if ( v9 == -2134374536 )
      {
LABEL_9:
        LODWORD(v32) = 1;
        v33 = 0;
        v34 = v31;
        if ( v31 && ((*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31), (v11 = v34) != 0) )
        {
          v12 = *((_DWORD *)this + 6);
          if ( v33 )
          {
            auto_TableHandle::Close((auto_TableHandle *)&v33);
            v11 = v34;
          }
          v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct TableHandleInfo **))(*(_QWORD *)v11 + 64LL))(
                  v11,
                  v12,
                  0,
                  &v33);
          v14 = v13;
          if ( v13 >= 0 )
          {
            v15 = UnistoreJetGotoBookmarkEx(v33, (DBRow *)((char *)this + 32), 0);
            v14 = v15;
            if ( v15 >= 0 )
            {
              v16 = *((_DWORD *)this + 6);
              if ( !v16 || v16 != 50 && (v2 = 131075, v16 == 53) )
                v2 = 17170435;
              v36 = v2;
              v37 = 1;
              v35 = 0;
              hMem = 0;
              v17 = ESEReadRecordProps(v33, 0, &v37, &v36, (unsigned __int8 **)&hMem, &v35);
              v14 = v17;
              if ( v17 >= 0 )
              {
                v18 = hMem;
                v19 = 2147483640;
                if ( (*((_WORD *)hMem + 3) & 0x100) == 0 )
                  v19 = *((_DWORD *)hMem + 2);
                *((_DWORD *)this + 7) = v19;
                if ( v18 )
                  LocalFree(v18);
                v20 = v34;
                if ( v34 )
                {
                  if ( v33 )
                  {
                    (*(void (**)(void))(*(_QWORD *)v34 + 80LL))();
                    v20 = v34;
                    v33 = 0;
                  }
                  if ( v20 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
                }
                if ( !(_DWORD)v32 )
                  goto LABEL_37;
                if ( !v31 )
                  Log_AssertionEvent(
                    v20,
                    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
                    850);
                if ( HIDWORD(v32) )
                {
                  v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 40LL))(v31);
                  if ( v21 < 0 )
                  {
                    Log_UnistoreHREvent_0(
                      (unsigned int)v21,
                      1,
                      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
                      853);
LABEL_37:
                    if ( v31 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                    if ( v29 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                    goto LABEL_41;
                  }
                  HIDWORD(v32) = 0;
                }
                if ( v31 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                  v31 = 0;
                }
                LODWORD(v32) = 0;
                goto LABEL_37;
              }
              Log_UnistoreHREvent_0(
                (unsigned int)v17,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                8735);
              if ( hMem )
                LocalFree(hMem);
LABEL_47:
              auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v33);
              auto_DBSession::~auto_DBSession((auto_DBSession *)&v31);
              ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v29);
              return v14;
            }
            Log_UnistoreHREvent_0(
              (unsigned int)v15,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
              859);
            v26 = 8728;
LABEL_46:
            Log_UnistoreHREvent_0(
              v14,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
              v26);
            goto LABEL_47;
          }
          v23 = 771;
          v25 = 1;
          v24 = (unsigned int)v13;
        }
        else
        {
          v14 = -2147418113;
          v23 = 764;
          v24 = 2147549183LL;
          v25 = 0;
        }
        Log_UnistoreHREvent_0(
          v24,
          v25,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
          v23);
        v26 = 8726;
        goto LABEL_46;
      }
      if ( (v9 & 0x80000000) == 0 )
      {
        HIDWORD(v32) = 1;
        goto LABEL_9;
      }
      v27 = 838;
      v28 = v9;
    }
    Log_UnistoreHREvent_0(
      v28,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
      v27);
    Log_UnistoreHREvent_0(
      v9,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      8723);
    auto_DBSession::~auto_DBSession((auto_DBSession *)&v31);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v29);
    return v9;
  }
  Log_UnistoreHREvent_0(
    (unsigned int)v6,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
    8720);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  return v7;
}

```

## disassembly

```asm
0x180009b40  mov     [rsp-28h+arg_8], rbx
0x180009b45  push    rbp
0x180009b46  push    rsi
0x180009b47  push    rdi
0x180009b48  push    r14
0x180009b4a  push    r15
0x180009b4c  mov     rbp, rsp
0x180009b4f  sub     rsp, 60h
0x180009b53  mov     esi, 0FFFFFFFFh
0x180009b58  mov     r14, rdx
0x180009b5b  mov     rbx, rcx
0x180009b5e  cmp     [rcx+1Ch], esi
0x180009b61  jnz     loc_180009DA2
0x180009b67  mov     rax, [rcx]
0x180009b6a  lea     rdx, [rbp+var_30]
0x180009b6e  xor     r15d, r15d
0x180009b71  mov     [rbp+var_30], r15
0x180009b75  mov     rax, [rax+18h]
0x180009b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b7e  mov     edi, eax
0x180009b80  test    eax, eax
0x180009b82  js      loc_180009EA6
0x180009b88  mov     rcx, [rbp+var_30]
0x180009b8c  lea     rdx, [rbp+var_20]
0x180009b90  mov     [rbp+var_20], r15
0x180009b94  mov     [rbp+var_18], r15
0x180009b98  mov     rax, [rcx]
0x180009b9b  mov     rax, [rax+0A0h]
0x180009ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ba7  mov     edi, eax
0x180009ba9  test    eax, eax
0x180009bab  js      loc_180009E5B
0x180009bb1  mov     rcx, [rbp+var_20]
0x180009bb5  mov     rax, [rcx]
0x180009bb8  mov     rax, [rax+20h]
0x180009bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bc1  cmp     cs:?g_breakOnJetError@@3JA, 0FFFFF888h; long g_breakOnJetError
0x180009bcb  mov     edi, eax
0x180009bcd  jz      loc_180009F19
0x180009bd3  cmp     edi, 80C80778h
0x180009bd9  jz      short loc_180009BEA
0x180009bdb  test    edi, edi
0x180009bdd  js      loc_180009EDB
0x180009be3  mov     dword ptr [rbp+var_18+4], 1
0x180009bea  mov     rcx, [rbp+var_20]
0x180009bee  mov     rax, r15
0x180009bf1  mov     dword ptr [rbp+var_18], 1
0x180009bf8  mov     [rbp+var_10], rax
0x180009bfc  mov     [rbp+var_8], rcx
0x180009c00  test    rcx, rcx
0x180009c03  jz      loc_180009DC3
0x180009c09  mov     rax, [rcx]
0x180009c0c  mov     rax, [rax+8]
0x180009c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c15  mov     rcx, [rbp+var_8]
0x180009c19  mov     rax, [rbp+var_10]
0x180009c1d  test    rcx, rcx
0x180009c20  jz      loc_180009DC3
0x180009c26  mov     edi, [rbx+18h]
0x180009c29  test    rax, rax
0x180009c2c  jnz     loc_180009F30
0x180009c32  mov     rax, [rcx]
0x180009c35  lea     r9, [rbp+var_10]
0x180009c39  xor     r8d, r8d
0x180009c3c  mov     edx, edi
0x180009c3e  mov     rax, [rax+40h]
0x180009c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c47  mov     edi, eax
0x180009c49  test    eax, eax
0x180009c4b  js      loc_180009F42
0x180009c51  mov     rcx, [rbp+var_10]; struct TableHandleInfo *
0x180009c55  lea     rdx, [rbx+20h]; struct UnifiedStoreCursorLocation *
0x180009c59  xor     r8d, r8d; int *
0x180009c5c  call    ?UnistoreJetGotoBookmarkEx@@YAJPEAUTableHandleInfo@@AEBVUnifiedStoreCursorLocation@@PEAH@Z; UnistoreJetGotoBookmarkEx(TableHandleInfo *,UnifiedStoreCursorLocation const &,int *)
0x180009c61  mov     edi, eax
0x180009c63  test    eax, eax
0x180009c65  js      loc_180009F54
0x180009c6b  mov     eax, [rbx+18h]
0x180009c6e  test    eax, eax
0x180009c70  jz      loc_180009E1E
0x180009c76  cmp     eax, 32h ; '2'
0x180009c79  jz      short loc_180009C89
0x180009c7b  mov     esi, 20003h
0x180009c80  cmp     eax, 35h ; '5'
0x180009c83  jz      loc_180009E1E
0x180009c89  mov     rcx, [rbp+var_10]; struct TableHandleInfo *
0x180009c8d  lea     rax, [rbp+arg_0]
0x180009c91  mov     [rsp+60h+var_38], rax; unsigned int *
0x180009c96  lea     r9, [rbp+arg_10]; unsigned int *
0x180009c9a  lea     rax, [rbp+hMem]
0x180009c9e  mov     [rbp+arg_10], esi
0x180009ca1  lea     r8, [rbp+arg_18]; unsigned int *
0x180009ca5  mov     [rsp+60h+var_40], rax; unsigned __int8 **
0x180009caa  xor     edx, edx; unsigned int
0x180009cac  mov     [rbp+arg_18], 1
0x180009cb3  mov     [rbp+arg_0], r15d
0x180009cb7  mov     [rbp+hMem], r15
0x180009cbb  call    ?ESEReadRecordProps@@YAJPEAUTableHandleInfo@@KPEAK1PEAPEAE1@Z; ESEReadRecordProps(TableHandleInfo *,ulong,ulong *,ulong *,uchar * *,ulong *)
0x180009cc0  mov     edi, eax
0x180009cc2  test    eax, eax
0x180009cc4  js      loc_180009EE8
0x180009cca  mov     rcx, [rbp+hMem]; hMem
0x180009cce  mov     eax, 100h
0x180009cd3  test    [rcx+6], ax
0x180009cd7  mov     eax, 7FFFFFF8h
0x180009cdc  jz      loc_180009E16
0x180009ce2  mov     [rbx+1Ch], eax
0x180009ce5  test    rcx, rcx
0x180009ce8  jz      short loc_180009CF0
0x180009cea  call    cs:__imp_LocalFree
0x180009cf0  mov     rcx, [rbp+var_8]
0x180009cf4  test    rcx, rcx
0x180009cf7  jz      short loc_180009D27
0x180009cf9  mov     rdx, [rbp+var_10]
0x180009cfd  test    rdx, rdx
0x180009d00  jz      short loc_180009D16
0x180009d02  mov     rax, [rcx]
0x180009d05  mov     rax, [rax+50h]
0x180009d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d0e  mov     rcx, [rbp+var_8]
0x180009d12  mov     [rbp+var_10], r15
0x180009d16  test    rcx, rcx
0x180009d19  jz      short loc_180009D27
0x180009d1b  mov     rax, [rcx]
0x180009d1e  mov     rax, [rax+10h]
0x180009d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d27  cmp     dword ptr [rbp+var_18], r15d
0x180009d2b  jz      short loc_180009D78
0x180009d2d  cmp     [rbp+var_20], r15
0x180009d31  jnz     short loc_180009D45
0x180009d33  mov     r8d, 352h
0x180009d39  lea     rdx, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009d40  call    Log_AssertionEvent
0x180009d45  cmp     dword ptr [rbp+var_18+4], r15d
0x180009d49  jz      short loc_180009D67
0x180009d4b  mov     rcx, [rbp+var_20]
0x180009d4f  mov     rax, [rcx]
0x180009d52  mov     rax, [rax+28h]
0x180009d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d5b  test    eax, eax
0x180009d5d  js      loc_180009E3D
0x180009d63  mov     dword ptr [rbp+var_18+4], r15d
0x180009d67  mov     rcx, [rbp+var_20]
0x180009d6b  test    rcx, rcx
0x180009d6e  jnz     loc_180009E28
0x180009d74  mov     dword ptr [rbp+var_18], r15d
0x180009d78  mov     rcx, [rbp+var_20]
0x180009d7c  test    rcx, rcx
0x180009d7f  jz      short loc_180009D8D
0x180009d81  mov     rax, [rcx]
0x180009d84  mov     rax, [rax+10h]
0x180009d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d8d  mov     rcx, [rbp+var_30]
0x180009d91  test    rcx, rcx
0x180009d94  jz      short loc_180009DA2
0x180009d96  mov     rax, [rcx]
0x180009d99  mov     rax, [rax+10h]
0x180009d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009da2  test    r14, r14
0x180009da5  jz      short loc_180009DAD
0x180009da7  mov     eax, [rbx+1Ch]
0x180009daa  mov     [r14], eax
0x180009dad  xor     eax, eax
0x180009daf  mov     rbx, [rsp+60h+arg_8]
0x180009db7  add     rsp, 60h
0x180009dbb  pop     r15
0x180009dbd  pop     r14
0x180009dbf  pop     rdi
0x180009dc0  pop     rsi
0x180009dc1  pop     rbp
0x180009dc2  retn
0x180009dc3  mov     edi, 8000FFFFh
0x180009dc8  mov     r9d, 2FCh
0x180009dce  mov     ecx, edi
0x180009dd0  xor     edx, edx
0x180009dd2  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009dd9  call    Log_UnistoreHREvent_0
0x180009dde  mov     r9d, 2216h
0x180009de4  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009deb  mov     edx, 1
0x180009df0  mov     ecx, edi
0x180009df2  call    Log_UnistoreHREvent_0
0x180009df7  lea     rcx, [rbp+var_10]; this
0x180009dfb  call    ??1auto_TableHandle@@QEAA@XZ; auto_TableHandle::~auto_TableHandle(void)
0x180009e00  lea     rcx, [rbp+var_20]; this
0x180009e04  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x180009e09  lea     rcx, [rbp+var_30]; void *
0x180009e0d  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180009e12  mov     eax, edi
0x180009e14  jmp     short loc_180009DAF
0x180009e16  mov     eax, [rcx+8]
0x180009e19  jmp     loc_180009CE2
0x180009e1e  mov     esi, 1060003h
0x180009e23  jmp     loc_180009C89
0x180009e28  mov     rax, [rcx]
0x180009e2b  mov     rax, [rax+10h]
0x180009e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e34  mov     [rbp+var_20], r15
0x180009e38  jmp     loc_180009D74
0x180009e3d  mov     r9d, 355h
0x180009e43  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009e4a  mov     edx, 1
0x180009e4f  mov     ecx, eax
0x180009e51  call    Log_UnistoreHREvent_0
0x180009e56  jmp     loc_180009D78
0x180009e5b  mov     r9d, 342h
0x180009e61  mov     ecx, eax
0x180009e63  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009e6a  mov     edx, 1
0x180009e6f  call    Log_UnistoreHREvent_0
0x180009e74  mov     r9d, 2213h
0x180009e7a  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009e81  mov     edx, 1
0x180009e86  mov     ecx, edi
0x180009e88  call    Log_UnistoreHREvent_0
0x180009e8d  lea     rcx, [rbp+var_20]; this
0x180009e91  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x180009e96  lea     rcx, [rbp+var_30]; void *
0x180009e9a  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180009e9f  mov     eax, edi
0x180009ea1  jmp     loc_180009DAF
0x180009ea6  mov     r9d, 2210h
0x180009eac  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009eb3  mov     edx, 1
0x180009eb8  mov     ecx, edi
0x180009eba  call    Log_UnistoreHREvent_0
0x180009ebf  mov     rcx, [rbp+var_30]
0x180009ec3  test    rcx, rcx
0x180009ec6  jz      short loc_180009ED4
0x180009ec8  mov     rax, [rcx]
0x180009ecb  mov     rax, [rax+10h]
0x180009ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ed4  mov     eax, edi
0x180009ed6  jmp     loc_180009DAF
0x180009edb  mov     r9d, 346h
0x180009ee1  mov     ecx, edi
0x180009ee3  jmp     loc_180009E63
0x180009ee8  mov     r9d, 221Fh
0x180009eee  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009ef5  mov     edx, 1
0x180009efa  mov     ecx, edi
0x180009efc  call    Log_UnistoreHREvent_0
0x180009f01  mov     rcx, [rbp+hMem]; hMem
0x180009f05  test    rcx, rcx
0x180009f08  jz      loc_180009DF7
0x180009f0e  call    cs:__imp_LocalFree
0x180009f14  jmp     loc_180009DF7
0x180009f19  mov     r8d, 19h
0x180009f1f  lea     rdx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009f26  call    Log_AssertionEvent
0x180009f2b  jmp     loc_180009BD3
0x180009f30  lea     rcx, [rbp+var_10]; this
0x180009f34  call    ?Close@auto_TableHandle@@QEAAXXZ; auto_TableHandle::Close(void)
0x180009f39  mov     rcx, [rbp+var_8]
0x180009f3d  jmp     loc_180009C32
0x180009f42  mov     r9d, 303h
0x180009f48  mov     edx, 1
0x180009f4d  mov     ecx, eax
0x180009f4f  jmp     loc_180009DD2
0x180009f54  mov     r9d, 35Bh
0x180009f5a  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009f61  mov     edx, 1
0x180009f66  mov     ecx, edi
0x180009f68  call    Log_UnistoreHREvent_0
0x180009f6d  mov     r9d, 2218h
0x180009f73  jmp     loc_180009DE4
```
