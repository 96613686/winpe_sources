# CPicturePasswordNativeHWNDHost::Create(HWND__ *,int,int,int,int,int,int,uint,CPicturePasswordNativeHWNDHost * *)

- ea: `0x18000e204`
- end: `0x18000e310`
- name: `?Create@CPicturePasswordNativeHWNDHost@@SAJPEAUHWND__@@HHHHHHIPEAPEAV1@@Z`
- size: `268`
- prototype: `__int64 __fastcall(HWND, unsigned __int64, __int64, __int64, int, int, int, unsigned int, struct CPicturePasswordNativeHWNDHost **Src)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180010fd0`

## callees

- `0x180005a10`
- `0x180006cfc`
- `0x18000e204`
- `0x18000e9cc`
- `0x180018aec`
- `0x18001f010`

## import_xrefs

- `DUI70!?Initialize@NativeHWNDHost@DirectUI@@QEAAJPEBGPEAUHWND__@@PEAUHICON__@@HHHHHHI@Z` at `0x18000e2c1`
- `DUI70!?Initialize@NativeHWNDHost@DirectUI@@QEAAJPEBGPEAUHWND__@@PEAUHICON__@@HHHHHHI@Z` at `0x18000e2c1`
- `DUI70!??0NativeHWNDHost@DirectUI@@QEAA@XZ` at `0x18000e23e`
- `DUI70!??0NativeHWNDHost@DirectUI@@QEAA@XZ` at `0x18000e23e`

## pseudocode

```c
__int64 __fastcall CPicturePasswordNativeHWNDHost::Create(
        HWND a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        unsigned int a8,
        struct CPicturePasswordNativeHWNDHost **Src)
{
  struct CPicturePasswordNativeHWNDHost **v9; // rsi
  DirectUI::NativeHWNDHost *v11; // rax
  DirectUI::NativeHWNDHost *v12; // rbx
  __int64 v13; // r8
  void *v14; // r9
  int v15; // edi
  void *v16; // rdx
  int v18; // [rsp+20h] [rbp-48h]

  v9 = Src;
  *Src = 0;
  v11 = (DirectUI::NativeHWNDHost *)DirectUI::HAllocAndZero((DirectUI *)0x30, a2);
  v12 = v11;
  if ( v11 )
  {
    DirectUI::NativeHWNDHost::NativeHWNDHost(v11);
    Src = 0;
    *(_QWORD *)v12 = &CPicturePasswordNativeHWNDHost::`vftable';
    TResourceStringAllocCopyEx<unsigned short *>(&_ImageBase, 17546, v13, v14, v18, (void **)&Src);
    v15 = DirectUI::NativeHWNDHost::Initialize(
            v12,
            (const unsigned __int16 *)Src,
            a1,
            0,
            0,
            0,
            0,
            0,
            0,
            -2117140480,
            0x10u);
    if ( v15 < 0 )
    {
      (**(void (__fastcall ***)(DirectUI::NativeHWNDHost *, _QWORD))v12)(v12, 0);
      DirectUI::HFree(v12, v16);
    }
    else
    {
      *v9 = v12;
    }
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>((void **)&Src);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000e204  mov     [rsp+arg_0], rbx
0x18000e209  mov     [rsp+arg_8], rsi
0x18000e20e  push    rdi
0x18000e20f  sub     rsp, 60h
0x18000e213  mov     rsi, [rsp+68h+arg_40]
0x18000e21b  mov     rdi, rcx
0x18000e21e  mov     ecx, 30h ; '0'; this
0x18000e223  mov     qword ptr [rsi], 0
0x18000e22a  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000e22f  mov     rbx, rax
0x18000e232  test    rax, rax
0x18000e235  jz      loc_18000E2F9
0x18000e23b  mov     rcx, rax
0x18000e23e  call    cs:__imp_??0NativeHWNDHost@DirectUI@@QEAA@XZ; DirectUI::NativeHWNDHost::NativeHWNDHost(void)
0x18000e244  lea     rax, ??_7CPicturePasswordNativeHWNDHost@@6B@; const CPicturePasswordNativeHWNDHost::`vftable'
0x18000e24b  mov     [rsp+68h+arg_40], 0
0x18000e257  mov     [rbx], rax
0x18000e25a  lea     rcx, __ImageBase; int
0x18000e261  lea     rax, [rsp+68h+arg_40]
0x18000e269  mov     edx, 448Ah; int
0x18000e26e  mov     [rsp+68h+Src], rax; Src
0x18000e273  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18000e278  mov     rdx, [rsp+68h+arg_40]
0x18000e280  xor     r9d, r9d
0x18000e283  mov     [rsp+68h+var_18], 10h
0x18000e28b  mov     r8, rdi
0x18000e28e  mov     [rsp+68h+var_20], 81CF0000h
0x18000e296  mov     rcx, rbx
0x18000e299  mov     [rsp+68h+var_28], 0
0x18000e2a1  mov     [rsp+68h+var_30], 0
0x18000e2a9  mov     [rsp+68h+var_38], 0
0x18000e2b1  mov     dword ptr [rsp+68h+Src], 0
0x18000e2b9  mov     [rsp+68h+var_48], 0
0x18000e2c1  call    cs:__imp_?Initialize@NativeHWNDHost@DirectUI@@QEAAJPEBGPEAUHWND__@@PEAUHICON__@@HHHHHHI@Z; DirectUI::NativeHWNDHost::Initialize(ushort const *,HWND__ *,HICON__ *,int,int,int,int,int,int,uint)
0x18000e2c7  mov     edi, eax
0x18000e2c9  test    eax, eax
0x18000e2cb  js      short loc_18000E2D2
0x18000e2cd  mov     [rsi], rbx
0x18000e2d0  jmp     short loc_18000E2EA
0x18000e2d2  mov     rax, [rbx]
0x18000e2d5  xor     edx, edx
0x18000e2d7  mov     rcx, rbx
0x18000e2da  mov     rax, [rax]
0x18000e2dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2e2  mov     rcx, rbx; this
0x18000e2e5  call    ?HFree@DirectUI@@YAXPEAX@Z; DirectUI::HFree(void *)
0x18000e2ea  lea     rcx, [rsp+68h+arg_40]
0x18000e2f2  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18000e2f7  jmp     short loc_18000E2FE
0x18000e2f9  mov     edi, 8007000Eh
0x18000e2fe  mov     rbx, [rsp+68h+arg_0]
0x18000e303  mov     eax, edi
0x18000e305  mov     rsi, [rsp+68h+arg_8]
0x18000e30a  add     rsp, 60h
0x18000e30e  pop     rdi
0x18000e30f  retn
```
