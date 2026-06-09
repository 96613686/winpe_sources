# SdbGetMergeRedirectPath

- ea: `0x140015eb4`
- end: `0x140016069`
- name: `SdbGetMergeRedirectPath`
- size: `437`
- prototype: `__int64 __fastcall(_QWORD *, BOOL *, int, const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140016198`
- `0x140023334`

## callees

- `0x14001008c`
- `0x140010270`
- `0x140015eb4`
- `0x140016c98`
- `0x14001759c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140015ffd`
- `ntdll!RtlFreeHeap` at `0x14001602c`
- `ntdll!RtlFreeHeap` at `0x140015ffd`
- `ntdll!RtlFreeHeap` at `0x14001602c`

## string_xrefs

- `0x140015f59`: `SdbpGetMergeRedirectPathInternal failed[%x]`
- `0x140015f52`: `SdbGetMergeRedirectPath`
- `0x140015fa5`: `SdbGetMergeRedirectPath`

## pseudocode

```c
__int64 __fastcall SdbGetMergeRedirectPath(_QWORD *a1, BOOL *a2, int a3, const wchar_t *a4)
{
  int MergeRedirectPathInternal; // ebx
  BOOL v10; // esi
  const wchar_t *FileNamePart; // rax
  int v12; // eax
  PVOID P[9]; // [rsp+30h] [rbp-48h] BYREF
  int v14; // [rsp+80h] [rbp+8h] BYREF

  v14 = 0;
  P[0] = 0;
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( a2 )
    *a2 = 0;
  if ( !(unsigned int)SdbpGetMergeSdbsSupported() )
  {
    MergeRedirectPathInternal = -1073741772;
    goto LABEL_20;
  }
  MergeRedirectPathInternal = SdbpGetMergeRedirectPathInternal(P, &v14, 1, a4);
  if ( (int)(MergeRedirectPathInternal + 0x80000000) >= 0 && MergeRedirectPathInternal != -1073741772 )
  {
    AslLogCallPrintf(
      1,
      "SdbGetMergeRedirectPath",
      2134,
      "SdbpGetMergeRedirectPathInternal failed[%x]",
      MergeRedirectPathInternal);
    goto LABEL_20;
  }
  v10 = 0;
  if ( MergeRedirectPathInternal >= 0 )
    v10 = v14 != 0;
  if ( !a3 || !v10 )
  {
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    v12 = SdbpGetMergeRedirectPathInternal(P, 0, 0, a4);
    MergeRedirectPathInternal = v12;
    if ( v12 < 0 )
    {
      if ( v12 != -1073741772 )
        AslLogCallPrintf(1, "SdbGetMergeRedirectPath", 2149, "SdbpGetMergeRedirectPathInternal failed[%x]", v12);
      goto LABEL_20;
    }
    goto LABEL_17;
  }
  FileNamePart = AslPathGetFileNamePart(a4);
  AslLogCallPrintf(
    1,
    "SdbGetMergeRedirectPath",
    2158,
    "Handled Error: MergeSdb staged deletion feature was used, probably to prevent sdb mismatch error. SdbName: [%ls].",
    FileNamePart);
  if ( P[0] )
  {
    if ( MergeRedirectPathInternal < 0 )
    {
LABEL_20:
      if ( P[0] )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
      return (unsigned int)MergeRedirectPathInternal;
    }
LABEL_17:
    *a1 = P[0];
    P[0] = 0;
    if ( a2 )
      *a2 = v10;
    MergeRedirectPathInternal = 0;
    goto LABEL_20;
  }
  return (unsigned int)-1073741772;
}

```

## disassembly

```asm
0x140015eb4  mov     rax, rsp
0x140015eb7  push    rbx
0x140015eb8  push    rbp
0x140015eb9  push    rsi
0x140015eba  push    r12
0x140015ebc  push    r14
0x140015ebe  push    r15
0x140015ec0  sub     rsp, 48h
0x140015ec4  mov     dword ptr [rax+8], 0
0x140015ecb  mov     rbp, r9
0x140015ece  mov     qword ptr [rax-48h], 0
0x140015ed6  mov     r12d, r8d
0x140015ed9  mov     r14, rdx
0x140015edc  mov     r15, rcx
0x140015edf  test    rcx, rcx
0x140015ee2  jnz     short loc_140015EEE
0x140015ee4  mov     eax, 0C00000EFh
0x140015ee9  jmp     loc_140016005
0x140015eee  mov     qword ptr [rcx], 0
0x140015ef5  test    r14, r14
0x140015ef8  jz      short loc_140015F00
0x140015efa  mov     dword ptr [rdx], 0
0x140015f00  call    SdbpGetMergeSdbsSupported
0x140015f05  test    eax, eax
0x140015f07  jnz     short loc_140015F13
0x140015f09  mov     ebx, 0C0000034h
0x140015f0e  jmp     loc_140015FE4
0x140015f13  mov     esi, 1
0x140015f18  lea     rdx, [rsp+78h+arg_0]
0x140015f20  mov     r8d, esi
0x140015f23  lea     rcx, [rsp+78h+P]
0x140015f28  mov     r9, rbp
0x140015f2b  call    SdbpGetMergeRedirectPathInternal
0x140015f30  mov     ebx, eax
0x140015f32  mov     eax, 80000000h
0x140015f37  lea     edx, [rbx+rax]
0x140015f3a  test    eax, edx
0x140015f3c  jnz     short loc_140015F67
0x140015f3e  cmp     ebx, 0C0000034h
0x140015f44  jz      short loc_140015F67
0x140015f46  mov     dword ptr [rsp+78h+var_58], ebx
0x140015f4a  mov     r8d, 856h
0x140015f50  mov     ecx, esi
0x140015f52  lea     rdx, aSdbgetmergered_0; "SdbGetMergeRedirectPath"
0x140015f59  lea     r9, aSdbpgetmergere_0; "SdbpGetMergeRedirectPathInternal failed"...
0x140015f60  call    AslLogCallPrintf
0x140015f65  jmp     short loc_140015FE4
0x140015f67  xor     esi, esi
0x140015f69  test    ebx, ebx
0x140015f6b  js      short loc_140015F7A
0x140015f6d  cmp     [rsp+78h+arg_0], esi
0x140015f74  lea     eax, [rsi+1]
0x140015f77  cmovnz  esi, eax
0x140015f7a  test    r12d, r12d
0x140015f7d  jz      loc_140016013
0x140015f83  test    esi, esi
0x140015f85  jz      loc_140016013
0x140015f8b  mov     rcx, rbp
0x140015f8e  call    AslPathGetFileNamePart
0x140015f93  lea     r9, aHandledErrorMe_0; "Handled Error: MergeSdb staged deletion"...
0x140015f9a  mov     [rsp+78h+var_58], rax
0x140015f9f  mov     r8d, 86Eh
0x140015fa5  lea     rdx, aSdbgetmergered_0; "SdbGetMergeRedirectPath"
0x140015fac  mov     ecx, 1
0x140015fb1  call    AslLogCallPrintf
0x140015fb6  cmp     [rsp+78h+P], 0
0x140015fbc  jnz     short loc_140015FC5
0x140015fbe  mov     ebx, 0C0000034h
0x140015fc3  jmp     short loc_140016003
0x140015fc5  test    ebx, ebx
0x140015fc7  js      short loc_140015FE4
0x140015fc9  mov     rax, [rsp+78h+P]
0x140015fce  mov     [r15], rax
0x140015fd1  mov     [rsp+78h+P], 0
0x140015fda  test    r14, r14
0x140015fdd  jz      short loc_140015FE2
0x140015fdf  mov     [r14], esi
0x140015fe2  xor     ebx, ebx
0x140015fe4  mov     r8, [rsp+78h+P]; P
0x140015fe9  test    r8, r8
0x140015fec  jz      short loc_140016003
0x140015fee  mov     rcx, gs:60h
0x140015ff7  xor     edx, edx; Flags
0x140015ff9  mov     rcx, [rcx+30h]; HeapHandle
0x140015ffd  call    cs:__imp_RtlFreeHeap
0x140016003  mov     eax, ebx
0x140016005  add     rsp, 48h
0x140016009  pop     r15
0x14001600b  pop     r14
0x14001600d  pop     r12
0x14001600f  pop     rsi
0x140016010  pop     rbp
0x140016011  pop     rbx
0x140016012  retn
0x140016013  mov     r8, [rsp+78h+P]; P
0x140016018  test    r8, r8
0x14001601b  jz      short loc_140016032
0x14001601d  mov     rcx, gs:60h
0x140016026  xor     edx, edx; Flags
0x140016028  mov     rcx, [rcx+30h]; HeapHandle
0x14001602c  call    cs:__imp_RtlFreeHeap
0x140016032  mov     r9, rbp
0x140016035  lea     rcx, [rsp+78h+P]
0x14001603a  xor     r8d, r8d
0x14001603d  xor     edx, edx
0x14001603f  call    SdbpGetMergeRedirectPathInternal
0x140016044  mov     ebx, eax
0x140016046  test    eax, eax
0x140016048  jns     loc_140015FC9
0x14001604e  cmp     eax, 0C0000034h
0x140016053  jz      short loc_140015FE4
0x140016055  mov     dword ptr [rsp+78h+var_58], eax
0x140016059  mov     r8d, 865h
0x14001605f  mov     ecx, 1
0x140016064  jmp     loc_140015F52
```
