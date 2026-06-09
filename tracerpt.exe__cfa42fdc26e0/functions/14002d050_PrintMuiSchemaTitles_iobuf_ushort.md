# PrintMuiSchemaTitles(_iobuf *,ushort *)

- ea: `0x14002d050`
- end: `0x14002d239`
- name: `?PrintMuiSchemaTitles@@YAEPEAU_iobuf@@PEAG@Z`
- size: `489`
- prototype: `unsigned __int8 __fastcall(struct _iobuf *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14002d560`

## callees

- `0x14002d050`
- `0x14002e418`
- `0x140040130`
- `0x1400401c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002d1de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002d205`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002d1de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14002d205`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002d140`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002d1d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002d1f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002d140`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002d1d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002d1f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002d151`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002d151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d11c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d1a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d20d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d11c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d1a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d20d`
- `api-ms-win-core-localization-l1-2-0!GetFileMUIPath` at `0x14002d10e`
- `api-ms-win-core-localization-l1-2-0!GetFileMUIPath` at `0x14002d19e`
- `api-ms-win-core-localization-l1-2-0!GetFileMUIPath` at `0x14002d10e`
- `api-ms-win-core-localization-l1-2-0!GetFileMUIPath` at `0x14002d19e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14002d0b2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14002d0b2`

## pseudocode

```c
unsigned __int8 __fastcall PrintMuiSchemaTitles(struct _iobuf *a1, unsigned __int16 *a2)
{
  WCHAR *pwszFileMUIPath; // rbx
  DWORD LastError; // eax
  unsigned __int64 v5; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v7; // rax
  HANDLE v9; // rax
  ULONG pcchFileMUIPath; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pcchLanguage; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int64 pululEnumerator; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Mem[1024]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Dst[1024]; // [rsp+850h] [rbp+750h] BYREF

  pcchLanguage = 0;
  pcchFileMUIPath = 0;
  pululEnumerator = 0;
  if ( ExpandEnvironmentStringsW(a2, Dst, 0x400u) - 1 > 0x3FE )
  {
    GetLastError();
    return 0;
  }
  pcchFileMUIPath = 1024;
  pcchLanguage = 0;
  pululEnumerator = 0;
  pwszFileMUIPath = Mem;
  if ( GetFileMUIPath(0, Dst, 0, &pcchLanguage, Mem, &pcchFileMUIPath, &pululEnumerator) )
    goto LABEL_9;
  LastError = GetLastError();
  if ( LastError != 122 )
    goto LABEL_8;
  v5 = 2LL * pcchFileMUIPath;
  if ( v5 > 0xFFFFFFFF )
    return 0;
  ProcessHeap = GetProcessHeap();
  pwszFileMUIPath = (WCHAR *)HeapAlloc(ProcessHeap, 8u, (unsigned int)v5);
  if ( !pwszFileMUIPath )
    return 0;
  pcchLanguage = 0;
  pululEnumerator = 0;
  if ( GetFileMUIPath(0, Dst, 0, &pcchLanguage, pwszFileMUIPath, &pcchFileMUIPath, &pululEnumerator) )
    goto LABEL_9;
  LastError = GetLastError();
LABEL_8:
  if ( LastError )
  {
LABEL_14:
    if ( pwszFileMUIPath && pwszFileMUIPath != Mem )
    {
      v9 = GetProcessHeap();
      HeapFree(v9, 0, pwszFileMUIPath);
    }
    return 0;
  }
LABEL_9:
  if ( XmlParseMuiPathAndPrintTitles(a1, pwszFileMUIPath) )
    goto LABEL_14;
  if ( pwszFileMUIPath )
  {
    if ( pwszFileMUIPath != Mem )
    {
      v7 = GetProcessHeap();
      HeapFree(v7, 0, pwszFileMUIPath);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14002d050  mov     [rsp-8+arg_10], rbx
0x14002d055  mov     [rsp-8+arg_18], rdi
0x14002d05a  push    rbp
0x14002d05b  lea     rbp, [rsp-0F60h]
0x14002d063  mov     eax, 1060h
0x14002d068  call    _alloca_probe
0x14002d06d  sub     rsp, rax
0x14002d070  mov     rax, cs:__security_cookie
0x14002d077  xor     rax, rsp
0x14002d07a  mov     [rbp+0F60h+var_10], rax
0x14002d081  mov     rax, rdx
0x14002d084  mov     [rsp+1060h+pcchLanguage], 0
0x14002d08c  mov     rdi, rcx
0x14002d08f  mov     [rsp+1060h+var_1020], 0
0x14002d097  mov     ebx, 400h
0x14002d09c  mov     [rsp+1060h+var_1018], 0
0x14002d0a5  mov     r8d, ebx; nSize
0x14002d0a8  lea     rdx, [rbp+0F60h+Dst]; lpDst
0x14002d0af  mov     rcx, rax; lpSrc
0x14002d0b2  call    cs:__imp_ExpandEnvironmentStringsW
0x14002d0b8  dec     eax
0x14002d0ba  cmp     eax, 3FEh
0x14002d0bf  ja      loc_14002D20D
0x14002d0c5  lea     rax, [rsp+1060h+var_1018]
0x14002d0ca  mov     [rsp+1060h+var_1020], ebx
0x14002d0ce  mov     [rsp+1060h+pululEnumerator], rax; pululEnumerator
0x14002d0d3  lea     r9, [rsp+1060h+pcchLanguage]; pcchLanguage
0x14002d0d8  lea     rax, [rsp+1060h+var_1020]
0x14002d0dd  mov     [rsp+1060h+pcchLanguage], 0
0x14002d0e5  mov     [rsp+1060h+pcchFileMUIPath], rax; pcchFileMUIPath
0x14002d0ea  lea     rdx, [rbp+0F60h+Dst]; pcwszFilePath
0x14002d0f1  lea     rax, [rsp+1060h+Mem]
0x14002d0f6  mov     [rsp+1060h+var_1018], 0
0x14002d0ff  xor     r8d, r8d; pwszLanguage
0x14002d102  mov     [rsp+1060h+pwszFileMUIPath], rax; pwszFileMUIPath
0x14002d107  xor     ecx, ecx; dwFlags
0x14002d109  lea     rbx, [rsp+1060h+Mem]
0x14002d10e  call    cs:__imp_GetFileMUIPath
0x14002d114  test    eax, eax
0x14002d116  jnz     loc_14002D1B2
0x14002d11c  call    cs:__imp_GetLastError
0x14002d122  cmp     eax, 7Ah ; 'z'
0x14002d125  jnz     loc_14002D1AE
0x14002d12b  mov     ebx, [rsp+1060h+var_1020]
0x14002d12f  mov     eax, 0FFFFFFFFh
0x14002d134  add     rbx, rbx
0x14002d137  cmp     rbx, rax
0x14002d13a  ja      loc_14002D213
0x14002d140  call    cs:__imp_GetProcessHeap
0x14002d146  mov     r8d, ebx; dwBytes
0x14002d149  mov     edx, 8; dwFlags
0x14002d14e  mov     rcx, rax; hHeap
0x14002d151  call    cs:__imp_HeapAlloc
0x14002d157  mov     rbx, rax
0x14002d15a  test    rax, rax
0x14002d15d  jz      loc_14002D213
0x14002d163  lea     rax, [rsp+1060h+var_1018]
0x14002d168  mov     [rsp+1060h+pcchLanguage], 0
0x14002d170  mov     [rsp+1060h+pululEnumerator], rax; pululEnumerator
0x14002d175  lea     r9, [rsp+1060h+pcchLanguage]; pcchLanguage
0x14002d17a  lea     rax, [rsp+1060h+var_1020]
0x14002d17f  mov     [rsp+1060h+var_1018], 0
0x14002d188  mov     [rsp+1060h+pcchFileMUIPath], rax; pcchFileMUIPath
0x14002d18d  lea     rdx, [rbp+0F60h+Dst]; pcwszFilePath
0x14002d194  xor     r8d, r8d; pwszLanguage
0x14002d197  mov     [rsp+1060h+pwszFileMUIPath], rbx; pwszFileMUIPath
0x14002d19c  xor     ecx, ecx; dwFlags
0x14002d19e  call    cs:__imp_GetFileMUIPath
0x14002d1a4  test    eax, eax
0x14002d1a6  jnz     short loc_14002D1B2
0x14002d1a8  call    cs:__imp_GetLastError
0x14002d1ae  test    eax, eax
0x14002d1b0  jnz     short loc_14002D1E8
0x14002d1b2  mov     rdx, rbx; lpSrc
0x14002d1b5  mov     rcx, rdi; struct _iobuf *
0x14002d1b8  call    ?XmlParseMuiPathAndPrintTitles@@YAKPEAU_iobuf@@PEAG@Z; XmlParseMuiPathAndPrintTitles(_iobuf *,ushort *)
0x14002d1bd  test    eax, eax
0x14002d1bf  jnz     short loc_14002D1E8
0x14002d1c1  test    rbx, rbx
0x14002d1c4  jz      short loc_14002D1E4
0x14002d1c6  lea     rax, [rsp+1060h+Mem]
0x14002d1cb  cmp     rbx, rax
0x14002d1ce  jz      short loc_14002D1E4
0x14002d1d0  call    cs:__imp_GetProcessHeap
0x14002d1d6  mov     r8, rbx; lpMem
0x14002d1d9  xor     edx, edx; dwFlags
0x14002d1db  mov     rcx, rax; hHeap
0x14002d1de  call    cs:__imp_HeapFree
0x14002d1e4  mov     al, 1
0x14002d1e6  jmp     short loc_14002D215
0x14002d1e8  test    rbx, rbx
0x14002d1eb  jz      short loc_14002D213
0x14002d1ed  lea     rax, [rsp+1060h+Mem]
0x14002d1f2  cmp     rbx, rax
0x14002d1f5  jz      short loc_14002D213
0x14002d1f7  call    cs:__imp_GetProcessHeap
0x14002d1fd  mov     r8, rbx; lpMem
0x14002d200  xor     edx, edx; dwFlags
0x14002d202  mov     rcx, rax; hHeap
0x14002d205  call    cs:__imp_HeapFree
0x14002d20b  jmp     short loc_14002D213
0x14002d20d  call    cs:__imp_GetLastError
0x14002d213  xor     al, al
0x14002d215  mov     rcx, [rbp+0F60h+var_10]
0x14002d21c  xor     rcx, rsp; StackCookie
0x14002d21f  call    __security_check_cookie
0x14002d224  lea     r11, [rsp+1060h+var_s0]
0x14002d22c  mov     rbx, [r11+20h]
0x14002d230  mov     rdi, [r11+28h]
0x14002d234  mov     rsp, r11
0x14002d237  pop     rbp
0x14002d238  retn
```
