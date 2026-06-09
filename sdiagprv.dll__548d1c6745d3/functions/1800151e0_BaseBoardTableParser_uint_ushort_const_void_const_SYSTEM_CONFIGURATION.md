# BaseBoardTableParser(uint,ushort const *,void * const,_SYSTEM_CONFIGURATION *)

- ea: `0x1800151e0`
- end: `0x18001531d`
- name: `?BaseBoardTableParser@@YAJIPEBGQEAXPEAU_SYSTEM_CONFIGURATION@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned __int8 *, struct _SYSTEM_CONFIGURATION *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x1800151e0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001529c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800152b4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800152cc`
- `OLEAUT32!__imp_SysAllocString` at `0x18001529c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800152b4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800152cc`

## string_xrefs

- `0x180015249`: `SystemConfiguration`

## pseudocode

```c
__int64 __fastcall BaseBoardTableParser(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        struct _SYSTEM_CONFIGURATION *a4)
{
  unsigned int v5; // ebx
  const char *v6; // rax
  BSTR v7; // rax
  __int64 *v8; // rdx

  if ( !a2 )
  {
    v5 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      v6 = "String";
LABEL_12:
      McTemplateU0sqs_EventWriteTransfer(a1, (_DWORD)a2, (unsigned int)"BaseBoardTableParser", -2147024809, (__int64)v6);
      return v5;
    }
    return v5;
  }
  if ( a3 && a4 )
  {
    if ( a3[4] == (_DWORD)a1 )
    {
      v7 = SysAllocString(a2);
      *((_QWORD *)a4 + 10) = v7;
    }
    else if ( a3[5] == (_DWORD)a1 )
    {
      v7 = SysAllocString(a2);
      *((_QWORD *)a4 + 11) = v7;
    }
    else
    {
      if ( a3[6] != (_DWORD)a1 )
        goto LABEL_24;
      v7 = SysAllocString(a2);
      *((_QWORD *)a4 + 12) = v7;
    }
    if ( !v7 )
    {
      v5 = -2147024882;
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        return v5;
      v8 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
LABEL_26:
      McTemplateU0s_EventWriteTransfer(a1, v8, "BaseBoardTableParser");
      return v5;
    }
LABEL_24:
    v5 = 0;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
      return v5;
    v8 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
    goto LABEL_26;
  }
  v5 = -2147024809;
  if ( a3 )
  {
    if ( a4 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        McTemplateU0sq_EventWriteTransfer(a1, a2, "BaseBoardTableParser", 2147942487LL);
    }
    else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      v6 = "SystemConfiguration";
      goto LABEL_12;
    }
  }
  else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v6 = "Table";
    goto LABEL_12;
  }
  return v5;
}

```

## disassembly

```asm
0x1800151e0  mov     [rsp+arg_0], rbx
0x1800151e5  push    rdi
0x1800151e6  sub     rsp, 30h
0x1800151ea  mov     rdi, r9
0x1800151ed  test    rdx, rdx
0x1800151f0  jnz     short loc_18001520D
0x1800151f2  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800151f9  mov     ebx, 80070057h
0x1800151fe  jz      loc_180015310
0x180015204  lea     rax, aString; "String"
0x18001520b  jmp     short loc_180015250
0x18001520d  test    r8, r8
0x180015210  jz      short loc_180015217
0x180015212  test    rdi, rdi
0x180015215  jnz     short loc_180015290
0x180015217  mov     ebx, 80070057h
0x18001521c  test    r8, r8
0x18001521f  jnz     short loc_180015237
0x180015221  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180015228  jz      loc_180015310
0x18001522e  lea     rax, aTable; "Table"
0x180015235  jmp     short loc_180015250
0x180015237  test    rdi, rdi
0x18001523a  jnz     short loc_18001526C
0x18001523c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180015243  jz      loc_180015310
0x180015249  lea     rax, aSystemconfigur; "SystemConfiguration"
0x180015250  mov     r9d, 80070057h
0x180015256  mov     [rsp+38h+var_18], rax
0x18001525b  lea     r8, aBaseboardtable; "BaseBoardTableParser"
0x180015262  call    McTemplateU0sqs_EventWriteTransfer
0x180015267  jmp     loc_180015310
0x18001526c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180015273  jz      loc_180015310
0x180015279  mov     r9d, 80070057h
0x18001527f  lea     r8, aBaseboardtable; "BaseBoardTableParser"
0x180015286  call    McTemplateU0sq_EventWriteTransfer
0x18001528b  jmp     loc_180015310
0x180015290  movzx   eax, byte ptr [r8+4]
0x180015295  cmp     eax, ecx
0x180015297  jnz     short loc_1800152A8
0x180015299  mov     rcx, rdx; psz
0x18001529c  call    cs:__imp_SysAllocString
0x1800152a2  mov     [rdi+50h], rax
0x1800152a6  jmp     short loc_1800152D6
0x1800152a8  movzx   eax, byte ptr [r8+5]
0x1800152ad  cmp     eax, ecx
0x1800152af  jnz     short loc_1800152C0
0x1800152b1  mov     rcx, rdx; psz
0x1800152b4  call    cs:__imp_SysAllocString
0x1800152ba  mov     [rdi+58h], rax
0x1800152be  jmp     short loc_1800152D6
0x1800152c0  movzx   eax, byte ptr [r8+6]
0x1800152c5  cmp     eax, ecx
0x1800152c7  jnz     short loc_1800152F2
0x1800152c9  mov     rcx, rdx; psz
0x1800152cc  call    cs:__imp_SysAllocString
0x1800152d2  mov     [rdi+60h], rax
0x1800152d6  test    rax, rax
0x1800152d9  jnz     short loc_1800152F2
0x1800152db  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800152e2  mov     ebx, 8007000Eh
0x1800152e7  jz      short loc_180015310
0x1800152e9  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x1800152f0  jmp     short loc_180015304
0x1800152f2  xor     ebx, ebx
0x1800152f4  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800152fb  jz      short loc_180015310
0x1800152fd  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180015304  lea     r8, aBaseboardtable; "BaseBoardTableParser"
0x18001530b  call    McTemplateU0s_EventWriteTransfer
0x180015310  mov     eax, ebx
0x180015312  mov     rbx, [rsp+38h+arg_0]
0x180015317  add     rsp, 30h
0x18001531b  pop     rdi
0x18001531c  retn
```
