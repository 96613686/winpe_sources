# CBWCResponse::get_DiagnosticCollection(CDiagnosticCollection *)

- ea: `0x18000daa0`
- end: `0x18000dc1f`
- name: `?get_DiagnosticCollection@CBWCResponse@@QEBAJPEAVCDiagnosticCollection@@@Z`
- size: `383`
- prototype: `__int64 __fastcall(SAFEARRAY **this, Enumerator **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000ac18`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x18000daa0`
- `0x18001114c`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000db10`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000db10`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000dc0a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000dc0a`

## pseudocode

```c
__int64 __fastcall CBWCResponse::get_DiagnosticCollection(SAFEARRAY **this, Enumerator **a2)
{
  int v4; // ebx
  SAFEARRAY *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rsi
  __int64 v8; // r9
  struct IDiagnostic *v10; // [rsp+58h] [rbp+10h] BYREF
  void *ppvData; // [rsp+60h] [rbp+18h] BYREF

  ppvData = 0;
  v10 = 0;
  if ( a2 )
  {
    v5 = *this;
    v4 = 0;
    if ( !v5 )
      goto LABEL_19;
    v4 = SafeArrayAccessData(v5, &ppvData);
    if ( v4 >= 0 )
    {
      v5 = *this;
      v7 = 0;
      if ( !(*this)->rgsabound[0].cElements )
      {
LABEL_13:
        if ( v4 )
        {
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
            goto LABEL_21;
          v8 = (unsigned int)v4;
LABEL_16:
          McTemplateU0sq_EventWriteTransfer(v5, v6, "CBWCResponse::get_DiagnosticCollection", v8);
          goto LABEL_21;
        }
LABEL_19:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
          McTemplateU0s_EventWriteTransfer(v5, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CBWCResponse::get_DiagnosticCollection");
        goto LABEL_21;
      }
      do
      {
        if ( v10 )
        {
          (*(void (__fastcall **)(struct IDiagnostic *))(*(_QWORD *)v10 + 16LL))(v10);
          v10 = 0;
        }
        v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IDiagnostic **))ppvData + 3 * v7 + 1))(
               *((_QWORD *)ppvData + 3 * v7 + 1),
               &IID_IDiagnostic,
               &v10);
        if ( v4 < 0 )
          break;
        v4 = CDiagnosticCollection::Append(a2, v10);
        if ( v4 < 0 )
          break;
        v7 = (unsigned int)(v7 + 1);
      }
      while ( (unsigned int)v7 < (*this)->rgsabound[0].cElements );
    }
    if ( v4 == -2147024809 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_21;
      v8 = 2147942487LL;
      goto LABEL_16;
    }
    goto LABEL_13;
  }
  v4 = -2147024809;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
    return (unsigned int)v4;
  McTemplateU0sqs_EventWriteTransfer(
    (_DWORD)this,
    0,
    (unsigned int)"CBWCResponse::get_DiagnosticCollection",
    -2147024809,
    (__int64)"DiagnosticCollection");
LABEL_21:
  if ( v10 )
  {
    (*(void (__fastcall **)(struct IDiagnostic *))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = 0;
  }
  if ( ppvData )
    SafeArrayUnaccessData(*this);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000daa0  mov     r11, rsp
0x18000daa3  mov     [r11+8], rbx
0x18000daa7  push    rbp
0x18000daa8  push    rsi
0x18000daa9  push    rdi
0x18000daaa  sub     rsp, 30h
0x18000daae  mov     qword ptr [r11+18h], 0
0x18000dab6  mov     rbp, rdx
0x18000dab9  mov     qword ptr [r11+10h], 0
0x18000dac1  mov     rdi, rcx
0x18000dac4  test    rdx, rdx
0x18000dac7  jnz     short loc_18000DAFD
0x18000dac9  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000dad0  mov     ebx, 80070057h
0x18000dad5  jz      loc_18000DC10
0x18000dadb  lea     rax, aDiagnosticcoll; "DiagnosticCollection"
0x18000dae2  mov     r9d, 80070057h
0x18000dae8  lea     r8, aCbwcresponseGe; "CBWCResponse::get_DiagnosticCollection"
0x18000daef  mov     [r11-28h], rax
0x18000daf3  call    McTemplateU0sqs_EventWriteTransfer
0x18000daf8  jmp     loc_18000DBE0
0x18000dafd  mov     rcx, [rcx]; psa
0x18000db00  xor     ebx, ebx
0x18000db02  test    rcx, rcx
0x18000db05  jz      loc_18000DBC4
0x18000db0b  lea     rdx, [rsp+48h+ppvData]; ppvData
0x18000db10  call    cs:__imp_SafeArrayAccessData
0x18000db16  mov     ebx, eax
0x18000db18  test    eax, eax
0x18000db1a  js      short loc_18000DB8D
0x18000db1c  mov     rcx, [rdi]
0x18000db1f  xor     esi, esi
0x18000db21  cmp     [rcx+18h], esi
0x18000db24  jbe     short loc_18000DB95
0x18000db26  mov     rcx, [rsp+48h+arg_8]
0x18000db2b  test    rcx, rcx
0x18000db2e  jz      short loc_18000DB45
0x18000db30  mov     rax, [rcx]
0x18000db33  mov     rax, [rax+10h]
0x18000db37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db3c  mov     [rsp+48h+arg_8], 0
0x18000db45  mov     rax, [rsp+48h+ppvData]
0x18000db4a  lea     rcx, [rsi+rsi*2]
0x18000db4e  lea     r8, [rsp+48h+arg_8]
0x18000db53  lea     rdx, IID_IDiagnostic
0x18000db5a  mov     rcx, [rax+rcx*8+8]
0x18000db5f  mov     rax, [rcx]
0x18000db62  mov     rax, [rax]
0x18000db65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db6a  mov     ebx, eax
0x18000db6c  test    eax, eax
0x18000db6e  js      short loc_18000DB8D
0x18000db70  mov     rdx, [rsp+48h+arg_8]; struct IDiagnostic *
0x18000db75  mov     rcx, rbp; this
0x18000db78  call    ?Append@CDiagnosticCollection@@QEAAJPEAUIDiagnostic@@@Z; CDiagnosticCollection::Append(IDiagnostic *)
0x18000db7d  mov     ebx, eax
0x18000db7f  test    eax, eax
0x18000db81  js      short loc_18000DB8D
0x18000db83  mov     rax, [rdi]
0x18000db86  inc     esi
0x18000db88  cmp     esi, [rax+18h]
0x18000db8b  jb      short loc_18000DB26
0x18000db8d  cmp     ebx, 80070057h
0x18000db93  jz      short loc_18000DBB3
0x18000db95  test    ebx, ebx
0x18000db97  jz      short loc_18000DBC4
0x18000db99  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000dba0  jz      short loc_18000DBE0
0x18000dba2  mov     r9d, ebx
0x18000dba5  lea     r8, aCbwcresponseGe; "CBWCResponse::get_DiagnosticCollection"
0x18000dbac  call    McTemplateU0sq_EventWriteTransfer
0x18000dbb1  jmp     short loc_18000DBE0
0x18000dbb3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000dbba  jz      short loc_18000DBE0
0x18000dbbc  mov     r9d, 80070057h
0x18000dbc2  jmp     short loc_18000DBA5
0x18000dbc4  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000dbcb  jz      short loc_18000DBE0
0x18000dbcd  lea     r8, aCbwcresponseGe; "CBWCResponse::get_DiagnosticCollection"
0x18000dbd4  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000dbdb  call    McTemplateU0s_EventWriteTransfer
0x18000dbe0  mov     rcx, [rsp+48h+arg_8]
0x18000dbe5  test    rcx, rcx
0x18000dbe8  jz      short loc_18000DBFF
0x18000dbea  mov     rax, [rcx]
0x18000dbed  mov     rax, [rax+10h]
0x18000dbf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbf6  mov     [rsp+48h+arg_8], 0
0x18000dbff  cmp     [rsp+48h+ppvData], 0
0x18000dc05  jz      short loc_18000DC10
0x18000dc07  mov     rcx, [rdi]; psa
0x18000dc0a  call    cs:__imp_SafeArrayUnaccessData
0x18000dc10  mov     eax, ebx
0x18000dc12  mov     rbx, [rsp+48h+arg_0]
0x18000dc17  add     rsp, 30h
0x18000dc1b  pop     rdi
0x18000dc1c  pop     rsi
0x18000dc1d  pop     rbp
0x18000dc1e  retn
```
