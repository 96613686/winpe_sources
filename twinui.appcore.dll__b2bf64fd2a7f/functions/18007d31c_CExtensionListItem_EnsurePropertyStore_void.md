# CExtensionListItem::_EnsurePropertyStore(void)

- ea: `0x18007d31c`
- end: `0x18007d588`
- name: `?_EnsurePropertyStore@CExtensionListItem@@AEAAJXZ`
- size: `620`
- prototype: `__int64 __fastcall(CExtensionListItem *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18007a120`

## callees

- `0x180022fb4`
- `0x18004b430`
- `0x180075240`
- `0x18007d31c`
- `0x18007d97c`
- `0x18007dd20`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007d515`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007d515`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x18007d4ea`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x18007d4ea`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18007d380`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18007d380`

## pseudocode

```c
__int64 __fastcall CExtensionListItem::_EnsurePropertyStore(CExtensionListItem *this)
{
  char *v2; // r15
  HRESULT MFURank; // ebx
  bool v4; // zf
  unsigned __int64 v5; // rdi
  void *v6; // rdi
  __int64 (__fastcall *v7)(void *, GUID *, char *); // rbx
  PROPVARIANT ppropvar[2]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v10; // [rsp+30h] [rbp-10h]
  void *ppv; // [rsp+70h] [rbp+30h] BYREF
  PCWSTR psz; // [rsp+78h] [rbp+38h] BYREF

  if ( *((_QWORD *)this + 4) )
  {
    v2 = (char *)this + 48;
    if ( !*((_QWORD *)this + 6) || (MFURank = 0, *((_BYTE *)this + 584)) )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(&ppv);
      Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&ppv);
      MFURank = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
      if ( MFURank >= 0 )
      {
        v4 = (*((_BYTE *)this + 576) & 1) == 0;
        LOWORD(ppropvar[0]) = 11;
        LOWORD(ppropvar[1]) = v4 ? 0 : -1;
        MFURank = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                    ppv,
                    PKEY_AppContract_Pinned,
                    ppropvar);
        if ( MFURank >= 0 )
        {
          v4 = (*((_BYTE *)this + 576) & 2) == 0;
          LOWORD(ppropvar[0]) = 11;
          LOWORD(ppropvar[1]) = v4 ? 0 : -1;
          MFURank = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                      ppv,
                      PKEY_AppContract_Hidden,
                      ppropvar);
          if ( MFURank >= 0 )
          {
            LOWORD(ppropvar[0]) = 19;
            LODWORD(ppropvar[1]) = *((_DWORD *)this + 145);
            MFURank = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                        ppv,
                        PKEY_AppContract_PinnedOrder,
                        ppropvar);
            if ( MFURank >= 0 )
            {
              psz = 0;
              MFURank = CExtensionListItem::_GetMFURank(this, (double *)&psz);
              if ( MFURank >= 0 )
              {
                ppropvar[1] = (PROPVARIANT)psz;
                LOWORD(ppropvar[0]) = 5;
                MFURank = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                            ppv,
                            PKEY_AppContract_Relevance,
                            ppropvar);
                if ( MFURank >= 0 )
                {
                  v5 = 0;
                  while ( v5 < 4 )
                  {
                    psz = 0;
                    if ( (int)CExtensionListItem::_GetCustomStringProperty(
                                this,
                                (&off_1800B2410)[2 * v5],
                                (unsigned __int16 **)&psz) >= 0 )
                    {
                      *(_OWORD *)ppropvar = 0;
                      v10 = 0;
                      MFURank = InitPropVariantFromStringAsVector(psz, ppropvar);
                      if ( MFURank >= 0 )
                      {
                        MFURank = (*(__int64 (__fastcall **)(void *, _QWORD, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                                    ppv,
                                    *(&off_1800B2410 + 2 * v5 + 1),
                                    ppropvar);
                        PropVariantClear(ppropvar);
                      }
                    }
                    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&psz);
                    ++v5;
                    if ( MFURank < 0 )
                      goto LABEL_24;
                  }
                  v6 = ppv;
                  v7 = **(__int64 (__fastcall ***)(void *, GUID *, char *))ppv;
                  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(v2);
                  MFURank = v7(v6, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, v2);
                  *((_BYTE *)this + 584) = 0;
                }
              }
            }
          }
        }
      }
LABEL_24:
      Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&ppv);
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)MFURank;
}

```

## disassembly

```asm
0x18007d31c  mov     [rsp-28h+arg_10], rbx
0x18007d321  mov     [rsp-28h+arg_18], rsi
0x18007d326  push    rbp
0x18007d327  push    rdi
0x18007d328  push    r13
0x18007d32a  push    r14
0x18007d32c  push    r15
0x18007d32e  mov     rbp, rsp
0x18007d331  sub     rsp, 40h
0x18007d335  cmp     qword ptr [rcx+20h], 0
0x18007d33a  mov     rsi, rcx
0x18007d33d  jz      loc_18007D568
0x18007d343  lea     r15, [rcx+30h]
0x18007d347  cmp     qword ptr [r15], 0
0x18007d34b  jz      short loc_18007D35B
0x18007d34d  xor     ebx, ebx
0x18007d34f  cmp     [rcx+248h], bl
0x18007d355  jz      loc_18007D56D
0x18007d35b  lea     rcx, [rbp+ppv]
0x18007d35f  mov     [rbp+ppv], 0
0x18007d367  call    ?InternalAddRef@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(void)
0x18007d36c  lea     rcx, [rbp+ppv]
0x18007d370  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18007d375  lea     rdx, [rbp+ppv]; ppv
0x18007d379  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18007d380  call    cs:__imp_PSCreateMemoryPropertyStore
0x18007d386  mov     ebx, eax
0x18007d388  test    eax, eax
0x18007d38a  js      loc_18007D55D
0x18007d390  or      r14d, 0FFFFFFFFh
0x18007d394  test    byte ptr [rsi+240h], 1
0x18007d39b  lea     edi, [r14+0Ch]
0x18007d39f  mov     word ptr [rbp+ppropvar], di
0x18007d3a3  jz      short loc_18007D3AC
0x18007d3a5  mov     word ptr [rbp+ppropvar+8], r14w
0x18007d3aa  jmp     short loc_18007D3B2
0x18007d3ac  xor     eax, eax
0x18007d3ae  mov     word ptr [rbp+ppropvar+8], ax
0x18007d3b2  mov     rcx, [rbp+ppv]
0x18007d3b6  lea     r8, [rbp+ppropvar]
0x18007d3ba  lea     rdx, PKEY_AppContract_Pinned
0x18007d3c1  mov     rax, [rcx]
0x18007d3c4  mov     rax, [rax+30h]
0x18007d3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d3cd  mov     ebx, eax
0x18007d3cf  test    eax, eax
0x18007d3d1  js      loc_18007D55D
0x18007d3d7  test    byte ptr [rsi+240h], 2
0x18007d3de  mov     word ptr [rbp+ppropvar], di
0x18007d3e2  jz      short loc_18007D3EB
0x18007d3e4  mov     word ptr [rbp+ppropvar+8], r14w
0x18007d3e9  jmp     short loc_18007D3F1
0x18007d3eb  xor     eax, eax
0x18007d3ed  mov     word ptr [rbp+ppropvar+8], ax
0x18007d3f1  mov     rcx, [rbp+ppv]
0x18007d3f5  lea     r8, [rbp+ppropvar]
0x18007d3f9  lea     rdx, PKEY_AppContract_Hidden
0x18007d400  mov     rax, [rcx]
0x18007d403  mov     rax, [rax+30h]
0x18007d407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d40c  mov     ebx, eax
0x18007d40e  test    eax, eax
0x18007d410  js      loc_18007D55D
0x18007d416  mov     rcx, [rbp+ppv]
0x18007d41a  lea     r8, [rbp+ppropvar]
0x18007d41e  mov     eax, 13h
0x18007d423  lea     rdx, PKEY_AppContract_PinnedOrder
0x18007d42a  mov     word ptr [rbp+ppropvar], ax
0x18007d42e  mov     eax, [rsi+244h]
0x18007d434  mov     dword ptr [rbp+ppropvar+8], eax
0x18007d437  mov     rax, [rcx]
0x18007d43a  mov     rax, [rax+30h]
0x18007d43e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d443  mov     ebx, eax
0x18007d445  test    eax, eax
0x18007d447  js      loc_18007D55D
0x18007d44d  xorps   xmm0, xmm0
0x18007d450  lea     rdx, [rbp+psz]; double *
0x18007d454  mov     rcx, rsi; this
0x18007d457  movsd   [rbp+psz], xmm0
0x18007d45c  call    ?_GetMFURank@CExtensionListItem@@AEAAJPEAN@Z; CExtensionListItem::_GetMFURank(double *)
0x18007d461  mov     ebx, eax
0x18007d463  test    eax, eax
0x18007d465  js      loc_18007D55D
0x18007d46b  mov     rcx, [rbp+ppv]
0x18007d46f  lea     r8, [rbp+ppropvar]
0x18007d473  movsd   xmm0, [rbp+psz]
0x18007d478  lea     rdx, PKEY_AppContract_Relevance
0x18007d47f  mov     eax, 5
0x18007d484  movsd   [rbp+ppropvar+8], xmm0
0x18007d489  mov     word ptr [rbp+ppropvar], ax
0x18007d48d  mov     rax, [rcx]
0x18007d490  mov     rax, [rax+30h]
0x18007d494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d499  mov     ebx, eax
0x18007d49b  test    eax, eax
0x18007d49d  js      loc_18007D55D
0x18007d4a3  xor     edi, edi
0x18007d4a5  lea     r13, off_1800B2410; "ApplicationCategories"
0x18007d4ac  cmp     rdi, 4
0x18007d4b0  jnb     short loc_18007D52D
0x18007d4b2  mov     r14, rdi
0x18007d4b5  mov     [rbp+psz], 0
0x18007d4bd  add     r14, r14
0x18007d4c0  lea     r8, [rbp+psz]; unsigned __int16 **
0x18007d4c4  mov     rcx, rsi; this
0x18007d4c7  mov     rdx, [r13+r14*8+0]; unsigned __int16 *
0x18007d4cc  call    ?_GetCustomStringProperty@CExtensionListItem@@AEAAJPEBGPEAPEAG@Z; CExtensionListItem::_GetCustomStringProperty(ushort const *,ushort * *)
0x18007d4d1  test    eax, eax
0x18007d4d3  js      short loc_18007D51B
0x18007d4d5  mov     rcx, [rbp+psz]; psz
0x18007d4d9  lea     rdx, [rbp+ppropvar]; ppropvar
0x18007d4dd  xorps   xmm0, xmm0
0x18007d4e0  xor     eax, eax
0x18007d4e2  movups  xmmword ptr [rbp+ppropvar], xmm0
0x18007d4e6  mov     [rbp+var_10], rax
0x18007d4ea  call    cs:__imp_InitPropVariantFromStringAsVector
0x18007d4f0  mov     ebx, eax
0x18007d4f2  test    eax, eax
0x18007d4f4  js      short loc_18007D51B
0x18007d4f6  mov     rcx, [rbp+ppv]
0x18007d4fa  lea     r8, [rbp+ppropvar]
0x18007d4fe  mov     rdx, [r13+r14*8+8]
0x18007d503  mov     rax, [rcx]
0x18007d506  mov     rax, [rax+30h]
0x18007d50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d50f  lea     rcx, [rbp+ppropvar]; pvar
0x18007d513  mov     ebx, eax
0x18007d515  call    cs:__imp_PropVariantClear
0x18007d51b  lea     rcx, [rbp+psz]
0x18007d51f  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18007d524  inc     rdi
0x18007d527  test    ebx, ebx
0x18007d529  jns     short loc_18007D4AC
0x18007d52b  jmp     short loc_18007D55D
0x18007d52d  mov     rdi, [rbp+ppv]
0x18007d531  mov     rcx, r15
0x18007d534  mov     rax, [rdi]
0x18007d537  mov     rbx, [rax]
0x18007d53a  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18007d53f  mov     r8, r15
0x18007d542  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18007d549  mov     rcx, rdi
0x18007d54c  mov     rax, rbx
0x18007d54f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d554  mov     ebx, eax
0x18007d556  mov     byte ptr [rsi+248h], 0
0x18007d55d  lea     rcx, [rbp+ppv]
0x18007d561  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18007d566  jmp     short loc_18007D56D
0x18007d568  mov     ebx, 8000FFFFh
0x18007d56d  lea     r11, [rsp+40h+var_s0]
0x18007d572  mov     eax, ebx
0x18007d574  mov     rbx, [r11+40h]
0x18007d578  mov     rsi, [r11+48h]
0x18007d57c  mov     rsp, r11
0x18007d57f  pop     r15
0x18007d581  pop     r14
0x18007d583  pop     r13
0x18007d585  pop     rdi
0x18007d586  pop     rbp
0x18007d587  retn
```
