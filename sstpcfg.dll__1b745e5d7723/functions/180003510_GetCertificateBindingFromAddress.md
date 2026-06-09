# GetCertificateBindingFromAddress

- ea: `0x180003510`
- end: `0x180003819`
- name: `GetCertificateBindingFromAddress`
- size: `777`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001d10`
- `0x180007450`

## callees

- `0x180003510`
- `0x18000a014`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003681`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003681`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000366e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003766`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000366e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003766`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003774`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003774`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x1800035ed`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x180003757`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x1800035ed`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x180003757`
- `rtutils!RouterLogEventStringW` at `0x1800036b5`
- `rtutils!RouterLogEventStringW` at `0x1800036b5`

## string_xrefs

- `0x1800037c8`: `GetCertificateBindingFromAddress operation completed with status: %d`

## pseudocode

```c
__int64 __fastcall GetCertificateBindingFromAddress(__int16 a1, __int16 a2, void **a3, ULONG *a4)
{
  __int64 v8; // r8
  ULONG v9; // eax
  ULONG v10; // edi
  _QWORD *v11; // rcx
  ULONG v12; // ebx
  HANDLE ProcessHeap; // rax
  void *pOutput; // rax
  void *v15; // rbx
  HANDLE v16; // rax
  __int128 pInput; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h]
  _WORD v20[64]; // [rsp+60h] [rbp-A0h] BYREF
  int v21; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v22[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  v19 = 0;
  pInput = 0;
  memset_0(v20, 0, sizeof(v20));
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  if ( !a3 || !a4 || (*a3 = 0, v20[0] = a1, a1 != 2) && a1 != 23 )
  {
    v10 = 87;
    goto LABEL_24;
  }
  v20[1] = __ROR2__(a2, 8);
  *((_QWORD *)&pInput + 1) = v20;
  LODWORD(v19) = 0;
  v9 = HttpQueryServiceConfiguration(0, HttpServiceConfigSSLCertInfo, &pInput, 0x18u, 0, 0, a4, 0);
  v10 = v9;
  if ( v9 == 2 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30);
      v11 = WPP_GLOBAL_Control;
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSstpCfgTemplateFunc)(
        gSstpCfgEtwContext,
        xmmword_1800146E0,
        L"Unable to query the SSL certificate: ERROR_FILE_NOT_FOUND");
      v11 = WPP_GLOBAL_Control;
    }
    v10 = 0;
    goto LABEL_25;
  }
  if ( v9 != 122 )
  {
LABEL_24:
    v11 = WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  v12 = *a4;
  ProcessHeap = GetProcessHeap();
  v10 = 8;
  pOutput = HeapAlloc(ProcessHeap, 8u, v12);
  *a3 = pOutput;
  if ( pOutput )
  {
    v10 = HttpQueryServiceConfiguration(0, HttpServiceConfigSSLCertInfo, &pInput, 0x18u, pOutput, *a4, 0, 0);
    if ( v10 )
    {
      v15 = *a3;
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v15);
      *a3 = 0;
      *a4 = 0;
    }
    goto LABEL_24;
  }
  RouterLogEventStringW(EventSource, 1u, 0x14u, 0, 0, 8u, 0);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v8, 8);
    v11 = WPP_GLOBAL_Control;
  }
  if ( (_QWORD)xmmword_1800146E0 )
  {
    LOWORD(v21) = 0;
    FormatRRASErrorString(&v21, L"Unable to alloate memory to query the cert: %d", 8);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v21);
    goto LABEL_24;
  }
LABEL_25:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 && *((_BYTE *)v11 + 25) >= 3u )
    WPP_SF_d(v11[2], 32, v8, v10);
  if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
  {
    LOWORD(v21) = 0;
    FormatRRASErrorString(&v21, L"GetCertificateBindingFromAddress operation completed with status: %d", v10);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
      gSstpCfgEtwContext,
      *((_QWORD *)&xmmword_1800146E0 + 1),
      &v21);
  }
  return v10;
}

```

## disassembly

```asm
0x180003510  push    rbp
0x180003512  push    rbx
0x180003513  push    rsi
0x180003514  push    rdi
0x180003515  push    r13
0x180003517  push    r14
0x180003519  push    r15
0x18000351b  lea     rbp, [rsp-7F0h]
0x180003523  sub     rsp, 8F0h
0x18000352a  mov     rax, cs:__security_cookie
0x180003531  xor     rax, rsp
0x180003534  mov     [rbp+820h+var_40], rax
0x18000353b  mov     r14, r8
0x18000353e  mov     edi, edx
0x180003540  movzx   ebx, cx
0x180003543  xorps   xmm0, xmm0
0x180003546  xor     eax, eax
0x180003548  lea     rcx, [rsp+920h+var_8C0]; void *
0x18000354d  xor     edx, edx; Val
0x18000354f  mov     [rsp+920h+var_8D0], rax
0x180003554  mov     r8d, 80h; Size
0x18000355a  mov     rsi, r9
0x18000355d  movups  [rsp+920h+pInput], xmm0
0x180003562  call    memset_0
0x180003567  xor     r15d, r15d
0x18000356a  lea     rcx, [rbp+820h+var_83C]; void *
0x18000356e  xor     edx, edx; Val
0x180003570  mov     [rbp+820h+var_840], r15d
0x180003574  mov     r8d, 7FCh; Size
0x18000357a  call    memset_0
0x18000357f  test    r14, r14
0x180003582  jz      loc_180003782
0x180003588  test    rsi, rsi
0x18000358b  jz      loc_180003782
0x180003591  lea     r13d, [r15+2]
0x180003595  mov     [r14], r15
0x180003598  mov     [rsp+920h+var_8C0], bx
0x18000359d  cmp     r13w, bx
0x1800035a1  jz      short loc_1800035B0
0x1800035a3  lea     eax, [r15+17h]
0x1800035a7  cmp     ax, bx
0x1800035aa  jnz     loc_180003782
0x1800035b0  mov     [rsp+920h+pOverlapped], r15; pOverlapped
0x1800035b5  lea     rax, [rsp+920h+var_8C0]
0x1800035ba  mov     r9d, 18h; InputLength
0x1800035c0  mov     [rsp+920h+pReturnLength], rsi; pReturnLength
0x1800035c5  ror     di, 8
0x1800035c9  lea     r8, [rsp+920h+pInput]; pInput
0x1800035ce  mov     [rsp+920h+OutputLength], r15d; OutputLength
0x1800035d3  xor     ecx, ecx; ServiceHandle
0x1800035d5  mov     [rsp+920h+var_8BE], di
0x1800035da  lea     edx, [r9-17h]; ConfigId
0x1800035de  mov     qword ptr [rsp+920h+pInput+8], rax
0x1800035e3  mov     dword ptr [rsp+920h+var_8D0], r15d
0x1800035e8  mov     [rsp+920h+pOutput], r15; pOutput
0x1800035ed  call    cs:__imp_HttpQueryServiceConfiguration
0x1800035f3  mov     edi, eax
0x1800035f5  cmp     eax, r13d
0x1800035f8  jnz     short loc_180003663
0x1800035fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180003601  lea     rbx, WPP_GLOBAL_Control
0x180003608  cmp     rcx, rbx
0x18000360b  jz      short loc_18000362E
0x18000360d  test    byte ptr [rcx+1Ch], 40h
0x180003611  jz      short loc_18000362E
0x180003613  cmp     byte ptr [rcx+19h], 1
0x180003617  jb      short loc_18000362E
0x180003619  mov     rcx, [rcx+10h]
0x18000361d  mov     edx, 1Eh
0x180003622  call    WPP_SF_
0x180003627  mov     rcx, cs:WPP_GLOBAL_Control
0x18000362e  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180003635  test    rdx, rdx
0x180003638  jz      short loc_18000365B
0x18000363a  mov     rcx, cs:gSstpCfgEtwContext
0x180003641  lea     r8, aUnableToQueryT_1; "Unable to query the SSL certificate: ER"...
0x180003648  mov     rax, cs:gSstpCfgTemplateFunc
0x18000364f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003654  mov     rcx, cs:WPP_GLOBAL_Control
0x18000365b  mov     edi, r15d
0x18000365e  jmp     loc_180003795
0x180003663  cmp     eax, 7Ah ; 'z'
0x180003666  jnz     loc_180003787
0x18000366c  mov     ebx, [rsi]
0x18000366e  call    cs:__imp_GetProcessHeap
0x180003674  mov     edi, 8
0x180003679  mov     r8d, ebx; dwBytes
0x18000367c  mov     rcx, rax; hHeap
0x18000367f  mov     edx, edi; dwFlags
0x180003681  call    cs:__imp_HeapAlloc
0x180003687  mov     [r14], rax
0x18000368a  mov     rcx, rax
0x18000368d  lea     edx, [rdi-7]; ConfigId
0x180003690  test    rax, rax
0x180003693  jnz     loc_180003735
0x180003699  mov     rcx, cs:EventSource; hLogHandle
0x1800036a0  lea     r8d, [rdi+0Ch]; dwMessageId
0x1800036a4  mov     dword ptr [rsp+920h+pReturnLength], r15d; dwErrorIndex
0x1800036a9  xor     r9d, r9d; dwSubStringCount
0x1800036ac  mov     [rsp+920h+OutputLength], edi; dwErrorCode
0x1800036b0  mov     [rsp+920h+pOutput], r15; plpszSubStringArray
0x1800036b5  call    cs:__imp_RouterLogEventStringW
0x1800036bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036c2  lea     rbx, WPP_GLOBAL_Control
0x1800036c9  cmp     rcx, rbx
0x1800036cc  jz      short loc_1800036F0
0x1800036ce  test    byte ptr [rcx+1Ch], 40h
0x1800036d2  jz      short loc_1800036F0
0x1800036d4  cmp     byte ptr [rcx+19h], 1
0x1800036d8  jb      short loc_1800036F0
0x1800036da  mov     rcx, [rcx+10h]
0x1800036de  lea     edx, [rdi+17h]
0x1800036e1  mov     r9d, edi
0x1800036e4  call    WPP_SF_d
0x1800036e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036f0  cmp     qword ptr cs:xmmword_1800146E0, r15
0x1800036f7  jz      loc_180003795
0x1800036fd  mov     r8d, edi
0x180003700  mov     word ptr [rbp+820h+var_840], r15w
0x180003705  lea     rdx, aUnableToAlloat; "Unable to alloate memory to query the c"...
0x18000370c  lea     rcx, [rbp+820h+var_840]
0x180003710  call    FormatRRASErrorString
0x180003715  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000371c  lea     r8, [rbp+820h+var_840]
0x180003720  mov     rcx, cs:gSstpCfgEtwContext
0x180003727  mov     rax, cs:gSstpCfgTemplateFunc
0x18000372e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003733  jmp     short loc_18000378E
0x180003735  mov     eax, [rsi]
0x180003737  lea     r8, [rsp+920h+pInput]; pInput
0x18000373c  mov     [rsp+920h+pOverlapped], r15; pOverlapped
0x180003741  mov     r9d, 18h; InputLength
0x180003747  mov     [rsp+920h+pReturnLength], r15; pReturnLength
0x18000374c  mov     [rsp+920h+OutputLength], eax; OutputLength
0x180003750  mov     [rsp+920h+pOutput], rcx; pOutput
0x180003755  xor     ecx, ecx; ServiceHandle
0x180003757  call    cs:__imp_HttpQueryServiceConfiguration
0x18000375d  mov     edi, eax
0x18000375f  test    eax, eax
0x180003761  jz      short loc_180003787
0x180003763  mov     rbx, [r14]
0x180003766  call    cs:__imp_GetProcessHeap
0x18000376c  mov     r8, rbx; lpMem
0x18000376f  xor     edx, edx; dwFlags
0x180003771  mov     rcx, rax; hHeap
0x180003774  call    cs:__imp_HeapFree
0x18000377a  mov     [r14], r15
0x18000377d  mov     [rsi], r15d
0x180003780  jmp     short loc_180003787
0x180003782  mov     edi, 57h ; 'W'
0x180003787  lea     rbx, WPP_GLOBAL_Control
0x18000378e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003795  cmp     rcx, rbx
0x180003798  jz      short loc_1800037B7
0x18000379a  test    byte ptr [rcx+1Ch], 40h
0x18000379e  jz      short loc_1800037B7
0x1800037a0  cmp     byte ptr [rcx+19h], 3
0x1800037a4  jb      short loc_1800037B7
0x1800037a6  mov     rcx, [rcx+10h]
0x1800037aa  mov     edx, 20h ; ' '
0x1800037af  mov     r9d, edi
0x1800037b2  call    WPP_SF_d
0x1800037b7  cmp     qword ptr cs:xmmword_1800146E0+8, r15
0x1800037be  jz      short loc_1800037F6
0x1800037c0  mov     r8d, edi
0x1800037c3  mov     word ptr [rbp+820h+var_840], r15w
0x1800037c8  lea     rdx, aGetcertificate_2; "GetCertificateBindingFromAddress operat"...
0x1800037cf  lea     rcx, [rbp+820h+var_840]
0x1800037d3  call    FormatRRASErrorString
0x1800037d8  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x1800037df  lea     r8, [rbp+820h+var_840]
0x1800037e3  mov     rcx, cs:gSstpCfgEtwContext
0x1800037ea  mov     rax, cs:gSstpCfgTemplateFunc
0x1800037f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f6  mov     eax, edi
0x1800037f8  mov     rcx, [rbp+820h+var_40]
0x1800037ff  xor     rcx, rsp; StackCookie
0x180003802  call    __security_check_cookie
0x180003807  add     rsp, 8F0h
0x18000380e  pop     r15
0x180003810  pop     r14
0x180003812  pop     r13
0x180003814  pop     rdi
0x180003815  pop     rsi
0x180003816  pop     rbx
0x180003817  pop     rbp
0x180003818  retn
```
