# GetUserProfileDirectoryWInternal(void *,ushort *,ulong *)

- ea: `0x180005100`
- end: `0x18000553a`
- name: `?GetUserProfileDirectoryWInternal@@YAHPEAXPEAGPEAK@Z`
- size: `1082`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006bd0`

## callees

- `0x180005100`
- `0x180005690`
- `0x180005900`
- `0x180005b30`
- `0x18000e640`
- `0x18001408c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000528e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000528e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800051b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005239`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800051b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005239`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005197`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005222`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000527a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005197`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005222`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000527a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000513b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000541d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800054f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000513b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000541d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800054f6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800051f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005492`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800051f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005492`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005210`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005210`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000525b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000525b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000538d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000538d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800052b7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800052b7`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000532b`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180005406`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000532b`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180005406`

## pseudocode

```c
__int64 __fastcall GetUserProfileDirectoryWInternal(HANDLE TokenHandle, unsigned __int16 *a2, unsigned int *a3)
{
  HANDLE ProcessHeap; // rax
  LPWSTR v8; // rsi
  unsigned int v9; // r13d
  void *v10; // rbp
  int Error; // edi
  DWORD LengthSid; // edi
  HANDLE v13; // rax
  void *v14; // rax
  void *v15; // r14
  HANDLE v16; // rax
  int v17; // edi
  LPWSTR v18; // rsi
  HANDLE v19; // rax
  __int64 v20; // rbp
  int BasicProfileFolderPath; // edi
  __int64 v22; // rcx
  int v23; // eax
  BOOL TokenInformation; // eax
  _WORD *v25; // rax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-268h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-260h] BYREF
  _BYTE v28[528]; // [rsp+40h] [rbp-258h] BYREF

  if ( TokenHandle )
  {
    if ( !a3 )
    {
      SetLastError(0x57u);
      return 0;
    }
    TokenInformationLength = 200;
    ProcessHeap = GetProcessHeap();
    StringSid = (LPWSTR)HeapAlloc(ProcessHeap, 8u, 0xC8u);
    v8 = StringSid;
    if ( !StringSid )
      goto LABEL_35;
    v9 = 1;
    v10 = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, StringSid, TokenInformationLength, &TokenInformationLength) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error == -2147024774 )
      {
        v23 = ResultFromHeapReAlloc(v8, TokenInformationLength, (void **)&StringSid);
        v8 = StringSid;
        Error = v23;
        if ( v23 < 0 )
          goto LABEL_12;
        TokenInformation = GetTokenInformation(
                             TokenHandle,
                             TokenUser,
                             StringSid,
                             TokenInformationLength,
                             &TokenInformationLength);
        Error = ResultFromWin32Bool(TokenInformation);
      }
    }
    if ( Error >= 0 )
    {
      LengthSid = GetLengthSid(*(PSID *)v8);
      TokenInformationLength = LengthSid;
      v13 = GetProcessHeap();
      v14 = HeapAlloc(v13, 8u, LengthSid);
      v15 = v14;
      if ( !v14 )
      {
        Error = -2147024882;
        goto LABEL_12;
      }
      if ( CopySid(TokenInformationLength, v14, *(PSID *)v8) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
          ResultFromHeapFree(v15);
          goto LABEL_12;
        }
      }
      v10 = v15;
    }
LABEL_12:
    if ( v8 )
    {
      v16 = GetProcessHeap();
      if ( !HeapFree(v16, 0, v8) )
        ResultFromKnownLastError();
    }
    if ( Error < 0 )
      goto LABEL_35;
    StringSid = 0;
    if ( ConvertSidToStringSidW(v10, &StringSid) )
    {
      v17 = 0;
    }
    else
    {
      v18 = 0;
      v17 = ResultFromKnownLastError();
      if ( v17 < 0 )
        goto LABEL_19;
    }
    v18 = StringSid;
LABEL_19:
    if ( v10 )
    {
      v19 = GetProcessHeap();
      if ( !HeapFree(v19, 0, v10) )
        ResultFromKnownLastError();
    }
    if ( v17 >= 0 )
    {
      if ( a2 && *a3 )
      {
        v20 = 0x7FFFFFFF;
        BasicProfileFolderPath = GetBasicProfileFolderPath(5, v18, a2, *a3);
        if ( BasicProfileFolderPath >= 0 )
        {
          v22 = 0x7FFFFFFF;
          do
          {
            if ( !*a2 )
              break;
            ++a2;
            --v22;
          }
          while ( v22 );
          BasicProfileFolderPath = -2147024809;
          if ( v22 )
          {
            BasicProfileFolderPath = 0;
            *a3 = 0x80000000 - v22;
          }
        }
        if ( BasicProfileFolderPath != -2147024774 )
        {
          if ( BasicProfileFolderPath >= 0 )
          {
LABEL_33:
            LocalFree(v18);
            return v9;
          }
LABEL_38:
          SetLastError((unsigned __int16)BasicProfileFolderPath);
          v9 = 0;
          goto LABEL_33;
        }
        if ( *a3 >= 0x104 )
          goto LABEL_38;
      }
      else
      {
        LOWORD(BasicProfileFolderPath) = 122;
        *a3 = 0;
        v20 = 0x7FFFFFFF;
      }
      if ( (int)GetBasicProfileFolderPath(5, v18, v28, 260) >= 0 )
      {
        v25 = v28;
        while ( *v25 )
        {
          ++v25;
          if ( !--v20 )
            goto LABEL_38;
        }
        *a3 = 0x80000000 - v20;
      }
      goto LABEL_38;
    }
LABEL_35:
    v9 = 0;
    SetLastError(6u);
    return v9;
  }
  SetLastError(6u);
  return 0;
}

```

## disassembly

```asm
0x180005100  push    rbx
0x180005102  push    r12
0x180005104  push    r14
0x180005106  sub     rsp, 280h
0x18000510d  mov     rax, cs:__security_cookie
0x180005114  xor     rax, rsp
0x180005117  mov     [rsp+298h+var_48], rax
0x18000511f  mov     r12, r8
0x180005122  mov     rbx, rdx
0x180005125  mov     r14, rcx
0x180005128  test    rcx, rcx
0x18000512b  jz      loc_1800054F1
0x180005131  test    r8, r8
0x180005134  jnz     short loc_180005167
0x180005136  mov     ecx, 57h ; 'W'; dwErrCode
0x18000513b  call    cs:__imp_SetLastError
0x180005142  nop     dword ptr [rax+rax+00h]
0x180005147  xor     eax, eax
0x180005149  mov     rcx, [rsp+298h+var_48]
0x180005151  xor     rcx, rsp; StackCookie
0x180005154  call    __security_check_cookie
0x180005159  add     rsp, 280h
0x180005160  pop     r14
0x180005162  pop     r12
0x180005164  pop     rbx
0x180005165  retn
0x180005167  mov     [rsp+298h+arg_18], rbp
0x18000516f  mov     [rsp+298h+var_20], rsi
0x180005177  mov     [rsp+298h+var_28], rdi
0x18000517f  mov     [rsp+298h+var_30], r13
0x180005187  mov     [rsp+298h+var_38], r15
0x18000518f  mov     [rsp+298h+TokenInformationLength], 0C8h
0x180005197  call    cs:__imp_GetProcessHeap
0x18000519e  nop     dword ptr [rax+rax+00h]
0x1800051a3  mov     edx, 8; dwFlags
0x1800051a8  mov     r8d, 0C8h; dwBytes
0x1800051ae  mov     rcx, rax; hHeap
0x1800051b1  call    cs:__imp_HeapAlloc
0x1800051b8  nop     dword ptr [rax+rax+00h]
0x1800051bd  xor     r15d, r15d
0x1800051c0  mov     [rsp+298h+StringSid], rax
0x1800051c5  mov     rsi, rax
0x1800051c8  test    rax, rax
0x1800051cb  jz      loc_1800053C9
0x1800051d1  mov     r9d, [rsp+298h+TokenInformationLength]; TokenInformationLength
0x1800051d6  lea     rax, [rsp+298h+TokenInformationLength]
0x1800051db  mov     r13d, 1
0x1800051e1  mov     [rsp+298h+ReturnLength], rax; ReturnLength
0x1800051e6  mov     edx, r13d; TokenInformationClass
0x1800051e9  mov     r8, rsi; TokenInformation
0x1800051ec  mov     rcx, r14; TokenHandle
0x1800051ef  mov     ebp, r15d
0x1800051f2  call    cs:__imp_GetTokenInformation
0x1800051f9  nop     dword ptr [rax+rax+00h]
0x1800051fe  test    eax, eax
0x180005200  jz      loc_180005448
0x180005206  mov     edi, r15d
0x180005209  test    edi, edi
0x18000520b  js      short loc_180005275
0x18000520d  mov     rcx, [rsi]; pSid
0x180005210  call    cs:__imp_GetLengthSid
0x180005217  nop     dword ptr [rax+rax+00h]
0x18000521c  mov     edi, eax
0x18000521e  mov     [rsp+298h+TokenInformationLength], edi
0x180005222  call    cs:__imp_GetProcessHeap
0x180005229  nop     dword ptr [rax+rax+00h]
0x18000522e  mov     r8d, edi; dwBytes
0x180005231  mov     edx, 8; dwFlags
0x180005236  mov     rcx, rax; hHeap
0x180005239  call    cs:__imp_HeapAlloc
0x180005240  nop     dword ptr [rax+rax+00h]
0x180005245  mov     r14, rax
0x180005248  test    rax, rax
0x18000524b  jz      loc_180005509
0x180005251  mov     r8, [rsi]; pSourceSid
0x180005254  mov     rdx, rax; pDestinationSid
0x180005257  mov     ecx, [rsp+298h+TokenInformationLength]; nDestinationSidLength
0x18000525b  call    cs:__imp_CopySid
0x180005262  nop     dword ptr [rax+rax+00h]
0x180005267  test    eax, eax
0x180005269  jz      loc_1800054AC
0x18000526f  mov     edi, r15d
0x180005272  mov     rbp, r14
0x180005275  test    rsi, rsi
0x180005278  jz      short loc_1800052A2
0x18000527a  call    cs:__imp_GetProcessHeap
0x180005281  nop     dword ptr [rax+rax+00h]
0x180005286  mov     r8, rsi; lpMem
0x180005289  xor     edx, edx; dwFlags
0x18000528b  mov     rcx, rax; hHeap
0x18000528e  call    cs:__imp_HeapFree
0x180005295  nop     dword ptr [rax+rax+00h]
0x18000529a  test    eax, eax
0x18000529c  jz      loc_180005513
0x1800052a2  test    edi, edi
0x1800052a4  js      loc_1800053C9
0x1800052aa  lea     rdx, [rsp+298h+StringSid]; StringSid
0x1800052af  mov     [rsp+298h+StringSid], r15
0x1800052b4  mov     rcx, rbp; Sid
0x1800052b7  call    cs:__imp_ConvertSidToStringSidW
0x1800052be  nop     dword ptr [rax+rax+00h]
0x1800052c3  test    eax, eax
0x1800052c5  jz      loc_180005431
0x1800052cb  mov     edi, r15d
0x1800052ce  mov     rsi, [rsp+298h+StringSid]
0x1800052d3  test    rbp, rbp
0x1800052d6  jz      short loc_180005300
0x1800052d8  call    cs:__imp_GetProcessHeap
0x1800052df  nop     dword ptr [rax+rax+00h]
0x1800052e4  mov     r8, rbp; lpMem
0x1800052e7  xor     edx, edx; dwFlags
0x1800052e9  mov     rcx, rax; hHeap
0x1800052ec  call    cs:__imp_HeapFree
0x1800052f3  nop     dword ptr [rax+rax+00h]
0x1800052f8  test    eax, eax
0x1800052fa  jz      loc_18000551D
0x180005300  test    edi, edi
0x180005302  js      loc_1800053C9
0x180005308  test    rbx, rbx
0x18000530b  jz      loc_1800053DF
0x180005311  mov     eax, [r12]
0x180005315  test    eax, eax
0x180005317  jz      loc_1800053DF
0x18000531d  mov     r9d, eax
0x180005320  mov     r8, rbx
0x180005323  mov     rdx, rsi
0x180005326  mov     ecx, 5
0x18000532b  call    cs:__imp_GetBasicProfileFolderPath
0x180005332  nop     dword ptr [rax+rax+00h]
0x180005337  mov     ebp, 7FFFFFFFh
0x18000533c  mov     r14d, 80000000h
0x180005342  mov     edi, eax
0x180005344  test    eax, eax
0x180005346  js      short loc_180005376
0x180005348  mov     ecx, ebp
0x18000534a  nop     word ptr [rax+rax+00h]
0x180005350  cmp     [rbx], r15w
0x180005354  jz      short loc_18000535F
0x180005356  add     rbx, 2
0x18000535a  sub     rcx, r13
0x18000535d  jnz     short loc_180005350
0x18000535f  test    rcx, rcx
0x180005362  mov     edi, 80070057h
0x180005367  cmovnz  edi, r15d
0x18000536b  jz      short loc_180005376
0x18000536d  mov     eax, r14d
0x180005370  sub     eax, ecx
0x180005372  mov     [r12], eax
0x180005376  cmp     edi, 8007007Ah
0x18000537c  jz      loc_180005527
0x180005382  test    edi, edi
0x180005384  js      loc_18000541A
0x18000538a  mov     rcx, rsi; hMem
0x18000538d  call    cs:__imp_LocalFree
0x180005394  nop     dword ptr [rax+rax+00h]
0x180005399  mov     r15, [rsp+298h+var_38]
0x1800053a1  mov     eax, r13d
0x1800053a4  mov     r13, [rsp+298h+var_30]
0x1800053ac  mov     rdi, [rsp+298h+var_28]
0x1800053b4  mov     rsi, [rsp+298h+var_20]
0x1800053bc  mov     rbp, [rsp+298h+arg_18]
0x1800053c4  jmp     loc_180005149
0x1800053c9  mov     ecx, 6; dwErrCode
0x1800053ce  mov     r13d, r15d
0x1800053d1  call    cs:__imp_SetLastError
0x1800053d8  nop     dword ptr [rax+rax+00h]
0x1800053dd  jmp     short loc_180005399
0x1800053df  mov     edi, 8007007Ah
0x1800053e4  mov     [r12], r15d
0x1800053e8  mov     ebp, 7FFFFFFFh
0x1800053ed  mov     r14d, 80000000h
0x1800053f3  mov     r9d, 104h
0x1800053f9  lea     r8, [rsp+298h+var_258]
0x1800053fe  mov     rdx, rsi
0x180005401  mov     ecx, 5
0x180005406  call    cs:__imp_GetBasicProfileFolderPath
0x18000540d  nop     dword ptr [rax+rax+00h]
0x180005412  test    eax, eax
0x180005414  jns     loc_1800054C8
0x18000541a  movzx   ecx, di; dwErrCode
0x18000541d  call    cs:__imp_SetLastError
0x180005424  nop     dword ptr [rax+rax+00h]
0x180005429  mov     r13d, r15d
0x18000542c  jmp     loc_18000538A
0x180005431  mov     rsi, r15
0x180005434  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005439  mov     edi, eax
0x18000543b  test    eax, eax
0x18000543d  jns     loc_1800052CE
0x180005443  jmp     loc_1800052D3
0x180005448  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000544d  mov     edi, eax
0x18000544f  cmp     eax, 8007007Ah
0x180005454  jnz     loc_180005209
0x18000545a  mov     edx, [rsp+298h+TokenInformationLength]; dwBytes
0x18000545e  lea     r8, [rsp+298h+StringSid]; void **
0x180005463  mov     rcx, rsi; lpMem
0x180005466  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x18000546b  mov     rsi, [rsp+298h+StringSid]
0x180005470  mov     edi, eax
0x180005472  test    eax, eax
0x180005474  js      loc_180005275
0x18000547a  mov     r9d, [rsp+298h+TokenInformationLength]; TokenInformationLength
0x18000547f  lea     rax, [rsp+298h+TokenInformationLength]
0x180005484  mov     r8, rsi; TokenInformation
0x180005487  mov     [rsp+298h+ReturnLength], rax; ReturnLength
0x18000548c  mov     edx, r13d; TokenInformationClass
0x18000548f  mov     rcx, r14; TokenHandle
0x180005492  call    cs:__imp_GetTokenInformation
0x180005499  nop     dword ptr [rax+rax+00h]
0x18000549e  mov     ecx, eax; int
0x1800054a0  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800054a5  mov     edi, eax
0x1800054a7  jmp     loc_180005209
0x1800054ac  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800054b1  mov     edi, eax
0x1800054b3  test    eax, eax
0x1800054b5  jns     loc_180005272
0x1800054bb  mov     rcx, r14; lpMem
0x1800054be  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800054c3  jmp     loc_180005275
0x1800054c8  lea     rax, [rsp+298h+var_258]
0x1800054cd  nop     dword ptr [rax]
0x1800054d0  cmp     [rax], r15w
0x1800054d4  jz      short loc_1800054E5
0x1800054d6  add     rax, 2
0x1800054da  sub     rbp, 1
0x1800054de  jnz     short loc_1800054D0
0x1800054e0  jmp     loc_18000541A
0x1800054e5  sub     r14d, ebp
0x1800054e8  mov     [r12], r14d
0x1800054ec  jmp     loc_18000541A
0x1800054f1  mov     ecx, 6; dwErrCode
0x1800054f6  call    cs:__imp_SetLastError
0x1800054fd  nop     dword ptr [rax+rax+00h]
0x180005502  xor     eax, eax
0x180005504  jmp     loc_180005149
0x180005509  mov     edi, 8007000Eh
0x18000550e  jmp     loc_180005275
0x180005513  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005518  jmp     loc_1800052A2
0x18000551d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005522  jmp     loc_180005300
0x180005527  cmp     dword ptr [r12], 104h
0x18000552f  jnb     loc_18000541A
0x180005535  jmp     loc_1800053F3
```
