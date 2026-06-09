# HrHttpInitialize(void)

- ea: `0x18001363c`
- end: `0x18001375c`
- name: `?HrHttpInitialize@@YAJXZ`
- size: `288`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800134e4`

## callees

- `0x18001363c`
- `0x180013818`
- `0x180014580`
- `0x1800200f4`
- `0x18003c018`
- `0x180052310`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800136bd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800136bd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013692`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013692`

## string_xrefs

- `0x180013689`: `upnphost.dll.mui`

## pseudocode

```c
__int64 HrHttpInitialize(void)
{
  int IsapiExtensionDirectory; // ebx
  CGlobalVariables *v1; // rax
  CGlobalVariables *v2; // rax
  CHAR *v3; // rcx

  IsapiExtensionDirectory = HrMakeIsapiExtensionDirectory();
  if ( IsapiExtensionDirectory < 0 )
    goto LABEL_14;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids);
  g_hInst = LoadLibraryExW(L"upnphost.dll.mui", 0, 0);
  if ( !g_hInst )
    g_hInst = qword_180075D50;
  v1 = (CGlobalVariables *)malloc(0x68u);
  if ( v1 )
  {
    v2 = CGlobalVariables::CGlobalVariables(v1);
    g_pVars = v2;
    if ( v2 && *((_QWORD *)v2 + 2) && *((_QWORD *)v2 + 11) && *(_QWORD *)v2 )
    {
      v3 = (CHAR *)*((_QWORD *)v2 + 10);
      if ( v3 )
        IsapiExtensionDirectory = InitializeResponseCodes(v3);
LABEL_14:
      if ( !IsapiExtensionDirectory )
        return (unsigned int)IsapiExtensionDirectory;
      goto LABEL_15;
    }
  }
  else
  {
    g_pVars = 0;
  }
  IsapiExtensionDirectory = -2147467259;
LABEL_15:
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids,
      (unsigned int)"HrHttpInitialize",
      IsapiExtensionDirectory);
  return (unsigned int)IsapiExtensionDirectory;
}

```

## disassembly

```asm
0x18001363c  mov     [rsp+arg_0], rbx
0x180013641  push    rsi
0x180013642  sub     rsp, 30h
0x180013646  call    ?HrMakeIsapiExtensionDirectory@@YAJXZ; HrMakeIsapiExtensionDirectory(void)
0x18001364b  lea     rsi, WPP_GLOBAL_Control
0x180013652  mov     ebx, eax
0x180013654  test    eax, eax
0x180013656  js      loc_180013706
0x18001365c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013663  cmp     rcx, rsi
0x180013666  jz      short loc_180013686
0x180013668  test    dword ptr [rcx+1Ch], 1000h
0x18001366f  jz      short loc_180013686
0x180013671  mov     rcx, [rcx+10h]
0x180013675  lea     r8, WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids
0x18001367c  mov     edx, 0Ah
0x180013681  call    WPP_SF_
0x180013686  xor     r8d, r8d; dwFlags
0x180013689  lea     rcx, LibFileName; "upnphost.dll.mui"
0x180013690  xor     edx, edx; hFile
0x180013692  call    cs:__imp_LoadLibraryExW
0x180013699  nop     dword ptr [rax+rax+00h]
0x18001369e  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInst
0x1800136a5  test    rax, rax
0x1800136a8  jnz     short loc_1800136B8
0x1800136aa  mov     rax, cs:qword_180075D50
0x1800136b1  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInst
0x1800136b8  mov     ecx, 68h ; 'h'; Size
0x1800136bd  call    cs:__imp_malloc
0x1800136c4  nop     dword ptr [rax+rax+00h]
0x1800136c9  test    rax, rax
0x1800136cc  jz      short loc_18001374A
0x1800136ce  mov     rcx, rax; this
0x1800136d1  call    ??0CGlobalVariables@@QEAA@XZ; CGlobalVariables::CGlobalVariables(void)
0x1800136d6  mov     cs:?g_pVars@@3PEAVCGlobalVariables@@EA, rax; CGlobalVariables * g_pVars
0x1800136dd  test    rax, rax
0x1800136e0  jz      short loc_180013755
0x1800136e2  cmp     qword ptr [rax+10h], 0
0x1800136e7  jz      short loc_180013755
0x1800136e9  cmp     qword ptr [rax+58h], 0
0x1800136ee  jz      short loc_180013755
0x1800136f0  cmp     qword ptr [rax], 0
0x1800136f4  jz      short loc_180013755
0x1800136f6  mov     rcx, [rax+50h]; lpMultiByteStr
0x1800136fa  test    rcx, rcx
0x1800136fd  jz      short loc_180013706
0x1800136ff  call    ?InitializeResponseCodes@@YAJPEAD@Z; InitializeResponseCodes(char *)
0x180013704  mov     ebx, eax
0x180013706  test    ebx, ebx
0x180013708  jz      short loc_18001373C
0x18001370a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013711  cmp     rcx, rsi
0x180013714  jz      short loc_18001373C
0x180013716  test    byte ptr [rcx+1Ch], 1
0x18001371a  jz      short loc_18001373C
0x18001371c  mov     rcx, [rcx+10h]
0x180013720  lea     r9, aHrhttpinitiali; "HrHttpInitialize"
0x180013727  mov     edx, 0Bh
0x18001372c  mov     [rsp+38h+var_18], ebx
0x180013730  lea     r8, WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids
0x180013737  call    WPP_SF_sd
0x18001373c  mov     eax, ebx
0x18001373e  mov     rbx, [rsp+38h+arg_0]
0x180013743  add     rsp, 30h
0x180013747  pop     rsi
0x180013748  retn
0x18001374a  mov     cs:?g_pVars@@3PEAVCGlobalVariables@@EA, 0; CGlobalVariables * g_pVars
0x180013755  mov     ebx, 80004005h
0x18001375a  jmp     short loc_18001370A
```
