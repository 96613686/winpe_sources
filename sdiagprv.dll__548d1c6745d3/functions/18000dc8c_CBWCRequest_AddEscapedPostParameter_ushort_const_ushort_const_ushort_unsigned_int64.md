# CBWCRequest::AddEscapedPostParameter(ushort const *,ushort const *,ushort * *,unsigned __int64 *)

- ea: `0x18000dc8c`
- end: `0x18000e1b4`
- name: `?AddEscapedPostParameter@CBWCRequest@@AEBAJPEBG0PEAPEAGPEA_K@Z`
- size: `1320`
- prototype: `__int64 __fastcall(CBWCRequest *this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000e1bc`
- `0x18000f0ec`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180003350`
- `0x1800033a4`
- `0x180003400`
- `0x1800034e4`
- `0x18000dc8c`
- `0x18000edd4`
- `0x1800180be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ddf9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000de43`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000df7f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dff5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ddf9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000de43`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000df7f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dff5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000deb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e09c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e166`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e17f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e19c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000deb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e09c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e166`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e17f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e19c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dde4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000deaa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dfe3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e08d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e158`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e171`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e18e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dde4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000deaa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dfe3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e08d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e158`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e171`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e18e`
- `SHLWAPI!UrlEscapeW` at `0x18000de9a`
- `SHLWAPI!UrlEscapeW` at `0x18000de9a`

## pseudocode

```c
__int64 __fastcall CBWCRequest::AddEscapedPostParameter(
        CBWCRequest *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  const unsigned __int16 **v5; // r13
  HRESULT v7; // ebx
  unsigned __int64 *v8; // rax
  WCHAR *v9; // r15
  WCHAR *v10; // rdi
  unsigned __int16 *v11; // r12
  const char *v12; // rax
  HANDLE ProcessHeap; // rax
  size_t v14; // rbx
  WCHAR *v15; // rax
  __int64 *v16; // rdx
  HANDLE v17; // rax
  WCHAR *v18; // rax
  unsigned __int64 v19; // rdx
  unsigned __int64 i; // rax
  unsigned __int16 v21; // cx
  HANDLE v22; // rax
  unsigned __int64 v23; // r13
  unsigned __int64 v24; // r11
  char *v25; // r14
  HANDLE v26; // rax
  WCHAR *v27; // rax
  HANDLE v28; // rax
  unsigned __int16 *v29; // rax
  const wchar_t *v30; // r9
  unsigned __int16 *v31; // rcx
  unsigned __int64 v32; // rdx
  HANDLE v33; // rax
  unsigned __int64 *v34; // rax
  __int64 v35; // r9
  HANDLE v36; // rax
  HANDLE v37; // rax
  HANDLE v38; // rax
  unsigned __int64 v40; // [rsp+30h] [rbp-30h] BYREF
  SIZE_T Size; // [rsp+38h] [rbp-28h] BYREF
  SIZE_T v42; // [rsp+40h] [rbp-20h] BYREF
  SIZE_T dwBytes; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v44; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int64 v45; // [rsp+58h] [rbp-8h] BYREF
  unsigned __int64 pcchEscaped; // [rsp+A0h] [rbp+40h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp+48h]
  const unsigned __int16 **v48; // [rsp+B8h] [rbp+58h]

  v48 = a4;
  lpMem = a2;
  v40 = 0;
  v5 = a4;
  v45 = 0;
  pcchEscaped = 0;
  dwBytes = 0;
  v44 = 0;
  Size = 0;
  v42 = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"CBWCRequest::AddEscapedPostParameter",
        -2147024809,
        (__int64)"ParamName");
    return (unsigned int)v7;
  }
  v8 = a5;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  if ( !a4 || !a5 )
  {
    v7 = -2147024809;
    goto LABEL_14;
  }
  v7 = 0;
  if ( !a3 )
  {
LABEL_67:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
      goto LABEL_70;
    v16 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
    goto LABEL_69;
  }
  v7 = StringCchLengthW(a3, 0x7FFFFFFFu, &v40);
  if ( v7 < 0 )
    goto LABEL_55;
  v7 = ULongLongMult(v40, 3u, &pcchEscaped);
  if ( v7 < 0 )
    goto LABEL_55;
  this = (CBWCRequest *)(pcchEscaped + 1);
  if ( pcchEscaped + 1 < pcchEscaped )
  {
    pcchEscaped = -1;
    goto LABEL_53;
  }
  ++pcchEscaped;
  if ( (unsigned __int64)this <= 0x824 )
  {
    v7 = ULongLongMult((unsigned __int64)this, 2u, &dwBytes);
    if ( v7 < 0 )
      goto LABEL_55;
    ProcessHeap = GetProcessHeap();
    v14 = dwBytes;
    v15 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, dwBytes);
    v9 = v15;
    if ( !v15 )
      goto LABEL_19;
    memset_0(v15, 0, v14);
    v17 = GetProcessHeap();
    v18 = (WCHAR *)HeapAlloc(v17, 8u, v14);
    v10 = v18;
    if ( !v18 )
      goto LABEL_19;
    memset_0(v18, 0, v14);
    v19 = v40;
    for ( i = 0; i < v19; ++i )
    {
      v21 = a3[i];
      if ( v21 == 32 )
        v21 = 43;
      v10[i] = v21;
    }
    v7 = UrlEscapeW(v10, v9, (DWORD *)&pcchEscaped, 0x3000u);
    if ( v7 >= 0 )
    {
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v10);
      v10 = 0;
      v7 = StringCchLengthW(*v5, 0x7FFFFFFFu, &v44);
      if ( v7 >= 0 )
      {
        v23 = v44;
        if ( (v44 != 0) + v44 >= v44 )
        {
          v7 = StringCchLengthW((const unsigned __int16 *)lpMem, 0x7FFFFFFFu, &v45);
          if ( v7 < 0 )
            goto LABEL_54;
          this = (CBWCRequest *)(v24 + v45);
          if ( v24 + v45 >= v24 )
          {
            a2 = (unsigned __int16 *)((char *)this + 1);
            if ( (CBWCRequest *)((char *)this + 1) >= this )
            {
              this = (CBWCRequest *)((char *)a2 + pcchEscaped);
              if ( (unsigned __int16 *)((char *)a2 + pcchEscaped) >= a2 )
              {
                v25 = (char *)this + 1;
                if ( (CBWCRequest *)((char *)this + 1) >= this )
                {
                  if ( (unsigned __int64)v25 <= *a5 )
                    goto LABEL_80;
                  v7 = ULongLongMult((unsigned __int64)this + 1, 2u, &Size);
                  if ( v7 >= 0 )
                  {
                    v26 = GetProcessHeap();
                    v27 = (WCHAR *)HeapAlloc(v26, 8u, Size);
                    v10 = v27;
                    if ( !v27 )
                      goto LABEL_19;
                    memset_0(v27, 0, Size);
                    v7 = StringCchCopyNW(v10, (unsigned __int64)v25, *v48, v23);
                    if ( v7 >= 0 )
                    {
LABEL_80:
                      v45 = (unsigned __int64)&v25[-v23];
                      v7 = ULongLongMult((unsigned __int64)&v25[-v23], 2u, &v42);
                      if ( v7 >= 0 )
                      {
                        v28 = GetProcessHeap();
                        v29 = (unsigned __int16 *)HeapAlloc(v28, 8u, v42);
                        v11 = v29;
                        if ( v29 )
                        {
                          memset_0(v29, 0, v42);
                          v30 = L"&";
                          if ( !v23 )
                            v30 = (const wchar_t *)&Format;
                          v7 = StringCchPrintfW(v11, v45, L"%s%s=%s", v30, lpMem, v9);
                          if ( v7 >= 0 )
                          {
                            v5 = v48;
                            if ( v10 )
                            {
                              v31 = v10;
                              v32 = (unsigned __int64)v25;
                            }
                            else
                            {
                              v31 = (unsigned __int16 *)*v48;
                              v32 = *a5;
                            }
                            v7 = StringCchCatW(v31, v32, v11);
                            if ( v7 >= 0 )
                            {
                              if ( v10 )
                              {
                                lpMem = (LPVOID)*v5;
                                if ( lpMem )
                                {
                                  v33 = GetProcessHeap();
                                  HeapFree(v33, 0, lpMem);
                                }
                                v34 = a5;
                                *v5 = v10;
                                *v34 = (unsigned __int64)v25;
                                goto LABEL_57;
                              }
LABEL_56:
                              if ( v7 == -2147024809 )
                                goto LABEL_13;
LABEL_57:
                              if ( v7 )
                                goto LABEL_58;
                              goto LABEL_67;
                            }
                            goto LABEL_55;
                          }
                          goto LABEL_54;
                        }
LABEL_19:
                        v7 = -2147024882;
                        goto LABEL_20;
                      }
                    }
                  }
LABEL_54:
                  v5 = v48;
                  goto LABEL_55;
                }
              }
            }
          }
        }
LABEL_53:
        v7 = -2147024362;
LABEL_58:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_70;
        v35 = (unsigned int)v7;
LABEL_60:
        McTemplateU0sq_EventWriteTransfer(this, a2, "CBWCRequest::AddEscapedPostParameter", v35);
        goto LABEL_70;
      }
    }
LABEL_55:
    if ( v7 != -2147024882 )
      goto LABEL_56;
LABEL_20:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_70;
    v16 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
LABEL_69:
    McTemplateU0s_EventWriteTransfer(this, v16, "CBWCRequest::AddEscapedPostParameter");
    goto LABEL_70;
  }
  v7 = -2147024809;
LABEL_13:
  v8 = a5;
LABEL_14:
  if ( !v5 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      v12 = "Buffer";
LABEL_64:
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        (_DWORD)a2,
        (unsigned int)"CBWCRequest::AddEscapedPostParameter",
        -2147024809,
        (__int64)v12);
      goto LABEL_70;
    }
    goto LABEL_70;
  }
  if ( v8 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_70;
    v35 = 2147942487LL;
    goto LABEL_60;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v12 = "BufferLength";
    goto LABEL_64;
  }
LABEL_70:
  if ( v9 )
  {
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v9);
  }
  if ( v11 )
  {
    v37 = GetProcessHeap();
    HeapFree(v37, 0, v11);
  }
  if ( v7 < 0 && v10 )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, v10);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000dc8c  mov     r11, rsp
0x18000dc8f  mov     [r11+20h], r9
0x18000dc93  mov     [r11+10h], rdx
0x18000dc97  mov     [r11+8], rcx
0x18000dc9b  push    rbp
0x18000dc9c  push    rbx
0x18000dc9d  push    rdi
0x18000dc9e  push    r12
0x18000dca0  push    r13
0x18000dca2  push    r14
0x18000dca4  push    r15
0x18000dca6  mov     rbp, rsp
0x18000dca9  sub     rsp, 60h
0x18000dcad  mov     [rbp+var_30], 0
0x18000dcb5  mov     r13, r9
0x18000dcb8  mov     [rbp+var_8], 0
0x18000dcc0  mov     r14, r8
0x18000dcc3  mov     [rbp+pcchEscaped], 0
0x18000dccb  mov     [rbp+dwBytes], 0
0x18000dcd3  mov     [rbp+var_10], 0
0x18000dcdb  mov     [rbp+Size], 0
0x18000dce3  mov     [rbp+var_20], 0
0x18000dceb  test    rdx, rdx
0x18000dcee  jnz     short loc_18000DD24
0x18000dcf0  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000dcf7  mov     ebx, 80070057h
0x18000dcfc  jz      loc_18000E1A2
0x18000dd02  lea     rax, aParamname; "ParamName"
0x18000dd09  mov     r9d, 80070057h
0x18000dd0f  lea     r8, aCbwcrequestAdd_1; "CBWCRequest::AddEscapedPostParameter"
0x18000dd16  mov     [r11-78h], rax
0x18000dd1a  call    McTemplateU0sqs_EventWriteTransfer
0x18000dd1f  jmp     loc_18000E1A2
0x18000dd24  mov     rax, [rbp+arg_20]
0x18000dd28  xor     r15d, r15d
0x18000dd2b  xor     edi, edi
0x18000dd2d  xor     r12d, r12d
0x18000dd30  test    r13, r13
0x18000dd33  jnz     short loc_18000DD3C
0x18000dd35  mov     ebx, 80070057h
0x18000dd3a  jmp     short loc_18000DDAA
0x18000dd3c  test    rax, rax
0x18000dd3f  jz      short loc_18000DD35
0x18000dd41  xor     ebx, ebx
0x18000dd43  test    r14, r14
0x18000dd46  jz      loc_18000E137
0x18000dd4c  lea     r8, [rbp+var_30]; unsigned __int64 *
0x18000dd50  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000dd55  mov     rcx, r14; unsigned __int16 *
0x18000dd58  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000dd5d  mov     ebx, eax
0x18000dd5f  test    eax, eax
0x18000dd61  js      loc_18000E0C2
0x18000dd67  mov     rcx, [rbp+var_30]; unsigned __int64
0x18000dd6b  lea     r8, [rbp+pcchEscaped]; unsigned __int64 *
0x18000dd6f  mov     edx, 3; unsigned __int64
0x18000dd74  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000dd79  mov     ebx, eax
0x18000dd7b  test    eax, eax
0x18000dd7d  js      loc_18000E0C2
0x18000dd83  mov     rax, [rbp+pcchEscaped]
0x18000dd87  lea     rcx, [rax+1]; unsigned __int64
0x18000dd8b  cmp     rcx, rax
0x18000dd8e  jb      loc_18000E0AF
0x18000dd94  mov     [rbp+pcchEscaped], rcx
0x18000dd98  cmp     rcx, 824h
0x18000dd9f  jbe     short loc_18000DDCC
0x18000dda1  mov     ebx, 80070057h
0x18000dda6  mov     rax, [rbp+arg_20]
0x18000ddaa  test    r13, r13
0x18000ddad  jnz     loc_18000E0F8
0x18000ddb3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000ddba  jz      loc_18000E153
0x18000ddc0  lea     rax, aBuffer; "Buffer"
0x18000ddc7  jmp     loc_18000E10D
0x18000ddcc  lea     r8, [rbp+dwBytes]; unsigned __int64 *
0x18000ddd0  mov     edx, 2; unsigned __int64
0x18000ddd5  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000ddda  mov     ebx, eax
0x18000dddc  test    eax, eax
0x18000ddde  js      loc_18000E0C2
0x18000dde4  call    cs:__imp_GetProcessHeap
0x18000ddea  mov     rbx, [rbp+dwBytes]
0x18000ddee  mov     edx, 8; dwFlags
0x18000ddf3  mov     r8, rbx; dwBytes
0x18000ddf6  mov     rcx, rax; hHeap
0x18000ddf9  call    cs:__imp_HeapAlloc
0x18000ddff  mov     r15, rax
0x18000de02  test    rax, rax
0x18000de05  jnz     short loc_18000DE25
0x18000de07  mov     ebx, 8007000Eh
0x18000de0c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000de13  jz      loc_18000E153
0x18000de19  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000de20  jmp     loc_18000E147
0x18000de25  mov     r8, rbx; Size
0x18000de28  xor     edx, edx; Val
0x18000de2a  mov     rcx, r15; void *
0x18000de2d  call    memset_0
0x18000de32  call    cs:__imp_GetProcessHeap
0x18000de38  mov     r8, rbx; dwBytes
0x18000de3b  mov     edx, 8; dwFlags
0x18000de40  mov     rcx, rax; hHeap
0x18000de43  call    cs:__imp_HeapAlloc
0x18000de49  mov     rdi, rax
0x18000de4c  test    rax, rax
0x18000de4f  jz      short loc_18000DE07
0x18000de51  mov     r8, rbx; Size
0x18000de54  xor     edx, edx; Val
0x18000de56  mov     rcx, rax; void *
0x18000de59  call    memset_0
0x18000de5e  mov     rdx, [rbp+var_30]
0x18000de62  xor     eax, eax
0x18000de64  test    rdx, rdx
0x18000de67  jz      short loc_18000DE8A
0x18000de69  movzx   ecx, word ptr [r14+rax*2]
0x18000de6e  mov     r8d, 20h ; ' '
0x18000de74  cmp     r8w, cx
0x18000de78  jnz     short loc_18000DE7E
0x18000de7a  lea     ecx, [r8+0Bh]
0x18000de7e  mov     [rdi+rax*2], cx
0x18000de82  inc     rax
0x18000de85  cmp     rax, rdx
0x18000de88  jb      short loc_18000DE69
0x18000de8a  mov     r9d, 3000h; dwFlags
0x18000de90  lea     r8, [rbp+pcchEscaped]; pcchEscaped
0x18000de94  mov     rdx, r15; pszEscaped
0x18000de97  mov     rcx, rdi; pszUrl
0x18000de9a  call    cs:__imp_UrlEscapeW
0x18000dea0  mov     ebx, eax
0x18000dea2  test    eax, eax
0x18000dea4  js      loc_18000E0C2
0x18000deaa  call    cs:__imp_GetProcessHeap
0x18000deb0  mov     r8, rdi; lpMem
0x18000deb3  xor     edx, edx; dwFlags
0x18000deb5  mov     rcx, rax; hHeap
0x18000deb8  call    cs:__imp_HeapFree
0x18000debe  mov     rcx, [r13+0]; unsigned __int16 *
0x18000dec2  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18000dec6  mov     r14d, 7FFFFFFFh
0x18000decc  xor     edi, edi
0x18000dece  mov     edx, r14d; unsigned __int64
0x18000ded1  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000ded6  mov     ebx, eax
0x18000ded8  test    eax, eax
0x18000deda  js      loc_18000E0C2
0x18000dee0  mov     r13, [rbp+var_10]
0x18000dee4  xor     eax, eax
0x18000dee6  test    r13, r13
0x18000dee9  setnz   al
0x18000deec  lea     r11, [rax+r13]
0x18000def0  cmp     r11, r13
0x18000def3  jb      loc_18000E0B7
0x18000def9  mov     rcx, [rbp+lpMem]; unsigned __int16 *
0x18000defd  lea     r8, [rbp+var_8]; unsigned __int64 *
0x18000df01  mov     edx, r14d; unsigned __int64
0x18000df04  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000df09  mov     ebx, eax
0x18000df0b  test    eax, eax
0x18000df0d  js      loc_18000E0BE
0x18000df13  mov     rcx, [rbp+var_8]
0x18000df17  add     rcx, r11
0x18000df1a  cmp     rcx, r11
0x18000df1d  jb      loc_18000E0B7
0x18000df23  lea     rdx, [rcx+1]
0x18000df27  cmp     rdx, rcx
0x18000df2a  jb      loc_18000E0B7
0x18000df30  mov     rcx, [rbp+pcchEscaped]
0x18000df34  add     rcx, rdx
0x18000df37  cmp     rcx, rdx
0x18000df3a  jb      loc_18000E0B7
0x18000df40  lea     r14, [rcx+1]
0x18000df44  cmp     r14, rcx
0x18000df47  jb      loc_18000E0B7
0x18000df4d  mov     rax, [rbp+arg_20]
0x18000df51  cmp     r14, [rax]
0x18000df54  jbe     short loc_18000DFBE
0x18000df56  lea     r8, [rbp+Size]; unsigned __int64 *
0x18000df5a  mov     rcx, r14; unsigned __int64
0x18000df5d  lea     edx, [rdi+2]; unsigned __int64
0x18000df60  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000df65  mov     ebx, eax
0x18000df67  test    eax, eax
0x18000df69  js      loc_18000E0BE
0x18000df6f  call    cs:__imp_GetProcessHeap
0x18000df75  mov     r8, [rbp+Size]; dwBytes
0x18000df79  lea     edx, [rdi+8]; dwFlags
0x18000df7c  mov     rcx, rax; hHeap
0x18000df7f  call    cs:__imp_HeapAlloc
0x18000df85  mov     rdi, rax
0x18000df88  test    rax, rax
0x18000df8b  jz      loc_18000DE07
0x18000df91  mov     r8, [rbp+Size]; Size
0x18000df95  xor     edx, edx; Val
0x18000df97  mov     rcx, rax; void *
0x18000df9a  call    memset_0
0x18000df9f  mov     r8, [rbp+arg_18]
0x18000dfa3  mov     r9, r13; unsigned __int64
0x18000dfa6  mov     rdx, r14; unsigned __int64
0x18000dfa9  mov     rcx, rdi; unsigned __int16 *
0x18000dfac  mov     r8, [r8]; unsigned __int16 *
0x18000dfaf  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000dfb4  mov     ebx, eax
0x18000dfb6  test    eax, eax
0x18000dfb8  js      loc_18000E0BE
0x18000dfbe  mov     rax, r14
0x18000dfc1  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18000dfc5  sub     rax, r13
0x18000dfc8  mov     edx, 2; unsigned __int64
0x18000dfcd  mov     rcx, rax; unsigned __int64
0x18000dfd0  mov     [rbp+var_8], rax
0x18000dfd4  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000dfd9  mov     ebx, eax
0x18000dfdb  test    eax, eax
0x18000dfdd  js      loc_18000E0BE
0x18000dfe3  call    cs:__imp_GetProcessHeap
0x18000dfe9  mov     r8, [rbp+var_20]; dwBytes
0x18000dfed  mov     edx, 8; dwFlags
0x18000dff2  mov     rcx, rax; hHeap
0x18000dff5  call    cs:__imp_HeapAlloc
0x18000dffb  mov     r12, rax
0x18000dffe  test    rax, rax
0x18000e001  jz      loc_18000DE07
0x18000e007  mov     r8, [rbp+var_20]; Size
0x18000e00b  xor     edx, edx; Val
0x18000e00d  mov     rcx, rax; void *
0x18000e010  call    memset_0
0x18000e015  mov     rdx, [rbp+var_8]; unsigned __int64
0x18000e019  lea     rax, Format
0x18000e020  test    r13, r13
0x18000e023  mov     [rsp+60h+var_38], r15
0x18000e028  lea     r9, asc_18001CFC8; "&"
0x18000e02f  mov     rcx, r12; unsigned __int16 *
0x18000e032  cmovz   r9, rax
0x18000e036  lea     r8, aSSS_0; "%s%s=%s"
0x18000e03d  mov     rax, [rbp+lpMem]
0x18000e041  mov     [rsp+60h+var_40], rax
0x18000e046  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e04b  mov     ebx, eax
0x18000e04d  test    eax, eax
0x18000e04f  js      short loc_18000E0BE
0x18000e051  mov     r13, [rbp+arg_18]
0x18000e055  test    rdi, rdi
0x18000e058  jz      short loc_18000E062
0x18000e05a  mov     rcx, rdi
0x18000e05d  mov     rdx, r14
0x18000e060  jmp     short loc_18000E06D
0x18000e062  mov     rax, [rbp+arg_20]
0x18000e066  mov     rcx, [r13+0]; unsigned __int16 *
0x18000e06a  mov     rdx, [rax]; unsigned __int64
0x18000e06d  mov     r8, r12; unsigned __int16 *
0x18000e070  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e075  mov     ebx, eax
0x18000e077  test    eax, eax
0x18000e079  js      short loc_18000E0C2
0x18000e07b  test    rdi, rdi
0x18000e07e  jz      short loc_18000E0CE
0x18000e080  mov     rax, [r13+0]
0x18000e084  mov     [rbp+lpMem], rax
0x18000e088  test    rax, rax
0x18000e08b  jz      short loc_18000E0A2
0x18000e08d  call    cs:__imp_GetProcessHeap
0x18000e093  mov     r8, [rbp+lpMem]; lpMem
0x18000e097  xor     edx, edx; dwFlags
0x18000e099  mov     rcx, rax; hHeap
0x18000e09c  call    cs:__imp_HeapFree
0x18000e0a2  mov     rax, [rbp+arg_20]
0x18000e0a6  mov     [r13+0], rdi
0x18000e0aa  mov     [rax], r14
0x18000e0ad  jmp     short loc_18000E0DA
0x18000e0af  mov     [rbp+pcchEscaped], 0FFFFFFFFFFFFFFFFh
0x18000e0b7  mov     ebx, 80070216h
0x18000e0bc  jmp     short loc_18000E0DE
0x18000e0be  mov     r13, [rbp+arg_18]
0x18000e0c2  cmp     ebx, 8007000Eh
0x18000e0c8  jz      loc_18000DE0C
0x18000e0ce  cmp     ebx, 80070057h
0x18000e0d4  jz      loc_18000DDA6
0x18000e0da  test    ebx, ebx
0x18000e0dc  jz      short loc_18000E137
0x18000e0de  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000e0e5  jz      short loc_18000E153
0x18000e0e7  mov     r9d, ebx
0x18000e0ea  lea     r8, aCbwcrequestAdd_1; "CBWCRequest::AddEscapedPostParameter"
0x18000e0f1  call    McTemplateU0sq_EventWriteTransfer
0x18000e0f6  jmp     short loc_18000E153
0x18000e0f8  test    rax, rax
0x18000e0fb  jnz     short loc_18000E126
0x18000e0fd  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000e104  jz      short loc_18000E153
0x18000e106  lea     rax, aBufferlength; "BufferLength"
0x18000e10d  mov     r9d, 80070057h
0x18000e113  mov     [rsp+60h+var_40], rax
0x18000e118  lea     r8, aCbwcrequestAdd_1; "CBWCRequest::AddEscapedPostParameter"
0x18000e11f  call    McTemplateU0sqs_EventWriteTransfer
0x18000e124  jmp     short loc_18000E153
0x18000e126  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000e12d  jz      short loc_18000E153
0x18000e12f  mov     r9d, 80070057h
0x18000e135  jmp     short loc_18000E0EA
  ... truncated ...
```
