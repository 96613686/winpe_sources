# DuplicateDaclWithSpecialPermission(_ACL *,void * *,ulong,bool,_ACL * *)

- ea: `0x1400705dc`
- end: `0x140070829`
- name: `?DuplicateDaclWithSpecialPermission@@YAKPEAU_ACL@@PEAPEAXK_NPEAPEAU1@@Z`
- size: `589`
- prototype: `unsigned int __usercall@<eax>(PACL pAcl@<rcx>, void **@<rdx>, unsigned int@<r8d>, bool@<r9b>, struct _ACL **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140070ebc`

## callees

- `0x14000b20c`
- `0x14002d0a0`
- `0x14002dd20`
- `0x14002e0dc`
- `0x1400705dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400707ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400707ba`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140070631`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140070631`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1400706eb`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1400706eb`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x140070733`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x140070733`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1400707a3`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1400707a3`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1400706b7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1400706b7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x140070776`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x140070776`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140070660`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140070660`

## pseudocode

```c
DWORD __fastcall DuplicateDaclWithSpecialPermission(PACL pAcl, void **a2, unsigned int a3, char a4, struct _ACL **a5)
{
  DWORD v8; // edi
  __int64 i; // rbx
  DWORD LengthSid; // eax
  struct _ACL *v11; // rsi
  char v12; // r14
  DWORD j; // edi
  __int64 k; // rbx
  unsigned __int16 *v15; // r9
  __int64 m; // rbx
  DWORD LastError; // ebx
  struct _ACL *v19; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-30h] BYREF
  PACL pAcla; // [rsp+48h] [rbp-28h]
  __int64 pAclInformation; // [rsp+50h] [rbp-20h] BYREF
  int v23; // [rsp+58h] [rbp-18h]

  pAcla = pAcl;
  pAclInformation = 0;
  v23 = 0;
  if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
    return GetLastError();
  v8 = HIDWORD(pAclInformation);
  for ( i = 0; (unsigned int)i < a3; v8 += LengthSid + 12 )
  {
    LengthSid = GetLengthSid(a2[i]);
    i = (unsigned int)(i + 1);
  }
  v19 = 0;
  v11 = (struct _ACL *)operator new[](v8);
  NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&v19);
  if ( v11 )
  {
    v19 = v11;
    memset_0(v11, 0, v8);
    if ( !InitializeAcl(v11, v8, 2u) )
    {
LABEL_24:
      LastError = GetLastError();
      NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&v19);
      return LastError;
    }
    v12 = 0;
    for ( j = 0; ; ++j )
    {
      if ( j >= (unsigned int)pAclInformation )
      {
        *a5 = v11;
        v19 = 0;
        NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&v19);
        return 0;
      }
      pAce = 0;
      if ( !GetAce(pAcla, j, &pAce) )
        goto LABEL_24;
      if ( !v12 )
      {
        if ( a4 )
        {
          v12 = 1;
          for ( k = 0; (unsigned int)k < a3; k = (unsigned int)(k + 1) )
          {
            if ( !AddAccessDeniedAceEx(v11, 2u, 3u, 0xF003Fu, a2[k]) )
              goto LABEL_24;
          }
        }
        else
        {
          v15 = (unsigned __int16 *)pAce;
          if ( *(_BYTE *)pAce == 6 )
            goto LABEL_22;
          v12 = 1;
          for ( m = 0; (unsigned int)m < a3; m = (unsigned int)(m + 1) )
          {
            if ( !AddAccessAllowedAceEx(v11, 2u, 3u, 0x20019u, a2[m]) )
              goto LABEL_24;
          }
        }
      }
      v15 = (unsigned __int16 *)pAce;
LABEL_22:
      if ( !AddAce(v11, 2u, 0xFFFFFFFF, v15, v15[1]) )
        goto LABEL_24;
    }
  }
  v19 = 0;
  NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&v19);
  return 8;
}

```

## disassembly

```asm
0x1400705dc  mov     [rsp-38h+arg_10], rbx
0x1400705e1  push    rbp
0x1400705e2  push    rsi
0x1400705e3  push    rdi
0x1400705e4  push    r12
0x1400705e6  push    r13
0x1400705e8  push    r14
0x1400705ea  push    r15
0x1400705ec  mov     rbp, rsp
0x1400705ef  sub     rsp, 70h
0x1400705f3  mov     rax, cs:__security_cookie
0x1400705fa  xor     rax, rsp
0x1400705fd  mov     [rbp+var_10], rax
0x140070601  mov     r13, [rbp+arg_20]
0x140070605  mov     rax, rcx
0x140070608  mov     [rbp+pAcl], rcx
0x14007060c  mov     r15d, r8d
0x14007060f  xor     ecx, ecx
0x140070611  mov     [rbp+var_40], r9b
0x140070615  mov     r12, rdx
0x140070618  mov     [rbp+pAclInformation], rcx
0x14007061c  mov     [rbp+var_18], ecx
0x14007061f  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x140070623  lea     r14d, [rcx+2]
0x140070627  lea     r8d, [rcx+0Ch]; nAclInformationLength
0x14007062b  mov     r9d, r14d; dwAclInformationClass
0x14007062e  mov     rcx, rax; pAcl
0x140070631  call    cs:__imp_GetAclInformation
0x140070638  nop     dword ptr [rax+rax+00h]
0x14007063d  test    eax, eax
0x14007063f  jnz     short loc_140070652
0x140070641  call    cs:__imp_GetLastError
0x140070648  nop     dword ptr [rax+rax+00h]
0x14007064d  jmp     loc_140070804
0x140070652  mov     edi, dword ptr [rbp+pAclInformation+4]
0x140070655  xor     ebx, ebx
0x140070657  test    r15d, r15d
0x14007065a  jz      short loc_140070678
0x14007065c  mov     rcx, [r12+rbx*8]; pSid
0x140070660  call    cs:__imp_GetLengthSid
0x140070667  nop     dword ptr [rax+rax+00h]
0x14007066c  add     edi, 0Ch
0x14007066f  inc     ebx
0x140070671  add     edi, eax
0x140070673  cmp     ebx, r15d
0x140070676  jb      short loc_14007065C
0x140070678  mov     ecx, edi; unsigned __int64
0x14007067a  mov     ebx, edi
0x14007067c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140070681  lea     rcx, [rbp+var_38]
0x140070685  mov     [rbp+var_38], 0
0x14007068d  mov     rsi, rax
0x140070690  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x140070695  test    rsi, rsi
0x140070698  jz      loc_1400707EE
0x14007069e  mov     r8d, ebx; Size
0x1400706a1  mov     [rbp+var_38], rsi
0x1400706a5  xor     edx, edx; Val
0x1400706a7  mov     rcx, rsi; void *
0x1400706aa  call    memset_0
0x1400706af  mov     r8d, r14d; dwAclRevision
0x1400706b2  mov     edx, edi; nAclLength
0x1400706b4  mov     rcx, rsi; pAcl
0x1400706b7  call    cs:__imp_InitializeAcl
0x1400706be  nop     dword ptr [rax+rax+00h]
0x1400706c3  test    eax, eax
0x1400706c5  jz      loc_1400707BA
0x1400706cb  xor     r14b, r14b
0x1400706ce  xor     edi, edi
0x1400706d0  cmp     edi, dword ptr [rbp+pAclInformation]
0x1400706d3  jnb     loc_1400707D5
0x1400706d9  mov     rcx, [rbp+pAcl]; pAcl
0x1400706dd  lea     r8, [rbp+pAce]; pAce
0x1400706e1  mov     edx, edi; dwAceIndex
0x1400706e3  mov     [rbp+pAce], 0
0x1400706eb  call    cs:__imp_GetAce
0x1400706f2  nop     dword ptr [rax+rax+00h]
0x1400706f7  test    eax, eax
0x1400706f9  jz      loc_1400707BA
0x1400706ff  test    r14b, r14b
0x140070702  jnz     loc_14007078A
0x140070708  cmp     [rbp+var_40], r14b
0x14007070c  jz      short loc_140070747
0x14007070e  mov     r14b, 1
0x140070711  xor     ebx, ebx
0x140070713  cmp     ebx, r15d
0x140070716  jnb     short loc_14007078A
0x140070718  mov     rcx, [r12+rbx*8]
0x14007071c  mov     edx, 2; dwAceRevision
0x140070721  mov     [rsp+70h+pSid], rcx; pSid
0x140070726  mov     r9d, 0F003Fh; AccessMask
0x14007072c  mov     rcx, rsi; pAcl
0x14007072f  lea     r8d, [rdx+1]; AceFlags
0x140070733  call    cs:__imp_AddAccessDeniedAceEx
0x14007073a  nop     dword ptr [rax+rax+00h]
0x14007073f  test    eax, eax
0x140070741  jz      short loc_1400707BA
0x140070743  inc     ebx
0x140070745  jmp     short loc_140070713
0x140070747  mov     r9, [rbp+pAce]
0x14007074b  cmp     byte ptr [r9], 6
0x14007074f  jz      short loc_14007078E
0x140070751  mov     r14b, 1
0x140070754  xor     ebx, ebx
0x140070756  cmp     ebx, r15d
0x140070759  jnb     short loc_14007078A
0x14007075b  mov     rcx, [r12+rbx*8]
0x14007075f  mov     edx, 2; dwAceRevision
0x140070764  mov     [rsp+70h+pSid], rcx; pSid
0x140070769  mov     r9d, 20019h; AccessMask
0x14007076f  mov     rcx, rsi; pAcl
0x140070772  lea     r8d, [rdx+1]; AceFlags
0x140070776  call    cs:__imp_AddAccessAllowedAceEx
0x14007077d  nop     dword ptr [rax+rax+00h]
0x140070782  test    eax, eax
0x140070784  jz      short loc_1400707BA
0x140070786  inc     ebx
0x140070788  jmp     short loc_140070756
0x14007078a  mov     r9, [rbp+pAce]; pAceList
0x14007078e  movzx   eax, word ptr [r9+2]
0x140070793  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x140070797  mov     edx, 2; dwAceRevision
0x14007079c  mov     dword ptr [rsp+70h+pSid], eax; nAceListLength
0x1400707a0  mov     rcx, rsi; pAcl
0x1400707a3  call    cs:__imp_AddAce
0x1400707aa  nop     dword ptr [rax+rax+00h]
0x1400707af  test    eax, eax
0x1400707b1  jz      short loc_1400707BA
0x1400707b3  inc     edi
0x1400707b5  jmp     loc_1400706D0
0x1400707ba  call    cs:__imp_GetLastError
0x1400707c1  nop     dword ptr [rax+rax+00h]
0x1400707c6  lea     rcx, [rbp+var_38]
0x1400707ca  mov     ebx, eax
0x1400707cc  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x1400707d1  mov     eax, ebx
0x1400707d3  jmp     short loc_140070804
0x1400707d5  lea     rcx, [rbp+var_38]
0x1400707d9  mov     [r13+0], rsi
0x1400707dd  mov     [rbp+var_38], 0
0x1400707e5  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x1400707ea  xor     eax, eax
0x1400707ec  jmp     short loc_140070804
0x1400707ee  lea     rcx, [rbp+var_38]
0x1400707f2  mov     [rbp+var_38], 0
0x1400707fa  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x1400707ff  mov     eax, 8
0x140070804  mov     rcx, [rbp+var_10]
0x140070808  xor     rcx, rsp; StackCookie
0x14007080b  call    __security_check_cookie
0x140070810  mov     rbx, [rsp+70h+arg_10]
0x140070818  add     rsp, 70h
0x14007081c  pop     r15
0x14007081e  pop     r14
0x140070820  pop     r13
0x140070822  pop     r12
0x140070824  pop     rdi
0x140070825  pop     rsi
0x140070826  pop     rbp
0x140070827  retn
```
