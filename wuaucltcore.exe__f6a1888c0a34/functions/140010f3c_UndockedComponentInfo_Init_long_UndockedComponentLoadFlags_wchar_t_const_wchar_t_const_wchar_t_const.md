# UndockedComponentInfo::Init(long,UndockedComponentLoadFlags,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x140010f3c`
- end: `0x1400110a5`
- name: `?Init@UndockedComponentInfo@@QEAAJJW4UndockedComponentLoadFlags@@PEB_W11@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400074c8`

## callees

- `0x140002ac0`
- `0x14000ce5c`
- `0x14000d4cc`
- `0x140010f3c`
- `0x140014bd0`
- `0x1400150cc`
- `0x14001aa60`

## pseudocode

```c
__int64 __fastcall UndockedComponentInfo::Init(__int64 a1, int a2, int a3, __int64 a4, _WORD *a5, __int64 a6)
{
  _QWORD *v6; // rdi
  void *v9; // rcx
  int v10; // edi
  __int64 v11; // rdx
  void *v13; // rcx
  void *v14; // rcx
  int FileVersion; // ebx
  __int64 v16; // rdx
  void *v17; // rcx
  unsigned __int64 v18; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v6 = (_QWORD *)(a1 + 8);
  *(_DWORD *)a1 = a2;
  *(_DWORD *)(a1 + 4) = a3;
  v9 = *(void **)(a1 + 8);
  if ( v9 )
  {
    SusFree(v9);
    *v6 = 0;
  }
  v10 = DuplicateOptionalString<wchar_t const *,wchar_t *>(a4, v6);
  if ( v10 < 0 )
  {
    v11 = 15;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\UndockingTelemetry\\UndockingTelemetry.cpp",
      (const char *)(unsigned int)v10,
      v18);
    return (unsigned int)v10;
  }
  v13 = *(void **)(a1 + 16);
  if ( v13 )
  {
    SusFree(v13);
    *(_QWORD *)(a1 + 16) = 0;
  }
  v10 = DuplicateOptionalString<wchar_t const *,wchar_t *>(a5, a1 + 16);
  if ( v10 < 0 )
  {
    v11 = 17;
    goto LABEL_5;
  }
  v14 = *(void **)(a1 + 32);
  if ( v14 )
  {
    SusFree(v14);
    *(_QWORD *)(a1 + 32) = 0;
  }
  v10 = DuplicateOptionalString<wchar_t const *,wchar_t *>(a6, a1 + 32);
  if ( v10 < 0 )
  {
    v11 = 19;
    goto LABEL_5;
  }
  if ( a5 && *a5 )
  {
    v18 = 0;
    FileVersion = GetFileVersion(a5, &v18);
    if ( FileVersion < 0 )
    {
      v16 = 24;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\UndockingTelemetry\\UndockingTelemetry.cpp",
        (const char *)(unsigned int)FileVersion,
        v18);
      return (unsigned int)FileVersion;
    }
    v17 = *(void **)(a1 + 24);
    if ( v17 )
    {
      SusFree(v17);
      *(_QWORD *)(a1 + 24) = 0;
    }
    FileVersion = ConvertFileVerToStringW(v18, (wchar_t **)(a1 + 24));
    if ( FileVersion < 0 )
    {
      v16 = 25;
      goto LABEL_18;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140010f3c  mov     [rsp+arg_8], rbx
0x140010f41  push    rbp
0x140010f42  push    rsi
0x140010f43  push    rdi
0x140010f44  push    r14
0x140010f46  push    r15
0x140010f48  sub     rsp, 30h
0x140010f4c  mov     rax, cs:__security_cookie
0x140010f53  xor     rax, rsp
0x140010f56  mov     [rsp+58h+var_30], rax
0x140010f5b  mov     rbx, [rsp+58h+arg_20]
0x140010f63  lea     rdi, [rcx+8]
0x140010f67  mov     r14, [rsp+58h+arg_28]
0x140010f6f  mov     rsi, rcx
0x140010f72  mov     [rcx], edx
0x140010f74  xor     r15d, r15d
0x140010f77  mov     [rcx+4], r8d
0x140010f7b  mov     rbp, r9
0x140010f7e  mov     rcx, [rdi]; lpMem
0x140010f81  test    rcx, rcx
0x140010f84  jz      short loc_140010F8E
0x140010f86  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140010f8b  mov     [rdi], r15
0x140010f8e  mov     rdx, rdi
0x140010f91  mov     rcx, rbp
0x140010f94  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x140010f99  mov     edi, eax
0x140010f9b  test    eax, eax
0x140010f9d  jns     short loc_140010FBF
0x140010f9f  mov     edx, 0Fh; void *
0x140010fa4  mov     rcx, [rsp+58h]; this
0x140010fa9  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x140010fb0  mov     r9d, edi; char *
0x140010fb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010fb8  mov     eax, edi
0x140010fba  jmp     loc_140011087
0x140010fbf  lea     rdi, [rsi+10h]
0x140010fc3  mov     rcx, [rdi]; lpMem
0x140010fc6  test    rcx, rcx
0x140010fc9  jz      short loc_140010FD3
0x140010fcb  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140010fd0  mov     [rdi], r15
0x140010fd3  mov     rdx, rdi
0x140010fd6  mov     rcx, rbx
0x140010fd9  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x140010fde  mov     edi, eax
0x140010fe0  test    eax, eax
0x140010fe2  jns     short loc_140010FEB
0x140010fe4  mov     edx, 11h
0x140010fe9  jmp     short loc_140010FA4
0x140010feb  lea     rdi, [rsi+20h]
0x140010fef  mov     rcx, [rdi]; lpMem
0x140010ff2  test    rcx, rcx
0x140010ff5  jz      short loc_140010FFF
0x140010ff7  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140010ffc  mov     [rdi], r15
0x140010fff  mov     rdx, rdi
0x140011002  mov     rcx, r14
0x140011005  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x14001100a  mov     edi, eax
0x14001100c  test    eax, eax
0x14001100e  jns     short loc_140011017
0x140011010  mov     edx, 13h
0x140011015  jmp     short loc_140010FA4
0x140011017  test    rbx, rbx
0x14001101a  jz      short loc_140011085
0x14001101c  cmp     [rbx], r15w
0x140011020  jz      short loc_140011085
0x140011022  lea     rdx, [rsp+58h+var_38]
0x140011027  mov     [rsp+58h+var_38], r15; int
0x14001102c  mov     rcx, rbx
0x14001102f  call    ?GetFileVersion@@YAJPEB_WPEA_KW4GetFileVersionFlag@@@Z; GetFileVersion(wchar_t const *,unsigned __int64 *,GetFileVersionFlag)
0x140011034  mov     ebx, eax
0x140011036  test    eax, eax
0x140011038  jns     short loc_140011057
0x14001103a  mov     edx, 18h; void *
0x14001103f  mov     rcx, [rsp+58h]; this
0x140011044  lea     r8, aCW1SSrcClientL_2; "C:\\__w\\1\\s\\src\\Client\\lib\\Undock"...
0x14001104b  mov     r9d, ebx; char *
0x14001104e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011053  mov     eax, ebx
0x140011055  jmp     short loc_140011087
0x140011057  lea     rbx, [rsi+18h]
0x14001105b  mov     rcx, [rbx]; lpMem
0x14001105e  test    rcx, rcx
0x140011061  jz      short loc_14001106B
0x140011063  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140011068  mov     [rbx], r15
0x14001106b  mov     rcx, [rsp+58h+var_38]; unsigned __int64
0x140011070  mov     rdx, rbx; wchar_t **
0x140011073  call    ?ConvertFileVerToStringW@@YAJ_KPEAPEA_W@Z; ConvertFileVerToStringW(unsigned __int64,wchar_t * *)
0x140011078  mov     ebx, eax
0x14001107a  test    eax, eax
0x14001107c  jns     short loc_140011085
0x14001107e  mov     edx, 19h
0x140011083  jmp     short loc_14001103F
0x140011085  xor     eax, eax
0x140011087  mov     rcx, [rsp+58h+var_30]
0x14001108c  xor     rcx, rsp; StackCookie
0x14001108f  call    __security_check_cookie
0x140011094  mov     rbx, [rsp+58h+arg_8]
0x140011099  add     rsp, 30h
0x14001109d  pop     r15
0x14001109f  pop     r14
0x1400110a1  pop     rdi
0x1400110a2  pop     rsi
0x1400110a3  pop     rbp
0x1400110a4  retn
```
