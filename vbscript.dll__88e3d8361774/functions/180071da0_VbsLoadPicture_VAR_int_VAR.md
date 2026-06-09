# VbsLoadPicture(VAR *,int,VAR *)

- ea: `0x180071da0`
- end: `0x180071f56`
- name: `?VbsLoadPicture@@YAJPEAVVAR@@H0@Z`
- size: `438`
- prototype: `__int64 __fastcall(struct VAR *this, int, struct VAR *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x1800038c0`
- `0x180004610`
- `0x1800060b0`
- `0x18001c950`
- `0x180035ec4`
- `0x180039668`
- `0x180071da0`
- `0x180071f5c`
- `0x180077010`

## import_xrefs

- `OLEAUT32!__imp_OleLoadPicture` at `0x180071ef4`
- `OLEAUT32!__imp_OleLoadPicture` at `0x180071ef4`
- `OLE32!StgIsStorageFile` at `0x180071e3f`
- `OLE32!StgIsStorageFile` at `0x180071e3f`
- `OLE32!StgOpenStorage` at `0x180071e86`
- `OLE32!StgOpenStorage` at `0x180071e86`
- `OLE32!StgCreateDocfile` at `0x180071e65`
- `OLE32!StgCreateDocfile` at `0x180071e65`

## pseudocode

```c
__int64 __fastcall VbsLoadPicture(struct VAR *this, int a2, struct VAR *a3)
{
  COleScript *CurrentOleScript; // rax
  int v7; // ecx
  struct VAR *VarVal; // rax
  const WCHAR *v10; // rbx
  HRESULT IsStorageFile; // eax
  HRESULT v12; // ebx
  void *v13; // rcx
  HRESULT v14; // eax
  LPVOID lpvObj; // [rsp+40h] [rbp-10h] BYREF
  IStorage *ppstgOpen; // [rsp+70h] [rbp+20h] BYREF
  LPSTREAM lpstream; // [rsp+88h] [rbp+38h] BYREF

  lpvObj = 0;
  *(_WORD *)this = 1;
  ppstgOpen = 0;
  lpstream = 0;
  CurrentOleScript = CScriptRuntime::GetCurrentOleScript();
  if ( CurrentOleScript && (unsigned int)COleScript::InSafeMode(CurrentOleScript, 0) != 1 )
  {
    if ( a2 != 1 )
    {
      v7 = -2146827838;
      return VbsLoadPictureMapHR(v7);
    }
    VarVal = VAR::PvarGetVarVal(a3, 0);
    if ( *(_WORD *)VarVal == 1 )
    {
      v7 = -2146828194;
      return VbsLoadPictureMapHR(v7);
    }
    v10 = (const WCHAR *)*((_QWORD *)VAR::PvarConvert(VarVal, 8u) + 1);
    IsStorageFile = StgIsStorageFile(v10);
    if ( IsStorageFile < 0
      || (!IsStorageFile
        ? (IsStorageFile = StgOpenStorage(v10, 0, 0x10u, 0, 0, &ppstgOpen))
        : (IsStorageFile = StgCreateDocfile(v10, 0x30012u, 0, &ppstgOpen)),
          IsStorageFile < 0) )
    {
      v7 = IsStorageFile;
      return VbsLoadPictureMapHR(v7);
    }
    v12 = ((__int64 (__fastcall *)(IStorage *, const wchar_t *, _QWORD, __int64, _DWORD, LPSTREAM *))ppstgOpen->lpVtbl->OpenStream)(
            ppstgOpen,
            L"CONTENTS",
            0,
            16,
            0,
            &lpstream);
    if ( v12 >= 0 )
    {
      v12 = OleLoadPicture(lpstream, 0, 1, &IID_IDispatch, &lpvObj);
      ((void (__fastcall *)(LPSTREAM))lpstream->lpVtbl->Release)(lpstream);
      ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
      if ( v12 < 0 )
        goto LABEL_17;
      VAR::SetIDispatch(this, (struct IDispatch *)lpvObj);
      v14 = VAR::MoveToHeap(this);
      v13 = lpvObj;
      v12 = v14;
    }
    else
    {
      v13 = ppstgOpen;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
LABEL_17:
    v7 = v12;
    return VbsLoadPictureMapHR(v7);
  }
  return 2148139025LL;
}

```

## disassembly

```asm
0x180071da0  mov     [rsp-18h+arg_8], rbx
0x180071da5  mov     [rsp-18h+arg_10], rsi
0x180071daa  push    rbp
0x180071dab  push    rdi
0x180071dac  push    r15
0x180071dae  mov     rbp, rsp
0x180071db1  sub     rsp, 50h
0x180071db5  mov     r15d, 1
0x180071dbb  mov     [rbp+lpvObj], 0
0x180071dc3  mov     [rcx], r15w
0x180071dc7  mov     rsi, r8
0x180071dca  mov     ebx, edx
0x180071dcc  mov     [rbp+ppstgOpen], 0
0x180071dd4  mov     rdi, rcx
0x180071dd7  mov     [rbp+lpstream], 0
0x180071ddf  call    ?GetCurrentOleScript@CScriptRuntime@@SAPEAVCOleScript@@XZ; CScriptRuntime::GetCurrentOleScript(void)
0x180071de4  test    rax, rax
0x180071de7  jz      loc_180071F3C
0x180071ded  xor     edx, edx; struct _GUID *
0x180071def  mov     rcx, rax; this
0x180071df2  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x180071df7  cmp     eax, r15d
0x180071dfa  jz      loc_180071F3C
0x180071e00  cmp     ebx, r15d
0x180071e03  jz      short loc_180071E14
0x180071e05  mov     ecx, 800A01C2h; int
0x180071e0a  call    ?VbsLoadPictureMapHR@@YAJJ@Z; VbsLoadPictureMapHR(long)
0x180071e0f  jmp     loc_180071F41
0x180071e14  xor     edx, edx; int
0x180071e16  mov     rcx, rsi; this
0x180071e19  call    ?PvarGetVarVal@VAR@@QEAAPEAV1@H@Z; VAR::PvarGetVarVal(int)
0x180071e1e  cmp     r15w, [rax]
0x180071e22  jnz     short loc_180071E2B
0x180071e24  mov     ecx, 800A005Eh
0x180071e29  jmp     short loc_180071E0A
0x180071e2b  mov     edx, 8; vt
0x180071e30  mov     rcx, rax; this
0x180071e33  call    ?PvarConvert@VAR@@QEAAPEAV1@H@Z; VAR::PvarConvert(int)
0x180071e38  mov     rbx, [rax+8]
0x180071e3c  mov     rcx, rbx; pwcsName
0x180071e3f  call    cs:__imp_StgIsStorageFile
0x180071e45  test    eax, eax
0x180071e47  jns     short loc_180071E4D
0x180071e49  mov     ecx, eax
0x180071e4b  jmp     short loc_180071E0A
0x180071e4d  mov     esi, 10h
0x180071e52  mov     rcx, rbx; pwcsName
0x180071e55  test    eax, eax
0x180071e57  jz      short loc_180071E6D
0x180071e59  lea     r9, [rbp+ppstgOpen]; ppstgOpen
0x180071e5d  xor     r8d, r8d; reserved
0x180071e60  mov     edx, 30012h; grfMode
0x180071e65  call    cs:__imp_StgCreateDocfile
0x180071e6b  jmp     short loc_180071E8C
0x180071e6d  lea     rax, [rbp+ppstgOpen]
0x180071e71  xor     r9d, r9d; snbExclude
0x180071e74  mov     [rsp+50h+var_28], rax; ppstgOpen
0x180071e79  mov     r8d, esi; grfMode
0x180071e7c  xor     edx, edx; pstgPriority
0x180071e7e  mov     [rsp+50h+reserved], 0; reserved
0x180071e86  call    cs:__imp_StgOpenStorage
0x180071e8c  test    eax, eax
0x180071e8e  js      short loc_180071E49
0x180071e90  mov     rcx, [rbp+ppstgOpen]
0x180071e94  lea     rdx, [rbp+lpstream]
0x180071e98  mov     [rsp+50h+var_28], rdx
0x180071e9d  mov     r9d, esi
0x180071ea0  xor     r8d, r8d
0x180071ea3  mov     [rsp+50h+reserved], 0
0x180071eab  lea     rdx, aContents; "CONTENTS"
0x180071eb2  mov     rax, [rcx]
0x180071eb5  mov     rax, [rax+20h]
0x180071eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ebe  mov     ebx, eax
0x180071ec0  test    eax, eax
0x180071ec2  jns     short loc_180071EDB
0x180071ec4  mov     rcx, [rbp+ppstgOpen]
0x180071ec8  mov     rdx, [rcx]
0x180071ecb  mov     rax, [rdx+10h]
0x180071ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ed4  mov     ecx, ebx
0x180071ed6  jmp     loc_180071E0A
0x180071edb  mov     rcx, [rbp+lpstream]; lpstream
0x180071edf  lea     rax, [rbp+lpvObj]
0x180071ee3  lea     r9, IID_IDispatch; riid
0x180071eea  mov     qword ptr [rsp+50h+reserved], rax; lplpvObj
0x180071eef  mov     r8d, r15d; fRunmode
0x180071ef2  xor     edx, edx; lSize
0x180071ef4  call    cs:__imp_OleLoadPicture
0x180071efa  mov     rcx, [rbp+lpstream]
0x180071efe  mov     ebx, eax
0x180071f00  mov     rdx, [rcx]
0x180071f03  mov     rax, [rdx+10h]
0x180071f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f0c  mov     rcx, [rbp+ppstgOpen]
0x180071f10  mov     rdx, [rcx]
0x180071f13  mov     rax, [rdx+10h]
0x180071f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f1c  test    ebx, ebx
0x180071f1e  js      short loc_180071ED4
0x180071f20  mov     rdx, [rbp+lpvObj]; struct IDispatch *
0x180071f24  mov     rcx, rdi; this
0x180071f27  call    ?SetIDispatch@VAR@@QEAAXPEAUIDispatch@@@Z; VAR::SetIDispatch(IDispatch *)
0x180071f2c  mov     rcx, rdi; this
0x180071f2f  call    ?MoveToHeap@VAR@@QEAAJXZ; VAR::MoveToHeap(void)
0x180071f34  mov     rcx, [rbp+lpvObj]
0x180071f38  mov     ebx, eax
0x180071f3a  jmp     short loc_180071EC8
0x180071f3c  mov     eax, 800A0011h
0x180071f41  lea     r11, [rsp+50h+var_s0]
0x180071f46  mov     rbx, [r11+28h]
0x180071f4a  mov     rsi, [r11+30h]
0x180071f4e  mov     rsp, r11
0x180071f51  pop     r15
0x180071f53  pop     rdi
0x180071f54  pop     rbp
0x180071f55  retn
```
