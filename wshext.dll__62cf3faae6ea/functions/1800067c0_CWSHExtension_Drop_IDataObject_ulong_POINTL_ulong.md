# CWSHExtension::Drop(IDataObject *,ulong,_POINTL,ulong *)

- ea: `0x1800067c0`
- end: `0x180006a33`
- name: `?Drop@CWSHExtension@@UEAAJPEAUIDataObject@@KU_POINTL@@PEAK@Z`
- size: `627`
- prototype: `__int64 __fastcall(CWSHExtension *__hidden this, struct IDataObject *, unsigned int, struct _POINTL, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800067c0`
- `0x180006a94`
- `0x18000d17e`
- `0x18000d1c0`
- `0x18000e010`

## import_xrefs

- `msvcrt!strcat_s` at `0x180006922`
- `msvcrt!strcat_s` at `0x180006922`
- `USER32!GetFocus` at `0x180006955`
- `USER32!GetFocus` at `0x1800069d5`
- `USER32!GetFocus` at `0x180006955`
- `USER32!GetFocus` at `0x1800069d5`
- `USER32!MessageBoxA` at `0x1800069ea`
- `USER32!MessageBoxA` at `0x1800069ea`
- `USER32!LoadStringA` at `0x1800069c8`
- `USER32!LoadStringA` at `0x1800069c8`
- `SHELL32!DragFinish` at `0x180006932`
- `SHELL32!DragFinish` at `0x180006932`
- `SHELL32!DragQueryFileA` at `0x180006885`
- `SHELL32!DragQueryFileA` at `0x1800068f0`
- `SHELL32!DragQueryFileA` at `0x180006885`
- `SHELL32!DragQueryFileA` at `0x1800068f0`
- `SHELL32!ShellExecuteExA` at `0x180006989`
- `SHELL32!ShellExecuteExA` at `0x180006989`
- `SHELL32!SHGetMalloc` at `0x180006865`
- `SHELL32!SHGetMalloc` at `0x180006865`
- `SHLWAPI!PathQuoteSpacesA` at `0x1800068fd`
- `SHLWAPI!PathQuoteSpacesA` at `0x1800068fd`

## pseudocode

```c
__int64 __fastcall CWSHExtension::Drop(const CHAR *this, struct IDataObject *a2, __int64 a3, struct _POINTL a4)
{
  struct IDataObjectVtbl *lpVtbl; // rax
  HDROP v6; // rbx
  __int64 result; // rax
  signed int FileA; // r15d
  size_t v9; // r14
  char *v10; // rax
  char *v11; // rdi
  signed int i; // esi
  HWND Focus; // rax
  void *v14; // rsp
  HWND v15; // rax
  CHAR Buffer[2016]; // [rsp+0h] [rbp-800h] BYREF
  IMalloc *ppMalloc; // [rsp+800h] [rbp+0h] BYREF
  __int128 v18; // [rsp+808h] [rbp+8h] BYREF
  unsigned __int64 v19; // [rsp+818h] [rbp+18h]
  __int64 v20; // [rsp+820h] [rbp+20h]
  HDROP hDrop[2]; // [rsp+828h] [rbp+28h] BYREF
  __int64 v22; // [rsp+838h] [rbp+38h]
  SHELLEXECUTEINFOA pExecInfo; // [rsp+840h] [rbp+40h] BYREF
  CHAR szFile[272]; // [rsp+8B0h] [rbp+B0h] BYREF

  v22 = 0;
  v20 = 1;
  v19 = 0xFFFFFFFF00000001uLL;
  v18 = 0;
  LOWORD(v18) = 15;
  lpVtbl = a2->lpVtbl;
  *(_OWORD *)hDrop = 0;
  if ( ((int (__fastcall *)(struct IDataObject *, __int128 *, HDROP *))lpVtbl->GetData)(a2, &v18, hDrop) < 0 )
    return 2147942487LL;
  v6 = hDrop[1];
  if ( !hDrop[1] )
    return 2147942487LL;
  ppMalloc = 0;
  if ( SHGetMalloc(&ppMalloc) < 0 )
    return 2147500037LL;
  FileA = DragQueryFileA(v6, 0xFFFFFFFF, 0, 0);
  v9 = (unsigned int)(261 * FileA);
  v10 = (char *)((__int64 (__fastcall *)(IMalloc *, _QWORD))ppMalloc->lpVtbl->Alloc)(ppMalloc, (unsigned int)v9);
  v11 = v10;
  if ( !v10 )
  {
    ((void (__fastcall *)(IMalloc *))ppMalloc->lpVtbl->Release)(ppMalloc);
    return 2147942414LL;
  }
  memset_0(v10, 0, v9);
  for ( i = 0; i < FileA; ++i )
  {
    DragQueryFileA(v6, i, szFile, 0x104u);
    PathQuoteSpacesA(szFile);
    StringCchCatA(v11, v9, szFile);
    strcat_s(v11, v9, " ");
  }
  DragFinish(v6);
  memset_0(&pExecInfo.hwnd, 0, 0x68u);
  pExecInfo.cbSize = 112;
  pExecInfo.fMask = 1024;
  Focus = GetFocus();
  pExecInfo.lpParameters = v11;
  pExecInfo.hwnd = Focus;
  pExecInfo.lpFile = this + 64;
  pExecInfo.lpVerb = "open";
  pExecInfo.lpDirectory = 0;
  pExecInfo.nShow = 5;
  ShellExecuteExA(&pExecInfo);
  ((void (__fastcall *)(IMalloc *))ppMalloc->lpVtbl->Release)(ppMalloc);
  if ( pExecInfo.hInstApp == (HINSTANCE)5 )
  {
    v14 = alloca(2048);
    Buffer[LoadStringA(Global::g_hResource, 0x11FAu, Buffer, 2048)] = 0;
    v15 = GetFocus();
    MessageBoxA(v15, Buffer, this + 64, 0x10u);
    return 2147942487LL;
  }
  result = 2147500037LL;
  if ( (__int64)pExecInfo.hInstApp > 32 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800067c0  push    rbp
0x1800067c2  push    rdi
0x1800067c3  push    r13
0x1800067c5  push    r14
0x1800067c7  push    r15
0x1800067c9  sub     rsp, 1F0h
0x1800067d0  lea     rbp, [rsp+20h]
0x1800067d5  mov     [rbp+1F0h+arg_10], rbx
0x1800067dc  mov     [rbp+1F0h+arg_18], rsi
0x1800067e3  mov     rax, cs:__security_cookie
0x1800067ea  xor     rax, rbp
0x1800067ed  mov     [rbp+1F0h+var_30], rax
0x1800067f4  xor     eax, eax
0x1800067f6  lea     r8, [rbp+1F0h+hDrop]
0x1800067fa  mov     [rbp+1F0h+var_1B8], rax
0x1800067fe  xorps   xmm1, xmm1
0x180006801  mov     eax, 1
0x180006806  mov     r9, rdx
0x180006809  movups  [rbp+1F0h+var_1D8], xmm1
0x18000680d  mov     dword ptr [rbp+1F0h+var_1D8+8], eax
0x180006810  mov     r13, rcx
0x180006813  mov     dword ptr [rbp+1F0h+var_1D8], eax
0x180006816  xorps   xmm0, xmm0
0x180006819  mov     eax, 0Fh
0x18000681e  mov     dword ptr [rbp+1F0h+var_1D8+4], 0FFFFFFFFh
0x180006825  movups  [rbp+1F0h+var_1E8], xmm1
0x180006829  mov     word ptr [rbp+1F0h+var_1E8], ax
0x18000682d  mov     rcx, r9
0x180006830  mov     rax, [rdx]
0x180006833  lea     rdx, [rbp+1F0h+var_1E8]
0x180006837  movups  xmmword ptr [rbp+1F0h+hDrop], xmm0
0x18000683b  mov     rax, [rax+18h]
0x18000683f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006844  test    eax, eax
0x180006846  js      loc_1800069F0
0x18000684c  mov     rbx, [rbp+1F0h+hDrop+8]
0x180006850  test    rbx, rbx
0x180006853  jz      loc_1800069F0
0x180006859  lea     rcx, [rbp+1F0h+ppMalloc]; ppMalloc
0x18000685d  mov     [rbp+1F0h+ppMalloc], 0
0x180006865  call    cs:__imp_SHGetMalloc
0x18000686b  test    eax, eax
0x18000686d  jns     short loc_180006879
0x18000686f  mov     eax, 80004005h
0x180006874  jmp     loc_1800069F5
0x180006879  xor     r9d, r9d; cch
0x18000687c  xor     r8d, r8d; lpszFile
0x18000687f  or      edx, 0FFFFFFFFh; iFile
0x180006882  mov     rcx, rbx; hDrop
0x180006885  call    cs:__imp_DragQueryFileA
0x18000688b  mov     rcx, [rbp+1F0h+ppMalloc]
0x18000688f  mov     r15d, eax
0x180006892  imul    r14d, eax, 105h
0x180006899  mov     rdx, [rcx]
0x18000689c  mov     rax, [rdx+18h]
0x1800068a0  mov     edx, r14d
0x1800068a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068a8  mov     rdi, rax
0x1800068ab  test    rax, rax
0x1800068ae  jnz     short loc_1800068CA
0x1800068b0  mov     rcx, [rbp+1F0h+ppMalloc]
0x1800068b4  mov     rax, [rcx]
0x1800068b7  mov     rax, [rax+10h]
0x1800068bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068c0  mov     eax, 8007000Eh
0x1800068c5  jmp     loc_1800069F5
0x1800068ca  mov     r8, r14; Size
0x1800068cd  xor     edx, edx; Val
0x1800068cf  mov     rcx, rdi; void *
0x1800068d2  call    memset_0
0x1800068d7  xor     esi, esi
0x1800068d9  test    r15d, r15d
0x1800068dc  jle     short loc_18000692F
0x1800068de  mov     r9d, 104h; cch
0x1800068e4  lea     r8, [rbp+1F0h+szFile]; lpszFile
0x1800068eb  mov     edx, esi; iFile
0x1800068ed  mov     rcx, rbx; hDrop
0x1800068f0  call    cs:__imp_DragQueryFileA
0x1800068f6  lea     rcx, [rbp+1F0h+szFile]; lpsz
0x1800068fd  call    cs:__imp_PathQuoteSpacesA
0x180006903  lea     r8, [rbp+1F0h+szFile]; char *
0x18000690a  mov     rdx, r14; unsigned __int64
0x18000690d  mov     rcx, rdi; char *
0x180006910  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180006915  lea     r8, asc_180010390; " "
0x18000691c  mov     rdx, r14; SizeInBytes
0x18000691f  mov     rcx, rdi; Destination
0x180006922  call    cs:__imp_strcat_s
0x180006928  inc     esi
0x18000692a  cmp     esi, r15d
0x18000692d  jl      short loc_1800068DE
0x18000692f  mov     rcx, rbx; hDrop
0x180006932  call    cs:__imp_DragFinish
0x180006938  xor     edx, edx; Val
0x18000693a  lea     rcx, [rbp+1F0h+pExecInfo.hwnd]; void *
0x18000693e  lea     r8d, [rdx+68h]; Size
0x180006942  call    memset_0
0x180006947  mov     [rbp+1F0h+pExecInfo.cbSize], 70h ; 'p'
0x18000694e  mov     [rbp+1F0h+pExecInfo.fMask], 400h
0x180006955  call    cs:__imp_GetFocus
0x18000695b  mov     [rbp+1F0h+pExecInfo.lpParameters], rdi
0x18000695f  lea     rcx, [rbp+1F0h+pExecInfo]; pExecInfo
0x180006963  mov     [rbp+1F0h+pExecInfo.hwnd], rax
0x180006967  lea     rdi, [r13+40h]
0x18000696b  lea     rax, aOpen; "open"
0x180006972  mov     [rbp+1F0h+pExecInfo.lpFile], rdi
0x180006976  mov     [rbp+1F0h+pExecInfo.lpVerb], rax
0x18000697a  mov     [rbp+1F0h+pExecInfo.lpDirectory], 0
0x180006982  mov     [rbp+1F0h+pExecInfo.nShow], 5
0x180006989  call    cs:__imp_ShellExecuteExA
0x18000698f  mov     rcx, [rbp+1F0h+ppMalloc]
0x180006993  mov     rax, [rcx]
0x180006996  mov     rax, [rax+10h]
0x18000699a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000699f  cmp     [rbp+1F0h+pExecInfo.hInstApp], 5
0x1800069a4  jnz     short loc_180006A22
0x1800069a6  mov     eax, [rsp+210h+var_210]
0x1800069a9  mov     r9d, 800h; cchBufferMax
0x1800069af  sub     rsp, r9
0x1800069b2  lea     rbx, [rsp+0A10h+Buffer]
0x1800069b7  mov     eax, [rbx]
0x1800069b9  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x1800069c0  mov     r8, rbx; lpBuffer
0x1800069c3  mov     edx, 11FAh; uID
0x1800069c8  call    cs:__imp_LoadStringA
0x1800069ce  movsxd  rcx, eax
0x1800069d1  mov     byte ptr [rcx+rbx], 0
0x1800069d5  call    cs:__imp_GetFocus
0x1800069db  mov     r9d, 10h; uType
0x1800069e1  mov     r8, rdi; lpCaption
0x1800069e4  mov     rcx, rax; hWnd
0x1800069e7  mov     rdx, rbx; lpText
0x1800069ea  call    cs:__imp_MessageBoxA
0x1800069f0  mov     eax, 80070057h
0x1800069f5  mov     rcx, [rbp+1F0h+var_30]
0x1800069fc  xor     rcx, rbp; StackCookie
0x1800069ff  call    __security_check_cookie
0x180006a04  mov     rbx, [rbp+1F0h+arg_10]
0x180006a0b  mov     rsi, [rbp+1F0h+arg_18]
0x180006a12  lea     rsp, [rbp+1D0h]
0x180006a19  pop     r15
0x180006a1b  pop     r14
0x180006a1d  pop     r13
0x180006a1f  pop     rdi
0x180006a20  pop     rbp
0x180006a21  retn
0x180006a22  xor     ecx, ecx
0x180006a24  mov     eax, 80004005h
0x180006a29  cmp     [rbp+1F0h+pExecInfo.hInstApp], 20h ; ' '
0x180006a2e  cmovg   eax, ecx
0x180006a31  jmp     short loc_1800069F5
```
