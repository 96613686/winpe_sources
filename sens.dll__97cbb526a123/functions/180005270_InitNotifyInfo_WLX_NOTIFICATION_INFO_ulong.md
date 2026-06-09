# InitNotifyInfo(_WLX_NOTIFICATION_INFO *,ulong)

- ea: `0x180005270`
- end: `0x1800055c8`
- name: `?InitNotifyInfo@@YAKPEAU_WLX_NOTIFICATION_INFO@@K@Z`
- size: `856`
- prototype: `__int64 __fastcall(struct _WLX_NOTIFICATION_INFO *, ULONG SessionId)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004e00`
- `0x180004e70`
- `0x180004f10`
- `0x1800050b0`
- `0x1800051d0`
- `0x180005da0`
- `0x180005f20`
- `0x180009840`
- `0x1800098a0`

## callees

- `0x180005270`
- `0x180005830`
- `0x180008300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000537f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000546f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000537f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000546f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005533`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000543f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000543f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800052f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800053b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800053e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800054d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005503`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000557f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800055ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800052f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800053b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800053e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800054d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005503`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000557f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800055ab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800052c9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005321`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800052c9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005321`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180005371`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180005422`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180005371`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180005422`
- `WTSAPI32!WTSQueryUserToken` at `0x18000529a`
- `WTSAPI32!WTSQueryUserToken` at `0x18000529a`

## pseudocode

```c
__int64 __fastcall InitNotifyInfo(struct _WLX_NOTIFICATION_INFO *a1, ULONG SessionId)
{
  HANDLE hToken; // rcx
  void **v5; // rdi
  void *v6; // rsi
  void *v7; // rcx
  SIZE_T v8; // rax
  WCHAR *v9; // rax
  SIZE_T v10; // rax
  WCHAR *v11; // rax
  DWORD LastError; // esi
  WCHAR *v14; // rax
  HANDLE v15; // rcx
  WCHAR *v16; // rax
  __int64 v17; // r9
  WCHAR *v18; // rax
  HANDLE v19; // rcx
  enum _SID_NAME_USE peUse[14]; // [rsp+30h] [rbp-38h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+80h] [rbp+18h] BYREF
  DWORD cchName; // [rsp+88h] [rbp+20h] BYREF

  *(_OWORD *)&a1->Size = 0;
  *(_OWORD *)&a1->Domain = 0;
  *(_OWORD *)&a1->hToken = 0;
  a1->pStatusCallback = 0;
  if ( WTSQueryUserToken(SessionId, &a1->hToken) )
  {
    hToken = a1->hToken;
    TokenInformationLength = 0;
    if ( GetTokenInformation(hToken, TokenUser, 0, 0, &TokenInformationLength) )
    {
      LastError = 87;
      goto LABEL_20;
    }
    if ( GetLastError() == 122 )
    {
      v5 = (void **)HeapAlloc(ghSensHeap, 0, TokenInformationLength);
      if ( !v5 )
      {
        LastError = 14;
        goto LABEL_20;
      }
      if ( !GetTokenInformation(a1->hToken, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
      {
        LastError = GetLastError();
        goto LABEL_16;
      }
      a1->Flags = SessionId;
      peUse[0] = 0;
      v6 = *v5;
      v7 = *v5;
      cchName = 0;
      cchReferencedDomainName = 0;
      if ( LookupAccountSidLocalW(v7, 0, &cchName, 0, &cchReferencedDomainName, peUse) )
      {
        LastError = 87;
        goto LABEL_16;
      }
      if ( GetLastError() == 122 )
      {
        v8 = 2LL * cchName;
        if ( !is_mul_ok(cchName, 2u) )
          v8 = -1;
        v9 = (WCHAR *)HeapAlloc(ghSensHeap, 0, v8);
        a1->UserName = v9;
        if ( !v9 )
        {
          LastError = 14;
          goto LABEL_16;
        }
        v10 = 2LL * cchReferencedDomainName;
        if ( !is_mul_ok(cchReferencedDomainName, 2u) )
          v10 = -1;
        v11 = (WCHAR *)HeapAlloc(ghSensHeap, 0, v10);
        a1->Domain = v11;
        if ( !v11 )
        {
          LastError = 14;
          goto LABEL_16;
        }
        if ( LookupAccountSidLocalW(v6, a1->UserName, &cchName, v11, &cchReferencedDomainName, peUse) )
          goto LABEL_15;
        v17 = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4bfcbcf89dc83e060bd09cba59c8d2ce_Traceguids, v17);
        }
        v18 = (WCHAR *)HeapAlloc(ghSensHeap, 0, 2u);
        a1->UserName = v18;
        if ( !v18 )
        {
          LastError = 14;
          goto LABEL_16;
        }
        v19 = ghSensHeap;
        *v18 = 0;
        v16 = (WCHAR *)HeapAlloc(v19, 0, 2u);
        a1->Domain = v16;
        if ( !v16 )
        {
LABEL_43:
          LastError = 14;
          goto LABEL_16;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4bfcbcf89dc83e060bd09cba59c8d2ce_Traceguids, 0);
        }
        v14 = (WCHAR *)HeapAlloc(ghSensHeap, 0, 2u);
        a1->UserName = v14;
        if ( !v14 )
        {
          LastError = 14;
          goto LABEL_16;
        }
        v15 = ghSensHeap;
        *v14 = 0;
        v16 = (WCHAR *)HeapAlloc(v15, 0, 2u);
        a1->Domain = v16;
        if ( !v16 )
          goto LABEL_43;
      }
      *v16 = 0;
LABEL_15:
      LastError = 0;
LABEL_16:
      HeapFree(ghSensHeap, 0, v5);
      goto LABEL_17;
    }
  }
  LastError = GetLastError();
LABEL_17:
  if ( LastError )
LABEL_20:
    FreeNotifyInfo(a1);
  return LastError;
}

```

## disassembly

```asm
0x180005270  push    rbx
0x180005272  push    rbp
0x180005273  push    rsi
0x180005274  push    rdi
0x180005275  push    r14
0x180005277  sub     rsp, 40h
0x18000527b  xorps   xmm0, xmm0
0x18000527e  mov     ebp, edx
0x180005280  movups  xmmword ptr [rcx], xmm0
0x180005283  xor     eax, eax
0x180005285  mov     rbx, rcx
0x180005288  movups  xmmword ptr [rcx+10h], xmm0
0x18000528c  lea     rdx, [rcx+20h]; phToken
0x180005290  movups  xmmword ptr [rcx+20h], xmm0
0x180005294  mov     [rcx+30h], rax
0x180005298  mov     ecx, ebp; SessionId
0x18000529a  call    cs:__imp_WTSQueryUserToken
0x1800052a0  test    eax, eax
0x1800052a2  jz      loc_18000546F
0x1800052a8  mov     rcx, [rbx+20h]; TokenHandle
0x1800052ac  lea     rax, [rsp+68h+TokenInformationLength]
0x1800052b1  xor     r14d, r14d
0x1800052b4  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800052b9  xor     r9d, r9d; TokenInformationLength
0x1800052bc  mov     [rsp+68h+TokenInformationLength], r14d
0x1800052c1  xor     r8d, r8d; TokenInformation
0x1800052c4  mov     edx, 1; TokenInformationClass
0x1800052c9  call    cs:__imp_GetTokenInformation
0x1800052cf  test    eax, eax
0x1800052d1  jnz     loc_180005479
0x1800052d7  call    cs:__imp_GetLastError
0x1800052dd  cmp     eax, 7Ah ; 'z'
0x1800052e0  jnz     loc_180005480
0x1800052e6  mov     r8d, [rsp+68h+TokenInformationLength]; dwBytes
0x1800052eb  xor     edx, edx; dwFlags
0x1800052ed  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x1800052f4  call    cs:__imp_HeapAlloc
0x1800052fa  mov     rdi, rax
0x1800052fd  test    rax, rax
0x180005300  jz      loc_180005456
0x180005306  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x18000530b  lea     rax, [rsp+68h+TokenInformationLength]
0x180005310  mov     rcx, [rbx+20h]; TokenHandle
0x180005314  mov     r8, rdi; TokenInformation
0x180005317  mov     edx, 1; TokenInformationClass
0x18000531c  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180005321  call    cs:__imp_GetTokenInformation
0x180005327  test    eax, eax
0x180005329  jz      loc_180005465
0x18000532f  lea     rax, [rsp+68h+var_38]
0x180005334  mov     [rbx+4], ebp
0x180005337  mov     [rsp+68h+peUse], rax; peUse
0x18000533c  lea     r8, [rsp+68h+cchName]; cchName
0x180005344  mov     [rsp+68h+var_38], r14d
0x180005349  lea     rax, [rsp+68h+cchReferencedDomainName]
0x180005351  mov     rsi, [rdi]
0x180005354  xor     r9d, r9d; ReferencedDomainName
0x180005357  xor     edx, edx; Name
0x180005359  mov     [rsp+68h+ReturnLength], rax; cchReferencedDomainName
0x18000535e  mov     rcx, rsi; Sid
0x180005361  mov     [rsp+68h+cchName], r14d
0x180005369  mov     [rsp+68h+cchReferencedDomainName], r14d
0x180005371  call    cs:__imp_LookupAccountSidLocalW
0x180005377  test    eax, eax
0x180005379  jnz     loc_18000548A
0x18000537f  call    cs:__imp_GetLastError
0x180005385  cmp     eax, 7Ah ; 'z'
0x180005388  jnz     loc_180005491
0x18000538e  mov     ecx, [rsp+68h+cchName]
0x180005395  mov     eax, 2
0x18000539a  mul     rcx
0x18000539d  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x1800053a4  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x1800053ab  cmovb   rax, rbp
0x1800053af  xor     edx, edx; dwFlags
0x1800053b1  mov     r8, rax; dwBytes
0x1800053b4  call    cs:__imp_HeapAlloc
0x1800053ba  mov     [rbx+8], rax
0x1800053be  test    rax, rax
0x1800053c1  jz      loc_18000551F
0x1800053c7  mov     ecx, [rsp+68h+cchReferencedDomainName]
0x1800053ce  mov     eax, 2
0x1800053d3  mul     rcx
0x1800053d6  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x1800053dd  cmovb   rax, rbp
0x1800053e1  xor     edx, edx; dwFlags
0x1800053e3  mov     r8, rax; dwBytes
0x1800053e6  call    cs:__imp_HeapAlloc
0x1800053ec  mov     [rbx+10h], rax
0x1800053f0  test    rax, rax
0x1800053f3  jz      loc_180005529
0x1800053f9  mov     rdx, [rbx+8]; Name
0x1800053fd  lea     rcx, [rsp+68h+var_38]
0x180005402  mov     [rsp+68h+peUse], rcx; peUse
0x180005407  lea     r8, [rsp+68h+cchName]; cchName
0x18000540f  lea     rcx, [rsp+68h+cchReferencedDomainName]
0x180005417  mov     r9, rax; ReferencedDomainName
0x18000541a  mov     [rsp+68h+ReturnLength], rcx; cchReferencedDomainName
0x18000541f  mov     rcx, rsi; Sid
0x180005422  call    cs:__imp_LookupAccountSidLocalW
0x180005428  test    eax, eax
0x18000542a  jz      loc_180005533
0x180005430  mov     esi, r14d
0x180005433  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x18000543a  mov     r8, rdi; lpMem
0x18000543d  xor     edx, edx; dwFlags
0x18000543f  call    cs:__imp_HeapFree
0x180005445  test    esi, esi
0x180005447  jnz     short loc_18000545B
0x180005449  mov     eax, esi
0x18000544b  add     rsp, 40h
0x18000544f  pop     r14
0x180005451  pop     rdi
0x180005452  pop     rsi
0x180005453  pop     rbp
0x180005454  pop     rbx
0x180005455  retn
0x180005456  mov     esi, 0Eh
0x18000545b  mov     rcx, rbx; struct _WLX_NOTIFICATION_INFO *
0x18000545e  call    ?FreeNotifyInfo@@YAXPEAU_WLX_NOTIFICATION_INFO@@@Z; FreeNotifyInfo(_WLX_NOTIFICATION_INFO *)
0x180005463  jmp     short loc_180005449
0x180005465  call    cs:__imp_GetLastError
0x18000546b  mov     esi, eax
0x18000546d  jmp     short loc_180005433
0x18000546f  call    cs:__imp_GetLastError
0x180005475  mov     esi, eax
0x180005477  jmp     short loc_180005445
0x180005479  mov     esi, 57h ; 'W'
0x18000547e  jmp     short loc_18000545B
0x180005480  call    cs:__imp_GetLastError
0x180005486  mov     esi, eax
0x180005488  jmp     short loc_180005445
0x18000548a  mov     esi, 57h ; 'W'
0x18000548f  jmp     short loc_180005433
0x180005491  mov     rcx, cs:WPP_GLOBAL_Control
0x180005498  lea     rax, WPP_GLOBAL_Control
0x18000549f  cmp     rcx, rax
0x1800054a2  jz      short loc_1800054C8
0x1800054a4  test    byte ptr [rcx+1Ch], 1
0x1800054a8  jz      short loc_1800054C8
0x1800054aa  cmp     byte ptr [rcx+19h], 3
0x1800054ae  jb      short loc_1800054C8
0x1800054b0  mov     rcx, [rcx+10h]
0x1800054b4  lea     r8, WPP_4bfcbcf89dc83e060bd09cba59c8d2ce_Traceguids
0x1800054bb  mov     edx, 0Ah
0x1800054c0  xor     r9d, r9d
0x1800054c3  call    WPP_SF_d
0x1800054c8  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x1800054cf  xor     edx, edx; dwFlags
0x1800054d1  mov     r8d, 2; dwBytes
0x1800054d7  call    cs:__imp_HeapAlloc
0x1800054dd  mov     [rbx+8], rax
0x1800054e1  test    rax, rax
0x1800054e4  jnz     short loc_1800054F0
0x1800054e6  mov     esi, 0Eh
0x1800054eb  jmp     loc_180005433
0x1800054f0  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x1800054f7  xor     edx, edx; dwFlags
0x1800054f9  mov     r8d, 2; dwBytes
0x1800054ff  mov     [rax], r14w
0x180005503  call    cs:__imp_HeapAlloc
0x180005509  mov     [rbx+10h], rax
0x18000550d  test    rax, rax
0x180005510  jz      loc_1800055BE
0x180005516  mov     [rax], r14w
0x18000551a  jmp     loc_180005430
0x18000551f  mov     esi, 0Eh
0x180005524  jmp     loc_180005433
0x180005529  mov     esi, 0Eh
0x18000552e  jmp     loc_180005433
0x180005533  call    cs:__imp_GetLastError
0x180005539  mov     r9d, eax
0x18000553c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005543  lea     rax, WPP_GLOBAL_Control
0x18000554a  cmp     rcx, rax
0x18000554d  jz      short loc_180005570
0x18000554f  test    byte ptr [rcx+1Ch], 1
0x180005553  jz      short loc_180005570
0x180005555  cmp     byte ptr [rcx+19h], 3
0x180005559  jb      short loc_180005570
0x18000555b  mov     rcx, [rcx+10h]
0x18000555f  lea     r8, WPP_4bfcbcf89dc83e060bd09cba59c8d2ce_Traceguids
0x180005566  mov     edx, 0Bh
0x18000556b  call    WPP_SF_d
0x180005570  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180005577  xor     edx, edx; dwFlags
0x180005579  mov     r8d, 2; dwBytes
0x18000557f  call    cs:__imp_HeapAlloc
0x180005585  mov     [rbx+8], rax
0x180005589  test    rax, rax
0x18000558c  jnz     short loc_180005598
0x18000558e  mov     esi, 0Eh
0x180005593  jmp     loc_180005433
0x180005598  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x18000559f  xor     edx, edx; dwFlags
0x1800055a1  mov     r8d, 2; dwBytes
0x1800055a7  mov     [rax], r14w
0x1800055ab  call    cs:__imp_HeapAlloc
0x1800055b1  mov     [rbx+10h], rax
0x1800055b5  test    rax, rax
0x1800055b8  jnz     loc_180005516
0x1800055be  mov     esi, 0Eh
0x1800055c3  jmp     loc_180005433
```
