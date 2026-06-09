# GetObjectFromProgID(COleScript *,ushort *,ushort *,VAR *,int,ushort *)

- ea: `0x18002583c`
- end: `0x180025cdc`
- name: `?GetObjectFromProgID@@YAJPEAVCOleScript@@PEAG1PEAVVAR@@H1@Z`
- size: `1184`
- prototype: `HRESULT __fastcall(struct CSession **this, const OLECHAR *lpszProgID, BSTR pbstr, struct VAR *, int, unsigned __int16 *String2)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002516c`
- `0x180042d28`

## callees

- `0x18002583c`
- `0x180026380`
- `0x1800264d8`
- `0x180026570`
- `0x180037330`
- `0x18003f194`
- `0x1800402a0`
- `0x180053c74`
- `0x180061f08`
- `0x1800620e0`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180025a5a`
- `msvcrt!_wcsicmp` at `0x180025a5a`
- `OLEAUT32!__imp_SysStringLen` at `0x18002595a`
- `OLEAUT32!__imp_SysStringLen` at `0x18002595a`
- `OLEAUT32!__imp_GetActiveObject` at `0x180025990`
- `OLEAUT32!__imp_GetActiveObject` at `0x180025990`
- `KERNEL32!GetComputerNameA` at `0x180025a08`
- `KERNEL32!GetComputerNameA` at `0x180025a08`
- `KERNEL32!MultiByteToWideChar` at `0x180025a35`
- `KERNEL32!MultiByteToWideChar` at `0x180025a35`
- `OLE32!CoGetClassObject` at `0x180025aab`
- `OLE32!CoGetClassObject` at `0x180025aab`
- `OLE32!CLSIDFromProgID` at `0x1800258ca`
- `OLE32!CLSIDFromProgID` at `0x1800258ca`
- `OLE32!CLSIDFromProgIDEx` at `0x1800258b3`
- `OLE32!CLSIDFromProgIDEx` at `0x1800258b3`

## pseudocode

```c
HRESULT __fastcall GetObjectFromProgID(
        struct CSession **this,
        const OLECHAR *lpszProgID,
        BSTR pbstr,
        struct VAR *a4,
        int a5,
        unsigned __int16 *String2)
{
  unsigned __int16 *v6; // rsi
  _QWORD *v7; // r15
  unsigned int v11; // eax
  HRESULT result; // eax
  int v13; // ebx
  UINT v14; // eax
  UINT v15; // r14d
  BOOL v16; // r12d
  DWORD v17; // ebx
  int v18; // eax
  bool v19; // sf
  __int64 v20; // rax
  struct CSession *v21; // rdx
  int v22; // eax
  SiteService *v23; // rsi
  void (*Release)(void); // rax
  bool v25; // zf
  __int64 v26; // rax
  DWORD nSize[2]; // [rsp+30h] [rbp-99h] BYREF
  IUnknown *ppunk; // [rsp+38h] [rbp-91h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-89h] BYREF
  __int64 v30; // [rsp+48h] [rbp-81h] BYREF
  struct IActiveScriptSiteWldp *v31; // [rsp+50h] [rbp-79h] BYREF
  struct VAR *v32; // [rsp+58h] [rbp-71h]
  _QWORD v33[4]; // [rsp+60h] [rbp-69h] BYREF
  CLSID clsid; // [rsp+80h] [rbp-49h] BYREF
  CHAR Buffer[16]; // [rsp+90h] [rbp-39h] BYREF
  WCHAR WideCharStr[16]; // [rsp+A0h] [rbp-29h] BYREF

  v6 = String2;
  v7 = 0;
  v32 = a4;
  if ( !lpszProgID )
    return -2146828283;
  v11 = *((_DWORD *)lpszProgID - 1);
  if ( v11 < 2 || (v11 & 0xFFFFFFFE) > 0x1F0 )
    return -2146828283;
  clsid = 0;
  if ( !(unsigned int)COleScript::InSafeMode((COleScript *)this, 0) && CLSIDFromProgIDEx(lpszProgID, &clsid) >= 0
    || (result = CLSIDFromProgID(lpszProgID, &clsid), result >= 0) )
  {
    v31 = 0;
    if ( (int)COleScript::GetActiveScriptSiteWldp((COleScript *)this, &v31) >= 0 )
    {
      nSize[0] = 0;
      v13 = (*(__int64 (__fastcall **)(struct IActiveScriptSiteWldp *, CLSID *, DWORD *))(*(_QWORD *)v31 + 32LL))(
              v31,
              &clsid,
              nSize);
      if ( v13 >= 0 && !nSize[0] )
        v13 = -2146827859;
      (*(void (__fastcall **)(struct IActiveScriptSiteWldp *))(*(_QWORD *)v31 + 16LL))(v31);
      if ( v13 < 0 )
        return v13;
    }
    if ( (unsigned int)IsProhibitedUnsafeExtension(&clsid) )
      return -2146827859;
    ppunk = 0;
    v14 = SysStringLen(pbstr);
    v15 = v14;
    if ( v14 || !a5 )
    {
      v16 = v14 != 0;
      if ( (unsigned int)COleScript::CanCreateObject((COleScript *)this, &clsid) )
      {
        v33[0] = 0;
        v33[1] = String2;
        v17 = 21;
        v33[2] = 0;
        v33[3] = 0;
        v18 = COleScript::InSafeMode((COleScript *)this, 0);
        if ( String2 )
        {
          if ( v18 )
            return -2146827859;
          nSize[0] = 16;
          if ( !GetComputerNameA(Buffer, nSize) || !MultiByteToWideChar(0, 0, Buffer, -1, WideCharStr, 16) )
            goto LABEL_28;
          while ( *v6 == 92 )
            ++v6;
          if ( _wcsicmp(WideCharStr, v6) )
          {
LABEL_28:
            v7 = v33;
            v17 = 16;
          }
        }
        else if ( v18 )
        {
          v17 = 5;
        }
        ppv = 0;
        v30 = 0;
        result = CoGetClassObject(&clsid, v17, v7, &IID_IClassFactory, &ppv);
        if ( result < 0 )
          return result;
        v19 = (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IClassFactory3, &v30) < 0;
        v20 = *(_QWORD *)ppv;
        if ( v19 )
        {
          v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, IUnknown **))(v20 + 24))(
                  ppv,
                  0,
                  &IID_IUnknown,
                  &ppunk);
          Release = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
          if ( v13 < 0 )
          {
LABEL_39:
            Release();
            return v13;
          }
          Release();
        }
        else
        {
          (*(void (**)(void))(v20 + 16))();
          v21 = this[80];
          *(_QWORD *)nSize = 0;
          v22 = SiteService::Create((struct SiteService **)nSize, v21);
          v23 = *(SiteService **)nSize;
          v13 = v22;
          if ( v22 < 0
            || (v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, GUID *, IUnknown **))(*(_QWORD *)v30 + 40LL))(
                        v30,
                        *(_QWORD *)nSize,
                        0,
                        &IID_IUnknown,
                        &ppunk),
                v13 < 0) )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            if ( v23 )
              SiteService::Release(v23);
            return v13;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          SiteService::Release(v23);
        }
        if ( (unsigned int)COleScript::CanObjectRun((COleScript *)this, &clsid, ppunk, v16) )
        {
          if ( v15 )
          {
            *(_QWORD *)nSize = 0;
            if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, DWORD *))ppunk->lpVtbl->QueryInterface)(
                   ppunk,
                   &IID_IPersistFile,
                   nSize) < 0 )
            {
              v13 = -2146827856;
              goto LABEL_52;
            }
            v25 = (unsigned int)COleScript::CanObjectPersistFromURL((COleScript *)this, pbstr) == 0;
            v26 = **(_QWORD **)nSize;
            if ( v25 )
            {
              (*(void (**)(void))(v26 + 16))();
              ((void (__fastcall *)(IUnknown *))ppunk->lpVtbl->Release)(ppunk);
              return -2146827859;
            }
            v13 = (*(__int64 (__fastcall **)(_QWORD, BSTR, _QWORD))(v26 + 40))(*(_QWORD *)nSize, pbstr, 0);
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)nSize + 16LL))(*(_QWORD *)nSize);
            if ( v13 == 1 )
              v13 = -2146827859;
          }
          if ( v13 < 0 )
          {
LABEL_52:
            Release = (void (*)(void))ppunk->lpVtbl->Release;
            goto LABEL_39;
          }
LABEL_51:
          v13 = PrepareObject((struct COleScript *)this, ppunk, v32);
          goto LABEL_52;
        }
        ((void (__fastcall *)(IUnknown *))ppunk->lpVtbl->Release)(ppunk);
      }
    }
    else if ( !(unsigned int)COleScript::InSafeMode((COleScript *)this, 0) )
    {
      result = GetActiveObject(&clsid, 0, &ppunk);
      if ( result < 0 )
        return result;
      goto LABEL_51;
    }
    return -2146827859;
  }
  return result;
}

```

## disassembly

```asm
0x18002583c  push    rbp
0x18002583e  push    rbx
0x18002583f  push    rsi
0x180025840  push    rdi
0x180025841  push    r12
0x180025843  push    r13
0x180025845  push    r14
0x180025847  push    r15
0x180025849  lea     rbp, [rsp-0Fh]
0x18002584e  sub     rsp, 0D8h
0x180025855  mov     rax, cs:__security_cookie
0x18002585c  xor     rax, rsp
0x18002585f  mov     [rbp+47h+var_50], rax
0x180025863  mov     rsi, [rbp+47h+String2]
0x180025867  xor     r15d, r15d
0x18002586a  mov     [rbp+47h+var_B8], r9
0x18002586e  mov     r13, r8
0x180025871  mov     rbx, rdx
0x180025874  mov     rdi, rcx
0x180025877  test    rdx, rdx
0x18002587a  jz      loc_180025CB6
0x180025880  mov     eax, [rdx-4]
0x180025883  cmp     eax, 2
0x180025886  jb      loc_180025CB6
0x18002588c  and     eax, 0FFFFFFFEh
0x18002588f  cmp     eax, 1F0h
0x180025894  ja      loc_180025CB6
0x18002589a  xorps   xmm0, xmm0
0x18002589d  xor     edx, edx; struct _GUID *
0x18002589f  movups  xmmword ptr [rbp+47h+clsid.Data1], xmm0
0x1800258a3  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x1800258a8  test    eax, eax
0x1800258aa  jnz     short loc_1800258C3
0x1800258ac  lea     rdx, [rbp+47h+clsid]; lpclsid
0x1800258b0  mov     rcx, rbx; lpszProgID
0x1800258b3  call    cs:__imp_CLSIDFromProgIDEx
0x1800258ba  nop     dword ptr [rax+rax+00h]
0x1800258bf  test    eax, eax
0x1800258c1  jns     short loc_1800258DE
0x1800258c3  lea     rdx, [rbp+47h+clsid]; lpclsid
0x1800258c7  mov     rcx, rbx; lpszProgID
0x1800258ca  call    cs:__imp_CLSIDFromProgID
0x1800258d1  nop     dword ptr [rax+rax+00h]
0x1800258d6  test    eax, eax
0x1800258d8  js      loc_180025CBB
0x1800258de  lea     rdx, [rbp+47h+var_C0]; struct IActiveScriptSiteWldp **
0x1800258e2  mov     [rbp+47h+var_C0], r15
0x1800258e6  mov     rcx, rdi; this
0x1800258e9  call    ?GetActiveScriptSiteWldp@COleScript@@QEAAJPEAPEAVIActiveScriptSiteWldp@@@Z; COleScript::GetActiveScriptSiteWldp(IActiveScriptSiteWldp * *)
0x1800258ee  test    eax, eax
0x1800258f0  js      short loc_180025941
0x1800258f2  mov     rcx, [rbp+47h+var_C0]
0x1800258f6  lea     r8, [rsp+110h+nSize]
0x1800258fb  mov     [rsp+110h+nSize], r15d
0x180025900  lea     rdx, [rbp+47h+clsid]
0x180025904  mov     rax, [rcx]
0x180025907  mov     rax, [rax+20h]
0x18002590b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025910  mov     ebx, eax
0x180025912  test    eax, eax
0x180025914  js      short loc_180025923
0x180025916  cmp     [rsp+110h+nSize], r15d
0x18002591b  mov     eax, 800A01ADh
0x180025920  cmovz   ebx, eax
0x180025923  mov     rdx, [rbp+47h+var_C0]
0x180025927  mov     rcx, [rdx]
0x18002592a  mov     rax, [rcx+10h]
0x18002592e  mov     rcx, rdx
0x180025931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025936  test    ebx, ebx
0x180025938  jns     short loc_180025941
0x18002593a  mov     eax, ebx
0x18002593c  jmp     loc_180025CBB
0x180025941  lea     rcx, [rbp+47h+clsid]
0x180025945  call    IsProhibitedUnsafeExtension
0x18002594a  test    eax, eax
0x18002594c  jnz     loc_180025BED
0x180025952  mov     rcx, r13; pbstr
0x180025955  mov     [rsp+110h+ppunk], r15
0x18002595a  call    cs:__imp_SysStringLen
0x180025961  nop     dword ptr [rax+rax+00h]
0x180025966  mov     r14d, eax
0x180025969  test    eax, eax
0x18002596b  jnz     short loc_1800259A9
0x18002596d  cmp     [rbp+47h+arg_20], r15d
0x180025971  jz      short loc_1800259A9
0x180025973  xor     edx, edx; struct _GUID *
0x180025975  mov     rcx, rdi; this
0x180025978  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x18002597d  test    eax, eax
0x18002597f  jnz     loc_180025BED
0x180025985  lea     r8, [rsp+110h+ppunk]; ppunk
0x18002598a  xor     edx, edx; pvReserved
0x18002598c  lea     rcx, [rbp+47h+clsid]; rclsid
0x180025990  call    cs:__imp_GetActiveObject
0x180025997  nop     dword ptr [rax+rax+00h]
0x18002599c  test    eax, eax
0x18002599e  jns     loc_180025C8B
0x1800259a4  jmp     loc_180025CBB
0x1800259a9  test    r14d, r14d
0x1800259ac  lea     rdx, [rbp+47h+clsid]; struct _GUID *
0x1800259b0  mov     r12d, r15d
0x1800259b3  mov     rcx, rdi; this
0x1800259b6  setnz   r12b
0x1800259ba  call    ?CanCreateObject@COleScript@@QEAAHAEBU_GUID@@@Z; COleScript::CanCreateObject(_GUID const &)
0x1800259bf  test    eax, eax
0x1800259c1  jz      loc_180025BED
0x1800259c7  xor     edx, edx; struct _GUID *
0x1800259c9  mov     [rbp+47h+var_B0], r15
0x1800259cd  mov     rcx, rdi; this
0x1800259d0  mov     [rbp+47h+var_A8], rsi
0x1800259d4  mov     ebx, 15h
0x1800259d9  mov     [rbp+47h+var_A0], r15
0x1800259dd  mov     [rbp+47h+var_98], r15
0x1800259e1  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x1800259e6  test    rsi, rsi
0x1800259e9  jz      loc_180025A75
0x1800259ef  test    eax, eax
0x1800259f1  jnz     loc_180025BED
0x1800259f7  lea     rdx, [rsp+110h+nSize]; nSize
0x1800259fc  mov     [rsp+110h+nSize], 10h
0x180025a04  lea     rcx, [rbp+47h+Buffer]; lpBuffer
0x180025a08  call    cs:__imp_GetComputerNameA
0x180025a0f  nop     dword ptr [rax+rax+00h]
0x180025a14  test    eax, eax
0x180025a16  jz      short loc_180025A6A
0x180025a18  lea     rax, [rbp+47h+WideCharStr]
0x180025a1c  mov     [rsp+110h+cchWideChar], 10h; cchWideChar
0x180025a24  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180025a28  mov     [rsp+110h+lpWideCharStr], rax; lpWideCharStr
0x180025a2d  lea     r8, [rbp+47h+Buffer]; lpMultiByteStr
0x180025a31  xor     edx, edx; dwFlags
0x180025a33  xor     ecx, ecx; CodePage
0x180025a35  call    cs:__imp_MultiByteToWideChar
0x180025a3c  nop     dword ptr [rax+rax+00h]
0x180025a41  test    eax, eax
0x180025a43  jz      short loc_180025A6A
0x180025a45  lea     eax, [rbx+47h]
0x180025a48  jmp     short loc_180025A4E
0x180025a4a  add     rsi, 2
0x180025a4e  cmp     ax, [rsi]
0x180025a51  jz      short loc_180025A4A
0x180025a53  mov     rdx, rsi; String2
0x180025a56  lea     rcx, [rbp+47h+WideCharStr]; String1
0x180025a5a  call    cs:__imp__wcsicmp
0x180025a61  nop     dword ptr [rax+rax+00h]
0x180025a66  test    eax, eax
0x180025a68  jz      short loc_180025A7F
0x180025a6a  lea     r15, [rbp+47h+var_B0]
0x180025a6e  mov     ebx, 10h
0x180025a73  jmp     short loc_180025A7F
0x180025a75  test    eax, eax
0x180025a77  mov     ecx, 5
0x180025a7c  cmovnz  ebx, ecx
0x180025a7f  lea     rax, [rsp+110h+ppv]
0x180025a84  mov     [rsp+110h+ppv], 0
0x180025a8d  lea     r9, IID_IClassFactory; riid
0x180025a94  mov     [rsp+110h+lpWideCharStr], rax; ppv
0x180025a99  mov     r8, r15; pvReserved
0x180025a9c  mov     [rsp+110h+var_C8], 0
0x180025aa5  mov     edx, ebx; dwClsContext
0x180025aa7  lea     rcx, [rbp+47h+clsid]; rclsid
0x180025aab  call    cs:__imp_CoGetClassObject
0x180025ab2  nop     dword ptr [rax+rax+00h]
0x180025ab7  test    eax, eax
0x180025ab9  js      loc_180025CBB
0x180025abf  mov     rcx, [rsp+110h+ppv]
0x180025ac4  lea     r8, [rsp+110h+var_C8]
0x180025ac9  lea     rdx, IID_IClassFactory3
0x180025ad0  mov     rax, [rcx]
0x180025ad3  mov     rax, [rax]
0x180025ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025adb  mov     rcx, [rsp+110h+ppv]
0x180025ae0  test    eax, eax
0x180025ae2  mov     rax, [rcx]
0x180025ae5  js      loc_180025B89
0x180025aeb  mov     rax, [rax+10h]
0x180025aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025af4  mov     rdx, [rdi+280h]; struct CSession *
0x180025afb  lea     rcx, [rsp+110h+nSize]; struct SiteService **
0x180025b00  mov     qword ptr [rsp+110h+nSize], 0
0x180025b09  call    ?Create@SiteService@@SAJPEAPEAV1@PEAVCSession@@@Z; SiteService::Create(SiteService * *,CSession *)
0x180025b0e  mov     rsi, qword ptr [rsp+110h+nSize]
0x180025b13  mov     ebx, eax
0x180025b15  test    eax, eax
0x180025b17  js      short loc_180025B62
0x180025b19  mov     rcx, [rsp+110h+var_C8]
0x180025b1e  lea     rdx, [rsp+110h+ppunk]
0x180025b23  mov     [rsp+110h+lpWideCharStr], rdx
0x180025b28  lea     r9, IID_IUnknown
0x180025b2f  xor     r8d, r8d
0x180025b32  mov     rdx, rsi
0x180025b35  mov     rax, [rcx]
0x180025b38  mov     rax, [rax+28h]
0x180025b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b41  mov     ebx, eax
0x180025b43  test    eax, eax
0x180025b45  js      short loc_180025B62
0x180025b47  mov     rcx, [rsp+110h+var_C8]
0x180025b4c  mov     rax, [rcx]
0x180025b4f  mov     rax, [rax+10h]
0x180025b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b58  mov     rcx, rsi; this
0x180025b5b  call    ?Release@SiteService@@UEAAKXZ; SiteService::Release(void)
0x180025b60  jmp     short loc_180025BC1
0x180025b62  mov     rcx, [rsp+110h+var_C8]
0x180025b67  mov     rax, [rcx]
0x180025b6a  mov     rax, [rax+10h]
0x180025b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b73  test    rsi, rsi
0x180025b76  jz      loc_18002593A
0x180025b7c  mov     rcx, rsi; this
0x180025b7f  call    ?Release@SiteService@@UEAAKXZ; SiteService::Release(void)
0x180025b84  jmp     loc_18002593A
0x180025b89  mov     rax, [rax+18h]
0x180025b8d  lea     r9, [rsp+110h+ppunk]
0x180025b92  lea     r8, IID_IUnknown
0x180025b99  xor     edx, edx
0x180025b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ba0  mov     rcx, [rsp+110h+ppv]
0x180025ba5  mov     ebx, eax
0x180025ba7  test    eax, eax
0x180025ba9  mov     rax, [rcx]
0x180025bac  mov     rax, [rax+10h]
0x180025bb0  jns     short loc_180025BBC
0x180025bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bb7  jmp     loc_18002593A
0x180025bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bc1  mov     r8, [rsp+110h+ppunk]; struct IUnknown *
0x180025bc6  lea     rdx, [rbp+47h+clsid]; struct _GUID *
0x180025bca  mov     r9d, r12d; int
0x180025bcd  mov     rcx, rdi; this
0x180025bd0  call    ?CanObjectRun@COleScript@@QEAAHAEBU_GUID@@PEAUIUnknown@@H@Z; COleScript::CanObjectRun(_GUID const &,IUnknown *,int)
0x180025bd5  test    eax, eax
0x180025bd7  jnz     short loc_180025BF7
0x180025bd9  mov     rdx, [rsp+110h+ppunk]
0x180025bde  mov     rcx, [rdx]
0x180025be1  mov     rax, [rcx+10h]
0x180025be5  mov     rcx, rdx
0x180025be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bed  mov     eax, 800A01ADh
0x180025bf2  jmp     loc_180025CBB
0x180025bf7  test    r14d, r14d
0x180025bfa  jz      loc_180025C87
0x180025c00  mov     rcx, [rsp+110h+ppunk]
0x180025c05  lea     r8, [rsp+110h+nSize]
0x180025c0a  mov     qword ptr [rsp+110h+nSize], 0
0x180025c13  lea     rdx, IID_IPersistFile
0x180025c1a  mov     rax, [rcx]
0x180025c1d  mov     rax, [rax]
0x180025c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c25  test    eax, eax
0x180025c27  js      loc_180025CAF
0x180025c2d  mov     rdx, r13; unsigned __int16 *
0x180025c30  mov     rcx, rdi; this
0x180025c33  call    ?CanObjectPersistFromURL@COleScript@@QEAAHPEAG@Z; COleScript::CanObjectPersistFromURL(ushort *)
0x180025c38  mov     rcx, qword ptr [rsp+110h+nSize]
0x180025c3d  test    eax, eax
0x180025c3f  mov     rax, [rcx]
0x180025c42  jnz     short loc_180025C5B
0x180025c44  mov     rax, [rax+10h]
0x180025c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c4d  mov     rcx, [rsp+110h+ppunk]
0x180025c52  mov     rax, [rcx]
0x180025c55  mov     rax, [rax+10h]
0x180025c59  jmp     short loc_180025BE8
0x180025c5b  mov     rax, [rax+28h]
0x180025c5f  xor     r8d, r8d
0x180025c62  mov     rdx, r13
0x180025c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c6a  mov     rcx, qword ptr [rsp+110h+nSize]
0x180025c6f  mov     ebx, eax
0x180025c71  mov     rax, [rcx]
0x180025c74  mov     rax, [rax+10h]
0x180025c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c7d  cmp     ebx, 1
0x180025c80  jnz     short loc_180025C87
0x180025c82  mov     ebx, 800A01ADh
0x180025c87  test    ebx, ebx
0x180025c89  js      short loc_180025C9E
0x180025c8b  mov     r8, [rbp+47h+var_B8]; struct VAR *
0x180025c8f  mov     rcx, rdi; struct COleScript *
0x180025c92  mov     rdx, [rsp+110h+ppunk]; struct IUnknown *
0x180025c97  call    ?PrepareObject@@YAJPEAVCOleScript@@PEAUIUnknown@@PEAVVAR@@@Z; PrepareObject(COleScript *,IUnknown *,VAR *)
0x180025c9c  mov     ebx, eax
0x180025c9e  mov     rcx, [rsp+110h+ppunk]
0x180025ca3  mov     rax, [rcx]
0x180025ca6  mov     rax, [rax+10h]
0x180025caa  jmp     loc_180025BB2
0x180025caf  mov     ebx, 800A01B0h
0x180025cb4  jmp     short loc_180025C9E
0x180025cb6  mov     eax, 800A0005h
0x180025cbb  mov     rcx, [rbp+47h+var_50]
0x180025cbf  xor     rcx, rsp; StackCookie
0x180025cc2  call    __security_check_cookie
0x180025cc7  add     rsp, 0D8h
0x180025cce  pop     r15
0x180025cd0  pop     r14
0x180025cd2  pop     r13
0x180025cd4  pop     r12
  ... truncated ...
```
