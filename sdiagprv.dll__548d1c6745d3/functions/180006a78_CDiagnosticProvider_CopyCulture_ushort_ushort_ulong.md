# CDiagnosticProvider::CopyCulture(ushort *,ushort * *,ulong *)

- ea: `0x180006a78`
- end: `0x180006cc7`
- name: `?CopyCulture@CDiagnosticProvider@@AEAAJPEAGPEAPEAGPEAK@Z`
- size: `591`
- prototype: `__int64 __fastcall(CDiagnosticProvider *this, unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006fa0`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x1800033a4`
- `0x180006a78`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x180006b50`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x180006b50`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180006b0a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180006c2f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180006b0a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180006c2f`
- `OLEAUT32!__imp_SysFreeString` at `0x180006ca8`
- `OLEAUT32!__imp_SysFreeString` at `0x180006ca8`
- `OLEAUT32!__imp_SysStringLen` at `0x180006afc`
- `OLEAUT32!__imp_SysStringLen` at `0x180006afc`

## string_xrefs

- `0x180006ac8`: `CDiagnosticProvider::CopyCulture`
- `0x180006be8`: `CDiagnosticProvider::CopyCulture`
- `0x180006c05`: `CDiagnosticProvider::CopyCulture`
- `0x180006c4b`: `CDiagnosticProvider::CopyCulture`
- `0x180006c71`: `CDiagnosticProvider::CopyCulture`
- `0x180006c99`: `CDiagnosticProvider::CopyCulture`

## pseudocode

```c
__int64 __fastcall CDiagnosticProvider::CopyCulture(
        CDiagnosticProvider *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  unsigned int v7; // ebx
  OLECHAR *v8; // rdi
  UINT v9; // eax
  unsigned __int64 v10; // r12
  BSTR v11; // rax
  unsigned __int64 v12; // rbx
  const unsigned __int16 *v13; // rbp
  unsigned int v14; // r14d
  int v15; // eax
  unsigned __int64 v16; // rax
  const char *v17; // rax
  unsigned __int16 *v18; // rax
  bool v19; // zf
  unsigned __int64 v21; // [rsp+60h] [rbp+8h] BYREF

  v21 = 0;
  if ( a2 )
  {
    v8 = 0;
    if ( a3 && a4 )
    {
      *a3 = 0;
      *a4 = 0;
      v9 = SysStringLen(a2);
      v10 = v9;
      v11 = SysAllocStringLen(a2, v9);
      v8 = v11;
      if ( v11 )
      {
        v12 = 0;
        v13 = v11;
        v14 = 0;
        while ( v12 < v10 && *v13 )
        {
          v15 = StringCchLengthW(v13, 0x55u, &v21);
          if ( v15 < 0 )
          {
            if ( v15 == -2147024882 )
            {
              v7 = -2147024882;
              goto LABEL_33;
            }
            v7 = v15;
            if ( v15 == -2147024809 )
              goto LABEL_19;
            goto LABEL_41;
          }
          if ( !IsValidLocaleName(v13) )
            goto LABEL_16;
          this = (CDiagnosticProvider *)v21;
          v16 = v21 + v12;
          if ( v21 + v12 < v12 )
            goto LABEL_40;
          v12 = v16 + 1;
          if ( v16 + 1 < v16 )
            goto LABEL_40;
          v13 += v21 + 1;
          ++v14;
        }
        if ( v14 )
        {
          if ( v12 <= 0xFFFFFFFF )
          {
            v18 = SysAllocStringLen(v8, v12);
            *a3 = v18;
            if ( !v18 )
              goto LABEL_32;
            v19 = (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0;
            *a4 = v14;
            if ( !v19 )
              McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CDiagnosticProvider::CopyCulture");
            v7 = 0;
            goto LABEL_43;
          }
LABEL_40:
          v7 = -2147024362;
        }
        else
        {
LABEL_16:
          v7 = -2147446783;
        }
LABEL_41:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
          McTemplateU0sq_EventWriteTransfer(this, a2, "CDiagnosticProvider::CopyCulture", v7);
        goto LABEL_43;
      }
LABEL_32:
      v7 = -2147024882;
LABEL_33:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY, "CDiagnosticProvider::CopyCulture");
LABEL_35:
      if ( !v8 )
        return v7;
LABEL_43:
      SysFreeString(v8);
      return v7;
    }
    v7 = -2147024809;
LABEL_19:
    if ( a3 )
    {
      if ( a4 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
          McTemplateU0sq_EventWriteTransfer(this, a2, "CDiagnosticProvider::CopyCulture", 2147942487LL);
        goto LABEL_35;
      }
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_35;
      v17 = "NumLanguages";
    }
    else
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_35;
      v17 = "Languages";
    }
    McTemplateU0sqs_EventWriteTransfer(
      (_DWORD)this,
      (_DWORD)a2,
      (unsigned int)"CDiagnosticProvider::CopyCulture",
      -2147024809,
      (__int64)v17);
    goto LABEL_35;
  }
  v7 = -2147024809;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sqs_EventWriteTransfer(
      (_DWORD)this,
      0,
      (unsigned int)"CDiagnosticProvider::CopyCulture",
      -2147024809,
      (__int64)"Culture");
  return v7;
}

```

## disassembly

```asm
0x180006a78  mov     r11, rsp
0x180006a7b  mov     [r11+10h], rbx
0x180006a7f  mov     [r11+18h], rbp
0x180006a83  mov     [r11+8], rcx
0x180006a87  push    rsi
0x180006a88  push    rdi
0x180006a89  push    r12
0x180006a8b  push    r14
0x180006a8d  push    r15
0x180006a8f  sub     rsp, 30h
0x180006a93  mov     qword ptr [r11+8], 0
0x180006a9b  mov     rsi, r9
0x180006a9e  mov     r15, r8
0x180006aa1  mov     rbx, rdx
0x180006aa4  test    rdx, rdx
0x180006aa7  jnz     short loc_180006ADD
0x180006aa9  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180006ab0  mov     ebx, 80070057h
0x180006ab5  jz      loc_180006CAE
0x180006abb  lea     rax, aCulture; "Culture"
0x180006ac2  mov     r9d, 80070057h
0x180006ac8  lea     r8, aCdiagnosticpro_6; "CDiagnosticProvider::CopyCulture"
0x180006acf  mov     [r11-38h], rax
0x180006ad3  call    McTemplateU0sqs_EventWriteTransfer
0x180006ad8  jmp     loc_180006CAE
0x180006add  xor     edi, edi
0x180006adf  test    r15, r15
0x180006ae2  jnz     short loc_180006AEE
0x180006ae4  mov     ebx, 80070057h
0x180006ae9  jmp     loc_180006BA9
0x180006aee  test    rsi, rsi
0x180006af1  jz      short loc_180006AE4
0x180006af3  mov     rcx, rbx; pbstr
0x180006af6  mov     [r8], rdi
0x180006af9  mov     [r9], edi
0x180006afc  call    cs:__imp_SysStringLen
0x180006b02  mov     edx, eax; ui
0x180006b04  mov     r12d, eax
0x180006b07  mov     rcx, rbx; strIn
0x180006b0a  call    cs:__imp_SysAllocStringLen
0x180006b10  mov     rdi, rax
0x180006b13  test    rax, rax
0x180006b16  jz      loc_180006C3D
0x180006b1c  xor     ebx, ebx
0x180006b1e  mov     rbp, rax
0x180006b21  xor     r14d, r14d
0x180006b24  cmp     rbx, r12
0x180006b27  jnb     loc_180006C17
0x180006b2d  xor     eax, eax
0x180006b2f  cmp     ax, [rbp+0]
0x180006b33  jz      loc_180006C17
0x180006b39  lea     r8, [rsp+58h+arg_0]; unsigned __int64 *
0x180006b3e  mov     rcx, rbp; unsigned __int16 *
0x180006b41  lea     edx, [rax+55h]; unsigned __int64
0x180006b44  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180006b49  test    eax, eax
0x180006b4b  js      short loc_180006B91
0x180006b4d  mov     rcx, rbp; lpLocaleName
0x180006b50  call    cs:__imp_IsValidLocaleName
0x180006b56  test    eax, eax
0x180006b58  jz      short loc_180006B87
0x180006b5a  mov     rcx, [rsp+58h+arg_0]
0x180006b5f  lea     rax, [rcx+rbx]
0x180006b63  cmp     rax, rbx
0x180006b66  jb      loc_180006C88
0x180006b6c  lea     rbx, [rax+1]
0x180006b70  cmp     rbx, rax
0x180006b73  jb      loc_180006C88
0x180006b79  lea     rbp, [rbp+rcx*2+0]
0x180006b7e  add     rbp, 2
0x180006b82  inc     r14d
0x180006b85  jmp     short loc_180006B24
0x180006b87  mov     ebx, 80009001h
0x180006b8c  jmp     loc_180006C8D
0x180006b91  mov     ebx, 8007000Eh
0x180006b96  cmp     eax, ebx
0x180006b98  jz      short loc_180006C13
0x180006b9a  mov     ebx, 80070057h
0x180006b9f  cmp     eax, ebx
0x180006ba1  mov     ebx, eax
0x180006ba3  jnz     loc_180006C8D
0x180006ba9  test    r15, r15
0x180006bac  jnz     short loc_180006BC4
0x180006bae  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180006bb5  jz      loc_180006C5E
0x180006bbb  lea     rax, aLanguages; "Languages"
0x180006bc2  jmp     short loc_180006BDD
0x180006bc4  test    rsi, rsi
0x180006bc7  jnz     short loc_180006BF6
0x180006bc9  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180006bd0  jz      loc_180006C5E
0x180006bd6  lea     rax, aNumlanguages; "NumLanguages"
0x180006bdd  mov     r9d, 80070057h
0x180006be3  mov     [rsp+58h+var_38], rax
0x180006be8  lea     r8, aCdiagnosticpro_6; "CDiagnosticProvider::CopyCulture"
0x180006bef  call    McTemplateU0sqs_EventWriteTransfer
0x180006bf4  jmp     short loc_180006C5E
0x180006bf6  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180006bfd  jz      short loc_180006C5E
0x180006bff  mov     r9d, 80070057h
0x180006c05  lea     r8, aCdiagnosticpro_6; "CDiagnosticProvider::CopyCulture"
0x180006c0c  call    McTemplateU0sq_EventWriteTransfer
0x180006c11  jmp     short loc_180006C5E
0x180006c13  mov     ebx, eax
0x180006c15  jmp     short loc_180006C42
0x180006c17  test    r14d, r14d
0x180006c1a  jz      loc_180006B87
0x180006c20  mov     eax, 0FFFFFFFFh
0x180006c25  cmp     rbx, rax
0x180006c28  ja      short loc_180006C88
0x180006c2a  mov     edx, ebx; ui
0x180006c2c  mov     rcx, rdi; strIn
0x180006c2f  call    cs:__imp_SysAllocStringLen
0x180006c35  mov     [r15], rax
0x180006c38  test    rax, rax
0x180006c3b  jnz     short loc_180006C65
0x180006c3d  mov     ebx, 8007000Eh
0x180006c42  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180006c49  jz      short loc_180006C5E
0x180006c4b  lea     r8, aCdiagnosticpro_6; "CDiagnosticProvider::CopyCulture"
0x180006c52  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180006c59  call    McTemplateU0s_EventWriteTransfer
0x180006c5e  test    rdi, rdi
0x180006c61  jz      short loc_180006CAE
0x180006c63  jmp     short loc_180006CA5
0x180006c65  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180006c6c  mov     [rsi], r14d
0x180006c6f  jz      short loc_180006C84
0x180006c71  lea     r8, aCdiagnosticpro_6; "CDiagnosticProvider::CopyCulture"
0x180006c78  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180006c7f  call    McTemplateU0s_EventWriteTransfer
0x180006c84  xor     ebx, ebx
0x180006c86  jmp     short loc_180006CA5
0x180006c88  mov     ebx, 80070216h
0x180006c8d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180006c94  jz      short loc_180006CA5
0x180006c96  mov     r9d, ebx
0x180006c99  lea     r8, aCdiagnosticpro_6; "CDiagnosticProvider::CopyCulture"
0x180006ca0  call    McTemplateU0sq_EventWriteTransfer
0x180006ca5  mov     rcx, rdi; bstrString
0x180006ca8  call    cs:__imp_SysFreeString
0x180006cae  mov     rbp, [rsp+58h+arg_10]
0x180006cb3  mov     eax, ebx
0x180006cb5  mov     rbx, [rsp+58h+arg_8]
0x180006cba  add     rsp, 30h
0x180006cbe  pop     r15
0x180006cc0  pop     r14
0x180006cc2  pop     r12
0x180006cc4  pop     rdi
0x180006cc5  pop     rsi
0x180006cc6  retn
```
