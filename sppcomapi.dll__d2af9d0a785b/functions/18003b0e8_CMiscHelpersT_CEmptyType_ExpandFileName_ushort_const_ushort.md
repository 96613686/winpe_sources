# CMiscHelpersT<CEmptyType>::ExpandFileName(ushort const *,ushort * *)

- ea: `0x18003b0e8`
- end: `0x18003b28e`
- name: `?ExpandFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003b94c`

## callees

- `0x1800031fc`
- `0x180003520`
- `0x1800036ec`
- `0x180004288`
- `0x18001f044`
- `0x18003b0e8`
- `0x18003c560`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b246`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b246`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b25b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b25b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b209`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003b125`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003b1f9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003b125`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003b1f9`

## string_xrefs

- `0x18003b10a`: `%windir%\system32\spp\tokens\pkeyconfig`
- `0x18003b1ec`: `%windir%\system32\spp\tokens\pkeyconfig`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::ExpandFileName(__int64 a1, LPWSTR *a2)
{
  LPWSTR v3; // rbx
  DWORD v4; // eax
  DWORD v5; // esi
  int StringCch; // eax
  unsigned int v7; // edi
  int CchBufferN; // eax
  DWORD v9; // eax
  signed int LastError; // eax
  LPWSTR v11; // rax
  HANDLE ProcessHeap; // rax
  LPWSTR lpDst[2]; // [rsp+20h] [rbp-258h] BYREF
  WCHAR Dst[264]; // [rsp+30h] [rbp-248h] BYREF

  v3 = 0;
  lpDst[0] = 0;
  v4 = ExpandEnvironmentStringsW(L"%windir%\\system32\\spp\\tokens\\pkeyconfig", Dst, 0x104u);
  v5 = v4;
  if ( !v4 )
    goto LABEL_17;
  if ( v4 <= 0x104 )
  {
    LODWORD(lpDst[0]) = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Dst, lpDst);
    v7 = StringCch;
    if ( StringCch < 0
      || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Dst),
          v7 = StringCch,
          StringCch < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
    if ( (v7 & 0x80000000) != 0 )
      goto LABEL_11;
    goto LABEL_22;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CchBufferN = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateCchBufferN(0, v5, lpDst);
  v7 = CchBufferN;
  if ( CchBufferN < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)CchBufferN);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( (v7 & 0x80000000) != 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    v3 = lpDst[0];
    goto LABEL_22;
  }
  v3 = lpDst[0];
  v9 = ExpandEnvironmentStringsW(L"%windir%\\system32\\spp\\tokens\\pkeyconfig", lpDst[0], v5);
  if ( !v9 )
  {
LABEL_17:
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v7 = -2147467259;
    }
    goto LABEL_11;
  }
  if ( v9 != v5 )
  {
    v7 = -2147024774;
LABEL_11:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_22;
  }
  v11 = v3;
  v3 = 0;
  *a2 = v11;
LABEL_22:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v7;
}

```

## disassembly

```asm
0x18003b0e8  push    rbx
0x18003b0ea  push    rsi
0x18003b0eb  push    rdi
0x18003b0ec  push    r14
0x18003b0ee  sub     rsp, 258h
0x18003b0f5  mov     rax, cs:__security_cookie
0x18003b0fc  xor     rax, rsp
0x18003b0ff  mov     [rsp+278h+var_38], rax
0x18003b107  mov     r14, rdx
0x18003b10a  lea     rcx, aWindirSystem32; "%windir%\\system32\\spp\\tokens\\pkeyco"...
0x18003b111  mov     edi, 104h
0x18003b116  lea     rdx, [rsp+278h+Dst]; lpDst
0x18003b11b  xor     ebx, ebx
0x18003b11d  mov     r8d, edi; nSize
0x18003b120  mov     [rsp+278h+lpDst], rbx
0x18003b125  call    cs:__imp_ExpandEnvironmentStringsW
0x18003b12c  nop     dword ptr [rax+rax+00h]
0x18003b131  mov     esi, eax
0x18003b133  test    eax, eax
0x18003b135  jz      loc_18003B209
0x18003b13b  cmp     eax, edi
0x18003b13d  ja      short loc_18003B1A5
0x18003b13f  lea     rdx, [rsp+278h+lpDst]
0x18003b144  mov     dword ptr [rsp+278h+lpDst], ebx
0x18003b148  lea     rcx, [rsp+278h+Dst]
0x18003b14d  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18003b152  mov     edi, eax
0x18003b154  test    eax, eax
0x18003b156  js      short loc_18003B16F
0x18003b158  mov     edx, dword ptr [rsp+278h+lpDst]
0x18003b15c  lea     rcx, [rsp+278h+Dst]; Src
0x18003b161  mov     r8, r14
0x18003b164  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18003b169  mov     edi, eax
0x18003b16b  test    eax, eax
0x18003b16d  jns     short loc_18003B176
0x18003b16f  mov     ecx, eax
0x18003b171  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b176  mov     ecx, edi
0x18003b178  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b17d  test    edi, edi
0x18003b17f  jns     loc_18003B23A
0x18003b185  jmp     short loc_18003B199
0x18003b187  mov     edi, 80004005h
0x18003b18c  jmp     short loc_18003B199
0x18003b18e  jle     short loc_18003B199
0x18003b190  movzx   edi, ax
0x18003b193  or      edi, 80070000h
0x18003b199  mov     ecx, edi
0x18003b19b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b1a0  jmp     loc_18003B23A
0x18003b1a5  xor     ecx, ecx
0x18003b1a7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b1ac  xor     ecx, ecx
0x18003b1ae  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b1b3  xor     ecx, ecx
0x18003b1b5  lea     r8, [rsp+278h+lpDst]
0x18003b1ba  mov     edx, esi
0x18003b1bc  call    ?CreateCchBufferN@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateCchBufferN(ushort,ulong,ushort * *)
0x18003b1c1  mov     edi, eax
0x18003b1c3  test    eax, eax
0x18003b1c5  jns     short loc_18003B1CE
0x18003b1c7  mov     ecx, eax
0x18003b1c9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b1ce  mov     ecx, edi
0x18003b1d0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b1d5  test    edi, edi
0x18003b1d7  jns     short loc_18003B1E7
0x18003b1d9  mov     ecx, edi
0x18003b1db  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b1e0  mov     rbx, [rsp+278h+lpDst]
0x18003b1e5  jmp     short loc_18003B23A
0x18003b1e7  mov     rbx, [rsp+278h+lpDst]
0x18003b1ec  lea     rcx, aWindirSystem32; "%windir%\\system32\\spp\\tokens\\pkeyco"...
0x18003b1f3  mov     rdx, rbx; lpDst
0x18003b1f6  mov     r8d, esi; nSize
0x18003b1f9  call    cs:__imp_ExpandEnvironmentStringsW
0x18003b200  nop     dword ptr [rax+rax+00h]
0x18003b205  test    eax, eax
0x18003b207  jnz     short loc_18003B224
0x18003b209  call    cs:__imp_GetLastError
0x18003b210  nop     dword ptr [rax+rax+00h]
0x18003b215  mov     edi, eax
0x18003b217  test    eax, eax
0x18003b219  jz      loc_18003B187
0x18003b21f  jmp     loc_18003B18E
0x18003b224  cmp     eax, esi
0x18003b226  jz      short loc_18003B232
0x18003b228  mov     edi, 8007007Ah
0x18003b22d  jmp     loc_18003B199
0x18003b232  mov     rax, rbx
0x18003b235  xor     ebx, ebx
0x18003b237  mov     [r14], rax
0x18003b23a  mov     ecx, edi
0x18003b23c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b241  test    rbx, rbx
0x18003b244  jz      short loc_18003B26E
0x18003b246  call    cs:__imp_GetProcessHeap
0x18003b24d  nop     dword ptr [rax+rax+00h]
0x18003b252  lea     r8, [rbx-4]; lpMem
0x18003b256  xor     edx, edx; dwFlags
0x18003b258  mov     rcx, rax; hHeap
0x18003b25b  call    cs:__imp_HeapFree
0x18003b262  nop     dword ptr [rax+rax+00h]
0x18003b267  xor     ecx, ecx
0x18003b269  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b26e  mov     eax, edi
0x18003b270  mov     rcx, [rsp+278h+var_38]
0x18003b278  xor     rcx, rsp; StackCookie
0x18003b27b  call    __security_check_cookie
0x18003b280  add     rsp, 258h
0x18003b287  pop     r14
0x18003b289  pop     rdi
0x18003b28a  pop     rsi
0x18003b28b  pop     rbx
0x18003b28c  retn
```
