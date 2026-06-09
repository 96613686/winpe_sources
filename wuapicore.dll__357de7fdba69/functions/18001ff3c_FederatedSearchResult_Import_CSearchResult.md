# FederatedSearchResult::Import(CSearchResult *)

- ea: `0x18001ff3c`
- end: `0x180020387`
- name: `?Import@FederatedSearchResult@@QEAAJPEAVCSearchResult@@@Z`
- size: `1099`
- prototype: `__int64 __fastcall(FederatedSearchResult *__hidden this, struct CSearchResult *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d890`

## callees

- `0x180006ac4`
- `0x18001ff3c`
- `0x180066750`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800200fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800201ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800202af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800202c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020363`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800200fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800201ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800202af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800202c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020363`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ff81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020008`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800201d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ff81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020008`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800201d6`

## string_xrefs

- `0x180020375`: `C:\__w\1\s\src\Client\comapi\FederatedSearchResult.cpp`
- `0x18001ffce`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x18002004f`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x18002011e`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x18002013b`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x180020173`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x180020216`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x1800202f3`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x18002032b`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall FederatedSearchResult::Import(FederatedSearchResult *this, struct CSearchResult *a2)
{
  char *v3; // rsi
  unsigned __int64 v4; // rbx
  int v5; // edi
  __int64 v6; // rdx
  struct CSearchResult *v7; // rdi
  __int64 v8; // r12
  char *v9; // rax
  char *v10; // r14
  __int64 v11; // r15
  int v12; // eax
  struct _RTL_CRITICAL_SECTION *v13; // rcx
  unsigned int v14; // r15d
  int v15; // eax
  int v16; // eax
  struct CSearchResult *v17; // rdi
  char *v18; // r14
  struct _RTL_CRITICAL_SECTION *v19; // r15
  int v20; // eax
  struct _RTL_CRITICAL_SECTION *v21; // rcx
  unsigned int v22; // esi
  int v23; // eax
  int v24; // eax
  int v26; // [rsp+20h] [rbp-40h]
  struct CSearchResult *v27; // [rsp+20h] [rbp-40h]
  struct CSearchResult *v28; // [rsp+20h] [rbp-40h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+28h] [rbp-38h]
  struct CSearchResult *v30; // [rsp+40h] [rbp-20h] BYREF
  int v31; // [rsp+48h] [rbp-18h] BYREF
  struct IUpdateException *v32; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v30 = a2;
  v3 = (char *)this + 232;
  v4 = ((unsigned __int64)this + 232) & -(__int64)(this != 0);
  if ( v4 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  v5 = (*(__int64 (__fastcall **)(char *, struct CSearchResult **, _QWORD))(*((_QWORD *)this + 64) + 8LL))(
         (char *)this + 512,
         &v30,
         0);
  if ( v5 < 0 )
  {
    v6 = 27;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\FederatedSearchResult.cpp",
      (const char *)(unsigned int)v5,
      v26);
    goto LABEL_51;
  }
  v7 = v30;
  v27 = v30;
  if ( !v30 )
  {
    v5 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x628,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
      (const char *)0x80004003LL,
      0);
LABEL_33:
    v6 = 28;
    goto LABEL_63;
  }
  v31 = 0;
  v8 = 8;
  if ( this )
  {
    v9 = v3;
    v10 = v3;
    if ( v3 )
    {
      v11 = (__int64)(v3 + 8);
      EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
      lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)(v3 + 8);
      goto LABEL_12;
    }
  }
  else
  {
    v10 = 0;
    v9 = 0;
  }
  v11 = 8;
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)(v9 + 8);
LABEL_12:
  v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)(*((_QWORD *)v7 + 44) + 24LL) + 80LL))(
          *((_QWORD *)v7 + 44) + 24LL,
          &v31);
  v5 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
      (const char *)(unsigned int)v12,
      (int)v27);
    if ( !v10 )
      goto LABEL_33;
    v13 = (struct _RTL_CRITICAL_SECTION *)v11;
LABEL_32:
    LeaveCriticalSection(v13);
    goto LABEL_33;
  }
  v14 = 0;
  if ( v31 > 0 )
  {
    while ( 1 )
    {
      v32 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IUpdateException **))(*(_QWORD *)(*((_QWORD *)v27 + 44)
                                                                                               + 24LL)
                                                                                   + 56LL))(
              *((_QWORD *)v27 + 44) + 24LL,
              v14,
              &v32);
      v5 = v15;
      if ( v15 < 0 )
        break;
      v16 = (*(__int64 (__fastcall **)(__int64, struct IUpdateException *, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 44)
                                                                                              + 24LL)
                                                                                  + 96LL))(
              *((_QWORD *)this + 44) + 24LL,
              v32,
              0);
      v5 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x637,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
          (const char *)(unsigned int)v16,
          (int)v27);
        if ( v32 )
        {
          ((void (__fastcall *)(struct IUpdateException *))v32->lpVtbl->Release)(v32);
          v32 = 0;
        }
        goto LABEL_30;
      }
      if ( v32 )
        ((void (__fastcall *)(struct IUpdateException *))v32->lpVtbl->Release)(v32);
      if ( (int)++v14 >= v31 )
        goto LABEL_21;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x634,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
      (const char *)(unsigned int)v15,
      (int)v27);
    if ( v32 )
    {
      ((void (__fastcall *)(struct IUpdateException *))v32->lpVtbl->Release)(v32);
      v32 = 0;
    }
LABEL_30:
    if ( !v10 )
      goto LABEL_33;
    v13 = (struct _RTL_CRITICAL_SECTION *)(v10 + 8);
    goto LABEL_32;
  }
LABEL_21:
  if ( v10 )
    LeaveCriticalSection(lpCriticalSection);
  v17 = v30;
  v28 = v30;
  if ( !v30 )
  {
    v5 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x643,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
      (const char *)0x80004003LL,
      0);
LABEL_62:
    v6 = 29;
    goto LABEL_63;
  }
  v31 = 0;
  if ( this )
  {
    v18 = v3;
    if ( v3 )
    {
      v8 = (__int64)(v3 + 8);
      EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
      v19 = (struct _RTL_CRITICAL_SECTION *)(v3 + 8);
      goto LABEL_39;
    }
  }
  else
  {
    v18 = 0;
    v3 = 0;
  }
  v19 = (struct _RTL_CRITICAL_SECTION *)(v3 + 8);
LABEL_39:
  v20 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)(*((_QWORD *)v17 + 39) + 8LL) + 72LL))(
          *((_QWORD *)v17 + 39) + 8LL,
          &v31);
  v5 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x649,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
      (const char *)(unsigned int)v20,
      (int)v28);
    if ( !v18 )
      goto LABEL_62;
    v21 = (struct _RTL_CRITICAL_SECTION *)v8;
LABEL_61:
    LeaveCriticalSection(v21);
    goto LABEL_62;
  }
  v22 = 0;
  if ( v31 > 0 )
  {
    while ( 1 )
    {
      v32 = 0;
      v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IUpdateException **))(*(_QWORD *)(*((_QWORD *)v28 + 39)
                                                                                               + 8LL)
                                                                                   + 56LL))(
              *((_QWORD *)v28 + 39) + 8LL,
              v22,
              &v32);
      v5 = v23;
      if ( v23 < 0 )
        break;
      v24 = CUpdateExceptionCollection::AddInner(*((CUpdateExceptionCollection **)this + 39), v32);
      v5 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x652,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
          (const char *)(unsigned int)v24,
          (int)v28);
        if ( v32 )
        {
          ((void (__fastcall *)(struct IUpdateException *))v32->lpVtbl->Release)(v32);
          v32 = 0;
        }
        goto LABEL_59;
      }
      if ( v32 )
        ((void (__fastcall *)(struct IUpdateException *))v32->lpVtbl->Release)(v32);
      if ( (int)++v22 >= v31 )
        goto LABEL_48;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64F,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
      (const char *)(unsigned int)v23,
      (int)v28);
    if ( v32 )
    {
      ((void (__fastcall *)(struct IUpdateException *))v32->lpVtbl->Release)(v32);
      v32 = 0;
    }
LABEL_59:
    if ( !v18 )
      goto LABEL_62;
    v21 = (struct _RTL_CRITICAL_SECTION *)(v18 + 8);
    goto LABEL_61;
  }
LABEL_48:
  if ( v18 )
    LeaveCriticalSection(v19);
  v5 = 0;
LABEL_51:
  if ( v4 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001ff3c  mov     [rsp-38h+arg_10], rbx
0x18001ff41  push    rbp
0x18001ff42  push    rsi
0x18001ff43  push    rdi
0x18001ff44  push    r12
0x18001ff46  push    r13
0x18001ff48  push    r14
0x18001ff4a  push    r15
0x18001ff4c  mov     rbp, rsp
0x18001ff4f  sub     rsp, 60h
0x18001ff53  mov     rax, cs:__security_cookie
0x18001ff5a  xor     rax, rsp
0x18001ff5d  mov     [rbp+var_8], rax
0x18001ff61  mov     r13, rcx
0x18001ff64  mov     [rbp+var_20], rdx
0x18001ff68  lea     rsi, [rcx+0E8h]
0x18001ff6f  mov     rax, rcx
0x18001ff72  neg     rax
0x18001ff75  sbb     rbx, rbx
0x18001ff78  and     rbx, rsi
0x18001ff7b  jz      short loc_18001FF87
0x18001ff7d  lea     rcx, [rbx+8]; lpCriticalSection
0x18001ff81  call    cs:__imp_EnterCriticalSection
0x18001ff87  mov     [rbp+var_28], rbx
0x18001ff8b  lea     rcx, [r13+200h]
0x18001ff92  mov     rax, [rcx]
0x18001ff95  xor     r8d, r8d
0x18001ff98  lea     rdx, [rbp+var_20]
0x18001ff9c  mov     rax, [rax+8]
0x18001ffa0  call    _guard_dispatch_icall
0x18001ffa5  mov     edi, eax
0x18001ffa7  test    eax, eax
0x18001ffa9  jns     short loc_18001FFB5
0x18001ffab  mov     edx, 1Bh
0x18001ffb0  jmp     loc_18002036E
0x18001ffb5  mov     rdi, [rbp+var_20]
0x18001ffb9  mov     [rbp+var_40], rdi
0x18001ffbd  test    rdi, rdi
0x18001ffc0  jnz     short loc_18001FFE4
0x18001ffc2  mov     rcx, [rbp+38h]; this
0x18001ffc6  mov     edi, 80004003h
0x18001ffcb  mov     r9d, edi; char *
0x18001ffce  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x18001ffd5  mov     edx, 628h; void *
0x18001ffda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ffdf  jmp     loc_1800201B1
0x18001ffe4  mov     [rbp+var_18], 0
0x18001ffeb  mov     r12d, 8
0x18001fff1  test    r13, r13
0x18001fff4  jz      short loc_180020014
0x18001fff6  mov     rax, rsi
0x18001fff9  mov     r14, rsi
0x18001fffc  test    rsi, rsi
0x18001ffff  jz      short loc_180020019
0x180020001  lea     r15, [rsi+8]
0x180020005  mov     rcx, r15; lpCriticalSection
0x180020008  call    cs:__imp_EnterCriticalSection
0x18002000e  mov     [rbp+lpCriticalSection], r15
0x180020012  jmp     short loc_180020023
0x180020014  xor     r14d, r14d
0x180020017  xor     eax, eax
0x180020019  mov     r15, r12
0x18002001c  add     rax, r12
0x18002001f  mov     [rbp+lpCriticalSection], rax
0x180020023  mov     [rbp+var_30], r14
0x180020027  mov     rcx, [rdi+160h]
0x18002002e  add     rcx, 18h
0x180020032  mov     rax, [rcx]
0x180020035  lea     rdx, [rbp+var_18]
0x180020039  mov     rax, [rax+50h]
0x18002003d  call    _guard_dispatch_icall
0x180020042  mov     edi, eax
0x180020044  test    eax, eax
0x180020046  jns     short loc_180020072
0x180020048  mov     rcx, [rbp+38h]; this
0x18002004c  mov     r9d, eax; char *
0x18002004f  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x180020056  mov     edx, 62Eh; void *
0x18002005b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020060  nop
0x180020061  test    r14, r14
0x180020064  jz      loc_1800201B1
0x18002006a  mov     rcx, r15
0x18002006d  jmp     loc_1800201AB
0x180020072  xor     r15d, r15d
0x180020075  cmp     [rbp+var_18], r15d
0x180020079  jle     short loc_1800200F2
0x18002007b  mov     [rbp+var_10], 0
0x180020083  mov     rax, [rbp+var_40]
0x180020087  mov     rcx, [rax+160h]
0x18002008e  add     rcx, 18h
0x180020092  mov     rax, [rcx]
0x180020095  lea     r8, [rbp+var_10]
0x180020099  mov     edx, r15d
0x18002009c  mov     rax, [rax+38h]
0x1800200a0  call    _guard_dispatch_icall
0x1800200a5  mov     edi, eax
0x1800200a7  test    eax, eax
0x1800200a9  js      loc_18002016C
0x1800200af  mov     rcx, [r13+160h]
0x1800200b6  add     rcx, 18h
0x1800200ba  mov     rax, [rcx]
0x1800200bd  xor     r8d, r8d
0x1800200c0  mov     rdx, [rbp+var_10]
0x1800200c4  mov     rax, [rax+60h]
0x1800200c8  call    _guard_dispatch_icall
0x1800200cd  mov     edi, eax
0x1800200cf  test    eax, eax
0x1800200d1  js      short loc_180020134
0x1800200d3  mov     rcx, [rbp+var_10]
0x1800200d7  test    rcx, rcx
0x1800200da  jz      short loc_1800200E9
0x1800200dc  mov     rax, [rcx]
0x1800200df  mov     rax, [rax+10h]
0x1800200e3  call    _guard_dispatch_icall
0x1800200e8  nop
0x1800200e9  inc     r15d
0x1800200ec  cmp     r15d, [rbp+var_18]
0x1800200f0  jl      short loc_18002007B
0x1800200f2  test    r14, r14
0x1800200f5  jz      short loc_180020101
0x1800200f7  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800200fb  call    cs:__imp_LeaveCriticalSection
0x180020101  mov     rdi, [rbp+var_20]
0x180020105  mov     [rbp+var_40], rdi
0x180020109  test    rdi, rdi
0x18002010c  jnz     loc_1800201BB
0x180020112  mov     rcx, [rbp+38h]; this
0x180020116  mov     edi, 80004003h
0x18002011b  mov     r9d, edi; char *
0x18002011e  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x180020125  mov     edx, 643h; void *
0x18002012a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002012f  jmp     loc_180020369
0x180020134  mov     rcx, [rbp+38h]; this
0x180020138  mov     r9d, eax; char *
0x18002013b  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x180020142  mov     edx, 637h; void *
0x180020147  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002014c  nop
0x18002014d  mov     rcx, [rbp+var_10]
0x180020151  test    rcx, rcx
0x180020154  jz      short loc_18002016A
0x180020156  mov     rax, [rcx]
0x180020159  mov     rax, [rax+10h]
0x18002015d  call    _guard_dispatch_icall
0x180020162  mov     [rbp+var_10], 0
0x18002016a  jmp     short loc_1800201A2
0x18002016c  mov     rcx, [rbp+38h]; this
0x180020170  mov     r9d, eax; char *
0x180020173  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x18002017a  mov     edx, 634h; void *
0x18002017f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020184  nop
0x180020185  mov     rcx, [rbp+var_10]
0x180020189  test    rcx, rcx
0x18002018c  jz      short loc_1800201A2
0x18002018e  mov     rax, [rcx]
0x180020191  mov     rax, [rax+10h]
0x180020195  call    _guard_dispatch_icall
0x18002019a  mov     [rbp+var_10], 0
0x1800201a2  test    r14, r14
0x1800201a5  jz      short loc_1800201B1
0x1800201a7  lea     rcx, [r14+8]; lpCriticalSection
0x1800201ab  call    cs:__imp_LeaveCriticalSection
0x1800201b1  mov     edx, 1Ch
0x1800201b6  jmp     loc_18002036E
0x1800201bb  mov     [rbp+var_18], 0
0x1800201c2  test    r13, r13
0x1800201c5  jz      short loc_1800201E1
0x1800201c7  mov     r14, rsi
0x1800201ca  test    rsi, rsi
0x1800201cd  jz      short loc_1800201E6
0x1800201cf  lea     r12, [rsi+8]
0x1800201d3  mov     rcx, r12; lpCriticalSection
0x1800201d6  call    cs:__imp_EnterCriticalSection
0x1800201dc  mov     r15, r12
0x1800201df  jmp     short loc_1800201EA
0x1800201e1  xor     r14d, r14d
0x1800201e4  xor     esi, esi
0x1800201e6  lea     r15, [rsi+8]
0x1800201ea  mov     [rbp+var_30], r14
0x1800201ee  mov     rcx, [rdi+138h]
0x1800201f5  add     rcx, 8
0x1800201f9  mov     rax, [rcx]
0x1800201fc  lea     rdx, [rbp+var_18]
0x180020200  mov     rax, [rax+48h]
0x180020204  call    _guard_dispatch_icall
0x180020209  mov     edi, eax
0x18002020b  test    eax, eax
0x18002020d  jns     short loc_180020239
0x18002020f  mov     rcx, [rbp+38h]; this
0x180020213  mov     r9d, eax; char *
0x180020216  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x18002021d  mov     edx, 649h; void *
0x180020222  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020227  nop
0x180020228  test    r14, r14
0x18002022b  jz      loc_180020369
0x180020231  mov     rcx, r12
0x180020234  jmp     loc_180020363
0x180020239  xor     esi, esi
0x18002023b  cmp     [rbp+var_18], esi
0x18002023e  jle     short loc_1800202A7
0x180020240  mov     r12, [rbp+var_40]
0x180020244  mov     [rbp+var_10], 0
0x18002024c  mov     rcx, [r12+138h]
0x180020254  add     rcx, 8
0x180020258  mov     rax, [rcx]
0x18002025b  lea     r8, [rbp+var_10]
0x18002025f  mov     edx, esi
0x180020261  mov     rax, [rax+38h]
0x180020265  call    _guard_dispatch_icall
0x18002026a  mov     edi, eax
0x18002026c  test    eax, eax
0x18002026e  js      loc_180020324
0x180020274  mov     rdx, [rbp+var_10]; struct IUpdateException *
0x180020278  mov     rcx, [r13+138h]; this
0x18002027f  call    ?AddInner@CUpdateExceptionCollection@@QEAAJPEAUIUpdateException@@@Z; CUpdateExceptionCollection::AddInner(IUpdateException *)
0x180020284  mov     edi, eax
0x180020286  test    eax, eax
0x180020288  js      short loc_1800202EC
0x18002028a  mov     rcx, [rbp+var_10]
0x18002028e  test    rcx, rcx
0x180020291  jz      short loc_1800202A0
0x180020293  mov     rax, [rcx]
0x180020296  mov     rax, [rax+10h]
0x18002029a  call    _guard_dispatch_icall
0x18002029f  nop
0x1800202a0  inc     esi
0x1800202a2  cmp     esi, [rbp+var_18]
0x1800202a5  jl      short loc_180020244
0x1800202a7  test    r14, r14
0x1800202aa  jz      short loc_1800202B5
0x1800202ac  mov     rcx, r15; lpCriticalSection
0x1800202af  call    cs:__imp_LeaveCriticalSection
0x1800202b5  xor     edi, edi
0x1800202b7  test    rbx, rbx
0x1800202ba  jz      short loc_1800202C6
0x1800202bc  lea     rcx, [rbx+8]; lpCriticalSection
0x1800202c0  call    cs:__imp_LeaveCriticalSection
0x1800202c6  mov     eax, edi
0x1800202c8  mov     rcx, [rbp+var_8]
0x1800202cc  xor     rcx, rsp; StackCookie
0x1800202cf  call    __security_check_cookie
0x1800202d4  mov     rbx, [rsp+60h+arg_10]
0x1800202dc  add     rsp, 60h
0x1800202e0  pop     r15
0x1800202e2  pop     r14
0x1800202e4  pop     r13
0x1800202e6  pop     r12
0x1800202e8  pop     rdi
0x1800202e9  pop     rsi
0x1800202ea  pop     rbp
0x1800202eb  retn
0x1800202ec  mov     rcx, [rbp+38h]; this
0x1800202f0  mov     r9d, eax; char *
0x1800202f3  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x1800202fa  mov     edx, 652h; void *
0x1800202ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020304  nop
0x180020305  mov     rcx, [rbp+var_10]
0x180020309  test    rcx, rcx
0x18002030c  jz      short loc_180020322
0x18002030e  mov     rax, [rcx]
0x180020311  mov     rax, [rax+10h]
0x180020315  call    _guard_dispatch_icall
0x18002031a  mov     [rbp+var_10], 0
0x180020322  jmp     short loc_18002035A
0x180020324  mov     rcx, [rbp+38h]; this
0x180020328  mov     r9d, eax; char *
0x18002032b  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x180020332  mov     edx, 64Fh; void *
0x180020337  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002033c  nop
0x18002033d  mov     rcx, [rbp+var_10]
0x180020341  test    rcx, rcx
0x180020344  jz      short loc_18002035A
0x180020346  mov     rax, [rcx]
0x180020349  mov     rax, [rax+10h]
0x18002034d  call    _guard_dispatch_icall
0x180020352  mov     [rbp+var_10], 0
0x18002035a  test    r14, r14
0x18002035d  jz      short loc_180020369
0x18002035f  lea     rcx, [r14+8]; lpCriticalSection
0x180020363  call    cs:__imp_LeaveCriticalSection
0x180020369  mov     edx, 1Dh; void *
0x18002036e  mov     rcx, [rbp+38h]; this
0x180020372  mov     r9d, edi; char *
0x180020375  lea     r8, aCW1SSrcClientC_70; "C:\\__w\\1\\s\\src\\Client\\comapi\\Fed"...
0x18002037c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020381  jmp     loc_1800202B7
```
