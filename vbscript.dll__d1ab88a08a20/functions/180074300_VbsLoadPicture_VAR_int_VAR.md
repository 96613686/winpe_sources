# VbsLoadPicture(VAR *,int,VAR *)

- ea: `0x180074300`
- end: `0x1800744cf`
- name: `?VbsLoadPicture@@YAJPEAVVAR@@H0@Z`
- size: `463`
- prototype: `__int64 __fastcall(struct VAR *this, int, struct VAR *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x180003f00`
- `0x180016a60`
- `0x180025090`
- `0x18002580c`
- `0x180026570`
- `0x180037434`
- `0x180074300`
- `0x1800744d8`
- `0x18007a010`

## import_xrefs

- `OLEAUT32!__imp_OleLoadPicture` at `0x180074466`
- `OLEAUT32!__imp_OleLoadPicture` at `0x180074466`
- `OLE32!StgIsStorageFile` at `0x18007439f`
- `OLE32!StgIsStorageFile` at `0x18007439f`
- `OLE32!StgOpenStorage` at `0x1800743f2`
- `OLE32!StgOpenStorage` at `0x1800743f2`
- `OLE32!StgCreateDocfile` at `0x1800743cb`
- `OLE32!StgCreateDocfile` at `0x1800743cb`

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
0x180074300  mov     [rsp-18h+arg_8], rbx
0x180074305  mov     [rsp-18h+arg_10], rsi
0x18007430a  push    rbp
0x18007430b  push    rdi
0x18007430c  push    r15
0x18007430e  mov     rbp, rsp
0x180074311  sub     rsp, 50h
0x180074315  mov     r15d, 1
0x18007431b  mov     [rbp+lpvObj], 0
0x180074323  mov     [rcx], r15w
0x180074327  mov     rsi, r8
0x18007432a  mov     ebx, edx
0x18007432c  mov     [rbp+ppstgOpen], 0
0x180074334  mov     rdi, rcx
0x180074337  mov     [rbp+lpstream], 0
0x18007433f  call    ?GetCurrentOleScript@CScriptRuntime@@SAPEAVCOleScript@@XZ; CScriptRuntime::GetCurrentOleScript(void)
0x180074344  test    rax, rax
0x180074347  jz      loc_1800744B4
0x18007434d  xor     edx, edx; struct _GUID *
0x18007434f  mov     rcx, rax; this
0x180074352  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x180074357  cmp     eax, r15d
0x18007435a  jz      loc_1800744B4
0x180074360  cmp     ebx, r15d
0x180074363  jz      short loc_180074374
0x180074365  mov     ecx, 800A01C2h; int
0x18007436a  call    ?VbsLoadPictureMapHR@@YAJJ@Z; VbsLoadPictureMapHR(long)
0x18007436f  jmp     loc_1800744B9
0x180074374  xor     edx, edx; int
0x180074376  mov     rcx, rsi; this
0x180074379  call    ?PvarGetVarVal@VAR@@QEAAPEAV1@H@Z; VAR::PvarGetVarVal(int)
0x18007437e  cmp     r15w, [rax]
0x180074382  jnz     short loc_18007438B
0x180074384  mov     ecx, 800A005Eh
0x180074389  jmp     short loc_18007436A
0x18007438b  mov     edx, 8; vt
0x180074390  mov     rcx, rax; this
0x180074393  call    ?PvarConvert@VAR@@QEAAPEAV1@H@Z; VAR::PvarConvert(int)
0x180074398  mov     rbx, [rax+8]
0x18007439c  mov     rcx, rbx; pwcsName
0x18007439f  call    cs:__imp_StgIsStorageFile
0x1800743a6  nop     dword ptr [rax+rax+00h]
0x1800743ab  test    eax, eax
0x1800743ad  jns     short loc_1800743B3
0x1800743af  mov     ecx, eax
0x1800743b1  jmp     short loc_18007436A
0x1800743b3  mov     esi, 10h
0x1800743b8  mov     rcx, rbx; pwcsName
0x1800743bb  test    eax, eax
0x1800743bd  jz      short loc_1800743D9
0x1800743bf  lea     r9, [rbp+ppstgOpen]; ppstgOpen
0x1800743c3  xor     r8d, r8d; reserved
0x1800743c6  mov     edx, 30012h; grfMode
0x1800743cb  call    cs:__imp_StgCreateDocfile
0x1800743d2  nop     dword ptr [rax+rax+00h]
0x1800743d7  jmp     short loc_1800743FE
0x1800743d9  lea     rax, [rbp+ppstgOpen]
0x1800743dd  xor     r9d, r9d; snbExclude
0x1800743e0  mov     [rsp+50h+var_28], rax; ppstgOpen
0x1800743e5  mov     r8d, esi; grfMode
0x1800743e8  xor     edx, edx; pstgPriority
0x1800743ea  mov     [rsp+50h+reserved], 0; reserved
0x1800743f2  call    cs:__imp_StgOpenStorage
0x1800743f9  nop     dword ptr [rax+rax+00h]
0x1800743fe  test    eax, eax
0x180074400  js      short loc_1800743AF
0x180074402  mov     rcx, [rbp+ppstgOpen]
0x180074406  lea     rdx, [rbp+lpstream]
0x18007440a  mov     [rsp+50h+var_28], rdx
0x18007440f  mov     r9d, esi
0x180074412  xor     r8d, r8d
0x180074415  mov     [rsp+50h+reserved], 0
0x18007441d  lea     rdx, aContents; "CONTENTS"
0x180074424  mov     rax, [rcx]
0x180074427  mov     rax, [rax+20h]
0x18007442b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074430  mov     ebx, eax
0x180074432  test    eax, eax
0x180074434  jns     short loc_18007444D
0x180074436  mov     rcx, [rbp+ppstgOpen]
0x18007443a  mov     rdx, [rcx]
0x18007443d  mov     rax, [rdx+10h]
0x180074441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074446  mov     ecx, ebx
0x180074448  jmp     loc_18007436A
0x18007444d  mov     rcx, [rbp+lpstream]; lpstream
0x180074451  lea     rax, [rbp+lpvObj]
0x180074455  lea     r9, IID_IDispatch; riid
0x18007445c  mov     qword ptr [rsp+50h+reserved], rax; lplpvObj
0x180074461  mov     r8d, r15d; fRunmode
0x180074464  xor     edx, edx; lSize
0x180074466  call    cs:__imp_OleLoadPicture
0x18007446d  nop     dword ptr [rax+rax+00h]
0x180074472  mov     rcx, [rbp+lpstream]
0x180074476  mov     ebx, eax
0x180074478  mov     rdx, [rcx]
0x18007447b  mov     rax, [rdx+10h]
0x18007447f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074484  mov     rcx, [rbp+ppstgOpen]
0x180074488  mov     rdx, [rcx]
0x18007448b  mov     rax, [rdx+10h]
0x18007448f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074494  test    ebx, ebx
0x180074496  js      short loc_180074446
0x180074498  mov     rdx, [rbp+lpvObj]; struct IDispatch *
0x18007449c  mov     rcx, rdi; this
0x18007449f  call    ?SetIDispatch@VAR@@QEAAXPEAUIDispatch@@@Z; VAR::SetIDispatch(IDispatch *)
0x1800744a4  mov     rcx, rdi; this
0x1800744a7  call    ?MoveToHeap@VAR@@QEAAJXZ; VAR::MoveToHeap(void)
0x1800744ac  mov     rcx, [rbp+lpvObj]
0x1800744b0  mov     ebx, eax
0x1800744b2  jmp     short loc_18007443A
0x1800744b4  mov     eax, 800A0011h
0x1800744b9  lea     r11, [rsp+50h+var_s0]
0x1800744be  mov     rbx, [r11+28h]
0x1800744c2  mov     rsi, [r11+30h]
0x1800744c6  mov     rsp, r11
0x1800744c9  pop     r15
0x1800744cb  pop     rdi
0x1800744cc  pop     rbp
0x1800744cd  retn
```
