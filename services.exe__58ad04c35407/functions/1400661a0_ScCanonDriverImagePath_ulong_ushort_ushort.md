# ScCanonDriverImagePath(ulong,ushort *,ushort * *)

- ea: `0x1400661a0`
- end: `0x140066545`
- name: `?ScCanonDriverImagePath@@YAKKPEAGPEAPEAG@Z`
- size: `933`
- prototype: `__int64 __fastcall(int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, loader_planting`

## callers

- `0x140066ef4`
- `0x140068b60`

## callees

- `0x140008b90`
- `0x14000cee0`
- `0x140010010`
- `0x1400188fc`
- `0x14001df34`
- `0x14001f99c`
- `0x14004af50`
- `0x1400661a0`
- `0x140066848`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x14006645f`
- `ntdll!RtlFreeUnicodeString` at `0x14006648e`
- `ntdll!RtlFreeUnicodeString` at `0x14006645f`
- `ntdll!RtlFreeUnicodeString` at `0x14006648e`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400663f8`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400663f8`
- `ntdll!RtlFreeHeap` at `0x1400664df`
- `ntdll!RtlFreeHeap` at `0x1400664f9`
- `ntdll!RtlFreeHeap` at `0x1400664df`
- `ntdll!RtlFreeHeap` at `0x1400664f9`
- `ntdll!RtlAllocateHeap` at `0x14006624c`
- `ntdll!RtlAllocateHeap` at `0x1400662f6`
- `ntdll!RtlAllocateHeap` at `0x14006639e`
- `ntdll!RtlAllocateHeap` at `0x140066428`
- `ntdll!RtlAllocateHeap` at `0x14006624c`
- `ntdll!RtlAllocateHeap` at `0x1400662f6`
- `ntdll!RtlAllocateHeap` at `0x14006639e`
- `ntdll!RtlAllocateHeap` at `0x140066428`

## pseudocode

```c
__int64 __fastcall ScCanonDriverImagePath(int a1, unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v6; // rsi
  SIZE_T v7; // r8
  unsigned __int64 v8; // rsi
  unsigned __int16 *Heap; // rax
  PRPC_ASYNC_STATE v10; // rcx
  __int64 v11; // rdx
  const unsigned __int16 *v12; // r8
  PRPC_ASYNC_STATE v13; // rcx
  __int64 v14; // rdx
  SIZE_T v15; // r8
  unsigned __int64 v16; // rsi
  unsigned __int16 *v17; // rax
  SIZE_T v18; // r8
  unsigned __int64 v19; // rsi
  unsigned __int16 *v20; // rax
  SIZE_T v22; // rsi
  unsigned __int16 *v23; // rax
  size_t *v24; // r8
  unsigned int v25; // edi
  struct _UNICODE_STRING NtPathName; // [rsp+30h] [rbp-38h] BYREF
  PVOID P; // [rsp+88h] [rbp+20h] BYREF

  NtPathName = 0;
  P = 0;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 0x40) != 0 )
    WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 88, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, a2);
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( (unsigned int)v6 > 0xC && !wcsnicmp(L"\\SystemRoot\\", a2, 0xCu) )
  {
    v7 = 2LL * (unsigned int)(v6 + 1);
    v8 = (unsigned int)(v6 + 1);
    Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    *a3 = Heap;
    if ( !Heap )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        return 8;
      v11 = 89;
LABEL_35:
      WPP_SF_(v10->StubInfo, v11, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids);
      return 8;
    }
    v12 = a2 + 12;
    if ( a1 )
      v12 = a2;
    StringCchCopyW(Heap, v8, v12);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 0x40) == 0 )
    {
      return 0;
    }
    v14 = 90;
    goto LABEL_55;
  }
  if ( (unsigned int)v6 > 0xD && !wcsnicmp(L"%SystemRoot%\\", a2, 0xDu) )
  {
    v15 = 2LL * (unsigned int)(v6 + 1);
    v16 = (unsigned int)(v6 + 1);
    v17 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v15);
    *a3 = v17;
    if ( !v17 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        return 8;
      v11 = 91;
      goto LABEL_35;
    }
    if ( a1 )
      StringCchCopyW(v17, v16, L"\\SystemRoot\\");
    else
      *v17 = 0;
    StringCchCatW(*a3, v16, a2 + 13);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 0x40) == 0 )
    {
      return 0;
    }
    v14 = 92;
    goto LABEL_55;
  }
  if ( *a2 != 92 && a2[1] != 58 )
  {
    v18 = 2LL * (unsigned int)(v6 + 1);
    v19 = (unsigned int)(v6 + 1);
    v20 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
    *a3 = v20;
    if ( !v20 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        return 8;
      v11 = 93;
      goto LABEL_35;
    }
    StringCchCopyW(v20, v19, a2);
    return 0;
  }
  if ( !RtlDosPathNameToNtPathName_U(a2, &NtPathName, 0, 0) )
    return 87;
  v22 = (unsigned int)NtPathName.Length + 2;
  v23 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
  *a3 = v23;
  if ( !v23 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 94, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids);
    RtlFreeUnicodeString(&NtPathName);
    return 8;
  }
  if ( v22 >> 1 )
    StringCopyWorkerW(v23, v22 >> 1, v24, NtPathName.Buffer, (unsigned __int64)NtPathName.Length >> 1);
  RtlFreeUnicodeString(&NtPathName);
  if ( a1 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 0x40) == 0 )
    {
      return 0;
    }
    v14 = 95;
LABEL_55:
    WPP_SF_S(v13->StubInfo, v14, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, *a3);
    return 0;
  }
  v25 = ScConvertToBootPathName(*a3, (unsigned __int16 **)&P);
  if ( v25 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a3);
    *a3 = 0;
  }
  else
  {
    StringCbCopyW(*a3, v22, (const unsigned __int16 *)P + 12);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return v25;
}

```

## disassembly

```asm
0x1400661a0  mov     rax, rsp
0x1400661a3  mov     [rax+8], rbx
0x1400661a7  mov     [rax+10h], rbp
0x1400661ab  push    rsi
0x1400661ac  push    rdi
0x1400661ad  push    r12
0x1400661af  push    r14
0x1400661b1  push    r15
0x1400661b3  sub     rsp, 40h
0x1400661b7  xorps   xmm0, xmm0
0x1400661ba  xor     r14d, r14d
0x1400661bd  movups  xmmword ptr [rax-38h], xmm0
0x1400661c1  mov     [rax+20h], r14
0x1400661c5  mov     rbx, r8
0x1400661c8  mov     rdi, rdx
0x1400661cb  mov     ebp, ecx
0x1400661cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400661d4  lea     r15, WPP_GLOBAL_Control
0x1400661db  lea     r12, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x1400661e2  cmp     rcx, r15
0x1400661e5  jz      short loc_140066200
0x1400661e7  test    byte ptr [rcx+1Ch], 40h
0x1400661eb  jz      short loc_140066200
0x1400661ed  mov     rcx, [rcx+10h]
0x1400661f1  lea     edx, [r14+58h]
0x1400661f5  mov     r9, rdi
0x1400661f8  mov     r8, r12
0x1400661fb  call    WPP_SF_S
0x140066200  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140066204  inc     rsi
0x140066207  cmp     [rdi+rsi*2], r14w
0x14006620c  jnz     short loc_140066204
0x14006620e  mov     r8d, 0Ch; MaxCount
0x140066214  cmp     esi, r8d
0x140066217  jbe     loc_1400662B5
0x14006621d  mov     rdx, rdi; String2
0x140066220  lea     rcx, aSystemroot_0; "\\SystemRoot\\"
0x140066227  call    _wcsnicmp
0x14006622c  test    eax, eax
0x14006622e  jnz     loc_1400662B5
0x140066234  mov     rcx, gs:60h
0x14006623d  lea     eax, [rsi+1]
0x140066240  lea     r8, [rax+rax]; Size
0x140066244  mov     esi, eax
0x140066246  xor     edx, edx; Flags
0x140066248  mov     rcx, [rcx+30h]; HeapHandle
0x14006624c  call    cs:__imp_RtlAllocateHeap
0x140066252  mov     [rbx], rax
0x140066255  test    rax, rax
0x140066258  jnz     short loc_14006627C
0x14006625a  mov     rcx, cs:WPP_GLOBAL_Control
0x140066261  cmp     rcx, r15
0x140066264  jz      loc_1400663CD
0x14006626a  test    byte ptr [rcx+1Ch], 1
0x14006626e  jz      loc_1400663CD
0x140066274  lea     edx, [rax+59h]
0x140066277  jmp     loc_1400663C1
0x14006627c  test    ebp, ebp
0x14006627e  lea     r8, [rdi+18h]
0x140066282  mov     rdx, rsi; unsigned __int64
0x140066285  mov     rcx, rax; unsigned __int16 *
0x140066288  cmovnz  r8, rdi; unsigned __int16 *
0x14006628c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140066291  mov     rcx, cs:WPP_GLOBAL_Control
0x140066298  cmp     rcx, r15
0x14006629b  jz      loc_14006652C
0x1400662a1  test    byte ptr [rcx+1Ch], 40h
0x1400662a5  jz      loc_14006652C
0x1400662ab  mov     edx, 5Ah ; 'Z'
0x1400662b0  jmp     loc_14006651D
0x1400662b5  mov     r8d, 0Dh; MaxCount
0x1400662bb  cmp     esi, r8d
0x1400662be  jbe     loc_140066375
0x1400662c4  mov     rdx, rdi; String2
0x1400662c7  lea     rcx, aSystemroot_1; "%SystemRoot%\\"
0x1400662ce  call    _wcsnicmp
0x1400662d3  test    eax, eax
0x1400662d5  jnz     loc_140066375
0x1400662db  mov     rcx, gs:60h
0x1400662e4  lea     eax, [rsi+1]
0x1400662e7  lea     r8, [rax+rax]; Size
0x1400662eb  mov     esi, eax
0x1400662ed  mov     edx, 8; Flags
0x1400662f2  mov     rcx, [rcx+30h]; HeapHandle
0x1400662f6  call    cs:__imp_RtlAllocateHeap
0x1400662fc  mov     [rbx], rax
0x1400662ff  mov     rcx, rax; unsigned __int16 *
0x140066302  test    rax, rax
0x140066305  jnz     short loc_140066329
0x140066307  mov     rcx, cs:WPP_GLOBAL_Control
0x14006630e  cmp     rcx, r15
0x140066311  jz      loc_1400663CD
0x140066317  test    byte ptr [rcx+1Ch], 1
0x14006631b  jz      loc_1400663CD
0x140066321  lea     edx, [rax+5Bh]
0x140066324  jmp     loc_1400663C1
0x140066329  test    ebp, ebp
0x14006632b  jz      short loc_14006633E
0x14006632d  lea     r8, aSystemroot_0; "\\SystemRoot\\"
0x140066334  mov     rdx, rsi; unsigned __int64
0x140066337  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14006633c  jmp     short loc_140066342
0x14006633e  mov     [rax], r14w
0x140066342  mov     rcx, [rbx]; unsigned __int16 *
0x140066345  lea     r8, [rdi+1Ah]; unsigned __int16 *
0x140066349  mov     rdx, rsi; unsigned __int64
0x14006634c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140066351  mov     rcx, cs:WPP_GLOBAL_Control
0x140066358  cmp     rcx, r15
0x14006635b  jz      loc_14006652C
0x140066361  test    byte ptr [rcx+1Ch], 40h
0x140066365  jz      loc_14006652C
0x14006636b  mov     edx, 5Ch ; '\'
0x140066370  jmp     loc_14006651D
0x140066375  mov     eax, 5Ch ; '\'
0x14006637a  cmp     [rdi], ax
0x14006637d  jz      short loc_1400663EA
0x14006637f  cmp     word ptr [rdi+2], 3Ah ; ':'
0x140066384  jz      short loc_1400663EA
0x140066386  mov     rcx, gs:60h
0x14006638f  lea     eax, [rsi+1]
0x140066392  lea     r8, [rax+rax]; Size
0x140066396  mov     esi, eax
0x140066398  xor     edx, edx; Flags
0x14006639a  mov     rcx, [rcx+30h]; HeapHandle
0x14006639e  call    cs:__imp_RtlAllocateHeap
0x1400663a4  mov     [rbx], rax
0x1400663a7  test    rax, rax
0x1400663aa  jnz     short loc_1400663D7
0x1400663ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400663b3  cmp     rcx, r15
0x1400663b6  jz      short loc_1400663CD
0x1400663b8  test    byte ptr [rcx+1Ch], 1
0x1400663bc  jz      short loc_1400663CD
0x1400663be  lea     edx, [rax+5Dh]
0x1400663c1  mov     rcx, [rcx+10h]
0x1400663c5  mov     r8, r12
0x1400663c8  call    WPP_SF_
0x1400663cd  mov     eax, 8
0x1400663d2  jmp     loc_14006652E
0x1400663d7  mov     r8, rdi; unsigned __int16 *
0x1400663da  mov     rdx, rsi; unsigned __int64
0x1400663dd  mov     rcx, rax; unsigned __int16 *
0x1400663e0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400663e5  jmp     loc_14006652C
0x1400663ea  xor     r9d, r9d; DirectoryInfo
0x1400663ed  lea     rdx, [rsp+68h+NtPathName]; NtPathName
0x1400663f2  xor     r8d, r8d; NtFileNamePart
0x1400663f5  mov     rcx, rdi; DosPathName
0x1400663f8  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1400663fe  test    al, al
0x140066400  jnz     short loc_14006640C
0x140066402  mov     eax, 57h ; 'W'
0x140066407  jmp     loc_14006652E
0x14006640c  mov     rcx, gs:60h
0x140066415  xor     edx, edx; Flags
0x140066417  movzx   eax, [rsp+68h+NtPathName.Length]
0x14006641c  add     eax, 2
0x14006641f  mov     r8d, eax; Size
0x140066422  mov     rcx, [rcx+30h]; HeapHandle
0x140066426  mov     esi, eax
0x140066428  call    cs:__imp_RtlAllocateHeap
0x14006642e  mov     [rbx], rax
0x140066431  mov     rcx, rax; pszDest
0x140066434  test    rax, rax
0x140066437  jnz     short loc_14006646A
0x140066439  mov     rcx, cs:WPP_GLOBAL_Control
0x140066440  cmp     rcx, r15
0x140066443  jz      short loc_14006645A
0x140066445  test    byte ptr [rcx+1Ch], 1
0x140066449  jz      short loc_14006645A
0x14006644b  mov     rcx, [rcx+10h]
0x14006644f  lea     edx, [rax+5Eh]
0x140066452  mov     r8, r12
0x140066455  call    WPP_SF_
0x14006645a  lea     rcx, [rsp+68h+NtPathName]; UnicodeString
0x14006645f  call    cs:__imp_RtlFreeUnicodeString
0x140066465  jmp     loc_1400663CD
0x14006646a  mov     rdx, rsi
0x14006646d  shr     rdx, 1; cchDest
0x140066470  jz      short loc_140066489
0x140066472  movzx   eax, [rsp+68h+NtPathName.Length]
0x140066477  mov     r9, [rsp+68h+NtPathName.Buffer]; pszSrc
0x14006647c  shr     rax, 1
0x14006647f  mov     [rsp+68h+cchToCopy], rax; cchToCopy
0x140066484  call    StringCopyWorkerW
0x140066489  lea     rcx, [rsp+68h+NtPathName]; UnicodeString
0x14006648e  call    cs:__imp_RtlFreeUnicodeString
0x140066494  test    ebp, ebp
0x140066496  jnz     short loc_140066506
0x140066498  mov     rcx, [rbx]; unsigned __int16 *
0x14006649b  lea     rdx, [rsp+68h+P]; unsigned __int16 **
0x1400664a3  call    ?ScConvertToBootPathName@@YAKPEAGPEAPEAG@Z; ScConvertToBootPathName(ushort *,ushort * *)
0x1400664a8  mov     edi, eax
0x1400664aa  mov     rax, [rbx]
0x1400664ad  test    edi, edi
0x1400664af  jnz     short loc_1400664E7
0x1400664b1  mov     r8, [rsp+68h+P]
0x1400664b9  mov     rdx, rsi; unsigned __int64
0x1400664bc  add     r8, 18h; unsigned __int16 *
0x1400664c0  mov     rcx, rax; unsigned __int16 *
0x1400664c3  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1400664c8  mov     rcx, gs:60h
0x1400664d1  xor     edx, edx; Flags
0x1400664d3  mov     r8, [rsp+68h+P]; P
0x1400664db  mov     rcx, [rcx+30h]; HeapHandle
0x1400664df  call    cs:__imp_RtlFreeHeap
0x1400664e5  jmp     short loc_140066502
0x1400664e7  mov     rcx, gs:60h
0x1400664f0  mov     r8, rax; P
0x1400664f3  xor     edx, edx; Flags
0x1400664f5  mov     rcx, [rcx+30h]; HeapHandle
0x1400664f9  call    cs:__imp_RtlFreeHeap
0x1400664ff  mov     [rbx], r14
0x140066502  mov     eax, edi
0x140066504  jmp     short loc_14006652E
0x140066506  mov     rcx, cs:WPP_GLOBAL_Control
0x14006650d  cmp     rcx, r15
0x140066510  jz      short loc_14006652C
0x140066512  test    byte ptr [rcx+1Ch], 40h
0x140066516  jz      short loc_14006652C
0x140066518  mov     edx, 5Fh ; '_'
0x14006651d  mov     r9, [rbx]
0x140066520  mov     r8, r12
0x140066523  mov     rcx, [rcx+10h]
0x140066527  call    WPP_SF_S
0x14006652c  xor     eax, eax
0x14006652e  mov     rbx, [rsp+68h+arg_0]
0x140066533  mov     rbp, [rsp+68h+arg_8]
0x140066538  add     rsp, 40h
0x14006653c  pop     r15
0x14006653e  pop     r14
0x140066540  pop     r12
0x140066542  pop     rdi
0x140066543  pop     rsi
0x140066544  retn
```
