# CBitmapSource::Create(void *,ulong,CBitmapSource * *)

- ea: `0x18009f90c`
- end: `0x18009f9a7`
- name: `?Create@CBitmapSource@@SAJPEAXKPEAPEAV1@@Z`
- size: `155`
- prototype: `__int64 __fastcall(void *, unsigned int, struct CBitmapSource **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009f868`

## callees

- `0x1800814a4`
- `0x180081a68`
- `0x18009f90c`
- `0x18009f9b0`

## import_xrefs

- `dwmcore!__imp_CreateCompressedSourceBitmap` at `0x18009f94d`
- `dwmcore!__imp_CreateCompressedSourceBitmap` at `0x18009f94d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CBitmapSource::Create(void *a1, unsigned int a2, struct CBitmapSource **a3)
{
  int CompressedSourceBitmap; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct IWICBitmap *v9; // [rsp+58h] [rbp+20h] BYREF

  v9 = 0;
  CompressedSourceBitmap = CreateCompressedSourceBitmap(
                             *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 30),
                             a1,
                             a2);
  v5 = CompressedSourceBitmap;
  if ( CompressedSourceBitmap >= 0 )
  {
    CompressedSourceBitmap = CBitmapSource::CreateFromWicBitmap(v9, a3);
    v5 = CompressedSourceBitmap;
    if ( CompressedSourceBitmap >= 0 )
    {
      v5 = 0;
      goto LABEL_7;
    }
    v6 = 85;
  }
  else
  {
    v6 = 84;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"clientcore\\windows\\dwm\\udwm\\bitmapsource.cpp",
    (const char *)(unsigned int)CompressedSourceBitmap,
    DOUBLE_96_0);
LABEL_7:
  wil::com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>(&v9);
  return v5;
}

```

## disassembly

```asm
0x18009f90c  mov     r11, rsp
0x18009f90f  mov     [r11+8], rbx
0x18009f913  push    rdi
0x18009f914  sub     rsp, 30h
0x18009f918  mov     rdi, r8
0x18009f91b  mov     qword ptr [r11+20h], 0
0x18009f923  lea     rax, [r11+20h]
0x18009f927  mov     [r11-10h], rax
0x18009f92b  movsd   xmm3, cs:__real@4058000000000000
0x18009f933  movsd   qword ptr [rsp+38h+var_18], xmm3; int
0x18009f939  mov     r8d, edx
0x18009f93c  mov     rdx, rcx
0x18009f93f  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18009f946  mov     rcx, [rcx+0F0h]
0x18009f94d  call    cs:__imp_CreateCompressedSourceBitmap
0x18009f953  mov     ebx, eax
0x18009f955  test    eax, eax
0x18009f957  jns     short loc_18009F960
0x18009f959  mov     edx, 54h ; 'T'
0x18009f95e  jmp     short loc_18009F978
0x18009f960  mov     rdx, rdi; struct CBitmapSource **
0x18009f963  mov     rcx, [rsp+38h+arg_18]; struct IWICBitmap *
0x18009f968  call    ?CreateFromWicBitmap@CBitmapSource@@CAJPEAUIWICBitmap@@PEAPEAV1@@Z; CBitmapSource::CreateFromWicBitmap(IWICBitmap *,CBitmapSource * *)
0x18009f96d  mov     ebx, eax
0x18009f96f  test    eax, eax
0x18009f971  jns     short loc_18009F98E
0x18009f973  mov     edx, 55h ; 'U'; void *
0x18009f978  lea     r8, aClientcoreWind_40; "clientcore\\windows\\dwm\\udwm\\bitmaps"...
0x18009f97f  mov     r9d, eax; char *
0x18009f982  mov     rcx, [rsp+38h]; this
0x18009f987  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f98c  jmp     short loc_18009F990
0x18009f98e  xor     ebx, ebx
0x18009f990  lea     rcx, [rsp+38h+arg_18]
0x18009f995  call    ??1?$com_ptr_t@UICompositionVisualSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>(void)
0x18009f99a  mov     eax, ebx
0x18009f99c  mov     rbx, [rsp+38h+arg_0]
0x18009f9a1  add     rsp, 30h
0x18009f9a5  pop     rdi
0x18009f9a6  retn
```
