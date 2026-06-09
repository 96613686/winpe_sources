# LogonScreenHelper::ClipAndAddBackground(TopViewer *,HINSTANCE__ *,_CREDSDLG_PROPERTIES *)

- ea: `0x1800176d0`
- end: `0x18001783c`
- name: `?ClipAndAddBackground@LogonScreenHelper@@QEAAXPEAVTopViewer@@PEAUHINSTANCE__@@PEAU_CREDSDLG_PROPERTIES@@@Z`
- size: `364`
- prototype: `void(LogonScreenHelper *__hidden this, struct TopViewer *, HINSTANCE, struct _CREDSDLG_PROPERTIES *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800190c0`

## callees

- `0x180016f48`
- `0x18001716c`
- `0x1800176d0`
- `0x180017e00`
- `0x18001d010`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800177e4`
- `GDI32!DeleteObject` at `0x1800177e4`
- `ole32!CoCreateInstance` at `0x180017755`
- `ole32!CoCreateInstance` at `0x180017755`
- `USER32!GetSystemMetrics` at `0x180017718`
- `USER32!GetSystemMetrics` at `0x180017727`
- `USER32!GetSystemMetrics` at `0x180017718`
- `USER32!GetSystemMetrics` at `0x180017727`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800177d0`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800177d0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800177b4`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800177b4`
- `DUI70!StrToID` at `0x1800177a8`
- `DUI70!StrToID` at `0x1800177a8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800177d9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800177d9`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800177ba`

## string_xrefs

- `0x1800177a1`: `InsideFrame`

## pseudocode

```c
void __fastcall LogonScreenHelper::ClipAndAddBackground(
        LogonScreenHelper *this,
        struct TopViewer *a2,
        HINSTANCE a3,
        struct _CREDSDLG_PROPERTIES *a4)
{
  __int64 v4; // rax
  int SystemMetrics; // edi
  int v9; // eax
  unsigned int v10; // esi
  LogonScreenHelper *v11; // rcx
  int v12; // r15d
  LogonScreenHelper *v13; // rcx
  struct DirectUI::Value *v14; // rbp
  unsigned __int16 v15; // ax
  DirectUI::Element *Descendent; // rax
  const unsigned __int16 *ClosestBackground; // rax
  LogonScreenHelper *v18; // rcx
  unsigned __int8 v19; // [rsp+28h] [rbp-30h]
  HGDIOBJ ho; // [rsp+60h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+20h] BYREF

  ho = this;
  v4 = *((_QWORD *)a4 + 1);
  if ( v4 && *(_DWORD *)(v4 + 8) && *(_QWORD *)(v4 + 64) )
  {
    SystemMetrics = GetSystemMetrics(0);
    v9 = GetSystemMetrics(1);
    ppv = 0;
    v10 = v9;
    if ( CoCreateInstance(&CLSID_AuthUIBackground, 0, 1u, &GUID_6f7aef3e_2780_4a3f_82c3_5c078663af2a, &ppv) < 0 )
      goto LABEL_10;
    v12 = 0;
    ho = 0;
    if ( (*(int (__fastcall **)(LPVOID, HGDIOBJ *))(*(_QWORD *)ppv + 24LL))(ppv, &ho) >= 0 )
    {
      v14 = LogonScreenHelper::AddBackgroundFromHBITMAP(v13, a2, (HBITMAP)ho, SystemMetrics, v10, v19);
      if ( v14 )
      {
        v15 = StrToID(L"InsideFrame");
        Descendent = DirectUI::Element::FindDescendent(a2, v15);
        v12 = 1;
        DirectUI::Element::SetValue(
          Descendent,
          (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
          1,
          v14);
        DirectUI::Value::Release(v14);
      }
      DeleteObject(ho);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( !v12 )
    {
LABEL_10:
      ClosestBackground = LogonScreenHelper::FindClosestBackground(v11, a4, SystemMetrics, v10);
      LogonScreenHelper::AddBackground(v18, a2, a3, SystemMetrics, v10, ClosestBackground);
    }
  }
}

```

## disassembly

```asm
0x1800176d0  mov     [rsp+arg_8], rbx
0x1800176d5  mov     [rsp+arg_10], rbp
0x1800176da  mov     [rsp+ho], rcx
0x1800176df  push    rsi
0x1800176e0  push    rdi
0x1800176e1  push    r12
0x1800176e3  push    r14
0x1800176e5  push    r15
0x1800176e7  sub     rsp, 30h
0x1800176eb  mov     rax, [r9+8]
0x1800176ef  mov     r14, r9
0x1800176f2  mov     r12, r8
0x1800176f5  mov     rbx, rdx
0x1800176f8  test    rax, rax
0x1800176fb  jz      loc_180017825
0x180017701  cmp     dword ptr [rax+8], 0
0x180017705  jz      loc_180017825
0x18001770b  cmp     qword ptr [rax+40h], 0
0x180017710  jz      loc_180017825
0x180017716  xor     ecx, ecx; nIndex
0x180017718  call    cs:__imp_GetSystemMetrics
0x18001771e  mov     ebp, 1
0x180017723  mov     edi, eax
0x180017725  mov     ecx, ebp; nIndex
0x180017727  call    cs:__imp_GetSystemMetrics
0x18001772d  lea     r9, _GUID_6f7aef3e_2780_4a3f_82c3_5c078663af2a; riid
0x180017734  mov     [rsp+58h+arg_18], 0
0x18001773d  mov     esi, eax
0x18001773f  lea     rcx, CLSID_AuthUIBackground; rclsid
0x180017746  lea     rax, [rsp+58h+arg_18]
0x18001774b  mov     r8d, ebp; dwClsContext
0x18001774e  xor     edx, edx; pUnkOuter
0x180017750  mov     [rsp+58h+ppv], rax; ppv
0x180017755  call    cs:__imp_CoCreateInstance
0x18001775b  test    eax, eax
0x18001775d  js      loc_180017800
0x180017763  mov     rcx, [rsp+58h+arg_18]
0x180017768  lea     rdx, [rsp+58h+ho]
0x18001776d  xor     r15d, r15d
0x180017770  mov     [rsp+58h+ho], r15
0x180017775  mov     rax, [rcx]
0x180017778  mov     rax, [rax+18h]
0x18001777c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017781  test    eax, eax
0x180017783  js      short loc_1800177EA
0x180017785  mov     r8, [rsp+58h+ho]; HBITMAP
0x18001778a  mov     r9d, edi; unsigned int
0x18001778d  mov     rdx, rbx; struct TopViewer *
0x180017790  mov     dword ptr [rsp+58h+ppv], esi; unsigned int
0x180017794  call    ?AddBackgroundFromHBITMAP@LogonScreenHelper@@QEAAPEAVValue@DirectUI@@PEAVTopViewer@@PEAUHBITMAP__@@IIE@Z; LogonScreenHelper::AddBackgroundFromHBITMAP(TopViewer *,HBITMAP__ *,uint,uint,uchar)
0x180017799  mov     rbp, rax
0x18001779c  test    rax, rax
0x18001779f  jz      short loc_1800177DF
0x1800177a1  lea     rcx, aInsideframe; "InsideFrame"
0x1800177a8  call    cs:__imp_StrToID
0x1800177ae  movzx   edx, ax
0x1800177b1  mov     rcx, rbx
0x1800177b4  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800177ba  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800177c1  mov     r15d, 1
0x1800177c7  mov     r8d, r15d
0x1800177ca  mov     rcx, rax
0x1800177cd  mov     r9, rbp
0x1800177d0  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800177d6  mov     rcx, rbp
0x1800177d9  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800177df  mov     rcx, [rsp+58h+ho]; ho
0x1800177e4  call    cs:__imp_DeleteObject
0x1800177ea  mov     rcx, [rsp+58h+arg_18]
0x1800177ef  mov     rax, [rcx]
0x1800177f2  mov     rax, [rax+10h]
0x1800177f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177fb  test    r15d, r15d
0x1800177fe  jnz     short loc_180017825
0x180017800  mov     r9d, esi; int
0x180017803  mov     r8d, edi; int
0x180017806  mov     rdx, r14; struct _CREDSDLG_PROPERTIES *
0x180017809  call    ?FindClosestBackground@LogonScreenHelper@@QEAAPEBGPEAU_CREDSDLG_PROPERTIES@@HH@Z; LogonScreenHelper::FindClosestBackground(_CREDSDLG_PROPERTIES *,int,int)
0x18001780e  mov     qword ptr [rsp+58h+var_30], rax; unsigned __int16 *
0x180017813  mov     r9d, edi; int
0x180017816  mov     r8, r12; HINSTANCE
0x180017819  mov     dword ptr [rsp+58h+ppv], esi; int
0x18001781d  mov     rdx, rbx; struct TopViewer *
0x180017820  call    ?AddBackground@LogonScreenHelper@@QEAAXPEAVTopViewer@@PEAUHINSTANCE__@@HHPEBG@Z; LogonScreenHelper::AddBackground(TopViewer *,HINSTANCE__ *,int,int,ushort const *)
0x180017825  mov     rbx, [rsp+58h+arg_8]
0x18001782a  mov     rbp, [rsp+58h+arg_10]
0x18001782f  add     rsp, 30h
0x180017833  pop     r15
0x180017835  pop     r14
0x180017837  pop     r12
0x180017839  pop     rdi
0x18001783a  pop     rsi
0x18001783b  retn
```
