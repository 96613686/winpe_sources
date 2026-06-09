# CResourceLoader::ParseLocalizedResource(ushort *,ushort * *,long *)

- ea: `0x1800122b8`
- end: `0x1800124a0`
- name: `?ParseLocalizedResource@CResourceLoader@@AEAAJPEAGPEAPEAGPEAJ@Z`
- size: `488`
- prototype: `__int64 __fastcall(wchar_t *this, unsigned __int16 *, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011d2c`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180002ac4`
- `0x180002dc0`
- `0x1800122b8`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180012379`
- `msvcrt!wcsrchr` at `0x180012379`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001248b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001248b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001247d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001247d`

## string_xrefs

- `0x180012332`: `ResourcePath`

## pseudocode

```c
__int64 __fastcall CResourceLoader::ParseLocalizedResource(
        wchar_t *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        int *a4)
{
  unsigned __int16 *v4; // rbp
  unsigned int v8; // ebx
  const char *v9; // rax
  int v10; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v13; // [rsp+50h] [rbp+8h] BYREF
  __int64 v14; // [rsp+58h] [rbp+10h] BYREF

  v4 = 0;
  v13 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"CResourceLoader::ParseLocalizedResource",
        -2147024809,
        (__int64)"Value");
    return v8;
  }
  if ( !a3 || !a4 )
  {
    v8 = -2147024809;
    goto LABEL_6;
  }
  *a3 = 0;
  *a4 = 0;
  if ( *a2 != 64
    || (this = wcsrchr(a2, 0x2Cu)) == 0
    || (*this = 0, v14 = 0, (int)SDiagPrviHexToLongLong(this + 2, &v14) < 0) )
  {
    v8 = -2147446780;
    goto LABEL_20;
  }
  v10 = SDiagPrviCopyPWSTR(a2 + 1, &v13);
  v4 = v13;
  v8 = v10;
  if ( v10 >= 0 )
  {
    this = (wchar_t *)(unsigned int)v14;
    *a4 = v14;
    *a3 = v4;
    goto LABEL_19;
  }
  if ( v10 == -2147024882 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0s_EventWriteTransfer(
        this,
        SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY,
        "CResourceLoader::ParseLocalizedResource");
    goto LABEL_33;
  }
  if ( v10 == -2147024809 )
  {
LABEL_6:
    if ( a3 )
    {
      if ( a4 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
          McTemplateU0sq_EventWriteTransfer(this, a2, "CResourceLoader::ParseLocalizedResource", 2147942487LL);
        goto LABEL_33;
      }
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      {
LABEL_33:
        if ( v4 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v4);
        }
        return v8;
      }
      v9 = "ResourceId";
    }
    else
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_33;
      v9 = "ResourcePath";
    }
    McTemplateU0sqs_EventWriteTransfer(
      (_DWORD)this,
      (_DWORD)a2,
      (unsigned int)"CResourceLoader::ParseLocalizedResource",
      -2147024809,
      (__int64)v9);
    goto LABEL_33;
  }
LABEL_19:
  if ( !v10 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
      McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CResourceLoader::ParseLocalizedResource");
    return v8;
  }
LABEL_20:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sq_EventWriteTransfer(this, a2, "CResourceLoader::ParseLocalizedResource", v8);
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_33;
  return v8;
}

```

## disassembly

```asm
0x1800122b8  mov     r11, rsp
0x1800122bb  mov     [r11+18h], rbx
0x1800122bf  mov     [r11+8], rcx
0x1800122c3  push    rbp
0x1800122c4  push    rsi
0x1800122c5  push    rdi
0x1800122c6  sub     rsp, 30h
0x1800122ca  xor     ebp, ebp
0x1800122cc  mov     rdi, r9
0x1800122cf  mov     [r11+8], rbp
0x1800122d3  mov     rsi, r8
0x1800122d6  mov     rbx, rdx
0x1800122d9  test    rdx, rdx
0x1800122dc  jnz     short loc_180012312
0x1800122de  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800122e5  mov     ebx, 80070057h
0x1800122ea  jz      loc_180012491
0x1800122f0  lea     rax, aValue; "Value"
0x1800122f7  mov     r9d, 80070057h
0x1800122fd  lea     r8, aCresourceloade_2; "CResourceLoader::ParseLocalizedResource"
0x180012304  mov     [r11-28h], rax
0x180012308  call    McTemplateU0sqs_EventWriteTransfer
0x18001230d  jmp     loc_180012491
0x180012312  test    rsi, rsi
0x180012315  jnz     short loc_180012355
0x180012317  mov     ebx, 80070057h
0x18001231c  test    rsi, rsi
0x18001231f  jnz     loc_180012425
0x180012325  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001232c  jz      loc_180012478
0x180012332  lea     rax, aResourcepath; "ResourcePath"
0x180012339  mov     r9d, 80070057h
0x18001233f  mov     [rsp+48h+var_28], rax
0x180012344  lea     r8, aCresourceloade_2; "CResourceLoader::ParseLocalizedResource"
0x18001234b  call    McTemplateU0sqs_EventWriteTransfer
0x180012350  jmp     loc_180012478
0x180012355  test    rdi, rdi
0x180012358  jz      short loc_180012317
0x18001235a  mov     eax, 40h ; '@'
0x18001235f  mov     [r8], rbp
0x180012362  mov     [r9], ebp
0x180012365  cmp     ax, [rdx]
0x180012368  jz      short loc_180012371
0x18001236a  mov     ebx, 80009004h
0x18001236f  jmp     short loc_1800123E1
0x180012371  mov     edx, 2Ch ; ','; Ch
0x180012376  mov     rcx, rbx; Str
0x180012379  call    cs:__imp_wcsrchr
0x18001237f  mov     rcx, rax
0x180012382  test    rax, rax
0x180012385  jz      short loc_18001236A
0x180012387  xor     eax, eax
0x180012389  mov     [rcx], ax
0x18001238c  mov     [rsp+48h+arg_8], rax
0x180012391  add     rcx, 4; String1
0x180012395  lea     rdx, [rsp+48h+arg_8]; __int64 *
0x18001239a  call    ?SDiagPrviHexToLongLong@@YAJPEBGPEA_J@Z; SDiagPrviHexToLongLong(ushort const *,__int64 *)
0x18001239f  test    eax, eax
0x1800123a1  js      short loc_18001236A
0x1800123a3  lea     rcx, [rbx+2]; unsigned __int16 *
0x1800123a7  lea     rdx, [rsp+48h+arg_0]; unsigned __int16 **
0x1800123ac  call    ?SDiagPrviCopyPWSTR@@YAJPEBGPEAPEAG@Z; SDiagPrviCopyPWSTR(ushort const *,ushort * *)
0x1800123b1  mov     rbp, [rsp+48h+arg_0]
0x1800123b6  mov     ebx, eax
0x1800123b8  test    eax, eax
0x1800123ba  js      short loc_1800123C7
0x1800123bc  mov     ecx, dword ptr [rsp+48h+arg_8]
0x1800123c0  mov     [rdi], ecx
0x1800123c2  mov     [rsi], rbp
0x1800123c5  jmp     short loc_1800123DD
0x1800123c7  cmp     eax, 8007000Eh
0x1800123cc  jz      loc_18001245C
0x1800123d2  cmp     eax, 80070057h
0x1800123d7  jz      loc_18001231C
0x1800123dd  test    eax, eax
0x1800123df  jz      short loc_180012403
0x1800123e1  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800123e8  jz      short loc_1800123F9
0x1800123ea  mov     r9d, ebx
0x1800123ed  lea     r8, aCresourceloade_2; "CResourceLoader::ParseLocalizedResource"
0x1800123f4  call    McTemplateU0sq_EventWriteTransfer
0x1800123f9  test    ebx, ebx
0x1800123fb  jns     loc_180012491
0x180012401  jmp     short loc_180012478
0x180012403  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18001240a  jz      loc_180012491
0x180012410  lea     r8, aCresourceloade_2; "CResourceLoader::ParseLocalizedResource"
0x180012417  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18001241e  call    McTemplateU0s_EventWriteTransfer
0x180012423  jmp     short loc_180012491
0x180012425  test    rdi, rdi
0x180012428  jnz     short loc_18001243F
0x18001242a  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180012431  jz      short loc_180012478
0x180012433  lea     rax, aResourceid; "ResourceId"
0x18001243a  jmp     loc_180012339
0x18001243f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180012446  jz      short loc_180012478
0x180012448  mov     r9d, 80070057h
0x18001244e  lea     r8, aCresourceloade_2; "CResourceLoader::ParseLocalizedResource"
0x180012455  call    McTemplateU0sq_EventWriteTransfer
0x18001245a  jmp     short loc_180012478
0x18001245c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180012463  jz      short loc_180012478
0x180012465  lea     r8, aCresourceloade_2; "CResourceLoader::ParseLocalizedResource"
0x18001246c  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180012473  call    McTemplateU0s_EventWriteTransfer
0x180012478  test    rbp, rbp
0x18001247b  jz      short loc_180012491
0x18001247d  call    cs:__imp_GetProcessHeap
0x180012483  mov     r8, rbp; lpMem
0x180012486  xor     edx, edx; dwFlags
0x180012488  mov     rcx, rax; hHeap
0x18001248b  call    cs:__imp_HeapFree
0x180012491  mov     eax, ebx
0x180012493  mov     rbx, [rsp+48h+arg_10]
0x180012498  add     rsp, 30h
0x18001249c  pop     rdi
0x18001249d  pop     rsi
0x18001249e  pop     rbp
0x18001249f  retn
```
