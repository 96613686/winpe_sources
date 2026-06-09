# BaseSrvSxsProbeManifestAndPolicyAndDotLocal

- ea: `0x1800028d0`
- end: `0x180002d30`
- name: `BaseSrvSxsProbeManifestAndPolicyAndDotLocal`
- size: `1120`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, __int64, unsigned __int16 *, unsigned __int16 *, int, __int64, __int64, __int64, __int64, _OWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting`

## callers

- `0x180001e00`

## callees

- `0x1800028d0`
- `0x180002d40`
- `0x180004020`
- `0x1800042b0`
- `0x180006cc1`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180002c0d`
- `ntdll!RtlFreeHeap` at `0x180002ceb`
- `ntdll!RtlFreeHeap` at `0x180002d0e`
- `ntdll!RtlFreeHeap` at `0x180002c0d`
- `ntdll!RtlFreeHeap` at `0x180002ceb`
- `ntdll!RtlFreeHeap` at `0x180002d0e`
- `ntdll!RtlpApplyLengthFunction` at `0x180002bad`
- `ntdll!RtlpApplyLengthFunction` at `0x180002bad`
- `ntdll!RtlAllocateHeap` at `0x1800029f6`
- `ntdll!RtlAllocateHeap` at `0x180002aa5`
- `ntdll!RtlAllocateHeap` at `0x180002b5b`
- `ntdll!RtlAllocateHeap` at `0x1800029f6`
- `ntdll!RtlAllocateHeap` at `0x180002aa5`
- `ntdll!RtlAllocateHeap` at `0x180002b5b`
- `ntdll!RtlAppendUnicodeToString` at `0x180002a56`
- `ntdll!RtlAppendUnicodeToString` at `0x180002ae0`
- `ntdll!RtlAppendUnicodeToString` at `0x180002a56`
- `ntdll!RtlAppendUnicodeToString` at `0x180002ae0`
- `ntdll!RtlGetLengthWithoutLastFullDosOrNtPathElement` at `0x180002b8f`
- `CSRSRV!CsrRevertToSelf` at `0x180002d1f`
- `CSRSRV!CsrRevertToSelf` at `0x180002d1f`
- `CSRSRV!CsrImpersonateClient` at `0x180002af8`
- `CSRSRV!CsrImpersonateClient` at `0x180002af8`

## string_xrefs

- `0x180002a47`: `.Config`
- `0x180002ad1`: `.Config`

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
  __int64 result; // rax
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  WCHAR *v19; // r13
  unsigned __int16 v20; // cx
  WCHAR *Heap; // rax
  WCHAR *v22; // r12
  void *v23; // r14
  NTSTATUS appended; // ebx
  unsigned __int16 v25; // cx
  WCHAR *v26; // rax
  const void **v27; // r14
  __int64 v28; // rcx
  char v29; // si
  int FileStream; // eax
  PVOID v31; // rax
  PVOID v32; // rbx
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 UnicodeStringOrUnicodeStringBuffer; // [rsp+50h] [rbp-39h] BYREF
  struct _UNICODE_STRING v36; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v38[6]; // [rsp+80h] [rbp-9h] BYREF
  PVOID P; // [rsp+C0h] [rbp+37h]

  v38[0] = &v36;
  v38[1] = &Destination;
  v36 = 0;
  Destination = 0;
  UnicodeStringOrUnicodeStringBuffer = 0;
  if ( a1 )
  {
    *a14 |= 0x2000u;
    v17 = *(_OWORD *)(a1 + 16);
    *(_OWORD *)a10 = *(_OWORD *)a1;
    v18 = *(_OWORD *)(a1 + 32);
    *(_OWORD *)(a10 + 16) = v17;
    *(_QWORD *)&v17 = *(_QWORD *)(a1 + 48);
    *(_OWORD *)(a10 + 32) = v18;
    *(_QWORD *)(a10 + 48) = v17;
  }
  else
  {
    result = BaseSrvSxsCheckManifestAndDotLocal((_DWORD)a6, (_DWORD)a7, a3, a4, a5, a8, a9, a10, (__int64)a14);
    if ( (int)result < 0 )
      return result;
  }
  if ( (*a14 & 0x2000) == 0 )
    return 0;
  v19 = 0;
  if ( a1 )
  {
    v22 = 0;
    if ( a2 )
    {
      v33 = *(_OWORD *)(a2 + 16);
      *(_OWORD *)a12 = *(_OWORD *)a2;
      v34 = *(_OWORD *)(a2 + 32);
      *(_OWORD *)(a12 + 16) = v33;
      *(_QWORD *)&v33 = *(_QWORD *)(a2 + 48);
      *(_OWORD *)(a12 + 32) = v34;
      *(_QWORD *)(a12 + 48) = v33;
    }
    v27 = (const void **)(a6 + 4);
    v29 = 0;
    goto LABEL_21;
  }
  v20 = *a7;
  if ( *a7 > 0xFFEFu )
    return 3221225734LL;
  Destination.Length = *a7;
  if ( (unsigned __int16)(v20 + 16) < v20 )
    return 3221225621LL;
  Destination.MaximumLength = v20 + 16;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned __int16)(v20 + 16));
  v22 = Heap;
  if ( !Heap )
    return 3221225495LL;
  v23 = 0;
  memcpy_0(Heap, *((const void **)a7 + 1), *a7);
  Destination.Buffer = v22;
  appended = RtlAppendUnicodeToString(&Destination, L".Config");
  if ( appended < 0 )
    goto LABEL_40;
  v25 = *a6;
  if ( *a6 > 0xFFEFu )
  {
    appended = -1073741562;
LABEL_40:
    v29 = 0;
    goto LABEL_33;
  }
  v36.Length = *a6;
  if ( (unsigned __int16)(v25 + 16) < v25 )
  {
    appended = -1073741675;
    v36.MaximumLength = -1;
    v29 = 0;
  }
  else
  {
    v36.MaximumLength = v25 + 16;
    v26 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned __int16)(v25 + 16));
    v19 = v26;
    if ( v26 )
    {
      v27 = (const void **)(a6 + 4);
      memcpy_0(v26, *((const void **)a6 + 1), *a6);
      v36.Buffer = v19;
      appended = RtlAppendUnicodeToString(&v36, L".Config");
      if ( appended < 0 )
      {
        v29 = 0;
      }
      else
      {
        v29 = CsrImpersonateClient(0);
        if ( v29 )
        {
          FileStream = BasepSxsCreateFileStreamEx(v28, v38, 0, a11, a12);
          appended = FileStream;
          if ( FileStream < 0 )
          {
            if ( (unsigned int)BasepSxsIsStatusFileNotFoundEtc((unsigned int)FileStream) )
              goto LABEL_21;
            goto LABEL_46;
          }
          v19 = 0;
          *(_BYTE *)(a12 + 2) = 5;
LABEL_21:
          v31 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, a6[1]);
          P = v31;
          v32 = v31;
          if ( v31 )
          {
            memcpy_0(v31, *v27, *a6);
            LODWORD(UnicodeStringOrUnicodeStringBuffer) = *(_DWORD *)a6;
            *((_QWORD *)&UnicodeStringOrUnicodeStringBuffer + 1) = v32;
            appended = RtlpApplyLengthFunction(
                         0,
                         0x10u,
                         &UnicodeStringOrUnicodeStringBuffer,
                         RtlGetLengthWithoutLastFullDosOrNtPathElement);
            if ( appended >= 0 )
            {
              v23 = 0;
              appended = 0;
              *(_WORD *)(*((_QWORD *)&UnicodeStringOrUnicodeStringBuffer + 1)
                       + 2 * ((unsigned __int64)(unsigned __int16)UnicodeStringOrUnicodeStringBuffer >> 1)) = 0;
              *a13 = UnicodeStringOrUnicodeStringBuffer;
            }
            else
            {
              v23 = P;
            }
          }
          else
          {
            appended = -1073741801;
            v23 = 0;
          }
          if ( !v22 )
            goto LABEL_25;
          goto LABEL_33;
        }
        appended = -1073741659;
      }
LABEL_46:
      v23 = 0;
      goto LABEL_33;
    }
    appended = -1073741801;
    v29 = 0;
  }
LABEL_33:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
LABEL_25:
  if ( v19 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
  if ( v23 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
  if ( v29 )
    CsrRevertToSelf();
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800028d0  mov     [rsp-8+arg_18], rbx
0x1800028d5  push    rbp
0x1800028d6  push    rsi
0x1800028d7  push    rdi
0x1800028d8  push    r14
0x1800028da  push    r15
0x1800028dc  lea     rbp, [rsp-7]
0x1800028e1  sub     rsp, 90h
0x1800028e8  mov     rdi, [rbp+27h+arg_68]
0x1800028ef  lea     rax, [rbp+27h+var_50]
0x1800028f3  mov     rsi, [rbp+27h+arg_30]
0x1800028f7  xorps   xmm0, xmm0
0x1800028fa  mov     r15, [rbp+27h+arg_28]
0x1800028fe  xorps   xmm1, xmm1
0x180002901  mov     [rbp+27h+var_30], rax
0x180002905  lea     rax, [rbp+27h+Destination]
0x180002909  mov     [rbp+27h+var_28], rax
0x18000290d  mov     r14, rdx
0x180002910  mov     rax, [rbp+27h+arg_48]
0x180002914  mov     rbx, rcx
0x180002917  movups  xmmword ptr [rbp+27h+var_50.Length], xmm0
0x18000291b  movups  xmmword ptr [rbp+27h+Destination.Length], xmm1
0x18000291f  movups  [rbp+27h+UnicodeStringOrUnicodeStringBuffer], xmm0
0x180002923  test    rcx, rcx
0x180002926  jnz     short loc_180002972
0x180002928  mov     [rsp+0B0h+var_70], rdi
0x18000292d  mov     rdx, rsi
0x180002930  mov     [rsp+0B0h+var_78], rax
0x180002935  mov     rcx, r15
0x180002938  mov     rax, [rbp+27h+arg_40]
0x18000293c  mov     [rsp+0B0h+var_80], rax
0x180002941  mov     eax, [rbp+27h+arg_38]
0x180002944  mov     [rsp+0B0h+var_88], eax
0x180002948  mov     rax, [rbp+27h+arg_20]
0x18000294c  mov     [rsp+0B0h+var_90], rax
0x180002951  call    BaseSrvSxsCheckManifestAndDotLocal
0x180002956  test    eax, eax
0x180002958  jns     short loc_180002998
0x18000295a  mov     rbx, [rsp+0B0h+arg_18]
0x180002962  add     rsp, 90h
0x180002969  pop     r15
0x18000296b  pop     r14
0x18000296d  pop     rdi
0x18000296e  pop     rsi
0x18000296f  pop     rbp
0x180002970  retn
0x180002972  or      dword ptr [rdi], 2000h
0x180002978  movups  xmm0, xmmword ptr [rcx]
0x18000297b  movups  xmm1, xmmword ptr [rcx+10h]
0x18000297f  movups  xmmword ptr [rax], xmm0
0x180002982  movups  xmm0, xmmword ptr [rcx+20h]
0x180002986  movups  xmmword ptr [rax+10h], xmm1
0x18000298a  movsd   xmm1, qword ptr [rcx+30h]
0x18000298f  movups  xmmword ptr [rax+20h], xmm0
0x180002993  movsd   qword ptr [rax+30h], xmm1
0x180002998  test    dword ptr [rdi], 2000h
0x18000299e  jz      loc_180002A2B
0x1800029a4  xor     edi, edi
0x1800029a6  mov     [rsp+0B0h+arg_8], r12
0x1800029ae  mov     [rsp+0B0h+arg_10], r13
0x1800029b6  mov     r13d, edi
0x1800029b9  test    rbx, rbx
0x1800029bc  jnz     loc_180002C1B
0x1800029c2  movzx   ecx, word ptr [rsi]
0x1800029c5  mov     eax, 0FFEFh
0x1800029ca  cmp     cx, ax
0x1800029cd  ja      loc_180002C83
0x1800029d3  lea     eax, [rcx+10h]
0x1800029d6  mov     [rbp+27h+Destination.Length], cx
0x1800029da  cmp     ax, cx
0x1800029dd  jb      short loc_180002A24
0x1800029df  mov     [rbp+27h+Destination.MaximumLength], ax
0x1800029e3  xor     edx, edx; Flags
0x1800029e5  mov     rcx, gs:60h
0x1800029ee  movzx   r8d, ax; Size
0x1800029f2  mov     rcx, [rcx+30h]; HeapHandle
0x1800029f6  call    cs:__imp_RtlAllocateHeap
0x1800029fd  nop     dword ptr [rax+rax+00h]
0x180002a02  mov     r12, rax
0x180002a05  test    rax, rax
0x180002a08  jnz     short loc_180002A34
0x180002a0a  mov     eax, 0C0000017h
0x180002a0f  mov     r12, [rsp+0B0h+arg_8]
0x180002a17  mov     r13, [rsp+0B0h+arg_10]
0x180002a1f  jmp     loc_18000295A
0x180002a24  mov     eax, 0C0000095h
0x180002a29  jmp     short loc_180002A0F
0x180002a2b  xor     edi, edi
0x180002a2d  mov     eax, edi
0x180002a2f  jmp     loc_18000295A
0x180002a34  movzx   r8d, word ptr [rsi]; Size
0x180002a38  mov     rcx, r12; void *
0x180002a3b  mov     rdx, [rsi+8]; Src
0x180002a3f  mov     r14, rdi
0x180002a42  call    memcpy_0
0x180002a47  lea     rdx, Source; ".Config"
0x180002a4e  mov     [rbp+27h+Destination.Buffer], r12
0x180002a52  lea     rcx, [rbp+27h+Destination]; Destination
0x180002a56  call    cs:__imp_RtlAppendUnicodeToString
0x180002a5d  nop     dword ptr [rax+rax+00h]
0x180002a62  mov     ebx, eax
0x180002a64  test    eax, eax
0x180002a66  js      loc_180002C92
0x180002a6c  movzx   ecx, word ptr [r15]
0x180002a70  mov     eax, 0FFEFh
0x180002a75  cmp     cx, ax
0x180002a78  ja      loc_180002C8D
0x180002a7e  lea     eax, [rcx+10h]
0x180002a81  mov     [rbp+27h+var_50.Length], cx
0x180002a85  cmp     ax, cx
0x180002a88  jb      loc_180002BEA
0x180002a8e  mov     [rbp+27h+var_50.MaximumLength], ax
0x180002a92  xor     edx, edx; Flags
0x180002a94  mov     rcx, gs:60h
0x180002a9d  movzx   r8d, ax; Size
0x180002aa1  mov     rcx, [rcx+30h]; HeapHandle
0x180002aa5  call    cs:__imp_RtlAllocateHeap
0x180002aac  nop     dword ptr [rax+rax+00h]
0x180002ab1  mov     r13, rax
0x180002ab4  test    rax, rax
0x180002ab7  jz      loc_180002C9A
0x180002abd  mov     rdx, [r15+8]; Src
0x180002ac1  lea     r14, [r15+8]
0x180002ac5  movzx   r8d, word ptr [r15]; Size
0x180002ac9  mov     rcx, rax; void *
0x180002acc  call    memcpy_0
0x180002ad1  lea     rdx, Source; ".Config"
0x180002ad8  mov     [rbp+27h+var_50.Buffer], r13
0x180002adc  lea     rcx, [rbp+27h+var_50]; Destination
0x180002ae0  call    cs:__imp_RtlAppendUnicodeToString
0x180002ae7  nop     dword ptr [rax+rax+00h]
0x180002aec  mov     ebx, eax
0x180002aee  test    eax, eax
0x180002af0  js      loc_180002CCE
0x180002af6  xor     ecx, ecx
0x180002af8  call    cs:__imp_CsrImpersonateClient
0x180002aff  nop     dword ptr [rax+rax+00h]
0x180002b04  movzx   esi, al
0x180002b07  test    al, al
0x180002b09  jz      loc_180002CA7
0x180002b0f  mov     rax, [rbp+27h+arg_58]
0x180002b16  lea     rdx, [rbp+27h+var_30]
0x180002b1a  mov     r9, [rbp+27h+arg_50]
0x180002b21  xor     r8d, r8d
0x180002b24  mov     [rsp+0B0h+var_90], rax
0x180002b29  call    BasepSxsCreateFileStreamEx
0x180002b2e  mov     ebx, eax
0x180002b30  test    eax, eax
0x180002b32  jns     loc_180002CAE
0x180002b38  mov     ecx, eax
0x180002b3a  call    BasepSxsIsStatusFileNotFoundEtc
0x180002b3f  test    eax, eax
0x180002b41  jz      loc_180002CD1
0x180002b47  mov     rcx, gs:60h
0x180002b50  xor     edx, edx; Flags
0x180002b52  movzx   r8d, word ptr [r15+2]; Size
0x180002b57  mov     rcx, [rcx+30h]; HeapHandle
0x180002b5b  call    cs:__imp_RtlAllocateHeap
0x180002b62  nop     dword ptr [rax+rax+00h]
0x180002b67  mov     [rbp+27h+P], rax
0x180002b6b  mov     rbx, rax
0x180002b6e  test    rax, rax
0x180002b71  jz      loc_180002CC1
0x180002b77  movzx   r8d, word ptr [r15]; Size
0x180002b7b  mov     rcx, rax; void *
0x180002b7e  mov     rdx, [r14]; Src
0x180002b81  call    memcpy_0
0x180002b86  movzx   eax, word ptr [r15+2]
0x180002b8b  lea     r8, [rbp+27h+UnicodeStringOrUnicodeStringBuffer]; UnicodeStringOrUnicodeStringBuffer
0x180002b8f  mov     r9, cs:__imp_RtlGetLengthWithoutLastFullDosOrNtPathElement; LengthFunction
0x180002b96  mov     edx, 10h; Type
0x180002b9b  mov     word ptr [rbp+27h+UnicodeStringOrUnicodeStringBuffer+2], ax
0x180002b9f  xor     ecx, ecx; Flags
0x180002ba1  movzx   eax, word ptr [r15]
0x180002ba5  mov     word ptr [rbp+27h+UnicodeStringOrUnicodeStringBuffer], ax
0x180002ba9  mov     qword ptr [rbp+27h+UnicodeStringOrUnicodeStringBuffer+8], rbx
0x180002bad  call    cs:__imp_RtlpApplyLengthFunction
0x180002bb4  nop     dword ptr [rax+rax+00h]
0x180002bb9  mov     ebx, eax
0x180002bbb  test    eax, eax
0x180002bbd  jns     short loc_180002C2F
0x180002bbf  mov     r14, [rbp+27h+P]
0x180002bc3  test    r12, r12
0x180002bc6  jnz     short loc_180002BFB
0x180002bc8  test    r13, r13
0x180002bcb  jnz     loc_180002CD9
0x180002bd1  test    r14, r14
0x180002bd4  jnz     loc_180002CFC
0x180002bda  test    sil, sil
0x180002bdd  jnz     loc_180002D1F
0x180002be3  mov     eax, ebx
0x180002be5  jmp     loc_180002A0F
0x180002bea  mov     eax, 0FFFFh
0x180002bef  mov     ebx, 0C0000095h
0x180002bf4  mov     [rbp+27h+var_50.MaximumLength], ax
0x180002bf8  xor     sil, sil
0x180002bfb  mov     rcx, gs:60h
0x180002c04  mov     r8, r12; P
0x180002c07  xor     edx, edx; Flags
0x180002c09  mov     rcx, [rcx+30h]; HeapHandle
0x180002c0d  call    cs:__imp_RtlFreeHeap
0x180002c14  nop     dword ptr [rax+rax+00h]
0x180002c19  jmp     short loc_180002BC8
0x180002c1b  mov     r12, rdi
0x180002c1e  test    r14, r14
0x180002c21  jnz     short loc_180002C56
0x180002c23  lea     r14, [r15+8]
0x180002c27  xor     sil, sil
0x180002c2a  jmp     loc_180002B47
0x180002c2f  movzx   ecx, word ptr [rbp+27h+UnicodeStringOrUnicodeStringBuffer]
0x180002c33  mov     r14, rdi
0x180002c36  mov     rax, qword ptr [rbp+27h+UnicodeStringOrUnicodeStringBuffer+8]
0x180002c3a  mov     ebx, edi
0x180002c3c  shr     rcx, 1
0x180002c3f  mov     [rax+rcx*2], di
0x180002c43  mov     rax, [rbp+27h+arg_60]
0x180002c4a  movups  xmm0, [rbp+27h+UnicodeStringOrUnicodeStringBuffer]
0x180002c4e  movups  xmmword ptr [rax], xmm0
0x180002c51  jmp     loc_180002BC3
0x180002c56  mov     rax, [rbp+27h+arg_58]
0x180002c5d  movups  xmm0, xmmword ptr [r14]
0x180002c61  movups  xmm1, xmmword ptr [r14+10h]
0x180002c66  movups  xmmword ptr [rax], xmm0
0x180002c69  movups  xmm0, xmmword ptr [r14+20h]
0x180002c6e  movups  xmmword ptr [rax+10h], xmm1
0x180002c72  movsd   xmm1, qword ptr [r14+30h]
0x180002c78  movups  xmmword ptr [rax+20h], xmm0
0x180002c7c  movsd   qword ptr [rax+30h], xmm1
0x180002c81  jmp     short loc_180002C23
0x180002c83  mov     eax, 0C0000106h
0x180002c88  jmp     loc_180002A0F
0x180002c8d  mov     ebx, 0C0000106h
0x180002c92  xor     sil, sil
0x180002c95  jmp     loc_180002BFB
0x180002c9a  mov     ebx, 0C0000017h
0x180002c9f  xor     sil, sil
0x180002ca2  jmp     loc_180002BFB
0x180002ca7  mov     ebx, 0C00000A5h
0x180002cac  jmp     short loc_180002CD1
0x180002cae  mov     rax, [rbp+27h+arg_58]
0x180002cb5  mov     r13, rdi
0x180002cb8  mov     byte ptr [rax+2], 5
0x180002cbc  jmp     loc_180002B47
0x180002cc1  mov     ebx, 0C0000017h
0x180002cc6  mov     r14, rax
0x180002cc9  jmp     loc_180002BC3
0x180002cce  xor     sil, sil
0x180002cd1  mov     r14, rdi
0x180002cd4  jmp     loc_180002BFB
0x180002cd9  mov     rcx, gs:60h
0x180002ce2  mov     r8, r13; P
0x180002ce5  xor     edx, edx; Flags
0x180002ce7  mov     rcx, [rcx+30h]; HeapHandle
0x180002ceb  call    cs:__imp_RtlFreeHeap
0x180002cf2  nop     dword ptr [rax+rax+00h]
0x180002cf7  jmp     loc_180002BD1
0x180002cfc  mov     rcx, gs:60h
0x180002d05  mov     r8, r14; P
0x180002d08  xor     edx, edx; Flags
0x180002d0a  mov     rcx, [rcx+30h]; HeapHandle
0x180002d0e  call    cs:__imp_RtlFreeHeap
0x180002d15  nop     dword ptr [rax+rax+00h]
0x180002d1a  jmp     loc_180002BDA
0x180002d1f  call    cs:__imp_CsrRevertToSelf
0x180002d26  nop     dword ptr [rax+rax+00h]
0x180002d2b  jmp     loc_180002BE3
```
