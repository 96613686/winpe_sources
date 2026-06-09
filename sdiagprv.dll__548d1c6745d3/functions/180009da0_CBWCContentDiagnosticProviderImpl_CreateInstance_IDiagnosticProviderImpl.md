# CBWCContentDiagnosticProviderImpl::CreateInstance(IDiagnosticProviderImpl * *)

- ea: `0x180009da0`
- end: `0x180009e58`
- name: `?CreateInstance@CBWCContentDiagnosticProviderImpl@@SAJPEAPEAVIDiagnosticProviderImpl@@@Z`
- size: `184`
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
- `0x180009da0`

## string_xrefs

- `0x180009dd3`: `CBWCContentDiagnosticProviderImpl::CreateInstance`
- `0x180009e3f`: `CBWCContentDiagnosticProviderImpl::CreateInstance`

## pseudocode

```c
__int64 __fastcall CBWCContentDiagnosticProviderImpl::CreateInstance(struct IDiagnosticProviderImpl **a1, int a2)
{
  unsigned int v2; // ebx
  _QWORD *v4; // rax
  void **v5; // rcx
  __int64 *v6; // rdx

  v2 = 0;
  if ( a1 )
  {
    *a1 = 0;
    v4 = operator new(0x28u);
    if ( v4 )
    {
      v5 = &CBWCContentDiagnosticProviderImpl::`vftable';
      v4[1] = 0;
      *v4 = &CBWCContentDiagnosticProviderImpl::`vftable';
      v4[2] = 0;
      v4[3] = -1;
      *((_DWORD *)v4 + 8) = 0;
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
    McTemplateU0s_EventWriteTransfer(v5, v6, "CBWCContentDiagnosticProviderImpl::CreateInstance");
    return v2;
  }
  v2 = -2147024809;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sqs_EventWriteTransfer(
      0,
      a2,
      (unsigned int)"CBWCContentDiagnosticProviderImpl::CreateInstance",
      -2147024809,
      (__int64)"DiagnosticProviderImpl");
  return v2;
}

```

## disassembly

```asm
0x180009da0  mov     [rsp+arg_0], rbx
0x180009da5  push    rdi
0x180009da6  sub     rsp, 30h
0x180009daa  xor     ebx, ebx
0x180009dac  mov     rdi, rcx
0x180009daf  test    rcx, rcx
0x180009db2  jnz     short loc_180009DE6
0x180009db4  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180009dbb  mov     ebx, 80070057h
0x180009dc0  jz      loc_180009E4B
0x180009dc6  lea     rax, aDiagnosticprov; "DiagnosticProviderImpl"
0x180009dcd  mov     r9d, 80070057h
0x180009dd3  lea     r8, aCbwccontentdia_2; "CBWCContentDiagnosticProviderImpl::Crea"...
0x180009dda  mov     [rsp+38h+var_18], rax
0x180009ddf  call    McTemplateU0sqs_EventWriteTransfer
0x180009de4  jmp     short loc_180009E4B
0x180009de6  mov     [rcx], rbx
0x180009de9  mov     ecx, 28h ; '('; Size
0x180009dee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009df3  test    rax, rax
0x180009df6  jz      short loc_180009E2A
0x180009df8  lea     rcx, ??_7CBWCContentDiagnosticProviderImpl@@6B@; const CBWCContentDiagnosticProviderImpl::`vftable'
0x180009dff  mov     [rax+8], rbx
0x180009e03  mov     [rax], rcx
0x180009e06  mov     [rax+10h], rbx
0x180009e0a  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180009e12  mov     [rax+20h], ebx
0x180009e15  mov     [rdi], rax
0x180009e18  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180009e1f  jz      short loc_180009E4B
0x180009e21  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180009e28  jmp     short loc_180009E3F
0x180009e2a  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180009e31  mov     ebx, 8007000Eh
0x180009e36  jz      short loc_180009E4B
0x180009e38  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180009e3f  lea     r8, aCbwccontentdia_2; "CBWCContentDiagnosticProviderImpl::Crea"...
0x180009e46  call    McTemplateU0s_EventWriteTransfer
0x180009e4b  mov     eax, ebx
0x180009e4d  mov     rbx, [rsp+38h+arg_0]
0x180009e52  add     rsp, 30h
0x180009e56  pop     rdi
0x180009e57  retn
```
