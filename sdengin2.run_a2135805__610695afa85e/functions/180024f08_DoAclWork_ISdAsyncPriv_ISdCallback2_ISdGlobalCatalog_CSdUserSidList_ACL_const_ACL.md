# DoAclWork(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,_ACL * const,_ACL * *)

- ea: `0x180024f08`
- end: `0x1800252ea`
- name: `?DoAclWork@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAU_ACL@@PEAPEAU5@@Z`
- size: `994`
- prototype: `__int64 __fastcall(struct ISdAsyncPriv *, struct ISdCallback2 *, struct ISdGlobalCatalog *, struct CSdUserSidList *, PACL pAcl, struct _ACL **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180023224`

## callees

- `0x180008370`
- `0x1800083a0`
- `0x180024f08`
- `0x1800255bc`
- `0x180027a9c`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800cf5c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800250f2`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800250f2`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180025023`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180025023`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180025156`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180025156`
- `ole32!CoTaskMemFree` at `0x18002528a`
- `ole32!CoTaskMemFree` at `0x18002528a`
- `ole32!CoTaskMemAlloc` at `0x1800250c0`
- `ole32!CoTaskMemAlloc` at `0x1800250c0`

## string_xrefs

- `0x180024f69`: `DoAclWork`

## pseudocode

```c
__int64 __fastcall DoAclWork(
        struct ISdAsyncPriv *a1,
        struct ISdCallback2 *a2,
        struct ISdGlobalCatalog *a3,
        struct CSdUserSidList *a4,
        PACL pAcl,
        struct _ACL **a6)
{
  struct _ACL *v10; // r15
  __int16 v11; // ax
  __int64 v12; // rcx
  __int64 v13; // r9
  DWORD v14; // r13d
  DWORD v15; // esi
  struct _ACL *v16; // rax
  struct _ACL *v17; // rbx
  __int64 v18; // rcx
  __int16 v19; // ax
  DWORD i; // r12d
  __int64 v21; // rcx
  _BYTE *v22; // r15
  unsigned int v23; // esi
  BYTE v24; // dl
  bool v25; // sf
  unsigned int v26; // ebx
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v30; // [rsp+4Ch] [rbp-B4h]
  __int16 v31; // [rsp+4Eh] [rbp-B2h]
  LPVOID pAce; // [rsp+80h] [rbp-80h] BYREF
  struct CSdUserSidList *v33; // [rsp+88h] [rbp-78h]
  struct ISdGlobalCatalog *v34; // [rsp+90h] [rbp-70h]
  struct ISdCallback2 *v35; // [rsp+98h] [rbp-68h]
  struct ISdAsyncPriv *v36; // [rsp+A0h] [rbp-60h]
  PACL v37; // [rsp+A8h] [rbp-58h]
  __int64 pAclInformation; // [rsp+B0h] [rbp-50h] BYREF
  int v39; // [rsp+B8h] [rbp-48h]
  _BYTE v40[80]; // [rsp+C0h] [rbp-40h] BYREF

  v33 = a4;
  v34 = a3;
  v35 = a2;
  v36 = a1;
  v10 = pAcl;
  v37 = pAcl;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "DoAclWork", 0x224u, 1u);
  pAclInformation = 0;
  v39 = 0;
  pAce = 0;
  v28 = 0;
  if ( a6 )
    *a6 = 0;
  v11 = 567;
  if ( !a1 )
    goto LABEL_39;
  v30 = 567;
  v11 = 568;
  if ( !a2 )
    goto LABEL_39;
  v30 = 568;
  v11 = 569;
  if ( !a3 || (v30 = 569, v11 = 570, !a4) || (v30 = 570, v11 = 571, !pAcl) || (v30 = 571, v11 = 572, !a6) )
  {
LABEL_39:
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_40;
  }
  LastFailureAsHRESULT = 0;
  v30 = 572;
  if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12);
    v11 = 574;
LABEL_40:
    v31 = v11;
    goto LABEL_41;
  }
  LastFailureAsHRESULT = 0;
  v30 = 574;
  v14 = pAclInformation;
  v15 = 80 * pAclInformation + 8;
  if ( v15 <= 0xFFFC )
  {
    v16 = (struct _ACL *)CoTaskMemAlloc(v15);
    v17 = v16;
    if ( v16 )
    {
      LastFailureAsHRESULT = 0;
      v30 = 591;
      if ( InitializeAcl(v16, v15, 2u) )
      {
        LastFailureAsHRESULT = 0;
        v30 = 594;
        for ( i = 0; i < v14; ++i )
        {
          v28 = 0;
          if ( !GetAce(v10, i, &pAce) )
          {
            LastFailureAsHRESULT = GetLastFailureAsHRESULT(v21);
            v31 = 601;
            goto LABEL_36;
          }
          LastFailureAsHRESULT = 0;
          v30 = 601;
          v22 = pAce;
          v23 = *(unsigned __int8 *)pAce;
          if ( (unsigned __int8)v23 <= 3u || (_BYTE)v23 == 17 )
          {
            LastFailureAsHRESULT = DoSidWork(v36, v35, v34, v33, (char *)pAce + 8, v40, 0x44u, &v28);
            v19 = 608;
            if ( LastFailureAsHRESULT < 0 )
              goto LABEL_19;
            v30 = 608;
            v24 = v22[1];
            if ( v28 )
            {
              LastFailureAsHRESULT = SxAddKnownAce(v17, v24, *((_DWORD *)pAce + 1), v40, v23);
              v25 = LastFailureAsHRESULT < 0;
              v19 = 622;
            }
            else
            {
              LastFailureAsHRESULT = SxAddKnownAce(v17, v24, *((_DWORD *)pAce + 1), (char *)pAce + 8, v23);
              v25 = LastFailureAsHRESULT < 0;
              v19 = 626;
            }
            if ( v25 )
              goto LABEL_19;
            v30 = v19;
          }
          else
          {
            v28 = 0;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, v23);
          }
          v10 = v37;
        }
        *a6 = v17;
      }
      else
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v18);
        v19 = 594;
LABEL_19:
        v31 = v19;
LABEL_36:
        CoTaskMemFree(v17);
      }
    }
    else
    {
      LastFailureAsHRESULT = -2147024882;
      v31 = 591;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, v13);
    *a6 = 0;
    LastFailureAsHRESULT = 1;
    v30 = 587;
  }
LABEL_41:
  v26 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v26;
}

```

## disassembly

```asm
0x180024f08  push    rbp
0x180024f0a  push    rbx
0x180024f0b  push    rsi
0x180024f0c  push    rdi
0x180024f0d  push    r12
0x180024f0f  push    r13
0x180024f11  push    r14
0x180024f13  push    r15
0x180024f15  lea     rbp, [rsp-28h]
0x180024f1a  sub     rsp, 128h
0x180024f21  mov     rax, cs:__security_cookie
0x180024f28  xor     rax, rsp
0x180024f2b  mov     [rbp+60h+var_50], rax
0x180024f2f  mov     r12, r9
0x180024f32  mov     [rbp+60h+var_D8], r9
0x180024f36  mov     r14, r8
0x180024f39  mov     [rbp+60h+var_D0], r8
0x180024f3d  mov     rsi, rdx
0x180024f40  mov     [rbp+60h+var_C8], rdx
0x180024f44  mov     rbx, rcx
0x180024f47  mov     [rbp+60h+var_C0], rcx
0x180024f4b  mov     r15, [rbp+60h+pAcl]
0x180024f52  mov     [rbp+60h+var_B8], r15
0x180024f56  mov     rdi, [rbp+60h+arg_28]
0x180024f5d  mov     r9d, 1; unsigned __int16
0x180024f63  mov     r8d, 224h; unsigned __int16
0x180024f69  lea     rdx, aDoaclwork; "DoAclWork"
0x180024f70  lea     rcx, [rsp+160h+var_118]; this
0x180024f75  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180024f7a  xor     eax, eax
0x180024f7c  mov     [rbp+60h+pAclInformation], rax
0x180024f80  mov     [rbp+60h+var_A8], eax
0x180024f83  xor     r13d, r13d
0x180024f86  mov     [rbp+60h+pAce], r13
0x180024f8a  mov     [rsp+160h+var_120], r13d
0x180024f8f  test    rdi, rdi
0x180024f92  jz      short loc_180024F97
0x180024f94  mov     [rdi], r13
0x180024f97  mov     eax, 237h
0x180024f9c  test    rbx, rbx
0x180024f9f  jz      loc_1800252AC
0x180024fa5  mov     [rsp+160h+var_114], ax
0x180024faa  mov     eax, 238h
0x180024faf  test    rsi, rsi
0x180024fb2  jz      loc_1800252AC
0x180024fb8  mov     [rsp+160h+var_114], ax
0x180024fbd  mov     eax, 239h
0x180024fc2  test    r14, r14
0x180024fc5  jz      loc_1800252AC
0x180024fcb  mov     [rsp+160h+var_114], ax
0x180024fd0  mov     eax, 23Ah
0x180024fd5  test    r12, r12
0x180024fd8  jz      loc_1800252AC
0x180024fde  mov     [rsp+160h+var_114], ax
0x180024fe3  mov     eax, 23Bh
0x180024fe8  test    r15, r15
0x180024feb  jz      loc_1800252AC
0x180024ff1  mov     [rsp+160h+var_114], ax
0x180024ff6  mov     eax, 23Ch
0x180024ffb  test    rdi, rdi
0x180024ffe  jz      loc_1800252AC
0x180025004  mov     [rsp+160h+var_118], r13d
0x180025009  mov     [rsp+160h+var_114], ax
0x18002500e  mov     r12d, 2
0x180025014  mov     r9d, r12d; dwAclInformationClass
0x180025017  lea     r8d, [r12+0Ah]; nAclInformationLength
0x18002501c  lea     rdx, [rbp+60h+pAclInformation]; pAclInformation
0x180025020  mov     rcx, r15; pAcl
0x180025023  call    cs:__imp_GetAclInformation
0x18002502a  nop     dword ptr [rax+rax+00h]
0x18002502f  test    eax, eax
0x180025031  jnz     short loc_180025046
0x180025033  call    GetLastFailureAsHRESULT
0x180025038  mov     [rsp+160h+var_118], eax
0x18002503c  mov     eax, 23Eh
0x180025041  jmp     loc_1800252B4
0x180025046  mov     [rsp+160h+var_118], r13d
0x18002504b  mov     eax, 23Eh
0x180025050  mov     [rsp+160h+var_114], ax
0x180025055  mov     r13d, dword ptr [rbp+60h+pAclInformation]
0x180025059  lea     esi, ds:0[r13*4]
0x180025061  add     esi, r13d
0x180025064  shl     esi, 4
0x180025067  add     esi, 8
0x18002506a  cmp     esi, 0FFFCh
0x180025070  jbe     short loc_1800250BE
0x180025072  lea     r14, WPP_GLOBAL_Control
0x180025079  mov     rcx, cs:WPP_GLOBAL_Control
0x180025080  cmp     rcx, r14
0x180025083  jz      short loc_1800250A0
0x180025085  test    [rcx+1Ch], r12b
0x180025089  jz      short loc_1800250A0
0x18002508b  mov     edx, 14h
0x180025090  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x180025097  mov     rcx, [rcx+10h]
0x18002509b  call    WPP_SF_
0x1800250a0  mov     qword ptr [rdi], 0
0x1800250a7  mov     [rsp+160h+var_118], 1
0x1800250af  mov     eax, 24Bh
0x1800250b4  mov     [rsp+160h+var_114], ax
0x1800250b9  jmp     loc_1800252B9
0x1800250be  mov     ecx, esi; cb
0x1800250c0  call    cs:__imp_CoTaskMemAlloc
0x1800250c7  nop     dword ptr [rax+rax+00h]
0x1800250cc  mov     rbx, rax
0x1800250cf  mov     ecx, 24Fh
0x1800250d4  test    rax, rax
0x1800250d7  jz      loc_18002529D
0x1800250dd  mov     [rsp+160h+var_118], 0
0x1800250e5  mov     [rsp+160h+var_114], cx
0x1800250ea  mov     r8d, r12d; dwAclRevision
0x1800250ed  mov     edx, esi; nAclLength
0x1800250ef  mov     rcx, rax; pAcl
0x1800250f2  call    cs:__imp_InitializeAcl
0x1800250f9  nop     dword ptr [rax+rax+00h]
0x1800250fe  test    eax, eax
0x180025100  jnz     short loc_18002511A
0x180025102  call    GetLastFailureAsHRESULT
0x180025107  mov     [rsp+160h+var_118], eax
0x18002510b  mov     eax, 252h
0x180025110  mov     [rsp+160h+var_112], ax
0x180025115  jmp     loc_180025287
0x18002511a  mov     [rsp+160h+var_118], 0
0x180025122  mov     eax, 252h
0x180025127  mov     [rsp+160h+var_114], ax
0x18002512c  xor     r12d, r12d
0x18002512f  lea     r14, WPP_GLOBAL_Control
0x180025136  mov     esi, 259h
0x18002513b  cmp     r12d, r13d
0x18002513e  jnb     loc_180025298
0x180025144  mov     [rsp+160h+var_120], 0
0x18002514c  lea     r8, [rbp+60h+pAce]; pAce
0x180025150  mov     edx, r12d; dwAceIndex
0x180025153  mov     rcx, r15; pAcl
0x180025156  call    cs:__imp_GetAce
0x18002515d  nop     dword ptr [rax+rax+00h]
0x180025162  test    eax, eax
0x180025164  jz      loc_180025279
0x18002516a  mov     [rsp+160h+var_118], 0
0x180025172  mov     [rsp+160h+var_114], si
0x180025177  mov     r15, [rbp+60h+pAce]
0x18002517b  movzx   esi, byte ptr [r15]
0x18002517f  cmp     sil, 3
0x180025183  jbe     short loc_1800251CA
0x180025185  cmp     sil, 11h
0x180025189  jz      short loc_1800251CA
0x18002518b  mov     [rsp+160h+var_120], 0
0x180025193  mov     rcx, cs:WPP_GLOBAL_Control
0x18002519a  cmp     rcx, r14
0x18002519d  jz      loc_18002526D
0x1800251a3  test    byte ptr [rcx+1Ch], 80h
0x1800251a7  jz      loc_18002526D
0x1800251ad  mov     r9d, esi
0x1800251b0  mov     edx, 15h
0x1800251b5  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x1800251bc  mov     rcx, [rcx+10h]
0x1800251c0  call    WPP_SF_d
0x1800251c5  jmp     loc_18002526D
0x1800251ca  lea     rax, [r15+8]
0x1800251ce  lea     rcx, [rsp+160h+var_120]
0x1800251d3  mov     [rsp+160h+var_128], rcx; int *
0x1800251d8  mov     [rsp+160h+var_130], 44h ; 'D'; unsigned int
0x1800251e0  lea     rcx, [rbp+60h+var_A0]
0x1800251e4  mov     [rsp+160h+var_138], rcx; void *
0x1800251e9  mov     [rsp+160h+pSid], rax; pSid
0x1800251ee  mov     r9, [rbp+60h+var_D8]; struct CSdUserSidList *
0x1800251f2  mov     r8, [rbp+60h+var_D0]; struct ISdGlobalCatalog *
0x1800251f6  mov     rdx, [rbp+60h+var_C8]; struct ISdCallback2 *
0x1800251fa  mov     rcx, [rbp+60h+var_C0]; struct ISdAsyncPriv *
0x1800251fe  call    ?DoSidWork@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAXPEAXKPEAH@Z; DoSidWork(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,void * const,void *,ulong,int *)
0x180025203  mov     [rsp+160h+var_118], eax
0x180025207  test    eax, eax
0x180025209  mov     eax, 260h
0x18002520e  js      loc_180025110
0x180025214  mov     [rsp+160h+var_114], ax
0x180025219  mov     byte ptr [rsp+160h+pSid], sil; unsigned __int8
0x18002521e  mov     r8, [rbp+60h+pAce]
0x180025222  mov     dl, [r15+1]; unsigned __int8
0x180025226  mov     rcx, rbx; pAcl
0x180025229  cmp     [rsp+160h+var_120], 0
0x18002522e  jz      short loc_18002524A
0x180025230  lea     r9, [rbp+60h+var_A0]; void *
0x180025234  mov     r8d, [r8+4]; unsigned int
0x180025238  call    ?SxAddKnownAce@@YAJPEAU_ACL@@EKQEAXE@Z; SxAddKnownAce(_ACL *,uchar,ulong,void * const,uchar)
0x18002523d  mov     [rsp+160h+var_118], eax
0x180025241  test    eax, eax
0x180025243  mov     eax, 26Eh
0x180025248  jmp     short loc_180025262
0x18002524a  lea     r9, [r8+8]; void *
0x18002524e  mov     r8d, [r8+4]; unsigned int
0x180025252  call    ?SxAddKnownAce@@YAJPEAU_ACL@@EKQEAXE@Z; SxAddKnownAce(_ACL *,uchar,ulong,void * const,uchar)
0x180025257  mov     [rsp+160h+var_118], eax
0x18002525b  test    eax, eax
0x18002525d  mov     eax, 272h
0x180025262  js      loc_180025110
0x180025268  mov     [rsp+160h+var_114], ax
0x18002526d  inc     r12d
0x180025270  mov     r15, [rbp+60h+var_B8]
0x180025274  jmp     loc_180025136
0x180025279  call    GetLastFailureAsHRESULT
0x18002527e  mov     [rsp+160h+var_118], eax
0x180025282  mov     [rsp+160h+var_112], si
0x180025287  mov     rcx, rbx; pv
0x18002528a  call    cs:__imp_CoTaskMemFree
0x180025291  nop     dword ptr [rax+rax+00h]
0x180025296  jmp     short loc_1800252B9
0x180025298  mov     [rdi], rbx
0x18002529b  jmp     short loc_1800252B9
0x18002529d  mov     [rsp+160h+var_118], 8007000Eh
0x1800252a5  mov     [rsp+160h+var_112], cx
0x1800252aa  jmp     short loc_1800252B9
0x1800252ac  mov     [rsp+160h+var_118], 80070057h
0x1800252b4  mov     [rsp+160h+var_112], ax
0x1800252b9  mov     ebx, [rsp+160h+var_118]
0x1800252bd  lea     rcx, [rsp+160h+var_118]; this
0x1800252c2  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800252c7  mov     eax, ebx
0x1800252c9  mov     rcx, [rbp+60h+var_50]
0x1800252cd  xor     rcx, rsp; StackCookie
0x1800252d0  call    __security_check_cookie
0x1800252d5  add     rsp, 128h
0x1800252dc  pop     r15
0x1800252de  pop     r14
0x1800252e0  pop     r13
0x1800252e2  pop     r12
0x1800252e4  pop     rdi
0x1800252e5  pop     rsi
0x1800252e6  pop     rbx
0x1800252e7  pop     rbp
0x1800252e8  retn
```
