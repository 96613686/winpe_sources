# CConfirmationInterrupt::_FormatDescription(ushort const *,ushort * *)

- ea: `0x18030f0c8`
- end: `0x18030f371`
- name: `?_FormatDescription@CConfirmationInterrupt@@AEAAJPEBGPEAPEAG@Z`
- size: `681`
- prototype: `__int64 __fastcall(CConfirmationInterrupt *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18030c780`

## callees

- `0x18006c8b0`
- `0x1801caadc`
- `0x180233280`
- `0x18030f0c8`
- `0x18030f50c`
- `0x18030f794`
- `0x18030f848`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18030f301`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18030f301`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f161`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f197`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f1db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f221`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f258`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f28c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f30c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f316`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f321`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f32c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f337`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f342`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f161`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f197`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f1db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f221`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f258`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f28c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f30c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f316`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f321`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f32c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f337`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030f342`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18030f2f6`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18030f2f6`
- `ext-ms-win-shell-fileplaceholder-l1-1-0!FECommon_GetStorageProviderDisplayName` at `0x18030f1a4`
- `ext-ms-win-shell-fileplaceholder-l1-1-0!FECommon_GetStorageProviderDisplayName` at `0x18030f1a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CConfirmationInterrupt::_FormatDescription(
        CConfirmationInterrupt *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  const wchar_t *v4; // r15
  unsigned __int16 *v5; // r12
  const wchar_t *v6; // r13
  _QWORD *v7; // r14
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, LPVOID *); // rbx
  HRESULT OwnerInformation; // edi
  __int64 *v11; // rcx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64, LPVOID *); // rbx
  unsigned __int16 *v14; // r14
  unsigned __int16 *v15; // rbx
  const WCHAR *v16; // rax
  WCHAR *v17; // rsi
  unsigned __int16 *v19; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int16 *v20; // [rsp+58h] [rbp-31h]
  const wchar_t *v21; // [rsp+60h] [rbp-29h]
  const wchar_t *v22; // [rsp+68h] [rbp-21h]
  const unsigned __int16 *v23; // [rsp+70h] [rbp-19h]
  LPWSTR *ppwsz; // [rsp+78h] [rbp-11h]
  LPVOID pv; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int16 *v26; // [rsp+88h] [rbp-1h] BYREF
  unsigned __int16 *v27; // [rsp+90h] [rbp+7h] BYREF
  LPVOID v28; // [rsp+98h] [rbp+Fh] BYREF
  LPVOID v29; // [rsp+A0h] [rbp+17h] BYREF

  ppwsz = a3;
  v23 = a2;
  v22 = L"<%1 NULL:NameDest>";
  v4 = L"<%2 NULL:NameItem>";
  v21 = L"<%3 NULL:OpText>";
  v20 = L"<%5 NULL:Error>";
  v5 = L"<%6 NULL:CreationDateItem>";
  v6 = L"<%7 NULL:StorageProviderNameDest>";
  v29 = 0;
  pv = 0;
  v7 = (_QWORD *)((char *)this + 80);
  if ( !(unsigned __int8)ATL::CComPtrBase<IShellFolder>::operator!=((char *)this + 80, 0) )
  {
LABEL_6:
    v28 = 0;
    if ( (unsigned __int8)ATL::CComPtrBase<IShellFolder>::operator!=((char *)this + 72, 0) )
    {
      v12 = *v11;
      v13 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)*v11 + 40LL);
      CoTaskMemFree(0);
      OwnerInformation = v13(v12, 2147684353LL, &v28);
      if ( OwnerInformation < 0 )
      {
LABEL_27:
        CoTaskMemFree(v28);
        goto LABEL_28;
      }
      v4 = (const wchar_t *)v28;
    }
    if ( (*((_BYTE *)this + 48) & 4) != 0 )
      v21 = (const wchar_t *)*((_QWORD *)this + 8);
    v27 = 0;
    if ( (*((_BYTE *)this + 48) & 8) != 0 )
    {
      CoTaskMemFree(0);
      OwnerInformation = CConfirmationInterrupt::_GetOwnerInformation(this, &v27);
      if ( OwnerInformation < 0 )
      {
LABEL_26:
        CoTaskMemFree(v27);
        goto LABEL_27;
      }
      v14 = v27;
    }
    else
    {
      v14 = L"<%4 NULL:Owner>";
    }
    v15 = 0;
    v19 = 0;
    if ( (*((_BYTE *)this + 48) & 0x10) != 0 )
    {
      CoTaskMemFree(0);
      OwnerInformation = CConfirmationInterrupt::_GetErrorInformation(this, &v19);
      v15 = v19;
      if ( OwnerInformation < 0 )
      {
LABEL_25:
        CoTaskMemFree(v15);
        goto LABEL_26;
      }
      v20 = v19;
    }
    v26 = 0;
    if ( (*((_BYTE *)this + 48) & 0x40) != 0 )
    {
      CoTaskMemFree(0);
      OwnerInformation = CConfirmationInterrupt::_GetMergeFolderInfo(this, &v26);
      if ( OwnerInformation < 0 )
      {
LABEL_24:
        CoTaskMemFree(v26);
        goto LABEL_25;
      }
      v5 = v26;
    }
    v16 = (const WCHAR *)ShellConstructMessageStringW(g_hinst, v23, v22, v4, v21, v14, v20, v5, v6);
    v17 = (WCHAR *)v16;
    if ( v16 )
    {
      OwnerInformation = SHStrDupW(v16, ppwsz);
      LocalFree(v17);
    }
    else
    {
      OwnerInformation = -2147024882;
    }
    goto LABEL_24;
  }
  v8 = *v7;
  v9 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)*v7 + 40LL);
  CoTaskMemFree(0);
  OwnerInformation = v9(v8, 2147684353LL, &v29);
  if ( OwnerInformation >= 0 )
  {
    v22 = (const wchar_t *)v29;
    if ( *((char *)this + 48) >= 0 )
      goto LABEL_6;
    CoTaskMemFree(pv);
    OwnerInformation = FECommon_GetStorageProviderDisplayName(*v7, &pv);
    if ( OwnerInformation >= 0 )
    {
      v6 = (const wchar_t *)pv;
      goto LABEL_6;
    }
  }
LABEL_28:
  CoTaskMemFree(pv);
  CoTaskMemFree(v29);
  return (unsigned int)OwnerInformation;
}

```

## disassembly

```asm
0x18030f0c8  mov     [rsp-8+arg_18], rbx
0x18030f0cd  push    rbp
0x18030f0ce  push    rsi
0x18030f0cf  push    rdi
0x18030f0d0  push    r12
0x18030f0d2  push    r13
0x18030f0d4  push    r14
0x18030f0d6  push    r15
0x18030f0d8  lea     rbp, [rsp-27h]
0x18030f0dd  sub     rsp, 0B0h
0x18030f0e4  mov     rax, cs:__security_cookie
0x18030f0eb  xor     rax, rsp
0x18030f0ee  mov     [rbp+57h+var_38], rax
0x18030f0f2  mov     [rbp+57h+ppwsz], r8
0x18030f0f6  mov     [rbp+57h+var_70], rdx
0x18030f0fa  mov     rsi, rcx
0x18030f0fd  lea     r8, a1NullNamedest; "<%1 NULL:NameDest>"
0x18030f104  mov     [rbp+57h+var_78], r8
0x18030f108  lea     r15, a2NullNameitem; "<%2 NULL:NameItem>"
0x18030f10f  lea     rax, a3NullOptext; "<%3 NULL:OpText>"
0x18030f116  mov     [rbp+57h+var_80], rax
0x18030f11a  lea     rax, a5NullError; "<%5 NULL:Error>"
0x18030f121  mov     [rbp+57h+var_88], rax
0x18030f125  lea     r12, a6NullCreationd; "<%6 NULL:CreationDateItem>"
0x18030f12c  lea     r13, a7NullStoragepr_0; "<%7 NULL:StorageProviderNameDest>"
0x18030f133  mov     [rbp+57h+var_40], 0
0x18030f13b  mov     [rbp+57h+pv], 0
0x18030f143  lea     r14, [rcx+50h]
0x18030f147  xor     edx, edx
0x18030f149  mov     rcx, r14
0x18030f14c  call    ??9?$CComPtrBase@UIShellFolder@@@ATL@@QEBA_NPEAUIShellFolder@@@Z; ATL::CComPtrBase<IShellFolder>::operator!=(IShellFolder *)
0x18030f151  test    al, al
0x18030f153  jz      short loc_18030F1B8
0x18030f155  mov     rdi, [r14]
0x18030f158  mov     rax, [rdi]
0x18030f15b  mov     rbx, [rax+28h]
0x18030f15f  xor     ecx, ecx; pv
0x18030f161  call    cs:__imp_CoTaskMemFree
0x18030f167  lea     r8, [rbp+57h+var_40]
0x18030f16b  mov     edx, 80031001h
0x18030f170  mov     rcx, rdi
0x18030f173  mov     rax, rbx
0x18030f176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030f17b  mov     edi, eax
0x18030f17d  test    eax, eax
0x18030f17f  js      loc_18030F333
0x18030f185  mov     rax, [rbp+57h+var_40]
0x18030f189  mov     [rbp+57h+var_78], rax
0x18030f18d  test    byte ptr [rsi+30h], 80h
0x18030f191  jz      short loc_18030F1B8
0x18030f193  mov     rcx, [rbp+57h+pv]; pv
0x18030f197  call    cs:__imp_CoTaskMemFree
0x18030f19d  lea     rdx, [rbp+57h+pv]
0x18030f1a1  mov     rcx, [r14]
0x18030f1a4  call    cs:__imp_FECommon_GetStorageProviderDisplayName
0x18030f1aa  mov     edi, eax
0x18030f1ac  test    eax, eax
0x18030f1ae  js      loc_18030F333
0x18030f1b4  mov     r13, [rbp+57h+pv]
0x18030f1b8  mov     [rbp+57h+var_48], 0
0x18030f1c0  lea     rcx, [rsi+48h]
0x18030f1c4  xor     edx, edx
0x18030f1c6  call    ??9?$CComPtrBase@UIShellFolder@@@ATL@@QEBA_NPEAUIShellFolder@@@Z; ATL::CComPtrBase<IShellFolder>::operator!=(IShellFolder *)
0x18030f1cb  test    al, al
0x18030f1cd  jz      short loc_18030F203
0x18030f1cf  mov     rdi, [rcx]
0x18030f1d2  mov     rax, [rdi]
0x18030f1d5  mov     rbx, [rax+28h]
0x18030f1d9  xor     ecx, ecx; pv
0x18030f1db  call    cs:__imp_CoTaskMemFree
0x18030f1e1  lea     r8, [rbp+57h+var_48]
0x18030f1e5  mov     edx, 80031001h
0x18030f1ea  mov     rcx, rdi
0x18030f1ed  mov     rax, rbx
0x18030f1f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030f1f5  mov     edi, eax
0x18030f1f7  test    eax, eax
0x18030f1f9  js      loc_18030F328
0x18030f1ff  mov     r15, [rbp+57h+var_48]
0x18030f203  test    byte ptr [rsi+30h], 4
0x18030f207  jz      short loc_18030F211
0x18030f209  mov     rax, [rsi+40h]
0x18030f20d  mov     [rbp+57h+var_80], rax
0x18030f211  mov     [rbp+57h+var_50], 0
0x18030f219  test    byte ptr [rsi+30h], 8
0x18030f21d  jz      short loc_18030F243
0x18030f21f  xor     ecx, ecx; pv
0x18030f221  call    cs:__imp_CoTaskMemFree
0x18030f227  lea     rdx, [rbp+57h+var_50]; unsigned __int16 **
0x18030f22b  mov     rcx, rsi; this
0x18030f22e  call    ?_GetOwnerInformation@CConfirmationInterrupt@@AEAAJPEAPEAG@Z; CConfirmationInterrupt::_GetOwnerInformation(ushort * *)
0x18030f233  mov     edi, eax
0x18030f235  test    eax, eax
0x18030f237  js      loc_18030F31D
0x18030f23d  mov     r14, [rbp+57h+var_50]
0x18030f241  jmp     short loc_18030F24A
0x18030f243  lea     r14, a4NullOwner; "<%4 NULL:Owner>"
0x18030f24a  xor     ebx, ebx
0x18030f24c  mov     [rbp+57h+var_90], rbx
0x18030f250  test    byte ptr [rsi+30h], 10h
0x18030f254  jz      short loc_18030F27C
0x18030f256  xor     ecx, ecx; pv
0x18030f258  call    cs:__imp_CoTaskMemFree
0x18030f25e  lea     rdx, [rbp+57h+var_90]; unsigned __int16 **
0x18030f262  mov     rcx, rsi; this
0x18030f265  call    ?_GetErrorInformation@CConfirmationInterrupt@@AEAAJPEAPEAG@Z; CConfirmationInterrupt::_GetErrorInformation(ushort * *)
0x18030f26a  mov     edi, eax
0x18030f26c  mov     rbx, [rbp+57h+var_90]
0x18030f270  test    eax, eax
0x18030f272  js      loc_18030F313
0x18030f278  mov     [rbp+57h+var_88], rbx
0x18030f27c  mov     [rbp+57h+var_58], 0
0x18030f284  test    byte ptr [rsi+30h], 40h
0x18030f288  jz      short loc_18030F2A8
0x18030f28a  xor     ecx, ecx; pv
0x18030f28c  call    cs:__imp_CoTaskMemFree
0x18030f292  lea     rdx, [rbp+57h+var_58]; unsigned __int16 **
0x18030f296  mov     rcx, rsi; this
0x18030f299  call    ?_GetMergeFolderInfo@CConfirmationInterrupt@@AEAAJPEAPEAG@Z; CConfirmationInterrupt::_GetMergeFolderInfo(ushort * *)
0x18030f29e  mov     edi, eax
0x18030f2a0  test    eax, eax
0x18030f2a2  js      short loc_18030F308
0x18030f2a4  mov     r12, [rbp+57h+var_58]
0x18030f2a8  mov     [rsp+0E0h+var_A0], r13
0x18030f2ad  mov     [rsp+0E0h+var_A8], r12
0x18030f2b2  mov     rax, [rbp+57h+var_88]
0x18030f2b6  mov     [rsp+0E0h+var_B0], rax
0x18030f2bb  mov     [rsp+0E0h+var_B8], r14
0x18030f2c0  mov     rax, [rbp+57h+var_80]
0x18030f2c4  mov     [rsp+0E0h+var_C0], rax
0x18030f2c9  mov     r9, r15
0x18030f2cc  mov     r8, [rbp+57h+var_78]
0x18030f2d0  mov     rdx, [rbp+57h+var_70]
0x18030f2d4  mov     rcx, cs:g_hinst
0x18030f2db  call    ShellConstructMessageStringW
0x18030f2e0  mov     rsi, rax
0x18030f2e3  test    rax, rax
0x18030f2e6  jnz     short loc_18030F2EF
0x18030f2e8  mov     edi, 8007000Eh
0x18030f2ed  jmp     short loc_18030F308
0x18030f2ef  mov     rdx, [rbp+57h+ppwsz]; ppwsz
0x18030f2f3  mov     rcx, rsi; psz
0x18030f2f6  call    cs:__imp_SHStrDupW
0x18030f2fc  mov     edi, eax
0x18030f2fe  mov     rcx, rsi; hMem
0x18030f301  call    cs:__imp_LocalFree
0x18030f307  nop
0x18030f308  mov     rcx, [rbp+57h+var_58]; pv
0x18030f30c  call    cs:__imp_CoTaskMemFree
0x18030f312  nop
0x18030f313  mov     rcx, rbx; pv
0x18030f316  call    cs:__imp_CoTaskMemFree
0x18030f31c  nop
0x18030f31d  mov     rcx, [rbp+57h+var_50]; pv
0x18030f321  call    cs:__imp_CoTaskMemFree
0x18030f327  nop
0x18030f328  mov     rcx, [rbp+57h+var_48]; pv
0x18030f32c  call    cs:__imp_CoTaskMemFree
0x18030f332  nop
0x18030f333  mov     rcx, [rbp+57h+pv]; pv
0x18030f337  call    cs:__imp_CoTaskMemFree
0x18030f33d  nop
0x18030f33e  mov     rcx, [rbp+57h+var_40]; pv
0x18030f342  call    cs:__imp_CoTaskMemFree
0x18030f348  mov     eax, edi
0x18030f34a  mov     rcx, [rbp+57h+var_38]
0x18030f34e  xor     rcx, rsp; StackCookie
0x18030f351  call    __security_check_cookie
0x18030f356  mov     rbx, [rsp+0E0h+arg_18]
0x18030f35e  add     rsp, 0B0h
0x18030f365  pop     r15
0x18030f367  pop     r14
0x18030f369  pop     r13
0x18030f36b  pop     r12
0x18030f36d  pop     rdi
0x18030f36e  pop     rsi
0x18030f36f  pop     rbp
0x18030f370  retn
```
