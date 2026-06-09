# CDiagnostic::Load(IXMLDOMNode *)

- ea: `0x18001374c`
- end: `0x180013a61`
- name: `?Load@CDiagnostic@@QEAAJPEAUIXMLDOMNode@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(CDiagnostic *__hidden this, struct IXMLDOMNode *)`
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008f00`
- `0x18000d418`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x1800037fc`
- `0x180003908`
- `0x18001360c`
- `0x18001374c`
- `0x180016c78`
- `0x18001737c`
- `0x180017548`
- `0x180017628`
- `0x180017708`
- `0x1800177e8`
- `0x1800178c8`
- `0x1800179a8`
- `0x180017a88`
- `0x180017b68`
- `0x180017d30`
- `0x180017e10`
- `0x180017ee8`
- `0x180019010`

## string_xrefs

- `0x180013854`: `CDiagnosticXmlParser::get_Url`
- `0x180013890`: `CDiagnosticXmlParser::get_Url`
- `0x1800138aa`: `CDiagnosticXmlParser::get_Url`

## pseudocode

```c
__int64 __fastcall CDiagnostic::Load(CDiagnostic *this, struct IXMLDOMNode *a2)
{
  struct CDiagnosticXmlParser *v2; // rdi
  __int64 v5; // rcx
  int Id; // ebx
  __int64 v7; // rcx
  unsigned int XmlStringElement; // eax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r9
  __int64 *v13; // rdx
  struct CDiagnosticXmlParser *v15; // [rsp+70h] [rbp+8h] BYREF

  v2 = 0;
  v15 = 0;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START, "CDiagnostic::Load");
  SDiagPrvSyncObject::Lock((CDiagnostic *)((char *)this + 8));
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(v5, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END, "CDiagnostic::Load");
  if ( !a2 )
  {
    Id = -2147024809;
    goto LABEL_37;
  }
  Id = CDiagnosticXmlParser::CreateInstance(a2, &v15);
  if ( Id < 0 )
  {
    v2 = v15;
    goto LABEL_37;
  }
  CDiagnostic::Clear(this);
  v2 = v15;
  Id = CDiagnosticXmlParser::get_Id(v15, (unsigned __int16 **)this + 14);
  if ( Id < 0 )
    goto LABEL_37;
  Id = CDiagnosticXmlParser::get_Name(v2, (unsigned __int16 **)this + 9);
  if ( Id < 0 )
    goto LABEL_37;
  Id = CDiagnosticXmlParser::get_Description(v2, (unsigned __int16 **)this + 10);
  if ( Id < 0 )
    goto LABEL_37;
  *((_QWORD *)this + 11) = 0;
  if ( *((_DWORD *)v2 + 4) != 1 )
    goto LABEL_22;
  XmlStringElement = CDiagnosticXmlParser::ReadXmlStringElement(v2, L"dcp:Url", (unsigned __int16 **)this + 11);
  Id = XmlStringElement;
  if ( XmlStringElement == -2147024809 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      McTemplateU0sq_EventWriteTransfer(v7, v9, "CDiagnosticXmlParser::get_Url", 2147942487LL);
      goto LABEL_37;
    }
LABEL_18:
    if ( Id >= 0 )
      goto LABEL_38;
    goto LABEL_37;
  }
  if ( XmlStringElement )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v7, v9, "CDiagnosticXmlParser::get_Url", XmlStringElement);
    if ( (int)(Id + 0x80000000) >= 0 && Id != -2147024637 )
      goto LABEL_18;
  }
  else
  {
LABEL_22:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
      McTemplateU0s_EventWriteTransfer(v7, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CDiagnosticXmlParser::get_Url");
  }
  Id = CDiagnosticXmlParser::get_PrivacyUrl(v2, (unsigned __int16 **)this + 12);
  if ( Id >= 0 )
  {
    Id = CDiagnosticXmlParser::get_DiagnosticIcon(v2, (unsigned __int16 **)this + 17);
    if ( (int)(Id + 0x80000000) < 0 || Id == -2147024637 )
    {
      Id = CDiagnosticXmlParser::get_RequiresAdminPrivileges(v2, (__int16 *)this + 52);
      if ( (int)(Id + 0x80000000) < 0 || Id == -2147024637 )
      {
        Id = CDiagnosticXmlParser::get_Version(v2, (unsigned __int16 **)this + 18);
        if ( Id >= 0 )
        {
          Id = CDiagnosticXmlParser::get_PublisherName(v2, (unsigned __int16 **)this + 15);
          if ( Id >= 0 )
          {
            Id = CDiagnosticXmlParser::get_PublisherCertificateHash((__int64)v2, (struct tagSAFEARRAY **)this + 16);
            if ( Id >= 0 )
            {
              Id = CDiagnosticXmlParser::get_Category(v2, (unsigned __int16 **)this + 19);
              if ( Id >= 0 )
              {
                Id = CDiagnosticXmlParser::get_Keywords(v2, (struct tagSAFEARRAY **)this + 20);
                if ( (int)(Id + 0x80000000) < 0 || Id == -2147024637 )
                {
                  Id = 0;
                  goto LABEL_38;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_37:
  CDiagnostic::Clear(this);
LABEL_38:
  SDiagPrvSyncObject::Unlock((CDiagnostic *)((char *)this + 8));
  if ( Id == -2147024882 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_54;
    v13 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    goto LABEL_53;
  }
  if ( Id == -2147024809 )
  {
    if ( a2 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      {
        v12 = 2147942487LL;
LABEL_43:
        McTemplateU0sq_EventWriteTransfer(v11, v10, "CDiagnostic::Load", v12);
      }
    }
    else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      McTemplateU0sqs_EventWriteTransfer(v11, v10, (unsigned int)"CDiagnostic::Load", -2147024809, (__int64)"Node");
    }
  }
  else
  {
    if ( Id )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_54;
      v12 = (unsigned int)Id;
      goto LABEL_43;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    {
      v13 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_53:
      McTemplateU0s_EventWriteTransfer(v11, v13, "CDiagnostic::Load");
    }
  }
LABEL_54:
  if ( v2 )
    (**(void (__fastcall ***)(struct CDiagnosticXmlParser *, __int64))v2)(v2, 1);
  return (unsigned int)Id;
}

```

## disassembly

```asm
0x18001374c  push    rbx
0x18001374e  push    rbp
0x18001374f  push    rsi
0x180013750  push    rdi
0x180013751  push    r12
0x180013753  push    r14
0x180013755  sub     rsp, 38h
0x180013759  xor     edi, edi
0x18001375b  lea     r12, aCdiagnosticLoa; "CDiagnostic::Load"
0x180013762  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, dil
0x180013769  mov     rbp, rdx
0x18001376c  mov     rsi, rcx
0x18001376f  mov     [rsp+68h+arg_0], rdi
0x180013774  jge     short loc_180013785
0x180013776  mov     r8, r12
0x180013779  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START
0x180013780  call    McTemplateU0s_EventWriteTransfer
0x180013785  lea     rcx, [rsi+8]; this
0x180013789  call    ?Lock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Lock(void)
0x18001378e  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, dil
0x180013795  jge     short loc_1800137A6
0x180013797  mov     r8, r12
0x18001379a  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END
0x1800137a1  call    McTemplateU0s_EventWriteTransfer
0x1800137a6  test    rbp, rbp
0x1800137a9  jnz     short loc_1800137B5
0x1800137ab  mov     ebx, 80070057h
0x1800137b0  jmp     loc_18001399A
0x1800137b5  lea     rdx, [rsp+68h+arg_0]; struct CDiagnosticXmlParser **
0x1800137ba  mov     rcx, rbp; struct IXMLDOMNode *
0x1800137bd  call    ?CreateInstance@CDiagnosticXmlParser@@SAJPEAUIXMLDOMNode@@PEAPEAV1@@Z; CDiagnosticXmlParser::CreateInstance(IXMLDOMNode *,CDiagnosticXmlParser * *)
0x1800137c2  mov     ebx, eax
0x1800137c4  test    eax, eax
0x1800137c6  js      loc_180013995
0x1800137cc  mov     rcx, rsi; this
0x1800137cf  call    ?Clear@CDiagnostic@@AEAAXXZ; CDiagnostic::Clear(void)
0x1800137d4  mov     rdi, [rsp+68h+arg_0]
0x1800137d9  lea     rdx, [rsi+70h]; unsigned __int16 **
0x1800137dd  mov     rcx, rdi; this
0x1800137e0  call    ?get_Id@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z; CDiagnosticXmlParser::get_Id(ushort * *)
0x1800137e5  mov     ebx, eax
0x1800137e7  test    eax, eax
0x1800137e9  js      loc_18001399A
0x1800137ef  lea     rdx, [rsi+48h]; unsigned __int16 **
0x1800137f3  mov     rcx, rdi; this
0x1800137f6  call    ?get_Name@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z; CDiagnosticXmlParser::get_Name(ushort * *)
0x1800137fb  mov     ebx, eax
0x1800137fd  test    eax, eax
0x1800137ff  js      loc_18001399A
0x180013805  lea     rdx, [rsi+50h]; unsigned __int16 **
0x180013809  mov     rcx, rdi; this
0x18001380c  call    ?get_Description@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z; CDiagnosticXmlParser::get_Description(ushort * *)
0x180013811  mov     ebx, eax
0x180013813  test    eax, eax
0x180013815  js      loc_18001399A
0x18001381b  lea     r8, [rsi+58h]; unsigned __int16 **
0x18001381f  mov     qword ptr [r8], 0
0x180013826  cmp     dword ptr [rdi+10h], 1
0x18001382a  jnz     short loc_1800138A1
0x18001382c  lea     rdx, aDcpUrl; "dcp:Url"
0x180013833  mov     rcx, rdi; this
0x180013836  call    ?ReadXmlStringElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAG@Z; CDiagnosticXmlParser::ReadXmlStringElement(ushort const *,ushort * *)
0x18001383b  mov     ebx, eax
0x18001383d  cmp     eax, 80070057h
0x180013842  jz      short loc_180013881
0x180013844  test    eax, eax
0x180013846  jz      short loc_1800138A1
0x180013848  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001384f  jz      short loc_180013860
0x180013851  mov     r9d, eax
0x180013854  lea     r8, aCdiagnosticxml_12; "CDiagnosticXmlParser::get_Url"
0x18001385b  call    McTemplateU0sq_EventWriteTransfer
0x180013860  mov     ecx, 80000000h
0x180013865  lea     eax, [rbx+rcx]
0x180013868  test    ecx, eax
0x18001386a  jnz     short loc_1800138BD
0x18001386c  cmp     ebx, 80070103h
0x180013872  jz      short loc_1800138BD
0x180013874  test    ebx, ebx
0x180013876  jns     loc_1800139A2
0x18001387c  jmp     loc_18001399A
0x180013881  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180013888  jz      short loc_180013874
0x18001388a  mov     r9d, 80070057h
0x180013890  lea     r8, aCdiagnosticxml_12; "CDiagnosticXmlParser::get_Url"
0x180013897  call    McTemplateU0sq_EventWriteTransfer
0x18001389c  jmp     loc_18001399A
0x1800138a1  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800138a8  jz      short loc_1800138BD
0x1800138aa  lea     r8, aCdiagnosticxml_12; "CDiagnosticXmlParser::get_Url"
0x1800138b1  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800138b8  call    McTemplateU0s_EventWriteTransfer
0x1800138bd  lea     rdx, [rsi+60h]; unsigned __int16 **
0x1800138c1  mov     rcx, rdi; this
0x1800138c4  call    ?get_PrivacyUrl@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z; CDiagnosticXmlParser::get_PrivacyUrl(ushort * *)
0x1800138c9  mov     ebx, eax
0x1800138cb  test    eax, eax
0x1800138cd  js      loc_18001399A
0x1800138d3  lea     rdx, [rsi+88h]; unsigned __int16 **
0x1800138da  mov     rcx, rdi; this
0x1800138dd  call    ?get_DiagnosticIcon@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z; CDiagnosticXmlParser::get_DiagnosticIcon(ushort * *)
0x1800138e2  mov     ecx, 80000000h
0x1800138e7  mov     ebx, eax
0x1800138e9  add     eax, ecx
0x1800138eb  test    ecx, eax
0x1800138ed  jnz     short loc_1800138FB
0x1800138ef  cmp     ebx, 80070103h
0x1800138f5  jnz     loc_18001399A
0x1800138fb  lea     rdx, [rsi+68h]; __int16 *
0x1800138ff  mov     rcx, rdi; this
0x180013902  call    ?get_RequiresAdminPrivileges@CDiagnosticXmlParser@@QEAAJPEAF@Z; CDiagnosticXmlParser::get_RequiresAdminPrivileges(short *)
0x180013907  mov     ecx, 80000000h
0x18001390c  mov     ebx, eax
0x18001390e  add     eax, ecx
0x180013910  test    ecx, eax
0x180013912  jnz     short loc_18001391C
0x180013914  cmp     ebx, 80070103h
0x18001391a  jnz     short loc_18001399A
0x18001391c  lea     rdx, [rsi+90h]; unsigned __int16 **
0x180013923  mov     rcx, rdi; this
0x180013926  call    ?get_Version@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z; CDiagnosticXmlParser::get_Version(ushort * *)
0x18001392b  mov     ebx, eax
0x18001392d  test    eax, eax
0x18001392f  js      short loc_18001399A
0x180013931  lea     rdx, [rsi+78h]; unsigned __int16 **
0x180013935  mov     rcx, rdi; this
0x180013938  call    ?get_PublisherName@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z; CDiagnosticXmlParser::get_PublisherName(ushort * *)
0x18001393d  mov     ebx, eax
0x18001393f  test    eax, eax
0x180013941  js      short loc_18001399A
0x180013943  lea     rdx, [rsi+80h]; struct tagSAFEARRAY **
0x18001394a  mov     rcx, rdi; this
0x18001394d  call    ?get_PublisherCertificateHash@CDiagnosticXmlParser@@QEAAJPEAPEAUtagSAFEARRAY@@@Z; CDiagnosticXmlParser::get_PublisherCertificateHash(tagSAFEARRAY * *)
0x180013952  mov     ebx, eax
0x180013954  test    eax, eax
0x180013956  js      short loc_18001399A
0x180013958  lea     rdx, [rsi+98h]; unsigned __int16 **
0x18001395f  mov     rcx, rdi; this
0x180013962  call    ?get_Category@CDiagnosticXmlParser@@QEAAJPEAPEAG@Z; CDiagnosticXmlParser::get_Category(ushort * *)
0x180013967  mov     ebx, eax
0x180013969  test    eax, eax
0x18001396b  js      short loc_18001399A
0x18001396d  lea     rdx, [rsi+0A0h]; struct tagSAFEARRAY **
0x180013974  mov     rcx, rdi; this
0x180013977  call    ?get_Keywords@CDiagnosticXmlParser@@QEAAJPEAPEAUtagSAFEARRAY@@@Z; CDiagnosticXmlParser::get_Keywords(tagSAFEARRAY * *)
0x18001397c  mov     ecx, 80000000h
0x180013981  mov     ebx, eax
0x180013983  add     eax, ecx
0x180013985  test    ecx, eax
0x180013987  jnz     short loc_180013991
0x180013989  cmp     ebx, 80070103h
0x18001398f  jnz     short loc_18001399A
0x180013991  xor     ebx, ebx
0x180013993  jmp     short loc_1800139A2
0x180013995  mov     rdi, [rsp+68h+arg_0]
0x18001399a  mov     rcx, rsi; this
0x18001399d  call    ?Clear@CDiagnostic@@AEAAXXZ; CDiagnostic::Clear(void)
0x1800139a2  lea     rcx, [rsi+8]; this
0x1800139a6  call    ?Unlock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Unlock(void)
0x1800139ab  cmp     ebx, 8007000Eh
0x1800139b1  jz      short loc_180013A22
0x1800139b3  cmp     ebx, 80070057h
0x1800139b9  jz      short loc_1800139E7
0x1800139bb  test    ebx, ebx
0x1800139bd  jz      short loc_1800139D5
0x1800139bf  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800139c6  jz      short loc_180013A3A
0x1800139c8  mov     r9d, ebx
0x1800139cb  mov     r8, r12
0x1800139ce  call    McTemplateU0sq_EventWriteTransfer
0x1800139d3  jmp     short loc_180013A3A
0x1800139d5  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800139dc  jz      short loc_180013A3A
0x1800139de  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800139e5  jmp     short loc_180013A32
0x1800139e7  test    rbp, rbp
0x1800139ea  jnz     short loc_180013A11
0x1800139ec  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800139f3  jz      short loc_180013A3A
0x1800139f5  lea     rax, aNode; "Node"
0x1800139fc  mov     r9d, 80070057h
0x180013a02  mov     r8, r12
0x180013a05  mov     [rsp+68h+var_48], rax
0x180013a0a  call    McTemplateU0sqs_EventWriteTransfer
0x180013a0f  jmp     short loc_180013A3A
0x180013a11  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180013a18  jz      short loc_180013A3A
0x180013a1a  mov     r9d, 80070057h
0x180013a20  jmp     short loc_1800139CB
0x180013a22  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180013a29  jz      short loc_180013A3A
0x180013a2b  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180013a32  mov     r8, r12
0x180013a35  call    McTemplateU0s_EventWriteTransfer
0x180013a3a  test    rdi, rdi
0x180013a3d  jz      short loc_180013A52
0x180013a3f  mov     rax, [rdi]
0x180013a42  mov     edx, 1
0x180013a47  mov     rcx, rdi
0x180013a4a  mov     rax, [rax]
0x180013a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a52  mov     eax, ebx
0x180013a54  add     rsp, 38h
0x180013a58  pop     r14
0x180013a5a  pop     r12
0x180013a5c  pop     rdi
0x180013a5d  pop     rsi
0x180013a5e  pop     rbp
0x180013a5f  pop     rbx
0x180013a60  retn
```
