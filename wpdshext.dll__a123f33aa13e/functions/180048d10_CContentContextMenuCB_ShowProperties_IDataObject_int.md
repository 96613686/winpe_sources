# CContentContextMenuCB::_ShowProperties(IDataObject *,int)

- ea: `0x180048d10`
- end: `0x180048e86`
- name: `?_ShowProperties@CContentContextMenuCB@@AEAAJPEAUIDataObject@@H@Z`
- size: `374`
- prototype: `__int64 __fastcall(CContentContextMenuCB *__hidden this, struct IDataObject *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180042340`

## callees

- `0x18002ff5c`
- `0x180048d10`
- `0x180078010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x180048e04`
- `SHLWAPI!__imp_SHCreateThread` at `0x180048e04`
- `ole32!CoTaskMemFree` at `0x180048e30`
- `ole32!CoTaskMemFree` at `0x180048e30`
- `ole32!CoTaskMemAlloc` at `0x180048d70`
- `ole32!CoTaskMemAlloc` at `0x180048d70`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x180048d34`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x180048d34`

## pseudocode

```c
__int64 __fastcall CContentContextMenuCB::_ShowProperties(CContentContextMenuCB *this, IUnknown *a2, int a3)
{
  HRESULT v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rdi
  LPSTREAM ppStm; // [rsp+68h] [rbp+20h] BYREF

  ppStm = 0;
  v5 = CoMarshalInterThreadInterfaceInStream(&IID_IDataObject, a2, &ppStm);
  if ( v5 >= 0 )
  {
    v8 = CoTaskMemAlloc(0x20u);
    if ( v8 )
    {
      (*(void (__fastcall **)(CContentContextMenuCB *))(*(_QWORD *)this + 8LL))(this);
      *v8 = *((_QWORD *)this + 4);
      v8[1] = *((_QWORD *)this + 4);
      v8[2] = ppStm;
      *((_DWORD *)v8 + 6) = a3;
      if ( !SHCreateThread(_PropSheetThreadProc, v8, 8u, 0) )
      {
        if ( ppStm )
        {
          ((void (__fastcall *)(LPSTREAM))ppStm->lpVtbl->Release)(ppStm);
          ppStm = 0;
        }
        CoTaskMemFree(v8);
        (*(void (__fastcall **)(CContentContextMenuCB *))(*(_QWORD *)this + 16LL))(this);
        v5 = -2147467259;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v7 = 427;
          goto LABEL_17;
        }
      }
    }
    else
    {
      if ( ppStm )
      {
        ((void (__fastcall *)(LPSTREAM))ppStm->lpVtbl->Release)(ppStm);
        ppStm = 0;
      }
      v5 = -2147024882;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v7 = 426;
        goto LABEL_17;
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v7 = 425;
LABEL_17:
      WPP_SF_d(v6[2], v7, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v5);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180048d10  push    rbx
0x180048d12  push    rbp
0x180048d13  push    rsi
0x180048d14  push    rdi
0x180048d15  sub     rsp, 28h
0x180048d19  mov     ebp, r8d
0x180048d1c  mov     [rsp+48h+ppStm], 0
0x180048d25  mov     rsi, rcx
0x180048d28  lea     r8, [rsp+48h+ppStm]; ppStm
0x180048d2d  lea     rcx, IID_IDataObject; riid
0x180048d34  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180048d3a  mov     ebx, eax
0x180048d3c  test    eax, eax
0x180048d3e  jns     short loc_180048D6B
0x180048d40  mov     rcx, cs:WPP_GLOBAL_Control
0x180048d47  lea     rax, WPP_GLOBAL_Control
0x180048d4e  cmp     rcx, rax
0x180048d51  jz      loc_180048E7B
0x180048d57  test    byte ptr [rcx+1Ch], 2
0x180048d5b  jz      loc_180048E7B
0x180048d61  mov     edx, 1A9h
0x180048d66  jmp     loc_180048E68
0x180048d6b  mov     ecx, 20h ; ' '; cb
0x180048d70  call    cs:__imp_CoTaskMemAlloc
0x180048d76  mov     rdi, rax
0x180048d79  test    rax, rax
0x180048d7c  jnz     short loc_180048DC9
0x180048d7e  mov     rcx, [rsp+48h+ppStm]
0x180048d83  test    rcx, rcx
0x180048d86  jz      short loc_180048D99
0x180048d88  mov     rax, [rcx]
0x180048d8b  mov     rax, [rax+10h]
0x180048d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d94  mov     [rsp+48h+ppStm], rdi
0x180048d99  mov     ebx, 8007000Eh
0x180048d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180048da5  lea     rax, WPP_GLOBAL_Control
0x180048dac  cmp     rcx, rax
0x180048daf  jz      loc_180048E7B
0x180048db5  test    byte ptr [rcx+1Ch], 2
0x180048db9  jz      loc_180048E7B
0x180048dbf  mov     edx, 1AAh
0x180048dc4  jmp     loc_180048E68
0x180048dc9  mov     rax, [rsi]
0x180048dcc  mov     rcx, rsi
0x180048dcf  mov     rax, [rax+8]
0x180048dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048dd8  mov     rax, [rsi+20h]
0x180048ddc  lea     rcx, ?_PropSheetThreadProc@@YAKPEAX@Z; pfnThreadProc
0x180048de3  mov     [rdi], rax
0x180048de6  xor     r9d, r9d; pfnCallback
0x180048de9  mov     rax, [rsi+20h]
0x180048ded  mov     rdx, rdi; pData
0x180048df0  mov     [rdi+8], rax
0x180048df4  mov     rax, [rsp+48h+ppStm]
0x180048df9  lea     r8d, [r9+8]; flags
0x180048dfd  mov     [rdi+10h], rax
0x180048e01  mov     [rdi+18h], ebp
0x180048e04  call    cs:__imp_SHCreateThread
0x180048e0a  test    eax, eax
0x180048e0c  jnz     short loc_180048E7B
0x180048e0e  mov     rcx, [rsp+48h+ppStm]
0x180048e13  test    rcx, rcx
0x180048e16  jz      short loc_180048E2D
0x180048e18  mov     rax, [rcx]
0x180048e1b  mov     rax, [rax+10h]
0x180048e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e24  mov     [rsp+48h+ppStm], 0
0x180048e2d  mov     rcx, rdi; pv
0x180048e30  call    cs:__imp_CoTaskMemFree
0x180048e36  mov     rax, [rsi]
0x180048e39  mov     rcx, rsi
0x180048e3c  mov     rax, [rax+10h]
0x180048e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e45  mov     ebx, 80004005h
0x180048e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048e51  lea     rax, WPP_GLOBAL_Control
0x180048e58  cmp     rcx, rax
0x180048e5b  jz      short loc_180048E7B
0x180048e5d  test    byte ptr [rcx+1Ch], 2
0x180048e61  jz      short loc_180048E7B
0x180048e63  mov     edx, 1ABh
0x180048e68  mov     rcx, [rcx+10h]
0x180048e6c  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180048e73  mov     r9d, ebx
0x180048e76  call    WPP_SF_d
0x180048e7b  mov     eax, ebx
0x180048e7d  add     rsp, 28h
0x180048e81  pop     rdi
0x180048e82  pop     rsi
0x180048e83  pop     rbp
0x180048e84  pop     rbx
0x180048e85  retn
```
