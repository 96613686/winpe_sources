# CMiscHelpersT<CEmptyType>::AppendToSystemPath(ushort const *,ushort * *)

- ea: `0x18001ecb0`
- end: `0x18001ef7c`
- name: `?AppendToSystemPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z`
- size: `716`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001f2a0`
- `0x180037870`
- `0x1800379a0`
- `0x180037ad0`
- `0x18003b94c`

## callees

- `0x1800031fc`
- `0x180003520`
- `0x1800036ec`
- `0x180004288`
- `0x18001ecb0`
- `0x18002031c`
- `0x18003c560`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eecd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eefa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ef27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eecd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eefa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ef27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001eee2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ef0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ef3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001eee2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ef0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ef3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001ed1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001ed1d`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::AppendToSystemPath(char *Src, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // r15
  __int64 v5; // r14
  __int64 v6; // rsi
  signed int LastError; // eax
  unsigned int v8; // edi
  __int64 v9; // rdx
  WCHAR *v10; // rax
  __int64 v11; // rcx
  int Internal; // eax
  char *v13; // rbx
  int StringCch; // eax
  int v15; // eax
  int v16; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v18; // rax
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+48h] [rbp-B8h]
  int v24; // [rsp+4Ch] [rbp-B4h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  v22 = 0;
  v20 = 0;
  v21 = 0;
  v23 = 1;
  v24 = *(_DWORD *)L"\\";
  v4 = 0;
  v5 = 0;
  v6 = 0;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
LABEL_6:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_35;
  }
  v9 = 260;
  v10 = Buffer;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v8 = v9 == 0 ? 0x80070057 : 0;
  v11 = (260 - v9) & -(__int64)(v9 != 0);
  if ( !v9 )
    goto LABEL_6;
  if ( Buffer[v11 - 1] == 92 || Buffer[v11 - 1] == 47 )
    --v11;
  if ( v11 == (unsigned int)v11 )
  {
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v8 = 0;
  }
  else
  {
    v8 = -2147024362;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( (v8 & 0x80000000) == 0 )
  {
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Buffer);
    v8 = Internal;
    if ( Internal < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
    v5 = v20;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_6;
  v13 = Src + 2;
  if ( *(_WORD *)Src != 92 )
    v13 = Src;
  LODWORD(v20) = 0;
  if ( v13
    && (StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v13, &v20),
        v8 = StringCch,
        StringCch < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  else
  {
    v15 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v13);
    v8 = v15;
    if ( v15 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v15);
    v6 = v21;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_6;
  v16 = STRAPI_MultiCat(&v22, 3u, v5, &v24, v6);
  v8 = v16;
  if ( v16 >= 0 )
  {
    *a2 = v22;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v16);
    v4 = v22;
  }
LABEL_35:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v6 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v4 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v8;
}

```

## disassembly

```asm
0x18001ecb0  mov     [rsp-8+arg_10], rbx
0x18001ecb5  push    rbp
0x18001ecb6  push    rsi
0x18001ecb7  push    rdi
0x18001ecb8  push    r12
0x18001ecba  push    r13
0x18001ecbc  push    r14
0x18001ecbe  push    r15
0x18001ecc0  lea     rbp, [rsp-170h]
0x18001ecc8  sub     rsp, 270h
0x18001eccf  mov     rax, cs:__security_cookie
0x18001ecd6  xor     rax, rsp
0x18001ecd9  mov     [rbp+1A0h+var_40], rax
0x18001ece0  mov     eax, dword ptr cs:asc_18003F940; "\\"
0x18001ece6  xor     edi, edi
0x18001ece8  mov     r12, rdx
0x18001eceb  mov     [rsp+2A0h+var_260], rdi
0x18001ecf0  mov     r13, rcx
0x18001ecf3  mov     [rsp+2A0h+var_270], rdi
0x18001ecf8  mov     ebx, 104h
0x18001ecfd  mov     [rsp+2A0h+var_268], rdi
0x18001ed02  mov     edx, ebx; uSize
0x18001ed04  mov     [rsp+2A0h+var_258], 1
0x18001ed0c  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x18001ed11  mov     [rsp+2A0h+var_254], eax
0x18001ed15  mov     r15d, edi
0x18001ed18  mov     r14d, edi
0x18001ed1b  mov     esi, edi
0x18001ed1d  call    cs:__imp_GetSystemDirectoryW
0x18001ed24  nop     dword ptr [rax+rax+00h]
0x18001ed29  test    eax, eax
0x18001ed2b  jnz     short loc_18001ED5D
0x18001ed2d  call    cs:__imp_GetLastError
0x18001ed34  nop     dword ptr [rax+rax+00h]
0x18001ed39  mov     edi, eax
0x18001ed3b  test    eax, eax
0x18001ed3d  jnz     short loc_18001ED46
0x18001ed3f  mov     edi, 80004005h
0x18001ed44  jmp     short loc_18001ED51
0x18001ed46  jle     short loc_18001ED51
0x18001ed48  movzx   edi, ax
0x18001ed4b  or      edi, 80070000h
0x18001ed51  mov     ecx, edi
0x18001ed53  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001ed58  jmp     loc_18001EEC1
0x18001ed5d  mov     rdx, rbx
0x18001ed60  lea     rax, [rsp+2A0h+Buffer]
0x18001ed65  cmp     [rax], di
0x18001ed68  jz      short loc_18001ED74
0x18001ed6a  add     rax, 2
0x18001ed6e  sub     rdx, 1
0x18001ed72  jnz     short loc_18001ED65
0x18001ed74  mov     rax, rdx
0x18001ed77  neg     rax
0x18001ed7a  mov     rax, rdx
0x18001ed7d  sbb     edi, edi
0x18001ed7f  sub     rbx, rdx
0x18001ed82  not     edi
0x18001ed84  and     edi, 80070057h
0x18001ed8a  neg     rax
0x18001ed8d  sbb     rcx, rcx
0x18001ed90  and     rcx, rbx
0x18001ed93  test    rdx, rdx
0x18001ed96  jz      short loc_18001ED51
0x18001ed98  mov     eax, 5Ch ; '\'
0x18001ed9d  cmp     ax, word ptr [rsp+rcx*2+2A0h+var_254+2]
0x18001eda2  jz      short loc_18001EDB0
0x18001eda4  mov     eax, 2Fh ; '/'
0x18001eda9  cmp     ax, word ptr [rsp+rcx*2+2A0h+var_254+2]
0x18001edae  jnz     short loc_18001EDB3
0x18001edb0  dec     rcx
0x18001edb3  mov     ebx, ecx
0x18001edb5  cmp     rcx, rbx
0x18001edb8  jz      short loc_18001EDCA
0x18001edba  mov     edi, 80070216h
0x18001edbf  xor     ebx, ebx
0x18001edc1  mov     ecx, edi
0x18001edc3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001edc8  jmp     short loc_18001EDD3
0x18001edca  xor     ecx, ecx
0x18001edcc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001edd1  xor     edi, edi
0x18001edd3  mov     ecx, edi
0x18001edd5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001edda  test    edi, edi
0x18001eddc  jns     short loc_18001EDE7
0x18001edde  mov     ecx, edi
0x18001ede0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001ede5  jmp     short loc_18001EE0A
0x18001ede7  lea     r8, [rsp+2A0h+var_270]
0x18001edec  mov     edx, ebx
0x18001edee  lea     rcx, [rsp+2A0h+Buffer]; Src
0x18001edf3  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18001edf8  mov     edi, eax
0x18001edfa  test    eax, eax
0x18001edfc  jns     short loc_18001EE05
0x18001edfe  mov     ecx, eax
0x18001ee00  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001ee05  mov     r14, [rsp+2A0h+var_270]
0x18001ee0a  mov     ecx, edi
0x18001ee0c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001ee11  test    edi, edi
0x18001ee13  js      loc_18001ED51
0x18001ee19  lea     rbx, [r13+2]
0x18001ee1d  mov     eax, 5Ch ; '\'
0x18001ee22  cmp     ax, [r13+0]
0x18001ee27  cmovnz  rbx, r13
0x18001ee2b  xor     r13d, r13d
0x18001ee2e  mov     edx, r13d
0x18001ee31  mov     dword ptr [rsp+2A0h+var_270], edx
0x18001ee35  test    rbx, rbx
0x18001ee38  jz      short loc_18001EE5A
0x18001ee3a  lea     rdx, [rsp+2A0h+var_270]
0x18001ee3f  mov     rcx, rbx
0x18001ee42  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18001ee47  mov     edi, eax
0x18001ee49  test    eax, eax
0x18001ee4b  jns     short loc_18001EE56
0x18001ee4d  mov     ecx, eax
0x18001ee4f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001ee54  jmp     short loc_18001EE79
0x18001ee56  mov     edx, dword ptr [rsp+2A0h+var_270]
0x18001ee5a  lea     r8, [rsp+2A0h+var_268]
0x18001ee5f  mov     rcx, rbx; Src
0x18001ee62  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18001ee67  mov     edi, eax
0x18001ee69  test    eax, eax
0x18001ee6b  jns     short loc_18001EE74
0x18001ee6d  mov     ecx, eax
0x18001ee6f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001ee74  mov     rsi, [rsp+2A0h+var_268]
0x18001ee79  mov     ecx, edi
0x18001ee7b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001ee80  test    edi, edi
0x18001ee82  js      loc_18001ED51
0x18001ee88  lea     r9, [rsp+2A0h+var_254]
0x18001ee8d  mov     [rsp+2A0h+var_280], rsi
0x18001ee92  mov     r8, r14
0x18001ee95  lea     rcx, [rsp+2A0h+var_260]; unsigned __int16 **
0x18001ee9a  mov     edx, 3; unsigned int
0x18001ee9f  call    ?STRAPI_MultiCat@@YAJPEAPEAGKZZ; STRAPI_MultiCat(ushort * *,ulong,...)
0x18001eea4  mov     edi, eax
0x18001eea6  test    eax, eax
0x18001eea8  jns     short loc_18001EEB8
0x18001eeaa  mov     ecx, eax
0x18001eeac  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001eeb1  mov     r15, [rsp+2A0h+var_260]
0x18001eeb6  jmp     short loc_18001EEC1
0x18001eeb8  mov     rax, [rsp+2A0h+var_260]
0x18001eebd  mov     [r12], rax
0x18001eec1  mov     ecx, edi
0x18001eec3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001eec8  test    rsi, rsi
0x18001eecb  jz      short loc_18001EEF5
0x18001eecd  call    cs:__imp_GetProcessHeap
0x18001eed4  nop     dword ptr [rax+rax+00h]
0x18001eed9  lea     r8, [rsi-4]; lpMem
0x18001eedd  xor     edx, edx; dwFlags
0x18001eedf  mov     rcx, rax; hHeap
0x18001eee2  call    cs:__imp_HeapFree
0x18001eee9  nop     dword ptr [rax+rax+00h]
0x18001eeee  xor     ecx, ecx
0x18001eef0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001eef5  test    r14, r14
0x18001eef8  jz      short loc_18001EF22
0x18001eefa  call    cs:__imp_GetProcessHeap
0x18001ef01  nop     dword ptr [rax+rax+00h]
0x18001ef06  lea     r8, [r14-4]; lpMem
0x18001ef0a  xor     edx, edx; dwFlags
0x18001ef0c  mov     rcx, rax; hHeap
0x18001ef0f  call    cs:__imp_HeapFree
0x18001ef16  nop     dword ptr [rax+rax+00h]
0x18001ef1b  xor     ecx, ecx
0x18001ef1d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001ef22  test    r15, r15
0x18001ef25  jz      short loc_18001EF4F
0x18001ef27  call    cs:__imp_GetProcessHeap
0x18001ef2e  nop     dword ptr [rax+rax+00h]
0x18001ef33  lea     r8, [r15-4]; lpMem
0x18001ef37  xor     edx, edx; dwFlags
0x18001ef39  mov     rcx, rax; hHeap
0x18001ef3c  call    cs:__imp_HeapFree
0x18001ef43  nop     dword ptr [rax+rax+00h]
0x18001ef48  xor     ecx, ecx
0x18001ef4a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001ef4f  mov     eax, edi
0x18001ef51  mov     rcx, [rbp+1A0h+var_40]
0x18001ef58  xor     rcx, rsp; StackCookie
0x18001ef5b  call    __security_check_cookie
0x18001ef60  mov     rbx, [rsp+2A0h+arg_10]
0x18001ef68  add     rsp, 270h
0x18001ef6f  pop     r15
0x18001ef71  pop     r14
0x18001ef73  pop     r13
0x18001ef75  pop     r12
0x18001ef77  pop     rdi
0x18001ef78  pop     rsi
0x18001ef79  pop     rbp
0x18001ef7a  retn
```
