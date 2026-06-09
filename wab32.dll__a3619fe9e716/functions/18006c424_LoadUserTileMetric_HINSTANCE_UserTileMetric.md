# LoadUserTileMetric(HINSTANCE__ *,UserTileMetric *)

- ea: `0x18006c424`
- end: `0x18006c4fe`
- name: `?LoadUserTileMetric@@YAJPEAUHINSTANCE__@@PEAUUserTileMetric@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(HINSTANCE, struct UserTileMetric *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18006cda0`
- `0x18006d95c`

## callees

- `0x180002818`
- `0x18006bbd0`
- `0x18006c424`

## import_xrefs

- `SHLWAPI!__imp_SHCreateMemStream` at `0x18006c493`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x18006c493`
- `KERNEL32!FindResourceW` at `0x18006c44f`
- `KERNEL32!FindResourceW` at `0x18006c44f`
- `KERNEL32!LoadResource` at `0x18006c463`
- `KERNEL32!LoadResource` at `0x18006c463`
- `KERNEL32!LockResource` at `0x18006c474`
- `KERNEL32!LockResource` at `0x18006c474`
- `KERNEL32!SizeofResource` at `0x18006c488`
- `KERNEL32!SizeofResource` at `0x18006c488`
- `KERNEL32!FreeResource` at `0x18006c4d5`
- `KERNEL32!FreeResource` at `0x18006c4d5`
- `gdiplus!GdipAlloc` at `0x18006c4ab`
- `gdiplus!GdipAlloc` at `0x18006c4ab`

## pseudocode

```c
__int64 __fastcall LoadUserTileMetric(IStream *a1, LPCWSTR *a2)
{
  HMODULE v2; // rsi
  HRSRC ResourceW; // rax
  HRSRC v5; // rbp
  HGLOBAL Resource; // rax
  void *v7; // rdi
  const BYTE *v8; // r14
  UINT v9; // eax
  struct IStream *v10; // rsi
  Gdiplus::Bitmap *v11; // rax
  IStream *v13; // [rsp+40h] [rbp+8h] BYREF

  v13 = a1;
  v2 = hinstMapiX;
  ResourceW = FindResourceW(hinstMapiX, (LPCWSTR)*(unsigned __int16 *)a2, a2[1]);
  v5 = ResourceW;
  if ( ResourceW )
  {
    Resource = LoadResource(v2, ResourceW);
    v7 = Resource;
    if ( Resource )
    {
      v8 = (const BYTE *)LockResource(Resource);
      if ( v8 )
      {
        v9 = SizeofResource(v2, v5);
        v13 = SHCreateMemStream(v8, v9);
        v10 = v13;
        if ( v13 )
        {
          v11 = (Gdiplus::Bitmap *)GdipAlloc(24);
          if ( v11 )
            v11 = Gdiplus::Bitmap::Bitmap(v11, v10, 0);
          a2[4] = (LPCWSTR)v11;
          OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v13);
        }
      }
      FreeResource(v7);
    }
  }
  return a2[4] == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x18006c424  mov     [rsp+arg_8], rbx
0x18006c429  mov     [rsp+arg_10], rbp
0x18006c42e  mov     [rsp+arg_0], rcx
0x18006c433  push    rsi
0x18006c434  push    rdi
0x18006c435  push    r14
0x18006c437  sub     rsp, 20h
0x18006c43b  mov     rsi, cs:hinstMapiX
0x18006c442  mov     rbx, rdx
0x18006c445  movzx   edx, word ptr [rdx]; lpName
0x18006c448  mov     rcx, rsi; hModule
0x18006c44b  mov     r8, [rbx+8]; lpType
0x18006c44f  call    cs:__imp_FindResourceW
0x18006c455  mov     rbp, rax
0x18006c458  test    rax, rax
0x18006c45b  jz      short loc_18006C4DB
0x18006c45d  mov     rdx, rax; hResInfo
0x18006c460  mov     rcx, rsi; hModule
0x18006c463  call    cs:__imp_LoadResource
0x18006c469  mov     rdi, rax
0x18006c46c  test    rax, rax
0x18006c46f  jz      short loc_18006C4DB
0x18006c471  mov     rcx, rax; hResData
0x18006c474  call    cs:__imp_LockResource
0x18006c47a  mov     r14, rax
0x18006c47d  test    rax, rax
0x18006c480  jz      short loc_18006C4D2
0x18006c482  mov     rdx, rbp; hResInfo
0x18006c485  mov     rcx, rsi; hModule
0x18006c488  call    cs:__imp_SizeofResource
0x18006c48e  mov     edx, eax; cbInit
0x18006c490  mov     rcx, r14; pInit
0x18006c493  call    cs:__imp_SHCreateMemStream
0x18006c499  mov     [rsp+38h+arg_0], rax
0x18006c49e  mov     rsi, rax
0x18006c4a1  test    rax, rax
0x18006c4a4  jz      short loc_18006C4D2
0x18006c4a6  mov     ecx, 18h
0x18006c4ab  call    cs:__imp_GdipAlloc
0x18006c4b1  test    rax, rax
0x18006c4b4  jz      short loc_18006C4C4
0x18006c4b6  xor     r8d, r8d; int
0x18006c4b9  mov     rdx, rsi; struct IStream *
0x18006c4bc  mov     rcx, rax; this
0x18006c4bf  call    ??0Bitmap@Gdiplus@@QEAA@PEAUIStream@@H@Z; Gdiplus::Bitmap::Bitmap(IStream *,int)
0x18006c4c4  lea     rcx, [rsp+38h+arg_0]
0x18006c4c9  mov     [rbx+20h], rax
0x18006c4cd  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18006c4d2  mov     rcx, rdi; hResData
0x18006c4d5  call    cs:__imp_FreeResource
0x18006c4db  mov     rax, [rbx+20h]
0x18006c4df  mov     rbx, [rsp+38h+arg_8]
0x18006c4e4  neg     rax
0x18006c4e7  mov     rbp, [rsp+38h+arg_10]
0x18006c4ec  sbb     eax, eax
0x18006c4ee  not     eax
0x18006c4f0  and     eax, 80004005h
0x18006c4f5  add     rsp, 20h
0x18006c4f9  pop     r14
0x18006c4fb  pop     rdi
0x18006c4fc  pop     rsi
0x18006c4fd  retn
```
