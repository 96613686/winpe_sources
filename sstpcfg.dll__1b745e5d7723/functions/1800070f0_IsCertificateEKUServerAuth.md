# IsCertificateEKUServerAuth

- ea: `0x1800070f0`
- end: `0x180007400`
- name: `IsCertificateEKUServerAuth`
- size: `784`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180003aac`
- `0x180004300`
- `0x180005370`
- `0x180005830`

## callees

- `0x1800070f0`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `msvcrt!_strcmpi` at `0x180007247`
- `msvcrt!_strcmpi` at `0x180007260`
- `msvcrt!_strcmpi` at `0x180007247`
- `msvcrt!_strcmpi` at `0x180007260`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000717f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000717f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007171`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007326`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007171`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007326`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007334`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007334`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x180007155`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x1800071f8`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x180007155`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x1800071f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000733f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000737a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000733f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000737a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073a1`

## pseudocode

```c
int __fastcall IsCertificateEKUServerAuth(PCCERT_CONTEXT pCertContext, int *a2)
{
  DWORD v4; // ebx
  HANDLE ProcessHeap; // rax
  struct _CTL_USAGE *v6; // rax
  struct _CTL_USAGE *v7; // rdi
  _UNKNOWN **v8; // rax
  __int64 v9; // rbx
  DWORD LastError; // eax
  __int64 v11; // r8
  DWORD v12; // eax
  int v13; // ebx
  __int64 v14; // r14
  __int64 v15; // rbx
  DWORD v16; // eax
  __int64 v17; // r8
  DWORD v18; // eax
  HANDLE v19; // rax
  __int64 v20; // rbx
  DWORD v21; // eax
  __int64 v22; // r8
  DWORD v23; // eax
  DWORD pcbUsage[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v27[2044]; // [rsp+34h] [rbp-CCh] BYREF

  pcbUsage[0] = 0;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  *a2 = 0;
  if ( CertGetEnhancedKeyUsage(pCertContext, 0, 0, pcbUsage) && pcbUsage[0] )
  {
    v4 = pcbUsage[0];
    ProcessHeap = GetProcessHeap();
    v6 = (struct _CTL_USAGE *)HeapAlloc(ProcessHeap, 0, v4);
    v7 = v6;
    if ( !v6 )
    {
      v8 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v9 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        LastError = GetLastError();
        LODWORD(v8) = WPP_SF_d(v9, 0xFu, v11, LastError);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v26) = 0;
        v12 = GetLastError();
        FormatRRASErrorString((wchar_t *)&v26, L"Unable to allocate memory for querying key usage...%d", v12);
LABEL_42:
        LODWORD(v8) = ((__int64 (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
                        gSstpCfgEtwContext,
                        xmmword_1800146E0,
                        &v26);
        return (int)v8;
      }
      return (int)v8;
    }
    if ( CertGetEnhancedKeyUsage(pCertContext, 0, v6, pcbUsage) && pcbUsage[0] )
    {
      if ( v7->cUsageIdentifier )
      {
        v14 = 0;
        while ( _strcmpi(v7->rgpszUsageIdentifier[v14], "1.3.6.1.5.5.7.3.1") )
        {
          if ( !_strcmpi(v7->rgpszUsageIdentifier[v14], "2.5.29.37.0") )
            *a2 = 2;
          v14 = (unsigned int)(v14 + 1);
          if ( (unsigned int)v14 >= v7->cUsageIdentifier )
            goto LABEL_33;
        }
        *a2 = 1;
        goto LABEL_33;
      }
      v13 = 2;
      if ( GetLastError() != -2146885628 )
        v13 = 0;
    }
    else if ( GetLastError() == -2146885628 )
    {
      v13 = 2;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v16 = GetLastError();
        WPP_SF_d(v15, 0x10u, v17, v16);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v26) = 0;
        v18 = GetLastError();
        FormatRRASErrorString((wchar_t *)&v26, L"Unable to query the EKU: %d", v18);
        ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v26);
      }
      v13 = 0;
    }
    *a2 = v13;
LABEL_33:
    v19 = GetProcessHeap();
    LODWORD(v8) = HeapFree(v19, 0, v7);
    return (int)v8;
  }
  LODWORD(v8) = GetLastError();
  if ( (_DWORD)v8 == -2146885628 )
  {
    *a2 = 2;
  }
  else
  {
    v8 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v20 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v21 = GetLastError();
      LODWORD(v8) = WPP_SF_d(v20, 0xEu, v22, v21);
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v26) = 0;
      v23 = GetLastError();
      FormatRRASErrorString((wchar_t *)&v26, L"Unable to query the EKU: %d", v23);
      goto LABEL_42;
    }
  }
  return (int)v8;
}

```

## disassembly

```asm
0x1800070f0  mov     [rsp-8+arg_10], rbx
0x1800070f5  push    rbp
0x1800070f6  push    rsi
0x1800070f7  push    rdi
0x1800070f8  push    r14
0x1800070fa  push    r15
0x1800070fc  lea     rbp, [rsp-740h]
0x180007104  sub     rsp, 840h
0x18000710b  mov     rax, cs:__security_cookie
0x180007112  xor     rax, rsp
0x180007115  mov     [rbp+760h+var_30], rax
0x18000711c  mov     rsi, rdx
0x18000711f  mov     [rsp+860h+pcbUsage], 0
0x180007127  mov     r14, rcx
0x18000712a  xor     eax, eax
0x18000712c  xor     edx, edx; Val
0x18000712e  mov     [rsp+860h+var_830], eax
0x180007132  lea     rcx, [rsp+860h+var_82C]; void *
0x180007137  mov     r8d, 7FCh; Size
0x18000713d  call    memset_0
0x180007142  lea     r9, [rsp+860h+pcbUsage]; pcbUsage
0x180007147  mov     dword ptr [rsi], 0
0x18000714d  xor     r8d, r8d; pUsage
0x180007150  xor     edx, edx; dwFlags
0x180007152  mov     rcx, r14; pCertContext
0x180007155  call    cs:__imp_CertGetEnhancedKeyUsage
0x18000715b  test    eax, eax
0x18000715d  jz      loc_18000733F
0x180007163  mov     eax, [rsp+860h+pcbUsage]
0x180007167  test    eax, eax
0x180007169  jz      loc_18000733F
0x18000716f  mov     ebx, eax
0x180007171  call    cs:__imp_GetProcessHeap
0x180007177  mov     r8d, ebx; dwBytes
0x18000717a  xor     edx, edx; dwFlags
0x18000717c  mov     rcx, rax; hHeap
0x18000717f  call    cs:__imp_HeapAlloc
0x180007185  mov     rdi, rax
0x180007188  test    rax, rax
0x18000718b  jnz     short loc_1800071EB
0x18000718d  mov     rbx, cs:WPP_GLOBAL_Control
0x180007194  lea     rax, WPP_GLOBAL_Control
0x18000719b  cmp     rbx, rax
0x18000719e  jz      short loc_1800071C4
0x1800071a0  test    byte ptr [rbx+1Ch], 40h
0x1800071a4  jz      short loc_1800071C4
0x1800071a6  cmp     byte ptr [rbx+19h], 1
0x1800071aa  jb      short loc_1800071C4
0x1800071ac  mov     rbx, [rbx+10h]
0x1800071b0  call    cs:__imp_GetLastError
0x1800071b6  lea     edx, [rdi+0Fh]
0x1800071b9  mov     rcx, rbx
0x1800071bc  mov     r9d, eax
0x1800071bf  call    WPP_SF_d
0x1800071c4  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800071cc  jz      loc_1800073DA
0x1800071d2  xor     eax, eax
0x1800071d4  mov     word ptr [rsp+860h+var_830], ax
0x1800071d9  call    cs:__imp_GetLastError
0x1800071df  lea     rdx, aUnableToAlloca; "Unable to allocate memory for querying "...
0x1800071e6  jmp     loc_1800073AE
0x1800071eb  lea     r9, [rsp+860h+pcbUsage]; pcbUsage
0x1800071f0  mov     r8, rdi; pUsage
0x1800071f3  xor     edx, edx; dwFlags
0x1800071f5  mov     rcx, r14; pCertContext
0x1800071f8  call    cs:__imp_CertGetEnhancedKeyUsage
0x1800071fe  test    eax, eax
0x180007200  jz      loc_180007288
0x180007206  cmp     [rsp+860h+pcbUsage], 0
0x18000720b  jz      short loc_180007288
0x18000720d  cmp     dword ptr [rdi], 0
0x180007210  jnz     short loc_18000722C
0x180007212  call    cs:__imp_GetLastError
0x180007218  xor     ecx, ecx
0x18000721a  mov     ebx, 2
0x18000721f  cmp     eax, 80092004h
0x180007224  cmovnz  ebx, ecx
0x180007227  jmp     loc_180007324
0x18000722c  xor     r14d, r14d
0x18000722f  cmp     [rdi], r14d
0x180007232  jbe     loc_180007326
0x180007238  mov     rcx, [rdi+8]
0x18000723c  lea     rdx, String2; "1.3.6.1.5.5.7.3.1"
0x180007243  mov     rcx, [rcx+r14*8]; String1
0x180007247  call    cs:__imp__strcmpi
0x18000724d  test    eax, eax
0x18000724f  jz      short loc_18000727D
0x180007251  mov     rcx, [rdi+8]
0x180007255  lea     rdx, a2529370; "2.5.29.37.0"
0x18000725c  mov     rcx, [rcx+r14*8]; String1
0x180007260  call    cs:__imp__strcmpi
0x180007266  test    eax, eax
0x180007268  jnz     short loc_180007270
0x18000726a  mov     dword ptr [rsi], 2
0x180007270  inc     r14d
0x180007273  cmp     r14d, [rdi]
0x180007276  jb      short loc_180007238
0x180007278  jmp     loc_180007326
0x18000727d  mov     dword ptr [rsi], 1
0x180007283  jmp     loc_180007326
0x180007288  call    cs:__imp_GetLastError
0x18000728e  cmp     eax, 80092004h
0x180007293  jnz     short loc_18000729F
0x180007295  mov     ebx, 2
0x18000729a  jmp     loc_180007324
0x18000729f  mov     rbx, cs:WPP_GLOBAL_Control
0x1800072a6  lea     rax, WPP_GLOBAL_Control
0x1800072ad  cmp     rbx, rax
0x1800072b0  jz      short loc_1800072D8
0x1800072b2  test    byte ptr [rbx+1Ch], 40h
0x1800072b6  jz      short loc_1800072D8
0x1800072b8  cmp     byte ptr [rbx+19h], 1
0x1800072bc  jb      short loc_1800072D8
0x1800072be  mov     rbx, [rbx+10h]
0x1800072c2  call    cs:__imp_GetLastError
0x1800072c8  mov     edx, 10h
0x1800072cd  mov     rcx, rbx
0x1800072d0  mov     r9d, eax
0x1800072d3  call    WPP_SF_d
0x1800072d8  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800072e0  jz      short loc_180007322
0x1800072e2  xor     eax, eax
0x1800072e4  mov     word ptr [rsp+860h+var_830], ax
0x1800072e9  call    cs:__imp_GetLastError
0x1800072ef  mov     r8d, eax
0x1800072f2  lea     rdx, aUnableToQueryT_0; "Unable to query the EKU: %d"
0x1800072f9  lea     rcx, [rsp+860h+var_830]
0x1800072fe  call    FormatRRASErrorString
0x180007303  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000730a  lea     r8, [rsp+860h+var_830]
0x18000730f  mov     rcx, cs:gSstpCfgEtwContext
0x180007316  mov     rax, cs:gSstpCfgTemplateFunc
0x18000731d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007322  xor     ebx, ebx
0x180007324  mov     [rsi], ebx
0x180007326  call    cs:__imp_GetProcessHeap
0x18000732c  mov     r8, rdi; lpMem
0x18000732f  xor     edx, edx; dwFlags
0x180007331  mov     rcx, rax; hHeap
0x180007334  call    cs:__imp_HeapFree
0x18000733a  jmp     loc_1800073DA
0x18000733f  call    cs:__imp_GetLastError
0x180007345  cmp     eax, 80092004h
0x18000734a  jnz     short loc_180007357
0x18000734c  mov     dword ptr [rsi], 2
0x180007352  jmp     loc_1800073DA
0x180007357  mov     rbx, cs:WPP_GLOBAL_Control
0x18000735e  lea     rax, WPP_GLOBAL_Control
0x180007365  cmp     rbx, rax
0x180007368  jz      short loc_180007390
0x18000736a  test    byte ptr [rbx+1Ch], 40h
0x18000736e  jz      short loc_180007390
0x180007370  cmp     byte ptr [rbx+19h], 1
0x180007374  jb      short loc_180007390
0x180007376  mov     rbx, [rbx+10h]
0x18000737a  call    cs:__imp_GetLastError
0x180007380  mov     edx, 0Eh
0x180007385  mov     rcx, rbx
0x180007388  mov     r9d, eax
0x18000738b  call    WPP_SF_d
0x180007390  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180007398  jz      short loc_1800073DA
0x18000739a  xor     eax, eax
0x18000739c  mov     word ptr [rsp+860h+var_830], ax
0x1800073a1  call    cs:__imp_GetLastError
0x1800073a7  lea     rdx, aUnableToQueryT_0; "Unable to query the EKU: %d"
0x1800073ae  mov     r8d, eax
0x1800073b1  lea     rcx, [rsp+860h+var_830]
0x1800073b6  call    FormatRRASErrorString
0x1800073bb  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800073c2  lea     r8, [rsp+860h+var_830]
0x1800073c7  mov     rcx, cs:gSstpCfgEtwContext
0x1800073ce  mov     rax, cs:gSstpCfgTemplateFunc
0x1800073d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073da  mov     rcx, [rbp+760h+var_30]
0x1800073e1  xor     rcx, rsp; StackCookie
0x1800073e4  call    __security_check_cookie
0x1800073e9  mov     rbx, [rsp+860h+arg_10]
0x1800073f1  add     rsp, 840h
0x1800073f8  pop     r15
0x1800073fa  pop     r14
0x1800073fc  pop     rdi
0x1800073fd  pop     rsi
0x1800073fe  pop     rbp
0x1800073ff  retn
```
