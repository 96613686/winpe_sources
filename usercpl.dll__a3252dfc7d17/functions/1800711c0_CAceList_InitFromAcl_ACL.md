# CAceList::_InitFromAcl(_ACL *)

- ea: `0x1800711c0`
- end: `0x180071452`
- name: `?_InitFromAcl@CAceList@@AEAAJPEAU_ACL@@@Z`
- size: `658`
- prototype: `__int64 __fastcall(CAceList *this, struct _ACL *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800707a0`

## callees

- `0x180002ae4`
- `0x18000dafc`
- `0x180063b30`
- `0x180070f18`
- `0x18007104c`
- `0x1800711c0`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800711eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007121d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071248`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800711eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007121d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071248`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180071204`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007122e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180071259`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180071204`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007122e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180071259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800713e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800713e9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180071332`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180071332`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800712c3`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800712c3`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180071299`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180071299`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800713c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800713ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800713c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800713ca`

## pseudocode

```c
__int64 __fastcall CAceList::_InitFromAcl(CAceList *this, struct _ACL *a2)
{
  HANDLE ProcessHeap; // rbx
  _DWORD *v5; // rax
  HANDLE v6; // rbx
  _DWORD *v7; // rax
  HANDLE v8; // rbx
  _QWORD *v9; // rax
  int v10; // ebx
  DWORD v11; // ebp
  char *v12; // r15
  _QWORD *v13; // rax
  _QWORD *v14; // rdi
  unsigned __int8 v15; // cl
  DWORD LengthSid; // eax
  char *v17; // rdx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  HDPA *v21; // rdx
  signed int LastError; // eax
  LPVOID pAce; // [rsp+40h] [rbp-48h] BYREF
  __int64 pAclInformation; // [rsp+48h] [rbp-40h] BYREF
  int v26; // [rsp+50h] [rbp-38h]

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 8u, 0x20u);
  if ( !v5 )
  {
    *(_QWORD *)this = 0;
    return (unsigned int)-2147024882;
  }
  v5[7] = 8;
  *((_QWORD *)v5 + 2) = ProcessHeap;
  *(_QWORD *)this = v5;
  v6 = GetProcessHeap();
  v7 = HeapAlloc(v6, 8u, 0x20u);
  if ( !v7 )
  {
    *((_QWORD *)this + 1) = 0;
    return (unsigned int)-2147024882;
  }
  v7[7] = 8;
  *((_QWORD *)v7 + 2) = v6;
  *((_QWORD *)this + 1) = v7;
  v8 = GetProcessHeap();
  v9 = HeapAlloc(v8, 8u, 0x20u);
  if ( !v9 )
  {
    *((_QWORD *)this + 2) = 0;
    return (unsigned int)-2147024882;
  }
  v9[2] = v8;
  v10 = 0;
  *((_DWORD *)v9 + 7) = 8;
  *((_QWORD *)this + 2) = v9;
  if ( a2 )
  {
    pAclInformation = 0;
    v26 = 0;
    GetAclInformation(a2, &pAclInformation, 0xCu, AclSizeInformation);
    v11 = 0;
    do
    {
      if ( v11 >= (unsigned int)pAclInformation )
        return (unsigned int)v10;
      pAce = 0;
      if ( !GetAce(a2, v11, &pAce) )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        if ( v10 >= 0 )
          return (unsigned int)-2147467259;
        return (unsigned int)v10;
      }
      v12 = (char *)pAce;
      v10 = -2147024882;
      v13 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v13;
      if ( !v13 )
        goto LABEL_27;
      *v13 = 0x80000;
      v13[1] = 0;
      v13[2] = 0;
      v13[3] = 0;
      if ( !v12 )
      {
        v10 = -2147024809;
LABEL_26:
        LocalFree((HLOCAL)v14[1]);
        LocalFree((HLOCAL)v14[2]);
        *((_DWORD *)v14 + 7) &= ~0x80000000;
        operator delete(v14);
        goto LABEL_27;
      }
      v15 = *v12;
      if ( *v12 == 9 )
      {
        LengthSid = GetLengthSid(v12 + 8);
        v15 = *v12;
        v17 = &v12[LengthSid + 8];
      }
      else
      {
        v17 = 0;
      }
      v10 = CAce::_Init((CAce *)v14, v12 + 8, *((_DWORD *)v12 + 1), v12[1], v15, *((_WORD *)v12 + 1), v17);
      if ( v10 < 0 )
        goto LABEL_26;
      v18 = *((_DWORD *)v14 + 7);
      v19 = v18 & 0x20;
      if ( (v18 & 0x20) != 0 )
      {
        v20 = v18 & 1;
      }
      else
      {
        v20 = v18 & 1;
        if ( !v20 )
        {
          v21 = (HDPA *)this;
LABEL_22:
          v10 = CAceList::_AddExplicitAceToDpa(v19, v21, v14);
          goto LABEL_25;
        }
      }
      if ( !(_DWORD)v19 && v20 )
      {
        v21 = (HDPA *)((char *)this + 8);
        goto LABEL_22;
      }
      v10 = 0;
      if ( DPA_InsertPtr(*((HDPA *)this + 2), 0x7FFFFFFF, v14) == -1 )
        v10 = -2147024882;
LABEL_25:
      if ( v10 )
        goto LABEL_26;
LABEL_27:
      ++v11;
    }
    while ( v10 >= 0 );
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800711c0  mov     [rsp+arg_10], rbx
0x1800711c5  mov     [rsp+arg_18], rbp
0x1800711ca  push    rsi
0x1800711cb  push    rdi
0x1800711cc  push    r12
0x1800711ce  push    r14
0x1800711d0  push    r15
0x1800711d2  sub     rsp, 60h
0x1800711d6  mov     rax, cs:__security_cookie
0x1800711dd  xor     rax, rsp
0x1800711e0  mov     [rsp+88h+var_30], rax
0x1800711e5  mov     r12, rdx
0x1800711e8  mov     r14, rcx
0x1800711eb  call    cs:__imp_GetProcessHeap
0x1800711f1  mov     esi, 20h ; ' '
0x1800711f6  mov     rcx, rax; hHeap
0x1800711f9  mov     r8d, esi; dwBytes
0x1800711fc  mov     rbx, rax
0x1800711ff  lea     edi, [rsi-18h]
0x180071202  mov     edx, edi; dwFlags
0x180071204  call    cs:__imp_HeapAlloc
0x18007120a  test    rax, rax
0x18007120d  jz      loc_18007141E
0x180071213  mov     [rax+1Ch], edi
0x180071216  mov     [rax+10h], rbx
0x18007121a  mov     [r14], rax
0x18007121d  call    cs:__imp_GetProcessHeap
0x180071223  mov     r8d, esi; dwBytes
0x180071226  mov     edx, edi; dwFlags
0x180071228  mov     rcx, rax; hHeap
0x18007122b  mov     rbx, rax
0x18007122e  call    cs:__imp_HeapAlloc
0x180071234  test    rax, rax
0x180071237  jz      loc_180071414
0x18007123d  mov     [rax+1Ch], edi
0x180071240  mov     [rax+10h], rbx
0x180071244  mov     [r14+8], rax
0x180071248  call    cs:__imp_GetProcessHeap
0x18007124e  mov     r8d, esi; dwBytes
0x180071251  mov     edx, edi; dwFlags
0x180071253  mov     rcx, rax; hHeap
0x180071256  mov     rbx, rax
0x180071259  call    cs:__imp_HeapAlloc
0x18007125f  test    rax, rax
0x180071262  jz      loc_18007140A
0x180071268  mov     [rax+10h], rbx
0x18007126c  xor     ebx, ebx
0x18007126e  mov     [rax+1Ch], edi
0x180071271  mov     [r14+10h], rax
0x180071275  test    r12, r12
0x180071278  jz      loc_18007142A
0x18007127e  xor     eax, eax
0x180071280  lea     r9d, [rsi-1Eh]; dwAclInformationClass
0x180071284  lea     r8d, [rsi-14h]; nAclInformationLength
0x180071288  mov     [rsp+88h+pAclInformation], rax
0x18007128d  lea     rdx, [rsp+88h+pAclInformation]; pAclInformation
0x180071292  mov     [rsp+88h+var_38], eax
0x180071296  mov     rcx, r12; pAcl
0x180071299  call    cs:__imp_GetAclInformation
0x18007129f  xor     ebp, ebp
0x1800712a1  mov     esi, 8007000Eh
0x1800712a6  cmp     ebp, dword ptr [rsp+88h+pAclInformation]
0x1800712aa  jnb     loc_18007142A
0x1800712b0  lea     r8, [rsp+88h+pAce]; pAce
0x1800712b5  mov     [rsp+88h+pAce], 0
0x1800712be  mov     edx, ebp; dwAceIndex
0x1800712c0  mov     rcx, r12; pAcl
0x1800712c3  call    cs:__imp_GetAce
0x1800712c9  test    eax, eax
0x1800712cb  jz      loc_1800713E9
0x1800712d1  mov     r15, [rsp+88h+pAce]
0x1800712d6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800712dd  mov     ecx, 20h ; ' '; unsigned __int64
0x1800712e2  mov     ebx, esi
0x1800712e4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800712e9  mov     rdi, rax
0x1800712ec  test    rax, rax
0x1800712ef  jz      loc_1800713DD
0x1800712f5  mov     qword ptr [rax], 80000h
0x1800712fc  mov     qword ptr [rax+8], 0
0x180071304  mov     qword ptr [rax+10h], 0
0x18007130c  mov     qword ptr [rax+18h], 0
0x180071314  test    r15, r15
0x180071317  jnz     short loc_180071323
0x180071319  mov     ebx, 80070057h
0x18007131e  jmp     loc_1800713BC
0x180071323  mov     cl, [r15]
0x180071326  lea     rbx, [r15+8]
0x18007132a  cmp     cl, 9
0x18007132d  jnz     short loc_180071342
0x18007132f  mov     rcx, rbx; pSid
0x180071332  call    cs:__imp_GetLengthSid
0x180071338  mov     cl, [r15]
0x18007133b  mov     edx, eax
0x18007133d  add     rdx, rbx
0x180071340  jmp     short loc_180071344
0x180071342  xor     edx, edx
0x180071344  movzx   eax, word ptr [r15+2]
0x180071349  mov     r9b, [r15+1]; unsigned __int8
0x18007134d  mov     r8d, [r15+4]; unsigned int
0x180071351  mov     [rsp+88h+var_58], rdx; void *
0x180071356  mov     rdx, rbx; void *
0x180071359  mov     [rsp+88h+var_60], ax; unsigned __int16
0x18007135e  mov     [rsp+88h+var_68], cl; unsigned __int8
0x180071362  mov     rcx, rdi; this
0x180071365  call    ?_Init@CAce@@AEAAJPEAXKEEG0@Z; CAce::_Init(void *,ulong,uchar,uchar,ushort,void *)
0x18007136a  mov     ebx, eax
0x18007136c  test    eax, eax
0x18007136e  js      short loc_1800713BC
0x180071370  mov     eax, [rdi+1Ch]
0x180071373  mov     ecx, eax
0x180071375  and     ecx, 20h
0x180071378  jnz     short loc_180071384
0x18007137a  and     eax, 1
0x18007137d  jnz     short loc_180071387
0x18007137f  mov     rdx, r14
0x180071382  jmp     short loc_180071393
0x180071384  and     eax, 1
0x180071387  test    ecx, ecx
0x180071389  jnz     short loc_18007139F
0x18007138b  test    eax, eax
0x18007138d  jz      short loc_18007139F
0x18007138f  lea     rdx, [r14+8]
0x180071393  mov     r8, rdi
0x180071396  call    ?_AddExplicitAceToDpa@CAceList@@AEAAJAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAVCAce@@@Z; CAceList::_AddExplicitAceToDpa(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,CAce *)
0x18007139b  mov     ebx, eax
0x18007139d  jmp     short loc_1800713B8
0x18007139f  mov     rcx, [r14+10h]; hdpa
0x1800713a3  mov     r8, rdi; p
0x1800713a6  mov     edx, 7FFFFFFFh; i
0x1800713ab  call    DPA_InsertPtr
0x1800713b0  xor     ebx, ebx
0x1800713b2  cmp     eax, 0FFFFFFFFh
0x1800713b5  cmovz   ebx, esi
0x1800713b8  test    ebx, ebx
0x1800713ba  jz      short loc_1800713DD
0x1800713bc  mov     rcx, [rdi+8]; hMem
0x1800713c0  call    cs:__imp_LocalFree
0x1800713c6  mov     rcx, [rdi+10h]; hMem
0x1800713ca  call    cs:__imp_LocalFree
0x1800713d0  btr     dword ptr [rdi+1Ch], 1Fh
0x1800713d5  mov     rcx, rdi; lpMem
0x1800713d8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800713dd  inc     ebp
0x1800713df  test    ebx, ebx
0x1800713e1  jns     loc_1800712A6
0x1800713e7  jmp     short loc_18007142A
0x1800713e9  call    cs:__imp_GetLastError
0x1800713ef  mov     ebx, eax
0x1800713f1  test    eax, eax
0x1800713f3  jle     short loc_1800713FE
0x1800713f5  movzx   ebx, ax
0x1800713f8  or      ebx, 80070000h
0x1800713fe  test    ebx, ebx
0x180071400  mov     eax, 80004005h
0x180071405  cmovns  ebx, eax
0x180071408  jmp     short loc_18007142A
0x18007140a  mov     qword ptr [r14+10h], 0
0x180071412  jmp     short loc_180071425
0x180071414  mov     qword ptr [r14+8], 0
0x18007141c  jmp     short loc_180071425
0x18007141e  mov     qword ptr [r14], 0
0x180071425  mov     ebx, 8007000Eh
0x18007142a  mov     eax, ebx
0x18007142c  mov     rcx, [rsp+88h+var_30]
0x180071431  xor     rcx, rsp; StackCookie
0x180071434  call    __security_check_cookie
0x180071439  lea     r11, [rsp+88h+var_28]
0x18007143e  mov     rbx, [r11+40h]
0x180071442  mov     rbp, [r11+48h]
0x180071446  mov     rsp, r11
0x180071449  pop     r15
0x18007144b  pop     r14
0x18007144d  pop     r12
0x18007144f  pop     rdi
0x180071450  pop     rsi
0x180071451  retn
```
