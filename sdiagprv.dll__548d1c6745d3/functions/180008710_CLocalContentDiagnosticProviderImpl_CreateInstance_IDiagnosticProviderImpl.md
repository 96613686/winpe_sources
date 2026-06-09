# CLocalContentDiagnosticProviderImpl::CreateInstance(IDiagnosticProviderImpl * *)

- ea: `0x180008710`
- end: `0x1800087cf`
- name: `?CreateInstance@CLocalContentDiagnosticProviderImpl@@SAJPEAPEAVIDiagnosticProviderImpl@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(struct IDiagnosticProviderImpl **, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007660`

## callees

- `0x180001074`
- `0x1800024d4`
- `0x1800025ec`
- `0x180008710`

## string_xrefs

- `0x180008743`: `CLocalContentDiagnosticProviderImpl::CreateInstance`
- `0x1800087b6`: `CLocalContentDiagnosticProviderImpl::CreateInstance`

## pseudocode

```c
__int64 __fastcall CLocalContentDiagnosticProviderImpl::CreateInstance(struct IDiagnosticProviderImpl **a1, int a2)
{
  unsigned int v2; // ebx
  _QWORD *v4; // rax
  void **v5; // rcx
  __int64 *v6; // rdx

  v2 = 0;
  if ( a1 )
  {
    *a1 = 0;
    v4 = operator new(0x38u);
    if ( v4 )
    {
      v5 = &CLocalContentDiagnosticProviderImpl::`vftable';
      v4[1] = 0;
      *v4 = &CLocalContentDiagnosticProviderImpl::`vftable';
      v4[2] = 0;
      v4[3] = 0;
      *((_DWORD *)v4 + 8) = 0;
      v4[5] = -1;
      *((_DWORD *)v4 + 12) = 0;
      *a1 = (struct IDiagnosticProviderImpl *)v4;
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
        return v2;
      v6 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
    }
    else
    {
      v2 = -2147024882;
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        return v2;
      v6 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    }
    McTemplateU0s_EventWriteTransfer(v5, v6, "CLocalContentDiagnosticProviderImpl::CreateInstance");
    return v2;
  }
  v2 = -2147024809;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sqs_EventWriteTransfer(
      0,
      a2,
      (unsigned int)"CLocalContentDiagnosticProviderImpl::CreateInstance",
      -2147024809,
      (__int64)"DiagnosticProviderImpl");
  return v2;
}

```

## disassembly

```asm
0x180008710  mov     [rsp+arg_0], rbx
0x180008715  push    rdi
0x180008716  sub     rsp, 30h
0x18000871a  xor     ebx, ebx
0x18000871c  mov     rdi, rcx
0x18000871f  test    rcx, rcx
0x180008722  jnz     short loc_180008756
0x180008724  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000872b  mov     ebx, 80070057h
0x180008730  jz      loc_1800087C2
0x180008736  lea     rax, aDiagnosticprov; "DiagnosticProviderImpl"
0x18000873d  mov     r9d, 80070057h
0x180008743  lea     r8, aClocalcontentd_4; "CLocalContentDiagnosticProviderImpl::Cr"...
0x18000874a  mov     [rsp+38h+var_18], rax
0x18000874f  call    McTemplateU0sqs_EventWriteTransfer
0x180008754  jmp     short loc_1800087C2
0x180008756  mov     [rcx], rbx
0x180008759  mov     ecx, 38h ; '8'; Size
0x18000875e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008763  test    rax, rax
0x180008766  jz      short loc_1800087A1
0x180008768  lea     rcx, ??_7CLocalContentDiagnosticProviderImpl@@6B@; const CLocalContentDiagnosticProviderImpl::`vftable'
0x18000876f  mov     [rax+8], rbx
0x180008773  mov     [rax], rcx
0x180008776  mov     [rax+10h], rbx
0x18000877a  mov     [rax+18h], rbx
0x18000877e  mov     [rax+20h], ebx
0x180008781  mov     qword ptr [rax+28h], 0FFFFFFFFFFFFFFFFh
0x180008789  mov     [rax+30h], ebx
0x18000878c  mov     [rdi], rax
0x18000878f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180008796  jz      short loc_1800087C2
0x180008798  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000879f  jmp     short loc_1800087B6
0x1800087a1  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800087a8  mov     ebx, 8007000Eh
0x1800087ad  jz      short loc_1800087C2
0x1800087af  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x1800087b6  lea     r8, aClocalcontentd_4; "CLocalContentDiagnosticProviderImpl::Cr"...
0x1800087bd  call    McTemplateU0s_EventWriteTransfer
0x1800087c2  mov     eax, ebx
0x1800087c4  mov     rbx, [rsp+38h+arg_0]
0x1800087c9  add     rsp, 30h
0x1800087cd  pop     rdi
0x1800087ce  retn
```
