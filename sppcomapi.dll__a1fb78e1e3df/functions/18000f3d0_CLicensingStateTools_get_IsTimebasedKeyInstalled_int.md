# CLicensingStateTools::get_IsTimebasedKeyInstalled(int *)

- ea: `0x18000f3d0`
- end: `0x18000f529`
- name: `?get_IsTimebasedKeyInstalled@CLicensingStateTools@@UEAAJPEAH@Z`
- size: `345`
- prototype: `__int64 __fastcall(CLicensingStateTools *__hidden this, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x1800031fc`
- `0x180003520`
- `0x1800036ec`
- `0x180004288`
- `0x18000f3d0`
- `0x18003c506`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f4dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f4dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f4f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f4f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f50f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f50f`

## pseudocode

```c
__int64 __fastcall CLicensingStateTools::get_IsTimebasedKeyInstalled(CLicensingStateTools *this, int *a2)
{
  _DWORD *v2; // rbx
  unsigned int v4; // edi
  __int64 v5; // rcx
  int v6; // eax
  int StringCch; // eax
  int v8; // eax
  void *v9; // rdi
  unsigned int v10; // r14d
  unsigned int v11; // ebp
  BOOL v12; // ecx
  HANDLE ProcessHeap; // rax
  unsigned int v15; // [rsp+58h] [rbp+10h] BYREF
  _DWORD *v16; // [rsp+60h] [rbp+18h] BYREF
  void *Buf1; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0;
  Buf1 = 0;
  v16 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    goto LABEL_3;
  }
  v6 = (*(__int64 (__fastcall **)(CLicensingStateTools *, void **))(*(_QWORD *)this + 136LL))(this, &Buf1);
  v4 = v6;
  if ( v6 < 0 )
  {
    v5 = (unsigned int)v6;
    goto LABEL_4;
  }
  v15 = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(L"Retail:TB", &v15);
  v4 = StringCch;
  if ( StringCch >= 0 )
  {
    v8 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(L"Retail:TB", v15, &v16);
    v4 = v8;
    if ( v8 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
    v2 = v16;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
  {
LABEL_3:
    v5 = v4;
LABEL_4:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_23;
  }
  v9 = Buf1;
  if ( Buf1 )
    v10 = *((_DWORD *)Buf1 - 1);
  else
    v10 = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v2 )
    v11 = *(v2 - 1);
  else
    v11 = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v12 = v10 >= v11 && memcmp_0(v9, v2, 2LL * v11) == 0;
  *a2 = v12;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v4 = 0;
LABEL_23:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2 - 1);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( Buf1 )
    SysFreeString((BSTR)Buf1);
  return v4;
}

```

## disassembly

```asm
0x18000f3d0  push    rbx
0x18000f3d2  push    rbp
0x18000f3d3  push    rsi
0x18000f3d4  push    rdi
0x18000f3d5  push    r14
0x18000f3d7  sub     rsp, 20h
0x18000f3db  xor     ebx, ebx
0x18000f3dd  mov     [rsp+48h+Buf1], 0
0x18000f3e6  mov     [rsp+48h+arg_10], rbx
0x18000f3eb  mov     rsi, rdx
0x18000f3ee  test    rdx, rdx
0x18000f3f1  jnz     short loc_18000F404
0x18000f3f3  mov     edi, 80070057h
0x18000f3f8  mov     ecx, edi
0x18000f3fa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000f3ff  jmp     loc_18000F4D1
0x18000f404  mov     rax, [rcx]
0x18000f407  lea     rdx, [rsp+48h+Buf1]
0x18000f40c  mov     rax, [rax+88h]
0x18000f413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f418  mov     edi, eax
0x18000f41a  test    eax, eax
0x18000f41c  jns     short loc_18000F422
0x18000f41e  mov     ecx, eax
0x18000f420  jmp     short loc_18000F3FA
0x18000f422  lea     rdx, [rsp+48h+arg_8]
0x18000f427  mov     [rsp+48h+arg_8], ebx
0x18000f42b  lea     rcx, aRetailTb; "Retail:TB"
0x18000f432  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18000f437  mov     edi, eax
0x18000f439  test    eax, eax
0x18000f43b  jns     short loc_18000F446
0x18000f43d  mov     ecx, eax
0x18000f43f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000f444  jmp     short loc_18000F46D
0x18000f446  mov     edx, [rsp+48h+arg_8]
0x18000f44a  lea     r8, [rsp+48h+arg_10]
0x18000f44f  lea     rcx, aRetailTb; "Retail:TB"
0x18000f456  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18000f45b  mov     edi, eax
0x18000f45d  test    eax, eax
0x18000f45f  jns     short loc_18000F468
0x18000f461  mov     ecx, eax
0x18000f463  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000f468  mov     rbx, [rsp+48h+arg_10]
0x18000f46d  mov     ecx, edi
0x18000f46f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000f474  test    edi, edi
0x18000f476  js      short loc_18000F3F8
0x18000f478  mov     rdi, [rsp+48h+Buf1]
0x18000f47d  test    rdi, rdi
0x18000f480  jnz     short loc_18000F496
0x18000f482  xor     r14d, r14d
0x18000f485  xor     ecx, ecx
0x18000f487  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000f48c  test    rbx, rbx
0x18000f48f  jz      short loc_18000F49C
0x18000f491  mov     ebp, [rbx-4]
0x18000f494  jmp     short loc_18000F49E
0x18000f496  mov     r14d, [rdi-4]
0x18000f49a  jmp     short loc_18000F485
0x18000f49c  xor     ebp, ebp
0x18000f49e  xor     ecx, ecx
0x18000f4a0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000f4a5  cmp     r14d, ebp
0x18000f4a8  jb      short loc_18000F4C4
0x18000f4aa  mov     r8d, ebp
0x18000f4ad  mov     rdx, rbx; Buf2
0x18000f4b0  add     r8, r8; Size
0x18000f4b3  mov     rcx, rdi; Buf1
0x18000f4b6  call    memcmp_0
0x18000f4bb  xor     ecx, ecx
0x18000f4bd  test    eax, eax
0x18000f4bf  setz    cl
0x18000f4c2  jmp     short loc_18000F4C6
0x18000f4c4  xor     ecx, ecx
0x18000f4c6  mov     [rsi], ecx
0x18000f4c8  xor     ecx, ecx
0x18000f4ca  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000f4cf  xor     edi, edi
0x18000f4d1  mov     ecx, edi
0x18000f4d3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000f4d8  test    rbx, rbx
0x18000f4db  jz      short loc_18000F505
0x18000f4dd  call    cs:__imp_GetProcessHeap
0x18000f4e4  nop     dword ptr [rax+rax+00h]
0x18000f4e9  lea     r8, [rbx-4]; lpMem
0x18000f4ed  xor     edx, edx; dwFlags
0x18000f4ef  mov     rcx, rax; hHeap
0x18000f4f2  call    cs:__imp_HeapFree
0x18000f4f9  nop     dword ptr [rax+rax+00h]
0x18000f4fe  xor     ecx, ecx
0x18000f500  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000f505  mov     rcx, [rsp+48h+Buf1]; bstrString
0x18000f50a  test    rcx, rcx
0x18000f50d  jz      short loc_18000F51B
0x18000f50f  call    cs:__imp_SysFreeString
0x18000f516  nop     dword ptr [rax+rax+00h]
0x18000f51b  mov     eax, edi
0x18000f51d  add     rsp, 20h
0x18000f521  pop     r14
0x18000f523  pop     rdi
0x18000f524  pop     rsi
0x18000f525  pop     rbp
0x18000f526  pop     rbx
0x18000f527  retn
```
