# CSpp::_RegQueryMinSizeForExtraMetadataFile(unsigned __int64 *)

- ea: `0x18001d97c`
- end: `0x18001daa1`
- name: `?_RegQueryMinSizeForExtraMetadataFile@CSpp@@AEAAJPEA_K@Z`
- size: `293`
- prototype: `__int64 __fastcall(CSpp *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ff4c`

## callees

- `0x18001d97c`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002e880`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001da76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001da76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001da13`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001da13`

## string_xrefs

- `0x18001da3f`: `MinSizeToCreateMetadataFile`

## pseudocode

```c
__int64 __fastcall CSpp::_RegQueryMinSizeForExtraMetadataFile(CSpp *this, unsigned __int64 *a2)
{
  __int64 v3; // r8
  int v4; // r9d
  int v5; // ebx
  __int16 v6; // ax
  char *v7; // rdx
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int16 v10; // [rsp+34h] [rbp-3Ch]
  __int16 v11; // [rsp+36h] [rbp-3Ah]
  int v12; // [rsp+38h] [rbp-38h]
  HKEY hKey; // [rsp+80h] [rbp+10h] BYREF
  unsigned __int64 v14; // [rsp+90h] [rbp+20h] BYREF

  hKey = (HKEY)this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "CSpp::_RegQueryMinSizeForExtraMetadataFile", 5209, 1);
  hKey = 0;
  v14 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SPP", 0, 0x20019u, &hKey) )
  {
    v5 = -2147467259;
    v6 = 5216;
    v9 = -2147467259;
LABEL_6:
    v11 = v6;
    v12 = 1;
    goto LABEL_9;
  }
  v5 = SxRegReadULONGLONG(hKey, L"MinSizeToCreateMetadataFile", &v14, v4);
  v9 = v5;
  v6 = 5220;
  if ( v5 < 0 )
    goto LABEL_6;
  v10 = 5220;
  *a2 = v14 << 20;
LABEL_9:
  v7 = (char *)hKey - 1;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9, (__int64)v7, v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001d97c  mov     [rsp-8+arg_8], rbx
0x18001d981  mov     [rsp-8+arg_18], rdi
0x18001d986  mov     [rsp-8+hKey], rcx
0x18001d98b  push    rbp
0x18001d98c  mov     rbp, rsp
0x18001d98f  sub     rsp, 70h
0x18001d993  mov     rdi, rdx
0x18001d996  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d99d  lea     rax, WPP_GLOBAL_Control
0x18001d9a4  cmp     rcx, rax
0x18001d9a7  jz      short loc_18001D9C7
0x18001d9a9  test    dword ptr [rcx+1Ch], 20000000h
0x18001d9b0  jz      short loc_18001D9C7
0x18001d9b2  mov     rcx, [rcx+10h]
0x18001d9b6  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001d9bd  mov     edx, 51h ; 'Q'
0x18001d9c2  call    WPP_SF_
0x18001d9c7  mov     r9d, 1; unsigned __int16
0x18001d9cd  lea     rdx, aCsppRegquerymi; "CSpp::_RegQueryMinSizeForExtraMetadataF"...
0x18001d9d4  mov     r8d, 1459h; unsigned __int16
0x18001d9da  lea     rcx, [rbp+var_40]; this
0x18001d9de  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001d9e3  lea     rax, [rbp+hKey]
0x18001d9e7  mov     [rbp+hKey], 0
0x18001d9ef  mov     r9d, 20019h; samDesired
0x18001d9f5  mov     [rsp+70h+phkResult], rax; phkResult
0x18001d9fa  xor     r8d, r8d; ulOptions
0x18001d9fd  mov     [rbp+arg_10], 0
0x18001da05  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001da0c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001da13  call    cs:__imp_RegOpenKeyExW
0x18001da19  test    eax, eax
0x18001da1b  jz      short loc_18001DA37
0x18001da1d  mov     ebx, 80004005h
0x18001da22  mov     eax, 1460h
0x18001da27  mov     [rbp+var_40], ebx
0x18001da2a  mov     [rbp+var_3A], ax
0x18001da2e  mov     [rbp+var_38], 1
0x18001da35  jmp     short loc_18001DA68
0x18001da37  mov     rcx, [rbp+hKey]; hKey
0x18001da3b  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x18001da3f  lea     rdx, aMinsizetocreat; "MinSizeToCreateMetadataFile"
0x18001da46  call    ?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z; SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)
0x18001da4b  mov     ebx, eax
0x18001da4d  mov     [rbp+var_40], eax
0x18001da50  test    eax, eax
0x18001da52  mov     eax, 1464h
0x18001da57  js      short loc_18001DA2A
0x18001da59  mov     [rbp+var_3C], ax
0x18001da5d  mov     rax, [rbp+arg_10]
0x18001da61  shl     rax, 14h
0x18001da65  mov     [rdi], rax
0x18001da68  mov     rcx, [rbp+hKey]; hKey
0x18001da6c  lea     rdx, [rcx-1]
0x18001da70  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001da74  ja      short loc_18001DA84
0x18001da76  call    cs:__imp_RegCloseKey
0x18001da7c  mov     [rbp+hKey], 0
0x18001da84  lea     rcx, [rbp+var_40]; this
0x18001da88  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001da8d  lea     r11, [rsp+70h+var_s0]
0x18001da92  mov     eax, ebx
0x18001da94  mov     rbx, [r11+18h]
0x18001da98  mov     rdi, [r11+28h]
0x18001da9c  mov     rsp, r11
0x18001da9f  pop     rbp
0x18001daa0  retn
```
