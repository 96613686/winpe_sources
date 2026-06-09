# CDataTransferBroker::GetSharableItemDisplayInfo(ulong,tagSIZE const &,SHARABLE_ITEM_DISPLAY_INFO *)

- ea: `0x18006aa20`
- end: `0x18006ac53`
- name: `?GetSharableItemDisplayInfo@CDataTransferBroker@@UEAAJKAEBUtagSIZE@@PEAUSHARABLE_ITEM_DISPLAY_INFO@@@Z`
- size: `563`
- prototype: `__int64 __fastcall(CDataTransferBroker *__hidden this, unsigned int, const struct tagSIZE *, struct SHARABLE_ITEM_DISPLAY_INFO *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001e028`
- `0x1800366a0`
- `0x18006109c`
- `0x180067f68`
- `0x18006a530`
- `0x18006aa20`
- `0x18006df74`
- `0x18006e0c8`
- `0x18006e5b8`
- `0x18006e614`
- `0x18006e884`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006aa3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006aa3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006abbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006abbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ab82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ab82`

## pseudocode

```c
__int64 __fastcall CDataTransferBroker::GetSharableItemDisplayInfo(
        CDataTransferBroker *this,
        unsigned int a2,
        const struct tagSIZE *a3,
        struct SHARABLE_ITEM_DISPLAY_INFO *a4)
{
  __int64 v7; // rcx
  const wchar_t **v8; // r13
  int SharableItemDescription; // edi
  int SharableItemType; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  const wchar_t *v14; // r8
  __int64 v15; // rdx
  int v16; // ebp
  int v17; // ecx
  PVOID v18; // rcx
  const wchar_t *v19; // r8
  const wchar_t *v20; // rax
  HWND v22; // rcx
  HICON v23; // [rsp+90h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McTemplateU0qq_EventWriteTransfer(
      v7,
      SharingManager_GetSharableItemDisplayInfo_Start,
      a2,
      *((unsigned int *)this + 27));
  v8 = (const wchar_t **)((char *)a4 + 16);
  *(_OWORD *)a4 = 0;
  *((_OWORD *)a4 + 1) = 0;
  *((_QWORD *)a4 + 4) = 0;
  SharableItemDescription = CDataTransferBroker::GetSharableItemDescription(
                              this,
                              a2,
                              (struct SHARABLE_ITEM_DISPLAY_INFO *)((char *)a4 + 16));
  if ( SharableItemDescription >= 0 )
  {
    SharableItemType = CDataTransferBroker::_GetSharableItemType((char *)this - 48, a2);
    if ( SharableItemType )
    {
      v13 = SharableItemType - 1;
      if ( v13 )
      {
        if ( v13 != 1 )
        {
LABEL_7:
          SharableItemDescription = -2147418113;
          goto LABEL_18;
        }
        goto LABEL_8;
      }
      v15 = 2;
      goto LABEL_10;
    }
    v12 = *((unsigned int *)this + 100);
    if ( (_DWORD)v12 )
    {
      v16 = 2;
      v17 = v12 - 2;
      if ( !v17 )
      {
        v22 = (HWND)*((_QWORD *)this + 34);
        v23 = 0;
        if ( (int)GetExecutableIconFromHwnd(v22, &v23) < 0 )
        {
          *((_WORD *)a4 + 4) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 10) + 64LL))(
                                 *((_QWORD *)this + 10),
                                 0);
          v16 = 1;
        }
        else
        {
          *((_QWORD *)a4 + 1) = v23;
          v23 = 0;
        }
        *(_DWORD *)a4 = v16;
        wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(&v23);
        goto LABEL_18;
      }
      v12 = (unsigned int)(v17 - 1);
      if ( !(_DWORD)v12 )
      {
        if ( (int)CDataTransferBroker::_GetSharableItemError((char *)this - 48, 0) >= 0 )
        {
LABEL_8:
          v14 = L"Microsoft.WindowsStore_8wekyb3d8bbwe!App";
          goto LABEL_16;
        }
        v15 = 0;
LABEL_10:
        *((_WORD *)a4 + 4) = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 10) + 64LL))(
                               *((_QWORD *)this + 10),
                               v15);
        *(_DWORD *)a4 = 1;
        goto LABEL_18;
      }
      if ( (_DWORD)v12 != 1 )
        goto LABEL_7;
    }
    v14 = (const wchar_t *)*((_QWORD *)this + 42);
LABEL_16:
    SharableItemDescription = _AllocString<CTCoAllocPolicy>(v12, v11, v14, (char *)a4 + 8);
    if ( SharableItemDescription >= 0 )
      *(_DWORD *)a4 = 0;
  }
LABEL_18:
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    v19 = L"<>";
    v20 = L"<>";
    if ( *((_QWORD *)a4 + 3) )
      v20 = (const wchar_t *)*((_QWORD *)a4 + 3);
    if ( *v8 )
      v19 = *v8;
    WPP_SF_qdSS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      13,
      (_DWORD)v19,
      (_DWORD)this - 48,
      SharableItemDescription,
      (__int64)v19,
      (__int64)v20);
  }
  if ( SharableItemDescription < 0 )
  {
    if ( !*(_DWORD *)a4 )
      CoTaskMemFree(*((LPVOID *)a4 + 1));
    FreeSharableItemDescriptor((LPVOID *)a4 + 2);
    *(_OWORD *)a4 = 0;
    *((_OWORD *)a4 + 1) = 0;
    *((_QWORD *)a4 + 4) = 0;
  }
  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McTemplateU0q_EventWriteTransfer(
      v18,
      SharingManager_GetSharableItemDisplayInfo_Stop,
      (unsigned int)SharableItemDescription);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return (unsigned int)SharableItemDescription;
}

```

## disassembly

```asm
0x18006aa20  push    rbx
0x18006aa22  push    rbp
0x18006aa23  push    rsi
0x18006aa24  push    rdi
0x18006aa25  push    r12
0x18006aa27  push    r13
0x18006aa29  push    r14
0x18006aa2b  push    r15
0x18006aa2d  sub     rsp, 48h
0x18006aa31  mov     rsi, rcx
0x18006aa34  mov     rbx, r9
0x18006aa37  add     rcx, 18h; lpCriticalSection
0x18006aa3b  mov     ebp, edx
0x18006aa3d  call    cs:__imp_EnterCriticalSection
0x18006aa43  test    cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x18006aa4a  lea     r15, [rsi-30h]
0x18006aa4e  jz      short loc_18006AA66
0x18006aa50  mov     r9d, [r15+9Ch]
0x18006aa57  lea     rdx, SharingManager_GetSharableItemDisplayInfo_Start
0x18006aa5e  mov     r8d, ebp
0x18006aa61  call    McTemplateU0qq_EventWriteTransfer
0x18006aa66  xorps   xmm0, xmm0
0x18006aa69  lea     r13, [rbx+10h]
0x18006aa6d  movups  xmmword ptr [rbx], xmm0
0x18006aa70  xor     eax, eax
0x18006aa72  mov     r8, r13; struct SHARABLE_ITEM_DESCRIPTOR *
0x18006aa75  movups  xmmword ptr [rbx+10h], xmm0
0x18006aa79  mov     edx, ebp; unsigned int
0x18006aa7b  mov     [rbx+20h], rax
0x18006aa7f  mov     rcx, rsi; this
0x18006aa82  call    ?GetSharableItemDescription@CDataTransferBroker@@UEAAJKPEAUSHARABLE_ITEM_DESCRIPTOR@@@Z; CDataTransferBroker::GetSharableItemDescription(ulong,SHARABLE_ITEM_DESCRIPTOR *)
0x18006aa87  xor     r14d, r14d
0x18006aa8a  mov     edi, eax
0x18006aa8c  test    eax, eax
0x18006aa8e  js      loc_18006AB1B
0x18006aa94  mov     edx, ebp
0x18006aa96  mov     rcx, r15
0x18006aa99  call    ?_GetSharableItemType@CDataTransferBroker@@AEAA?AW4SharableItemType@@K@Z; CDataTransferBroker::_GetSharableItemType(ulong)
0x18006aa9e  test    eax, eax
0x18006aaa0  jz      short loc_18006AADD
0x18006aaa2  sub     eax, 1
0x18006aaa5  jz      short loc_18006AABC
0x18006aaa7  cmp     eax, 1
0x18006aaaa  jz      short loc_18006AAB3
0x18006aaac  mov     edi, 8000FFFFh
0x18006aab1  jmp     short loc_18006AB1B
0x18006aab3  lea     r8, aMicrosoftWindo_1; "Microsoft.WindowsStore_8wekyb3d8bbwe!Ap"...
0x18006aaba  jmp     short loc_18006AB09
0x18006aabc  mov     edx, 2
0x18006aac1  mov     rcx, [rsi+50h]
0x18006aac5  mov     rax, [rcx]
0x18006aac8  mov     rax, [rax+40h]
0x18006aacc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aad1  mov     [rbx+8], ax
0x18006aad5  mov     dword ptr [rbx], 1
0x18006aadb  jmp     short loc_18006AB1B
0x18006aadd  mov     ecx, [rsi+190h]
0x18006aae3  test    ecx, ecx
0x18006aae5  jz      short loc_18006AB02
0x18006aae7  mov     ebp, 2
0x18006aaec  sub     ecx, ebp
0x18006aaee  jz      loc_18006ABEE
0x18006aaf4  sub     ecx, 1
0x18006aaf7  jz      loc_18006ABD5
0x18006aafd  cmp     ecx, 1
0x18006ab00  jnz     short loc_18006AAAC
0x18006ab02  mov     r8, [rsi+150h]
0x18006ab09  lea     r9, [rbx+8]
0x18006ab0d  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18006ab12  mov     edi, eax
0x18006ab14  test    eax, eax
0x18006ab16  js      short loc_18006AB1B
0x18006ab18  mov     [rbx], r14d
0x18006ab1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ab22  lea     rax, WPP_GLOBAL_Control
0x18006ab29  cmp     rcx, rax
0x18006ab2c  jz      short loc_18006AB75
0x18006ab2e  test    byte ptr [rcx+44h], 1
0x18006ab32  jz      short loc_18006AB75
0x18006ab34  cmp     byte ptr [rcx+41h], 4
0x18006ab38  jb      short loc_18006AB75
0x18006ab3a  cmp     [rbx+18h], r14
0x18006ab3e  lea     r8, asc_180099C2C; "<>"
0x18006ab45  mov     rcx, [rcx+38h]
0x18006ab49  mov     rax, r8
0x18006ab4c  cmovnz  rax, [rbx+18h]
0x18006ab51  mov     edx, 0Dh
0x18006ab56  cmp     [r13+0], r14
0x18006ab5a  mov     r9, r15
0x18006ab5d  mov     [rsp+88h+var_58], rax
0x18006ab62  cmovnz  r8, [r13+0]
0x18006ab67  mov     [rsp+88h+var_60], r8
0x18006ab6c  mov     [rsp+88h+var_68], edi
0x18006ab70  call    WPP_SF_qdSS
0x18006ab75  test    edi, edi
0x18006ab77  jns     short loc_18006ABA0
0x18006ab79  cmp     [rbx], r14d
0x18006ab7c  jnz     short loc_18006AB88
0x18006ab7e  mov     rcx, [rbx+8]; pv
0x18006ab82  call    cs:__imp_CoTaskMemFree
0x18006ab88  mov     rcx, r13; struct SHARABLE_ITEM_DESCRIPTOR *
0x18006ab8b  call    ?FreeSharableItemDescriptor@@YAXPEAUSHARABLE_ITEM_DESCRIPTOR@@@Z; FreeSharableItemDescriptor(SHARABLE_ITEM_DESCRIPTOR *)
0x18006ab90  xorps   xmm0, xmm0
0x18006ab93  xor     eax, eax
0x18006ab95  movups  xmmword ptr [rbx], xmm0
0x18006ab98  movups  xmmword ptr [rbx+10h], xmm0
0x18006ab9c  mov     [rbx+20h], rax
0x18006aba0  test    cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x18006aba7  jz      short loc_18006ABB8
0x18006aba9  mov     r8d, edi
0x18006abac  lea     rdx, SharingManager_GetSharableItemDisplayInfo_Stop
0x18006abb3  call    McTemplateU0q_EventWriteTransfer
0x18006abb8  lea     rcx, [rsi+18h]; lpCriticalSection
0x18006abbc  call    cs:__imp_LeaveCriticalSection
0x18006abc2  mov     eax, edi
0x18006abc4  add     rsp, 48h
0x18006abc8  pop     r15
0x18006abca  pop     r14
0x18006abcc  pop     r13
0x18006abce  pop     r12
0x18006abd0  pop     rdi
0x18006abd1  pop     rsi
0x18006abd2  pop     rbp
0x18006abd3  pop     rbx
0x18006abd4  retn
0x18006abd5  xor     edx, edx
0x18006abd7  mov     rcx, r15
0x18006abda  call    ?_GetSharableItemError@CDataTransferBroker@@AEAAJW4SharableItemType@@@Z; CDataTransferBroker::_GetSharableItemError(SharableItemType)
0x18006abdf  test    eax, eax
0x18006abe1  jns     loc_18006AAB3
0x18006abe7  xor     edx, edx
0x18006abe9  jmp     loc_18006AAC1
0x18006abee  mov     rcx, [rsi+110h]; HWND
0x18006abf5  lea     rdx, [rsp+88h+arg_0]; HICON *
0x18006abfd  mov     [rsp+88h+arg_0], r14
0x18006ac05  call    ?GetExecutableIconFromHwnd@@YAJPEAUHWND__@@PEAPEAUHICON__@@@Z; GetExecutableIconFromHwnd(HWND__ *,HICON__ * *)
0x18006ac0a  test    eax, eax
0x18006ac0c  js      short loc_18006AC24
0x18006ac0e  mov     rax, [rsp+88h+arg_0]
0x18006ac16  mov     [rbx+8], rax
0x18006ac1a  mov     [rsp+88h+arg_0], r14
0x18006ac22  jmp     short loc_18006AC3F
0x18006ac24  mov     rcx, [rsi+50h]
0x18006ac28  xor     edx, edx
0x18006ac2a  mov     rax, [rcx]
0x18006ac2d  mov     rax, [rax+40h]
0x18006ac31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac36  mov     [rbx+8], ax
0x18006ac3a  mov     ebp, 1
0x18006ac3f  lea     rcx, [rsp+88h+arg_0]
0x18006ac47  mov     [rbx], ebp
0x18006ac49  call    ??1?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(void)
0x18006ac4e  jmp     loc_18006AB1B
```
