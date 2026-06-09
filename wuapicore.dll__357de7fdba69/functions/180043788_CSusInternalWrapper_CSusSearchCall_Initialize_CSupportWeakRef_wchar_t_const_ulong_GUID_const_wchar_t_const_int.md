# CSusInternalWrapper::CSusSearchCall::Initialize(CSupportWeakRef *,wchar_t const *,ulong,_GUID const &,wchar_t const *,int,int,int,int,ulong,tagProxySettings const *,char const *,wchar_t const *,tagAttributeTargeting,ISusSearchCallback6 *)

- ea: `0x180043788`
- end: `0x180043a34`
- name: `?Initialize@CSusSearchCall@CSusInternalWrapper@@QEAAJPEAVCSupportWeakRef@@PEB_WKAEBU_GUID@@1HHHHKPEBUtagProxySettings@@PEBD1UtagAttributeTargeting@@PEAUISusSearchCallback6@@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004452c`

## callees

- `0x18000588c`
- `0x180043788`
- `0x180043a3c`
- `0x180049ce4`
- `0x180081a38`
- `0x1800826a0`
- `0x180082ab0`
- `0x180082b28`
- `0x180083780`
- `0x180096b10`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800437c2`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800437c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180043911`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180043911`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800438ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800438ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18004386e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800438a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800438cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18004386e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800438a3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800438cf`

## string_xrefs

- `0x180043976`: `C:\__w\1\s\src\Client\comapi\SusInternalWrapper.cpp`

## pseudocode

```c
__int64 __fastcall CSusInternalWrapper::CSusSearchCall::Initialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int128 *a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9,
        int a10,
        int a11,
        struct tagProxySettings *a12,
        __int64 a13,
        __int64 a14,
        wchar_t **a15,
        __int64 a16)
{
  __int64 v16; // rbp
  _QWORD *v19; // rsi
  HRESULT FreeThreadedMarshaler; // ebx
  void *v23; // rcx
  wchar_t *v24; // rcx
  wchar_t *v25; // rcx
  HANDLE ProcessHeap; // rax
  struct tagProxySettings *v27; // rax
  void *v28; // rcx
  int v29; // eax
  __int128 v30; // xmm0
  int v32; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v16 = a1 + 144;
  v19 = (_QWORD *)(a1 + 160);
  FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler((LPUNKNOWN)(a1 + 144), (LPUNKNOWN *)(a1 + 160));
  if ( FreeThreadedMarshaler < 0 )
  {
    if ( *v19 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 16LL))(*v19);
    *v19 = 0;
    *(_QWORD *)(v16 + 8) = 0;
    CSusInternalWrapper::CSusCallTN<ISusSearchCallback6,ISusSearchCallback6>::ClearInner((CSusInternalWrapper::CSusCall *)a1);
    goto LABEL_24;
  }
  *(_QWORD *)(v16 + 8) = a2;
  *(_QWORD *)(a1 + 168) = a16;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a16 + 8LL))(a16);
  if ( a3 )
  {
    FreeThreadedMarshaler = DuplicateString<wchar_t const *,wchar_t *>(a3, a1 + 176);
    if ( FreeThreadedMarshaler < 0 )
      goto LABEL_24;
  }
  if ( a6 )
  {
    FreeThreadedMarshaler = DuplicateString<wchar_t const *,wchar_t *>(a6, a1 + 184);
    if ( FreeThreadedMarshaler < 0 )
      goto LABEL_24;
  }
  v23 = *(void **)(a1 + 248);
  if ( v23 )
  {
    SusFree(v23);
    *(_QWORD *)(a1 + 248) = 0;
  }
  FreeThreadedMarshaler = DuplicateOptionalString<wchar_t const *,wchar_t *>(a14, a1 + 248);
  if ( FreeThreadedMarshaler < 0 )
    goto LABEL_24;
  SysFreeString(*(BSTR *)(a1 + 256));
  *(_QWORD *)(a1 + 256) = 0;
  FreeThreadedMarshaler = SusCopyBSTR(a15[1], (wchar_t **)(a1 + 256));
  if ( FreeThreadedMarshaler < 0 )
    goto LABEL_24;
  SysFreeString(*(BSTR *)(a1 + 264));
  v24 = *a15;
  *(_QWORD *)(a1 + 264) = 0;
  FreeThreadedMarshaler = SusCopyBSTR(v24, (wchar_t **)(a1 + 264));
  if ( FreeThreadedMarshaler < 0
    || (SysFreeString(*(BSTR *)(a1 + 272)),
        v25 = a15[2],
        *(_QWORD *)(a1 + 272) = 0,
        FreeThreadedMarshaler = SusCopyBSTR(v25, (wchar_t **)(a1 + 272)),
        FreeThreadedMarshaler < 0) )
  {
LABEL_24:
    CSusInternalWrapper::CSusSearchCall::ClearInner((CSusInternalWrapper::CSusSearchCall *)a1);
    return (unsigned int)FreeThreadedMarshaler;
  }
  if ( a12 )
  {
    ProcessHeap = GetProcessHeap();
    v27 = (struct tagProxySettings *)HeapAlloc(ProcessHeap, 8u, 0x20u);
    *(_QWORD *)(a1 + 192) = v27;
    if ( !v27 )
    {
      FreeThreadedMarshaler = -2147024882;
      goto LABEL_24;
    }
    FreeThreadedMarshaler = CopyProxySettings(a12, v27);
    if ( FreeThreadedMarshaler < 0 )
      goto LABEL_24;
  }
  v28 = *(void **)(a1 + 240);
  if ( v28 )
  {
    SusFree(v28);
    *(_QWORD *)(a1 + 240) = 0;
  }
  v29 = DuplicateString<char *,char *>(a13, a1 + 240);
  if ( v29 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6CC,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SusInternalWrapper.cpp",
      (const char *)(unsigned int)v29,
      v32);
  FreeThreadedMarshaler = 0;
  *(_DWORD *)(a1 + 200) = a4;
  v30 = *a5;
  *(_DWORD *)(a1 + 208) = a8;
  *(_DWORD *)(a1 + 212) = a9;
  *(_DWORD *)(a1 + 216) = a10;
  *(_DWORD *)(a1 + 220) = a11;
  *(_OWORD *)(a1 + 224) = v30;
  *(_DWORD *)(a1 + 204) = 1;
  return (unsigned int)FreeThreadedMarshaler;
}

```

## disassembly

```asm
0x180043788  mov     rax, rsp
0x18004378b  mov     [rax+8], rbx
0x18004378f  mov     [rax+10h], rbp
0x180043793  mov     [rax+18h], rsi
0x180043797  mov     [rax+20h], rdi
0x18004379b  push    r12
0x18004379d  push    r14
0x18004379f  push    r15; int
0x1800437a1  sub     rsp, 20h
0x1800437a5  lea     rbp, [rcx+90h]
0x1800437ac  mov     r15, rdx
0x1800437af  mov     rdi, rcx
0x1800437b2  lea     rsi, [rbp+10h]
0x1800437b6  mov     rdx, rsi; ppunkMarshal
0x1800437b9  mov     rcx, rbp; punkOuter
0x1800437bc  mov     r12d, r9d
0x1800437bf  mov     r14, r8
0x1800437c2  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800437c8  mov     ebx, eax
0x1800437ca  test    eax, eax
0x1800437cc  js      loc_1800439E0
0x1800437d2  mov     [rbp+8], r15
0x1800437d6  mov     rcx, [rsp+38h+arg_78]
0x1800437de  mov     [rdi+0A8h], rcx
0x1800437e5  mov     rax, [rcx]
0x1800437e8  mov     rax, [rax+8]
0x1800437ec  call    _guard_dispatch_icall
0x1800437f1  test    r14, r14
0x1800437f4  jz      short loc_18004380F
0x1800437f6  lea     rdx, [rdi+0B0h]
0x1800437fd  mov     rcx, r14
0x180043800  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x180043805  mov     ebx, eax
0x180043807  test    eax, eax
0x180043809  js      loc_180043A0B
0x18004380f  mov     rcx, [rsp+38h+arg_28]
0x180043814  test    rcx, rcx
0x180043817  jz      short loc_18004382F
0x180043819  lea     rdx, [rdi+0B8h]
0x180043820  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x180043825  mov     ebx, eax
0x180043827  test    eax, eax
0x180043829  js      loc_180043A0B
0x18004382f  lea     rbx, [rdi+0F8h]
0x180043836  mov     rcx, [rbx]; lpMem
0x180043839  test    rcx, rcx
0x18004383c  jz      short loc_18004384A
0x18004383e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180043843  mov     qword ptr [rbx], 0
0x18004384a  mov     rcx, [rsp+38h+arg_68]
0x180043852  mov     rdx, rbx
0x180043855  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18004385a  mov     ebx, eax
0x18004385c  test    eax, eax
0x18004385e  js      loc_180043A0B
0x180043864  lea     rbx, [rdi+100h]
0x18004386b  mov     rcx, [rbx]; bstrString
0x18004386e  call    cs:__imp_SysFreeString
0x180043874  mov     rsi, [rsp+38h+arg_70]
0x18004387c  mov     rdx, rbx; wchar_t **
0x18004387f  mov     qword ptr [rbx], 0
0x180043886  mov     rcx, [rsi+8]; strIn
0x18004388a  call    ?SusCopyBSTR@@YAJPEA_WPEAPEA_W@Z; SusCopyBSTR(wchar_t *,wchar_t * *)
0x18004388f  mov     ebx, eax
0x180043891  test    eax, eax
0x180043893  js      loc_180043A0B
0x180043899  lea     rbx, [rdi+108h]
0x1800438a0  mov     rcx, [rbx]; bstrString
0x1800438a3  call    cs:__imp_SysFreeString
0x1800438a9  mov     rcx, [rsi]; strIn
0x1800438ac  mov     rdx, rbx; wchar_t **
0x1800438af  mov     qword ptr [rbx], 0
0x1800438b6  call    ?SusCopyBSTR@@YAJPEA_WPEAPEA_W@Z; SusCopyBSTR(wchar_t *,wchar_t * *)
0x1800438bb  mov     ebx, eax
0x1800438bd  test    eax, eax
0x1800438bf  js      loc_180043A0B
0x1800438c5  lea     rbx, [rdi+110h]
0x1800438cc  mov     rcx, [rbx]; bstrString
0x1800438cf  call    cs:__imp_SysFreeString
0x1800438d5  mov     rcx, [rsi+10h]; strIn
0x1800438d9  mov     rdx, rbx; wchar_t **
0x1800438dc  mov     qword ptr [rbx], 0
0x1800438e3  call    ?SusCopyBSTR@@YAJPEA_WPEAPEA_W@Z; SusCopyBSTR(wchar_t *,wchar_t * *)
0x1800438e8  mov     ebx, eax
0x1800438ea  test    eax, eax
0x1800438ec  js      loc_180043A0B
0x1800438f2  mov     rbx, [rsp+38h+arg_58]
0x1800438fa  test    rbx, rbx
0x1800438fd  jz      short loc_180043942
0x1800438ff  call    cs:__imp_GetProcessHeap
0x180043905  mov     edx, 8; dwFlags
0x18004390a  mov     rcx, rax; hHeap
0x18004390d  lea     r8d, [rdx+18h]; dwBytes
0x180043911  call    cs:__imp_HeapAlloc
0x180043917  mov     [rdi+0C0h], rax
0x18004391e  test    rax, rax
0x180043921  jnz     short loc_18004392D
0x180043923  mov     ebx, 8007000Eh
0x180043928  jmp     loc_180043A0B
0x18004392d  mov     rdx, rax; struct tagProxySettings *
0x180043930  mov     rcx, rbx; struct tagProxySettings *
0x180043933  call    ?CopyProxySettings@@YAJAEBUtagProxySettings@@PEAU1@@Z; CopyProxySettings(tagProxySettings const &,tagProxySettings *)
0x180043938  mov     ebx, eax
0x18004393a  test    eax, eax
0x18004393c  js      loc_180043A0B
0x180043942  lea     rbx, [rdi+0F0h]
0x180043949  mov     rcx, [rbx]; lpMem
0x18004394c  test    rcx, rcx
0x18004394f  jz      short loc_18004395D
0x180043951  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180043956  mov     qword ptr [rbx], 0
0x18004395d  mov     rcx, [rsp+38h+arg_60]
0x180043965  mov     rdx, rbx
0x180043968  call    ??$DuplicateString@PEADPEAD@@YAJPEADPEAPEAD@Z; DuplicateString<char *,char *>(char *,char * *)
0x18004396d  test    eax, eax
0x18004396f  jns     short loc_18004398A
0x180043971  mov     rcx, [rsp+38h]; this
0x180043976  lea     r8, aCW1SSrcClientC_68; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sus"...
0x18004397d  mov     r9d, eax; char *
0x180043980  mov     edx, 6CCh; void *
0x180043985  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004398a  mov     rax, [rsp+38h+arg_20]
0x18004398f  xor     ebx, ebx
0x180043991  mov     [rdi+0C8h], r12d
0x180043998  movups  xmm0, xmmword ptr [rax]
0x18004399b  mov     eax, [rsp+38h+arg_38]
0x18004399f  mov     [rdi+0D0h], eax
0x1800439a5  mov     eax, [rsp+38h+arg_40]
0x1800439ac  mov     [rdi+0D4h], eax
0x1800439b2  mov     eax, [rsp+38h+arg_48]
0x1800439b9  mov     [rdi+0D8h], eax
0x1800439bf  mov     eax, [rsp+38h+arg_50]
0x1800439c6  mov     [rdi+0DCh], eax
0x1800439cc  movdqu  xmmword ptr [rdi+0E0h], xmm0
0x1800439d4  mov     dword ptr [rdi+0CCh], 1
0x1800439de  jmp     short loc_180043A13
0x1800439e0  mov     rcx, [rsi]
0x1800439e3  test    rcx, rcx
0x1800439e6  jz      short loc_1800439F4
0x1800439e8  mov     rax, [rcx]
0x1800439eb  mov     rax, [rax+10h]
0x1800439ef  call    _guard_dispatch_icall
0x1800439f4  mov     rcx, rdi; this
0x1800439f7  mov     qword ptr [rsi], 0
0x1800439fe  mov     qword ptr [rbp+8], 0
0x180043a06  call    ?ClearInner@?$CSusCallTN@UISusSearchCallback6@@U1@@CSusInternalWrapper@@IEAAJXZ; CSusInternalWrapper::CSusCallTN<ISusSearchCallback6,ISusSearchCallback6>::ClearInner(void)
0x180043a0b  mov     rcx, rdi; this
0x180043a0e  call    ?ClearInner@CSusSearchCall@CSusInternalWrapper@@AEAAJXZ; CSusInternalWrapper::CSusSearchCall::ClearInner(void)
0x180043a13  mov     rbp, [rsp+38h+arg_8]
0x180043a18  mov     eax, ebx
0x180043a1a  mov     rbx, [rsp+38h+arg_0]
0x180043a1f  mov     rsi, [rsp+38h+arg_10]
0x180043a24  mov     rdi, [rsp+38h+arg_18]
0x180043a29  add     rsp, 20h
0x180043a2d  pop     r15
0x180043a2f  pop     r14
0x180043a31  pop     r12
0x180043a33  retn
```
