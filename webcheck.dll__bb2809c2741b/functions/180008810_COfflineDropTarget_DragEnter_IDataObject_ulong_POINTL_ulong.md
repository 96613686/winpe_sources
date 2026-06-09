# COfflineDropTarget::DragEnter(IDataObject *,ulong,_POINTL,ulong *)

- ea: `0x180008810`
- end: `0x1800089c1`
- name: `?DragEnter@COfflineDropTarget@@UEAAJPEAUIDataObject@@KU_POINTL@@PEAK@Z`
- size: `433`
- prototype: `__int64 __fastcall(COfflineDropTarget *__hidden this, struct IDataObject *, unsigned int, struct _POINTL, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008810`
- `0x180008b90`
- `0x180008ea0`
- `0x1800090d8`
- `0x180029280`
- `0x180029310`
- `0x18002a010`

## import_xrefs

- `USER32!RegisterClipboardFormatW` at `0x180008890`
- `USER32!RegisterClipboardFormatW` at `0x180008890`

## pseudocode

```c
__int64 __fastcall COfflineDropTarget::DragEnter(
        COfflineDropTarget *this,
        struct IDataObject *a2,
        __int64 a3,
        struct _POINTL a4,
        unsigned int *a5)
{
  __int64 v6; // rcx
  int v7; // r14d
  struct IDataObjectVtbl *lpVtbl; // rax
  __int64 v10; // r9
  struct IDataObjectVtbl *v11; // rax
  __int64 v12; // r9
  unsigned int DropEffect; // eax
  __int16 v15; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+32h] [rbp-CEh]
  __int16 v17; // [rsp+36h] [rbp-CAh]
  __int64 v18; // [rsp+38h] [rbp-C8h]
  int v19; // [rsp+40h] [rbp-C0h]
  int v20; // [rsp+44h] [rbp-BCh]
  __int64 v21; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v22[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v23[2088]; // [rsp+260h] [rbp+160h] BYREF

  v6 = *((_QWORD *)this + 1);
  v7 = a3;
  if ( v6 )
    (*(void (__fastcall **)(__int64, struct IDataObject *, __int64, struct _POINTL))(*(_QWORD *)v6 + 16LL))(
      v6,
      a2,
      a3,
      a4);
  *((_DWORD *)this + 5) = v7;
  *((_QWORD *)this + 1) = a2;
  if ( a2 )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))a2->lpVtbl->AddRef)(a2, a2, a3, a4);
    v20 = -1;
    v15 = RegisterClipboardFormatW(L"UniformResourceLocator");
    v16 = 0;
    v17 = 0;
    v18 = 0;
    *(_QWORD *)((char *)this + 28) = 0;
    *((_DWORD *)this + 6) = 0;
    lpVtbl = a2->lpVtbl;
    v19 = 1;
    v21 = 1;
    if ( !((unsigned int (__fastcall *)(struct IDataObject *, __int16 *))lpVtbl->QueryGetData)(a2, &v15) )
      *((_DWORD *)this + 7) = _GetURLData(a2, 2, v23, v10, v22) == 0;
    v15 = 15;
    if ( !((unsigned int (__fastcall *)(struct IDataObject *, __int16 *))a2->lpVtbl->QueryGetData)(a2, &v15) )
      *((_DWORD *)this + 6) = _ConvertHDROPData(a2, 0) == 0;
    v11 = a2->lpVtbl;
    v15 = 1;
    if ( !((unsigned int (__fastcall *)(struct IDataObject *, __int16 *))v11->QueryGetData)(a2, &v15) )
      *((_DWORD *)this + 8) = _GetURLData(a2, 3, v23, v12, v22) == 0;
  }
  if ( a5 )
  {
    DropEffect = COfflineDropTarget::GetDropEffect(this, a5);
    *((_DWORD *)this + 9) = DropEffect;
    *a5 = DropEffect;
  }
  return 0;
}

```

## disassembly

```asm
0x180008810  mov     [rsp-8+arg_10], rbx
0x180008815  mov     [rsp-8+arg_18], rsi
0x18000881a  push    rbp
0x18000881b  push    rdi
0x18000881c  push    r14
0x18000881e  lea     rbp, [rsp-11C0h]
0x180008826  mov     eax, 12C0h
0x18000882b  call    _alloca_probe
0x180008830  sub     rsp, rax
0x180008833  mov     rax, cs:__security_cookie
0x18000883a  xor     rax, rsp
0x18000883d  mov     [rbp+11D0h+var_20], rax
0x180008844  mov     rsi, [rbp+11D0h+arg_20]
0x18000884b  mov     rdi, rcx
0x18000884e  mov     rcx, [rcx+8]
0x180008852  mov     r14d, r8d
0x180008855  mov     rbx, rdx
0x180008858  test    rcx, rcx
0x18000885b  jz      short loc_180008869
0x18000885d  mov     rax, [rcx]
0x180008860  mov     rax, [rax+10h]
0x180008864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008869  mov     [rdi+14h], r14d
0x18000886d  mov     [rdi+8], rbx
0x180008871  test    rbx, rbx
0x180008874  jz      loc_180008983
0x18000887a  mov     rax, [rbx]
0x18000887d  mov     rcx, rbx
0x180008880  mov     rax, [rax+8]
0x180008884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008889  lea     rcx, aUniformresourc; "UniformResourceLocator"
0x180008890  call    cs:__imp_RegisterClipboardFormatW
0x180008896  lea     rdx, [rsp+12D0h+var_12A0]
0x18000889b  mov     [rsp+12D0h+var_128C], 0FFFFFFFFh
0x1800088a3  mov     [rsp+12D0h+var_12A0], ax
0x1800088a8  mov     rcx, rbx
0x1800088ab  xor     eax, eax
0x1800088ad  mov     [rsp+12D0h+var_129E], eax
0x1800088b1  mov     [rsp+12D0h+var_129A], ax
0x1800088b6  mov     [rsp+12D0h+var_1298], rax
0x1800088bb  lea     r14d, [rax+1]
0x1800088bf  mov     [rdi+1Ch], rax
0x1800088c3  mov     [rdi+18h], eax
0x1800088c6  mov     rax, [rbx]
0x1800088c9  mov     [rsp+12D0h+var_1290], r14d
0x1800088ce  mov     [rsp+12D0h+var_1288], r14
0x1800088d3  mov     rax, [rax+28h]
0x1800088d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088dc  test    eax, eax
0x1800088de  jnz     short loc_180008907
0x1800088e0  lea     rax, [rsp+12D0h+var_1280]
0x1800088e5  mov     rcx, rbx; struct IDataObject *
0x1800088e8  lea     r8, [rbp+11D0h+var_1070]; unsigned __int16 *
0x1800088ef  mov     [rsp+12D0h+var_12B0], rax; unsigned __int16 *
0x1800088f4  lea     edx, [r14+1]; int
0x1800088f8  call    ?_GetURLData@@YAJPEAUIDataObject@@HPEAGI1I@Z; _GetURLData(IDataObject *,int,ushort *,uint,ushort *,uint)
0x1800088fd  xor     ecx, ecx
0x1800088ff  test    eax, eax
0x180008901  setz    cl
0x180008904  mov     [rdi+1Ch], ecx
0x180008907  mov     eax, 0Fh
0x18000890c  lea     rdx, [rsp+12D0h+var_12A0]
0x180008911  mov     [rsp+12D0h+var_12A0], ax
0x180008916  mov     rcx, rbx
0x180008919  mov     rax, [rbx]
0x18000891c  mov     rax, [rax+28h]
0x180008920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008925  test    eax, eax
0x180008927  jnz     short loc_18000893D
0x180008929  xor     edx, edx; int
0x18000892b  mov     rcx, rbx; struct IDataObject *
0x18000892e  call    ?_ConvertHDROPData@@YAJPEAUIDataObject@@H@Z; _ConvertHDROPData(IDataObject *,int)
0x180008933  xor     ecx, ecx
0x180008935  test    eax, eax
0x180008937  setz    cl
0x18000893a  mov     [rdi+18h], ecx
0x18000893d  mov     rax, [rbx]
0x180008940  lea     rdx, [rsp+12D0h+var_12A0]
0x180008945  mov     rcx, rbx
0x180008948  mov     [rsp+12D0h+var_12A0], r14w
0x18000894e  mov     rax, [rax+28h]
0x180008952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008957  test    eax, eax
0x180008959  jnz     short loc_180008983
0x18000895b  lea     rax, [rsp+12D0h+var_1280]
0x180008960  mov     edx, 3; int
0x180008965  lea     r8, [rbp+11D0h+var_1070]; unsigned __int16 *
0x18000896c  mov     [rsp+12D0h+var_12B0], rax; unsigned __int16 *
0x180008971  mov     rcx, rbx; struct IDataObject *
0x180008974  call    ?_GetURLData@@YAJPEAUIDataObject@@HPEAGI1I@Z; _GetURLData(IDataObject *,int,ushort *,uint,ushort *,uint)
0x180008979  xor     ecx, ecx
0x18000897b  test    eax, eax
0x18000897d  setz    cl
0x180008980  mov     [rdi+20h], ecx
0x180008983  test    rsi, rsi
0x180008986  jz      short loc_180008998
0x180008988  mov     rdx, rsi; unsigned int *
0x18000898b  mov     rcx, rdi; this
0x18000898e  call    ?GetDropEffect@COfflineDropTarget@@QEAAKPEBK@Z; COfflineDropTarget::GetDropEffect(ulong const *)
0x180008993  mov     [rdi+24h], eax
0x180008996  mov     [rsi], eax
0x180008998  xor     eax, eax
0x18000899a  mov     rcx, [rbp+11D0h+var_20]
0x1800089a1  xor     rcx, rsp; StackCookie
0x1800089a4  call    __security_check_cookie
0x1800089a9  lea     r11, [rsp+12D0h+var_10]
0x1800089b1  mov     rbx, [r11+30h]
0x1800089b5  mov     rsi, [r11+38h]
0x1800089b9  mov     rsp, r11
0x1800089bc  pop     r14
0x1800089be  pop     rdi
0x1800089bf  pop     rbp
0x1800089c0  retn
```
