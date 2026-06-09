# ScanTable(char const *,unsigned __int64,void * const,_SYSTEM_CONFIGURATION *,long (*)(uint,ushort const *,void * const,_SYSTEM_CONFIGURATION *),unsigned __int64 *)

- ea: `0x1800161e8`
- end: `0x180016506`
- name: `?ScanTable@@YAJPEBD_KQEAXPEAU_SYSTEM_CONFIGURATION@@P6AJIPEBG23@ZPEA_K@Z`
- size: `798`
- prototype: `__int64 __fastcall(unsigned __int64 lpMultiByteStr, __int64, void *const, struct _SYSTEM_CONFIGURATION *, int (*)(unsigned int, const unsigned __int16 *, void *const, struct _SYSTEM_CONFIGURATION *), unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015834`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180015324`
- `0x1800161e8`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800162f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800164ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800162f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800164ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800162e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800164df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800162e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800164df`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x1800163a2`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x1800163a2`

## string_xrefs

- `0x18001646c`: `SystemConfiguration`

## pseudocode

```c
__int64 __fastcall ScanTable(
        unsigned __int64 lpMultiByteStr,
        __int64 a2,
        void *const a3,
        struct _SYSTEM_CONFIGURATION *a4,
        int (*a5)(unsigned int, const unsigned __int16 *, void *const, struct _SYSTEM_CONFIGURATION *),
        unsigned __int64 *a6)
{
  struct _SYSTEM_CONFIGURATION *v6; // rax
  unsigned __int64 v7; // r9
  const CHAR *v8; // rbp
  void *v9; // rsi
  unsigned int v10; // ebx
  LPCCH v11; // r12
  int v12; // eax
  unsigned __int64 v13; // r15
  __int16 v14; // r13
  HANDLE ProcessHeap; // rax
  int v16; // eax
  bool v17; // zf
  __int16 v18; // cx
  __int64 v19; // r9
  const char *v20; // rax
  HANDLE v21; // rax
  unsigned int v23; // [rsp+30h] [rbp-58h]
  unsigned int v24; // [rsp+34h] [rbp-54h]
  LPVOID lpMem; // [rsp+38h] [rbp-50h] BYREF
  int v26; // [rsp+90h] [rbp+8h]
  __int64 v27; // [rsp+98h] [rbp+10h]
  void *v28; // [rsp+A0h] [rbp+18h]

  v28 = a3;
  v27 = a2;
  v6 = a4;
  lpMem = 0;
  v7 = a2;
  v8 = (const CHAR *)lpMultiByteStr;
  v9 = 0;
  if ( !lpMultiByteStr )
  {
    v10 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(0, a2, (unsigned int)"ScanTable", -2147024809, (__int64)"Buffer");
    return v10;
  }
  if ( !a3 || !v6 || !a6 )
  {
    v10 = -2147024809;
    goto LABEL_34;
  }
  *a6 = 0;
  v11 = (LPCCH)lpMultiByteStr;
  a2 = 1;
  lpMultiByteStr = 1;
  v23 = 1;
  LOWORD(v12) = 0;
  v24 = 1;
  v10 = 0;
  v26 = 0;
  v13 = 0;
  v14 = 0;
  while ( v11 && (unsigned __int16)v12 < 2u && v13 < v7 )
  {
    if ( *v11 )
    {
      LOWORD(v26) = 0;
      v24 = lpMultiByteStr + 1;
      v12 = IsCharAlphaNumericW(*v11);
      a2 = v23;
      v17 = v12 == 0;
      LOWORD(v12) = 0;
      v18 = v14 + 1;
      if ( v17 )
        v18 = v14;
      ++v11;
      v14 = v18;
    }
    else
    {
      if ( a5 && v14 )
      {
        if ( v9 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v9);
          LODWORD(lpMultiByteStr) = v24;
          lpMem = 0;
        }
        v16 = ConvertToString(v8, lpMultiByteStr, (unsigned __int16 **)&lpMem);
        v9 = lpMem;
        v10 = v16;
        if ( v16 < 0 )
          goto LABEL_27;
        v10 = ((__int64 (__fastcall *)(_QWORD, LPVOID, void *, struct _SYSTEM_CONFIGURATION *))a5)(v23, lpMem, v28, a4);
        if ( (v10 & 0x80000000) != 0 )
          goto LABEL_27;
        LODWORD(a2) = v23;
        v24 = 1;
      }
      HIWORD(v12) = HIWORD(v26);
      v8 = v11 + 1;
      LOWORD(v12) = v26 + 1;
      v14 = 0;
      a2 = (unsigned int)(a2 + 1);
      v26 = v12;
      v23 = a2;
      ++v11;
    }
    lpMultiByteStr = v24;
    ++v13;
    v7 = v27;
  }
  *a6 = v13;
LABEL_27:
  if ( v10 == -2147024809 )
  {
    v6 = a4;
    a3 = v28;
LABEL_34:
    if ( a3 )
    {
      if ( v6 )
      {
        if ( a5 )
        {
          if ( a6 )
          {
            if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
              goto LABEL_50;
            v19 = 2147942487LL;
            goto LABEL_49;
          }
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
            goto LABEL_50;
          v20 = "BytesScanned";
        }
        else
        {
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
            goto LABEL_50;
          v20 = "TableParser";
        }
      }
      else
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_50;
        v20 = "SystemConfiguration";
      }
    }
    else
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_50;
      v20 = "Table";
    }
    McTemplateU0sqs_EventWriteTransfer(lpMultiByteStr, a2, (unsigned int)"ScanTable", -2147024809, (__int64)v20);
    goto LABEL_50;
  }
  if ( !v10 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
      McTemplateU0s_EventWriteTransfer(lpMultiByteStr, SDIAGPRV_EVENT_DEBUG_SUCCESS, "ScanTable");
    goto LABEL_50;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v19 = v10;
LABEL_49:
    McTemplateU0sq_EventWriteTransfer(lpMultiByteStr, a2, "ScanTable", v19);
  }
LABEL_50:
  if ( v9 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v9);
  }
  return v10;
}

```

## disassembly

```asm
0x1800161e8  mov     r11, rsp
0x1800161eb  mov     [r11+20h], r9
0x1800161ef  mov     [r11+18h], r8
0x1800161f3  mov     [r11+10h], rdx
0x1800161f7  push    rbx
0x1800161f8  push    rbp
0x1800161f9  push    rsi
0x1800161fa  push    rdi
0x1800161fb  push    r12
0x1800161fd  push    r13
0x1800161ff  push    r14
0x180016201  push    r15
0x180016203  sub     rsp, 48h
0x180016207  xor     r10d, r10d
0x18001620a  mov     rax, r9
0x18001620d  mov     [r11-50h], r10
0x180016211  mov     r9, rdx
0x180016214  mov     rbp, rcx
0x180016217  mov     esi, r10d
0x18001621a  lea     edi, [r10+2]
0x18001621e  test    rcx, rcx
0x180016221  jnz     short loc_180016257
0x180016223  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, dil
0x18001622a  mov     ebx, 80070057h
0x18001622f  jz      loc_1800164F3
0x180016235  lea     rax, aBuffer; "Buffer"
0x18001623c  mov     r9d, 80070057h
0x180016242  lea     r8, aScantable; "ScanTable"
0x180016249  mov     [r11-68h], rax
0x18001624d  call    McTemplateU0sqs_EventWriteTransfer
0x180016252  jmp     loc_1800164F3
0x180016257  mov     r14, [rsp+88h+arg_28]
0x18001625f  test    r8, r8
0x180016262  jnz     short loc_18001626E
0x180016264  mov     ebx, 80070057h
0x180016269  jmp     loc_180016443
0x18001626e  test    rax, rax
0x180016271  jz      short loc_180016264
0x180016273  test    r14, r14
0x180016276  jz      short loc_180016264
0x180016278  mov     r8d, 1
0x18001627e  mov     [r14], r10
0x180016281  mov     r12, rcx
0x180016284  mov     edx, r8d
0x180016287  mov     ecx, r8d
0x18001628a  mov     [rsp+88h+var_58], edx
0x18001628e  mov     eax, r10d
0x180016291  mov     [rsp+88h+var_54], ecx
0x180016295  mov     ebx, r10d
0x180016298  mov     [rsp+88h+arg_0], eax
0x18001629f  mov     r15, r10
0x1800162a2  mov     r13d, r10d
0x1800162a5  test    r12, r12
0x1800162a8  jz      loc_1800163EA
0x1800162ae  cmp     di, ax
0x1800162b1  jbe     loc_1800163EA
0x1800162b7  cmp     r15, r9
0x1800162ba  jnb     loc_1800163EA
0x1800162c0  cmp     [r12], r10b
0x1800162c4  jnz     loc_18001638D
0x1800162ca  cmp     [rsp+88h+arg_20], r10
0x1800162d2  jz      loc_180016367
0x1800162d8  test    r13w, r13w
0x1800162dc  jz      loc_180016367
0x1800162e2  test    rsi, rsi
0x1800162e5  jz      short loc_180016308
0x1800162e7  call    cs:__imp_GetProcessHeap
0x1800162ed  mov     r8, rsi; lpMem
0x1800162f0  xor     edx, edx; dwFlags
0x1800162f2  mov     rcx, rax; hHeap
0x1800162f5  call    cs:__imp_HeapFree
0x1800162fb  mov     ecx, [rsp+88h+var_54]
0x1800162ff  mov     [rsp+88h+lpMem], 0
0x180016308  mov     edx, ecx; cbMultiByte
0x18001630a  lea     r8, [rsp+88h+lpMem]; unsigned __int16 **
0x18001630f  mov     rcx, rbp; lpMultiByteStr
0x180016312  call    ?ConvertToString@@YAJPEBDHPEAPEAG@Z; ConvertToString(char const *,int,ushort * *)
0x180016317  mov     rsi, [rsp+88h+lpMem]
0x18001631c  xor     r10d, r10d
0x18001631f  mov     ebx, eax
0x180016321  test    eax, eax
0x180016323  js      loc_1800163E2
0x180016329  mov     r9, [rsp+88h+arg_18]
0x180016331  mov     rdx, rsi
0x180016334  mov     r8, [rsp+88h+arg_10]
0x18001633c  mov     ecx, [rsp+88h+var_58]
0x180016340  mov     rax, [rsp+88h+arg_20]
0x180016348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001634d  xor     r10d, r10d
0x180016350  mov     ebx, eax
0x180016352  lea     r8d, [r10+1]
0x180016356  test    eax, eax
0x180016358  js      loc_1800163ED
0x18001635e  mov     edx, [rsp+88h+var_58]
0x180016362  mov     [rsp+88h+var_54], r8d
0x180016367  mov     eax, [rsp+88h+arg_0]
0x18001636e  lea     rbp, [r12+1]
0x180016373  add     ax, r8w
0x180016377  mov     r13d, r10d
0x18001637a  add     edx, r8d
0x18001637d  mov     [rsp+88h+arg_0], eax
0x180016384  mov     [rsp+88h+var_58], edx
0x180016388  mov     r12, rbp
0x18001638b  jmp     short loc_1800163CE
0x18001638d  add     ecx, r8d
0x180016390  mov     word ptr [rsp+88h+arg_0], r10w
0x180016399  mov     [rsp+88h+var_54], ecx
0x18001639d  movsx   ecx, byte ptr [r12]; ch
0x1800163a2  call    cs:__imp_IsCharAlphaNumericW
0x1800163a8  mov     edx, [rsp+88h+var_58]
0x1800163ac  xor     r10d, r10d
0x1800163af  test    eax, eax
0x1800163b1  mov     r8d, 1
0x1800163b7  mov     eax, [rsp+88h+arg_0]
0x1800163be  lea     ecx, [r8+r13]
0x1800163c2  cmovz   cx, r13w
0x1800163c7  inc     r12
0x1800163ca  movzx   r13d, cx
0x1800163ce  mov     ecx, [rsp+88h+var_54]
0x1800163d2  add     r15, r8
0x1800163d5  mov     r9, [rsp+88h+arg_8]
0x1800163dd  jmp     loc_1800162A5
0x1800163e2  mov     r8d, 1
0x1800163e8  jmp     short loc_1800163ED
0x1800163ea  mov     [r14], r15
0x1800163ed  cmp     ebx, 80070057h
0x1800163f3  jz      short loc_180016433
0x1800163f5  test    ebx, ebx
0x1800163f7  jz      short loc_18001640E
0x1800163f9  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, dil
0x180016400  jz      loc_1800164DA
0x180016406  mov     r9d, ebx
0x180016409  jmp     loc_1800164CE
0x18001640e  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, r8b
0x180016415  jz      loc_1800164DA
0x18001641b  lea     r8, aScantable; "ScanTable"
0x180016422  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180016429  call    McTemplateU0s_EventWriteTransfer
0x18001642e  jmp     loc_1800164DA
0x180016433  mov     rax, [rsp+88h+arg_18]
0x18001643b  mov     r8, [rsp+88h+arg_10]
0x180016443  test    r8, r8
0x180016446  jnz     short loc_18001645E
0x180016448  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, dil
0x18001644f  jz      loc_1800164DA
0x180016455  lea     rax, aTable; "Table"
0x18001645c  jmp     short loc_1800164A6
0x18001645e  test    rax, rax
0x180016461  jnz     short loc_180016475
0x180016463  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, dil
0x18001646a  jz      short loc_1800164DA
0x18001646c  lea     rax, aSystemconfigur; "SystemConfiguration"
0x180016473  jmp     short loc_1800164A6
0x180016475  cmp     [rsp+88h+arg_20], r10
0x18001647d  jnz     short loc_180016491
0x18001647f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, dil
0x180016486  jz      short loc_1800164DA
0x180016488  lea     rax, aTableparser; "TableParser"
0x18001648f  jmp     short loc_1800164A6
0x180016491  test    r14, r14
0x180016494  jnz     short loc_1800164BF
0x180016496  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, dil
0x18001649d  jz      short loc_1800164DA
0x18001649f  lea     rax, aBytesscanned; "BytesScanned"
0x1800164a6  mov     r9d, 80070057h
0x1800164ac  mov     [rsp+88h+var_68], rax
0x1800164b1  lea     r8, aScantable; "ScanTable"
0x1800164b8  call    McTemplateU0sqs_EventWriteTransfer
0x1800164bd  jmp     short loc_1800164DA
0x1800164bf  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, dil
0x1800164c6  jz      short loc_1800164DA
0x1800164c8  mov     r9d, 80070057h
0x1800164ce  lea     r8, aScantable; "ScanTable"
0x1800164d5  call    McTemplateU0sq_EventWriteTransfer
0x1800164da  test    rsi, rsi
0x1800164dd  jz      short loc_1800164F3
0x1800164df  call    cs:__imp_GetProcessHeap
0x1800164e5  mov     r8, rsi; lpMem
0x1800164e8  xor     edx, edx; dwFlags
0x1800164ea  mov     rcx, rax; hHeap
0x1800164ed  call    cs:__imp_HeapFree
0x1800164f3  mov     eax, ebx
0x1800164f5  add     rsp, 48h
0x1800164f9  pop     r15
0x1800164fb  pop     r14
0x1800164fd  pop     r13
0x1800164ff  pop     r12
0x180016501  pop     rdi
0x180016502  pop     rsi
0x180016503  pop     rbp
0x180016504  pop     rbx
0x180016505  retn
```
