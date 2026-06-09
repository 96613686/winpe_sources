# GetObjectFromProgID(COleScript *,ushort *,ushort *,VAR *,int,ushort *)

- ea: `0x180003a30`
- end: `0x180003e9b`
- name: `?GetObjectFromProgID@@YAJPEAVCOleScript@@PEAG1PEAVVAR@@H1@Z`
- size: `1131`
- prototype: `__int64 __usercall@<rax>(struct COleScript *this@<rcx>, LPCOLESTR lpszProgID@<rdx>, BSTR pbstr@<r8>, struct VAR *@<r9>, int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003f18`
- `0x180041370`

## callees

- `0x180003a30`
- `0x180035dc4`
- `0x180039480`
- `0x1800395d0`
- `0x180039668`
- `0x18003dbf8`
- `0x18003eb00`
- `0x18005244c`
- `0x180060268`
- `0x180060420`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003c26`
- `msvcrt!_wcsicmp` at `0x180003c26`
- `OLEAUT32!__imp_SysStringLen` at `0x180003b42`
- `OLEAUT32!__imp_SysStringLen` at `0x180003b42`
- `OLEAUT32!__imp_GetActiveObject` at `0x180003b72`
- `OLEAUT32!__imp_GetActiveObject` at `0x180003b72`
- `KERNEL32!GetComputerNameA` at `0x180003be0`
- `KERNEL32!GetComputerNameA` at `0x180003be0`
- `KERNEL32!MultiByteToWideChar` at `0x180003c07`
- `KERNEL32!MultiByteToWideChar` at `0x180003c07`
- `OLE32!CoGetClassObject` at `0x180003c71`
- `OLE32!CoGetClassObject` at `0x180003c71`
- `OLE32!CLSIDFromProgID` at `0x180003ab8`
- `OLE32!CLSIDFromProgID` at `0x180003ab8`
- `OLE32!CLSIDFromProgIDEx` at `0x180003aa7`
- `OLE32!CLSIDFromProgIDEx` at `0x180003aa7`

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
0x180003a30  push    rbp
0x180003a32  push    rbx
0x180003a33  push    rsi
0x180003a34  push    rdi
0x180003a35  push    r12
0x180003a37  push    r13
0x180003a39  push    r14
0x180003a3b  push    r15
0x180003a3d  lea     rbp, [rsp-0Fh]
0x180003a42  sub     rsp, 0D8h
0x180003a49  mov     rax, cs:__security_cookie
0x180003a50  xor     rax, rsp
0x180003a53  mov     [rbp+47h+var_50], rax
0x180003a57  mov     rsi, [rbp+47h+String2]
0x180003a5b  xor     r15d, r15d
0x180003a5e  mov     [rbp+47h+var_B8], r9
0x180003a62  mov     r13, r8
0x180003a65  mov     rbx, rdx
0x180003a68  mov     rdi, rcx
0x180003a6b  test    rdx, rdx
0x180003a6e  jz      loc_180003E76
0x180003a74  mov     eax, [rdx-4]
0x180003a77  cmp     eax, 2
0x180003a7a  jb      loc_180003E76
0x180003a80  and     eax, 0FFFFFFFEh
0x180003a83  cmp     eax, 1F0h
0x180003a88  ja      loc_180003E76
0x180003a8e  xorps   xmm0, xmm0
0x180003a91  xor     edx, edx; struct _GUID *
0x180003a93  movups  xmmword ptr [rbp+47h+clsid.Data1], xmm0
0x180003a97  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x180003a9c  test    eax, eax
0x180003a9e  jnz     short loc_180003AB1
0x180003aa0  lea     rdx, [rbp+47h+clsid]; lpclsid
0x180003aa4  mov     rcx, rbx; lpszProgID
0x180003aa7  call    cs:__imp_CLSIDFromProgIDEx
0x180003aad  test    eax, eax
0x180003aaf  jns     short loc_180003AC6
0x180003ab1  lea     rdx, [rbp+47h+clsid]; lpclsid
0x180003ab5  mov     rcx, rbx; lpszProgID
0x180003ab8  call    cs:__imp_CLSIDFromProgID
0x180003abe  test    eax, eax
0x180003ac0  js      loc_180003E7B
0x180003ac6  lea     rdx, [rbp+47h+var_C0]; struct IActiveScriptSiteWldp **
0x180003aca  mov     [rbp+47h+var_C0], r15
0x180003ace  mov     rcx, rdi; this
0x180003ad1  call    ?GetActiveScriptSiteWldp@COleScript@@QEAAJPEAPEAVIActiveScriptSiteWldp@@@Z; COleScript::GetActiveScriptSiteWldp(IActiveScriptSiteWldp * *)
0x180003ad6  test    eax, eax
0x180003ad8  js      short loc_180003B29
0x180003ada  mov     rcx, [rbp+47h+var_C0]
0x180003ade  lea     r8, [rsp+110h+nSize]
0x180003ae3  mov     [rsp+110h+nSize], r15d
0x180003ae8  lea     rdx, [rbp+47h+clsid]
0x180003aec  mov     rax, [rcx]
0x180003aef  mov     rax, [rax+20h]
0x180003af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003af8  mov     ebx, eax
0x180003afa  test    eax, eax
0x180003afc  js      short loc_180003B0B
0x180003afe  cmp     [rsp+110h+nSize], r15d
0x180003b03  mov     eax, 800A01ADh
0x180003b08  cmovz   ebx, eax
0x180003b0b  mov     rdx, [rbp+47h+var_C0]
0x180003b0f  mov     rcx, [rdx]
0x180003b12  mov     rax, [rcx+10h]
0x180003b16  mov     rcx, rdx
0x180003b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b1e  test    ebx, ebx
0x180003b20  jns     short loc_180003B29
0x180003b22  mov     eax, ebx
0x180003b24  jmp     loc_180003E7B
0x180003b29  lea     rcx, [rbp+47h+clsid]
0x180003b2d  call    IsProhibitedUnsafeExtension
0x180003b32  test    eax, eax
0x180003b34  jnz     loc_180003DAD
0x180003b3a  mov     rcx, r13; pbstr
0x180003b3d  mov     [rsp+110h+ppunk], r15
0x180003b42  call    cs:__imp_SysStringLen
0x180003b48  mov     r14d, eax
0x180003b4b  test    eax, eax
0x180003b4d  jnz     short loc_180003B85
0x180003b4f  cmp     [rbp+47h+arg_20], r15d
0x180003b53  jz      short loc_180003B85
0x180003b55  xor     edx, edx; struct _GUID *
0x180003b57  mov     rcx, rdi; this
0x180003b5a  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x180003b5f  test    eax, eax
0x180003b61  jnz     loc_180003DAD
0x180003b67  lea     r8, [rsp+110h+ppunk]; ppunk
0x180003b6c  xor     edx, edx; pvReserved
0x180003b6e  lea     rcx, [rbp+47h+clsid]; rclsid
0x180003b72  call    cs:__imp_GetActiveObject
0x180003b78  test    eax, eax
0x180003b7a  jns     loc_180003E4B
0x180003b80  jmp     loc_180003E7B
0x180003b85  test    r14d, r14d
0x180003b88  lea     rdx, [rbp+47h+clsid]; struct _GUID *
0x180003b8c  mov     r12d, r15d
0x180003b8f  mov     rcx, rdi; this
0x180003b92  setnz   r12b
0x180003b96  call    ?CanCreateObject@COleScript@@QEAAHAEBU_GUID@@@Z; COleScript::CanCreateObject(_GUID const &)
0x180003b9b  test    eax, eax
0x180003b9d  jz      loc_180003DAD
0x180003ba3  xor     edx, edx; struct _GUID *
0x180003ba5  mov     [rbp+47h+var_B0], r15
0x180003ba9  mov     rcx, rdi; this
0x180003bac  mov     [rbp+47h+var_A8], rsi
0x180003bb0  mov     ebx, 15h
0x180003bb5  mov     [rbp+47h+var_A0], r15
0x180003bb9  mov     [rbp+47h+var_98], r15
0x180003bbd  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x180003bc2  test    rsi, rsi
0x180003bc5  jz      short loc_180003C3B
0x180003bc7  test    eax, eax
0x180003bc9  jnz     loc_180003DAD
0x180003bcf  lea     rdx, [rsp+110h+nSize]; nSize
0x180003bd4  mov     [rsp+110h+nSize], 10h
0x180003bdc  lea     rcx, [rbp+47h+Buffer]; lpBuffer
0x180003be0  call    cs:__imp_GetComputerNameA
0x180003be6  test    eax, eax
0x180003be8  jz      short loc_180003C30
0x180003bea  lea     rax, [rbp+47h+WideCharStr]
0x180003bee  mov     [rsp+110h+cchWideChar], 10h; cchWideChar
0x180003bf6  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180003bfa  mov     [rsp+110h+lpWideCharStr], rax; lpWideCharStr
0x180003bff  lea     r8, [rbp+47h+Buffer]; lpMultiByteStr
0x180003c03  xor     edx, edx; dwFlags
0x180003c05  xor     ecx, ecx; CodePage
0x180003c07  call    cs:__imp_MultiByteToWideChar
0x180003c0d  test    eax, eax
0x180003c0f  jz      short loc_180003C30
0x180003c11  lea     eax, [rbx+47h]
0x180003c14  jmp     short loc_180003C1A
0x180003c16  add     rsi, 2
0x180003c1a  cmp     ax, [rsi]
0x180003c1d  jz      short loc_180003C16
0x180003c1f  mov     rdx, rsi; String2
0x180003c22  lea     rcx, [rbp+47h+WideCharStr]; String1
0x180003c26  call    cs:__imp__wcsicmp
0x180003c2c  test    eax, eax
0x180003c2e  jz      short loc_180003C45
0x180003c30  lea     r15, [rbp+47h+var_B0]
0x180003c34  mov     ebx, 10h
0x180003c39  jmp     short loc_180003C45
0x180003c3b  test    eax, eax
0x180003c3d  mov     ecx, 5
0x180003c42  cmovnz  ebx, ecx
0x180003c45  lea     rax, [rsp+110h+ppv]
0x180003c4a  mov     [rsp+110h+ppv], 0
0x180003c53  lea     r9, IID_IClassFactory; riid
0x180003c5a  mov     [rsp+110h+lpWideCharStr], rax; ppv
0x180003c5f  mov     r8, r15; pvReserved
0x180003c62  mov     [rsp+110h+var_C8], 0
0x180003c6b  mov     edx, ebx; dwClsContext
0x180003c6d  lea     rcx, [rbp+47h+clsid]; rclsid
0x180003c71  call    cs:__imp_CoGetClassObject
0x180003c77  test    eax, eax
0x180003c79  js      loc_180003E7B
0x180003c7f  mov     rcx, [rsp+110h+ppv]
0x180003c84  lea     r8, [rsp+110h+var_C8]
0x180003c89  lea     rdx, IID_IClassFactory3
0x180003c90  mov     rax, [rcx]
0x180003c93  mov     rax, [rax]
0x180003c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c9b  mov     rcx, [rsp+110h+ppv]
0x180003ca0  test    eax, eax
0x180003ca2  mov     rax, [rcx]
0x180003ca5  js      loc_180003D49
0x180003cab  mov     rax, [rax+10h]
0x180003caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cb4  mov     rdx, [rdi+280h]; struct CSession *
0x180003cbb  lea     rcx, [rsp+110h+nSize]; struct SiteService **
0x180003cc0  mov     qword ptr [rsp+110h+nSize], 0
0x180003cc9  call    ?Create@SiteService@@SAJPEAPEAV1@PEAVCSession@@@Z; SiteService::Create(SiteService * *,CSession *)
0x180003cce  mov     rsi, qword ptr [rsp+110h+nSize]
0x180003cd3  mov     ebx, eax
0x180003cd5  test    eax, eax
0x180003cd7  js      short loc_180003D22
0x180003cd9  mov     rcx, [rsp+110h+var_C8]
0x180003cde  lea     rdx, [rsp+110h+ppunk]
0x180003ce3  mov     [rsp+110h+lpWideCharStr], rdx
0x180003ce8  lea     r9, IID_IUnknown
0x180003cef  xor     r8d, r8d
0x180003cf2  mov     rdx, rsi
0x180003cf5  mov     rax, [rcx]
0x180003cf8  mov     rax, [rax+28h]
0x180003cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d01  mov     ebx, eax
0x180003d03  test    eax, eax
0x180003d05  js      short loc_180003D22
0x180003d07  mov     rcx, [rsp+110h+var_C8]
0x180003d0c  mov     rax, [rcx]
0x180003d0f  mov     rax, [rax+10h]
0x180003d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d18  mov     rcx, rsi; this
0x180003d1b  call    ?Release@SiteService@@UEAAKXZ; SiteService::Release(void)
0x180003d20  jmp     short loc_180003D81
0x180003d22  mov     rcx, [rsp+110h+var_C8]
0x180003d27  mov     rax, [rcx]
0x180003d2a  mov     rax, [rax+10h]
0x180003d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d33  test    rsi, rsi
0x180003d36  jz      loc_180003B22
0x180003d3c  mov     rcx, rsi; this
0x180003d3f  call    ?Release@SiteService@@UEAAKXZ; SiteService::Release(void)
0x180003d44  jmp     loc_180003B22
0x180003d49  mov     rax, [rax+18h]
0x180003d4d  lea     r9, [rsp+110h+ppunk]
0x180003d52  lea     r8, IID_IUnknown
0x180003d59  xor     edx, edx
0x180003d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d60  mov     rcx, [rsp+110h+ppv]
0x180003d65  mov     ebx, eax
0x180003d67  test    eax, eax
0x180003d69  mov     rax, [rcx]
0x180003d6c  mov     rax, [rax+10h]
0x180003d70  jns     short loc_180003D7C
0x180003d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d77  jmp     loc_180003B22
0x180003d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d81  mov     r8, [rsp+110h+ppunk]; struct IUnknown *
0x180003d86  lea     rdx, [rbp+47h+clsid]; struct _GUID *
0x180003d8a  mov     r9d, r12d; int
0x180003d8d  mov     rcx, rdi; this
0x180003d90  call    ?CanObjectRun@COleScript@@QEAAHAEBU_GUID@@PEAUIUnknown@@H@Z; COleScript::CanObjectRun(_GUID const &,IUnknown *,int)
0x180003d95  test    eax, eax
0x180003d97  jnz     short loc_180003DB7
0x180003d99  mov     rdx, [rsp+110h+ppunk]
0x180003d9e  mov     rcx, [rdx]
0x180003da1  mov     rax, [rcx+10h]
0x180003da5  mov     rcx, rdx
0x180003da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dad  mov     eax, 800A01ADh
0x180003db2  jmp     loc_180003E7B
0x180003db7  test    r14d, r14d
0x180003dba  jz      loc_180003E47
0x180003dc0  mov     rcx, [rsp+110h+ppunk]
0x180003dc5  lea     r8, [rsp+110h+nSize]
0x180003dca  mov     qword ptr [rsp+110h+nSize], 0
0x180003dd3  lea     rdx, IID_IPersistFile
0x180003dda  mov     rax, [rcx]
0x180003ddd  mov     rax, [rax]
0x180003de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003de5  test    eax, eax
0x180003de7  js      loc_180003E6F
0x180003ded  mov     rdx, r13; unsigned __int16 *
0x180003df0  mov     rcx, rdi; this
0x180003df3  call    ?CanObjectPersistFromURL@COleScript@@QEAAHPEAG@Z; COleScript::CanObjectPersistFromURL(ushort *)
0x180003df8  mov     rcx, qword ptr [rsp+110h+nSize]
0x180003dfd  test    eax, eax
0x180003dff  mov     rax, [rcx]
0x180003e02  jnz     short loc_180003E1B
0x180003e04  mov     rax, [rax+10h]
0x180003e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e0d  mov     rcx, [rsp+110h+ppunk]
0x180003e12  mov     rax, [rcx]
0x180003e15  mov     rax, [rax+10h]
0x180003e19  jmp     short loc_180003DA8
0x180003e1b  mov     rax, [rax+28h]
0x180003e1f  xor     r8d, r8d
0x180003e22  mov     rdx, r13
0x180003e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e2a  mov     rcx, qword ptr [rsp+110h+nSize]
0x180003e2f  mov     ebx, eax
0x180003e31  mov     rax, [rcx]
0x180003e34  mov     rax, [rax+10h]
0x180003e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e3d  cmp     ebx, 1
0x180003e40  jnz     short loc_180003E47
0x180003e42  mov     ebx, 800A01ADh
0x180003e47  test    ebx, ebx
0x180003e49  js      short loc_180003E5E
0x180003e4b  mov     r8, [rbp+47h+var_B8]; struct VAR *
0x180003e4f  mov     rcx, rdi; struct COleScript *
0x180003e52  mov     rdx, [rsp+110h+ppunk]; struct IUnknown *
0x180003e57  call    ?PrepareObject@@YAJPEAVCOleScript@@PEAUIUnknown@@PEAVVAR@@@Z; PrepareObject(COleScript *,IUnknown *,VAR *)
0x180003e5c  mov     ebx, eax
0x180003e5e  mov     rcx, [rsp+110h+ppunk]
0x180003e63  mov     rax, [rcx]
0x180003e66  mov     rax, [rax+10h]
0x180003e6a  jmp     loc_180003D72
0x180003e6f  mov     ebx, 800A01B0h
0x180003e74  jmp     short loc_180003E5E
0x180003e76  mov     eax, 800A0005h
0x180003e7b  mov     rcx, [rbp+47h+var_50]
0x180003e7f  xor     rcx, rsp; StackCookie
0x180003e82  call    __security_check_cookie
0x180003e87  add     rsp, 0D8h
0x180003e8e  pop     r15
0x180003e90  pop     r14
0x180003e92  pop     r13
0x180003e94  pop     r12
0x180003e96  pop     rdi
0x180003e97  pop     rsi
0x180003e98  pop     rbx
0x180003e99  pop     rbp
0x180003e9a  retn
```
