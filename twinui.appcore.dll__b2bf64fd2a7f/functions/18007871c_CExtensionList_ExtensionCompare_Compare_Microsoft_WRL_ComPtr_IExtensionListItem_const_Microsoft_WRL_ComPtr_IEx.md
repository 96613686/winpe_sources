# CExtensionList::ExtensionCompare::Compare(Microsoft::WRL::ComPtr<IExtensionListItem> const &,Microsoft::WRL::ComPtr<IExtensionListItem> const &)

- ea: `0x18007871c`
- end: `0x1800788bc`
- name: `?Compare@ExtensionCompare@CExtensionList@@QEBAHAEBV?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@0@Z`
- size: `416`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180077690`
- `0x1800778c0`

## callees

- `0x180022fb4`
- `0x180077108`
- `0x18007871c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180078867`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180078871`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180078867`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180078871`
- `PROPSYS!PropVariantCompareEx` at `0x180078853`
- `PROPSYS!PropVariantCompareEx` at `0x180078853`

## pseudocode

```c
__int64 __fastcall CExtensionList::ExtensionCompare::Compare(__int64 *a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // esi
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, GUID *, __int64 *); // rbx
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, GUID *, __int64 *); // rbx
  __int64 v10; // rdi
  __int64 v11; // rax
  int v12; // ebx
  __int64 v14; // [rsp+20h] [rbp-50h] BYREF
  __int64 v15; // [rsp+28h] [rbp-48h] BYREF
  __int64 v16; // [rsp+30h] [rbp-40h] BYREF
  PROPVARIANT propvar2[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v18; // [rsp+48h] [rbp-28h]
  PROPVARIANT propvar1[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+60h] [rbp-10h]
  __int64 v21; // [rsp+A8h] [rbp+38h] BYREF

  v4 = 0;
  v16 = 0;
  v15 = 0;
  if ( (int)Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(a2, &v16) >= 0
    && (int)Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(a3, &v15) >= 0 )
  {
    v6 = v16;
    v14 = 0;
    v21 = 0;
    v7 = *(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v16 + 24LL);
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v14);
    if ( v7(v6, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v14) >= 0 )
    {
      v8 = v15;
      v9 = *(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v15 + 24LL);
      Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v21);
      if ( v9(v8, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v21) >= 0 )
      {
        v10 = 0;
        do
        {
          if ( (unsigned int)v10 >= *((_DWORD *)a1 + 2) )
            break;
          v20 = 0;
          v18 = 0;
          v11 = *a1;
          *(_OWORD *)propvar1 = 0;
          *(_OWORD *)propvar2 = 0;
          if ( (*(int (__fastcall **)(__int64, __int64, PROPVARIANT *))(*(_QWORD *)v14 + 40LL))(
                 v14,
                 v11 + 24 * v10,
                 propvar1) >= 0
            && (*(int (__fastcall **)(__int64, __int64, PROPVARIANT *))(*(_QWORD *)v21 + 40LL))(
                 v21,
                 *a1 + 24 * v10,
                 propvar2) >= 0 )
          {
            v12 = *(_DWORD *)(*a1 + 24 * v10 + 20);
            v4 = PropVariantCompareEx(propvar1, propvar2, PVCU_DEFAULT, 0);
            if ( v12 != 1 )
              v4 = -v4;
          }
          PropVariantClear(propvar2);
          PropVariantClear(propvar1);
          v10 = (unsigned int)(v10 + 1);
        }
        while ( !v4 );
      }
    }
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v21);
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v14);
  }
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v16);
  return v4;
}

```

## disassembly

```asm
0x18007871c  mov     [rsp-18h+arg_0], rbx
0x180078721  mov     [rsp-18h+arg_8], rsi
0x180078726  push    rbp
0x180078727  push    rdi
0x180078728  push    r14
0x18007872a  mov     rbp, rsp
0x18007872d  sub     rsp, 70h
0x180078731  mov     rax, rdx
0x180078734  mov     r14, rcx
0x180078737  xor     esi, esi
0x180078739  lea     rdx, [rbp+var_40]
0x18007873d  mov     rcx, rax
0x180078740  mov     [rbp+var_40], rsi
0x180078744  mov     rbx, r8
0x180078747  mov     [rbp+var_48], rsi
0x18007874b  call    ??$As@UIObjectWithPropertyStore@@@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIObjectWithPropertyStore@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IObjectWithPropertyStore>>)
0x180078750  test    eax, eax
0x180078752  js      loc_180078893
0x180078758  lea     rdx, [rbp+var_48]
0x18007875c  mov     rcx, rbx
0x18007875f  call    ??$As@UIObjectWithPropertyStore@@@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIObjectWithPropertyStore@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IObjectWithPropertyStore>>)
0x180078764  test    eax, eax
0x180078766  js      loc_180078893
0x18007876c  mov     rdi, [rbp+var_40]
0x180078770  lea     rcx, [rbp+var_50]
0x180078774  mov     [rbp+var_50], rsi
0x180078778  mov     [rbp+arg_18], rsi
0x18007877c  mov     rax, [rdi]
0x18007877f  mov     rbx, [rax+18h]
0x180078783  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180078788  lea     r8, [rbp+var_50]
0x18007878c  mov     rcx, rdi
0x18007878f  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180078796  mov     rax, rbx
0x180078799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007879e  test    eax, eax
0x1800787a0  js      loc_180078881
0x1800787a6  mov     rdi, [rbp+var_48]
0x1800787aa  lea     rcx, [rbp+arg_18]
0x1800787ae  mov     rax, [rdi]
0x1800787b1  mov     rbx, [rax+18h]
0x1800787b5  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800787ba  lea     r8, [rbp+arg_18]
0x1800787be  mov     rcx, rdi
0x1800787c1  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1800787c8  mov     rax, rbx
0x1800787cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800787d0  test    eax, eax
0x1800787d2  js      loc_180078881
0x1800787d8  xor     edi, edi
0x1800787da  cmp     edi, [r14+8]
0x1800787de  jnb     loc_180078881
0x1800787e4  mov     rcx, [rbp+var_50]
0x1800787e8  lea     rbx, [rdi+rdi*2]
0x1800787ec  xor     eax, eax
0x1800787ee  xorps   xmm0, xmm0
0x1800787f1  mov     [rbp+var_10], rax
0x1800787f5  xorps   xmm1, xmm1
0x1800787f8  mov     [rbp+var_28], rax
0x1800787fc  mov     rax, [r14]
0x1800787ff  movups  xmmword ptr [rbp+propvar1], xmm0
0x180078803  movups  xmmword ptr [rbp+propvar2], xmm1
0x180078807  mov     r8, [rcx]
0x18007880a  lea     rdx, [rax+rbx*8]
0x18007880e  mov     rax, [r8+28h]
0x180078812  lea     r8, [rbp+propvar1]
0x180078816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007881b  test    eax, eax
0x18007881d  js      short loc_180078863
0x18007881f  mov     rax, [r14]
0x180078822  mov     rcx, [rbp+arg_18]
0x180078826  lea     rdx, [rax+rbx*8]
0x18007882a  mov     r8, [rcx]
0x18007882d  mov     rax, [r8+28h]
0x180078831  lea     r8, [rbp+propvar2]
0x180078835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007883a  test    eax, eax
0x18007883c  js      short loc_180078863
0x18007883e  mov     rax, [r14]
0x180078841  lea     rdx, [rbp+propvar2]; propvar2
0x180078845  xor     r9d, r9d; flags
0x180078848  lea     rcx, [rbp+propvar1]; propvar1
0x18007884c  xor     r8d, r8d; unit
0x18007884f  mov     ebx, [rax+rbx*8+14h]
0x180078853  call    cs:__imp_PropVariantCompareEx
0x180078859  mov     esi, eax
0x18007885b  neg     eax
0x18007885d  cmp     ebx, 1
0x180078860  cmovnz  esi, eax
0x180078863  lea     rcx, [rbp+propvar2]; pvar
0x180078867  call    cs:__imp_PropVariantClear
0x18007886d  lea     rcx, [rbp+propvar1]; pvar
0x180078871  call    cs:__imp_PropVariantClear
0x180078877  inc     edi
0x180078879  test    esi, esi
0x18007887b  jz      loc_1800787DA
0x180078881  lea     rcx, [rbp+arg_18]
0x180078885  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18007888a  lea     rcx, [rbp+var_50]
0x18007888e  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180078893  lea     rcx, [rbp+var_48]
0x180078897  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18007889c  lea     rcx, [rbp+var_40]
0x1800788a0  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800788a5  lea     r11, [rsp+70h+var_s0]
0x1800788aa  mov     eax, esi
0x1800788ac  mov     rbx, [r11+20h]
0x1800788b0  mov     rsi, [r11+28h]
0x1800788b4  mov     rsp, r11
0x1800788b7  pop     r14
0x1800788b9  pop     rdi
0x1800788ba  pop     rbp
0x1800788bb  retn
```
