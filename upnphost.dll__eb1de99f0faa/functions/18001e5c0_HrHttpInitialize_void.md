# HrHttpInitialize(void)

- ea: `0x18001e5c0`
- end: `0x18001e6d3`
- name: `?HrHttpInitialize@@YAJXZ`
- size: `275`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001e478`

## callees

- `0x18000db4c`
- `0x18001e5c0`
- `0x18001e790`
- `0x18001f41c`
- `0x180039a84`
- `0x18004ed9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001e63b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001e63b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e616`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e616`

## string_xrefs

- `0x18001e60d`: `upnphost.dll.mui`

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
    g_hInst = qword_180071C60;
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
0x18001e5c0  mov     [rsp+arg_0], rbx
0x18001e5c5  push    rsi
0x18001e5c6  sub     rsp, 30h
0x18001e5ca  call    ?HrMakeIsapiExtensionDirectory@@YAJXZ; HrMakeIsapiExtensionDirectory(void)
0x18001e5cf  lea     rsi, WPP_GLOBAL_Control
0x18001e5d6  mov     ebx, eax
0x18001e5d8  test    eax, eax
0x18001e5da  js      loc_18001E67E
0x18001e5e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5e7  cmp     rcx, rsi
0x18001e5ea  jz      short loc_18001E60A
0x18001e5ec  test    dword ptr [rcx+1Ch], 1000h
0x18001e5f3  jz      short loc_18001E60A
0x18001e5f5  mov     rcx, [rcx+10h]
0x18001e5f9  lea     r8, WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids
0x18001e600  mov     edx, 0Ah
0x18001e605  call    WPP_SF_
0x18001e60a  xor     r8d, r8d; dwFlags
0x18001e60d  lea     rcx, LibFileName; "upnphost.dll.mui"
0x18001e614  xor     edx, edx; hFile
0x18001e616  call    cs:__imp_LoadLibraryExW
0x18001e61c  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInst
0x18001e623  test    rax, rax
0x18001e626  jnz     short loc_18001E636
0x18001e628  mov     rax, cs:qword_180071C60
0x18001e62f  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInst
0x18001e636  mov     ecx, 68h ; 'h'; Size
0x18001e63b  call    cs:__imp_malloc
0x18001e641  test    rax, rax
0x18001e644  jz      short loc_18001E6C1
0x18001e646  mov     rcx, rax; this
0x18001e649  call    ??0CGlobalVariables@@QEAA@XZ; CGlobalVariables::CGlobalVariables(void)
0x18001e64e  mov     cs:?g_pVars@@3PEAVCGlobalVariables@@EA, rax; CGlobalVariables * g_pVars
0x18001e655  test    rax, rax
0x18001e658  jz      short loc_18001E6CC
0x18001e65a  cmp     qword ptr [rax+10h], 0
0x18001e65f  jz      short loc_18001E6CC
0x18001e661  cmp     qword ptr [rax+58h], 0
0x18001e666  jz      short loc_18001E6CC
0x18001e668  cmp     qword ptr [rax], 0
0x18001e66c  jz      short loc_18001E6CC
0x18001e66e  mov     rcx, [rax+50h]; lpMultiByteStr
0x18001e672  test    rcx, rcx
0x18001e675  jz      short loc_18001E67E
0x18001e677  call    ?InitializeResponseCodes@@YAJPEAD@Z; InitializeResponseCodes(char *)
0x18001e67c  mov     ebx, eax
0x18001e67e  test    ebx, ebx
0x18001e680  jz      short loc_18001E6B4
0x18001e682  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e689  cmp     rcx, rsi
0x18001e68c  jz      short loc_18001E6B4
0x18001e68e  test    byte ptr [rcx+1Ch], 1
0x18001e692  jz      short loc_18001E6B4
0x18001e694  mov     rcx, [rcx+10h]
0x18001e698  lea     r9, aHrhttpinitiali; "HrHttpInitialize"
0x18001e69f  mov     edx, 0Bh
0x18001e6a4  mov     [rsp+38h+var_18], ebx
0x18001e6a8  lea     r8, WPP_c07af9e9c7303a7e70c80d836769dc05_Traceguids
0x18001e6af  call    WPP_SF_sd
0x18001e6b4  mov     eax, ebx
0x18001e6b6  mov     rbx, [rsp+38h+arg_0]
0x18001e6bb  add     rsp, 30h
0x18001e6bf  pop     rsi
0x18001e6c0  retn
0x18001e6c1  mov     cs:?g_pVars@@3PEAVCGlobalVariables@@EA, 0; CGlobalVariables * g_pVars
0x18001e6cc  mov     ebx, 80004005h
0x18001e6d1  jmp     short loc_18001E682
```
