# SystemTableParser(uint,ushort const *,void * const,_SYSTEM_CONFIGURATION *)

- ea: `0x180016540`
- end: `0x1800166ad`
- name: `?SystemTableParser@@YAJIPEBGQEAXPEAU_SYSTEM_CONFIGURATION@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned __int8 *, struct _SYSTEM_CONFIGURATION *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180016540`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800165fc`
- `OLEAUT32!__imp_SysAllocString` at `0x180016614`
- `OLEAUT32!__imp_SysAllocString` at `0x18001662c`
- `OLEAUT32!__imp_SysAllocString` at `0x180016644`
- `OLEAUT32!__imp_SysAllocString` at `0x18001665c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800165fc`
- `OLEAUT32!__imp_SysAllocString` at `0x180016614`
- `OLEAUT32!__imp_SysAllocString` at `0x18001662c`
- `OLEAUT32!__imp_SysAllocString` at `0x180016644`
- `OLEAUT32!__imp_SysAllocString` at `0x18001665c`

## string_xrefs

- `0x1800165a9`: `SystemConfiguration`

## pseudocode

```c
__int64 __fastcall SystemTableParser(
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
      McTemplateU0sqs_EventWriteTransfer(a1, (_DWORD)a2, (unsigned int)"SystemTableParser", -2147024809, (__int64)v6);
      return v5;
    }
    return v5;
  }
  if ( a3 && a4 )
  {
    if ( a3[4] == (_DWORD)a1 )
    {
      v7 = SysAllocString(a2);
      *((_QWORD *)a4 + 5) = v7;
    }
    else if ( a3[5] == (_DWORD)a1 )
    {
      v7 = SysAllocString(a2);
      *((_QWORD *)a4 + 6) = v7;
    }
    else if ( a3[6] == (_DWORD)a1 )
    {
      v7 = SysAllocString(a2);
      *((_QWORD *)a4 + 9) = v7;
    }
    else if ( a3[25] == (_DWORD)a1 )
    {
      v7 = SysAllocString(a2);
      *((_QWORD *)a4 + 8) = v7;
    }
    else
    {
      if ( a3[26] != (_DWORD)a1 )
        goto LABEL_28;
      v7 = SysAllocString(a2);
      *((_QWORD *)a4 + 7) = v7;
    }
    if ( !v7 )
    {
      v5 = -2147024882;
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        return v5;
      v8 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
LABEL_30:
      McTemplateU0s_EventWriteTransfer(a1, v8, "SystemTableParser");
      return v5;
    }
LABEL_28:
    v5 = 0;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
      return v5;
    v8 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
    goto LABEL_30;
  }
  v5 = -2147024809;
  if ( a3 )
  {
    if ( a4 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        McTemplateU0sq_EventWriteTransfer(a1, a2, "SystemTableParser", 2147942487LL);
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
0x180016540  mov     [rsp+arg_0], rbx
0x180016545  push    rdi
0x180016546  sub     rsp, 30h
0x18001654a  mov     rdi, r9
0x18001654d  test    rdx, rdx
0x180016550  jnz     short loc_18001656D
0x180016552  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016559  mov     ebx, 80070057h
0x18001655e  jz      loc_1800166A0
0x180016564  lea     rax, aString; "String"
0x18001656b  jmp     short loc_1800165B0
0x18001656d  test    r8, r8
0x180016570  jz      short loc_180016577
0x180016572  test    rdi, rdi
0x180016575  jnz     short loc_1800165F0
0x180016577  mov     ebx, 80070057h
0x18001657c  test    r8, r8
0x18001657f  jnz     short loc_180016597
0x180016581  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016588  jz      loc_1800166A0
0x18001658e  lea     rax, aTable; "Table"
0x180016595  jmp     short loc_1800165B0
0x180016597  test    rdi, rdi
0x18001659a  jnz     short loc_1800165CC
0x18001659c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800165a3  jz      loc_1800166A0
0x1800165a9  lea     rax, aSystemconfigur; "SystemConfiguration"
0x1800165b0  mov     r9d, 80070057h
0x1800165b6  mov     [rsp+38h+var_18], rax
0x1800165bb  lea     r8, aSystemtablepar; "SystemTableParser"
0x1800165c2  call    McTemplateU0sqs_EventWriteTransfer
0x1800165c7  jmp     loc_1800166A0
0x1800165cc  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800165d3  jz      loc_1800166A0
0x1800165d9  mov     r9d, 80070057h
0x1800165df  lea     r8, aSystemtablepar; "SystemTableParser"
0x1800165e6  call    McTemplateU0sq_EventWriteTransfer
0x1800165eb  jmp     loc_1800166A0
0x1800165f0  movzx   eax, byte ptr [r8+4]
0x1800165f5  cmp     eax, ecx
0x1800165f7  jnz     short loc_180016608
0x1800165f9  mov     rcx, rdx; psz
0x1800165fc  call    cs:__imp_SysAllocString
0x180016602  mov     [rdi+28h], rax
0x180016606  jmp     short loc_180016666
0x180016608  movzx   eax, byte ptr [r8+5]
0x18001660d  cmp     eax, ecx
0x18001660f  jnz     short loc_180016620
0x180016611  mov     rcx, rdx; psz
0x180016614  call    cs:__imp_SysAllocString
0x18001661a  mov     [rdi+30h], rax
0x18001661e  jmp     short loc_180016666
0x180016620  movzx   eax, byte ptr [r8+6]
0x180016625  cmp     eax, ecx
0x180016627  jnz     short loc_180016638
0x180016629  mov     rcx, rdx; psz
0x18001662c  call    cs:__imp_SysAllocString
0x180016632  mov     [rdi+48h], rax
0x180016636  jmp     short loc_180016666
0x180016638  movzx   eax, byte ptr [r8+19h]
0x18001663d  cmp     eax, ecx
0x18001663f  jnz     short loc_180016650
0x180016641  mov     rcx, rdx; psz
0x180016644  call    cs:__imp_SysAllocString
0x18001664a  mov     [rdi+40h], rax
0x18001664e  jmp     short loc_180016666
0x180016650  movzx   eax, byte ptr [r8+1Ah]
0x180016655  cmp     eax, ecx
0x180016657  jnz     short loc_180016682
0x180016659  mov     rcx, rdx; psz
0x18001665c  call    cs:__imp_SysAllocString
0x180016662  mov     [rdi+38h], rax
0x180016666  test    rax, rax
0x180016669  jnz     short loc_180016682
0x18001666b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180016672  mov     ebx, 8007000Eh
0x180016677  jz      short loc_1800166A0
0x180016679  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180016680  jmp     short loc_180016694
0x180016682  xor     ebx, ebx
0x180016684  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18001668b  jz      short loc_1800166A0
0x18001668d  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180016694  lea     r8, aSystemtablepar; "SystemTableParser"
0x18001669b  call    McTemplateU0s_EventWriteTransfer
0x1800166a0  mov     eax, ebx
0x1800166a2  mov     rbx, [rsp+38h+arg_0]
0x1800166a7  add     rsp, 30h
0x1800166ab  pop     rdi
0x1800166ac  retn
```
