# BIOSTableParser(uint,ushort const *,void * const,_SYSTEM_CONFIGURATION *)

- ea: `0x180015060`
- end: `0x1800151d4`
- name: `?BIOSTableParser@@YAJIPEBGQEAXPEAU_SYSTEM_CONFIGURATION@@@Z`
- size: `372`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, _BYTE *, struct _SYSTEM_CONFIGURATION *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180015060`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180015124`
- `OLEAUT32!__imp_SysAllocString` at `0x18001513c`
- `OLEAUT32!__imp_SysAllocString` at `0x180015154`
- `OLEAUT32!__imp_SysAllocString` at `0x180015124`
- `OLEAUT32!__imp_SysAllocString` at `0x18001513c`
- `OLEAUT32!__imp_SysAllocString` at `0x180015154`

## string_xrefs

- `0x1800150d1`: `SystemConfiguration`

## pseudocode

```c
__int64 __fastcall BIOSTableParser(__int64 a1, const unsigned __int16 *a2, _BYTE *a3, struct _SYSTEM_CONFIGURATION *a4)
{
  unsigned int v6; // ebx
  const char *v7; // rax
  BSTR v8; // rax
  __int64 *v9; // rdx

  if ( !a2 )
  {
    v6 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      v7 = "String";
LABEL_12:
      McTemplateU0sqs_EventWriteTransfer(a1, (_DWORD)a2, (unsigned int)"BIOSTableParser", -2147024809, (__int64)v7);
      return v6;
    }
    return v6;
  }
  if ( a3 && a4 )
  {
    if ( (unsigned __int8)a3[4] == (_DWORD)a1 )
    {
      v8 = SysAllocString(a2);
      *((_QWORD *)a4 + 13) = v8;
    }
    else if ( (unsigned __int8)a3[5] == (_DWORD)a1 )
    {
      v8 = SysAllocString(a2);
      *((_QWORD *)a4 + 14) = v8;
    }
    else
    {
      if ( (unsigned __int8)a3[8] != (_DWORD)a1 )
        goto LABEL_24;
      v8 = SysAllocString(a2);
      *((_QWORD *)a4 + 15) = v8;
    }
    if ( !v8 )
    {
      v6 = -2147024882;
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        return v6;
      v9 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
      goto LABEL_28;
    }
LABEL_24:
    v6 = 0;
    if ( a3[1] >= 0x18u )
    {
      *((_BYTE *)a4 + 128) = a3[20];
      *((_BYTE *)a4 + 129) = a3[21];
      *((_BYTE *)a4 + 130) = a3[22];
      LOBYTE(a1) = a3[23];
      *((_BYTE *)a4 + 131) = a1;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
      return v6;
    v9 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_28:
    McTemplateU0s_EventWriteTransfer(a1, v9, "BIOSTableParser");
    return v6;
  }
  v6 = -2147024809;
  if ( a3 )
  {
    if ( a4 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        McTemplateU0sq_EventWriteTransfer(a1, a2, "BIOSTableParser", 2147942487LL);
    }
    else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      v7 = "SystemConfiguration";
      goto LABEL_12;
    }
  }
  else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v7 = "Table";
    goto LABEL_12;
  }
  return v6;
}

```

## disassembly

```asm
0x180015060  mov     [rsp+arg_0], rbx
0x180015065  mov     [rsp+arg_8], rsi
0x18001506a  push    rdi
0x18001506b  sub     rsp, 30h
0x18001506f  mov     rsi, r9
0x180015072  mov     rdi, r8
0x180015075  test    rdx, rdx
0x180015078  jnz     short loc_180015095
0x18001507a  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180015081  mov     ebx, 80070057h
0x180015086  jz      loc_1800151C2
0x18001508c  lea     rax, aString; "String"
0x180015093  jmp     short loc_1800150D8
0x180015095  test    rdi, rdi
0x180015098  jz      short loc_18001509F
0x18001509a  test    rsi, rsi
0x18001509d  jnz     short loc_180015118
0x18001509f  mov     ebx, 80070057h
0x1800150a4  test    rdi, rdi
0x1800150a7  jnz     short loc_1800150BF
0x1800150a9  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800150b0  jz      loc_1800151C2
0x1800150b6  lea     rax, aTable; "Table"
0x1800150bd  jmp     short loc_1800150D8
0x1800150bf  test    rsi, rsi
0x1800150c2  jnz     short loc_1800150F4
0x1800150c4  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800150cb  jz      loc_1800151C2
0x1800150d1  lea     rax, aSystemconfigur; "SystemConfiguration"
0x1800150d8  mov     r9d, 80070057h
0x1800150de  mov     [rsp+38h+var_18], rax
0x1800150e3  lea     r8, aBiostableparse; "BIOSTableParser"
0x1800150ea  call    McTemplateU0sqs_EventWriteTransfer
0x1800150ef  jmp     loc_1800151C2
0x1800150f4  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800150fb  jz      loc_1800151C2
0x180015101  mov     r9d, 80070057h
0x180015107  lea     r8, aBiostableparse; "BIOSTableParser"
0x18001510e  call    McTemplateU0sq_EventWriteTransfer
0x180015113  jmp     loc_1800151C2
0x180015118  movzx   eax, byte ptr [r8+4]
0x18001511d  cmp     eax, ecx
0x18001511f  jnz     short loc_180015130
0x180015121  mov     rcx, rdx; psz
0x180015124  call    cs:__imp_SysAllocString
0x18001512a  mov     [rsi+68h], rax
0x18001512e  jmp     short loc_18001515E
0x180015130  movzx   eax, byte ptr [r8+5]
0x180015135  cmp     eax, ecx
0x180015137  jnz     short loc_180015148
0x180015139  mov     rcx, rdx; psz
0x18001513c  call    cs:__imp_SysAllocString
0x180015142  mov     [rsi+70h], rax
0x180015146  jmp     short loc_18001515E
0x180015148  movzx   eax, byte ptr [r8+8]
0x18001514d  cmp     eax, ecx
0x18001514f  jnz     short loc_18001517A
0x180015151  mov     rcx, rdx; psz
0x180015154  call    cs:__imp_SysAllocString
0x18001515a  mov     [rsi+78h], rax
0x18001515e  test    rax, rax
0x180015161  jnz     short loc_18001517A
0x180015163  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001516a  mov     ebx, 8007000Eh
0x18001516f  jz      short loc_1800151C2
0x180015171  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180015178  jmp     short loc_1800151B6
0x18001517a  xor     ebx, ebx
0x18001517c  cmp     byte ptr [rdi+1], 18h
0x180015180  jb      short loc_1800151A6
0x180015182  mov     al, [rdi+14h]
0x180015185  mov     [rsi+80h], al
0x18001518b  mov     al, [rdi+15h]
0x18001518e  mov     [rsi+81h], al
0x180015194  mov     al, [rdi+16h]
0x180015197  mov     [rsi+82h], al
0x18001519d  mov     cl, [rdi+17h]
0x1800151a0  mov     [rsi+83h], cl
0x1800151a6  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800151ad  jz      short loc_1800151C2
0x1800151af  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800151b6  lea     r8, aBiostableparse; "BIOSTableParser"
0x1800151bd  call    McTemplateU0s_EventWriteTransfer
0x1800151c2  mov     rsi, [rsp+38h+arg_8]
0x1800151c7  mov     eax, ebx
0x1800151c9  mov     rbx, [rsp+38h+arg_0]
0x1800151ce  add     rsp, 30h
0x1800151d2  pop     rdi
0x1800151d3  retn
```
