# DoAclWork(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,_ACL * const,_ACL * *)

- ea: `0x1800240ac`
- end: `0x18002446f`
- name: `?DoAclWork@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAU_ACL@@PEAPEAU5@@Z`
- size: `963`
- prototype: `__int64 __fastcall(struct ISdAsyncPriv *, struct ISdCallback2 *, struct ISdGlobalCatalog *, struct CSdUserSidList *, PACL pAcl, struct _ACL **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180022564`

## callees

- `0x1800081d8`
- `0x180008200`
- `0x1800240ac`
- `0x180024724`
- `0x180026a90`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800c9830`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002428a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002428a`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800241c7`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800241c7`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800242e8`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800242e8`
- `ole32!CoTaskMemFree` at `0x180024416`
- `ole32!CoTaskMemFree` at `0x180024416`
- `ole32!CoTaskMemAlloc` at `0x18002425e`
- `ole32!CoTaskMemAlloc` at `0x18002425e`

## string_xrefs

- `0x18002410d`: `DoAclWork`

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
  DWORD v13; // r13d
  DWORD v14; // esi
  struct _ACL *v15; // rax
  struct _ACL *v16; // rbx
  __int64 v17; // rcx
  __int16 v18; // ax
  DWORD i; // r12d
  __int64 v20; // rcx
  _BYTE *v21; // r15
  unsigned int v22; // esi
  BYTE v23; // dl
  bool v24; // sf
  unsigned int v25; // ebx
  int v27; // [rsp+40h] [rbp-C0h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v29; // [rsp+4Ch] [rbp-B4h]
  __int16 v30; // [rsp+4Eh] [rbp-B2h]
  LPVOID pAce; // [rsp+80h] [rbp-80h] BYREF
  struct CSdUserSidList *v32; // [rsp+88h] [rbp-78h]
  struct ISdGlobalCatalog *v33; // [rsp+90h] [rbp-70h]
  struct ISdCallback2 *v34; // [rsp+98h] [rbp-68h]
  struct ISdAsyncPriv *v35; // [rsp+A0h] [rbp-60h]
  PACL v36; // [rsp+A8h] [rbp-58h]
  __int64 pAclInformation; // [rsp+B0h] [rbp-50h] BYREF
  int v38; // [rsp+B8h] [rbp-48h]
  _BYTE v39[80]; // [rsp+C0h] [rbp-40h] BYREF

  v32 = a4;
  v33 = a3;
  v34 = a2;
  v35 = a1;
  v10 = pAcl;
  v36 = pAcl;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "DoAclWork", 548, 1);
  pAclInformation = 0;
  v38 = 0;
  pAce = 0;
  v27 = 0;
  if ( a6 )
    *a6 = 0;
  v11 = 567;
  if ( !a1 )
    goto LABEL_39;
  v29 = 567;
  v11 = 568;
  if ( !a2 )
    goto LABEL_39;
  v29 = 568;
  v11 = 569;
  if ( !a3 || (v29 = 569, v11 = 570, !a4) || (v29 = 570, v11 = 571, !pAcl) || (v29 = 571, v11 = 572, !a6) )
  {
LABEL_39:
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_40;
  }
  LastFailureAsHRESULT = 0;
  v29 = 572;
  if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12);
    v11 = 574;
LABEL_40:
    v30 = v11;
    goto LABEL_41;
  }
  LastFailureAsHRESULT = 0;
  v29 = 574;
  v13 = pAclInformation;
  v14 = 80 * pAclInformation + 8;
  if ( v14 <= 0xFFFC )
  {
    v15 = (struct _ACL *)CoTaskMemAlloc(v14);
    v16 = v15;
    if ( v15 )
    {
      LastFailureAsHRESULT = 0;
      v29 = 591;
      if ( InitializeAcl(v15, v14, 2u) )
      {
        LastFailureAsHRESULT = 0;
        v29 = 594;
        for ( i = 0; i < v13; ++i )
        {
          v27 = 0;
          if ( !GetAce(v10, i, &pAce) )
          {
            LastFailureAsHRESULT = GetLastFailureAsHRESULT(v20);
            v30 = 601;
            goto LABEL_36;
          }
          LastFailureAsHRESULT = 0;
          v29 = 601;
          v21 = pAce;
          v22 = *(unsigned __int8 *)pAce;
          if ( (unsigned __int8)v22 <= 3u || (_BYTE)v22 == 17 )
          {
            LastFailureAsHRESULT = DoSidWork(v35, v34, v33, v32, (char *)pAce + 8, v39, 0x44u, &v27);
            v18 = 608;
            if ( LastFailureAsHRESULT < 0 )
              goto LABEL_19;
            v29 = 608;
            v23 = v21[1];
            if ( v27 )
            {
              LastFailureAsHRESULT = SxAddKnownAce(v16, v23, *((_DWORD *)pAce + 1), v39, v22);
              v24 = LastFailureAsHRESULT < 0;
              v18 = 622;
            }
            else
            {
              LastFailureAsHRESULT = SxAddKnownAce(v16, v23, *((_DWORD *)pAce + 1), (char *)pAce + 8, v22);
              v24 = LastFailureAsHRESULT < 0;
              v18 = 626;
            }
            if ( v24 )
              goto LABEL_19;
            v29 = v18;
          }
          else
          {
            v27 = 0;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, v22);
          }
          v10 = v36;
        }
        *a6 = v16;
      }
      else
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v17);
        v18 = 594;
LABEL_19:
        v30 = v18;
LABEL_36:
        CoTaskMemFree(v16);
      }
    }
    else
    {
      LastFailureAsHRESULT = -2147024882;
      v30 = 591;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids);
    *a6 = 0;
    LastFailureAsHRESULT = 1;
    v29 = 587;
  }
LABEL_41:
  v25 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v25;
}

```

## disassembly

```asm
0x1800240ac  push    rbp
0x1800240ae  push    rbx
0x1800240af  push    rsi
0x1800240b0  push    rdi
0x1800240b1  push    r12
0x1800240b3  push    r13
0x1800240b5  push    r14
0x1800240b7  push    r15
0x1800240b9  lea     rbp, [rsp-28h]
0x1800240be  sub     rsp, 128h
0x1800240c5  mov     rax, cs:__security_cookie
0x1800240cc  xor     rax, rsp
0x1800240cf  mov     [rbp+60h+var_50], rax
0x1800240d3  mov     r12, r9
0x1800240d6  mov     [rbp+60h+var_D8], r9
0x1800240da  mov     r14, r8
0x1800240dd  mov     [rbp+60h+var_D0], r8
0x1800240e1  mov     rsi, rdx
0x1800240e4  mov     [rbp+60h+var_C8], rdx
0x1800240e8  mov     rbx, rcx
0x1800240eb  mov     [rbp+60h+var_C0], rcx
0x1800240ef  mov     r15, [rbp+60h+pAcl]
0x1800240f6  mov     [rbp+60h+var_B8], r15
0x1800240fa  mov     rdi, [rbp+60h+arg_28]
0x180024101  mov     r9d, 1; unsigned __int16
0x180024107  mov     r8d, 224h; unsigned __int16
0x18002410d  lea     rdx, aDoaclwork; "DoAclWork"
0x180024114  lea     rcx, [rsp+160h+var_118]; this
0x180024119  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002411e  xor     eax, eax
0x180024120  mov     [rbp+60h+pAclInformation], rax
0x180024124  mov     [rbp+60h+var_A8], eax
0x180024127  xor     r13d, r13d
0x18002412a  mov     [rbp+60h+pAce], r13
0x18002412e  mov     [rsp+160h+var_120], r13d
0x180024133  test    rdi, rdi
0x180024136  jz      short loc_18002413B
0x180024138  mov     [rdi], r13
0x18002413b  mov     eax, 237h
0x180024140  test    rbx, rbx
0x180024143  jz      loc_180024432
0x180024149  mov     [rsp+160h+var_114], ax
0x18002414e  mov     eax, 238h
0x180024153  test    rsi, rsi
0x180024156  jz      loc_180024432
0x18002415c  mov     [rsp+160h+var_114], ax
0x180024161  mov     eax, 239h
0x180024166  test    r14, r14
0x180024169  jz      loc_180024432
0x18002416f  mov     [rsp+160h+var_114], ax
0x180024174  mov     eax, 23Ah
0x180024179  test    r12, r12
0x18002417c  jz      loc_180024432
0x180024182  mov     [rsp+160h+var_114], ax
0x180024187  mov     eax, 23Bh
0x18002418c  test    r15, r15
0x18002418f  jz      loc_180024432
0x180024195  mov     [rsp+160h+var_114], ax
0x18002419a  mov     eax, 23Ch
0x18002419f  test    rdi, rdi
0x1800241a2  jz      loc_180024432
0x1800241a8  mov     [rsp+160h+var_118], r13d
0x1800241ad  mov     [rsp+160h+var_114], ax
0x1800241b2  mov     r12d, 2
0x1800241b8  mov     r9d, r12d; dwAclInformationClass
0x1800241bb  lea     r8d, [r12+0Ah]; nAclInformationLength
0x1800241c0  lea     rdx, [rbp+60h+pAclInformation]; pAclInformation
0x1800241c4  mov     rcx, r15; pAcl
0x1800241c7  call    cs:__imp_GetAclInformation
0x1800241cd  test    eax, eax
0x1800241cf  jnz     short loc_1800241E4
0x1800241d1  call    GetLastFailureAsHRESULT
0x1800241d6  mov     [rsp+160h+var_118], eax
0x1800241da  mov     eax, 23Eh
0x1800241df  jmp     loc_18002443A
0x1800241e4  mov     [rsp+160h+var_118], r13d
0x1800241e9  mov     eax, 23Eh
0x1800241ee  mov     [rsp+160h+var_114], ax
0x1800241f3  mov     r13d, dword ptr [rbp+60h+pAclInformation]
0x1800241f7  lea     esi, ds:0[r13*4]
0x1800241ff  add     esi, r13d
0x180024202  shl     esi, 4
0x180024205  add     esi, 8
0x180024208  cmp     esi, 0FFFCh
0x18002420e  jbe     short loc_18002425C
0x180024210  lea     r14, WPP_GLOBAL_Control
0x180024217  mov     rcx, cs:WPP_GLOBAL_Control
0x18002421e  cmp     rcx, r14
0x180024221  jz      short loc_18002423E
0x180024223  test    [rcx+1Ch], r12b
0x180024227  jz      short loc_18002423E
0x180024229  mov     edx, 14h
0x18002422e  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x180024235  mov     rcx, [rcx+10h]
0x180024239  call    WPP_SF_
0x18002423e  mov     qword ptr [rdi], 0
0x180024245  mov     [rsp+160h+var_118], 1
0x18002424d  mov     eax, 24Bh
0x180024252  mov     [rsp+160h+var_114], ax
0x180024257  jmp     loc_18002443F
0x18002425c  mov     ecx, esi; cb
0x18002425e  call    cs:__imp_CoTaskMemAlloc
0x180024264  mov     rbx, rax
0x180024267  mov     ecx, 24Fh
0x18002426c  test    rax, rax
0x18002426f  jz      loc_180024423
0x180024275  mov     [rsp+160h+var_118], 0
0x18002427d  mov     [rsp+160h+var_114], cx
0x180024282  mov     r8d, r12d; dwAclRevision
0x180024285  mov     edx, esi; nAclLength
0x180024287  mov     rcx, rax; pAcl
0x18002428a  call    cs:__imp_InitializeAcl
0x180024290  test    eax, eax
0x180024292  jnz     short loc_1800242AC
0x180024294  call    GetLastFailureAsHRESULT
0x180024299  mov     [rsp+160h+var_118], eax
0x18002429d  mov     eax, 252h
0x1800242a2  mov     [rsp+160h+var_112], ax
0x1800242a7  jmp     loc_180024413
0x1800242ac  mov     [rsp+160h+var_118], 0
0x1800242b4  mov     eax, 252h
0x1800242b9  mov     [rsp+160h+var_114], ax
0x1800242be  xor     r12d, r12d
0x1800242c1  lea     r14, WPP_GLOBAL_Control
0x1800242c8  mov     esi, 259h
0x1800242cd  cmp     r12d, r13d
0x1800242d0  jnb     loc_18002441E
0x1800242d6  mov     [rsp+160h+var_120], 0
0x1800242de  lea     r8, [rbp+60h+pAce]; pAce
0x1800242e2  mov     edx, r12d; dwAceIndex
0x1800242e5  mov     rcx, r15; pAcl
0x1800242e8  call    cs:__imp_GetAce
0x1800242ee  test    eax, eax
0x1800242f0  jz      loc_180024405
0x1800242f6  mov     [rsp+160h+var_118], 0
0x1800242fe  mov     [rsp+160h+var_114], si
0x180024303  mov     r15, [rbp+60h+pAce]
0x180024307  movzx   esi, byte ptr [r15]
0x18002430b  cmp     sil, 3
0x18002430f  jbe     short loc_180024356
0x180024311  cmp     sil, 11h
0x180024315  jz      short loc_180024356
0x180024317  mov     [rsp+160h+var_120], 0
0x18002431f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024326  cmp     rcx, r14
0x180024329  jz      loc_1800243F9
0x18002432f  test    byte ptr [rcx+1Ch], 80h
0x180024333  jz      loc_1800243F9
0x180024339  mov     r9d, esi
0x18002433c  mov     edx, 15h
0x180024341  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x180024348  mov     rcx, [rcx+10h]
0x18002434c  call    WPP_SF_d
0x180024351  jmp     loc_1800243F9
0x180024356  lea     rax, [r15+8]
0x18002435a  lea     rcx, [rsp+160h+var_120]
0x18002435f  mov     [rsp+160h+var_128], rcx; int *
0x180024364  mov     [rsp+160h+var_130], 44h ; 'D'; unsigned int
0x18002436c  lea     rcx, [rbp+60h+var_A0]
0x180024370  mov     [rsp+160h+var_138], rcx; void *
0x180024375  mov     [rsp+160h+pSid], rax; pSid
0x18002437a  mov     r9, [rbp+60h+var_D8]; struct CSdUserSidList *
0x18002437e  mov     r8, [rbp+60h+var_D0]; struct ISdGlobalCatalog *
0x180024382  mov     rdx, [rbp+60h+var_C8]; struct ISdCallback2 *
0x180024386  mov     rcx, [rbp+60h+var_C0]; struct ISdAsyncPriv *
0x18002438a  call    ?DoSidWork@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAXPEAXKPEAH@Z; DoSidWork(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,void * const,void *,ulong,int *)
0x18002438f  mov     [rsp+160h+var_118], eax
0x180024393  test    eax, eax
0x180024395  mov     eax, 260h
0x18002439a  js      loc_1800242A2
0x1800243a0  mov     [rsp+160h+var_114], ax
0x1800243a5  mov     byte ptr [rsp+160h+pSid], sil; unsigned __int8
0x1800243aa  mov     r8, [rbp+60h+pAce]
0x1800243ae  mov     dl, [r15+1]; unsigned __int8
0x1800243b2  mov     rcx, rbx; pAcl
0x1800243b5  cmp     [rsp+160h+var_120], 0
0x1800243ba  jz      short loc_1800243D6
0x1800243bc  lea     r9, [rbp+60h+var_A0]; void *
0x1800243c0  mov     r8d, [r8+4]; unsigned int
0x1800243c4  call    ?SxAddKnownAce@@YAJPEAU_ACL@@EKQEAXE@Z; SxAddKnownAce(_ACL *,uchar,ulong,void * const,uchar)
0x1800243c9  mov     [rsp+160h+var_118], eax
0x1800243cd  test    eax, eax
0x1800243cf  mov     eax, 26Eh
0x1800243d4  jmp     short loc_1800243EE
0x1800243d6  lea     r9, [r8+8]; void *
0x1800243da  mov     r8d, [r8+4]; unsigned int
0x1800243de  call    ?SxAddKnownAce@@YAJPEAU_ACL@@EKQEAXE@Z; SxAddKnownAce(_ACL *,uchar,ulong,void * const,uchar)
0x1800243e3  mov     [rsp+160h+var_118], eax
0x1800243e7  test    eax, eax
0x1800243e9  mov     eax, 272h
0x1800243ee  js      loc_1800242A2
0x1800243f4  mov     [rsp+160h+var_114], ax
0x1800243f9  inc     r12d
0x1800243fc  mov     r15, [rbp+60h+var_B8]
0x180024400  jmp     loc_1800242C8
0x180024405  call    GetLastFailureAsHRESULT
0x18002440a  mov     [rsp+160h+var_118], eax
0x18002440e  mov     [rsp+160h+var_112], si
0x180024413  mov     rcx, rbx; pv
0x180024416  call    cs:__imp_CoTaskMemFree
0x18002441c  jmp     short loc_18002443F
0x18002441e  mov     [rdi], rbx
0x180024421  jmp     short loc_18002443F
0x180024423  mov     [rsp+160h+var_118], 8007000Eh
0x18002442b  mov     [rsp+160h+var_112], cx
0x180024430  jmp     short loc_18002443F
0x180024432  mov     [rsp+160h+var_118], 80070057h
0x18002443a  mov     [rsp+160h+var_112], ax
0x18002443f  mov     ebx, [rsp+160h+var_118]
0x180024443  lea     rcx, [rsp+160h+var_118]; this
0x180024448  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002444d  mov     eax, ebx
0x18002444f  mov     rcx, [rbp+60h+var_50]
0x180024453  xor     rcx, rsp; StackCookie
0x180024456  call    __security_check_cookie
0x18002445b  add     rsp, 128h
0x180024462  pop     r15
0x180024464  pop     r14
0x180024466  pop     r13
0x180024468  pop     r12
0x18002446a  pop     rdi
0x18002446b  pop     rsi
0x18002446c  pop     rbx
0x18002446d  pop     rbp
0x18002446e  retn
```
