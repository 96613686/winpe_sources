# CBWCResponse::CreateInstance(IStream *,CBWCResponse * *,ushort * *)

- ea: `0x18000d244`
- end: `0x18000d410`
- name: `?CreateInstance@CBWCResponse@@SAJPEAUIStream@@PEAPEAV1@PEAPEAG@Z`
- size: `460`
- prototype: `__int64 __fastcall(struct IStream *, struct tagSAFEARRAY ***, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ac18`

## callees

- `0x180001074`
- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180009b70`
- `0x18000d244`
- `0x18000d418`
- `0x18000d748`
- `0x180019010`

## string_xrefs

- `0x18000d2b7`: `CBWCResponse::CreateInstance`
- `0x18000d35e`: `CBWCResponse::CreateInstance`
- `0x18000d3a6`: `CBWCResponse::CreateInstance`

## pseudocode

```c
__int64 __fastcall CBWCResponse::CreateInstance(struct IStream *a1, struct tagSAFEARRAY ***a2, unsigned __int16 **a3)
{
  struct tagSAFEARRAY **v3; // rbx
  int Diagnostics; // edi
  const char *v8; // rax
  struct tagSAFEARRAY **v9; // rax
  __int64 v10; // r9
  __int64 *v11; // rdx
  struct IXMLDOMElement *v13; // [rsp+50h] [rbp+8h] BYREF
  struct IXMLDOMNodeList *v14; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  v13 = 0;
  v14 = 0;
  if ( !a1 )
  {
    Diagnostics = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      return (unsigned int)Diagnostics;
    v8 = "Stream";
    goto LABEL_9;
  }
  if ( !a2 || !a3 )
  {
    Diagnostics = -2147024809;
    goto LABEL_6;
  }
  *a2 = 0;
  *a3 = 0;
  v9 = (struct tagSAFEARRAY **)operator new(8u);
  v3 = v9;
  if ( !v9 )
  {
    Diagnostics = -2147024882;
    v3 = 0;
    goto LABEL_27;
  }
  *v9 = 0;
  Diagnostics = CBWCResponse::ValidateXml(a1, &v13, a3);
  if ( Diagnostics >= 0 )
  {
    Diagnostics = ((__int64 (__fastcall *)(struct IXMLDOMElement *, struct IXMLDOMNodeList **))v13->lpVtbl->get_childNodes)(
                    v13,
                    &v14);
    if ( Diagnostics >= 0 )
    {
      Diagnostics = CBWCResponse::ExtractDiagnostics(v14, v3);
      if ( Diagnostics >= 0 )
      {
        *a2 = v3;
LABEL_18:
        if ( Diagnostics )
        {
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
            goto LABEL_30;
          v10 = (unsigned int)Diagnostics;
LABEL_21:
          McTemplateU0sq_EventWriteTransfer(a1, a2, "CBWCResponse::CreateInstance", v10);
          goto LABEL_30;
        }
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
          goto LABEL_30;
        v11 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_29:
        McTemplateU0s_EventWriteTransfer(a1, v11, "CBWCResponse::CreateInstance");
        goto LABEL_30;
      }
    }
  }
  if ( Diagnostics == -2147024882 )
  {
LABEL_27:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_30;
    v11 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    goto LABEL_29;
  }
  if ( Diagnostics != -2147024809 )
    goto LABEL_18;
LABEL_6:
  if ( a2 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_30;
    v10 = 2147942487LL;
    goto LABEL_21;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v8 = "BWCResponse";
LABEL_9:
    McTemplateU0sqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      (unsigned int)"CBWCResponse::CreateInstance",
      -2147024809,
      (__int64)v8);
  }
LABEL_30:
  if ( v13 )
  {
    ((void (__fastcall *)(struct IXMLDOMElement *))v13->lpVtbl->Release)(v13);
    v13 = 0;
  }
  if ( v14 )
  {
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v14->lpVtbl->Release)(v14);
    v14 = 0;
  }
  if ( Diagnostics < 0 && v3 )
    CBWCResponse::`scalar deleting destructor'((CBWCResponse *)v3, (unsigned int)a2);
  return (unsigned int)Diagnostics;
}

```

## disassembly

```asm
0x18000d244  mov     [rsp+arg_8], rbx
0x18000d249  push    rbp
0x18000d24a  push    rsi
0x18000d24b  push    rdi
0x18000d24c  sub     rsp, 30h
0x18000d250  xor     ebx, ebx
0x18000d252  mov     rdi, r8
0x18000d255  mov     [rsp+48h+arg_0], rbx
0x18000d25a  mov     rsi, rdx
0x18000d25d  mov     [rsp+48h+arg_18], rbx
0x18000d262  mov     rbp, rcx
0x18000d265  test    rcx, rcx
0x18000d268  jnz     short loc_18000D285
0x18000d26a  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d271  mov     edi, 80070057h
0x18000d276  jz      loc_18000D401
0x18000d27c  lea     rax, aStream; "Stream"
0x18000d283  jmp     short loc_18000D2AC
0x18000d285  test    rsi, rsi
0x18000d288  jnz     short loc_18000D2C8
0x18000d28a  mov     edi, 80070057h
0x18000d28f  test    rsi, rsi
0x18000d292  jnz     loc_18000D37E
0x18000d298  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d29f  jz      loc_18000D3B2
0x18000d2a5  lea     rax, aBwcresponse; "BWCResponse"
0x18000d2ac  mov     r9d, 80070057h
0x18000d2b2  mov     [rsp+48h+var_28], rax
0x18000d2b7  lea     r8, aCbwcresponseCr; "CBWCResponse::CreateInstance"
0x18000d2be  call    McTemplateU0sqs_EventWriteTransfer
0x18000d2c3  jmp     loc_18000D3B2
0x18000d2c8  test    rdi, rdi
0x18000d2cb  jz      short loc_18000D28A
0x18000d2cd  mov     ecx, 8; Size
0x18000d2d2  mov     [rdx], rbx
0x18000d2d5  mov     [r8], rbx
0x18000d2d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d2dd  mov     rbx, rax
0x18000d2e0  test    rax, rax
0x18000d2e3  jz      loc_18000D38F
0x18000d2e9  mov     r8, rdi; unsigned __int16 **
0x18000d2ec  mov     qword ptr [rax], 0
0x18000d2f3  lea     rdx, [rsp+48h+arg_0]; struct IXMLDOMElement **
0x18000d2f8  mov     rcx, rbp; struct IStream *
0x18000d2fb  call    ?ValidateXml@CBWCResponse@@CAJPEAUIStream@@PEAPEAUIXMLDOMElement@@PEAPEAG@Z; CBWCResponse::ValidateXml(IStream *,IXMLDOMElement * *,ushort * *)
0x18000d300  mov     edi, eax
0x18000d302  test    eax, eax
0x18000d304  js      short loc_18000D33A
0x18000d306  mov     rcx, [rsp+48h+arg_0]
0x18000d30b  lea     rdx, [rsp+48h+arg_18]
0x18000d310  mov     rax, [rcx]
0x18000d313  mov     rax, [rax+60h]
0x18000d317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d31c  mov     edi, eax
0x18000d31e  test    eax, eax
0x18000d320  js      short loc_18000D33A
0x18000d322  mov     rcx, [rsp+48h+arg_18]; struct IXMLDOMNodeList *
0x18000d327  mov     rdx, rbx; struct tagSAFEARRAY **
0x18000d32a  call    ?ExtractDiagnostics@CBWCResponse@@CAJPEAUIXMLDOMNodeList@@PEAPEAUtagSAFEARRAY@@@Z; CBWCResponse::ExtractDiagnostics(IXMLDOMNodeList *,tagSAFEARRAY * *)
0x18000d32f  mov     edi, eax
0x18000d331  test    eax, eax
0x18000d333  js      short loc_18000D33A
0x18000d335  mov     [rsi], rbx
0x18000d338  jmp     short loc_18000D34E
0x18000d33a  cmp     edi, 8007000Eh
0x18000d340  jz      short loc_18000D396
0x18000d342  cmp     edi, 80070057h
0x18000d348  jz      loc_18000D28F
0x18000d34e  test    edi, edi
0x18000d350  jz      short loc_18000D36C
0x18000d352  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d359  jz      short loc_18000D3B2
0x18000d35b  mov     r9d, edi
0x18000d35e  lea     r8, aCbwcresponseCr; "CBWCResponse::CreateInstance"
0x18000d365  call    McTemplateU0sq_EventWriteTransfer
0x18000d36a  jmp     short loc_18000D3B2
0x18000d36c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000d373  jz      short loc_18000D3B2
0x18000d375  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000d37c  jmp     short loc_18000D3A6
0x18000d37e  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d385  jz      short loc_18000D3B2
0x18000d387  mov     r9d, 80070057h
0x18000d38d  jmp     short loc_18000D35E
0x18000d38f  mov     edi, 8007000Eh
0x18000d394  xor     ebx, ebx
0x18000d396  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d39d  jz      short loc_18000D3B2
0x18000d39f  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000d3a6  lea     r8, aCbwcresponseCr; "CBWCResponse::CreateInstance"
0x18000d3ad  call    McTemplateU0s_EventWriteTransfer
0x18000d3b2  mov     rcx, [rsp+48h+arg_0]
0x18000d3b7  test    rcx, rcx
0x18000d3ba  jz      short loc_18000D3D1
0x18000d3bc  mov     rax, [rcx]
0x18000d3bf  mov     rax, [rax+10h]
0x18000d3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3c8  mov     [rsp+48h+arg_0], 0
0x18000d3d1  mov     rcx, [rsp+48h+arg_18]
0x18000d3d6  test    rcx, rcx
0x18000d3d9  jz      short loc_18000D3F0
0x18000d3db  mov     rax, [rcx]
0x18000d3de  mov     rax, [rax+10h]
0x18000d3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3e7  mov     [rsp+48h+arg_18], 0
0x18000d3f0  test    edi, edi
0x18000d3f2  jns     short loc_18000D401
0x18000d3f4  test    rbx, rbx
0x18000d3f7  jz      short loc_18000D401
0x18000d3f9  mov     rcx, rbx; this
0x18000d3fc  call    ??_GCBWCResponse@@QEAAPEAXI@Z; CBWCResponse::`scalar deleting destructor'(uint)
0x18000d401  mov     rbx, [rsp+48h+arg_8]
0x18000d406  mov     eax, edi
0x18000d408  add     rsp, 30h
0x18000d40c  pop     rdi
0x18000d40d  pop     rsi
0x18000d40e  pop     rbp
0x18000d40f  retn
```
