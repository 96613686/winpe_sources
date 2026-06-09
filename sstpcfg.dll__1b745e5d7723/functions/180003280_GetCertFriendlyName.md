# GetCertFriendlyName

- ea: `0x180003280`
- end: `0x180003508`
- name: `GetCertFriendlyName`
- size: `648`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005830`

## callees

- `0x180003280`
- `0x18000a014`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003356`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003356`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003345`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003345`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034cf`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800032d4`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800033ea`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800032d4`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800033ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003387`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003387`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003441`

## pseudocode

```c
__int64 __fastcall GetCertFriendlyName(PCCERT_CONTEXT pCertContext, _QWORD *a2, DWORD *a3)
{
  unsigned int v6; // ebp
  __int64 v7; // rdx
  const wchar_t *v8; // r8
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  void *v11; // rax
  void *v12; // rdi
  __int64 v13; // rbx
  DWORD v14; // eax
  __int64 v15; // r8
  DWORD v16; // eax
  __int64 v17; // rbx
  DWORD LastError; // eax
  __int64 v19; // r8
  DWORD v20; // eax
  __int64 v21; // rdx
  const wchar_t *v22; // r8
  HANDLE v23; // rax
  int v25; // [rsp+20h] [rbp-838h] BYREF
  _BYTE v26[2044]; // [rsp+24h] [rbp-834h] BYREF

  v25 = 0;
  v6 = 0;
  memset_0(v26, 0, sizeof(v26));
  if ( !CertGetCertificateContextProperty(pCertContext, 0xBu, 0, a3) )
    return v6;
  if ( *a3 <= 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xABu);
    }
    v7 = xmmword_1800146E0;
    if ( (_QWORD)xmmword_1800146E0 )
    {
      v8 = L"CertGetCertificateContextProperty failed.";
LABEL_9:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v7, v8);
      return v6;
    }
    return v6;
  }
  v9 = *a3;
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, v9);
  v12 = v11;
  if ( v11 )
  {
    if ( CertGetCertificateContextProperty(pCertContext, 0xBu, v11, a3) )
    {
      if ( *a3 > 1 )
      {
        *a2 = v12;
        return 1;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xAEu);
      }
      v21 = xmmword_1800146E0;
      if ( !(_QWORD)xmmword_1800146E0 )
        goto LABEL_32;
      v22 = L"CertGetCertificateContextProperty failed.";
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v17 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        LastError = GetLastError();
        WPP_SF_d(v17, 0xADu, v19, LastError);
      }
      if ( !(_QWORD)xmmword_1800146E0 )
        goto LABEL_32;
      LOWORD(v25) = 0;
      v20 = GetLastError();
      FormatRRASErrorString((wchar_t *)&v25, L"CertGetCertificateContextProperty failed and returned 0x%x", v20);
      v21 = xmmword_1800146E0;
      v22 = (const wchar_t *)&v25;
    }
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v21, v22);
LABEL_32:
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v12);
    return v6;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v14 = GetLastError();
    WPP_SF_d(v13, 0xACu, v15, v14);
  }
  if ( (_QWORD)xmmword_1800146E0 )
  {
    LOWORD(v25) = 0;
    v16 = GetLastError();
    FormatRRASErrorString((wchar_t *)&v25, L"HeapAlloc failed and returned %d", v16);
    v7 = xmmword_1800146E0;
    v8 = (const wchar_t *)&v25;
    goto LABEL_9;
  }
  return v6;
}

```

## disassembly

```asm
0x180003280  mov     [rsp+arg_18], rbx
0x180003285  push    rbp
0x180003286  push    rsi
0x180003287  push    rdi
0x180003288  push    r14
0x18000328a  push    r15
0x18000328c  sub     rsp, 830h
0x180003293  mov     rax, cs:__security_cookie
0x18000329a  xor     rax, rsp
0x18000329d  mov     [rsp+858h+var_38], rax
0x1800032a5  mov     rsi, r8
0x1800032a8  mov     r14, rdx
0x1800032ab  mov     r15, rcx
0x1800032ae  xor     eax, eax
0x1800032b0  xor     edx, edx; Val
0x1800032b2  mov     [rsp+858h+var_838], eax
0x1800032b6  mov     r8d, 7FCh; Size
0x1800032bc  lea     rcx, [rsp+858h+var_834]; void *
0x1800032c1  xor     ebp, ebp
0x1800032c3  call    memset_0
0x1800032c8  mov     r9, rsi; pcbData
0x1800032cb  lea     edx, [rbp+0Bh]; dwPropId
0x1800032ce  xor     r8d, r8d; pvData
0x1800032d1  mov     rcx, r15; pCertContext
0x1800032d4  call    cs:__imp_CertGetCertificateContextProperty
0x1800032da  test    eax, eax
0x1800032dc  jz      loc_1800034DF
0x1800032e2  cmp     dword ptr [rsi], 1
0x1800032e5  ja      short loc_180003343
0x1800032e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032ee  lea     rax, WPP_GLOBAL_Control
0x1800032f5  cmp     rcx, rax
0x1800032f8  jz      short loc_180003314
0x1800032fa  test    byte ptr [rcx+1Ch], 40h
0x1800032fe  jz      short loc_180003314
0x180003300  cmp     byte ptr [rcx+19h], 1
0x180003304  jb      short loc_180003314
0x180003306  mov     rcx, [rcx+10h]
0x18000330a  mov     edx, 0ABh
0x18000330f  call    WPP_SF_
0x180003314  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000331b  test    rdx, rdx
0x18000331e  jz      loc_1800034DF
0x180003324  lea     r8, aCertgetcertifi_0; "CertGetCertificateContextProperty faile"...
0x18000332b  mov     rcx, cs:gSstpCfgEtwContext
0x180003332  mov     rax, cs:gSstpCfgTemplateFunc
0x180003339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000333e  jmp     loc_1800034DF
0x180003343  mov     ebx, [rsi]
0x180003345  call    cs:__imp_GetProcessHeap
0x18000334b  mov     r8d, ebx; dwBytes
0x18000334e  mov     edx, 8; dwFlags
0x180003353  mov     rcx, rax; hHeap
0x180003356  call    cs:__imp_HeapAlloc
0x18000335c  mov     rdi, rax
0x18000335f  test    rax, rax
0x180003362  jnz     short loc_1800033DC
0x180003364  mov     rbx, cs:WPP_GLOBAL_Control
0x18000336b  lea     rax, WPP_GLOBAL_Control
0x180003372  cmp     rbx, rax
0x180003375  jz      short loc_18000339D
0x180003377  test    byte ptr [rbx+1Ch], 40h
0x18000337b  jz      short loc_18000339D
0x18000337d  cmp     byte ptr [rbx+19h], 1
0x180003381  jb      short loc_18000339D
0x180003383  mov     rbx, [rbx+10h]
0x180003387  call    cs:__imp_GetLastError
0x18000338d  mov     edx, 0ACh
0x180003392  mov     rcx, rbx
0x180003395  mov     r9d, eax
0x180003398  call    WPP_SF_d
0x18000339d  cmp     qword ptr cs:xmmword_1800146E0, rbp
0x1800033a4  jz      loc_1800034DF
0x1800033aa  xor     eax, eax
0x1800033ac  mov     word ptr [rsp+858h+var_838], ax
0x1800033b1  call    cs:__imp_GetLastError
0x1800033b7  mov     r8d, eax
0x1800033ba  lea     rdx, aHeapallocFaile; "HeapAlloc failed and returned %d"
0x1800033c1  lea     rcx, [rsp+858h+var_838]
0x1800033c6  call    FormatRRASErrorString
0x1800033cb  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800033d2  lea     r8, [rsp+858h+var_838]
0x1800033d7  jmp     loc_18000332B
0x1800033dc  mov     r9, rsi; pcbData
0x1800033df  mov     r8, rdi; pvData
0x1800033e2  mov     edx, 0Bh; dwPropId
0x1800033e7  mov     rcx, r15; pCertContext
0x1800033ea  call    cs:__imp_CertGetCertificateContextProperty
0x1800033f0  test    eax, eax
0x1800033f2  jnz     short loc_180003469
0x1800033f4  mov     rbx, cs:WPP_GLOBAL_Control
0x1800033fb  lea     rax, WPP_GLOBAL_Control
0x180003402  cmp     rbx, rax
0x180003405  jz      short loc_18000342D
0x180003407  test    byte ptr [rbx+1Ch], 40h
0x18000340b  jz      short loc_18000342D
0x18000340d  cmp     byte ptr [rbx+19h], 1
0x180003411  jb      short loc_18000342D
0x180003413  mov     rbx, [rbx+10h]
0x180003417  call    cs:__imp_GetLastError
0x18000341d  mov     edx, 0ADh
0x180003422  mov     rcx, rbx
0x180003425  mov     r9d, eax
0x180003428  call    WPP_SF_d
0x18000342d  cmp     qword ptr cs:xmmword_1800146E0, rbp
0x180003434  jz      loc_1800034C1
0x18000343a  xor     eax, eax
0x18000343c  mov     word ptr [rsp+858h+var_838], ax
0x180003441  call    cs:__imp_GetLastError
0x180003447  mov     r8d, eax
0x18000344a  lea     rdx, aCertgetcertifi; "CertGetCertificateContextProperty faile"...
0x180003451  lea     rcx, [rsp+858h+var_838]
0x180003456  call    FormatRRASErrorString
0x18000345b  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180003462  lea     r8, [rsp+858h+var_838]
0x180003467  jmp     short loc_1800034AE
0x180003469  cmp     dword ptr [rsi], 1
0x18000346c  ja      short loc_1800034D7
0x18000346e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003475  lea     rax, WPP_GLOBAL_Control
0x18000347c  cmp     rcx, rax
0x18000347f  jz      short loc_18000349B
0x180003481  test    byte ptr [rcx+1Ch], 40h
0x180003485  jz      short loc_18000349B
0x180003487  cmp     byte ptr [rcx+19h], 1
0x18000348b  jb      short loc_18000349B
0x18000348d  mov     rcx, [rcx+10h]
0x180003491  mov     edx, 0AEh
0x180003496  call    WPP_SF_
0x18000349b  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800034a2  test    rdx, rdx
0x1800034a5  jz      short loc_1800034C1
0x1800034a7  lea     r8, aCertgetcertifi_0; "CertGetCertificateContextProperty faile"...
0x1800034ae  mov     rcx, cs:gSstpCfgEtwContext
0x1800034b5  mov     rax, cs:gSstpCfgTemplateFunc
0x1800034bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034c1  call    cs:__imp_GetProcessHeap
0x1800034c7  mov     r8, rdi; lpMem
0x1800034ca  xor     edx, edx; dwFlags
0x1800034cc  mov     rcx, rax; hHeap
0x1800034cf  call    cs:__imp_HeapFree
0x1800034d5  jmp     short loc_1800034DF
0x1800034d7  mov     [r14], rdi
0x1800034da  mov     ebp, 1
0x1800034df  mov     eax, ebp
0x1800034e1  mov     rcx, [rsp+858h+var_38]
0x1800034e9  xor     rcx, rsp; StackCookie
0x1800034ec  call    __security_check_cookie
0x1800034f1  mov     rbx, [rsp+858h+arg_18]
0x1800034f9  add     rsp, 830h
0x180003500  pop     r15
0x180003502  pop     r14
0x180003504  pop     rdi
0x180003505  pop     rsi
0x180003506  pop     rbp
0x180003507  retn
```
