# UdfSeqCacheWriteCheckPOW

- ea: `0x14001b37c`
- end: `0x14001b595`
- name: `UdfSeqCacheWriteCheckPOW`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140007b90`

## callees

- `0x14001b37c`
- `0x14001c080`
- `0x14002e99c`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14001b45c`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14001b4c4`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14001b45c`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x14001b4c4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b572`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b572`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x14001b50c`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x14001b50c`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14001b529`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14001b529`

## pseudocode

```c
char __fastcall UdfSeqCacheWriteCheckPOW(int a1, __int64 a2, unsigned int a3, _DWORD *a4, unsigned int *a5, _BYTE *a6)
{
  LONGLONG v6; // rbx
  int v10; // ecx
  _BYTE *v11; // rsi
  char result; // al
  unsigned int *v13; // rdx
  unsigned int v14; // ecx
  LONGLONG v15; // r12
  BOOLEAN v16; // bl
  unsigned int *v17; // rdx
  unsigned int v18; // ecx
  _DWORD *v19; // rsi
  LONGLONG v20; // r8
  __int64 v21; // rax
  int v22; // eax
  _DWORD *v23; // rdx
  __int64 v24; // rax
  __int64 SectorCountFromLbn; // [rsp+40h] [rbp-89h] BYREF
  unsigned int v26; // [rsp+48h] [rbp-81h] BYREF
  __int64 StartingLbn; // [rsp+50h] [rbp-79h] BYREF
  __int64 Lbn; // [rsp+58h] [rbp-71h] BYREF
  _BYTE v29[176]; // [rsp+60h] [rbp-69h] BYREF
  int v30; // [rsp+128h] [rbp+5Fh] BYREF

  v6 = a3;
  Lbn = 0;
  SectorCountFromLbn = 0;
  StartingLbn = 0;
  v30 = 0;
  v26 = 0;
  memset(v29, 0, 0x68u);
  v11 = a6;
  *a6 = 0;
  if ( (*(_DWORD *)(a2 + 212) & 0x80u) == 0 )
  {
    UdfAcquireResource(v29, *(_QWORD *)(a2 + 16), 0, 0);
    v15 = v6;
    v16 = FsRtlLookupLargeMcbEntry((PLARGE_MCB)(a2 + 232), v6, &Lbn, &SectorCountFromLbn, &StartingLbn, 0, 0);
    if ( !v16 || StartingLbn == -1 )
    {
      v16 = FsRtlLookupLargeMcbEntry((PLARGE_MCB)(a2 + 264), v15, &Lbn, &SectorCountFromLbn, &StartingLbn, 0, 0);
      if ( !v16 || StartingLbn == -1 )
      {
        v16 = 1;
        goto LABEL_24;
      }
      if ( StartingLbn < 0x80000000LL )
      {
        v19 = a5;
        v20 = SectorCountFromLbn;
        v21 = *a5;
        if ( SectorCountFromLbn >= v21 )
        {
          v20 = (unsigned int)v21;
          SectorCountFromLbn = *a5;
        }
        FsRtlRemoveLargeMcbEntry((PLARGE_MCB)(a2 + 264), v15, v20);
        v16 = FsRtlAddLargeMcbEntry((PLARGE_MCB)(a2 + 264), v15, 0x80000000LL, SectorCountFromLbn);
        if ( v16 )
        {
          v22 = SectorCountFromLbn;
          *a4 = 0;
          *v19 = v22;
        }
        goto LABEL_24;
      }
      v23 = a5;
      v24 = SectorCountFromLbn;
      *a4 = 0;
      if ( v24 >= (unsigned int)*v23 )
      {
        LODWORD(v24) = *v23;
        SectorCountFromLbn = (unsigned int)*v23;
      }
      *v23 = v24;
    }
    else
    {
      v17 = a5;
      *a4 = Lbn;
      v18 = SectorCountFromLbn;
      if ( SectorCountFromLbn >= *v17 )
      {
        v18 = *v17;
        SectorCountFromLbn = *v17;
      }
      *v17 = v18;
    }
    *v11 = 1;
LABEL_24:
    ExReleaseResourceLite(*(PERESOURCE *)(a2 + 16));
    return v16;
  }
  result = UdfVmcbVbnToLbn(v10, a1 + 984, v6, (unsigned int)&v30, (__int64)&v26);
  if ( result )
  {
    v13 = a5;
    v14 = v26;
    *a4 = v30;
    if ( *v13 < v14 )
      v14 = *v13;
    result = 1;
    *v13 = v14;
    *v11 = 1;
  }
  return result;
}

```

## disassembly

```asm
0x14001b37c  push    rbp
0x14001b37e  push    rbx
0x14001b37f  push    rsi
0x14001b380  push    rdi
0x14001b381  push    r12
0x14001b383  push    r13
0x14001b385  push    r14
0x14001b387  push    r15
0x14001b389  lea     rbp, [rsp-0Fh]
0x14001b38e  sub     rsp, 0D8h
0x14001b395  xor     r13d, r13d
0x14001b398  mov     ebx, r8d
0x14001b39b  mov     r14, rdx
0x14001b39e  mov     [rbp+47h+Lbn], r13
0x14001b3a2  mov     r15, rcx
0x14001b3a5  mov     [rsp+110h+SectorCountFromLbn], r13
0x14001b3aa  xor     edx, edx; Val
0x14001b3ac  mov     [rbp+47h+var_C0], r13
0x14001b3b0  lea     r8d, [r13+68h]; Size
0x14001b3b4  mov     [rbp+47h+arg_8], r13d
0x14001b3b8  lea     rcx, [rbp+47h+var_B0]; void *
0x14001b3bc  mov     [rsp+110h+var_C8], r13d
0x14001b3c1  mov     rdi, r9
0x14001b3c4  call    memset
0x14001b3c9  mov     rsi, [rbp+47h+arg_28]
0x14001b3cd  mov     [rsi], r13b
0x14001b3d0  mov     eax, [r14+0D4h]
0x14001b3d7  test    al, al
0x14001b3d9  jns     short loc_14001B420
0x14001b3db  lea     rax, [rsp+110h+var_C8]
0x14001b3e0  mov     r8d, ebx
0x14001b3e3  lea     rdx, [r15+3D8h]
0x14001b3ea  mov     [rsp+110h+StartingLbn], rax
0x14001b3ef  lea     r9, [rbp+47h+arg_8]
0x14001b3f3  call    UdfVmcbVbnToLbn
0x14001b3f8  test    al, al
0x14001b3fa  jz      loc_14001B580
0x14001b400  mov     rdx, [rbp+47h+arg_20]
0x14001b404  mov     eax, [rbp+47h+arg_8]
0x14001b407  mov     ecx, [rsp+110h+var_C8]
0x14001b40b  mov     [rdi], eax
0x14001b40d  mov     eax, [rdx]
0x14001b40f  cmp     eax, ecx
0x14001b411  cmovb   ecx, eax
0x14001b414  mov     al, 1
0x14001b416  mov     [rdx], ecx
0x14001b418  mov     byte ptr [rsi], 1
0x14001b41b  jmp     loc_14001B580
0x14001b420  mov     rdx, [r14+10h]
0x14001b424  lea     rcx, [rbp+47h+var_B0]
0x14001b428  xor     r9d, r9d
0x14001b42b  xor     r8d, r8d
0x14001b42e  call    UdfAcquireResource
0x14001b433  lea     rax, [rbp+47h+var_C0]
0x14001b437  mov     [rsp+110h+Index], r13; Index
0x14001b43c  lea     rcx, [r14+0E8h]; Mcb
0x14001b443  mov     [rsp+110h+SectorCountFromStartingLbn], r13; SectorCountFromStartingLbn
0x14001b448  lea     r9, [rsp+110h+SectorCountFromLbn]; SectorCountFromLbn
0x14001b44d  mov     [rsp+110h+StartingLbn], rax; StartingLbn
0x14001b452  lea     r8, [rbp+47h+Lbn]; Lbn
0x14001b456  mov     rdx, rbx; Vbn
0x14001b459  mov     r12, rbx
0x14001b45c  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x14001b463  nop     dword ptr [rax+rax+00h]
0x14001b468  mov     bl, al
0x14001b46a  test    al, al
0x14001b46c  jz      short loc_14001B49B
0x14001b46e  cmp     [rbp+47h+var_C0], 0FFFFFFFFFFFFFFFFh
0x14001b473  jz      short loc_14001B49B
0x14001b475  mov     ecx, dword ptr [rbp+47h+Lbn]
0x14001b478  mov     rdx, [rbp+47h+arg_20]
0x14001b47c  mov     [rdi], ecx
0x14001b47e  mov     rcx, [rsp+110h+SectorCountFromLbn]
0x14001b483  mov     eax, [rdx]
0x14001b485  cmp     rcx, rax
0x14001b488  jl      short loc_14001B491
0x14001b48a  mov     ecx, eax
0x14001b48c  mov     [rsp+110h+SectorCountFromLbn], rax
0x14001b491  mov     [rdx], ecx
0x14001b493  mov     byte ptr [rsi], 1
0x14001b496  jmp     loc_14001B56E
0x14001b49b  mov     [rsp+110h+Index], r13; Index
0x14001b4a0  lea     rax, [rbp+47h+var_C0]
0x14001b4a4  lea     r15, [r14+108h]
0x14001b4ab  mov     [rsp+110h+SectorCountFromStartingLbn], r13; SectorCountFromStartingLbn
0x14001b4b0  mov     rcx, r15; Mcb
0x14001b4b3  mov     [rsp+110h+StartingLbn], rax; StartingLbn
0x14001b4b8  lea     r9, [rsp+110h+SectorCountFromLbn]; SectorCountFromLbn
0x14001b4bd  mov     rdx, r12; Vbn
0x14001b4c0  lea     r8, [rbp+47h+Lbn]; Lbn
0x14001b4c4  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x14001b4cb  nop     dword ptr [rax+rax+00h]
0x14001b4d0  mov     bl, al
0x14001b4d2  test    al, al
0x14001b4d4  jz      loc_14001B56C
0x14001b4da  mov     rax, [rbp+47h+var_C0]
0x14001b4de  mov     ecx, 80000000h
0x14001b4e3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001b4e7  jz      short loc_14001B546
0x14001b4e9  cmp     rax, rcx
0x14001b4ec  jge     short loc_14001B54B
0x14001b4ee  mov     rsi, [rbp+47h+arg_20]
0x14001b4f2  mov     r8, [rsp+110h+SectorCountFromLbn]
0x14001b4f7  mov     eax, [rsi]
0x14001b4f9  cmp     r8, rax
0x14001b4fc  jl      short loc_14001B506
0x14001b4fe  mov     r8d, eax; SectorCount
0x14001b501  mov     [rsp+110h+SectorCountFromLbn], rax
0x14001b506  mov     rdx, r12; Vbn
0x14001b509  mov     rcx, r15; Mcb
0x14001b50c  call    cs:__imp_FsRtlRemoveLargeMcbEntry
0x14001b513  nop     dword ptr [rax+rax+00h]
0x14001b518  mov     r9, [rsp+110h+SectorCountFromLbn]; SectorCount
0x14001b51d  mov     r8d, 80000000h; Lbn
0x14001b523  mov     rdx, r12; Vbn
0x14001b526  mov     rcx, r15; Mcb
0x14001b529  call    cs:__imp_FsRtlAddLargeMcbEntry
0x14001b530  nop     dword ptr [rax+rax+00h]
0x14001b535  mov     bl, al
0x14001b537  test    al, al
0x14001b539  jz      short loc_14001B56E
0x14001b53b  mov     eax, dword ptr [rsp+110h+SectorCountFromLbn]
0x14001b53f  mov     [rdi], r13d
0x14001b542  mov     [rsi], eax
0x14001b544  jmp     short loc_14001B56E
0x14001b546  cmp     rax, rcx
0x14001b549  jl      short loc_14001B56C
0x14001b54b  mov     rdx, [rbp+47h+arg_20]
0x14001b54f  mov     rax, [rsp+110h+SectorCountFromLbn]
0x14001b554  mov     [rdi], r13d
0x14001b557  mov     ecx, [rdx]
0x14001b559  cmp     rax, rcx
0x14001b55c  jl      short loc_14001B565
0x14001b55e  mov     eax, ecx
0x14001b560  mov     [rsp+110h+SectorCountFromLbn], rcx
0x14001b565  mov     [rdx], eax
0x14001b567  jmp     loc_14001B493
0x14001b56c  mov     bl, 1
0x14001b56e  mov     rcx, [r14+10h]; Resource
0x14001b572  call    cs:__imp_ExReleaseResourceLite
0x14001b579  nop     dword ptr [rax+rax+00h]
0x14001b57e  mov     al, bl
0x14001b580  add     rsp, 0D8h
0x14001b587  pop     r15
0x14001b589  pop     r14
0x14001b58b  pop     r13
0x14001b58d  pop     r12
0x14001b58f  pop     rdi
0x14001b590  pop     rsi
0x14001b591  pop     rbx
0x14001b592  pop     rbp
0x14001b593  retn
```
