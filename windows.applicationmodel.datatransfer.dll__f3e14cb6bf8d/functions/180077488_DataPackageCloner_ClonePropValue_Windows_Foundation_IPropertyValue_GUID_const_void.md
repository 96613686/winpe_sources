# DataPackageCloner::ClonePropValue(Windows::Foundation::IPropertyValue *,_GUID const &,void * *)

- ea: `0x180077488`
- end: `0x1800776f9`
- name: `?ClonePropValue@DataPackageCloner@@AEAAJPEAUIPropertyValue@Foundation@Windows@@AEBU_GUID@@PEAPEAX@Z`
- size: `625`
- prototype: `__int64 __fastcall(DataPackageCloner *__hidden this, struct Windows::Foundation::IPropertyValue *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180076aac`

## callees

- `0x180048954`
- `0x180077488`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007753d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007757e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800775d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077609`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077678`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007753d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007757e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800775d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077609`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077678`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180077546`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180077636`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180077546`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180077636`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800775a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800775a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataPackageCloner::ClonePropValue(
        DataPackageCloner *this,
        struct Windows::Foundation::IPropertyValue *a2,
        const struct _GUID *a3,
        void **a4)
{
  signed int v8; // ebx
  __int64 v9; // rdx
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // rbx
  unsigned int v12; // r14d
  HSTRING v13; // rdi
  UINT32 StringLen; // eax
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rax
  __int64 v17; // rdx
  HSTRING v18; // rcx
  __int64 (__fastcall *v19)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  int v20; // eax
  __int64 v21; // r9
  __int64 v22; // rdx
  UINT32 v23; // eax
  unsigned __int64 v24; // rdx
  LPVOID pv[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  int v28; // [rsp+78h] [rbp+48h] BYREF
  HSTRING string; // [rsp+88h] [rbp+58h] BYREF

  *a4 = 0;
  v28 = 0;
  v8 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, int *))(*(_QWORD *)a2 + 48LL))(a2, &v28);
  if ( v8 < 0 )
  {
    v9 = 477;
    goto LABEL_35;
  }
  if ( v28 != 12 )
  {
    LODWORD(v10) = 0;
    if ( v28 == 1036 )
    {
      pv[0] = 0;
      LODWORD(string) = 0;
      v8 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *, LPVOID *))(*(_QWORD *)a2 + 296LL))(
             a2,
             &string,
             pv);
      if ( v8 < 0 )
      {
        v9 = 494;
        goto LABEL_35;
      }
      LODWORD(v11) = 0;
      v12 = 0;
      if ( (_DWORD)string )
      {
        while ( 1 )
        {
          v13 = (HSTRING)*((_QWORD *)pv[0] + v12);
          WindowsDeleteString(0);
          StringLen = WindowsGetStringLen(v13);
          if ( !is_mul_ok(2u, StringLen + 1) )
            break;
          v15 = 2 * (StringLen + 1) + (unsigned int)v11;
          if ( (unsigned int)v15 < (unsigned int)v11 )
          {
            v17 = 504;
            goto LABEL_17;
          }
          v11 = v15 + 2;
          if ( v15 + 2 < v15 || v11 > 0xFFFFFFFF )
          {
            v17 = 506;
            goto LABEL_17;
          }
          WindowsDeleteString(v13);
          if ( ++v12 >= (unsigned int)string )
            goto LABEL_13;
        }
        v17 = 503;
LABEL_17:
        v8 = -2147024362;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
          (const char *)0x80070216LL,
          (int)pv[0]);
        v18 = v13;
        goto LABEL_18;
      }
LABEL_13:
      v16 = (unsigned int)v11;
      v10 = (unsigned int)v11 + 2LL;
      if ( v10 < v16 || v10 > 0xFFFFFFFF )
      {
        v8 = -2147024362;
        v9 = 510;
        goto LABEL_35;
      }
      CoTaskMemFree(pv[0]);
    }
LABEL_28:
    v24 = *((_QWORD *)this + 3) + (unsigned int)v10;
    if ( v24 < *((_QWORD *)this + 3) )
    {
      v8 = -2147024882;
    }
    else
    {
      *((_QWORD *)this + 3) = v24;
      v8 = *((_QWORD *)this + 4) < v24 ? 0x8007000E : 0;
      if ( v24 <= *((_QWORD *)this + 4) )
      {
        v8 = (**(__int64 (__fastcall ***)(struct Windows::Foundation::IPropertyValue *, const struct _GUID *, void **))a2)(
               a2,
               a3,
               a4);
        if ( v8 >= 0 )
          return 0;
        v9 = 520;
        goto LABEL_35;
      }
    }
    v9 = 519;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v8,
      (int)pv[0]);
    return (unsigned int)v8;
  }
  string = 0;
  v19 = *(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)a2 + 152LL);
  WindowsDeleteString(0);
  string = 0;
  v20 = v19(a2, &string);
  v8 = v20;
  if ( v20 >= 0 )
  {
    v23 = WindowsGetStringLen(string);
    LODWORD(v10) = 2 * (v23 + 1);
    if ( is_mul_ok(2u, v23 + 1) )
    {
      WindowsDeleteString(string);
      goto LABEL_28;
    }
    v8 = -2147024362;
    v21 = 2147942934LL;
    v22 = 487;
  }
  else
  {
    v21 = (unsigned int)v20;
    v22 = 485;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v22,
    (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
    (const char *)v21,
    (int)pv[0]);
  v18 = string;
LABEL_18:
  WindowsDeleteString(v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180077488  mov     [rsp-38h+arg_0], rbx
0x18007748d  push    rbp
0x18007748e  push    rsi
0x18007748f  push    rdi
0x180077490  push    r12
0x180077492  push    r13
0x180077494  push    r14
0x180077496  push    r15
0x180077498  mov     rbp, rsp
0x18007749b  sub     rsp, 30h
0x18007749f  mov     r12, r9
0x1800774a2  mov     r13, r8
0x1800774a5  mov     rsi, rdx
0x1800774a8  mov     r15, rcx
0x1800774ab  xor     edi, edi
0x1800774ad  mov     [r9], rdi
0x1800774b0  mov     [rbp+arg_8], edi
0x1800774b3  mov     rax, [rdx]
0x1800774b6  lea     rdx, [rbp+arg_8]
0x1800774ba  mov     rcx, rsi
0x1800774bd  mov     rax, [rax+30h]
0x1800774c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800774c6  mov     ebx, eax
0x1800774c8  test    eax, eax
0x1800774ca  jns     short loc_1800774D6
0x1800774cc  mov     edx, 1DDh
0x1800774d1  jmp     loc_1800776CF
0x1800774d6  cmp     [rbp+arg_8], 0Ch
0x1800774da  jz      loc_1800775F9
0x1800774e0  mov     rbx, rdi
0x1800774e3  cmp     [rbp+arg_8], 40Ch
0x1800774ea  jnz     loc_18007767E
0x1800774f0  mov     [rbp+pv], rdi
0x1800774f4  mov     dword ptr [rbp+string], edi
0x1800774f7  mov     rax, [rsi]
0x1800774fa  lea     r8, [rbp+pv]
0x1800774fe  lea     rdx, [rbp+string]
0x180077502  mov     rcx, rsi
0x180077505  mov     rax, [rax+128h]
0x18007750c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077511  mov     ebx, eax
0x180077513  test    eax, eax
0x180077515  jns     short loc_180077521
0x180077517  mov     edx, 1EEh
0x18007751c  jmp     loc_1800776CF
0x180077521  mov     ebx, edi
0x180077523  mov     r14d, edi
0x180077526  mov     ecx, 0FFFFFFFFh
0x18007752b  cmp     dword ptr [rbp+string], edi
0x18007752e  jbe     short loc_180077592
0x180077530  mov     ecx, r14d
0x180077533  mov     rax, [rbp+pv]
0x180077537  mov     rdi, [rax+rcx*8]
0x18007753b  xor     ecx, ecx; string
0x18007753d  call    cs:__imp_WindowsDeleteString
0x180077543  mov     rcx, rdi; string
0x180077546  call    cs:__imp_WindowsGetStringLen
0x18007754c  lea     ecx, [rax+1]
0x18007754f  add     rcx, rcx
0x180077552  mov     rax, rcx
0x180077555  shr     rax, 20h
0x180077559  test    eax, eax
0x18007755b  jnz     loc_1800775E3
0x180077561  lea     eax, [rcx+rbx]
0x180077564  cmp     eax, ebx
0x180077566  jb      short loc_1800775DC
0x180077568  lea     rbx, [rax+2]
0x18007756c  cmp     rbx, rax
0x18007756f  jb      short loc_1800775B1
0x180077571  mov     eax, 0FFFFFFFFh
0x180077576  cmp     rbx, rax
0x180077579  ja      short loc_1800775B1
0x18007757b  mov     rcx, rdi; string
0x18007757e  call    cs:__imp_WindowsDeleteString
0x180077584  inc     r14d
0x180077587  cmp     r14d, dword ptr [rbp+string]
0x18007758b  jb      short loc_180077530
0x18007758d  mov     ecx, 0FFFFFFFFh
0x180077592  mov     eax, ebx
0x180077594  lea     rbx, [rax+2]
0x180077598  cmp     rbx, rax
0x18007759b  jb      short loc_1800775EA
0x18007759d  cmp     rbx, rcx
0x1800775a0  ja      short loc_1800775EA
0x1800775a2  mov     rcx, [rbp+pv]; pv
0x1800775a6  call    cs:__imp_CoTaskMemFree
0x1800775ac  jmp     loc_18007767E
0x1800775b1  mov     edx, 1FAh; void *
0x1800775b6  mov     ebx, 80070216h
0x1800775bb  mov     rcx, [rbp+38h]; this
0x1800775bf  mov     r9d, ebx; char *
0x1800775c2  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x1800775c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800775ce  mov     rcx, rdi; string
0x1800775d1  call    cs:__imp_WindowsDeleteString
0x1800775d7  jmp     loc_1800776E2
0x1800775dc  mov     edx, 1F8h
0x1800775e1  jmp     short loc_1800775B6
0x1800775e3  mov     edx, 1F7h
0x1800775e8  jmp     short loc_1800775B6
0x1800775ea  mov     ebx, 80070216h
0x1800775ef  mov     edx, 1FEh
0x1800775f4  jmp     loc_1800776CF
0x1800775f9  mov     [rbp+string], rdi
0x1800775fd  mov     rax, [rsi]
0x180077600  mov     rbx, [rax+98h]
0x180077607  xor     ecx, ecx; string
0x180077609  call    cs:__imp_WindowsDeleteString
0x18007760f  mov     [rbp+string], rdi
0x180077613  lea     rdx, [rbp+string]
0x180077617  mov     rcx, rsi
0x18007761a  mov     rax, rbx
0x18007761d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077622  mov     ebx, eax
0x180077624  test    eax, eax
0x180077626  jns     short loc_180077632
0x180077628  mov     r9d, eax
0x18007762b  mov     edx, 1E5h
0x180077630  jmp     short loc_18007765A
0x180077632  mov     rcx, [rbp+string]; string
0x180077636  call    cs:__imp_WindowsGetStringLen
0x18007763c  lea     ebx, [rax+1]
0x18007763f  add     rbx, rbx
0x180077642  mov     rax, rbx
0x180077645  shr     rax, 20h
0x180077649  test    eax, eax
0x18007764b  jz      short loc_180077674
0x18007764d  mov     ebx, 80070216h
0x180077652  mov     r9d, ebx; char *
0x180077655  mov     edx, 1E7h; void *
0x18007765a  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180077661  mov     rcx, [rbp+38h]; this
0x180077665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007766a  nop
0x18007766b  mov     rcx, [rbp+string]
0x18007766f  jmp     loc_1800775D1
0x180077674  mov     rcx, [rbp+string]; string
0x180077678  call    cs:__imp_WindowsDeleteString
0x18007767e  mov     edx, ebx
0x180077680  add     rdx, [r15+18h]
0x180077684  cmp     rdx, [r15+18h]
0x180077688  jb      short loc_1800776C5
0x18007768a  mov     [r15+18h], rdx
0x18007768e  cmp     [r15+20h], rdx
0x180077692  sbb     ebx, ebx
0x180077694  and     ebx, 8007000Eh
0x18007769a  cmp     rdx, [r15+20h]
0x18007769e  ja      short loc_1800776CA
0x1800776a0  mov     rax, [rsi]
0x1800776a3  mov     r8, r12
0x1800776a6  mov     rdx, r13
0x1800776a9  mov     rcx, rsi
0x1800776ac  mov     rax, [rax]
0x1800776af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800776b4  mov     ebx, eax
0x1800776b6  test    eax, eax
0x1800776b8  jns     short loc_1800776C1
0x1800776ba  mov     edx, 208h
0x1800776bf  jmp     short loc_1800776CF
0x1800776c1  xor     eax, eax
0x1800776c3  jmp     short loc_1800776E4
0x1800776c5  mov     ebx, 8007000Eh
0x1800776ca  mov     edx, 207h; void *
0x1800776cf  mov     r9d, ebx; char *
0x1800776d2  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x1800776d9  mov     rcx, [rbp+38h]; this
0x1800776dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800776e2  mov     eax, ebx
0x1800776e4  mov     rbx, [rsp+30h+arg_0]
0x1800776e9  add     rsp, 30h
0x1800776ed  pop     r15
0x1800776ef  pop     r14
0x1800776f1  pop     r13
0x1800776f3  pop     r12
0x1800776f5  pop     rdi
0x1800776f6  pop     rsi
0x1800776f7  pop     rbp
0x1800776f8  retn
```
