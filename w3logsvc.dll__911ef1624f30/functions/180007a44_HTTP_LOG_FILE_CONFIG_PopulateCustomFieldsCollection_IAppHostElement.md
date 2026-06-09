# HTTP_LOG_FILE_CONFIG::PopulateCustomFieldsCollection(IAppHostElement *)

- ea: `0x180007a44`
- end: `0x180007c73`
- name: `?PopulateCustomFieldsCollection@HTTP_LOG_FILE_CONFIG@@AEAAJPEAUIAppHostElement@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(HTTP_LOG_FILE_CONFIG *this, struct IAppHostElement *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180007744`

## callees

- `0x180006f4c`
- `0x180007170`
- `0x180007a44`
- `0x18000e97a`
- `0x18000e9a0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bf1`
- `OLEAUT32!__imp_VariantInit` at `0x180007ac7`
- `OLEAUT32!__imp_VariantInit` at `0x180007ac7`
- `iisutil!?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z` at `0x180007bab`
- `iisutil!?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z` at `0x180007bab`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007c49`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007c49`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007abb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007abb`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_FILE_CONFIG::PopulateCustomFieldsCollection(
        HTTP_LOG_FILE_CONFIG *this,
        struct IAppHostElement *a2)
{
  int DWORDProperty; // ebx
  signed int LastError; // eax
  unsigned int v7; // [rsp+20h] [rbp-E0h] BYREF
  struct IAppHostElement *v8; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG v11; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v12[32]; // [rsp+70h] [rbp-90h] BYREF
  _WORD *v13; // [rsp+90h] [rbp-70h]
  int v14; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v15[256]; // [rsp+B0h] [rbp-50h] BYREF

  v9 = 0;
  v8 = 0;
  v7 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset_0(v15, 0, sizeof(v15));
  STRU::STRU((STRU *)v12, v15, 0x100u);
  VariantInit(&pvarg);
  pvarg.vt = 19;
  DWORDProperty = Config_GetDWORDProperty(a2, L"maxCustomFieldLength", (unsigned int *)this + 54);
  if ( DWORDProperty >= 0 )
  {
    DWORDProperty = ((__int64 (__fastcall *)(struct IAppHostElement *, __int64 *))a2->lpVtbl->get_Collection)(a2, &v9);
    if ( DWORDProperty >= 0 )
    {
      DWORDProperty = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v9 + 24LL))(v9, &v7);
      if ( DWORDProperty >= 0 )
      {
        for ( pvarg.lVal = 0; pvarg.lVal < v7; ++pvarg.lVal )
        {
          v11 = pvarg;
          DWORDProperty = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, struct IAppHostElement **))(*(_QWORD *)v9 + 32LL))(
                            v9,
                            &v11,
                            &v8);
          if ( DWORDProperty < 0 )
            break;
          DWORDProperty = Config_GetStringProperty(v8, L"logFieldName", (struct STRU *)v12);
          if ( DWORDProperty < 0 )
            break;
          if ( !MULTISZ::Append((HTTP_LOG_FILE_CONFIG *)((char *)this + 160), (struct STRU *)v12) )
          {
            LastError = GetLastError();
            DWORDProperty = LastError;
            if ( LastError > 0 )
              DWORDProperty = (unsigned __int16)LastError | 0x80070000;
            break;
          }
          ((void (__fastcall *)(struct IAppHostElement *))v8->lpVtbl->Release)(v8);
          v8 = 0;
          *v13 = 0;
          v14 = 0;
        }
      }
    }
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
  }
  if ( v8 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v8->lpVtbl->Release)(v8);
    v8 = 0;
  }
  STRU::~STRU((STRU *)v12);
  return (unsigned int)DWORDProperty;
}

```

## disassembly

```asm
0x180007a44  mov     [rsp-8+arg_10], rbx
0x180007a49  push    rbp
0x180007a4a  push    rsi
0x180007a4b  push    rdi
0x180007a4c  lea     rbp, [rsp-1C0h]
0x180007a54  sub     rsp, 2C0h
0x180007a5b  mov     rax, cs:__security_cookie
0x180007a62  xor     rax, rsp
0x180007a65  mov     [rbp+1D0h+var_20], rax
0x180007a6c  mov     rdi, rdx
0x180007a6f  mov     rsi, rcx
0x180007a72  mov     [rsp+2D0h+var_2A0], 0
0x180007a7b  mov     [rsp+2D0h+var_2A8], 0
0x180007a84  mov     [rsp+2D0h+var_2B0], 0
0x180007a8c  xorps   xmm0, xmm0
0x180007a8f  xor     eax, eax
0x180007a91  movups  xmmword ptr [rsp+2D0h+pvarg], xmm0
0x180007a96  mov     qword ptr [rsp+2D0h+pvarg+10h], rax
0x180007a9b  xor     edx, edx; Val
0x180007a9d  mov     r8d, 200h; Size
0x180007aa3  lea     rcx, [rbp+1D0h+var_220]; void *
0x180007aa7  call    memset_0
0x180007aac  mov     r8d, 100h
0x180007ab2  lea     rdx, [rbp+1D0h+var_220]
0x180007ab6  lea     rcx, [rsp+2D0h+var_260]
0x180007abb  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180007ac1  nop
0x180007ac2  lea     rcx, [rsp+2D0h+pvarg]; pvarg
0x180007ac7  call    cs:__imp_VariantInit
0x180007acd  mov     eax, 13h
0x180007ad2  mov     word ptr [rsp+2D0h+pvarg], ax
0x180007ad7  lea     r8, [rsi+0D8h]; unsigned int *
0x180007ade  lea     rdx, aMaxcustomfield; "maxCustomFieldLength"
0x180007ae5  mov     rcx, rdi; struct IAppHostElement *
0x180007ae8  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x180007aed  mov     ebx, eax
0x180007aef  test    eax, eax
0x180007af1  js      loc_180007C06
0x180007af7  mov     rax, [rdi]
0x180007afa  lea     rdx, [rsp+2D0h+var_2A0]
0x180007aff  mov     rcx, rdi
0x180007b02  mov     rax, [rax+20h]
0x180007b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b0b  mov     ebx, eax
0x180007b0d  test    eax, eax
0x180007b0f  js      loc_180007C06
0x180007b15  mov     rcx, [rsp+2D0h+var_2A0]
0x180007b1a  mov     rax, [rcx]
0x180007b1d  lea     rdx, [rsp+2D0h+var_2B0]
0x180007b22  mov     rax, [rax+18h]
0x180007b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b2b  mov     ebx, eax
0x180007b2d  test    eax, eax
0x180007b2f  js      loc_180007C06
0x180007b35  mov     dword ptr [rsp+2D0h+pvarg+8], 0
0x180007b3d  cmp     [rsp+2D0h+var_2B0], 0
0x180007b42  jbe     loc_180007C06
0x180007b48  movups  xmm0, xmmword ptr [rsp+2D0h+pvarg]
0x180007b4d  movaps  [rsp+2D0h+var_280], xmm0
0x180007b52  movsd   xmm1, qword ptr [rsp+2D0h+pvarg+10h]
0x180007b58  movsd   [rsp+2D0h+var_270], xmm1
0x180007b5e  mov     rcx, [rsp+2D0h+var_2A0]
0x180007b63  mov     rax, [rcx]
0x180007b66  lea     r8, [rsp+2D0h+var_2A8]
0x180007b6b  lea     rdx, [rsp+2D0h+var_280]
0x180007b70  mov     rax, [rax+20h]
0x180007b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b79  mov     ebx, eax
0x180007b7b  test    eax, eax
0x180007b7d  js      loc_180007C06
0x180007b83  lea     r8, [rsp+2D0h+var_260]; struct STRU *
0x180007b88  lea     rdx, aLogfieldname; "logFieldName"
0x180007b8f  mov     rcx, [rsp+2D0h+var_2A8]; struct IAppHostElement *
0x180007b94  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAVSTRU@@@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,STRU *)
0x180007b99  mov     ebx, eax
0x180007b9b  test    eax, eax
0x180007b9d  js      short loc_180007C06
0x180007b9f  lea     rcx, [rsi+0A0h]
0x180007ba6  lea     rdx, [rsp+2D0h+var_260]
0x180007bab  call    cs:__imp_?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z; MULTISZ::Append(STRU &)
0x180007bb1  test    eax, eax
0x180007bb3  jz      short loc_180007BF1
0x180007bb5  mov     rcx, [rsp+2D0h+var_2A8]
0x180007bba  mov     rax, [rcx]
0x180007bbd  mov     rax, [rax+10h]
0x180007bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bc6  mov     [rsp+2D0h+var_2A8], 0
0x180007bcf  xor     ecx, ecx
0x180007bd1  mov     rax, [rbp+1D0h+var_240]
0x180007bd5  mov     [rax], cx
0x180007bd8  mov     [rbp+1D0h+var_230], ecx
0x180007bdb  mov     eax, dword ptr [rsp+2D0h+pvarg+8]
0x180007bdf  inc     eax
0x180007be1  mov     dword ptr [rsp+2D0h+pvarg+8], eax
0x180007be5  cmp     eax, [rsp+2D0h+var_2B0]
0x180007be9  jb      loc_180007B48
0x180007bef  jmp     short loc_180007C06
0x180007bf1  call    cs:__imp_GetLastError
0x180007bf7  mov     ebx, eax
0x180007bf9  test    eax, eax
0x180007bfb  jle     short loc_180007C06
0x180007bfd  movzx   ebx, ax
0x180007c00  or      ebx, 80070000h
0x180007c06  mov     rcx, [rsp+2D0h+var_2A0]
0x180007c0b  test    rcx, rcx
0x180007c0e  jz      short loc_180007C25
0x180007c10  mov     rax, [rcx]
0x180007c13  mov     rax, [rax+10h]
0x180007c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c1c  mov     [rsp+2D0h+var_2A0], 0
0x180007c25  mov     rcx, [rsp+2D0h+var_2A8]
0x180007c2a  test    rcx, rcx
0x180007c2d  jz      short loc_180007C44
0x180007c2f  mov     rax, [rcx]
0x180007c32  mov     rax, [rax+10h]
0x180007c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c3b  mov     [rsp+2D0h+var_2A8], 0
0x180007c44  lea     rcx, [rsp+2D0h+var_260]
0x180007c49  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007c4f  mov     eax, ebx
0x180007c51  mov     rcx, [rbp+1D0h+var_20]
0x180007c58  xor     rcx, rsp; StackCookie
0x180007c5b  call    __security_check_cookie
0x180007c60  mov     rbx, [rsp+2D0h+arg_10]
0x180007c68  add     rsp, 2C0h
0x180007c6f  pop     rdi
0x180007c70  pop     rsi
0x180007c71  pop     rbp
0x180007c72  retn
```
