# TaskDialog_ConfirmReplace(CProgressUI *,HWND__ *,REPLACEFILE const &,int *,int *)

- ea: `0x180071c94`
- end: `0x180071f4d`
- name: `?TaskDialog_ConfirmReplace@@YAJPEAVCProgressUI@@PEAUHWND__@@AEBUREPLACEFILE@@PEAH3@Z`
- size: `697`
- prototype: `__int64 __usercall@<rax>(struct CProgressUI *@<rcx>, HWND@<rdx>, const struct REPLACEFILE *@<r8>, int *@<r9>, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003a710`

## callees

- `0x1800285c8`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180041e44`
- `0x180042010`
- `0x180071c94`
- `0x180078010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180071e04`
- `ole32!CoCreateInstance` at `0x180071e4b`
- `ole32!CoCreateInstance` at `0x180071e04`
- `ole32!CoCreateInstance` at `0x180071e4b`
- `SHELL32!SHCreateItemFromIDList` at `0x180071d35`
- `SHELL32!SHCreateItemFromIDList` at `0x180071d6b`
- `SHELL32!SHCreateItemFromIDList` at `0x180071da0`
- `SHELL32!SHCreateItemFromIDList` at `0x180071dd6`
- `SHELL32!SHCreateItemFromIDList` at `0x180071d35`
- `SHELL32!SHCreateItemFromIDList` at `0x180071d6b`
- `SHELL32!SHCreateItemFromIDList` at `0x180071da0`
- `SHELL32!SHCreateItemFromIDList` at `0x180071dd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TaskDialog_ConfirmReplace(
        struct CProgressUI *a1,
        HWND a2,
        const struct REPLACEFILE *a3,
        int *a4,
        int *a5)
{
  __int128 v8; // xmm0
  unsigned int v9; // eax
  __int64 v10; // rdx
  int v12; // [rsp+30h] [rbp-61h] BYREF
  int v13; // [rsp+34h] [rbp-5Dh] BYREF
  LPVOID v14; // [rsp+38h] [rbp-59h] BYREF
  _BYTE v15[16]; // [rsp+40h] [rbp-51h] BYREF
  _DWORD v16[2]; // [rsp+50h] [rbp-41h] BYREF
  __int128 v18; // [rsp+5Ch] [rbp-35h]
  void *ppv; // [rsp+78h] [rbp-19h] BYREF
  void *v20[6]; // [rsp+80h] [rbp-11h] BYREF

  CPauseTimer::CPauseTimer((CPauseTimer *)v15, a1);
  v13 = 0;
  v12 = 0;
  v14 = 0;
  memset_0(v16, 0, 0x60u);
  v16[1] = *((_DWORD *)a3 + 2);
  if ( *(_DWORD *)a3 )
    v8 = STCONFIRM_REPLACE_STORAGE;
  else
    v8 = STCONFIRM_REPLACE_STREAM;
  v18 = v8;
  v20[4] = a2;
  v16[0] = 8;
  if ( SHCreateItemFromIDList(*((LPCITEMIDLIST *)a3 + 3), &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv) >= 0 )
  {
    if ( SHCreateItemFromIDList(*((LPCITEMIDLIST *)a3 + 4), &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v20) >= 0 )
    {
      if ( CoCreateInstance(&CLSID_TransferConfirmationUI, 0, 1u, &GUID_14cc750c_7b0b_43dc_910e_b687f84e7c3b, &v14) >= 0 )
      {
        if ( (*(int (__fastcall **)(LPVOID, _DWORD *, int *, int *))(*(_QWORD *)v14 + 24LL))(v14, v16, &v12, &v13) >= 0 )
        {
          if ( a4 )
          {
            if ( v12 )
            {
              if ( v12 == 1 )
                *a4 = 7;
              else
                *a4 = 2;
            }
            else
            {
              *a4 = 1;
            }
          }
          if ( a5 )
            *a5 = v13;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v9 = (*(__int64 (__fastcall **)(LPVOID, _DWORD *, int *, int *))(*(_QWORD *)v14 + 24LL))(v14, v16, &v12, &v13);
          v10 = 13;
          goto LABEL_8;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v9 = CoCreateInstance(&CLSID_TransferConfirmationUI, 0, 1u, &GUID_14cc750c_7b0b_43dc_910e_b687f84e7c3b, &v14);
        v10 = 12;
        goto LABEL_8;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v9 = SHCreateItemFromIDList(*((LPCITEMIDLIST *)a3 + 4), &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v20);
      v10 = 11;
      goto LABEL_8;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v9 = SHCreateItemFromIDList(*((LPCITEMIDLIST *)a3 + 3), &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    v10 = 10;
LABEL_8:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_14709025e6503dbfbcefb4d2d07798be_Traceguids, v9);
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v20[0] )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v20[0] + 16LL))(v20[0]);
    v20[0] = 0;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  CPauseTimer::~CPauseTimer((CPauseTimer *)v15);
  return 0;
}

```

## disassembly

```asm
0x180071c94  push    rbp
0x180071c96  push    rbx
0x180071c97  push    rsi
0x180071c98  push    rdi
0x180071c99  push    r14
0x180071c9b  lea     rbp, [rsp-2Fh]
0x180071ca0  sub     rsp, 0C0h
0x180071ca7  mov     rax, cs:__security_cookie
0x180071cae  xor     rax, rsp
0x180071cb1  mov     [rbp+4Fh+var_30], rax
0x180071cb5  mov     rbx, r9
0x180071cb8  mov     rdi, r8
0x180071cbb  mov     r14, rdx
0x180071cbe  mov     rsi, [rbp+4Fh+arg_20]
0x180071cc2  mov     rdx, rcx; struct CProgressUI *
0x180071cc5  lea     rcx, [rbp+4Fh+var_A0]; this
0x180071cc9  call    ??0CPauseTimer@@QEAA@PEAVCProgressUI@@@Z; CPauseTimer::CPauseTimer(CProgressUI *)
0x180071cce  nop
0x180071ccf  mov     [rbp+4Fh+var_AC], 0
0x180071cd6  mov     [rbp+4Fh+var_B0], 0
0x180071cdd  mov     [rbp+4Fh+var_A8], 0
0x180071ce5  xor     edx, edx; Val
0x180071ce7  lea     r8d, [rdx+60h]; Size
0x180071ceb  lea     rcx, [rbp+4Fh+var_90]; void *
0x180071cef  call    memset_0
0x180071cf4  mov     eax, [rdi+8]
0x180071cf7  mov     [rbp+4Fh+var_8C], eax
0x180071cfa  mov     eax, [rdi]
0x180071cfc  mov     [rbp+4Fh+var_88], eax
0x180071cff  test    eax, eax
0x180071d01  jz      short loc_180071D0C
0x180071d03  movups  xmm0, cs:STCONFIRM_REPLACE_STORAGE
0x180071d0a  jmp     short loc_180071D13
0x180071d0c  movups  xmm0, cs:STCONFIRM_REPLACE_STREAM
0x180071d13  movdqu  [rbp+4Fh+var_84], xmm0
0x180071d18  mov     [rbp+4Fh+var_40], r14
0x180071d1c  mov     [rbp+4Fh+var_90], 8
0x180071d23  lea     r8, [rbp+4Fh+ppv]; ppv
0x180071d27  lea     r14, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180071d2e  mov     rdx, r14; riid
0x180071d31  mov     rcx, [rdi+18h]; pidl
0x180071d35  call    cs:__imp_SHCreateItemFromIDList
0x180071d3b  test    eax, eax
0x180071d3d  jns     short loc_180071D95
0x180071d3f  lea     rax, WPP_GLOBAL_Control
0x180071d46  mov     rcx, cs:WPP_GLOBAL_Control
0x180071d4d  cmp     rcx, rax
0x180071d50  jz      loc_180071EE4
0x180071d56  test    byte ptr [rcx+1Ch], 2
0x180071d5a  jz      loc_180071EE4
0x180071d60  lea     r8, [rbp+4Fh+ppv]; ppv
0x180071d64  mov     rdx, r14; riid
0x180071d67  mov     rcx, [rdi+18h]; pidl
0x180071d6b  call    cs:__imp_SHCreateItemFromIDList
0x180071d71  mov     edx, 0Ah
0x180071d76  mov     r9d, eax
0x180071d79  lea     r8, WPP_14709025e6503dbfbcefb4d2d07798be_Traceguids
0x180071d80  mov     rcx, cs:WPP_GLOBAL_Control
0x180071d87  mov     rcx, [rcx+10h]
0x180071d8b  call    WPP_SF_d
0x180071d90  jmp     loc_180071EE4
0x180071d95  lea     r8, [rbp+4Fh+var_60]; ppv
0x180071d99  mov     rdx, r14; riid
0x180071d9c  mov     rcx, [rdi+20h]; pidl
0x180071da0  call    cs:__imp_SHCreateItemFromIDList
0x180071da6  test    eax, eax
0x180071da8  jns     short loc_180071DE3
0x180071daa  lea     rax, WPP_GLOBAL_Control
0x180071db1  mov     rcx, cs:WPP_GLOBAL_Control
0x180071db8  cmp     rcx, rax
0x180071dbb  jz      loc_180071EE4
0x180071dc1  test    byte ptr [rcx+1Ch], 2
0x180071dc5  jz      loc_180071EE4
0x180071dcb  lea     r8, [rbp+4Fh+var_60]; ppv
0x180071dcf  mov     rdx, r14; riid
0x180071dd2  mov     rcx, [rdi+20h]; pidl
0x180071dd6  call    cs:__imp_SHCreateItemFromIDList
0x180071ddc  mov     edx, 0Bh
0x180071de1  jmp     short loc_180071D76
0x180071de3  lea     rax, [rbp+4Fh+var_A8]
0x180071de7  mov     [rsp+0E0h+var_C0], rax; ppv
0x180071dec  lea     r9, _GUID_14cc750c_7b0b_43dc_910e_b687f84e7c3b; riid
0x180071df3  mov     edi, 1
0x180071df8  mov     r8d, edi; dwClsContext
0x180071dfb  xor     edx, edx; pUnkOuter
0x180071dfd  lea     rcx, CLSID_TransferConfirmationUI; rclsid
0x180071e04  call    cs:__imp_CoCreateInstance
0x180071e0a  test    eax, eax
0x180071e0c  jns     short loc_180071E59
0x180071e0e  lea     rax, WPP_GLOBAL_Control
0x180071e15  mov     rdx, cs:WPP_GLOBAL_Control
0x180071e1c  cmp     rdx, rax
0x180071e1f  jz      loc_180071EE4
0x180071e25  test    byte ptr [rdx+1Ch], 2
0x180071e29  jz      loc_180071EE4
0x180071e2f  lea     rax, [rbp+4Fh+var_A8]
0x180071e33  mov     [rsp+0E0h+var_C0], rax; ppv
0x180071e38  lea     r9, _GUID_14cc750c_7b0b_43dc_910e_b687f84e7c3b; riid
0x180071e3f  mov     r8d, edi; dwClsContext
0x180071e42  xor     edx, edx; pUnkOuter
0x180071e44  lea     rcx, CLSID_TransferConfirmationUI; rclsid
0x180071e4b  call    cs:__imp_CoCreateInstance
0x180071e51  lea     edx, [rdi+0Bh]
0x180071e54  jmp     loc_180071D76
0x180071e59  mov     rcx, [rbp+4Fh+var_A8]
0x180071e5d  mov     rax, [rcx]
0x180071e60  lea     r9, [rbp+4Fh+var_AC]
0x180071e64  lea     r8, [rbp+4Fh+var_B0]
0x180071e68  lea     rdx, [rbp+4Fh+var_90]
0x180071e6c  mov     rax, [rax+18h]
0x180071e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e75  test    eax, eax
0x180071e77  jns     short loc_180071EB8
0x180071e79  lea     rax, WPP_GLOBAL_Control
0x180071e80  mov     rcx, cs:WPP_GLOBAL_Control
0x180071e87  cmp     rcx, rax
0x180071e8a  jz      short loc_180071EE4
0x180071e8c  test    byte ptr [rcx+1Ch], 2
0x180071e90  jz      short loc_180071EE4
0x180071e92  mov     rcx, [rbp+4Fh+var_A8]
0x180071e96  mov     rax, [rcx]
0x180071e99  lea     r9, [rbp+4Fh+var_AC]
0x180071e9d  lea     r8, [rbp+4Fh+var_B0]
0x180071ea1  lea     rdx, [rbp+4Fh+var_90]
0x180071ea5  mov     rax, [rax+18h]
0x180071ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071eae  mov     edx, 0Dh
0x180071eb3  jmp     loc_180071D76
0x180071eb8  test    rbx, rbx
0x180071ebb  jz      short loc_180071EDA
0x180071ebd  mov     ecx, [rbp+4Fh+var_B0]
0x180071ec0  test    ecx, ecx
0x180071ec2  jz      short loc_180071ED8
0x180071ec4  cmp     ecx, edi
0x180071ec6  jz      short loc_180071ED0
0x180071ec8  mov     dword ptr [rbx], 2
0x180071ece  jmp     short loc_180071EDA
0x180071ed0  mov     dword ptr [rbx], 7
0x180071ed6  jmp     short loc_180071EDA
0x180071ed8  mov     [rbx], edi
0x180071eda  test    rsi, rsi
0x180071edd  jz      short loc_180071EE4
0x180071edf  mov     eax, [rbp+4Fh+var_AC]
0x180071ee2  mov     [rsi], eax
0x180071ee4  mov     rcx, [rbp+4Fh+ppv]
0x180071ee8  test    rcx, rcx
0x180071eeb  jz      short loc_180071F01
0x180071eed  mov     rax, [rcx]
0x180071ef0  mov     rax, [rax+10h]
0x180071ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ef9  mov     [rbp+4Fh+ppv], 0
0x180071f01  mov     rcx, [rbp+4Fh+var_60]
0x180071f05  test    rcx, rcx
0x180071f08  jz      short loc_180071F1E
0x180071f0a  mov     rax, [rcx]
0x180071f0d  mov     rax, [rax+10h]
0x180071f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f16  mov     [rbp+4Fh+var_60], 0
0x180071f1e  lea     rcx, [rbp+4Fh+var_A8]
0x180071f22  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180071f27  nop
0x180071f28  lea     rcx, [rbp+4Fh+var_A0]; this
0x180071f2c  call    ??1CPauseTimer@@QEAA@XZ; CPauseTimer::~CPauseTimer(void)
0x180071f31  xor     eax, eax
0x180071f33  mov     rcx, [rbp+4Fh+var_30]
0x180071f37  xor     rcx, rsp; StackCookie
0x180071f3a  call    __security_check_cookie
0x180071f3f  add     rsp, 0C0h
0x180071f46  pop     r14
0x180071f48  pop     rdi
0x180071f49  pop     rsi
0x180071f4a  pop     rbx
0x180071f4b  pop     rbp
0x180071f4c  retn
```
