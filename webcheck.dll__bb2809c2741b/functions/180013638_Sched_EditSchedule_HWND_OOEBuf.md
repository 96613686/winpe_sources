# Sched_EditSchedule(HWND__ *,OOEBuf *)

- ea: `0x180013638`
- end: `0x180013884`
- name: `?Sched_EditSchedule@@YAHPEAUHWND__@@PEAUOOEBuf@@@Z`
- size: `588`
- prototype: `__int64 __fastcall(HWND hWnd, struct OOEBuf *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013e38`
- `0x180014060`

## callees

- `0x18000c328`
- `0x180013194`
- `0x180013378`
- `0x180013638`
- `0x18002924e`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `USER32!GetDlgItem` at `0x1800136b7`
- `USER32!GetDlgItem` at `0x1800136b7`
- `USER32!SendMessageW` at `0x1800136d2`
- `USER32!SendMessageW` at `0x1800137cc`
- `USER32!SendMessageW` at `0x180013818`
- `USER32!SendMessageW` at `0x18001382e`
- `USER32!SendMessageW` at `0x1800136d2`
- `USER32!SendMessageW` at `0x1800137cc`
- `USER32!SendMessageW` at `0x180013818`
- `USER32!SendMessageW` at `0x18001382e`
- `USER32!CheckRadioButton` at `0x18001378c`
- `USER32!CheckRadioButton` at `0x18001378c`
- `ole32!CoCreateInstance` at `0x1800136a1`
- `ole32!CoCreateInstance` at `0x1800136a1`
- `ole32!CoUninitialize` at `0x180013856`
- `ole32!CoUninitialize` at `0x180013856`
- `ole32!CoInitialize` at `0x180013675`
- `ole32!CoInitialize` at `0x180013675`

## pseudocode

```c
__int64 __fastcall Sched_EditSchedule(HWND hWnd, struct OOEBuf *a2)
{
  HWND DlgItem; // rdi
  int v5; // r15d
  struct SCHED_LIST_DATA *Data; // rax
  struct SCHED_LIST_DATA *v7; // rbx
  int v8; // eax
  bool v9; // cf
  struct ISyncSchedule *v11; // [rsp+30h] [rbp-D0h] BYREF
  int v12; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  LPARAM lParam; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+5Ch] [rbp-A4h]
  int v16; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v17[264]; // [rsp+B0h] [rbp-50h] BYREF

  ppv = 0;
  if ( CoInitialize(0) >= 0 )
  {
    if ( CoCreateInstance(&CLSID_SyncMgr, 0, 0x17u, &IID_ISyncScheduleMgr, &ppv) >= 0 )
    {
      DlgItem = GetDlgItem(hWnd, 2105);
      v5 = SendMessageW(DlgItem, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
      Data = SchedList_GetData(DlgItem, v5);
      v7 = Data;
      if ( Data )
      {
        v11 = 0;
        if ( (*(int (__fastcall **)(LPVOID, struct SCHED_LIST_DATA *, _QWORD, struct ISyncSchedule **))(*(_QWORD *)ppv + 40LL))(
               ppv,
               Data,
               0,
               &v11) >= 0 )
        {
          if ( *((_DWORD *)v7 + 4) )
            (*(void (__fastcall **)(struct ISyncSchedule *, GUID *, char *, __int64))(*(_QWORD *)v11 + 136LL))(
              v11,
              &CLSID_WebCheckOfflineSync,
              (char *)a2 + 116,
              1);
          if ( !(*(unsigned int (__fastcall **)(struct ISyncSchedule *, HWND, _QWORD))(*(_QWORD *)v11 + 120LL))(
                  v11,
                  hWnd,
                  0) )
          {
            v8 = IsCookieOnSchedule(v11, (struct _GUID *)((char *)a2 + 116));
            *((_DWORD *)v7 + 4) = v8;
            if ( v8 )
              CheckRadioButton(hWnd, 2089, 2100, 2100);
            memset_0(&lParam, 0, 0x58u);
            v9 = *((_DWORD *)v7 + 4) != 0;
            v16 = 61440;
            v15 = v9 ? 0x2000 : 4096;
            SendMessageW(DlgItem, 0x102Bu, v5, (LPARAM)&lParam);
          }
          v12 = 260;
          if ( (*(int (__fastcall **)(struct ISyncSchedule *, int *, unsigned __int16 *))(*(_QWORD *)v11 + 56LL))(
                 v11,
                 &v12,
                 v17) >= 0 )
          {
            SchedList_SetName(DlgItem, v5, v17);
            SendMessageW(DlgItem, 0x101Eu, 0, 0xFFFF);
          }
          SendMessageW(hWnd, 0x28u, (WPARAM)DlgItem, 1);
          (*(void (__fastcall **)(struct ISyncSchedule *))(*(_QWORD *)v11 + 16LL))(v11);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    CoUninitialize();
  }
  return 0;
}

```

## disassembly

```asm
0x180013638  mov     [rsp-8+arg_10], rbx
0x18001363d  push    rbp
0x18001363e  push    rsi
0x18001363f  push    rdi
0x180013640  push    r14
0x180013642  push    r15
0x180013644  lea     rbp, [rsp-1D0h]
0x18001364c  sub     rsp, 2D0h
0x180013653  mov     rax, cs:__security_cookie
0x18001365a  xor     rax, rsp
0x18001365d  mov     [rbp+1F0h+var_30], rax
0x180013664  mov     rsi, rcx
0x180013667  mov     [rsp+2F0h+var_2B0], 0
0x180013670  xor     ecx, ecx; pvReserved
0x180013672  mov     r14, rdx
0x180013675  call    cs:__imp_CoInitialize
0x18001367b  test    eax, eax
0x18001367d  js      loc_18001385C
0x180013683  xor     edx, edx; pUnkOuter
0x180013685  lea     rax, [rsp+2F0h+var_2B0]
0x18001368a  lea     r9, IID_ISyncScheduleMgr; riid
0x180013691  mov     [rsp+2F0h+ppv], rax; ppv
0x180013696  lea     rcx, CLSID_SyncMgr; rclsid
0x18001369d  lea     r8d, [rdx+17h]; dwClsContext
0x1800136a1  call    cs:__imp_CoCreateInstance
0x1800136a7  test    eax, eax
0x1800136a9  js      loc_180013856
0x1800136af  mov     edx, 839h; nIDDlgItem
0x1800136b4  mov     rcx, rsi; hDlg
0x1800136b7  call    cs:__imp_GetDlgItem
0x1800136bd  mov     r9d, 2; lParam
0x1800136c3  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x1800136c7  mov     rcx, rax; hWnd
0x1800136ca  mov     edx, 100Ch; Msg
0x1800136cf  mov     rdi, rax
0x1800136d2  call    cs:__imp_SendMessageW
0x1800136d8  mov     edx, eax; int
0x1800136da  mov     rcx, rdi; HWND
0x1800136dd  mov     r15, rax
0x1800136e0  call    ?SchedList_GetData@@YAPEAUSCHED_LIST_DATA@@PEAUHWND__@@H@Z; SchedList_GetData(HWND__ *,int)
0x1800136e5  mov     rbx, rax
0x1800136e8  test    rax, rax
0x1800136eb  jz      loc_180013856
0x1800136f1  mov     r10, [rsp+2F0h+var_2B0]
0x1800136f6  lea     r9, [rsp+2F0h+var_2C0]
0x1800136fb  mov     [rsp+2F0h+var_2C0], 0
0x180013704  xor     r8d, r8d
0x180013707  mov     rdx, rbx
0x18001370a  mov     rcx, [r10]
0x18001370d  mov     rax, [rcx+28h]
0x180013711  mov     rcx, r10
0x180013714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013719  test    eax, eax
0x18001371b  js      loc_180013845
0x180013721  cmp     dword ptr [rbx+10h], 0
0x180013725  jz      short loc_18001374C
0x180013727  mov     rcx, [rsp+2F0h+var_2C0]
0x18001372c  lea     r8, [r14+74h]
0x180013730  mov     r9d, 1
0x180013736  lea     rdx, CLSID_WebCheckOfflineSync
0x18001373d  mov     rax, [rcx]
0x180013740  mov     rax, [rax+88h]
0x180013747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001374c  mov     rcx, [rsp+2F0h+var_2C0]
0x180013751  xor     r8d, r8d
0x180013754  mov     rdx, rsi
0x180013757  mov     rax, [rcx]
0x18001375a  mov     rax, [rax+78h]
0x18001375e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013763  test    eax, eax
0x180013765  jnz     short loc_1800137D2
0x180013767  mov     rcx, [rsp+2F0h+var_2C0]; struct ISyncSchedule *
0x18001376c  lea     rdx, [r14+74h]; struct _GUID *
0x180013770  call    ?IsCookieOnSchedule@@YAHPEAUISyncSchedule@@PEAU_GUID@@@Z; IsCookieOnSchedule(ISyncSchedule *,_GUID *)
0x180013775  mov     [rbx+10h], eax
0x180013778  test    eax, eax
0x18001377a  jz      short loc_180013792
0x18001377c  mov     r8d, 834h; nIDLastButton
0x180013782  mov     rcx, rsi; hDlg
0x180013785  mov     r9d, r8d; nIDCheckButton
0x180013788  lea     edx, [r8-0Bh]; nIDFirstButton
0x18001378c  call    cs:__imp_CheckRadioButton
0x180013792  xor     edx, edx; Val
0x180013794  lea     rcx, [rsp+2F0h+lParam]; void *
0x180013799  lea     r8d, [rdx+58h]; Size
0x18001379d  call    memset_0
0x1800137a2  mov     eax, [rbx+10h]
0x1800137a5  lea     r9, [rsp+2F0h+lParam]; lParam
0x1800137aa  neg     eax
0x1800137ac  movsxd  r8, r15d; wParam
0x1800137af  mov     eax, 1000h
0x1800137b4  mov     [rsp+2F0h+var_290], 0F000h
0x1800137bc  sbb     ecx, ecx
0x1800137be  and     ecx, eax
0x1800137c0  add     ecx, eax
0x1800137c2  mov     [rsp+2F0h+var_294], ecx
0x1800137c6  lea     edx, [rax+2Bh]; Msg
0x1800137c9  mov     rcx, rdi; hWnd
0x1800137cc  call    cs:__imp_SendMessageW
0x1800137d2  mov     rcx, [rsp+2F0h+var_2C0]
0x1800137d7  lea     r8, [rbp+1F0h+var_240]
0x1800137db  mov     [rsp+2F0h+var_2B8], 104h
0x1800137e3  lea     rdx, [rsp+2F0h+var_2B8]
0x1800137e8  mov     rax, [rcx]
0x1800137eb  mov     rax, [rax+38h]
0x1800137ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137f4  test    eax, eax
0x1800137f6  js      short loc_18001381E
0x1800137f8  lea     r8, [rbp+1F0h+var_240]; unsigned __int16 *
0x1800137fc  mov     edx, r15d; int
0x1800137ff  mov     rcx, rdi; HWND
0x180013802  call    ?SchedList_SetName@@YAXPEAUHWND__@@HPEAG@Z; SchedList_SetName(HWND__ *,int,ushort *)
0x180013807  mov     r9d, 0FFFFh; lParam
0x18001380d  xor     r8d, r8d; wParam
0x180013810  mov     edx, 101Eh; Msg
0x180013815  mov     rcx, rdi; hWnd
0x180013818  call    cs:__imp_SendMessageW
0x18001381e  mov     r9d, 1; lParam
0x180013824  mov     r8, rdi; wParam
0x180013827  mov     rcx, rsi; hWnd
0x18001382a  lea     edx, [r9+27h]; Msg
0x18001382e  call    cs:__imp_SendMessageW
0x180013834  mov     rcx, [rsp+2F0h+var_2C0]
0x180013839  mov     rax, [rcx]
0x18001383c  mov     rax, [rax+10h]
0x180013840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013845  mov     rcx, [rsp+2F0h+var_2B0]
0x18001384a  mov     rax, [rcx]
0x18001384d  mov     rax, [rax+10h]
0x180013851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013856  call    cs:__imp_CoUninitialize
0x18001385c  xor     eax, eax
0x18001385e  mov     rcx, [rbp+1F0h+var_30]
0x180013865  xor     rcx, rsp; StackCookie
0x180013868  call    __security_check_cookie
0x18001386d  mov     rbx, [rsp+2F0h+arg_10]
0x180013875  add     rsp, 2D0h
0x18001387c  pop     r15
0x18001387e  pop     r14
0x180013880  pop     rdi
0x180013881  pop     rsi
0x180013882  pop     rbp
0x180013883  retn
```
