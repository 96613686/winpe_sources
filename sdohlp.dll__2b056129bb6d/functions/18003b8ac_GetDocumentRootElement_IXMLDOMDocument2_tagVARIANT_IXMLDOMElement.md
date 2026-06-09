# GetDocumentRootElement(IXMLDOMDocument2 *,tagVARIANT,IXMLDOMElement * *)

- ea: `0x18003b8ac`
- end: `0x18003bb33`
- name: `?GetDocumentRootElement@@YAJPEAUIXMLDOMDocument2@@UtagVARIANT@@PEAPEAUIXMLDOMElement@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct tagVARIANT *__struct_ptr, struct IXMLDOMElement **)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18003a164`
- `0x18003a880`
- `0x18003b31c`
- `0x18003bc7c`
- `0x18003c96c`
- `0x18003d140`

## callees

- `0x18002cca4`
- `0x18002cd00`
- `0x18003b8ac`
- `0x18003d9b0`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x18003b905`: `m_pXmlDom->put_Async failed with 0x%x`
- `0x18003b987`: `m_pXmlDom->put_preserveWhiteSpace failed with 0x%x`
- `0x18003ba98`: `pXmlDom->load failed`
- `0x18003ba36`: `pXmlDom->get_documentElement failed with 0x%x`

## pseudocode

```c
__int64 __fastcall GetDocumentRootElement(
        struct IXMLDOMDocument2 *a1,
        struct tagVARIANT *a2,
        struct IXMLDOMElement **a3)
{
  int v6; // ebx
  int v7; // edx
  IRecordInfo *pRecInfo; // xmm1_8
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  int v10; // ebx
  PVOID *v11; // rax
  __int128 v13; // [rsp+30h] [rbp-48h] BYREF
  IRecordInfo *v14; // [rsp+40h] [rbp-38h]
  __int16 v15; // [rsp+80h] [rbp+8h] BYREF

  v6 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD))a1->lpVtbl->put_async)(a1, 0);
  if ( v6 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD))a1->lpVtbl->put_preserveWhiteSpace)(a1, 0);
    if ( v6 >= 0 )
    {
      pRecInfo = a2->pRecInfo;
      v13 = *(_OWORD *)&a2->vt;
      v15 = 0;
      lpVtbl = a1->lpVtbl;
      v14 = pRecInfo;
      v10 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int128 *, __int16 *))lpVtbl->load)(a1, &v13, &v15);
      if ( v10 >= 0 && v15 )
      {
        v6 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, struct IXMLDOMElement **))a1->lpVtbl->get_documentElement)(
               a1,
               a3);
        if ( v6 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("pXmlDom->get_documentElement failed with 0x%x");
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
              (unsigned int)"NPSSDO",
              v6);
          }
          TraceXMLFailure(a1);
        }
      }
      else
      {
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("pXmlDom->load failed");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids, "NPSSDO");
          v11 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v10 < 0 && v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 25) >= 2u && (*((_DWORD *)v11 + 7) & 0x400) != 0 )
        {
          WppDbgPrint("load failure: 0x%x");
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
            (unsigned int)"NPSSDO",
            v10);
        }
        TraceXMLFailure(a1);
        return (unsigned int)-2147467259;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("m_pXmlDom->put_preserveWhiteSpace failed with 0x%x");
      v7 = 14;
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("m_pXmlDom->put_Async failed with 0x%x");
    v7 = 13;
LABEL_6:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
      (unsigned int)"NPSSDO",
      v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003b8ac  push    rbx
0x18003b8ae  push    rbp
0x18003b8af  push    rsi
0x18003b8b0  push    rdi
0x18003b8b1  sub     rsp, 58h
0x18003b8b5  mov     rax, [rcx]
0x18003b8b8  mov     rdi, rdx
0x18003b8bb  xor     edx, edx
0x18003b8bd  mov     rbp, r8
0x18003b8c0  mov     rsi, rcx
0x18003b8c3  mov     rax, [rax+1F8h]
0x18003b8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8cf  mov     ebx, eax
0x18003b8d1  test    eax, eax
0x18003b8d3  jns     short loc_18003B93D
0x18003b8d5  mov     rax, cs:WPP_GLOBAL_Control
0x18003b8dc  lea     rdi, WPP_GLOBAL_Control
0x18003b8e3  cmp     rax, rdi
0x18003b8e6  jz      loc_18003BB28
0x18003b8ec  cmp     byte ptr [rax+19h], 2
0x18003b8f0  jb      loc_18003BB28
0x18003b8f6  test    dword ptr [rax+1Ch], 400h
0x18003b8fd  jz      loc_18003BB28
0x18003b903  mov     edx, ebx
0x18003b905  lea     rcx, aMPxmldomPutAsy; "m_pXmlDom->put_Async failed with 0x%x"
0x18003b90c  call    WppDbgPrint
0x18003b911  mov     edx, 0Dh
0x18003b916  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b91d  lea     r9, aNpssdo; "NPSSDO"
0x18003b924  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003b92b  mov     [rsp+78h+var_58], ebx
0x18003b92f  mov     rcx, [rcx+10h]
0x18003b933  call    WPP_SF_sd
0x18003b938  jmp     loc_18003BB28
0x18003b93d  mov     rax, [rsi]
0x18003b940  xor     edx, edx
0x18003b942  mov     rcx, rsi
0x18003b945  mov     rax, [rax+240h]
0x18003b94c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b951  mov     ebx, eax
0x18003b953  test    eax, eax
0x18003b955  jns     short loc_18003B99D
0x18003b957  mov     rax, cs:WPP_GLOBAL_Control
0x18003b95e  lea     rdi, WPP_GLOBAL_Control
0x18003b965  cmp     rax, rdi
0x18003b968  jz      loc_18003BB28
0x18003b96e  cmp     byte ptr [rax+19h], 2
0x18003b972  jb      loc_18003BB28
0x18003b978  test    dword ptr [rax+1Ch], 400h
0x18003b97f  jz      loc_18003BB28
0x18003b985  mov     edx, ebx
0x18003b987  lea     rcx, aMPxmldomPutPre; "m_pXmlDom->put_preserveWhiteSpace faile"...
0x18003b98e  call    WppDbgPrint
0x18003b993  mov     edx, 0Eh
0x18003b998  jmp     loc_18003B916
0x18003b99d  movaps  xmm0, xmmword ptr [rdi]
0x18003b9a0  lea     r8, [rsp+78h+arg_0]
0x18003b9a8  movsd   xmm1, qword ptr [rdi+10h]
0x18003b9ad  lea     rdx, [rsp+78h+var_48]
0x18003b9b2  xor     eax, eax
0x18003b9b4  movaps  [rsp+78h+var_48], xmm0
0x18003b9b9  mov     [rsp+78h+arg_0], ax
0x18003b9c1  mov     rcx, rsi
0x18003b9c4  mov     rax, [rsi]
0x18003b9c7  movsd   [rsp+78h+var_38], xmm1
0x18003b9cd  mov     rax, [rax+1D0h]
0x18003b9d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9d9  mov     ebx, eax
0x18003b9db  test    eax, eax
0x18003b9dd  js      loc_18003BA76
0x18003b9e3  xor     ecx, ecx
0x18003b9e5  cmp     cx, [rsp+78h+arg_0]
0x18003b9ed  jz      loc_18003BA76
0x18003b9f3  mov     rax, [rsi]
0x18003b9f6  mov     rdx, rbp
0x18003b9f9  mov     rcx, rsi
0x18003b9fc  mov     rax, [rax+168h]
0x18003ba03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba08  mov     ebx, eax
0x18003ba0a  test    eax, eax
0x18003ba0c  jns     loc_18003BB28
0x18003ba12  mov     rax, cs:WPP_GLOBAL_Control
0x18003ba19  lea     rdi, WPP_GLOBAL_Control
0x18003ba20  cmp     rax, rdi
0x18003ba23  jz      short loc_18003BA69
0x18003ba25  cmp     byte ptr [rax+19h], 2
0x18003ba29  jb      short loc_18003BA69
0x18003ba2b  test    dword ptr [rax+1Ch], 400h
0x18003ba32  jz      short loc_18003BA69
0x18003ba34  mov     edx, ebx
0x18003ba36  lea     rcx, aPxmldomGetDocu; "pXmlDom->get_documentElement failed wit"...
0x18003ba3d  call    WppDbgPrint
0x18003ba42  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ba49  lea     r9, aNpssdo; "NPSSDO"
0x18003ba50  mov     edx, 11h
0x18003ba55  mov     [rsp+78h+var_58], ebx
0x18003ba59  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003ba60  mov     rcx, [rcx+10h]
0x18003ba64  call    WPP_SF_sd
0x18003ba69  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x18003ba6c  call    ?TraceXMLFailure@@YAXPEAUIXMLDOMDocument2@@@Z; TraceXMLFailure(IXMLDOMDocument2 *)
0x18003ba71  jmp     loc_18003BB28
0x18003ba76  mov     rax, cs:WPP_GLOBAL_Control
0x18003ba7d  lea     rdi, WPP_GLOBAL_Control
0x18003ba84  cmp     rax, rdi
0x18003ba87  jz      short loc_18003BACE
0x18003ba89  cmp     byte ptr [rax+19h], 2
0x18003ba8d  jb      short loc_18003BACE
0x18003ba8f  test    dword ptr [rax+1Ch], 400h
0x18003ba96  jz      short loc_18003BACE
0x18003ba98  lea     rcx, aPxmldomLoadFai; "pXmlDom->load failed"
0x18003ba9f  call    WppDbgPrint
0x18003baa4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003baab  lea     r9, aNpssdo; "NPSSDO"
0x18003bab2  mov     edx, 0Fh
0x18003bab7  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003babe  mov     rcx, [rcx+10h]
0x18003bac2  call    WPP_SF_s
0x18003bac7  mov     rax, cs:WPP_GLOBAL_Control
0x18003bace  test    ebx, ebx
0x18003bad0  jns     short loc_18003BB1B
0x18003bad2  cmp     rax, rdi
0x18003bad5  jz      short loc_18003BB1B
0x18003bad7  cmp     byte ptr [rax+19h], 2
0x18003badb  jb      short loc_18003BB1B
0x18003badd  test    dword ptr [rax+1Ch], 400h
0x18003bae4  jz      short loc_18003BB1B
0x18003bae6  mov     edx, ebx
0x18003bae8  lea     rcx, aLoadFailure0xX; "load failure: 0x%x"
0x18003baef  call    WppDbgPrint
0x18003baf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bafb  lea     r9, aNpssdo; "NPSSDO"
0x18003bb02  mov     edx, 10h
0x18003bb07  mov     [rsp+78h+var_58], ebx
0x18003bb0b  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003bb12  mov     rcx, [rcx+10h]
0x18003bb16  call    WPP_SF_sd
0x18003bb1b  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x18003bb1e  call    ?TraceXMLFailure@@YAXPEAUIXMLDOMDocument2@@@Z; TraceXMLFailure(IXMLDOMDocument2 *)
0x18003bb23  mov     ebx, 80004005h
0x18003bb28  mov     eax, ebx
0x18003bb2a  add     rsp, 58h
0x18003bb2e  pop     rdi
0x18003bb2f  pop     rsi
0x18003bb30  pop     rbp
0x18003bb31  pop     rbx
0x18003bb32  retn
```
