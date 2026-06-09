# sub_1800FB5BC

- ea: `0x1800fb5bc`
- end: `0x1800fb7d6`
- name: `sub_1800FB5BC`
- size: `538`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180059c3c`
- `0x18005cdb8`

## callees

- `0x18003f7c0`
- `0x180061aec`
- `0x1800fb5bc`
- `0x18012e61c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800fb6d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800fb6d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fb78b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fb78b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fb769`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fb769`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fb733`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fb733`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x1800fb6ab`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x1800fb6ab`

## pseudocode

```c
__int64 __fastcall sub_1800FB5BC(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // rdi
  unsigned int v5; // ebx
  const WCHAR *v6; // rcx
  __int64 v7; // rdx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t ValueName[20]; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v14[7]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Filename[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR SubKey[320]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v4 = a4;
  v14[0] = xmmword_180189B30;
  v14[1] = xmmword_180189B40;
  v14[2] = xmmword_180189B50;
  v14[3] = xmmword_180189B60;
  v14[4] = xmmword_180189B70;
  v14[5] = xmmword_180189B80;
  hKey = 0;
  v14[6] = xmmword_180189B90;
  cbData = 4;
  wcscpy(ValueName, L"OpnFlags1");
  Type = 0;
  *(_DWORD *)Data = 0;
  if ( (a4 & dword_1801A50A8) != 0 )
  {
    v5 = (a4 & dword_1801A50AC) != 0;
    goto LABEL_14;
  }
  v5 = 1;
  if ( (a4 & 1) != 0 )
  {
    v6 = L"UseStreamingProxyForNSCFileDownload";
    goto LABEL_7;
  }
  if ( (a4 & 2) != 0 )
  {
    v6 = L"ExcludeProxyCheckForProgressiveDownload";
LABEL_7:
    if ( FindAtomW(v6) )
      goto LABEL_14;
  }
  v5 = 0;
  if ( GetModuleFileNameW(0, Filename, 0x105u) )
  {
    sub_18012E61C(v4, a2, v7, Filename);
    sub_180061AEC(v4, a2, 317, SubKey, L"%s\\%s", v14);
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
    {
      if ( !RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) && Type == 4 )
        v5 = v4 & *(_DWORD *)Data;
      RegCloseKey(hKey);
    }
  }
LABEL_14:
  if ( ((unsigned int)v4 & dword_1801A50A8) == 0 )
  {
    dword_1801A50A8 |= v4;
    if ( v5 )
      dword_1801A50AC |= v4;
  }
  return v5;
}

```

## disassembly

```asm
0x1800fb5bc  mov     [rsp-8+arg_0], rbx
0x1800fb5c1  mov     [rsp-8+arg_8], rdi
0x1800fb5c6  push    rbp
0x1800fb5c7  lea     rbp, [rsp-480h]
0x1800fb5cf  sub     rsp, 580h
0x1800fb5d6  mov     rax, cs:__security_cookie
0x1800fb5dd  xor     rax, rsp
0x1800fb5e0  mov     [rbp+480h+var_10], rax
0x1800fb5e7  test    cs:dword_1801A50A8, ecx
0x1800fb5ed  mov     edi, ecx; StackCookie
0x1800fb5ef  movaps  xmm0, cs:xmmword_180189B30
0x1800fb5f6  movaps  xmm1, cs:xmmword_180189B40
0x1800fb5fd  movaps  [rsp+580h+var_510], xmm0
0x1800fb602  movaps  xmm0, cs:xmmword_180189B50
0x1800fb609  movaps  [rbp+480h+var_500], xmm1
0x1800fb60d  movaps  xmm1, cs:xmmword_180189B60
0x1800fb614  movaps  [rbp+480h+var_4F0], xmm0
0x1800fb618  movaps  xmm0, cs:xmmword_180189B70
0x1800fb61f  movaps  [rbp+480h+var_4E0], xmm1
0x1800fb623  movaps  xmm1, cs:xmmword_180189B80
0x1800fb62a  movaps  [rbp+480h+var_4D0], xmm0
0x1800fb62e  movaps  xmm0, cs:xmmword_180189B90
0x1800fb635  movaps  [rbp+480h+var_4C0], xmm1
0x1800fb639  movups  xmm1, cs:xmmword_180189B08
0x1800fb640  mov     [rsp+580h+hKey], 0
0x1800fb649  movaps  [rbp+480h+var_4B0], xmm0
0x1800fb64d  movups  xmm0, cs:xmmword_180189B08+0Ah
0x1800fb654  mov     [rsp+580h+cbData], 4
0x1800fb65c  movups  xmmword ptr [rsp+580h+ValueName], xmm1
0x1800fb661  mov     [rsp+580h+Type], 0
0x1800fb669  movups  xmmword ptr [rsp+580h+ValueName+0Ah], xmm0
0x1800fb66e  mov     dword ptr [rsp+580h+Data], 0
0x1800fb676  jz      short loc_1800FB68B
0x1800fb678  test    cs:dword_1801A50AC, ecx
0x1800fb67e  mov     ebx, 0
0x1800fb683  setnz   bl
0x1800fb686  jmp     loc_1800FB797
0x1800fb68b  mov     ebx, 1
0x1800fb690  test    bl, dil
0x1800fb693  jz      short loc_1800FB69E
0x1800fb695  lea     rcx, aUsestreamingpr; "UseStreamingProxyForNSCFileDownload"
0x1800fb69c  jmp     short loc_1800FB6AB
0x1800fb69e  test    dil, 2
0x1800fb6a2  jz      short loc_1800FB6C5
0x1800fb6a4  lea     rcx, String; "ExcludeProxyCheckForProgressiveDownload"
0x1800fb6ab  call    cs:FindAtomW
0x1800fb6b2  nop     dword ptr [rax+rax+00h]
0x1800fb6b7  movzx   ecx, ax
0x1800fb6ba  xor     eax, eax
0x1800fb6bc  cmp     ax, cx
0x1800fb6bf  jnz     loc_1800FB797
0x1800fb6c5  mov     r8d, 105h; nSize
0x1800fb6cb  lea     rdx, [rbp+480h+Filename]; lpFilename
0x1800fb6cf  xor     ecx, ecx; hModule
0x1800fb6d1  xor     ebx, ebx
0x1800fb6d3  call    cs:GetModuleFileNameW
0x1800fb6da  nop     dword ptr [rax+rax+00h]
0x1800fb6df  test    eax, eax
0x1800fb6e1  jz      loc_1800FB797
0x1800fb6e7  lea     rcx, [rbp+480h+Filename]
0x1800fb6eb  call    sub_18012E61C
0x1800fb6f0  lea     r9, [rsp+580h+var_510]
0x1800fb6f5  mov     [rsp+580h+phkResult], rax
0x1800fb6fa  lea     r8, aSS; "%s\\%s"
0x1800fb701  mov     edx, 13Dh
0x1800fb706  lea     rcx, [rbp+480h+SubKey]
0x1800fb70d  call    sub_180061AEC
0x1800fb712  lea     rax, [rsp+580h+hKey]
0x1800fb717  mov     r9d, 20019h; samDesired
0x1800fb71d  xor     r8d, r8d; ulOptions
0x1800fb720  mov     [rsp+580h+phkResult], rax; phkResult
0x1800fb725  lea     rdx, [rbp+480h+SubKey]; lpSubKey
0x1800fb72c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800fb733  call    cs:RegOpenKeyExW
0x1800fb73a  nop     dword ptr [rax+rax+00h]
0x1800fb73f  test    eax, eax
0x1800fb741  jnz     short loc_1800FB797
0x1800fb743  mov     rcx, [rsp+580h+hKey]; hKey
0x1800fb748  lea     rax, [rsp+580h+cbData]
0x1800fb74d  mov     [rsp+580h+lpcbData], rax; lpcbData
0x1800fb752  lea     r9, [rsp+580h+Type]; lpType
0x1800fb757  lea     rax, [rsp+580h+Data]
0x1800fb75c  xor     r8d, r8d; lpReserved
0x1800fb75f  lea     rdx, [rsp+580h+ValueName]; lpValueName
0x1800fb764  mov     [rsp+580h+phkResult], rax; lpData
0x1800fb769  call    cs:RegQueryValueExW
0x1800fb770  nop     dword ptr [rax+rax+00h]
0x1800fb775  test    eax, eax
0x1800fb777  jnz     short loc_1800FB786
0x1800fb779  cmp     [rsp+580h+Type], 4
0x1800fb77e  jnz     short loc_1800FB786
0x1800fb780  mov     ebx, dword ptr [rsp+580h+Data]
0x1800fb784  and     ebx, edi
0x1800fb786  mov     rcx, [rsp+580h+hKey]; hKey
0x1800fb78b  call    cs:RegCloseKey
0x1800fb792  nop     dword ptr [rax+rax+00h]
0x1800fb797  test    cs:dword_1801A50A8, edi
0x1800fb79d  jnz     short loc_1800FB7AF
0x1800fb79f  or      cs:dword_1801A50A8, edi
0x1800fb7a5  test    ebx, ebx
0x1800fb7a7  jz      short loc_1800FB7AF
0x1800fb7a9  or      cs:dword_1801A50AC, edi
0x1800fb7af  mov     eax, ebx
0x1800fb7b1  mov     rcx, [rbp+480h+var_10]
0x1800fb7b8  xor     rcx, rsp
0x1800fb7bb  call    __security_check_cookie
0x1800fb7c0  lea     r11, [rsp+580h+var_s0]
0x1800fb7c8  mov     rbx, [r11+10h]
0x1800fb7cc  mov     rdi, [r11+18h]
0x1800fb7d0  mov     rsp, r11
0x1800fb7d3  pop     rbp
0x1800fb7d4  retn
```
