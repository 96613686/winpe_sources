# CSpinner::_Initialize(uint,DirectUI::Element *,int)

- ea: `0x180007778`
- end: `0x1800078e4`
- name: `?_Initialize@CSpinner@@AEAAJIPEAVElement@DirectUI@@H@Z`
- size: `364`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong, unsigned int, struct DirectUI::Element *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180011390`

## callees

- `0x1800075c0`
- `0x180007650`
- `0x180007778`
- `0x1800078ec`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800077b8`
- `KERNEL32!LoadLibraryExW` at `0x1800077b8`
- `KERNEL32!FreeLibrary` at `0x1800078ba`
- `KERNEL32!FreeLibrary` at `0x1800078ba`
- `GDI32!DeleteObject` at `0x180007854`
- `GDI32!DeleteObject` at `0x1800078a3`
- `GDI32!DeleteObject` at `0x180007854`
- `GDI32!DeleteObject` at `0x1800078a3`
- `GDI32!GetObjectW` at `0x180007817`
- `GDI32!GetObjectW` at `0x180007817`
- `USER32!LoadImageW` at `0x1800077ee`
- `USER32!LoadImageW` at `0x180007875`
- `USER32!LoadImageW` at `0x1800077ee`
- `USER32!LoadImageW` at `0x180007875`

## string_xrefs

- `0x1800077ad`: `imageres.dll`

## pseudocode

```c
__int64 __fastcall CSpinner::_Initialize(LONG_PTR dwNewLong, int a2, struct DirectUI::Element *a3, int a4)
{
  HMODULE Library; // rax
  HINSTANCE v7; // rsi
  signed int v8; // ebx
  HANDLE ImageW; // rax
  void *v10; // r15
  int cy; // r14d
  int v12; // ebx
  HBITMAP v13; // rax
  CSpinner *v14; // rcx
  HBITMAP v15; // r14
  struct DirectUI::Value **Frames; // rax
  struct DirectUI::Value **v17; // rbx
  _OWORD pv[2]; // [rsp+30h] [rbp-20h] BYREF
  int v20; // [rsp+88h] [rbp+38h] BYREF
  int v21; // [rsp+98h] [rbp+48h] BYREF

  v21 = a4;
  v20 = a2;
  *(_DWORD *)dwNewLong = 16;
  GetLogicalToPhysicalDPI((int *)dwNewLong, 0);
  *(_QWORD *)(dwNewLong + 24) = a3;
  Library = LoadLibraryExW(L"imageres.dll", 0, 2u);
  v7 = Library;
  if ( Library )
  {
    ImageW = LoadImageW(Library, (LPCWSTR)0x1389, 0, 0, 0, 0x2000u);
    v10 = ImageW;
    if ( !ImageW )
      goto LABEL_8;
    memset(pv, 0, sizeof(pv));
    GetObjectW(ImageW, 32, pv);
    v20 = DWORD2(pv[0]);
    v21 = DWORD1(pv[0]);
    GetLogicalToPhysicalDPI(&v21, &v20);
    cy = v20;
    v12 = v20 <= 0 ? v21 : v20 * (v21 / v20);
    DeleteObject(v10);
    v13 = (HBITMAP)LoadImageW(v7, (LPCWSTR)0x1389, 0, v12, cy, 0x2000u);
    v15 = v13;
    if ( v13 )
    {
      Frames = CSpinner::s_ExtractFrames(v14, v13, *(_DWORD *)dwNewLong, (int *)(dwNewLong + 16));
      *(_QWORD *)(dwNewLong + 8) = Frames;
      v17 = Frames;
      DeleteObject(v15);
      v8 = v17 != 0 ? 0 : 0x80004005;
    }
    else
    {
LABEL_8:
      v8 = -2147467259;
    }
    FreeLibrary(v7);
    if ( v8 >= 0 )
      return (unsigned int)CSpinner::_CreateWindow(dwNewLong);
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007778  mov     [rsp-28h+arg_0], rbx
0x18000777d  mov     [rsp-28h+arg_18], r9d
0x180007782  mov     [rsp-28h+arg_8], edx
0x180007786  push    rbp
0x180007787  push    rsi
0x180007788  push    rdi
0x180007789  push    r14
0x18000778b  push    r15
0x18000778d  mov     rbp, rsp
0x180007790  sub     rsp, 50h
0x180007794  xor     edx, edx; int *
0x180007796  mov     dword ptr [rcx], 10h
0x18000779c  mov     rbx, r8
0x18000779f  mov     rdi, rcx
0x1800077a2  call    ?GetLogicalToPhysicalDPI@@YAXPEAH0@Z; GetLogicalToPhysicalDPI(int *,int *)
0x1800077a7  xor     edx, edx; hFile
0x1800077a9  mov     [rdi+18h], rbx
0x1800077ad  lea     rcx, aImageresDll; "imageres.dll"
0x1800077b4  lea     r8d, [rdx+2]; dwFlags
0x1800077b8  call    cs:__imp_LoadLibraryExW
0x1800077be  mov     rsi, rax
0x1800077c1  test    rax, rax
0x1800077c4  jnz     short loc_1800077D0
0x1800077c6  mov     ebx, 80004005h
0x1800077cb  jmp     loc_1800078CE
0x1800077d0  mov     [rsp+50h+fuLoad], 2000h; fuLoad
0x1800077d8  xor     r9d, r9d; cx
0x1800077db  xor     r8d, r8d; type
0x1800077de  mov     [rsp+50h+cy], 0; cy
0x1800077e6  mov     edx, 1389h; name
0x1800077eb  mov     rcx, rsi; hInst
0x1800077ee  call    cs:__imp_LoadImageW
0x1800077f4  mov     r15, rax
0x1800077f7  test    rax, rax
0x1800077fa  jz      loc_180007883
0x180007800  xorps   xmm0, xmm0
0x180007803  lea     r8, [rbp+pv]; pv
0x180007807  mov     edx, 20h ; ' '; c
0x18000780c  mov     rcx, rax; h
0x18000780f  movups  [rbp+pv], xmm0
0x180007813  movups  [rbp+var_10], xmm0
0x180007817  call    cs:__imp_GetObjectW
0x18000781d  mov     eax, dword ptr [rbp+pv+4]
0x180007820  lea     rdx, [rbp+arg_8]; int *
0x180007824  mov     [rbp+arg_18], eax
0x180007827  lea     rcx, [rbp+arg_18]; int *
0x18000782b  mov     eax, dword ptr [rbp+pv+8]
0x18000782e  mov     [rbp+arg_8], eax
0x180007831  call    ?GetLogicalToPhysicalDPI@@YAXPEAH0@Z; GetLogicalToPhysicalDPI(int *,int *)
0x180007836  mov     r14d, [rbp+arg_8]
0x18000783a  test    r14d, r14d
0x18000783d  jle     short loc_18000784E
0x18000783f  mov     eax, [rbp+arg_18]
0x180007842  cdq
0x180007843  idiv    r14d
0x180007846  mov     ebx, eax
0x180007848  imul    ebx, r14d
0x18000784c  jmp     short loc_180007851
0x18000784e  mov     ebx, [rbp+arg_18]
0x180007851  mov     rcx, r15; ho
0x180007854  call    cs:__imp_DeleteObject
0x18000785a  mov     r9d, ebx; cx
0x18000785d  mov     [rsp+50h+fuLoad], 2000h; fuLoad
0x180007865  xor     r8d, r8d; type
0x180007868  mov     [rsp+50h+cy], r14d; cy
0x18000786d  mov     edx, 1389h; name
0x180007872  mov     rcx, rsi; hInst
0x180007875  call    cs:__imp_LoadImageW
0x18000787b  mov     r14, rax
0x18000787e  test    rax, rax
0x180007881  jnz     short loc_18000788A
0x180007883  mov     ebx, 80004005h
0x180007888  jmp     short loc_1800078B7
0x18000788a  mov     r8d, [rdi]; int
0x18000788d  lea     r9, [rdi+10h]; int *
0x180007891  mov     rdx, r14; HBITMAP
0x180007894  call    ?s_ExtractFrames@CSpinner@@AEAAPEAPEAVValue@DirectUI@@PEAUHBITMAP__@@HPEAH@Z; CSpinner::s_ExtractFrames(HBITMAP__ *,int,int *)
0x180007899  mov     rcx, r14; ho
0x18000789c  mov     [rdi+8], rax
0x1800078a0  mov     rbx, rax
0x1800078a3  call    cs:__imp_DeleteObject
0x1800078a9  neg     rbx
0x1800078ac  mov     ebx, 80004005h
0x1800078b1  sbb     eax, eax
0x1800078b3  not     eax
0x1800078b5  and     ebx, eax
0x1800078b7  mov     rcx, rsi; hLibModule
0x1800078ba  call    cs:__imp_FreeLibrary
0x1800078c0  test    ebx, ebx
0x1800078c2  js      short loc_1800078CE
0x1800078c4  mov     rcx, rdi; dwNewLong
0x1800078c7  call    ?_CreateWindow@CSpinner@@AEAAJXZ; CSpinner::_CreateWindow(void)
0x1800078cc  mov     ebx, eax
0x1800078ce  mov     eax, ebx
0x1800078d0  mov     rbx, [rsp+50h+arg_0]
0x1800078d8  add     rsp, 50h
0x1800078dc  pop     r15
0x1800078de  pop     r14
0x1800078e0  pop     rdi
0x1800078e1  pop     rsi
0x1800078e2  pop     rbp
0x1800078e3  retn
```
