# IASExim::Export(ushort *,ushort *)

- ea: `0x18003a6fc`
- end: `0x18003a87a`
- name: `?Export@IASExim@@QEAAJPEAG0@Z`
- size: `382`
- prototype: `__int64 __fastcall(IASExim *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002d3e0`

## callees

- `0x18002cd00`
- `0x18003a6fc`
- `0x18003a880`
- `0x18003b31c`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18003a726`
- `OLEAUT32!__imp_SysStringLen` at `0x18003a726`

## string_xrefs

- `0x18003a787`: `m_pXmlHelper->Export failed with 0x%x`
- `0x18003a7d6`: `ExportRegistry failed with 0x%x`

## pseudocode

```c
__int64 __fastcall IASExim::Export(struct IXMLDOMDocument2 **this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  int v7; // ebx
  int v8; // edx
  int v9; // eax
  unsigned __int16 *v10; // rdx
  char v11; // bl

  if ( a3 && *this )
  {
    if ( !SysStringLen(a3) )
      return 2147942487LL;
    v7 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, unsigned __int16 *, unsigned __int16 *))(*this)->lpVtbl->GetTypeInfoCount)(
           *this,
           a2,
           a3);
    if ( v7 >= 0 )
    {
      v9 = IASExim::ExportRegistry(this, a2, a3);
      v11 = v9;
      if ( v9 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("ExportRegistry failed with 0x%x");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
          (unsigned int)"NPSSDO",
          v11);
      }
      v7 = IASExim::ExportSystemInfo(this, v10, a3);
      if ( v7 >= 0
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
        return (unsigned int)v7;
      }
      WppDbgPrint("ExportSystemInfo failed with 0x%x");
      v8 = 40;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
        return (unsigned int)v7;
      }
      WppDbgPrint("m_pXmlHelper->Export failed with 0x%x");
      v8 = 38;
    }
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
      (unsigned int)"NPSSDO",
      v7);
    return (unsigned int)v7;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18003a6fc  push    rbx
0x18003a6fe  push    rbp
0x18003a6ff  push    rsi
0x18003a700  push    rdi
0x18003a701  push    r14
0x18003a703  sub     rsp, 30h
0x18003a707  mov     rbp, r8
0x18003a70a  mov     rdi, rdx
0x18003a70d  mov     r14, rcx
0x18003a710  test    r8, r8
0x18003a713  jz      loc_18003A86A
0x18003a719  cmp     qword ptr [rcx], 0
0x18003a71d  jz      loc_18003A86A
0x18003a723  mov     rcx, r8; pbstr
0x18003a726  call    cs:__imp_SysStringLen
0x18003a72c  cmp     eax, 1
0x18003a72f  jnb     short loc_18003A73B
0x18003a731  mov     eax, 80070057h
0x18003a736  jmp     loc_18003A86F
0x18003a73b  mov     rcx, [r14]
0x18003a73e  mov     r8, rbp
0x18003a741  mov     rdx, rdi
0x18003a744  mov     rax, [rcx]
0x18003a747  mov     rax, [rax+18h]
0x18003a74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a750  mov     ebx, eax
0x18003a752  test    eax, eax
0x18003a754  jns     short loc_18003A79D
0x18003a756  mov     rax, cs:WPP_GLOBAL_Control
0x18003a75d  lea     rsi, WPP_GLOBAL_Control
0x18003a764  cmp     rax, rsi
0x18003a767  jz      loc_18003A866
0x18003a76d  cmp     byte ptr [rax+19h], 2
0x18003a771  jb      loc_18003A866
0x18003a777  mov     edi, 400h
0x18003a77c  test    [rax+1Ch], edi
0x18003a77f  jz      loc_18003A866
0x18003a785  mov     edx, ebx
0x18003a787  lea     rcx, aMPxmlhelperExp; "m_pXmlHelper->Export failed with 0x%x"
0x18003a78e  call    WppDbgPrint
0x18003a793  mov     edx, 26h ; '&'
0x18003a798  jmp     loc_18003A844
0x18003a79d  mov     r8, rbp; unsigned __int16 *
0x18003a7a0  mov     rdx, rdi; unsigned __int16 *
0x18003a7a3  mov     rcx, r14; this
0x18003a7a6  call    ?ExportRegistry@IASExim@@AEAAJPEAG0@Z; IASExim::ExportRegistry(ushort *,ushort *)
0x18003a7ab  lea     rsi, WPP_GLOBAL_Control
0x18003a7b2  mov     ebx, eax
0x18003a7b4  mov     edi, 400h
0x18003a7b9  test    eax, eax
0x18003a7bb  jns     short loc_18003A809
0x18003a7bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a7c4  cmp     rcx, rsi
0x18003a7c7  jz      short loc_18003A809
0x18003a7c9  cmp     byte ptr [rcx+19h], 2
0x18003a7cd  jb      short loc_18003A809
0x18003a7cf  test    [rcx+1Ch], edi
0x18003a7d2  jz      short loc_18003A809
0x18003a7d4  mov     edx, eax
0x18003a7d6  lea     rcx, aExportregistry; "ExportRegistry failed with 0x%x"
0x18003a7dd  call    WppDbgPrint
0x18003a7e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a7e9  lea     r9, aNpssdo; "NPSSDO"
0x18003a7f0  mov     edx, 27h ; '''
0x18003a7f5  mov     [rsp+58h+var_38], ebx
0x18003a7f9  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003a800  mov     rcx, [rcx+10h]
0x18003a804  call    WPP_SF_sd
0x18003a809  mov     r8, rbp; unsigned __int16 *
0x18003a80c  mov     rcx, r14; this
0x18003a80f  call    ?ExportSystemInfo@IASExim@@AEAAJPEAG0@Z; IASExim::ExportSystemInfo(ushort *,ushort *)
0x18003a814  mov     ebx, eax
0x18003a816  test    eax, eax
0x18003a818  jns     short loc_18003A866
0x18003a81a  mov     rax, cs:WPP_GLOBAL_Control
0x18003a821  cmp     rax, rsi
0x18003a824  jz      short loc_18003A866
0x18003a826  cmp     byte ptr [rax+19h], 2
0x18003a82a  jb      short loc_18003A866
0x18003a82c  test    [rax+1Ch], edi
0x18003a82f  jz      short loc_18003A866
0x18003a831  mov     edx, ebx
0x18003a833  lea     rcx, aExportsystemin; "ExportSystemInfo failed with 0x%x"
0x18003a83a  call    WppDbgPrint
0x18003a83f  mov     edx, 28h ; '('
0x18003a844  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a84b  lea     r9, aNpssdo; "NPSSDO"
0x18003a852  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003a859  mov     [rsp+58h+var_38], ebx
0x18003a85d  mov     rcx, [rcx+10h]
0x18003a861  call    WPP_SF_sd
0x18003a866  mov     eax, ebx
0x18003a868  jmp     short loc_18003A86F
0x18003a86a  mov     eax, 80004003h
0x18003a86f  add     rsp, 30h
0x18003a873  pop     r14
0x18003a875  pop     rdi
0x18003a876  pop     rsi
0x18003a877  pop     rbp
0x18003a878  pop     rbx
0x18003a879  retn
```
