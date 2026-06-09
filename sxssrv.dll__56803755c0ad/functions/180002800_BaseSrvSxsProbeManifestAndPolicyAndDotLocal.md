# BaseSrvSxsProbeManifestAndPolicyAndDotLocal

- ea: `0x180002800`
- end: `0x180002c48`
- name: `BaseSrvSxsProbeManifestAndPolicyAndDotLocal`
- size: `1096`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, __int64, unsigned __int16 *, unsigned __int16 *, int, __int64, __int64, __int64, __int64, _OWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting`

## callers

- `0x180001d80`

## callees

- `0x180002800`
- `0x180002c50`
- `0x180003e70`
- `0x1800040f0`
- `0x180006c07`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180002b2f`
- `ntdll!RtlFreeHeap` at `0x180002c03`
- `ntdll!RtlFreeHeap` at `0x180002c26`
- `ntdll!RtlFreeHeap` at `0x180002b2f`
- `ntdll!RtlFreeHeap` at `0x180002c03`
- `ntdll!RtlFreeHeap` at `0x180002c26`
- `ntdll!RtlpApplyLengthFunction` at `0x180002ad3`
- `ntdll!RtlpApplyLengthFunction` at `0x180002ad3`
- `ntdll!RtlAllocateHeap` at `0x180002936`
- `ntdll!RtlAllocateHeap` at `0x1800029cf`
- `ntdll!RtlAllocateHeap` at `0x180002a85`
- `ntdll!RtlAllocateHeap` at `0x180002936`
- `ntdll!RtlAllocateHeap` at `0x1800029cf`
- `ntdll!RtlAllocateHeap` at `0x180002a85`
- `ntdll!RtlAppendUnicodeToString` at `0x180002985`
- `ntdll!RtlAppendUnicodeToString` at `0x180002a0a`
- `ntdll!RtlAppendUnicodeToString` at `0x180002985`
- `ntdll!RtlAppendUnicodeToString` at `0x180002a0a`
- `ntdll!RtlGetLengthWithoutLastFullDosOrNtPathElement` at `0x180002ab5`
- `CSRSRV!CsrRevertToSelf` at `0x180002c37`
- `CSRSRV!CsrRevertToSelf` at `0x180002c37`
- `CSRSRV!CsrImpersonateClient` at `0x180002a22`
- `CSRSRV!CsrImpersonateClient` at `0x180002a22`

## string_xrefs

- `0x180002976`: `.Config`
- `0x1800029fb`: `.Config`

## pseudocode

```c
__int64 __fastcall BaseSrvSxsProbeManifestAndPolicyAndDotLocal(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        _OWORD *a13,
        _DWORD *a14)
{
  WCHAR *v15; // r12
  WCHAR *v16; // rdi
  void *v17; // r13
  __int64 result; // rax
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  unsigned __int16 v21; // cx
  WCHAR *v22; // rax
  NTSTATUS appended; // ebx
  unsigned __int16 v24; // cx
  WCHAR *v25; // rax
  const void **v26; // r15
  __int64 v27; // rcx
  char v28; // si
  int FileStream; // eax
  PVOID Heap; // rax
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  __int128 UnicodeStringOrUnicodeStringBuffer; // [rsp+58h] [rbp-39h] BYREF
  struct _UNICODE_STRING v34; // [rsp+68h] [rbp-29h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+78h] [rbp-19h] BYREF
  _QWORD v36[2]; // [rsp+88h] [rbp-9h] BYREF
  __int64 v37; // [rsp+D0h] [rbp+3Fh]

  v37 = a2;
  v36[0] = &v34;
  v36[1] = &Destination;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v34 = 0;
  Destination = 0;
  UnicodeStringOrUnicodeStringBuffer = 0;
  if ( a1 )
  {
    *a14 |= 0x2000u;
    v19 = *(_OWORD *)(a1 + 16);
    *(_OWORD *)a10 = *(_OWORD *)a1;
    v20 = *(_OWORD *)(a1 + 32);
    *(_OWORD *)(a10 + 16) = v19;
    *(_QWORD *)&v19 = *(_QWORD *)(a1 + 48);
    *(_OWORD *)(a10 + 32) = v20;
    *(_QWORD *)(a10 + 48) = v19;
  }
  else
  {
    result = BaseSrvSxsCheckManifestAndDotLocal((_DWORD)a6, (_DWORD)a7, a3, a4, a5, a8, a9, a10, (__int64)a14);
    if ( (int)result < 0 )
      return result;
    a2 = v37;
  }
  if ( (*a14 & 0x2000) == 0 )
    return 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v31 = *(_OWORD *)(a2 + 16);
      *(_OWORD *)a12 = *(_OWORD *)a2;
      v32 = *(_OWORD *)(a2 + 32);
      *(_OWORD *)(a12 + 16) = v31;
      *(_QWORD *)&v31 = *(_QWORD *)(a2 + 48);
      *(_OWORD *)(a12 + 32) = v32;
      *(_QWORD *)(a12 + 48) = v31;
    }
    v26 = (const void **)(a6 + 4);
    v28 = 0;
LABEL_21:
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, a6[1]);
    v17 = Heap;
    if ( Heap )
    {
      memcpy_0(Heap, *v26, *a6);
      LODWORD(UnicodeStringOrUnicodeStringBuffer) = *(_DWORD *)a6;
      *((_QWORD *)&UnicodeStringOrUnicodeStringBuffer + 1) = v17;
      appended = RtlpApplyLengthFunction(
                   0,
                   0x10u,
                   &UnicodeStringOrUnicodeStringBuffer,
                   RtlGetLengthWithoutLastFullDosOrNtPathElement);
      if ( appended >= 0 )
      {
        v17 = 0;
        appended = 0;
        *(_WORD *)(*((_QWORD *)&UnicodeStringOrUnicodeStringBuffer + 1)
                 + 2 * ((unsigned __int64)(unsigned __int16)UnicodeStringOrUnicodeStringBuffer >> 1)) = 0;
        *a13 = UnicodeStringOrUnicodeStringBuffer;
      }
    }
    else
    {
      appended = -1073741801;
    }
    if ( !v16 )
      goto LABEL_25;
    goto LABEL_34;
  }
  v21 = *a7;
  if ( *a7 > 0xFFEFu )
    return 3221225734LL;
  Destination.Length = *a7;
  if ( (unsigned __int16)(v21 + 16) < v21 )
    return 3221225621LL;
  Destination.MaximumLength = v21 + 16;
  v22 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned __int16)(v21 + 16));
  v16 = v22;
  if ( !v22 )
    return 3221225495LL;
  memcpy_0(v22, *((const void **)a7 + 1), *a7);
  Destination.Buffer = v16;
  appended = RtlAppendUnicodeToString(&Destination, L".Config");
  if ( appended < 0 )
    goto LABEL_33;
  v24 = *a6;
  if ( *a6 > 0xFFEFu )
  {
    appended = -1073741562;
    goto LABEL_33;
  }
  v34.Length = *a6;
  if ( (unsigned __int16)(v24 + 16) < v24 )
  {
    appended = -1073741675;
    v34.MaximumLength = -1;
    goto LABEL_33;
  }
  v34.MaximumLength = v24 + 16;
  v25 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned __int16)(v24 + 16));
  v15 = v25;
  if ( !v25 )
  {
    appended = -1073741801;
    goto LABEL_33;
  }
  v26 = (const void **)(a6 + 4);
  memcpy_0(v25, *((const void **)a6 + 1), *a6);
  v34.Buffer = v15;
  appended = RtlAppendUnicodeToString(&v34, L".Config");
  if ( appended < 0 )
  {
LABEL_33:
    v28 = 0;
    goto LABEL_34;
  }
  v28 = CsrImpersonateClient(0);
  if ( !v28 )
  {
    appended = -1073741659;
    goto LABEL_34;
  }
  FileStream = BasepSxsCreateFileStreamEx(v27, v36, 0, a11, a12);
  appended = FileStream;
  if ( FileStream >= 0 )
  {
    v15 = 0;
    *(_BYTE *)(a12 + 2) = 5;
    goto LABEL_21;
  }
  if ( (unsigned int)BasepSxsIsStatusFileNotFoundEtc((unsigned int)FileStream) )
    goto LABEL_21;
LABEL_34:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
LABEL_25:
  if ( v15 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  if ( v17 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
  if ( v28 )
    CsrRevertToSelf();
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180002800  mov     r11, rsp
0x180002803  mov     [r11+8], rbx
0x180002807  mov     [r11+18h], rsi
0x18000280b  mov     [r11+20h], rdi
0x18000280f  mov     [r11+10h], rdx
0x180002813  push    rbp
0x180002814  push    r12
0x180002816  push    r13
0x180002818  push    r14
0x18000281a  push    r15
0x18000281c  lea     rbp, [r11-2Fh]
0x180002820  sub     rsp, 90h
0x180002827  mov     r14, [rbp+27h+arg_28]
0x18000282b  lea     rax, [rbp+27h+var_50]
0x18000282f  mov     rsi, [rbp+27h+arg_68]
0x180002836  xor     r10d, r10d
0x180002839  mov     r15, [rbp+27h+arg_30]
0x18000283d  xorps   xmm0, xmm0
0x180002840  mov     [rbp+27h+var_30], rax
0x180002844  lea     rax, [rbp+27h+Destination]
0x180002848  mov     [rbp+27h+var_28], rax
0x18000284c  xorps   xmm1, xmm1
0x18000284f  mov     rbx, rcx
0x180002852  mov     r12d, r10d
0x180002855  mov     edi, r10d
0x180002858  mov     r13d, r10d
0x18000285b  movups  xmmword ptr [rbp+27h+var_50.Length], xmm0
0x18000285f  movups  xmmword ptr [rbp+27h+Destination.Length], xmm0
0x180002863  movups  [rbp+27h+UnicodeStringOrUnicodeStringBuffer], xmm1
0x180002867  test    rcx, rcx
0x18000286a  jnz     short loc_1800028C6
0x18000286c  mov     rax, [rbp+27h+arg_48]
0x180002870  mov     rdx, r15
0x180002873  mov     [r11-78h], rsi
0x180002877  mov     rcx, r14
0x18000287a  mov     [r11-80h], rax
0x18000287e  mov     rax, [rbp+27h+arg_40]
0x180002882  mov     [rsp+0B0h+var_80], rax
0x180002887  mov     eax, [rbp+27h+arg_38]
0x18000288a  mov     dword ptr [rsp+0B0h+var_88], eax
0x18000288e  mov     rax, [rbp+27h+arg_20]
0x180002892  mov     qword ptr [rsp+0B0h+var_90], rax
0x180002897  call    BaseSrvSxsCheckManifestAndDotLocal
0x18000289c  test    eax, eax
0x18000289e  jns     loc_180002B3D
0x1800028a4  lea     r11, [rsp+0B0h+var_20]
0x1800028ac  mov     rbx, [r11+30h]
0x1800028b0  mov     rsi, [r11+40h]
0x1800028b4  mov     rdi, [r11+48h]
0x1800028b8  mov     rsp, r11
0x1800028bb  pop     r15
0x1800028bd  pop     r14
0x1800028bf  pop     r13
0x1800028c1  pop     r12
0x1800028c3  pop     rbp
0x1800028c4  retn
0x1800028c6  or      dword ptr [rsi], 2000h
0x1800028cc  mov     rcx, [rbp+27h+arg_48]
0x1800028d0  movups  xmm0, xmmword ptr [rbx]
0x1800028d3  movups  xmm1, xmmword ptr [rbx+10h]
0x1800028d7  movups  xmmword ptr [rcx], xmm0
0x1800028da  movups  xmm0, xmmword ptr [rbx+20h]
0x1800028de  movups  xmmword ptr [rcx+10h], xmm1
0x1800028e2  movsd   xmm1, qword ptr [rbx+30h]
0x1800028e7  movups  xmmword ptr [rcx+20h], xmm0
0x1800028eb  movsd   qword ptr [rcx+30h], xmm1
0x1800028f0  test    dword ptr [rsi], 2000h
0x1800028f6  jz      short loc_18000295E
0x1800028f8  test    rbx, rbx
0x1800028fb  jnz     loc_180002B49
0x180002901  movzx   ecx, word ptr [r15]
0x180002905  mov     esi, 0FFEFh
0x18000290a  cmp     cx, si
0x18000290d  ja      loc_180002BAC
0x180002913  lea     eax, [rcx+10h]
0x180002916  mov     [rbp+27h+Destination.Length], cx
0x18000291a  cmp     ax, cx
0x18000291d  jb      short loc_180002954
0x18000291f  mov     [rbp+27h+Destination.MaximumLength], ax
0x180002923  xor     edx, edx; Flags
0x180002925  mov     rcx, gs:60h
0x18000292e  movzx   r8d, ax; Size
0x180002932  mov     rcx, [rcx+30h]; HeapHandle
0x180002936  call    cs:__imp_RtlAllocateHeap
0x18000293d  nop     dword ptr [rax+rax+00h]
0x180002942  mov     rdi, rax
0x180002945  test    rax, rax
0x180002948  jnz     short loc_180002966
0x18000294a  mov     eax, 0C0000017h
0x18000294f  jmp     loc_1800028A4
0x180002954  mov     eax, 0C0000095h
0x180002959  jmp     loc_1800028A4
0x18000295e  mov     eax, r10d
0x180002961  jmp     loc_1800028A4
0x180002966  movzx   r8d, word ptr [r15]; Size
0x18000296a  mov     rcx, rdi; void *
0x18000296d  mov     rdx, [r15+8]; Src
0x180002971  call    memcpy_0
0x180002976  lea     rdx, Source; ".Config"
0x18000297d  mov     [rbp+27h+Destination.Buffer], rdi
0x180002981  lea     rcx, [rbp+27h+Destination]; Destination
0x180002985  call    cs:__imp_RtlAppendUnicodeToString
0x18000298c  nop     dword ptr [rax+rax+00h]
0x180002991  mov     ebx, eax
0x180002993  test    eax, eax
0x180002995  js      loc_180002B1A
0x18000299b  movzx   ecx, word ptr [r14]
0x18000299f  cmp     cx, si
0x1800029a2  ja      loc_180002BB6
0x1800029a8  lea     eax, [rcx+10h]
0x1800029ab  mov     [rbp+27h+var_50.Length], cx
0x1800029af  cmp     ax, cx
0x1800029b2  jb      loc_180002B0C
0x1800029b8  mov     [rbp+27h+var_50.MaximumLength], ax
0x1800029bc  xor     edx, edx; Flags
0x1800029be  mov     rcx, gs:60h
0x1800029c7  movzx   r8d, ax; Size
0x1800029cb  mov     rcx, [rcx+30h]; HeapHandle
0x1800029cf  call    cs:__imp_RtlAllocateHeap
0x1800029d6  nop     dword ptr [rax+rax+00h]
0x1800029db  mov     r12, rax
0x1800029de  test    rax, rax
0x1800029e1  jz      loc_180002BC0
0x1800029e7  mov     rdx, [r14+8]; Src
0x1800029eb  lea     r15, [r14+8]
0x1800029ef  movzx   r8d, word ptr [r14]; Size
0x1800029f3  mov     rcx, rax; void *
0x1800029f6  call    memcpy_0
0x1800029fb  lea     rdx, Source; ".Config"
0x180002a02  mov     [rbp+27h+var_50.Buffer], r12
0x180002a06  lea     rcx, [rbp+27h+var_50]; Destination
0x180002a0a  call    cs:__imp_RtlAppendUnicodeToString
0x180002a11  nop     dword ptr [rax+rax+00h]
0x180002a16  mov     ebx, eax
0x180002a18  test    eax, eax
0x180002a1a  js      loc_180002B1A
0x180002a20  xor     ecx, ecx
0x180002a22  call    cs:__imp_CsrImpersonateClient
0x180002a29  nop     dword ptr [rax+rax+00h]
0x180002a2e  movzx   esi, al
0x180002a31  test    al, al
0x180002a33  jz      loc_180002BCA
0x180002a39  mov     rax, [rbp+27h+arg_58]
0x180002a40  lea     rdx, [rbp+27h+var_30]
0x180002a44  mov     r9, [rbp+27h+arg_50]
0x180002a4b  xor     r8d, r8d
0x180002a4e  mov     qword ptr [rsp+0B0h+var_90], rax
0x180002a53  call    BasepSxsCreateFileStreamEx
0x180002a58  mov     ebx, eax
0x180002a5a  test    eax, eax
0x180002a5c  jns     loc_180002BD4
0x180002a62  mov     ecx, eax
0x180002a64  call    BasepSxsIsStatusFileNotFoundEtc
0x180002a69  test    eax, eax
0x180002a6b  jz      loc_180002B1D
0x180002a71  mov     rcx, gs:60h
0x180002a7a  xor     edx, edx; Flags
0x180002a7c  movzx   r8d, word ptr [r14+2]; Size
0x180002a81  mov     rcx, [rcx+30h]; HeapHandle
0x180002a85  call    cs:__imp_RtlAllocateHeap
0x180002a8c  nop     dword ptr [rax+rax+00h]
0x180002a91  mov     r13, rax
0x180002a94  test    rax, rax
0x180002a97  jz      loc_180002BE7
0x180002a9d  movzx   r8d, word ptr [r14]; Size
0x180002aa1  mov     rcx, rax; void *
0x180002aa4  mov     rdx, [r15]; Src
0x180002aa7  call    memcpy_0
0x180002aac  movzx   eax, word ptr [r14+2]
0x180002ab1  lea     r8, [rbp+27h+UnicodeStringOrUnicodeStringBuffer]; UnicodeStringOrUnicodeStringBuffer
0x180002ab5  mov     r9, cs:__imp_RtlGetLengthWithoutLastFullDosOrNtPathElement; LengthFunction
0x180002abc  mov     edx, 10h; Type
0x180002ac1  mov     word ptr [rbp+27h+UnicodeStringOrUnicodeStringBuffer+2], ax
0x180002ac5  xor     ecx, ecx; Flags
0x180002ac7  movzx   eax, word ptr [r14]
0x180002acb  mov     word ptr [rbp+27h+UnicodeStringOrUnicodeStringBuffer], ax
0x180002acf  mov     qword ptr [rbp+27h+UnicodeStringOrUnicodeStringBuffer+8], r13
0x180002ad3  call    cs:__imp_RtlpApplyLengthFunction
0x180002ada  nop     dword ptr [rax+rax+00h]
0x180002adf  mov     ebx, eax
0x180002ae1  test    eax, eax
0x180002ae3  jns     short loc_180002B5A
0x180002ae5  test    rdi, rdi
0x180002ae8  jnz     short loc_180002B1D
0x180002aea  test    r12, r12
0x180002aed  jnz     loc_180002BF1
0x180002af3  test    r13, r13
0x180002af6  jnz     loc_180002C14
0x180002afc  test    sil, sil
0x180002aff  jnz     loc_180002C37
0x180002b05  mov     eax, ebx
0x180002b07  jmp     loc_1800028A4
0x180002b0c  mov     eax, 0FFFFh
0x180002b11  mov     ebx, 0C0000095h
0x180002b16  mov     [rbp+27h+var_50.MaximumLength], ax
0x180002b1a  xor     sil, sil
0x180002b1d  mov     rcx, gs:60h
0x180002b26  mov     r8, rdi; P
0x180002b29  xor     edx, edx; Flags
0x180002b2b  mov     rcx, [rcx+30h]; HeapHandle
0x180002b2f  call    cs:__imp_RtlFreeHeap
0x180002b36  nop     dword ptr [rax+rax+00h]
0x180002b3b  jmp     short loc_180002AEA
0x180002b3d  mov     rdx, [rbp+27h+arg_8]
0x180002b41  xor     r10d, r10d
0x180002b44  jmp     loc_1800028F0
0x180002b49  test    rdx, rdx
0x180002b4c  jnz     short loc_180002B83
0x180002b4e  lea     r15, [r14+8]
0x180002b52  xor     sil, sil
0x180002b55  jmp     loc_180002A71
0x180002b5a  movzx   ecx, word ptr [rbp+27h+UnicodeStringOrUnicodeStringBuffer]
0x180002b5e  mov     rax, qword ptr [rbp+27h+UnicodeStringOrUnicodeStringBuffer+8]
0x180002b62  shr     rcx, 1
0x180002b65  xor     edx, edx
0x180002b67  mov     r13d, edx
0x180002b6a  mov     ebx, edx
0x180002b6c  mov     [rax+rcx*2], dx
0x180002b70  mov     rax, [rbp+27h+arg_60]
0x180002b77  movups  xmm0, [rbp+27h+UnicodeStringOrUnicodeStringBuffer]
0x180002b7b  movups  xmmword ptr [rax], xmm0
0x180002b7e  jmp     loc_180002AE5
0x180002b83  mov     rax, [rbp+27h+arg_58]
0x180002b8a  movups  xmm0, xmmword ptr [rdx]
0x180002b8d  movups  xmm1, xmmword ptr [rdx+10h]
0x180002b91  movups  xmmword ptr [rax], xmm0
0x180002b94  movups  xmm0, xmmword ptr [rdx+20h]
0x180002b98  movups  xmmword ptr [rax+10h], xmm1
0x180002b9c  movsd   xmm1, qword ptr [rdx+30h]
0x180002ba1  movups  xmmword ptr [rax+20h], xmm0
0x180002ba5  movsd   qword ptr [rax+30h], xmm1
0x180002baa  jmp     short loc_180002B4E
0x180002bac  mov     eax, 0C0000106h
0x180002bb1  jmp     loc_1800028A4
0x180002bb6  mov     ebx, 0C0000106h
0x180002bbb  jmp     loc_180002B1A
0x180002bc0  mov     ebx, 0C0000017h
0x180002bc5  jmp     loc_180002B1A
0x180002bca  mov     ebx, 0C00000A5h
0x180002bcf  jmp     loc_180002B1D
0x180002bd4  mov     rax, [rbp+27h+arg_58]
0x180002bdb  xor     r12d, r12d
0x180002bde  mov     byte ptr [rax+2], 5
0x180002be2  jmp     loc_180002A71
0x180002be7  mov     ebx, 0C0000017h
0x180002bec  jmp     loc_180002AE5
0x180002bf1  mov     rcx, gs:60h
0x180002bfa  mov     r8, r12; P
0x180002bfd  xor     edx, edx; Flags
0x180002bff  mov     rcx, [rcx+30h]; HeapHandle
0x180002c03  call    cs:__imp_RtlFreeHeap
0x180002c0a  nop     dword ptr [rax+rax+00h]
0x180002c0f  jmp     loc_180002AF3
0x180002c14  mov     rcx, gs:60h
0x180002c1d  mov     r8, r13; P
0x180002c20  xor     edx, edx; Flags
0x180002c22  mov     rcx, [rcx+30h]; HeapHandle
0x180002c26  call    cs:__imp_RtlFreeHeap
0x180002c2d  nop     dword ptr [rax+rax+00h]
0x180002c32  jmp     loc_180002AFC
0x180002c37  call    cs:__imp_CsrRevertToSelf
0x180002c3e  nop     dword ptr [rax+rax+00h]
0x180002c43  jmp     loc_180002B05
```
