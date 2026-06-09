# CResourceLoader::CreateInstance(CResourceLoader * *)

- ea: `0x180011c80`
- end: `0x180011d23`
- name: `?CreateInstance@CResourceLoader@@SAJPEAPEAV1@@Z`
- size: `163`
- prototype: `__int64 __fastcall(struct CResourceLoader **, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800087e0`

## callees

- `0x180001074`
- `0x1800024d4`
- `0x1800025ec`
- `0x180011c80`

## string_xrefs

- `0x180011caf`: `CResourceLoader::CreateInstance`
- `0x180011d0a`: `CResourceLoader::CreateInstance`

## pseudocode

```c
__int64 __fastcall CResourceLoader::CreateInstance(struct CResourceLoader **a1, int a2)
{
  unsigned int v2; // ebx
  struct CResourceLoader *v4; // rax
  __int64 v5; // rcx
  __int64 *v6; // rdx

  v2 = 0;
  if ( a1 )
  {
    *a1 = 0;
    v4 = (struct CResourceLoader *)operator new(0x10u);
    if ( v4 )
    {
      *((_QWORD *)v4 + 1) = v4;
      *(_QWORD *)v4 = v4;
      *a1 = v4;
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
    McTemplateU0s_EventWriteTransfer(v5, v6, "CResourceLoader::CreateInstance");
    return v2;
  }
  v2 = -2147024809;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sqs_EventWriteTransfer(
      0,
      a2,
      (unsigned int)"CResourceLoader::CreateInstance",
      -2147024809,
      (__int64)"ResourceLoader");
  return v2;
}

```

## disassembly

```asm
0x180011c80  mov     [rsp+arg_8], rbx
0x180011c85  push    rdi
0x180011c86  sub     rsp, 30h
0x180011c8a  xor     ebx, ebx
0x180011c8c  mov     rdi, rcx
0x180011c8f  test    rcx, rcx
0x180011c92  jnz     short loc_180011CC2
0x180011c94  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180011c9b  mov     ebx, 80070057h
0x180011ca0  jz      short loc_180011D16
0x180011ca2  lea     rax, aResourceloader; "ResourceLoader"
0x180011ca9  mov     r9d, 80070057h
0x180011caf  lea     r8, aCresourceloade; "CResourceLoader::CreateInstance"
0x180011cb6  mov     [rsp+38h+var_18], rax
0x180011cbb  call    McTemplateU0sqs_EventWriteTransfer
0x180011cc0  jmp     short loc_180011D16
0x180011cc2  mov     [rcx], rbx
0x180011cc5  mov     ecx, 10h; Size
0x180011cca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011ccf  mov     [rsp+38h+arg_0], rax
0x180011cd4  test    rax, rax
0x180011cd7  jz      short loc_180011CF5
0x180011cd9  mov     [rax+8], rax
0x180011cdd  mov     [rax], rax
0x180011ce0  mov     [rdi], rax
0x180011ce3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180011cea  jz      short loc_180011D16
0x180011cec  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180011cf3  jmp     short loc_180011D0A
0x180011cf5  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180011cfc  mov     ebx, 8007000Eh
0x180011d01  jz      short loc_180011D16
0x180011d03  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180011d0a  lea     r8, aCresourceloade; "CResourceLoader::CreateInstance"
0x180011d11  call    McTemplateU0s_EventWriteTransfer
0x180011d16  mov     eax, ebx
0x180011d18  mov     rbx, [rsp+38h+arg_8]
0x180011d1d  add     rsp, 30h
0x180011d21  pop     rdi
0x180011d22  retn
```
