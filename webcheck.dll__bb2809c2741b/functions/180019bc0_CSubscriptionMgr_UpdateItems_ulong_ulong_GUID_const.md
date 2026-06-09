# CSubscriptionMgr::UpdateItems(ulong,ulong,_GUID const *)

- ea: `0x180019bc0`
- end: `0x180019c9e`
- name: `?UpdateItems@CSubscriptionMgr@@UEAAJKKPEBU_GUID@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(CSubscriptionMgr *__hidden this, unsigned int, unsigned int, const struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180019bc0`
- `0x18001be60`
- `0x18002a010`

## import_xrefs

- `IEFRAME!__imp_SHRestricted2W` at `0x180019bf9`
- `IEFRAME!__imp_SHRestricted2W` at `0x180019bf9`
- `ole32!CoCreateInstance` at `0x180019c40`
- `ole32!CoCreateInstance` at `0x180019c40`

## pseudocode

```c
__int64 __fastcall CSubscriptionMgr::UpdateItems(CSubscriptionMgr *this, int a2, int a3, const struct _GUID *a4)
{
  char v6; // si
  HRESULT v8; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-38h] BYREF

  v6 = a2;
  if ( (a2 & 0xFFFFFFFE) != 0 || !a3 || !a4 )
    return 2147942487LL;
  if ( (unsigned int)SHRestricted2W(1342177289, 0, 0) )
  {
    SGMessageBox(0, 0x1FBCu, 0);
    return 2147942405LL;
  }
  else
  {
    ppv = 0;
    v8 = CoCreateInstance(&CLSID_SyncMgr, 0, 0x17u, &IID_ISyncMgrSynchronizeInvoke, &ppv);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, _QWORD, const struct _GUID *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             4 * (v6 & 1u) + 2,
             &CLSID_WebCheckOfflineSync,
             (unsigned int)(16 * a3),
             a4);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x180019bc0  push    rbx
0x180019bc2  push    rbp
0x180019bc3  push    rsi
0x180019bc4  push    rdi
0x180019bc5  sub     rsp, 48h
0x180019bc9  mov     rbp, r9
0x180019bcc  mov     edi, r8d
0x180019bcf  mov     esi, edx
0x180019bd1  test    edx, 0FFFFFFFEh
0x180019bd7  jnz     loc_180019C90
0x180019bdd  test    r8d, r8d
0x180019be0  jz      loc_180019C90
0x180019be6  test    r9, r9
0x180019be9  jz      loc_180019C90
0x180019bef  xor     r8d, r8d
0x180019bf2  xor     edx, edx
0x180019bf4  mov     ecx, 50000009h
0x180019bf9  call    cs:__imp_SHRestricted2W
0x180019bff  test    eax, eax
0x180019c01  jz      short loc_180019C19
0x180019c03  xor     r8d, r8d; unsigned int
0x180019c06  mov     edx, 1FBCh; unsigned int
0x180019c0b  xor     ecx, ecx; hWnd
0x180019c0d  call    ?SGMessageBox@@YAHPEAUHWND__@@II@Z; SGMessageBox(HWND__ *,uint,uint)
0x180019c12  mov     eax, 80070005h
0x180019c17  jmp     short loc_180019C95
0x180019c19  xor     edx, edx; pUnkOuter
0x180019c1b  mov     [rsp+68h+var_38], 0
0x180019c24  lea     rax, [rsp+68h+var_38]
0x180019c29  lea     r9, IID_ISyncMgrSynchronizeInvoke; riid
0x180019c30  mov     [rsp+68h+ppv], rax; ppv
0x180019c35  lea     rcx, CLSID_SyncMgr; rclsid
0x180019c3c  lea     r8d, [rdx+17h]; dwClsContext
0x180019c40  call    cs:__imp_CoCreateInstance
0x180019c46  mov     ebx, eax
0x180019c48  test    eax, eax
0x180019c4a  js      short loc_180019C8C
0x180019c4c  mov     rcx, [rsp+68h+var_38]
0x180019c51  lea     r8, CLSID_WebCheckOfflineSync
0x180019c58  and     esi, 1
0x180019c5b  shl     edi, 4
0x180019c5e  mov     r9d, edi
0x180019c61  mov     [rsp+68h+ppv], rbp
0x180019c66  mov     rax, [rcx]
0x180019c69  lea     edx, ds:2[rsi*4]
0x180019c70  mov     rax, [rax+18h]
0x180019c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c79  mov     rcx, [rsp+68h+var_38]
0x180019c7e  mov     ebx, eax
0x180019c80  mov     rax, [rcx]
0x180019c83  mov     rax, [rax+10h]
0x180019c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c8c  mov     eax, ebx
0x180019c8e  jmp     short loc_180019C95
0x180019c90  mov     eax, 80070057h
0x180019c95  add     rsp, 48h
0x180019c99  pop     rdi
0x180019c9a  pop     rsi
0x180019c9b  pop     rbp
0x180019c9c  pop     rbx
0x180019c9d  retn
```
