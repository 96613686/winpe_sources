# CResourceLoader::LoadModule(ushort const *,HINSTANCE__ * *)

- ea: `0x180012070`
- end: `0x1800122b2`
- name: `?LoadModule@CResourceLoader@@AEAAJPEBGPEAPEAUHINSTANCE__@@@Z`
- size: `578`
- prototype: `__int64 __fastcall(CResourceLoader *this, const unsigned __int16 *, HINSTANCE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011d2c`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180002ac4`
- `0x180012070`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180012123`
- `msvcrt!_wcsicmp` at `0x180012123`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800121c4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800121c4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012161`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012161`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012189`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012189`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800121dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800121dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012177`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800121cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012177`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800121cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001222d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001222d`

## string_xrefs

- `0x18001209d`: `ResourcePath`

## pseudocode

```c
__int64 __fastcall CResourceLoader::LoadModule(CResourceLoader *this, const unsigned __int16 *a2, HINSTANCE *a3)
{
  signed int v6; // ebx
  HMODULE Library; // rbp
  CResourceLoader **v8; // rdi
  CResourceLoader *v9; // rbx
  CResourceLoader *v10; // rdi
  HANDLE ProcessHeap; // rax
  LPVOID v12; // rax
  HANDLE v13; // rax
  CResourceLoader *v15; // rax
  signed int LastError; // eax

  if ( !a2 )
  {
    v6 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        (unsigned int)"CResourceLoader::LoadModule",
        -2147024809,
        (__int64)"ResourcePath");
    return (unsigned int)v6;
  }
  if ( !a3 )
  {
    Library = 0;
    v6 = -2147024809;
    v8 = 0;
LABEL_6:
    if ( a3 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        McTemplateU0sq_EventWriteTransfer(this, a2, "CResourceLoader::LoadModule", 2147942487LL);
    }
    else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      McTemplateU0sqs_EventWriteTransfer(
        (_DWORD)this,
        (_DWORD)a2,
        (unsigned int)"CResourceLoader::LoadModule",
        -2147024809,
        (__int64)"Module");
    }
    goto LABEL_21;
  }
  v9 = *(CResourceLoader **)this;
  *a3 = 0;
  while ( v9 != this )
  {
    v10 = v9;
    v9 = *(CResourceLoader **)v9;
    if ( !_wcsicmp(a2, *((const wchar_t **)v10 + 2)) )
    {
      v6 = 0;
      *a3 = (HINSTANCE)*((_QWORD *)v10 + 3);
      goto LABEL_13;
    }
  }
  Library = LoadLibraryExW(a2, 0, 2u);
  if ( (unsigned __int64)Library - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v8 = 0;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
    {
      v6 = -2147467259;
LABEL_37:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        McTemplateU0sq_EventWriteTransfer(this, a2, "CResourceLoader::LoadModule", (unsigned int)v6);
      goto LABEL_20;
    }
    goto LABEL_34;
  }
  ProcessHeap = GetProcessHeap();
  v12 = HeapAlloc(ProcessHeap, 8u, 0x20u);
  v8 = (CResourceLoader **)v12;
  if ( v12 )
  {
    *((_QWORD *)v12 + 3) = Library;
    v6 = SDiagPrviCopyPWSTR(a2, (unsigned __int16 **)v12 + 2);
    if ( v6 >= 0 )
    {
      v15 = *(CResourceLoader **)this;
      if ( *(CResourceLoader **)(*(_QWORD *)this + 8LL) != this )
        __fastfail(3u);
      *v8 = v15;
      v8[1] = this;
      *((_QWORD *)v15 + 1) = v8;
      *(_QWORD *)this = v8;
      *a3 = Library;
LABEL_36:
      if ( !v6 )
      {
LABEL_13:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
          McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CResourceLoader::LoadModule");
        return (unsigned int)v6;
      }
      goto LABEL_37;
    }
LABEL_34:
    if ( v6 == -2147024882 )
      goto LABEL_18;
    if ( v6 == -2147024809 )
      goto LABEL_6;
    goto LABEL_36;
  }
  v6 = -2147024882;
LABEL_18:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
    goto LABEL_21;
  McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY, "CResourceLoader::LoadModule");
LABEL_20:
  if ( v6 >= 0 )
    return (unsigned int)v6;
LABEL_21:
  if ( Library )
    FreeLibrary(Library);
  if ( v8 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012070  push    rbx
0x180012072  push    rbp
0x180012073  push    rsi
0x180012074  push    rdi
0x180012075  push    r14
0x180012077  push    r15
0x180012079  sub     rsp, 38h
0x18001207d  mov     r14, r8
0x180012080  mov     r15, rdx
0x180012083  mov     rsi, rcx
0x180012086  test    rdx, rdx
0x180012089  jnz     short loc_1800120C0
0x18001208b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180012092  mov     ebx, 80070057h
0x180012097  jz      loc_1800121E3
0x18001209d  lea     rax, aResourcepath; "ResourcePath"
0x1800120a4  mov     r9d, 80070057h
0x1800120aa  lea     r8, aCresourceloade_0; "CResourceLoader::LoadModule"
0x1800120b1  mov     [rsp+68h+var_48], rax
0x1800120b6  call    McTemplateU0sqs_EventWriteTransfer
0x1800120bb  jmp     loc_1800121E3
0x1800120c0  test    r14, r14
0x1800120c3  jnz     short loc_180012107
0x1800120c5  xor     ebp, ebp
0x1800120c7  mov     ebx, 80070057h
0x1800120cc  xor     edi, edi
0x1800120ce  test    r14, r14
0x1800120d1  jnz     loc_18001228E
0x1800120d7  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800120de  jz      loc_1800121BC
0x1800120e4  lea     rax, aModule; "Module"
0x1800120eb  mov     r9d, 80070057h
0x1800120f1  lea     r8, aCresourceloade_0; "CResourceLoader::LoadModule"
0x1800120f8  mov     [rsp+68h+var_48], rax
0x1800120fd  call    McTemplateU0sqs_EventWriteTransfer
0x180012102  jmp     loc_1800121BC
0x180012107  mov     rbx, [rcx]
0x18001210a  mov     qword ptr [r8], 0
0x180012111  mov     rcx, r15; lpLibFileName
0x180012114  cmp     rbx, rsi
0x180012117  jz      short loc_18001215B
0x180012119  mov     rdi, rbx
0x18001211c  mov     rbx, [rbx]
0x18001211f  mov     rdx, [rdi+10h]; String2
0x180012123  call    cs:__imp__wcsicmp
0x180012129  test    eax, eax
0x18001212b  jnz     short loc_180012111
0x18001212d  mov     rax, [rdi+18h]
0x180012131  xor     ebx, ebx
0x180012133  mov     [r14], rax
0x180012136  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18001213d  jz      loc_1800121E3
0x180012143  lea     r8, aCresourceloade_0; "CResourceLoader::LoadModule"
0x18001214a  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180012151  call    McTemplateU0s_EventWriteTransfer
0x180012156  jmp     loc_1800121E3
0x18001215b  xor     edx, edx; hFile
0x18001215d  lea     r8d, [rdx+2]; dwFlags
0x180012161  call    cs:__imp_LoadLibraryExW
0x180012167  mov     rbp, rax
0x18001216a  dec     rax
0x18001216d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012171  ja      loc_18001222B
0x180012177  call    cs:__imp_GetProcessHeap
0x18001217d  mov     edx, 8; dwFlags
0x180012182  mov     rcx, rax; hHeap
0x180012185  lea     r8d, [rdx+18h]; dwBytes
0x180012189  call    cs:__imp_HeapAlloc
0x18001218f  mov     rdi, rax
0x180012192  test    rax, rax
0x180012195  jnz     short loc_1800121F2
0x180012197  mov     ebx, 8007000Eh
0x18001219c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800121a3  jz      short loc_1800121BC
0x1800121a5  lea     r8, aCresourceloade_0; "CResourceLoader::LoadModule"
0x1800121ac  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x1800121b3  call    McTemplateU0s_EventWriteTransfer
0x1800121b8  test    ebx, ebx
0x1800121ba  jns     short loc_1800121E3
0x1800121bc  test    rbp, rbp
0x1800121bf  jz      short loc_1800121CA
0x1800121c1  mov     rcx, rbp; hLibModule
0x1800121c4  call    cs:__imp_FreeLibrary
0x1800121ca  test    rdi, rdi
0x1800121cd  jz      short loc_1800121E3
0x1800121cf  call    cs:__imp_GetProcessHeap
0x1800121d5  mov     r8, rdi; lpMem
0x1800121d8  xor     edx, edx; dwFlags
0x1800121da  mov     rcx, rax; hHeap
0x1800121dd  call    cs:__imp_HeapFree
0x1800121e3  mov     eax, ebx
0x1800121e5  add     rsp, 38h
0x1800121e9  pop     r15
0x1800121eb  pop     r14
0x1800121ed  pop     rdi
0x1800121ee  pop     rsi
0x1800121ef  pop     rbp
0x1800121f0  pop     rbx
0x1800121f1  retn
0x1800121f2  lea     rdx, [rax+10h]; unsigned __int16 **
0x1800121f6  mov     [rax+18h], rbp
0x1800121fa  mov     rcx, r15; unsigned __int16 *
0x1800121fd  call    ?SDiagPrviCopyPWSTR@@YAJPEBGPEAPEAG@Z; SDiagPrviCopyPWSTR(ushort const *,ushort * *)
0x180012202  mov     ebx, eax
0x180012204  test    eax, eax
0x180012206  js      short loc_18001224D
0x180012208  mov     rax, [rsi]
0x18001220b  cmp     [rax+8], rsi
0x18001220f  jz      short loc_180012218
0x180012211  mov     ecx, 3
0x180012216  int     29h; Win8: RtlFailFast(ecx)
0x180012218  mov     [rdi], rax
0x18001221b  mov     [rdi+8], rsi
0x18001221f  mov     [rax+8], rdi
0x180012223  mov     [rsi], rdi
0x180012226  mov     [r14], rbp
0x180012229  jmp     short loc_180012265
0x18001222b  xor     edi, edi
0x18001222d  call    cs:__imp_GetLastError
0x180012233  mov     ebx, eax
0x180012235  test    eax, eax
0x180012237  jle     short loc_180012242
0x180012239  movzx   ebx, ax
0x18001223c  or      ebx, 80070000h
0x180012242  test    ebx, ebx
0x180012244  js      short loc_18001224D
0x180012246  mov     ebx, 80004005h
0x18001224b  jmp     short loc_18001226D
0x18001224d  cmp     ebx, 8007000Eh
0x180012253  jz      loc_18001219C
0x180012259  cmp     ebx, 80070057h
0x18001225f  jz      loc_1800120CE
0x180012265  test    ebx, ebx
0x180012267  jz      loc_180012136
0x18001226d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180012274  jz      loc_1800121B8
0x18001227a  mov     r9d, ebx
0x18001227d  lea     r8, aCresourceloade_0; "CResourceLoader::LoadModule"
0x180012284  call    McTemplateU0sq_EventWriteTransfer
0x180012289  jmp     loc_1800121B8
0x18001228e  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180012295  jz      loc_1800121BC
0x18001229b  mov     r9d, 80070057h
0x1800122a1  lea     r8, aCresourceloade_0; "CResourceLoader::LoadModule"
0x1800122a8  call    McTemplateU0sq_EventWriteTransfer
0x1800122ad  jmp     loc_1800121BC
```
