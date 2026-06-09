# UbpmUtilsGetAccountNamesFromSid

- ea: `0x180004240`
- end: `0x1800046ac`
- name: `UbpmUtilsGetAccountNamesFromSid`
- size: `1132`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001fb0`
- `0x1800029d8`
- `0x180003050`
- `0x180004f40`
- `0x1800057b0`
- `0x180006650`
- `0x18000c650`
- `0x180019fb0`

## callees

- `0x180004240`
- `0x18000f9a0`
- `0x180019d90`
- `0x180030cec`
- `0x180032e38`
- `0x18003d7d2`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180004381`
- `ntdll!RtlAllocateHeap` at `0x180004381`
- `ntdll!RtlNtStatusToDosError` at `0x18000447a`
- `ntdll!RtlNtStatusToDosError` at `0x1800044ac`
- `ntdll!RtlNtStatusToDosError` at `0x18000447a`
- `ntdll!RtlNtStatusToDosError` at `0x1800044ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000465e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000465e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupTranslateSids` at `0x1800042d7`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupTranslateSids` at `0x1800042d7`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800042af`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800042af`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18000443a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18000443a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180004419`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000442b`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180004419`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000442b`

## pseudocode

```c
__int64 __fastcall UbpmUtilsGetAccountNamesFromSid(void *a1, int a2, _QWORD *a3, _QWORD *a4, _QWORD *a5)
{
  _WORD *v7; // rsi
  _WORD *v8; // r14
  _WORD *v9; // rbx
  int v11; // eax
  int v12; // eax
  __int64 Use; // r9
  _QWORD *v14; // r15
  PLSA_TRUST_INFORMATION v15; // rcx
  unsigned __int64 v16; // rdi
  SIZE_T v17; // r8
  _WORD *Heap; // rax
  unsigned __int64 v19; // rdi
  ULONG v20; // edi
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  unsigned __int64 Length; // rdi
  PWSTR Buffer; // r15
  _WORD *v26; // rax
  PLSA_TRUST_INFORMATION Domains; // rcx
  size_t v28; // rdi
  PWSTR v29; // r15
  _WORD *v30; // rax
  int v31; // [rsp+38h] [rbp-31h]
  PLSA_TRANSLATED_NAME Names; // [rsp+40h] [rbp-29h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+48h] [rbp-21h] BYREF
  PVOID PolicyHandle; // [rsp+50h] [rbp-19h] BYREF
  void *Src; // [rsp+58h] [rbp-11h]
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  PSID Sids; // [rsp+C8h] [rbp+5Fh] BYREF

  Sids = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ReferencedDomains = 0;
  Names = 0;
  v7 = 0;
  PolicyHandle = 0;
  v8 = 0;
  v9 = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v11 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 0x800u, &PolicyHandle);
  if ( v11 < 0 )
  {
    v20 = RtlNtStatusToDosError(v11);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v23 = 22;
LABEL_41:
    WPP_SF_d(v22[2], v23, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, v20);
    goto LABEL_19;
  }
  v12 = LsaLookupTranslateSids(PolicyHandle, 1u, &Sids, &ReferencedDomains, &Names);
  if ( v12 < 0 )
  {
    v20 = RtlNtStatusToDosError(v12);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v23 = 23;
    goto LABEL_41;
  }
  if ( !ReferencedDomains || !Names )
  {
    v20 = 13;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v23 = 24;
    goto LABEL_41;
  }
  Use = (unsigned int)Names->Use;
  if ( (_DWORD)Use != a2 )
  {
    v20 = 13;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, Use, 13);
    goto LABEL_19;
  }
  if ( Names->DomainIndex < 0 )
  {
    v20 = 13;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v23 = 26;
    goto LABEL_41;
  }
  if ( !ReferencedDomains->Entries )
  {
    v20 = 13;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v23 = 27;
    goto LABEL_41;
  }
  if ( a4 )
  {
    Length = Names->Name.Length;
    Buffer = Names->Name.Buffer;
    v26 = UbpmAlloc((unsigned int)(Length + 2));
    v8 = v26;
    if ( !v26 )
    {
      v20 = 14;
      goto LABEL_19;
    }
    memcpy_0(v26, Buffer, (unsigned int)Length);
    v8[Length >> 1] = 0;
  }
  if ( a3 )
  {
    Domains = ReferencedDomains->Domains;
    v28 = Domains[Names->DomainIndex].Name.Length;
    v29 = Domains[Names->DomainIndex].Name.Buffer;
    v30 = UbpmAlloc((unsigned int)(v28 + 2));
    v7 = v30;
    if ( !v30 )
    {
      v20 = 14;
      goto LABEL_19;
    }
    memcpy_0(v30, v29, v28);
    v7[v28 >> 1] = 0;
  }
  v14 = a5;
  if ( a5 )
  {
    v15 = ReferencedDomains->Domains;
    v16 = v15[Names->DomainIndex].Name.Length;
    v17 = (unsigned int)v16 + Names->Name.Length + 4;
    v31 = v15[Names->DomainIndex].Name.Length;
    Src = v15[Names->DomainIndex].Name.Buffer;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v17);
    v9 = Heap;
    if ( !Heap )
    {
      SetLastError(8u);
      v20 = 14;
      goto LABEL_19;
    }
    memcpy_0(Heap, Src, (unsigned int)v16);
    v19 = v16 >> 1;
    v9[v19] = 92;
    memcpy_0(&v9[v19 + 1], Names->Name.Buffer, Names->Name.Length);
    v9[((unsigned __int64)(v31 + (unsigned int)Names->Name.Length) >> 1) + 1] = 0;
  }
  v20 = 0;
  if ( a4 )
  {
    *a4 = v8;
    v8 = 0;
  }
  if ( a3 )
  {
    *a3 = v7;
    v7 = 0;
  }
  if ( v14 )
  {
    *v14 = v9;
    v9 = 0;
  }
LABEL_19:
  if ( ReferencedDomains )
    LsaLookupFreeMemory(ReferencedDomains);
  if ( Names )
    LsaLookupFreeMemory(Names);
  if ( PolicyHandle )
    LsaLookupClose(PolicyHandle);
  if ( v8 )
    UBPM_MIDL_user_free(v8);
  if ( v7 )
    UBPM_MIDL_user_free(v7);
  if ( v9 )
    UBPM_MIDL_user_free(v9);
  return v20;
}

```

## disassembly

```asm
0x180004240  mov     rax, rsp
0x180004243  mov     [rax+8], rcx
0x180004247  push    rbp
0x180004248  push    rbx
0x180004249  push    rdi
0x18000424a  lea     rbp, [rax-57h]
0x18000424e  sub     rsp, 0A0h
0x180004255  mov     [rax+10h], rsi
0x180004259  lea     rcx, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18000425d  mov     [rax+18h], r12
0x180004261  mov     edi, edx
0x180004263  mov     [rax+20h], r13
0x180004267  xorps   xmm0, xmm0
0x18000426a  mov     [rax-20h], r14
0x18000426e  mov     r13, r8
0x180004271  mov     [rax-28h], r15
0x180004275  lea     r8, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x180004279  xor     eax, eax
0x18000427b  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180004283  mov     edx, 800h; AccessMask
0x180004288  mov     [rbp+4Fh+ReferencedDomains], rax
0x18000428c  mov     [rbp+4Fh+Names], rax
0x180004290  mov     esi, eax
0x180004292  mov     [rbp+4Fh+PolicyHandle], rax
0x180004296  mov     r14d, eax
0x180004299  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], rax
0x18000429d  mov     ebx, eax
0x18000429f  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x1800042a3  mov     r12, r9
0x1800042a6  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1800042aa  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800042af  call    cs:__imp_LsaLookupOpenLocalPolicy
0x1800042b5  test    eax, eax
0x1800042b7  js      loc_180004478
0x1800042bd  mov     rcx, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x1800042c1  lea     rax, [rbp+4Fh+Names]
0x1800042c5  lea     r9, [rbp+4Fh+ReferencedDomains]; ReferencedDomains
0x1800042c9  mov     [rsp+20h], rax; Names
0x1800042ce  lea     r8, [rbp+4Fh+Sids]; Sids
0x1800042d2  mov     edx, 1; Count
0x1800042d7  call    cs:__imp_LsaLookupTranslateSids
0x1800042dd  test    eax, eax
0x1800042df  js      loc_1800044AA
0x1800042e5  cmp     [rbp+4Fh+ReferencedDomains], rbx
0x1800042e9  jz      loc_1800044DC
0x1800042ef  mov     r8, [rbp+4Fh+Names]
0x1800042f3  test    r8, r8
0x1800042f6  jz      loc_1800044DC
0x1800042fc  mov     r9d, [r8]
0x1800042ff  cmp     r9d, edi
0x180004302  jnz     loc_18000451F
0x180004308  mov     rax, r8
0x18000430b  cmp     [rax+18h], ebx
0x18000430e  jl      loc_18000459C
0x180004314  mov     rax, [rbp+4Fh+ReferencedDomains]
0x180004318  cmp     [rax], ebx
0x18000431a  jz      loc_1800045CC
0x180004320  test    r12, r12
0x180004323  jnz     loc_180004563
0x180004329  test    r13, r13
0x18000432c  jnz     loc_180004606
0x180004332  mov     r15, [rbp+4Fh+arg_20]
0x180004336  test    r15, r15
0x180004339  jz      loc_1800043DA
0x18000433f  mov     r8, [rbp+4Fh+Names]
0x180004343  movsxd  rax, dword ptr [r8+18h]
0x180004347  movzx   r8d, word ptr [r8+8]
0x18000434c  add     r8d, 4
0x180004350  lea     rdx, [rax+rax*2]
0x180004354  mov     rax, [rbp+4Fh+ReferencedDomains]
0x180004358  mov     rcx, [rax+8]
0x18000435c  movzx   edi, word ptr [rcx+rdx*8]
0x180004360  mov     rax, [rcx+rdx*8+8]
0x180004365  add     r8d, edi; Size
0x180004368  mov     rcx, gs:60h
0x180004371  mov     edx, 8; Flags
0x180004376  mov     [rbp+4Fh+var_80], edi
0x180004379  mov     [rbp+4Fh+Src], rax
0x18000437d  mov     rcx, [rcx+30h]; HeapHandle
0x180004381  call    cs:__imp_RtlAllocateHeap
0x180004387  mov     rbx, rax
0x18000438a  test    rax, rax
0x18000438d  jz      loc_180004659
0x180004393  mov     rdx, [rbp+4Fh+Src]; Src
0x180004397  mov     r8d, edi; Size
0x18000439a  mov     rcx, rax; void *
0x18000439d  call    memcpy_0
0x1800043a2  shr     rdi, 1
0x1800043a5  mov     word ptr [rbx+rdi*2], 5Ch ; '\'
0x1800043ab  lea     rcx, [rdi+1]
0x1800043af  mov     rdx, [rbp+4Fh+Names]
0x1800043b3  lea     rcx, [rbx+rcx*2]; void *
0x1800043b7  movzx   r8d, word ptr [rdx+8]; Size
0x1800043bc  mov     rdx, [rdx+10h]; Src
0x1800043c0  call    memcpy_0
0x1800043c5  mov     rax, [rbp+4Fh+Names]
0x1800043c9  movzx   edx, word ptr [rax+8]
0x1800043cd  add     edx, [rbp+4Fh+var_80]
0x1800043d0  shr     rdx, 1
0x1800043d3  xor     eax, eax
0x1800043d5  mov     [rbx+rdx*2+2], ax
0x1800043da  xor     edi, edi
0x1800043dc  test    r12, r12
0x1800043df  jnz     loc_18000466E
0x1800043e5  test    r13, r13
0x1800043e8  jnz     loc_18000467A
0x1800043ee  test    r15, r15
0x1800043f1  jz      short loc_1800043F8
0x1800043f3  mov     [r15], rbx
0x1800043f6  xor     ebx, ebx
0x1800043f8  mov     rcx, [rbp+4Fh+ReferencedDomains]; Buffer
0x1800043fc  mov     r15, [rsp+0B0h+var_20]
0x180004404  mov     r13, [rsp+0B0h+arg_18]
0x18000440c  mov     r12, [rsp+0B0h+arg_10]
0x180004414  test    rcx, rcx
0x180004417  jz      short loc_18000441F
0x180004419  call    cs:__imp_LsaLookupFreeMemory
0x18000441f  mov     r8, [rbp+4Fh+Names]
0x180004423  test    r8, r8
0x180004426  jz      short loc_180004431
0x180004428  mov     rcx, r8; Buffer
0x18000442b  call    cs:__imp_LsaLookupFreeMemory
0x180004431  mov     rcx, [rbp+4Fh+PolicyHandle]; ObjectHandle
0x180004435  test    rcx, rcx
0x180004438  jz      short loc_180004440
0x18000443a  call    cs:__imp_LsaLookupClose
0x180004440  test    r14, r14
0x180004443  jnz     loc_180004685
0x180004449  mov     r14, [rsp+98h]
0x180004451  test    rsi, rsi
0x180004454  jnz     loc_180004692
0x18000445a  mov     rsi, [rsp+0B0h+arg_8]
0x180004462  test    rbx, rbx
0x180004465  jnz     loc_18000469F
0x18000446b  mov     eax, edi
0x18000446d  add     rsp, 0A0h
0x180004474  pop     rdi
0x180004475  pop     rbx
0x180004476  pop     rbp
0x180004477  retn
0x180004478  mov     ecx, eax; Status
0x18000447a  call    cs:__imp_RtlNtStatusToDosError
0x180004480  mov     edi, eax
0x180004482  mov     rcx, cs:WPP_GLOBAL_Control
0x180004489  lea     rax, WPP_GLOBAL_Control
0x180004490  cmp     rcx, rax
0x180004493  jz      loc_1800043F8
0x180004499  test    byte ptr [rcx+1Ch], 1
0x18000449d  jz      loc_1800043F8
0x1800044a3  mov     edx, 16h
0x1800044a8  jmp     short loc_180004507
0x1800044aa  mov     ecx, eax; Status
0x1800044ac  call    cs:__imp_RtlNtStatusToDosError
0x1800044b2  mov     edi, eax
0x1800044b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044bb  lea     rax, WPP_GLOBAL_Control
0x1800044c2  cmp     rcx, rax
0x1800044c5  jz      loc_1800043F8
0x1800044cb  test    byte ptr [rcx+1Ch], 1
0x1800044cf  jz      loc_1800043F8
0x1800044d5  mov     edx, 17h
0x1800044da  jmp     short loc_180004507
0x1800044dc  mov     edi, 0Dh
0x1800044e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044e8  lea     rax, WPP_GLOBAL_Control
0x1800044ef  cmp     rcx, rax
0x1800044f2  jz      loc_1800043F8
0x1800044f8  test    byte ptr [rcx+1Ch], 1
0x1800044fc  jz      loc_1800043F8
0x180004502  mov     edx, 18h
0x180004507  mov     rcx, [rcx+10h]
0x18000450b  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180004512  mov     r9d, edi
0x180004515  call    WPP_SF_d
0x18000451a  jmp     loc_1800043F8
0x18000451f  mov     edi, 0Dh
0x180004524  mov     rcx, cs:WPP_GLOBAL_Control
0x18000452b  lea     rax, WPP_GLOBAL_Control
0x180004532  cmp     rcx, rax
0x180004535  jz      loc_1800043F8
0x18000453b  test    byte ptr [rcx+1Ch], 1
0x18000453f  jz      loc_1800043F8
0x180004545  mov     rcx, [rcx+10h]
0x180004549  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180004550  mov     edx, 19h
0x180004555  mov     [rsp+20h], edi
0x180004559  call    WPP_SF_dd
0x18000455e  jmp     loc_1800043F8
0x180004563  mov     rax, [rbp+4Fh+Names]
0x180004567  movzx   edi, word ptr [rax+8]
0x18000456b  mov     r15, [rax+10h]
0x18000456f  lea     ecx, [rdi+2]; Size
0x180004572  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180004577  mov     r14, rax
0x18000457a  test    rax, rax
0x18000457d  jz      short loc_1800045FC
0x18000457f  mov     r8d, edi; Size
0x180004582  mov     rdx, r15; Src
0x180004585  mov     rcx, rax; void *
0x180004588  call    memcpy_0
0x18000458d  shr     rdi, 1
0x180004590  xor     eax, eax
0x180004592  mov     [r14+rdi*2], ax
0x180004597  jmp     loc_180004329
0x18000459c  mov     edi, 0Dh
0x1800045a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045a8  lea     rax, WPP_GLOBAL_Control
0x1800045af  cmp     rcx, rax
0x1800045b2  jz      loc_1800043F8
0x1800045b8  test    byte ptr [rcx+1Ch], 1
0x1800045bc  jz      loc_1800043F8
0x1800045c2  mov     edx, 1Ah
0x1800045c7  jmp     loc_180004507
0x1800045cc  mov     edi, 0Dh
0x1800045d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045d8  lea     rax, WPP_GLOBAL_Control
0x1800045df  cmp     rcx, rax
0x1800045e2  jz      loc_1800043F8
0x1800045e8  test    byte ptr [rcx+1Ch], 1
0x1800045ec  jz      loc_1800043F8
0x1800045f2  mov     edx, 1Bh
0x1800045f7  jmp     loc_180004507
0x1800045fc  mov     edi, 0Eh
0x180004601  jmp     loc_1800043F8
0x180004606  mov     rax, [rbp+4Fh+Names]
0x18000460a  movsxd  rcx, dword ptr [rax+18h]
0x18000460e  mov     rax, [rbp+4Fh+ReferencedDomains]
0x180004612  lea     rdx, [rcx+rcx*2]
0x180004616  mov     rcx, [rax+8]
0x18000461a  movzx   edi, word ptr [rcx+rdx*8]
0x18000461e  mov     r15, [rcx+rdx*8+8]
0x180004623  lea     ecx, [rdi+2]; Size
0x180004626  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18000462b  mov     rsi, rax
0x18000462e  test    rax, rax
0x180004631  jnz     short loc_18000463D
0x180004633  mov     edi, 0Eh
0x180004638  jmp     loc_1800043F8
0x18000463d  mov     r8, rdi; Size
0x180004640  mov     rdx, r15; Src
0x180004643  mov     rcx, rsi; void *
0x180004646  call    memcpy_0
0x18000464b  shr     rdi, 1
0x18000464e  xor     eax, eax
0x180004650  mov     [rsi+rdi*2], ax
0x180004654  jmp     loc_180004332
0x180004659  mov     ecx, 8; dwErrCode
0x18000465e  call    cs:__imp_SetLastError
0x180004664  mov     edi, 0Eh
0x180004669  jmp     loc_1800043F8
0x18000466e  mov     [r12], r14
0x180004672  xor     r14d, r14d
0x180004675  jmp     loc_1800043E5
0x18000467a  mov     [r13+0], rsi
0x18000467e  xor     esi, esi
0x180004680  jmp     loc_1800043EE
0x180004685  mov     rcx, r14
0x180004688  call    UBPM_MIDL_user_free
0x18000468d  jmp     loc_180004449
0x180004692  mov     rcx, rsi
0x180004695  call    UBPM_MIDL_user_free
0x18000469a  jmp     loc_18000445A
0x18000469f  mov     rcx, rbx
0x1800046a2  call    UBPM_MIDL_user_free
0x1800046a7  jmp     loc_18000446B
```
