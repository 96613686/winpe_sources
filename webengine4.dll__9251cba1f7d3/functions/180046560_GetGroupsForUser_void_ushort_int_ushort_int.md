# GetGroupsForUser(void *,ushort *,int,ushort *,int)

- ea: `0x180046560`
- end: `0x1800468cb`
- name: `?GetGroupsForUser@@YAHPEAXPEAGH1H@Z`
- size: `875`
- prototype: `__int64 __usercall@<rax>(HANDLE TokenHandle@<rcx>, unsigned __int16 *@<rdx>, int@<r8d>, unsigned __int16 *@<r9>, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x180013690`
- `0x180046560`
- `0x18004d030`
- `0x18004d350`
- `0x18004d690`
- `0x18004d754`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18004672a`
- `KERNEL32!lstrlenW` at `0x18004673a`
- `KERNEL32!lstrlenW` at `0x18004672a`
- `KERNEL32!lstrlenW` at `0x18004673a`
- `KERNEL32!FormatMessageW` at `0x180046887`
- `KERNEL32!FormatMessageW` at `0x180046887`
- `ADVAPI32!GetTokenInformation` at `0x180046604`
- `ADVAPI32!GetTokenInformation` at `0x180046652`
- `ADVAPI32!GetTokenInformation` at `0x180046604`
- `ADVAPI32!GetTokenInformation` at `0x180046652`
- `ADVAPI32!LookupAccountSidW` at `0x1800466e6`
- `ADVAPI32!LookupAccountSidW` at `0x1800466e6`

## pseudocode

```c
__int64 __fastcall GetGroupsForUser(HANDLE TokenHandle, unsigned __int16 *a2, int a3, unsigned __int16 *a4, int nSize)
{
  WCHAR *v6; // r12
  unsigned int *v8; // rsi
  int v9; // edi
  int v10; // r13d
  DWORD LastWin32Error; // ebx
  unsigned int v12; // r12d
  int v13; // eax
  unsigned __int64 v14; // r14
  int v15; // eax
  unsigned __int64 v16; // r13
  int v17; // ecx
  unsigned __int16 *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  int v22; // [rsp+40h] [rbp-C0h]
  DWORD TokenInformationLength; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+4Ch] [rbp-B4h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v27; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v28; // [rsp+60h] [rbp-A0h]
  WCHAR ReferencedDomainName[256]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[256]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE TokenInformation[2048]; // [rsp+470h] [rbp+370h] BYREF

  v27 = a2;
  v28 = a4;
  v6 = a4;
  TokenInformationLength = 0;
  v22 = 0;
  v8 = (unsigned int *)TokenInformation;
  v9 = 0;
  v10 = 0;
  LastWin32Error = 0;
  if ( a3 < 0 || (unsigned __int64)a3 > 0x7FFFFFFFFFFFFFFFLL )
  {
    LastWin32Error = -2147024809;
    goto LABEL_45;
  }
  memset_0(a2, 0, 2LL * a3);
  if ( GetTokenInformation(TokenHandle, TokenGroups, TokenInformation, 0x800u, &TokenInformationLength) )
    goto LABEL_10;
  if ( TokenInformationLength > 0x800 )
  {
    v8 = (unsigned int *)MemAlloc(TokenInformationLength);
    if ( !v8 )
    {
      LastWin32Error = -2147024882;
      goto LABEL_45;
    }
    if ( !GetTokenInformation(TokenHandle, TokenGroups, v8, TokenInformationLength, &TokenInformationLength) )
    {
      LastWin32Error = GetLastWin32Error();
LABEL_41:
      if ( v8 != (unsigned int *)TokenInformation )
        MemFree(v8);
      goto LABEL_43;
    }
LABEL_10:
    v12 = 0;
    if ( *v8 )
    {
      do
      {
        cchName = 256;
        cchReferencedDomainName = 256;
        ReferencedDomainName[0] = 0;
        Name[0] = 0;
        if ( (v8[4 * v12 + 4] & 0xC0000014) == 4 )
        {
          if ( LookupAccountSidW(
                 0,
                 *(PSID *)&v8[4 * v12 + 2],
                 Name,
                 &cchName,
                 ReferencedDomainName,
                 &cchReferencedDomainName,
                 &peUse) )
          {
            if ( peUse != SidTypeDeletedAccount )
            {
              v14 = lstrlenW(ReferencedDomainName);
              v15 = lstrlenW(Name);
              v16 = v15;
              if ( v15 < 1 )
                goto LABEL_50;
              v17 = v14 + v15 + 1;
              if ( v9 <= 0 )
                v17 = v14 + v15;
              if ( (int)v14 > 0 )
                ++v17;
              if ( v17 < 0 || v9 < 0 )
              {
LABEL_50:
                LastWin32Error = -2147418113;
                goto LABEL_39;
              }
              if ( v17 + v9 >= a3 )
              {
                v10 = 1;
                v9 += v17;
                v22 = 1;
              }
              else
              {
                if ( v9 <= 0 )
                {
                  v18 = v27;
                }
                else
                {
                  if ( v9 >= a3 )
                    goto LABEL_38;
                  v18 = v27;
                  v19 = v9++;
                  v27[v19] = 9;
                }
                if ( (int)v14 > 0 )
                {
                  LastWin32Error = StringCchCopyNW(&v18[v9], a3 - v9, ReferencedDomainName, v14);
                  if ( LastWin32Error )
                    goto LABEL_39;
                  v9 += v14;
                  if ( v9 >= a3 )
                  {
LABEL_38:
                    LastWin32Error = -2147024774;
LABEL_39:
                    v10 = v22;
                    goto LABEL_40;
                  }
                  v18 = v27;
                  v20 = v9++;
                  v27[v20] = 92;
                }
                LastWin32Error = StringCchCopyNW(&v18[v9], a3 - v9, Name, v16);
                if ( LastWin32Error )
                  goto LABEL_39;
                v9 += v16;
                v10 = v22;
              }
            }
          }
          else
          {
            GetLastWin32Error();
          }
        }
        ++v12;
      }
      while ( v12 < *v8 );
      v13 = 0;
      if ( v10 )
        v13 = -2147024774;
      LastWin32Error = v13;
    }
LABEL_40:
    if ( !v8 )
      goto LABEL_43;
    goto LABEL_41;
  }
  LastWin32Error = GetLastWin32Error();
LABEL_43:
  if ( !LastWin32Error )
    return (unsigned int)v9;
  v6 = v28;
LABEL_45:
  if ( v6 )
  {
    if ( nSize > 0 )
      FormatMessageW(0x1200u, 0, LastWin32Error, 0x800u, v6, nSize, 0);
  }
  if ( !v10 )
    return 0;
  return (unsigned int)~v9;
}

```

## disassembly

```asm
0x180046560  push    rbp
0x180046562  push    rbx
0x180046563  push    rsi
0x180046564  push    rdi
0x180046565  push    r12
0x180046567  push    r13
0x180046569  push    r14
0x18004656b  push    r15
0x18004656d  lea     rbp, [rsp-0B88h]
0x180046575  sub     rsp, 0C88h
0x18004657c  mov     rax, cs:__security_cookie
0x180046583  xor     rax, rsp
0x180046586  mov     [rbp+0BC0h+var_50], rax
0x18004658d  mov     rax, rdx
0x180046590  mov     [rsp+0CC0h+var_C68], rdx
0x180046595  xor     edx, edx; Val
0x180046597  mov     [rsp+0CC0h+var_C60], r9
0x18004659c  movsxd  r15, r8d
0x18004659f  mov     r12, r9
0x1800465a2  mov     [rsp+0CC0h+TokenInformationLength], edx
0x1800465a6  mov     r14, rcx
0x1800465a9  mov     [rsp+0CC0h+var_C80], edx
0x1800465ad  lea     rsi, [rbp+0BC0h+TokenInformation]
0x1800465b4  mov     edi, edx
0x1800465b6  mov     r13d, edx
0x1800465b9  mov     ebx, edx
0x1800465bb  test    r8d, r8d
0x1800465be  js      loc_18004689D
0x1800465c4  mov     rcx, 7FFFFFFFFFFFFFFFh
0x1800465ce  mov     r8, r15
0x1800465d1  cmp     r15, rcx
0x1800465d4  ja      loc_18004689D
0x1800465da  add     r8, r8; Size
0x1800465dd  mov     rcx, rax; void *
0x1800465e0  call    memset_0
0x1800465e5  lea     rax, [rsp+0CC0h+TokenInformationLength]
0x1800465ea  mov     r9d, 800h; TokenInformationLength
0x1800465f0  lea     r8, [rbp+0BC0h+TokenInformation]; TokenInformation
0x1800465f7  mov     [rsp+0CC0h+ReturnLength], rax; ReturnLength
0x1800465fc  mov     edx, 2; TokenInformationClass
0x180046601  mov     rcx, r14; TokenHandle
0x180046604  call    cs:__imp_GetTokenInformation
0x18004660a  xor     r8d, r8d
0x18004660d  test    eax, eax
0x18004660f  jnz     short loc_180046677
0x180046611  cmp     [rsp+0CC0h+TokenInformationLength], 800h
0x180046619  jbe     short loc_18004666B
0x18004661b  mov     ecx, [rsp+0CC0h+TokenInformationLength]; unsigned __int64
0x18004661f  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180046624  xor     edx, edx
0x180046626  mov     rsi, rax
0x180046629  test    rax, rax
0x18004662c  jnz     short loc_180046638
0x18004662e  mov     ebx, 8007000Eh
0x180046633  jmp     loc_18004685A
0x180046638  mov     r9d, [rsp+0CC0h+TokenInformationLength]; TokenInformationLength
0x18004663d  lea     rax, [rsp+0CC0h+TokenInformationLength]
0x180046642  mov     r8, rsi; TokenInformation
0x180046645  mov     [rsp+0CC0h+ReturnLength], rax; ReturnLength
0x18004664a  mov     edx, 2; TokenInformationClass
0x18004664f  mov     rcx, r14; TokenHandle
0x180046652  call    cs:__imp_GetTokenInformation
0x180046658  xor     r8d, r8d
0x18004665b  test    eax, eax
0x18004665d  jnz     short loc_180046677
0x18004665f  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180046664  mov     ebx, eax
0x180046666  jmp     loc_18004683B
0x18004666b  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180046670  mov     ebx, eax
0x180046672  jmp     loc_18004684F
0x180046677  mov     r12d, r8d
0x18004667a  cmp     [rsi], r8d
0x18004667d  jbe     loc_180046836
0x180046683  mov     edx, r12d
0x180046686  add     rdx, rdx
0x180046689  mov     [rsp+0CC0h+cchName], 100h
0x180046691  mov     [rsp+0CC0h+var_C78], 100h
0x180046699  mov     [rsp+0CC0h+ReferencedDomainName], r8w
0x18004669f  mov     [rbp+0BC0h+Name], r8w
0x1800466a7  mov     eax, [rsi+rdx*8+10h]
0x1800466ab  and     eax, 0C0000014h
0x1800466b0  cmp     eax, 4
0x1800466b3  jnz     short loc_1800466FE
0x1800466b5  mov     rdx, [rsi+rdx*8+8]; Sid
0x1800466ba  lea     rax, [rsp+0CC0h+var_C70]
0x1800466bf  mov     [rsp+0CC0h+peUse], rax; peUse
0x1800466c4  lea     r9, [rsp+0CC0h+cchName]; cchName
0x1800466c9  lea     rax, [rsp+0CC0h+var_C78]
0x1800466ce  xor     ecx, ecx; lpSystemName
0x1800466d0  mov     [rsp+0CC0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800466d5  lea     r8, [rbp+0BC0h+Name]; Name
0x1800466dc  lea     rax, [rsp+0CC0h+ReferencedDomainName]
0x1800466e1  mov     [rsp+0CC0h+ReturnLength], rax; ReferencedDomainName
0x1800466e6  call    cs:__imp_LookupAccountSidW
0x1800466ec  xor     r8d, r8d
0x1800466ef  test    eax, eax
0x1800466f1  jnz     short loc_18004671E
0x1800466f3  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800466f8  xor     r8d, r8d
0x1800466fb  mov     ebx, r8d
0x1800466fe  inc     r12d
0x180046701  cmp     r12d, [rsi]
0x180046704  jb      loc_180046683
0x18004670a  mov     eax, ebx
0x18004670c  test    r13d, r13d
0x18004670f  mov     ebx, 8007007Ah
0x180046714  cmovnz  eax, ebx
0x180046717  mov     ebx, eax
0x180046719  jmp     loc_180046836
0x18004671e  cmp     [rsp+0CC0h+var_C70], 6
0x180046723  jz      short loc_1800466FB
0x180046725  lea     rcx, [rsp+0CC0h+ReferencedDomainName]; lpString
0x18004672a  call    cs:__imp_lstrlenW
0x180046730  lea     rcx, [rbp+0BC0h+Name]; lpString
0x180046737  movsxd  r14, eax
0x18004673a  call    cs:__imp_lstrlenW
0x180046740  movsxd  r13, eax
0x180046743  lea     edx, [r14+r13]
0x180046747  cmp     r13d, 1
0x18004674b  jl      loc_180046896
0x180046751  xor     r8d, r8d
0x180046754  lea     ecx, [rdx+1]
0x180046757  test    edi, edi
0x180046759  cmovle  ecx, edx
0x18004675c  test    r14d, r14d
0x18004675f  jle     short loc_180046763
0x180046761  inc     ecx
0x180046763  test    ecx, ecx
0x180046765  js      loc_180046896
0x18004676b  test    edi, edi
0x18004676d  js      loc_180046896
0x180046773  lea     eax, [rcx+rdi]
0x180046776  cmp     eax, r15d
0x180046779  jge     loc_18004681A
0x18004677f  test    edi, edi
0x180046781  jle     short loc_1800467A1
0x180046783  cmp     edi, r15d
0x180046786  jge     loc_18004682C
0x18004678c  mov     rcx, [rsp+0CC0h+var_C68]
0x180046791  mov     edx, 9
0x180046796  movsxd  rax, edi
0x180046799  inc     edi
0x18004679b  mov     [rcx+rax*2], dx
0x18004679f  jmp     short loc_1800467A6
0x1800467a1  mov     rcx, [rsp+0CC0h+var_C68]
0x1800467a6  test    r14d, r14d
0x1800467a9  jle     short loc_1800467E6
0x1800467ab  mov     eax, r15d
0x1800467ae  lea     r8, [rsp+0CC0h+ReferencedDomainName]; unsigned __int16 *
0x1800467b3  sub     eax, edi
0x1800467b5  mov     r9, r14; unsigned __int64
0x1800467b8  movsxd  rdx, eax; unsigned __int64
0x1800467bb  movsxd  rax, edi
0x1800467be  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x1800467c2  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800467c7  mov     ebx, eax
0x1800467c9  test    eax, eax
0x1800467cb  jnz     short loc_180046831
0x1800467cd  add     edi, r14d
0x1800467d0  cmp     edi, r15d
0x1800467d3  jge     short loc_18004682C
0x1800467d5  mov     rcx, [rsp+0CC0h+var_C68]
0x1800467da  lea     edx, [rbx+5Ch]
0x1800467dd  movsxd  rax, edi
0x1800467e0  inc     edi
0x1800467e2  mov     [rcx+rax*2], dx
0x1800467e6  mov     eax, r15d
0x1800467e9  lea     r8, [rbp+0BC0h+Name]; unsigned __int16 *
0x1800467f0  sub     eax, edi
0x1800467f2  mov     r9, r13; unsigned __int64
0x1800467f5  movsxd  rdx, eax; unsigned __int64
0x1800467f8  movsxd  rax, edi
0x1800467fb  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x1800467ff  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180046804  xor     r8d, r8d
0x180046807  mov     ebx, eax
0x180046809  test    eax, eax
0x18004680b  jnz     short loc_180046831
0x18004680d  add     edi, r13d
0x180046810  mov     r13d, [rsp+0CC0h+var_C80]
0x180046815  jmp     loc_1800466FE
0x18004681a  mov     r13d, 1
0x180046820  mov     edi, eax
0x180046822  mov     [rsp+0CC0h+var_C80], r13d
0x180046827  jmp     loc_1800466FE
0x18004682c  mov     ebx, 8007007Ah
0x180046831  mov     r13d, [rsp+0CC0h+var_C80]
0x180046836  test    rsi, rsi
0x180046839  jz      short loc_18004684F
0x18004683b  lea     rax, [rbp+0BC0h+TokenInformation]
0x180046842  cmp     rsi, rax
0x180046845  jz      short loc_18004684F
0x180046847  mov     rcx, rsi; lpMem
0x18004684a  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18004684f  xor     edx, edx
0x180046851  test    ebx, ebx
0x180046853  jz      short loc_1800468A6
0x180046855  mov     r12, [rsp+0CC0h+var_C60]
0x18004685a  test    r12, r12
0x18004685d  jz      short loc_18004688D
0x18004685f  mov     eax, [rbp+0BC0h+nSize]
0x180046865  test    eax, eax
0x180046867  jle     short loc_18004688D
0x180046869  mov     [rsp+0CC0h+peUse], rdx; Arguments
0x18004686e  mov     r9d, 800h; dwLanguageId
0x180046874  mov     dword ptr [rsp+0CC0h+cchReferencedDomainName], eax; nSize
0x180046878  xor     edx, edx; lpSource
0x18004687a  mov     r8d, ebx; dwMessageId
0x18004687d  mov     [rsp+0CC0h+ReturnLength], r12; lpBuffer
0x180046882  mov     ecx, 1200h; dwFlags
0x180046887  call    cs:__imp_FormatMessageW
0x18004688d  test    r13d, r13d
0x180046890  jnz     short loc_1800468A4
0x180046892  xor     eax, eax
0x180046894  jmp     short loc_1800468A8
0x180046896  mov     ebx, 8000FFFFh
0x18004689b  jmp     short loc_180046831
0x18004689d  mov     ebx, 80070057h
0x1800468a2  jmp     short loc_18004685A
0x1800468a4  not     edi
0x1800468a6  mov     eax, edi
0x1800468a8  mov     rcx, [rbp+0BC0h+var_50]
0x1800468af  xor     rcx, rsp; StackCookie
0x1800468b2  call    __security_check_cookie
0x1800468b7  add     rsp, 0C88h
0x1800468be  pop     r15
0x1800468c0  pop     r14
0x1800468c2  pop     r13
0x1800468c4  pop     r12
0x1800468c6  pop     rdi
0x1800468c7  pop     rsi
0x1800468c8  pop     rbx
0x1800468c9  pop     rbp
0x1800468ca  retn
```
