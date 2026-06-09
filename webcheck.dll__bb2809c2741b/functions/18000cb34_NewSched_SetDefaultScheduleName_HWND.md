# NewSched_SetDefaultScheduleName(HWND__ *)

- ea: `0x18000cb34`
- end: `0x18000cc7b`
- name: `?NewSched_SetDefaultScheduleName@@YAXPEAUHWND__@@@Z`
- size: `327`
- prototype: `void __fastcall(HWND hDlg)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c88c`

## callees

- `0x180003950`
- `0x18000cb34`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `USER32!SetDlgItemTextW` at `0x18000cc2d`
- `USER32!SetDlgItemTextW` at `0x18000cc2d`
- `ole32!CoCreateInstance` at `0x18000cb94`
- `ole32!CoCreateInstance` at `0x18000cb94`
- `ole32!CoUninitialize` at `0x18000cc55`
- `ole32!CoUninitialize` at `0x18000cc55`
- `ole32!CoInitialize` at `0x18000cb5f`
- `ole32!CoInitialize` at `0x18000cb5f`

## pseudocode

```c
void __fastcall NewSched_SetDefaultScheduleName(HWND hDlg)
{
  int v2; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v3; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v5; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v6[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String[264]; // [rsp+270h] [rbp+170h] BYREF

  if ( CoInitialize(0) >= 0 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_SyncMgr, 0, 0x17u, &IID_ISyncScheduleMgr, &ppv) >= 0 )
    {
      v3 = 0;
      v5 = 0;
      if ( (*(int (__fastcall **)(LPVOID, const WCHAR *, _QWORD, __int128 *, __int64 *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             &Default,
             0,
             &v5,
             &v3) >= 0 )
      {
        v2 = 260;
        if ( (*(int (__fastcall **)(__int64, int *, unsigned __int16 *))(*(_QWORD *)v3 + 56LL))(v3, &v2, v6) >= 0 )
        {
          StringCchCopyW(String, 0x104u, v6);
          SetDlgItemTextW(hDlg, 2106, String);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x18000cb34  mov     [rsp-8+arg_8], rbx
0x18000cb39  push    rbp
0x18000cb3a  lea     rbp, [rsp-390h]
0x18000cb42  sub     rsp, 490h
0x18000cb49  mov     rax, cs:__security_cookie
0x18000cb50  xor     rax, rsp
0x18000cb53  mov     [rbp+390h+var_10], rax
0x18000cb5a  mov     rbx, rcx
0x18000cb5d  xor     ecx, ecx; pvReserved
0x18000cb5f  call    cs:__imp_CoInitialize
0x18000cb65  test    eax, eax
0x18000cb67  js      loc_18000CC5B
0x18000cb6d  xor     edx, edx; pUnkOuter
0x18000cb6f  mov     [rsp+490h+var_450], 0
0x18000cb78  lea     rax, [rsp+490h+var_450]
0x18000cb7d  lea     r9, IID_ISyncScheduleMgr; riid
0x18000cb84  mov     [rsp+490h+ppv], rax; ppv
0x18000cb89  lea     rcx, CLSID_SyncMgr; rclsid
0x18000cb90  lea     r8d, [rdx+17h]; dwClsContext
0x18000cb94  call    cs:__imp_CoCreateInstance
0x18000cb9a  test    eax, eax
0x18000cb9c  js      loc_18000CC55
0x18000cba2  mov     rcx, [rsp+490h+var_450]
0x18000cba7  lea     rdx, [rsp+490h+var_458]
0x18000cbac  xorps   xmm0, xmm0
0x18000cbaf  mov     [rsp+490h+var_458], 0
0x18000cbb8  movups  [rsp+490h+var_448], xmm0
0x18000cbbd  mov     [rsp+490h+ppv], rdx
0x18000cbc2  lea     r9, [rsp+490h+var_448]
0x18000cbc7  mov     rax, [rcx]
0x18000cbca  lea     rdx, Default
0x18000cbd1  xor     r8d, r8d
0x18000cbd4  mov     rax, [rax+18h]
0x18000cbd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbdd  test    eax, eax
0x18000cbdf  js      short loc_18000CC44
0x18000cbe1  mov     rcx, [rsp+490h+var_458]
0x18000cbe6  lea     r8, [rsp+490h+var_430]
0x18000cbeb  mov     [rsp+490h+var_460], 104h
0x18000cbf3  lea     rdx, [rsp+490h+var_460]
0x18000cbf8  mov     rax, [rcx]
0x18000cbfb  mov     rax, [rax+38h]
0x18000cbff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc04  test    eax, eax
0x18000cc06  js      short loc_18000CC33
0x18000cc08  lea     r8, [rsp+490h+var_430]; unsigned __int16 *
0x18000cc0d  mov     edx, 104h; unsigned __int64
0x18000cc12  lea     rcx, [rbp+390h+String]; unsigned __int16 *
0x18000cc19  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cc1e  lea     r8, [rbp+390h+String]; lpString
0x18000cc25  mov     edx, 83Ah; nIDDlgItem
0x18000cc2a  mov     rcx, rbx; hDlg
0x18000cc2d  call    cs:__imp_SetDlgItemTextW
0x18000cc33  mov     rcx, [rsp+490h+var_458]
0x18000cc38  mov     rax, [rcx]
0x18000cc3b  mov     rax, [rax+10h]
0x18000cc3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc44  mov     rcx, [rsp+490h+var_450]
0x18000cc49  mov     rax, [rcx]
0x18000cc4c  mov     rax, [rax+10h]
0x18000cc50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc55  call    cs:__imp_CoUninitialize
0x18000cc5b  mov     rcx, [rbp+390h+var_10]
0x18000cc62  xor     rcx, rsp; StackCookie
0x18000cc65  call    __security_check_cookie
0x18000cc6a  mov     rbx, [rsp+490h+arg_8]
0x18000cc72  add     rsp, 490h
0x18000cc79  pop     rbp
0x18000cc7a  retn
```
