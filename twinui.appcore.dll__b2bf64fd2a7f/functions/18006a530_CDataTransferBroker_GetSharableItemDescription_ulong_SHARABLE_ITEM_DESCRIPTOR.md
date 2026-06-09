# CDataTransferBroker::GetSharableItemDescription(ulong,SHARABLE_ITEM_DESCRIPTOR *)

- ea: `0x18006a530`
- end: `0x18006aa0e`
- name: `?GetSharableItemDescription@CDataTransferBroker@@UEAAJKPEAUSHARABLE_ITEM_DESCRIPTOR@@@Z`
- size: `1246`
- prototype: `int(CDataTransferBroker *__hidden this, unsigned int, struct SHARABLE_ITEM_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006aa20`

## callees

- `0x180003d24`
- `0x180018180`
- `0x1800366a0`
- `0x18005add0`
- `0x18006109c`
- `0x1800639d8`
- `0x180068d0c`
- `0x18006a530`
- `0x18006de30`
- `0x18006e0c8`
- `0x18006e5b8`
- `0x18006e614`
- `0x18006e884`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a556`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a556`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a9eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a9eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a741`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a81b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a85b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a741`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a81b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006a85b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006a778`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006a842`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006a778`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006a842`

## pseudocode

```c
__int64 __fastcall CDataTransferBroker::GetSharableItemDescription(
        CDataTransferBroker *this,
        unsigned int a2,
        struct SHARABLE_ITEM_DESCRIPTOR *a3)
{
  __int64 v6; // rcx
  int SharableItemType; // eax
  int v8; // eax
  int v9; // ebx
  _QWORD *v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // rcx
  bool v13; // sf
  __int64 v14; // r8
  int v15; // r8d
  __int64 v16; // rdx
  int v17; // r8d
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64 *); // rbx
  int v21; // r15d
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v25; // eax
  __int64 v26; // rdi
  int (__fastcall *v27)(__int64, HSTRING *); // rbx
  const unsigned __int16 *v28; // rax
  __int64 *v29; // rdi
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, __int64, __int64 *); // rbx
  PVOID v32; // rcx
  const wchar_t *v33; // r8
  const wchar_t *v34; // rax
  __int64 v36; // [rsp+40h] [rbp-40h] BYREF
  __int64 v37; // [rsp+48h] [rbp-38h] BYREF
  __int64 v38; // [rsp+50h] [rbp-30h] BYREF
  __int64 v39; // [rsp+58h] [rbp-28h]
  __int64 v40; // [rsp+60h] [rbp-20h]
  __int64 v41; // [rsp+68h] [rbp-18h] BYREF
  __int64 v42; // [rsp+70h] [rbp-10h]
  __int64 v43; // [rsp+78h] [rbp-8h]
  UINT32 length; // [rsp+C0h] [rbp+40h] BYREF
  HSTRING string; // [rsp+D8h] [rbp+58h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McTemplateU0qq_EventWriteTransfer(
      v6,
      SharingManager_GetSharableItemDescription_Start,
      a2,
      *((unsigned int *)this + 27));
  *(_OWORD *)a3 = 0;
  *((_QWORD *)a3 + 2) = 0;
  SharableItemType = CDataTransferBroker::_GetSharableItemType((char *)this - 48, a2);
  if ( !SharableItemType )
  {
    v37 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    if ( (int)CDataTransferBroker::_GetSharableItemDataPackage((char *)this - 48, 0, &v37) < 0 )
      goto LABEL_37;
    v19 = v37;
    v36 = 0;
    v20 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    v21 = v20(v19, &v36);
    if ( v21 < 0 )
    {
LABEL_35:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      if ( v21 >= 0 )
      {
        v29 = (__int64 *)((char *)this + 80);
        goto LABEL_38;
      }
LABEL_37:
      v29 = (__int64 *)((char *)this + 80);
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, struct SHARABLE_ITEM_DESCRIPTOR *))(**((_QWORD **)this + 10) + 56LL))(
             *((_QWORD *)this + 10),
             0,
             *((unsigned int *)this + 100),
             *((_QWORD *)this + 42),
             *((_QWORD *)this + 34),
             a3);
      if ( v9 < 0 )
      {
LABEL_46:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
        goto LABEL_47;
      }
LABEL_38:
      v38 = 0;
      v39 = 0;
      v40 = 0;
      if ( *((_QWORD *)a3 + 1) )
      {
        v30 = *v29;
        v41 = 0;
        v42 = 0;
        v43 = 0;
        v31 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v30 + 48LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v41);
        v42 = -1;
        v43 = -1;
        v9 = v31(v30, 7, &v41);
        if ( v9 >= 0 )
          v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeMessage(
                 &v38,
                 v41,
                 *(_QWORD *)a3,
                 *((_QWORD *)a3 + 1));
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v41);
      }
      else
      {
        v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
               &v38,
               *(_QWORD *)a3,
               -1);
      }
      if ( v9 >= 0 )
      {
        *((_QWORD *)a3 + 2) = v38;
        v38 = 0;
        v40 = 0;
        v39 = 0;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v38);
      goto LABEL_46;
    }
    v22 = v36;
    string = 0;
    v23 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v21 = v23(v22, &string);
    if ( v21 >= 0 )
    {
      length = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
      if ( length )
      {
        if ( *((_DWORD *)this + 100) == 3 )
        {
          v21 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct SHARABLE_ITEM_DESCRIPTOR *))(**((_QWORD **)this + 10)
                                                                                              + 48LL))(
                  *((_QWORD *)this + 10),
                  9,
                  a3);
          if ( v21 < 0 )
            goto LABEL_34;
          v25 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, char *))(**((_QWORD **)this + 10)
                                                                                           + 56LL))(
                  *((_QWORD *)this + 10),
                  2,
                  *((unsigned int *)this + 100),
                  *((_QWORD *)this + 42),
                  *((_QWORD *)this + 34),
                  (char *)a3 + 8);
        }
        else
        {
          v21 = CoAllocStringOneLine(StringRawBuffer, (unsigned __int16 **)a3);
          if ( v21 < 0 )
            goto LABEL_34;
          v26 = v36;
          v27 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 64LL);
          WindowsDeleteString(string);
          string = 0;
          if ( v27(v26, &string) < 0 )
            goto LABEL_34;
          v28 = WindowsGetStringRawBuffer(string, 0);
          v25 = CoAllocStringOneLine(v28, (unsigned __int16 **)a3 + 1);
        }
        v21 = v25;
        goto LABEL_34;
      }
      v21 = -2147467259;
    }
LABEL_34:
    WindowsDeleteString(string);
    goto LABEL_35;
  }
  v8 = SharableItemType - 1;
  if ( v8 )
  {
    if ( v8 != 1 )
    {
LABEL_6:
      v9 = -2147418113;
      goto LABEL_47;
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct SHARABLE_ITEM_DESCRIPTOR *))(**((_QWORD **)this + 10) + 48LL))(
           *((_QWORD *)this + 10),
           9,
           a3);
    if ( v9 < 0 )
      goto LABEL_47;
    v10 = (_QWORD *)((char *)a3 + 8);
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, char *))(**((_QWORD **)this + 10) + 56LL))(
           *((_QWORD *)this + 10),
           2,
           *((unsigned int *)this + 100),
           *((_QWORD *)this + 42),
           *((_QWORD *)this + 34),
           (char *)a3 + 8);
    v13 = v9 < 0;
  }
  else
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct SHARABLE_ITEM_DESCRIPTOR *))(**((_QWORD **)this + 10) + 48LL))(
           *((_QWORD *)this + 10),
           8,
           a3);
    if ( v9 < 0 )
      goto LABEL_47;
    v14 = *((unsigned int *)this + 100);
    if ( (v14 & 0xFFFFFFFD) != 0 )
    {
      v15 = v14 - 1;
      if ( v15 )
      {
        v16 = 2;
        v17 = v15 - 2;
        if ( v17 )
        {
          if ( v17 != 1 )
            goto LABEL_6;
        }
        else
        {
          v16 = 1;
        }
      }
      else
      {
        v16 = 3;
      }
      v10 = (_QWORD *)((char *)a3 + 8);
      v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 10) + 48LL))(
              *((_QWORD *)this + 10),
              v16,
              (char *)a3 + 8);
    }
    else
    {
      v10 = (_QWORD *)((char *)a3 + 8);
      v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD, char *))(**((_QWORD **)this + 10) + 56LL))(
              *((_QWORD *)this + 10),
              1,
              v14,
              *((_QWORD *)this + 42),
              *((_QWORD *)this + 34),
              (char *)a3 + 8);
    }
    v9 = v18;
    v13 = v18 < 0;
  }
  if ( !v13 )
    v9 = _AllocString<CTCoAllocPolicy>(v12, v11, *v10, (char *)a3 + 16);
LABEL_47:
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    v33 = L"<>";
    v34 = L"<>";
    if ( *((_QWORD *)a3 + 1) )
      v34 = (const wchar_t *)*((_QWORD *)a3 + 1);
    if ( *(_QWORD *)a3 )
      v33 = *(const wchar_t **)a3;
    WPP_SF_qdSS(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, (_DWORD)v33, (_DWORD)this - 48, v9, (__int64)v33, (__int64)v34);
  }
  if ( v9 < 0 )
    FreeSharableItemDescriptor(a3);
  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McTemplateU0q_EventWriteTransfer(v32, SharingManager_GetSharableItemDescription_Stop, (unsigned int)v9);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18006a530  mov     [rsp-38h+arg_8], rbx
0x18006a535  push    rbp
0x18006a536  push    rsi
0x18006a537  push    rdi
0x18006a538  push    r12
0x18006a53a  push    r13
0x18006a53c  push    r14
0x18006a53e  push    r15
0x18006a540  mov     rbp, rsp
0x18006a543  sub     rsp, 80h
0x18006a54a  mov     r14, rcx
0x18006a54d  mov     rsi, r8
0x18006a550  add     rcx, 18h; lpCriticalSection
0x18006a554  mov     ebx, edx
0x18006a556  call    cs:__imp_EnterCriticalSection
0x18006a55c  test    cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x18006a563  lea     r13, [r14-30h]
0x18006a567  jz      short loc_18006A57F
0x18006a569  mov     r9d, [r13+9Ch]
0x18006a570  lea     rdx, SharingManager_GetSharableItemDescription_Start
0x18006a577  mov     r8d, ebx
0x18006a57a  call    McTemplateU0qq_EventWriteTransfer
0x18006a57f  xor     eax, eax
0x18006a581  xorps   xmm0, xmm0
0x18006a584  movups  xmmword ptr [rsi], xmm0
0x18006a587  mov     edx, ebx
0x18006a589  mov     [rsi+10h], rax
0x18006a58d  mov     rcx, r13
0x18006a590  call    ?_GetSharableItemType@CDataTransferBroker@@AEAA?AW4SharableItemType@@K@Z; CDataTransferBroker::_GetSharableItemType(ulong)
0x18006a595  xor     r15d, r15d
0x18006a598  test    eax, eax
0x18006a59a  jz      loc_18006A6D7
0x18006a5a0  sub     eax, 1
0x18006a5a3  jz      short loc_18006A617
0x18006a5a5  cmp     eax, 1
0x18006a5a8  jz      short loc_18006A5B4
0x18006a5aa  mov     ebx, 8000FFFFh
0x18006a5af  jmp     loc_18006A96B
0x18006a5b4  mov     rcx, [r14+50h]
0x18006a5b8  mov     r8, rsi
0x18006a5bb  mov     edx, 9
0x18006a5c0  mov     rax, [rcx]
0x18006a5c3  mov     rax, [rax+30h]
0x18006a5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a5cc  mov     ebx, eax
0x18006a5ce  test    eax, eax
0x18006a5d0  js      loc_18006A96B
0x18006a5d6  mov     rdx, [r14+110h]
0x18006a5dd  lea     rdi, [rsi+8]
0x18006a5e1  mov     rcx, [r14+50h]
0x18006a5e5  mov     r9, [r14+150h]
0x18006a5ec  mov     r8d, [r14+190h]
0x18006a5f3  mov     [rsp+80h+var_58], rdi
0x18006a5f8  mov     rax, [rcx]
0x18006a5fb  mov     [rsp+80h+var_60], rdx
0x18006a600  mov     edx, 2
0x18006a605  mov     rax, [rax+38h]
0x18006a609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a60e  mov     ebx, eax
0x18006a610  test    eax, eax
0x18006a612  jmp     loc_18006A6BE
0x18006a617  mov     rcx, [r14+50h]
0x18006a61b  mov     r8, rsi
0x18006a61e  mov     edx, 8
0x18006a623  mov     rax, [rcx]
0x18006a626  mov     rax, [rax+30h]
0x18006a62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a62f  mov     ebx, eax
0x18006a631  test    eax, eax
0x18006a633  js      loc_18006A96B
0x18006a639  mov     r8d, [r14+190h]
0x18006a640  test    r8d, 0FFFFFFFDh
0x18006a647  jz      short loc_18006A689
0x18006a649  sub     r8d, 1
0x18006a64d  jz      short loc_18006A66B
0x18006a64f  mov     edx, 2
0x18006a654  sub     r8d, edx
0x18006a657  jz      short loc_18006A664
0x18006a659  cmp     r8d, 1
0x18006a65d  jz      short loc_18006A670
0x18006a65f  jmp     loc_18006A5AA
0x18006a664  mov     edx, 1
0x18006a669  jmp     short loc_18006A670
0x18006a66b  mov     edx, 3
0x18006a670  mov     rcx, [r14+50h]
0x18006a674  lea     rdi, [rsi+8]
0x18006a678  mov     r8, rdi
0x18006a67b  mov     rax, [rcx]
0x18006a67e  mov     rax, [rax+30h]
0x18006a682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a687  jmp     short loc_18006A6BA
0x18006a689  mov     rdx, [r14+110h]
0x18006a690  lea     rdi, [rsi+8]
0x18006a694  mov     rcx, [r14+50h]
0x18006a698  mov     r9, [r14+150h]
0x18006a69f  mov     [rsp+80h+var_58], rdi
0x18006a6a4  mov     [rsp+80h+var_60], rdx
0x18006a6a9  mov     edx, 1
0x18006a6ae  mov     rax, [rcx]
0x18006a6b1  mov     rax, [rax+38h]
0x18006a6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a6ba  mov     ebx, eax
0x18006a6bc  test    eax, eax
0x18006a6be  js      loc_18006A96B
0x18006a6c4  mov     r8, [rdi]
0x18006a6c7  lea     r9, [rsi+10h]
0x18006a6cb  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18006a6d0  mov     ebx, eax
0x18006a6d2  jmp     loc_18006A96B
0x18006a6d7  lea     rcx, [rbp+var_38]
0x18006a6db  mov     [rbp+var_38], r15
0x18006a6df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006a6e4  lea     r8, [rbp+var_38]
0x18006a6e8  xor     edx, edx
0x18006a6ea  mov     rcx, r13
0x18006a6ed  call    ?_GetSharableItemDataPackage@CDataTransferBroker@@AEAAJW4SharableItemType@@PEAPEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@@Z; CDataTransferBroker::_GetSharableItemDataPackage(SharableItemType,Windows::ApplicationModel::DataTransfer::IDataPackage * *)
0x18006a6f2  test    eax, eax
0x18006a6f4  js      loc_18006A87B
0x18006a6fa  mov     rdi, [rbp+var_38]
0x18006a6fe  lea     rcx, [rbp+var_40]
0x18006a702  mov     [rbp+var_40], r15
0x18006a706  mov     rax, [rdi]
0x18006a709  mov     rbx, [rax+38h]
0x18006a70d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006a712  lea     rdx, [rbp+var_40]
0x18006a716  mov     rcx, rdi
0x18006a719  mov     rax, rbx
0x18006a71c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a721  mov     r15d, eax
0x18006a724  test    eax, eax
0x18006a726  js      loc_18006A861
0x18006a72c  mov     rdi, [rbp+var_40]
0x18006a730  xor     ecx, ecx; string
0x18006a732  mov     [rbp+string], 0
0x18006a73a  mov     rax, [rdi]
0x18006a73d  mov     rbx, [rax+30h]
0x18006a741  call    cs:__imp_WindowsDeleteString
0x18006a747  lea     rdx, [rbp+string]
0x18006a74b  mov     [rbp+string], 0
0x18006a753  mov     rcx, rdi
0x18006a756  mov     rax, rbx
0x18006a759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a75e  mov     r15d, eax
0x18006a761  test    eax, eax
0x18006a763  js      loc_18006A857
0x18006a769  mov     rcx, [rbp+string]; string
0x18006a76d  lea     rdx, [rbp+length]; length
0x18006a771  mov     [rbp+length], 0
0x18006a778  call    cs:__imp_WindowsGetStringRawBuffer
0x18006a77e  cmp     [rbp+length], 0
0x18006a782  jnz     short loc_18006A78F
0x18006a784  mov     r15d, 80004005h
0x18006a78a  jmp     loc_18006A857
0x18006a78f  mov     edx, 3
0x18006a794  cmp     [r14+190h], edx
0x18006a79b  jnz     short loc_18006A7FA
0x18006a79d  mov     rcx, [r14+50h]
0x18006a7a1  mov     r8, rsi
0x18006a7a4  mov     edx, 9
0x18006a7a9  mov     rax, [rcx]
0x18006a7ac  mov     rax, [rax+30h]
0x18006a7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a7b5  mov     r15d, eax
0x18006a7b8  test    eax, eax
0x18006a7ba  js      loc_18006A857
0x18006a7c0  mov     rcx, [r14+50h]
0x18006a7c4  lea     rdx, [rsi+8]
0x18006a7c8  mov     r9, [r14+150h]
0x18006a7cf  mov     r8d, [r14+190h]
0x18006a7d6  mov     [rsp+80h+var_58], rdx
0x18006a7db  mov     rdx, [r14+110h]
0x18006a7e2  mov     rax, [rcx]
0x18006a7e5  mov     [rsp+80h+var_60], rdx
0x18006a7ea  mov     edx, 2
0x18006a7ef  mov     rax, [rax+38h]
0x18006a7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a7f8  jmp     short loc_18006A854
0x18006a7fa  mov     rdx, rsi; unsigned __int16 **
0x18006a7fd  mov     rcx, rax; unsigned __int16 *
0x18006a800  call    ?CoAllocStringOneLine@@YAJPEBGPEAPEAG@Z; CoAllocStringOneLine(ushort const *,ushort * *)
0x18006a805  mov     r15d, eax
0x18006a808  test    eax, eax
0x18006a80a  js      short loc_18006A857
0x18006a80c  mov     rdi, [rbp+var_40]
0x18006a810  mov     rcx, [rbp+string]; string
0x18006a814  mov     rax, [rdi]
0x18006a817  mov     rbx, [rax+40h]
0x18006a81b  call    cs:__imp_WindowsDeleteString
0x18006a821  lea     rdx, [rbp+string]
0x18006a825  mov     [rbp+string], 0
0x18006a82d  mov     rcx, rdi
0x18006a830  mov     rax, rbx
0x18006a833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a838  test    eax, eax
0x18006a83a  js      short loc_18006A857
0x18006a83c  mov     rcx, [rbp+string]; string
0x18006a840  xor     edx, edx; length
0x18006a842  call    cs:__imp_WindowsGetStringRawBuffer
0x18006a848  mov     rcx, rax; unsigned __int16 *
0x18006a84b  lea     rdx, [rsi+8]; unsigned __int16 **
0x18006a84f  call    ?CoAllocStringOneLine@@YAJPEBGPEAPEAG@Z; CoAllocStringOneLine(ushort const *,ushort * *)
0x18006a854  mov     r15d, eax
0x18006a857  mov     rcx, [rbp+string]; string
0x18006a85b  call    cs:__imp_WindowsDeleteString
0x18006a861  lea     rcx, [rbp+var_40]
0x18006a865  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006a86a  test    r15d, r15d
0x18006a86d  js      short loc_18006A878
0x18006a86f  lea     rdi, [r14+50h]
0x18006a873  xor     r15d, r15d
0x18006a876  jmp     short loc_18006A8B9
0x18006a878  xor     r15d, r15d
0x18006a87b  mov     rdx, [r14+110h]
0x18006a882  lea     rdi, [r14+50h]
0x18006a886  mov     rcx, [rdi]
0x18006a889  mov     r9, [r14+150h]
0x18006a890  mov     r8d, [r14+190h]
0x18006a897  mov     [rsp+80h+var_58], rsi
0x18006a89c  mov     rax, [rcx]
0x18006a89f  mov     [rsp+80h+var_60], rdx
0x18006a8a4  xor     edx, edx
0x18006a8a6  mov     rax, [rax+38h]
0x18006a8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a8af  mov     ebx, eax
0x18006a8b1  test    eax, eax
0x18006a8b3  js      loc_18006A962
0x18006a8b9  mov     [rbp+var_30], r15
0x18006a8bd  mov     [rbp+var_28], r15
0x18006a8c1  mov     [rbp+var_20], r15
0x18006a8c5  cmp     [rsi+8], r15
0x18006a8c9  jnz     short loc_18006A8DF
0x18006a8cb  mov     rdx, [rsi]
0x18006a8ce  lea     rcx, [rbp+var_30]
0x18006a8d2  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006a8d6  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18006a8db  mov     ebx, eax
0x18006a8dd  jmp     short loc_18006A941
0x18006a8df  mov     rdi, [rdi]
0x18006a8e2  lea     rcx, [rbp+var_18]
0x18006a8e6  mov     [rbp+var_18], r15
0x18006a8ea  mov     [rbp+var_10], r15
0x18006a8ee  mov     [rbp+var_8], r15
0x18006a8f2  mov     rax, [rdi]
0x18006a8f5  mov     rbx, [rax+30h]
0x18006a8f9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006a8fe  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006a902  lea     r8, [rbp+var_18]
0x18006a906  mov     [rbp+var_10], rax
0x18006a90a  mov     rcx, rdi
0x18006a90d  mov     [rbp+var_8], rax
0x18006a911  lea     edx, [rax+8]
0x18006a914  mov     rax, rbx
0x18006a917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a91c  mov     ebx, eax
0x18006a91e  test    eax, eax
0x18006a920  js      short loc_18006A938
0x18006a922  mov     r9, [rsi+8]
0x18006a926  lea     rcx, [rbp+var_30]
0x18006a92a  mov     r8, [rsi]
0x18006a92d  mov     rdx, [rbp+var_18]
0x18006a931  call    ?InitializeMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeMessage(ushort const *,...)
0x18006a936  mov     ebx, eax
0x18006a938  lea     rcx, [rbp+var_18]
0x18006a93c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006a941  test    ebx, ebx
0x18006a943  js      short loc_18006A959
0x18006a945  mov     rax, [rbp+var_30]
0x18006a949  mov     [rsi+10h], rax
0x18006a94d  mov     [rbp+var_30], r15
0x18006a951  mov     [rbp+var_20], r15
0x18006a955  mov     [rbp+var_28], r15
0x18006a959  lea     rcx, [rbp+var_30]
0x18006a95d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006a962  lea     rcx, [rbp+var_38]
0x18006a966  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006a96b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a972  lea     rax, WPP_GLOBAL_Control
0x18006a979  cmp     rcx, rax
0x18006a97c  jz      short loc_18006A9C3
0x18006a97e  test    byte ptr [rcx+44h], 1
0x18006a982  jz      short loc_18006A9C3
0x18006a984  cmp     byte ptr [rcx+41h], 4
0x18006a988  jb      short loc_18006A9C3
0x18006a98a  cmp     [rsi+8], r15
0x18006a98e  lea     r8, asc_180099C2C; "<>"
0x18006a995  mov     rcx, [rcx+38h]
0x18006a999  mov     rax, r8
0x18006a99c  cmovnz  rax, [rsi+8]
0x18006a9a1  mov     edx, 0Ch
0x18006a9a6  cmp     [rsi], r15
0x18006a9a9  mov     r9, r13
0x18006a9ac  mov     [rsp+80h+var_50], rax
0x18006a9b1  cmovnz  r8, [rsi]
0x18006a9b5  mov     [rsp+80h+var_58], r8
0x18006a9ba  mov     dword ptr [rsp+80h+var_60], ebx
0x18006a9be  call    WPP_SF_qdSS
0x18006a9c3  test    ebx, ebx
0x18006a9c5  jns     short loc_18006A9CF
0x18006a9c7  mov     rcx, rsi; struct SHARABLE_ITEM_DESCRIPTOR *
0x18006a9ca  call    ?FreeSharableItemDescriptor@@YAXPEAUSHARABLE_ITEM_DESCRIPTOR@@@Z; FreeSharableItemDescriptor(SHARABLE_ITEM_DESCRIPTOR *)
  ... truncated ...
```
