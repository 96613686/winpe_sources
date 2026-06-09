# RestrictedToken::CreateProcessAdjustedSecDescriptor(void *,_SECURITY_DESCRIPTOR * *)

- ea: `0x18008d3a4`
- end: `0x18008d6f8`
- name: `?CreateProcessAdjustedSecDescriptor@RestrictedToken@@AEAAJPEAXPEAPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `852`
- prototype: `int(RestrictedToken *__hidden this, void *, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c5830`

## callees

- `0x1800081a0`
- `0x18001b480`
- `0x18008d3a4`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800da694`
- `0x1800db6b0`
- `0x1800dd350`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18008d59b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18008d59b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008d4b9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008d4fe`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008d4b9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008d4fe`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18008d546`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18008d546`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18008d5dd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18008d651`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18008d5dd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18008d651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d4c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d5eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d65b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d4c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d5eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d65b`

## pseudocode

```c
__int64 __fastcall RestrictedToken::CreateProcessAdjustedSecDescriptor(
        RestrictedToken *this,
        void *a2,
        struct _SECURITY_DESCRIPTOR **a3,
        int a4)
{
  struct _SECURITY_DESCRIPTOR *v4; // rbx
  __int64 v7; // rcx
  int v8; // esi
  struct _SECURITY_DESCRIPTOR *Heap; // rax
  struct _SECURITY_DESCRIPTOR *v10; // rdi
  signed int v11; // edi
  signed int v12; // eax
  signed int v13; // eax
  struct _ACL *v14; // rbp
  signed int v15; // eax
  DWORD i; // edi
  __int64 v17; // rcx
  __int64 v18; // r8
  _DWORD *v19; // rsi
  signed int v20; // eax
  signed int LastError; // eax
  signed int v22; // eax
  __int64 v24; // [rsp+20h] [rbp-68h]
  struct _SECURITY_DESCRIPTOR *v25; // [rsp+48h] [rbp-40h] BYREF
  LPVOID pAce; // [rsp+50h] [rbp-38h] BYREF

  v4 = 0;
  v25 = 0;
  pAce = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qqq_sid_((int)this, (int)a2, (int)a3, a4, (__int64)hObject, qword_180108038, a2);
  if ( a3 )
    *a3 = 0;
  if ( qword_180108038 && hObject )
  {
    v7 = *(unsigned __int16 *)(*(_QWORD *)qword_180108038 + 4LL);
    v8 = 80 * v7;
    Heap = (struct _SECURITY_DESCRIPTOR *)WxAllocateHeapEx(v7, (unsigned int)(80 * v7 + 244));
    v10 = Heap;
    if ( Heap )
    {
      memset_0(Heap, 0, (unsigned int)(v8 + 244));
      v4 = v10;
      v25 = v10;
      v10->Revision = 1;
      v10->Control = -32764;
      *(_DWORD *)(&v10->Control + 1) = 20;
      LODWORD(v10->Owner) = 88;
      LODWORD(v10->Group) = 156;
      if ( CopySid(0x44u, &v10->Revision + *(unsigned int *)(&v10->Control + 1), PacWorkerClient::s_RestrictedToken) )
      {
        if ( CopySid(0x44u, &v10->Revision + LODWORD(v10->Owner), PacWorkerClient::s_RestrictedToken) )
        {
          v14 = (struct _ACL *)(&v10->Revision + LODWORD(v10->Group));
          if ( InitializeAcl(v14, v8 + 88, 2u) )
          {
            for ( i = 0; i < *(unsigned __int16 *)(*(_QWORD *)qword_180108038 + 4LL); ++i )
            {
              if ( !GetAce(*(PACL *)qword_180108038, i, &pAce) )
              {
                LastError = GetLastError();
                v11 = LastError;
                if ( LastError > 0 )
                  v11 = (unsigned __int16)LastError | 0x80070000;
                if ( v11 >= 0 )
                  v11 = -2147418113;
                goto LABEL_53;
              }
              v19 = pAce;
              if ( !*(_BYTE *)pAce )
              {
                if ( (xmmword_180107A60 & 0x20) != 0 )
                {
                  LODWORD(v24) = *((_DWORD *)pAce + 1);
                  WPP_SF__sid_D(v17, 33, v18, (char *)pAce + 8);
                }
                if ( !AddAccessAllowedAce(v14, 2u, v19[1], v19 + 2) )
                {
                  v20 = GetLastError();
                  v11 = v20;
                  if ( v20 > 0 )
                    v11 = (unsigned __int16)v20 | 0x80070000;
                  if ( v11 >= 0 )
                    v11 = -2147418113;
                  goto LABEL_53;
                }
              }
            }
            if ( AddAccessAllowedAce(v14, 2u, 0x121011u, a2) )
            {
              v11 = 0;
              *a3 = v4;
              v4 = 0;
              v25 = 0;
            }
            else
            {
              v22 = GetLastError();
              v11 = v22;
              if ( v22 > 0 )
                v11 = (unsigned __int16)v22 | 0x80070000;
              if ( v11 >= 0 )
                v11 = -2147418113;
            }
          }
          else
          {
            v15 = GetLastError();
            v11 = v15;
            if ( v15 > 0 )
              v11 = (unsigned __int16)v15 | 0x80070000;
            if ( v11 >= 0 )
              v11 = -2147418113;
          }
        }
        else
        {
          v13 = GetLastError();
          v11 = v13;
          if ( v13 > 0 )
            v11 = (unsigned __int16)v13 | 0x80070000;
          if ( v11 >= 0 )
            v11 = -2147418113;
        }
      }
      else
      {
        v12 = GetLastError();
        v11 = v12;
        if ( v12 > 0 )
          v11 = (unsigned __int16)v12 | 0x80070000;
        if ( v11 >= 0 )
          v11 = -2147418113;
      }
    }
    else
    {
      v11 = -2147024882;
    }
  }
  else
  {
    v11 = -2147024809;
  }
LABEL_53:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 34, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids, (unsigned int)v11, v24);
  if ( v4 )
    WxFreeHeapEx(&v25);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18008d3a4  mov     r11, rsp
0x18008d3a7  mov     [r11+8], rbx
0x18008d3ab  mov     [r11+20h], rbp
0x18008d3af  push    rsi
0x18008d3b0  push    rdi
0x18008d3b1  push    r12
0x18008d3b3  push    r14
0x18008d3b5  push    r15
0x18008d3b7  sub     rsp, 60h
0x18008d3bb  mov     rax, cs:__security_cookie
0x18008d3c2  xor     rax, rsp
0x18008d3c5  mov     [rsp+88h+var_30], rax
0x18008d3ca  xor     ebx, ebx
0x18008d3cc  mov     [rsp+88h+var_44], 0
0x18008d3d4  mov     [rsp+88h+var_40], rbx
0x18008d3d9  mov     r14, r8
0x18008d3dc  mov     [r11-38h], rbx
0x18008d3e0  mov     r12, rdx
0x18008d3e3  test    byte ptr cs:xmmword_180107A60, 20h
0x18008d3ea  jz      short loc_18008D40B
0x18008d3ec  mov     rax, cs:qword_180108038
0x18008d3f3  mov     [r11-58h], rdx
0x18008d3f7  mov     [r11-60h], rax
0x18008d3fb  mov     rax, cs:hObject
0x18008d402  mov     [r11-68h], rax
0x18008d406  call    WPP_SF_qqq_sid_
0x18008d40b  test    r14, r14
0x18008d40e  jz      short loc_18008D413
0x18008d410  mov     [r14], rbx
0x18008d413  mov     rax, cs:qword_180108038
0x18008d41a  test    rax, rax
0x18008d41d  jz      loc_18008D692
0x18008d423  cmp     cs:hObject, rbx
0x18008d42a  jz      loc_18008D692
0x18008d430  mov     rax, [rax]
0x18008d433  movzx   ecx, word ptr [rax+4]
0x18008d437  mov     [rsp+88h+var_44], ebx
0x18008d43b  lea     esi, [rcx+rcx*4]
0x18008d43e  shl     esi, 4
0x18008d441  lea     eax, [rsi+0F4h]
0x18008d447  mov     edx, eax
0x18008d449  mov     ebp, eax
0x18008d44b  call    WxAllocateHeapEx
0x18008d450  mov     rdi, rax
0x18008d453  test    rax, rax
0x18008d456  jnz     short loc_18008D472
0x18008d458  mov     [rsp+88h+var_44], 4Ch ; 'L'
0x18008d460  mov     edi, 8007000Eh
0x18008d465  mov     [rsp+88h+var_44], 2F9h
0x18008d46d  jmp     loc_18008D69F
0x18008d472  mov     r8, rbp; Size
0x18008d475  xor     edx, edx; Val
0x18008d477  mov     rcx, rdi; void *
0x18008d47a  call    memset_0
0x18008d47f  mov     rbx, rdi
0x18008d482  mov     [rsp+88h+var_40], rbx
0x18008d487  mov     byte ptr [rdi], 1
0x18008d48a  lea     r8, ?s_RestrictedToken@PacWorkerClient@@0VRestrictedToken@@A; pSourceSid
0x18008d491  mov     word ptr [rdi+2], 8004h
0x18008d497  mov     ebp, 44h ; 'D'
0x18008d49c  mov     dword ptr [rdi+4], 14h
0x18008d4a3  mov     ecx, ebp; nDestinationSidLength
0x18008d4a5  mov     dword ptr [rdi+8], 58h ; 'X'
0x18008d4ac  mov     dword ptr [rdi+10h], 9Ch
0x18008d4b3  mov     edx, [rdi+4]
0x18008d4b6  add     rdx, rdi; pDestinationSid
0x18008d4b9  call    cs:__imp_CopySid
0x18008d4bf  test    eax, eax
0x18008d4c1  jnz     short loc_18008D4EF
0x18008d4c3  call    cs:__imp_GetLastError
0x18008d4c9  mov     edi, eax
0x18008d4cb  test    eax, eax
0x18008d4cd  jle     short loc_18008D4D8
0x18008d4cf  movzx   edi, ax
0x18008d4d2  or      edi, 80070000h
0x18008d4d8  test    edi, edi
0x18008d4da  mov     [rsp+88h+var_44], 308h
0x18008d4e2  mov     eax, 8000FFFFh
0x18008d4e7  cmovns  edi, eax
0x18008d4ea  jmp     loc_18008D69F
0x18008d4ef  mov     edx, [rdi+8]
0x18008d4f2  lea     r8, ?s_RestrictedToken@PacWorkerClient@@0VRestrictedToken@@A; pSourceSid
0x18008d4f9  add     rdx, rdi; pDestinationSid
0x18008d4fc  mov     ecx, ebp; nDestinationSidLength
0x18008d4fe  call    cs:__imp_CopySid
0x18008d504  test    eax, eax
0x18008d506  jnz     short loc_18008D534
0x18008d508  call    cs:__imp_GetLastError
0x18008d50e  mov     edi, eax
0x18008d510  test    eax, eax
0x18008d512  jle     short loc_18008D51D
0x18008d514  movzx   edi, ax
0x18008d517  or      edi, 80070000h
0x18008d51d  test    edi, edi
0x18008d51f  mov     [rsp+88h+var_44], 310h
0x18008d527  mov     eax, 8000FFFFh
0x18008d52c  cmovns  edi, eax
0x18008d52f  jmp     loc_18008D69F
0x18008d534  mov     ebp, [rdi+10h]
0x18008d537  lea     edx, [rsi+58h]; nAclLength
0x18008d53a  add     rbp, rdi
0x18008d53d  mov     r8d, 2; dwAclRevision
0x18008d543  mov     rcx, rbp; pAcl
0x18008d546  call    cs:__imp_InitializeAcl
0x18008d54c  test    eax, eax
0x18008d54e  jnz     short loc_18008D57C
0x18008d550  call    cs:__imp_GetLastError
0x18008d556  mov     edi, eax
0x18008d558  test    eax, eax
0x18008d55a  jle     short loc_18008D565
0x18008d55c  movzx   edi, ax
0x18008d55f  or      edi, 80070000h
0x18008d565  test    edi, edi
0x18008d567  mov     [rsp+88h+var_44], 31Ah
0x18008d56f  mov     eax, 8000FFFFh
0x18008d574  cmovns  edi, eax
0x18008d577  jmp     loc_18008D69F
0x18008d57c  xor     edi, edi
0x18008d57e  mov     rax, cs:qword_180108038
0x18008d585  mov     rcx, [rax]; pAcl
0x18008d588  movzx   eax, word ptr [rcx+4]
0x18008d58c  cmp     edi, eax
0x18008d58e  jnb     loc_18008D640
0x18008d594  lea     r8, [rsp+88h+pAce]; pAce
0x18008d599  mov     edx, edi; dwAceIndex
0x18008d59b  call    cs:__imp_GetAce
0x18008d5a1  test    eax, eax
0x18008d5a3  jz      short loc_18008D617
0x18008d5a5  mov     rsi, [rsp+88h+pAce]
0x18008d5aa  cmp     byte ptr [rsi], 0
0x18008d5ad  jnz     short loc_18008D5E7
0x18008d5af  test    byte ptr cs:xmmword_180107A60, 20h
0x18008d5b6  jz      short loc_18008D5CD
0x18008d5b8  mov     eax, [rsi+4]
0x18008d5bb  lea     r9, [rsi+8]
0x18008d5bf  mov     edx, 21h ; '!'
0x18008d5c4  mov     dword ptr [rsp+88h+var_68], eax
0x18008d5c8  call    WPP_SF__sid_D
0x18008d5cd  mov     r8d, [rsi+4]; AccessMask
0x18008d5d1  lea     r9, [rsi+8]; pSid
0x18008d5d5  mov     edx, 2; dwAceRevision
0x18008d5da  mov     rcx, rbp; pAcl
0x18008d5dd  call    cs:__imp_AddAccessAllowedAce
0x18008d5e3  test    eax, eax
0x18008d5e5  jz      short loc_18008D5EB
0x18008d5e7  inc     edi
0x18008d5e9  jmp     short loc_18008D57E
0x18008d5eb  call    cs:__imp_GetLastError
0x18008d5f1  mov     edi, eax
0x18008d5f3  test    eax, eax
0x18008d5f5  jle     short loc_18008D600
0x18008d5f7  movzx   edi, ax
0x18008d5fa  or      edi, 80070000h
0x18008d600  test    edi, edi
0x18008d602  mov     [rsp+88h+var_44], 332h
0x18008d60a  mov     eax, 8000FFFFh
0x18008d60f  cmovns  edi, eax
0x18008d612  jmp     loc_18008D69F
0x18008d617  call    cs:__imp_GetLastError
0x18008d61d  mov     edi, eax
0x18008d61f  test    eax, eax
0x18008d621  jle     short loc_18008D62C
0x18008d623  movzx   edi, ax
0x18008d626  or      edi, 80070000h
0x18008d62c  test    edi, edi
0x18008d62e  mov     [rsp+88h+var_44], 320h
0x18008d636  mov     eax, 8000FFFFh
0x18008d63b  cmovns  edi, eax
0x18008d63e  jmp     short loc_18008D69F
0x18008d640  mov     r9, r12; pSid
0x18008d643  mov     edx, 2; dwAceRevision
0x18008d648  mov     r8d, 121011h; AccessMask
0x18008d64e  mov     rcx, rbp; pAcl
0x18008d651  call    cs:__imp_AddAccessAllowedAce
0x18008d657  test    eax, eax
0x18008d659  jnz     short loc_18008D684
0x18008d65b  call    cs:__imp_GetLastError
0x18008d661  mov     edi, eax
0x18008d663  test    eax, eax
0x18008d665  jle     short loc_18008D670
0x18008d667  movzx   edi, ax
0x18008d66a  or      edi, 80070000h
0x18008d670  test    edi, edi
0x18008d672  mov     [rsp+88h+var_44], 341h
0x18008d67a  mov     eax, 8000FFFFh
0x18008d67f  cmovns  edi, eax
0x18008d682  jmp     short loc_18008D69F
0x18008d684  xor     edi, edi
0x18008d686  mov     [r14], rbx
0x18008d689  xor     ebx, ebx
0x18008d68b  mov     [rsp+88h+var_40], rbx
0x18008d690  jmp     short loc_18008D69F
0x18008d692  mov     edi, 80070057h
0x18008d697  mov     [rsp+88h+var_44], 2E6h
0x18008d69f  test    byte ptr cs:xmmword_180107A60, 20h
0x18008d6a6  jz      short loc_18008D6C1
0x18008d6a8  mov     edx, 22h ; '"'
0x18008d6ad  lea     r8, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids
0x18008d6b4  mov     ecx, 405h
0x18008d6b9  mov     r9d, edi
0x18008d6bc  call    WPP_SF_d
0x18008d6c1  test    rbx, rbx
0x18008d6c4  jz      short loc_18008D6D0
0x18008d6c6  lea     rcx, [rsp+88h+var_40]
0x18008d6cb  call    WxFreeHeapEx
0x18008d6d0  mov     eax, edi
0x18008d6d2  mov     rcx, [rsp+88h+var_30]
0x18008d6d7  xor     rcx, rsp; StackCookie
0x18008d6da  call    __security_check_cookie
0x18008d6df  lea     r11, [rsp+88h+var_28]
0x18008d6e4  mov     rbx, [r11+30h]
0x18008d6e8  mov     rbp, [r11+48h]
0x18008d6ec  mov     rsp, r11
0x18008d6ef  pop     r15
0x18008d6f1  pop     r14
0x18008d6f3  pop     r12
0x18008d6f5  pop     rdi
0x18008d6f6  pop     rsi
0x18008d6f7  retn
```
