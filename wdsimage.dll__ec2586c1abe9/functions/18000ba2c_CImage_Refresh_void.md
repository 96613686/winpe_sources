# CImage::Refresh(void)

- ea: `0x18000ba2c`
- end: `0x18000bc4f`
- name: `?Refresh@CImage@@QEAAJXZ`
- size: `547`
- prototype: `__int64 __fastcall(CImage *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003eb0`
- `0x180003f40`
- `0x1800041a0`
- `0x180005a90`
- `0x18000ae64`

## callees

- `0x18000a01c`
- `0x18000a814`
- `0x18000b17c`
- `0x18000ba2c`
- `0x18000d5b0`
- `0x18000dc28`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x18000bb81`
- `KERNEL32!GetFileAttributesW` at `0x18000bb81`
- `KERNEL32!GetProcessHeap` at `0x18000bba8`
- `KERNEL32!GetProcessHeap` at `0x18000bba8`
- `KERNEL32!HeapFree` at `0x18000bbbc`
- `KERNEL32!HeapFree` at `0x18000bbbc`
- `WdsCommonLib!??1CTokenString@@QEAA@XZ` at `0x18000bc26`
- `WdsCommonLib!??1CTokenString@@QEAA@XZ` at `0x18000bc26`
- `WdsCommonLib!??0CTokenString@@QEAA@XZ` at `0x18000ba50`
- `WdsCommonLib!??0CTokenString@@QEAA@XZ` at `0x18000ba50`

## pseudocode

```c
__int64 __fastcall CImage::Refresh(CImage *this)
{
  __int64 ImageInterface; // rdi
  _QWORD *v3; // rsi
  __int64 v4; // rdx
  __int64 v5; // rcx
  _QWORD *v6; // r14
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  const WCHAR *v13; // rcx
  const WCHAR *v14; // rsi
  void *v15; // rbp
  HANDLE ProcessHeap; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  struct IDepImageResolved **v21; // [rsp+20h] [rbp-48h]
  _BYTE v22[32]; // [rsp+30h] [rbp-38h] BYREF
  int v23; // [rsp+70h] [rbp+8h] BYREF

  LODWORD(ImageInterface) = 0;
  v23 = 0;
  CTokenString::CTokenString((CTokenString *)v22);
  if ( !*((_DWORD *)this + 88) )
  {
    v3 = (_QWORD *)((char *)this + 376);
    v4 = *((_QWORD *)this + 47);
    if ( v4 )
    {
      v5 = v4 + 8 + *(int *)(*(_QWORD *)(v4 + 8) + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      *v3 = 0;
    }
    v6 = (_QWORD *)((char *)this + 384);
    v7 = *((_QWORD *)this + 48);
    if ( v7 )
    {
      v8 = v7 + 8 + *(int *)(*(_QWORD *)(v7 + 8) + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      *v6 = 0;
    }
    ImageInterface = (unsigned int)CImage::GetImageInterface(
                                     *((const unsigned __int16 **)this + 11),
                                     v7,
                                     (struct IDepImageSetContainer **)this + 47,
                                     (struct IDepImageSet **)this + 48,
                                     v21);
    if ( (int)ElValidateHr_5(ImageInterface, v9, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 616) >= 0 )
    {
      ImageInterface = (*(unsigned int (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v3 + 8LL))(*v3, (char *)this + 32);
      if ( (int)ElValidateHr_5(ImageInterface, v10, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 622) >= 0 )
      {
        LODWORD(ImageInterface) = (**(__int64 (__fastcall ***)(_QWORD, int *))*v6)(*v6, &v23);
        if ( (int)ElValidateHr_5((unsigned int)ImageInterface, v11, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 628) >= 0 )
        {
          *((_DWORD *)this + 32) = v23;
          LODWORD(ImageInterface) = CImage::ExtractBootImageIndex(this);
          if ( (int)ElValidateHr_5((unsigned int)ImageInterface, v12, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 636) >= 0 )
          {
            v13 = (const WCHAR *)*((_QWORD *)this + 14);
            if ( !v13 || GetFileAttributesW(v13) == -1 )
              v14 = (const WCHAR *)*((_QWORD *)this + 11);
            else
              v14 = (const WCHAR *)*((_QWORD *)this + 14);
            v15 = (void *)*((_QWORD *)this + 15);
            if ( v15 )
            {
              ProcessHeap = GetProcessHeap();
              if ( HeapFree(ProcessHeap, 0, v15) )
                *((_QWORD *)this + 15) = 0;
            }
            LODWORD(ImageInterface) = pWdsImgGetSecurity(v14, (unsigned __int16 **)this + 15);
            ElValidateHr_5((unsigned int)ImageInterface, v17, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 556);
            if ( (int)ElValidateHr_5((unsigned int)ImageInterface, v18, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 642) >= 0 )
            {
              LODWORD(ImageInterface) = CImage::LoadImageInfo(this, *((_DWORD *)this + 33));
              ElValidateHr_5((unsigned int)ImageInterface, v19, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 648);
            }
          }
        }
      }
    }
  }
  CTokenString::~CTokenString((CTokenString *)v22);
  return (unsigned int)ImageInterface;
}

```

## disassembly

```asm
0x18000ba2c  mov     rax, rsp
0x18000ba2f  mov     [rax+10h], rbx
0x18000ba33  mov     [rax+18h], rbp
0x18000ba37  mov     [rax+20h], rsi
0x18000ba3b  push    rdi
0x18000ba3c  push    r12
0x18000ba3e  push    r14
0x18000ba40  sub     rsp, 50h
0x18000ba44  mov     rbx, rcx
0x18000ba47  xor     edi, edi
0x18000ba49  and     [rax+8], edi
0x18000ba4c  lea     rcx, [rax-38h]
0x18000ba50  call    cs:__imp_??0CTokenString@@QEAA@XZ; CTokenString::CTokenString(void)
0x18000ba57  nop     dword ptr [rax+rax+00h]
0x18000ba5c  cmp     [rbx+160h], edi
0x18000ba62  jnz     loc_18000BC21
0x18000ba68  lea     rsi, [rbx+178h]
0x18000ba6f  mov     rdx, [rsi]
0x18000ba72  test    rdx, rdx
0x18000ba75  jz      short loc_18000BA95
0x18000ba77  mov     rax, [rdx+8]
0x18000ba7b  add     rdx, 8
0x18000ba7f  movsxd  rcx, dword ptr [rax+4]
0x18000ba83  add     rcx, rdx
0x18000ba86  mov     rax, [rcx]
0x18000ba89  mov     rax, [rax+10h]
0x18000ba8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba92  and     [rsi], rdi
0x18000ba95  lea     r14, [rbx+180h]
0x18000ba9c  mov     rdx, [r14]
0x18000ba9f  test    rdx, rdx
0x18000baa2  jz      short loc_18000BAC2
0x18000baa4  mov     rax, [rdx+8]
0x18000baa8  add     rdx, 8
0x18000baac  movsxd  rcx, dword ptr [rax+4]
0x18000bab0  add     rcx, rdx
0x18000bab3  mov     rax, [rcx]
0x18000bab6  mov     rax, [rax+10h]
0x18000baba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000babf  and     [r14], rdi
0x18000bac2  mov     rcx, [rbx+58h]; unsigned __int16 *
0x18000bac6  mov     r9, r14; struct IDepImageSet **
0x18000bac9  mov     r8, rsi; struct IDepImageSetContainer **
0x18000bacc  call    ?GetImageInterface@CImage@@SAJPEBGKPEAPEAVIDepImageSetContainer@@PEAPEAVIDepImageSet@@PEAPEAVIDepImageResolved@@@Z; CImage::GetImageInterface(ushort const *,ulong,IDepImageSetContainer * *,IDepImageSet * *,IDepImageResolved * *)
0x18000bad1  lea     r12, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000bad8  mov     r9d, 268h
0x18000bade  mov     r8, r12
0x18000bae1  mov     ecx, eax
0x18000bae3  mov     edi, eax
0x18000bae5  call    ElValidateHr_5
0x18000baea  test    eax, eax
0x18000baec  js      loc_18000BC21
0x18000baf2  mov     rcx, [rsi]
0x18000baf5  lea     rdx, [rbx+20h]
0x18000baf9  mov     rax, [rcx]
0x18000bafc  mov     rax, [rax+8]
0x18000bb00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb05  mov     r9d, 26Eh
0x18000bb0b  mov     r8, r12
0x18000bb0e  mov     ecx, eax
0x18000bb10  mov     edi, eax
0x18000bb12  call    ElValidateHr_5
0x18000bb17  test    eax, eax
0x18000bb19  js      loc_18000BC21
0x18000bb1f  mov     rcx, [r14]
0x18000bb22  lea     rdx, [rsp+68h+arg_0]
0x18000bb27  mov     rax, [rcx]
0x18000bb2a  mov     rax, [rax]
0x18000bb2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb32  mov     r9d, 274h
0x18000bb38  mov     r8, r12
0x18000bb3b  mov     ecx, eax
0x18000bb3d  mov     edi, eax
0x18000bb3f  call    ElValidateHr_5
0x18000bb44  test    eax, eax
0x18000bb46  js      loc_18000BC21
0x18000bb4c  mov     eax, [rsp+68h+arg_0]
0x18000bb50  mov     rcx, rbx; this
0x18000bb53  mov     [rbx+80h], eax
0x18000bb59  call    ?ExtractBootImageIndex@CImage@@AEAAJXZ; CImage::ExtractBootImageIndex(void)
0x18000bb5e  mov     r9d, 27Ch
0x18000bb64  mov     r8, r12
0x18000bb67  mov     ecx, eax
0x18000bb69  mov     edi, eax
0x18000bb6b  call    ElValidateHr_5
0x18000bb70  test    eax, eax
0x18000bb72  js      loc_18000BC21
0x18000bb78  mov     rcx, [rbx+70h]; lpFileName
0x18000bb7c  test    rcx, rcx
0x18000bb7f  jz      short loc_18000BB98
0x18000bb81  call    cs:__imp_GetFileAttributesW
0x18000bb88  nop     dword ptr [rax+rax+00h]
0x18000bb8d  cmp     eax, 0FFFFFFFFh
0x18000bb90  jz      short loc_18000BB98
0x18000bb92  mov     rsi, [rbx+70h]
0x18000bb96  jmp     short loc_18000BB9C
0x18000bb98  mov     rsi, [rbx+58h]
0x18000bb9c  lea     rdi, [rbx+78h]
0x18000bba0  mov     rbp, [rdi]
0x18000bba3  test    rbp, rbp
0x18000bba6  jz      short loc_18000BBD0
0x18000bba8  call    cs:__imp_GetProcessHeap
0x18000bbaf  nop     dword ptr [rax+rax+00h]
0x18000bbb4  mov     r8, rbp; lpMem
0x18000bbb7  xor     edx, edx; dwFlags
0x18000bbb9  mov     rcx, rax; hHeap
0x18000bbbc  call    cs:__imp_HeapFree
0x18000bbc3  nop     dword ptr [rax+rax+00h]
0x18000bbc8  test    eax, eax
0x18000bbca  jz      short loc_18000BBD0
0x18000bbcc  and     qword ptr [rdi], 0
0x18000bbd0  mov     rdx, rdi; unsigned __int16 **
0x18000bbd3  mov     rcx, rsi; lpFileName
0x18000bbd6  call    ?pWdsImgGetSecurity@@YAJPEAGPEAPEAG@Z; pWdsImgGetSecurity(ushort *,ushort * *)
0x18000bbdb  mov     r9d, 22Ch
0x18000bbe1  mov     r8, r12
0x18000bbe4  mov     ecx, eax
0x18000bbe6  mov     edi, eax
0x18000bbe8  call    ElValidateHr_5
0x18000bbed  mov     r9d, 282h
0x18000bbf3  mov     r8, r12
0x18000bbf6  mov     ecx, edi
0x18000bbf8  call    ElValidateHr_5
0x18000bbfd  test    eax, eax
0x18000bbff  js      short loc_18000BC21
0x18000bc01  mov     edx, [rbx+84h]; unsigned int
0x18000bc07  mov     rcx, rbx; this
0x18000bc0a  call    ?LoadImageInfo@CImage@@QEAAJK@Z; CImage::LoadImageInfo(ulong)
0x18000bc0f  mov     r9d, 288h
0x18000bc15  mov     r8, r12
0x18000bc18  mov     ecx, eax
0x18000bc1a  mov     edi, eax
0x18000bc1c  call    ElValidateHr_5
0x18000bc21  lea     rcx, [rsp+68h+var_38]
0x18000bc26  call    cs:__imp_??1CTokenString@@QEAA@XZ; CTokenString::~CTokenString(void)
0x18000bc2d  nop     dword ptr [rax+rax+00h]
0x18000bc32  lea     r11, [rsp+68h+var_18]
0x18000bc37  mov     eax, edi
0x18000bc39  mov     rbx, [r11+28h]
0x18000bc3d  mov     rbp, [r11+30h]
0x18000bc41  mov     rsi, [r11+38h]
0x18000bc45  mov     rsp, r11
0x18000bc48  pop     r14
0x18000bc4a  pop     r12
0x18000bc4c  pop     rdi
0x18000bc4d  retn
```
