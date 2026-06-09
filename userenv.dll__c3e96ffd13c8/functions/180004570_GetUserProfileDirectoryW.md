# GetUserProfileDirectoryW

- ea: `0x180004570`
- end: `0x18000492f`
- name: `GetUserProfileDirectoryW`
- size: `959`
- prototype: `BOOL __stdcall(HANDLE hToken, LPWSTR lpProfileDir, LPDWORD lpcchSize)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004570`
- `0x180004fc0`
- `0x1800051f0`
- `0x1800053f0`
- `0x18000d9b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800046bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004706`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800046bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004706`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180004859`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180004859`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004610`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004679`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004610`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004679`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800045fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004668`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004845`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800045fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004668`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800046f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004845`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000480a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800048b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800047cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000480a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800048b4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004645`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800048ea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004645`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800048ea`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000465c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000465c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004695`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004695`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004797`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004797`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800046de`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800046de`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000473f`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800047fd`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000473f`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800047fd`

## pseudocode

```c
BOOL __stdcall GetUserProfileDirectoryW(HANDLE hToken, LPWSTR lpProfileDir, LPDWORD lpcchSize)
{
  HANDLE ProcessHeap; // rax
  PSID *v8; // rsi
  BOOL v9; // r13d
  void *v10; // r14
  signed int Error; // edi
  DWORD LengthSid; // edi
  HANDLE v13; // rax
  void *v14; // rax
  void *v15; // r15
  HANDLE v16; // rax
  signed int v17; // edi
  LPWSTR v18; // rsi
  HANDLE v19; // rax
  __int64 v20; // r14
  int BasicProfileFolderPath; // edi
  __int64 v22; // rcx
  DWORD v23; // edi
  HANDLE v24; // rax
  PSID *v25; // rax
  _WORD *v26; // rax
  BOOL TokenInformation; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-268h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-260h] BYREF
  _BYTE v30[528]; // [rsp+40h] [rbp-258h] BYREF

  if ( hToken )
  {
    if ( !lpcchSize )
    {
      SetLastError(0x57u);
      return 0;
    }
    TokenInformationLength = 200;
    ProcessHeap = GetProcessHeap();
    v8 = (PSID *)HeapAlloc(ProcessHeap, 8u, 0xC8u);
    if ( !v8 )
      goto LABEL_34;
    v9 = 1;
    v10 = 0;
    if ( GetTokenInformation(hToken, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error == -2147024774 )
      {
        v23 = TokenInformationLength;
        v24 = GetProcessHeap();
        v25 = (PSID *)HeapReAlloc(v24, 8u, v8, v23);
        if ( v25 )
        {
          v8 = v25;
        }
        else
        {
          Error = ResultFromKnownLastError();
          if ( Error < 0 )
            goto LABEL_12;
        }
        TokenInformation = GetTokenInformation(hToken, TokenUser, v8, TokenInformationLength, &TokenInformationLength);
        Error = ResultFromWin32Bool(TokenInformation);
      }
    }
    if ( Error < 0 )
      goto LABEL_12;
    LengthSid = GetLengthSid(*v8);
    TokenInformationLength = LengthSid;
    v13 = GetProcessHeap();
    v14 = HeapAlloc(v13, 8u, LengthSid);
    v15 = v14;
    if ( v14 )
    {
      if ( CopySid(TokenInformationLength, v14, *v8) )
      {
        Error = 0;
LABEL_11:
        v10 = v15;
        goto LABEL_12;
      }
      Error = ResultFromKnownLastError();
      if ( Error >= 0 )
        goto LABEL_11;
      ResultFromHeapFree(v15);
    }
    else
    {
      Error = -2147024882;
    }
LABEL_12:
    v16 = GetProcessHeap();
    if ( !HeapFree(v16, 0, v8) )
      ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_34;
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
        goto LABEL_18;
    }
    v18 = StringSid;
LABEL_18:
    if ( v10 )
    {
      v19 = GetProcessHeap();
      if ( !HeapFree(v19, 0, v10) )
        ResultFromKnownLastError();
    }
    if ( v17 >= 0 )
    {
      if ( lpProfileDir && *lpcchSize )
      {
        v20 = 0x7FFFFFFF;
        BasicProfileFolderPath = GetBasicProfileFolderPath(5, v18, lpProfileDir, *lpcchSize);
        if ( BasicProfileFolderPath >= 0 )
        {
          v22 = 0x7FFFFFFF;
          do
          {
            if ( !*lpProfileDir )
              break;
            ++lpProfileDir;
            --v22;
          }
          while ( v22 );
          BasicProfileFolderPath = -2147024809;
          if ( v22 )
          {
            BasicProfileFolderPath = 0;
            *lpcchSize = 0x80000000 - v22;
          }
        }
        if ( BasicProfileFolderPath != -2147024774 )
        {
          if ( BasicProfileFolderPath >= 0 )
          {
LABEL_32:
            LocalFree(v18);
            return v9;
          }
LABEL_37:
          SetLastError((unsigned __int16)BasicProfileFolderPath);
          v9 = 0;
          goto LABEL_32;
        }
        if ( *lpcchSize >= 0x104 )
          goto LABEL_37;
      }
      else
      {
        LOWORD(BasicProfileFolderPath) = 122;
        *lpcchSize = 0;
        v20 = 0x7FFFFFFF;
      }
      if ( (int)GetBasicProfileFolderPath(5, v18, v30, 260) >= 0 )
      {
        v26 = v30;
        while ( *v26 )
        {
          ++v26;
          if ( !--v20 )
            goto LABEL_37;
        }
        *lpcchSize = 0x80000000 - v20;
      }
      goto LABEL_37;
    }
LABEL_34:
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
0x180004570  push    rbx
0x180004572  push    rbp
0x180004573  push    r12
0x180004575  push    r15
0x180004577  sub     rsp, 278h
0x18000457e  mov     rax, cs:__security_cookie
0x180004585  xor     rax, rsp
0x180004588  mov     [rsp+298h+var_48], rax
0x180004590  mov     r12, r8
0x180004593  mov     rbx, rdx
0x180004596  mov     r15, rcx
0x180004599  test    rcx, rcx
0x18000459c  jz      loc_1800048AF
0x1800045a2  test    r8, r8
0x1800045a5  jnz     short loc_1800045D4
0x1800045a7  mov     ecx, 57h ; 'W'; dwErrCode
0x1800045ac  call    cs:__imp_SetLastError
0x1800045b2  xor     ebp, ebp
0x1800045b4  mov     eax, ebp
0x1800045b6  mov     rcx, [rsp+298h+var_48]
0x1800045be  xor     rcx, rsp; StackCookie
0x1800045c1  call    __security_check_cookie
0x1800045c6  add     rsp, 278h
0x1800045cd  pop     r15
0x1800045cf  pop     r12
0x1800045d1  pop     rbp
0x1800045d2  pop     rbx
0x1800045d3  retn
0x1800045d4  mov     [rsp+298h+arg_18], rsi
0x1800045dc  mov     [rsp+298h+var_28], rdi
0x1800045e4  mov     [rsp+298h+var_30], r13
0x1800045ec  mov     [rsp+298h+var_38], r14
0x1800045f4  mov     [rsp+298h+TokenInformationLength], 0C8h
0x1800045fc  call    cs:__imp_GetProcessHeap
0x180004602  mov     edx, 8; dwFlags
0x180004607  mov     r8d, 0C8h; dwBytes
0x18000460d  mov     rcx, rax; hHeap
0x180004610  call    cs:__imp_HeapAlloc
0x180004616  xor     ebp, ebp
0x180004618  mov     rsi, rax
0x18000461b  test    rax, rax
0x18000461e  jz      loc_1800047C5
0x180004624  mov     r9d, [rsp+298h+TokenInformationLength]; TokenInformationLength
0x180004629  lea     rax, [rsp+298h+TokenInformationLength]
0x18000462e  mov     r13d, 1
0x180004634  mov     [rsp+298h+ReturnLength], rax; ReturnLength
0x180004639  mov     edx, r13d; TokenInformationClass
0x18000463c  mov     r8, rsi; TokenInformation
0x18000463f  mov     rcx, r15; TokenHandle
0x180004642  mov     r14d, ebp
0x180004645  call    cs:__imp_GetTokenInformation
0x18000464b  test    eax, eax
0x18000464d  jz      loc_18000482F
0x180004653  mov     edi, ebp
0x180004655  test    edi, edi
0x180004657  js      short loc_1800046AD
0x180004659  mov     rcx, [rsi]; pSid
0x18000465c  call    cs:__imp_GetLengthSid
0x180004662  mov     edi, eax
0x180004664  mov     [rsp+298h+TokenInformationLength], edi
0x180004668  call    cs:__imp_GetProcessHeap
0x18000466e  mov     r8d, edi; dwBytes
0x180004671  mov     edx, 8; dwFlags
0x180004676  mov     rcx, rax; hHeap
0x180004679  call    cs:__imp_HeapAlloc
0x18000467f  mov     r15, rax
0x180004682  test    rax, rax
0x180004685  jz      loc_1800048FE
0x18000468b  mov     r8, [rsi]; pSourceSid
0x18000468e  mov     rdx, rax; pDestinationSid
0x180004691  mov     ecx, [rsp+298h+TokenInformationLength]; nDestinationSidLength
0x180004695  call    cs:__imp_CopySid
0x18000469b  test    eax, eax
0x18000469d  jz      loc_180004869
0x1800046a3  mov     edi, ebp
0x1800046a5  mov     r14, r15
0x1800046a8  test    rsi, rsi
0x1800046ab  jz      short loc_1800046C9
0x1800046ad  call    cs:__imp_GetProcessHeap
0x1800046b3  mov     r8, rsi; lpMem
0x1800046b6  xor     edx, edx; dwFlags
0x1800046b8  mov     rcx, rax; hHeap
0x1800046bb  call    cs:__imp_HeapFree
0x1800046c1  test    eax, eax
0x1800046c3  jz      loc_180004908
0x1800046c9  test    edi, edi
0x1800046cb  js      loc_1800047C5
0x1800046d1  lea     rdx, [rsp+298h+StringSid]; StringSid
0x1800046d6  mov     [rsp+298h+StringSid], rbp
0x1800046db  mov     rcx, r14; Sid
0x1800046de  call    cs:__imp_ConvertSidToStringSidW
0x1800046e4  test    eax, eax
0x1800046e6  jz      loc_180004818
0x1800046ec  mov     edi, ebp
0x1800046ee  mov     rsi, [rsp+298h+StringSid]
0x1800046f3  test    r14, r14
0x1800046f6  jz      short loc_180004714
0x1800046f8  call    cs:__imp_GetProcessHeap
0x1800046fe  mov     r8, r14; lpMem
0x180004701  xor     edx, edx; dwFlags
0x180004703  mov     rcx, rax; hHeap
0x180004706  call    cs:__imp_HeapFree
0x18000470c  test    eax, eax
0x18000470e  jz      loc_180004912
0x180004714  test    edi, edi
0x180004716  js      loc_1800047C5
0x18000471c  test    rbx, rbx
0x18000471f  jz      loc_1800047D5
0x180004725  mov     eax, [r12]
0x180004729  test    eax, eax
0x18000472b  jz      loc_1800047D5
0x180004731  mov     r9d, eax
0x180004734  mov     r8, rbx
0x180004737  mov     rdx, rsi
0x18000473a  mov     ecx, 5
0x18000473f  call    cs:__imp_GetBasicProfileFolderPath
0x180004745  mov     r14d, 7FFFFFFFh
0x18000474b  mov     r15d, 80000000h
0x180004751  mov     edi, eax
0x180004753  test    eax, eax
0x180004755  js      short loc_180004784
0x180004757  mov     ecx, r14d
0x18000475a  nop     word ptr [rax+rax+00h]
0x180004760  cmp     [rbx], bp
0x180004763  jz      short loc_18000476E
0x180004765  add     rbx, 2
0x180004769  sub     rcx, r13
0x18000476c  jnz     short loc_180004760
0x18000476e  test    rcx, rcx
0x180004771  mov     edi, 80070057h
0x180004776  cmovnz  edi, ebp
0x180004779  jz      short loc_180004784
0x18000477b  mov     eax, r15d
0x18000477e  sub     eax, ecx
0x180004780  mov     [r12], eax
0x180004784  cmp     edi, 8007007Ah
0x18000478a  jz      loc_18000491C
0x180004790  test    edi, edi
0x180004792  js      short loc_180004807
0x180004794  mov     rcx, rsi; hMem
0x180004797  call    cs:__imp_LocalFree
0x18000479d  mov     r14, [rsp+298h+var_38]
0x1800047a5  mov     eax, r13d
0x1800047a8  mov     r13, [rsp+298h+var_30]
0x1800047b0  mov     rdi, [rsp+298h+var_28]
0x1800047b8  mov     rsi, [rsp+298h+arg_18]
0x1800047c0  jmp     loc_1800045B6
0x1800047c5  mov     ecx, 6; dwErrCode
0x1800047ca  mov     r13d, ebp
0x1800047cd  call    cs:__imp_SetLastError
0x1800047d3  jmp     short loc_18000479D
0x1800047d5  mov     edi, 8007007Ah
0x1800047da  mov     [r12], ebp
0x1800047de  mov     r14d, 7FFFFFFFh
0x1800047e4  mov     r15d, 80000000h
0x1800047ea  mov     r9d, 104h
0x1800047f0  lea     r8, [rsp+298h+var_258]
0x1800047f5  mov     rdx, rsi
0x1800047f8  mov     ecx, 5
0x1800047fd  call    cs:__imp_GetBasicProfileFolderPath
0x180004803  test    eax, eax
0x180004805  jns     short loc_180004885
0x180004807  movzx   ecx, di; dwErrCode
0x18000480a  call    cs:__imp_SetLastError
0x180004810  mov     r13d, ebp
0x180004813  jmp     loc_180004794
0x180004818  mov     rsi, rbp
0x18000481b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004820  mov     edi, eax
0x180004822  test    eax, eax
0x180004824  jns     loc_1800046EE
0x18000482a  jmp     loc_1800046F3
0x18000482f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004834  mov     edi, eax
0x180004836  cmp     eax, 8007007Ah
0x18000483b  jnz     loc_180004655
0x180004841  mov     edi, [rsp+298h+TokenInformationLength]
0x180004845  call    cs:__imp_GetProcessHeap
0x18000484b  mov     r9d, edi; dwBytes
0x18000484e  mov     r8, rsi; lpMem
0x180004851  mov     rcx, rax; hHeap
0x180004854  mov     edx, 8; dwFlags
0x180004859  call    cs:__imp_HeapReAlloc
0x18000485f  test    rax, rax
0x180004862  jz      short loc_1800048C3
0x180004864  mov     rsi, rax
0x180004867  jmp     short loc_1800048D2
0x180004869  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000486e  mov     edi, eax
0x180004870  test    eax, eax
0x180004872  jns     loc_1800046A5
0x180004878  mov     rcx, r15; lpMem
0x18000487b  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180004880  jmp     loc_1800046A8
0x180004885  lea     rax, [rsp+298h+var_258]
0x18000488a  nop     word ptr [rax+rax+00h]
0x180004890  cmp     [rax], bp
0x180004893  jz      short loc_1800048A3
0x180004895  add     rax, 2
0x180004899  sub     r14, r13
0x18000489c  jnz     short loc_180004890
0x18000489e  jmp     loc_180004807
0x1800048a3  sub     r15d, r14d
0x1800048a6  mov     [r12], r15d
0x1800048aa  jmp     loc_180004807
0x1800048af  mov     ecx, 6; dwErrCode
0x1800048b4  call    cs:__imp_SetLastError
0x1800048ba  xor     ebp, ebp
0x1800048bc  mov     eax, ebp
0x1800048be  jmp     loc_1800045B6
0x1800048c3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800048c8  mov     edi, eax
0x1800048ca  test    eax, eax
0x1800048cc  js      loc_1800046AD
0x1800048d2  mov     r9d, [rsp+298h+TokenInformationLength]; TokenInformationLength
0x1800048d7  lea     rax, [rsp+298h+TokenInformationLength]
0x1800048dc  mov     r8, rsi; TokenInformation
0x1800048df  mov     [rsp+298h+ReturnLength], rax; ReturnLength
0x1800048e4  mov     edx, r13d; TokenInformationClass
0x1800048e7  mov     rcx, r15; TokenHandle
0x1800048ea  call    cs:__imp_GetTokenInformation
0x1800048f0  mov     ecx, eax; int
0x1800048f2  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800048f7  mov     edi, eax
0x1800048f9  jmp     loc_180004655
0x1800048fe  mov     edi, 8007000Eh
0x180004903  jmp     loc_1800046A8
0x180004908  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000490d  jmp     loc_1800046C9
0x180004912  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004917  jmp     loc_180004714
0x18000491c  cmp     dword ptr [r12], 104h
0x180004924  jnb     loc_180004807
0x18000492a  jmp     loc_1800047EA
```
