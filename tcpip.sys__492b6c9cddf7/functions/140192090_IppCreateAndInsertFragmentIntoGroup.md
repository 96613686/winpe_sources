# IppCreateAndInsertFragmentIntoGroup

- ea: `0x140192090`
- end: `0x1401923c2`
- name: `IppCreateAndInsertFragmentIntoGroup`
- size: `818`
- prototype: `__int64 __fastcall(int, int, int, int, int, char, __int64, KIRQL NewIrql, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400f1bc0`
- `0x1400f78b4`

## callees

- `0x140053e98`
- `0x1400ead1c`
- `0x1400eaef0`
- `0x140192090`
- `0x1401923c8`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x140192155`
- `ntoskrnl!MmSizeOfMdl` at `0x140192155`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14019231c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14019231c`
- `ntoskrnl!ExAllocatePool3` at `0x140192195`
- `ntoskrnl!ExAllocatePool3` at `0x140192195`
- `ntoskrnl!KeReleaseSpinLock` at `0x140192281`
- `ntoskrnl!KeReleaseSpinLock` at `0x140192281`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019229b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019229b`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x140192344`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x140192344`
- `NETIO!NetioAdvanceNetBufferList` at `0x140192234`
- `NETIO!NetioAdvanceNetBufferList` at `0x1401922af`
- `NETIO!NetioAdvanceNetBufferList` at `0x140192234`
- `NETIO!NetioAdvanceNetBufferList` at `0x1401922af`
- `NETIO!NetioAllocateAndReferenceVacantNetBufferList` at `0x140192219`
- `NETIO!NetioAllocateAndReferenceVacantNetBufferList` at `0x140192219`
- `NETIO!NetioRetreatNetBufferList` at `0x1401921e5`
- `NETIO!NetioRetreatNetBufferList` at `0x1401921e5`

## pseudocode

```c
__int64 __fastcall IppCreateAndInsertFragmentIntoGroup(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        char a6,
        __int64 a7,
        KIRQL NewIrql,
        _DWORD *a9)
{
  unsigned __int8 *v9; // rax
  __int64 v10; // rsi
  __int64 result; // rax
  int v13; // edi
  _DWORD *v14; // r15
  SIZE_T v15; // r14
  __int64 v16; // rdx
  __int64 Pool3; // rax
  __int64 v18; // r8
  _QWORD *v19; // rsi
  const wchar_t *v20; // r9
  __int64 v21; // rcx
  __int64 v22; // r10
  __int64 v23; // rdx
  int v24; // [rsp+20h] [rbp-88h]
  int v25; // [rsp+28h] [rbp-80h]
  __int64 v26; // [rsp+30h] [rbp-78h]
  __int64 v27; // [rsp+40h] [rbp-68h] BYREF
  __int64 v28; // [rsp+48h] [rbp-60h]
  __int64 v29; // [rsp+50h] [rbp-58h] BYREF
  _OWORD v30[5]; // [rsp+58h] [rbp-50h] BYREF
  unsigned __int8 v32; // [rsp+B8h] [rbp+10h]

  v9 = *(unsigned __int8 **)(a2 + 48);
  v10 = *(_QWORD *)(a3 + 8);
  v29 = 0;
  v32 = *v9;
  v27 = 0;
  v28 = v10;
  v30[0] = 0;
  *a9 = 18;
  result = IppFindLocationInFragmentGroup(a1, a7, a5, a4, a6, NewIrql, (__int64)&v27, (__int64)a9);
  v13 = result;
  if ( (int)result >= 0 )
  {
    v14 = (_DWORD *)(v10 + 24);
    if ( *(_DWORD *)(a7 + 168) == 1 )
    {
      v15 = 0;
      v16 = 64;
    }
    else
    {
      v15 = (MmSizeOfMdl((PVOID)0xFFF, (unsigned int)*v14) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      v16 = v15 + (unsigned int)*v14 + 16LL;
    }
    v30[0] = 1u;
    Pool3 = ExAllocatePool3(64, v16, 1701990473, v30, 1);
    v19 = (_QWORD *)Pool3;
    if ( !Pool3 )
    {
      if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
      {
        v20 = L"fragment (IPNG)";
LABEL_14:
        McTemplateK0z_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCPIP_MEMORY_FAILURES, v18, v20);
        goto LABEL_15;
      }
      goto LABEL_15;
    }
    if ( *(_DWORD *)(a7 + 168) == 1 )
    {
      v13 = NetioRetreatNetBufferList(a3, v32, 0);
      if ( v13 < 0 )
      {
        *a9 = 13;
        goto LABEL_16;
      }
      LOBYTE(v25) = 1;
      LOBYTE(v24) = 1;
      v19[2] = NetioAllocateAndReferenceVacantNetBufferList(a3, 0, 0, 0, v24, v25, v26);
      NetioAdvanceNetBufferList(a3, v32);
      v21 = v19[2];
      if ( !v21 )
      {
        if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
        {
          v20 = L"fragment NBL for grouping (IPNG)";
          goto LABEL_14;
        }
LABEL_15:
        v13 = -1073741670;
        *a9 = 3;
LABEL_16:
        KeReleaseSpinLock((PKSPIN_LOCK)(a7 + 48), NewIrql);
        if ( v19 )
          ExFreePoolWithTag(v19, 0);
        return (unsigned int)v13;
      }
      NetioAdvanceNetBufferList(v21, v32);
    }
    else
    {
      v22 = (unsigned int)*v14;
      *(_QWORD *)(Pool3 + 16) = 0;
      *(_DWORD *)(Pool3 + 56) = v22;
      *(_DWORD *)(Pool3 + 60) = ((_WORD)Pool3 + (_WORD)v15 + 16) & 0xFFF;
      *(_WORD *)(Pool3 + 26) = 0;
      *(_WORD *)(Pool3 + 24) = 8
                             * ((((unsigned __int64)(((_WORD)Pool3 + (_WORD)v15 + 16) & 0xFFF) + v22 + 4095) >> 12) + 6);
      *(_QWORD *)(Pool3 + 48) = (Pool3 + v15 + 16) & 0xFFFFFFFFFFFFF000uLL;
      MmBuildMdlForNonPagedPool((PMDL)(Pool3 + 16));
      RtlCopyMdlToKernelBuffer(
        *(_QWORD *)(v28 + 8),
        *(unsigned int *)(v28 + 16),
        (char *)v19 + v15 + 16,
        (unsigned int)*v14,
        &v29);
    }
    v23 = v27;
    *v19 = 0;
    *((_WORD *)v19 + 5) = a5;
    *((_WORD *)v19 + 4) = a4;
    IppReassemblyInsertFragment(a7, v23, v19);
    *(_DWORD *)(a7 + 124) += a4;
    if ( a6 )
      *(_DWORD *)(a7 + 120) = a4 + a5;
    IppIncreaseReassemblySize(a1 + 22352, a7, (unsigned int)(*v14 + 256), (unsigned int)*v14);
    return (unsigned int)v13;
  }
  return result;
}

```

## disassembly

```asm
0x140192090  mov     r11, rsp
0x140192093  mov     [r11+20h], rbx
0x140192097  mov     [r11+18h], r8
0x14019209b  mov     [r11+8], rcx
0x14019209f  push    rbp
0x1401920a0  push    rsi
0x1401920a1  push    rdi
0x1401920a2  push    r12
0x1401920a4  push    r13
0x1401920a6  push    r14
0x1401920a8  push    r15
0x1401920aa  sub     rsp, 70h
0x1401920ae  mov     rax, [rdx+30h]
0x1401920b2  xorps   xmm0, xmm0
0x1401920b5  mov     rsi, [r8+8]
0x1401920b9  mov     r12d, r9d
0x1401920bc  mov     rbx, [rsp+0A8h+arg_40]
0x1401920c4  mov     rbp, [rsp+0A8h+arg_30]
0x1401920cc  mov     r13d, [rsp+0A8h+arg_20]
0x1401920d4  mov     rdx, rbp; int
0x1401920d7  mov     [r11-70h], rbx
0x1401920db  mov     r8d, r13d; int
0x1401920de  mov     qword ptr [r11-58h], 0
0x1401920e6  mov     al, [rax]
0x1401920e8  mov     [rsp+0A8h+arg_8], al
0x1401920ef  lea     rax, [r11-68h]
0x1401920f3  mov     [r11-78h], rax
0x1401920f7  mov     al, [rsp+0A8h+NewIrql]
0x1401920fe  mov     [rsp+0A8h+var_80], al; NewIrql
0x140192102  mov     al, [rsp+0A8h+arg_28]
0x140192109  mov     [rsp+0A8h+var_88], al; char
0x14019210d  mov     qword ptr [r11-68h], 0
0x140192115  mov     [rsp+0A8h+var_60], rsi
0x14019211a  movups  [rsp+0A8h+var_50], xmm0
0x14019211f  mov     dword ptr [rbx], 12h
0x140192125  call    IppFindLocationInFragmentGroup
0x14019212a  mov     edi, eax
0x14019212c  test    eax, eax
0x14019212e  js      loc_1401923A9
0x140192134  lea     r15, [rsi+18h]
0x140192138  mov     esi, 1
0x14019213d  cmp     [rbp+0A8h], esi
0x140192143  jnz     short loc_14019214D
0x140192145  xor     r14d, r14d
0x140192148  lea     edx, [rsi+3Fh]
0x14019214b  jmp     short loc_140192173
0x14019214d  mov     edx, [r15]; Length
0x140192150  mov     ecx, 0FFFh; Base
0x140192155  call    cs:__imp_MmSizeOfMdl
0x14019215c  nop     dword ptr [rax+rax+00h]
0x140192161  mov     edx, [r15]
0x140192164  add     rdx, 10h
0x140192168  lea     r14, [rax+7]
0x14019216c  and     r14, 0FFFFFFFFFFFFFFF8h
0x140192170  add     rdx, r14
0x140192173  lea     r9, [rsp+0A8h+var_50]
0x140192178  mov     qword ptr [rsp+0A8h+var_50+8], 0
0x140192181  mov     ecx, 40h ; '@'
0x140192186  mov     qword ptr [rsp+0A8h+var_50], rsi
0x14019218b  mov     r8d, 65725049h
0x140192191  mov     dword ptr [rsp+0A8h+var_88], esi
0x140192195  call    cs:__imp_ExAllocatePool3
0x14019219c  nop     dword ptr [rax+rax+00h]
0x1401921a1  mov     rsi, rax
0x1401921a4  test    rax, rax
0x1401921a7  jnz     short loc_1401921C1
0x1401921a9  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x1401921af  jge     loc_14019226B
0x1401921b5  lea     r9, aFragmentIpng; "fragment (IPNG)"
0x1401921bc  jmp     loc_140192258
0x1401921c1  cmp     dword ptr [rbp+0A8h], 1
0x1401921c8  jnz     loc_1401922C0
0x1401921ce  movzx   r14d, [rsp+0A8h+arg_8]
0x1401921d7  xor     r8d, r8d
0x1401921da  mov     rcx, [rsp+0A8h+arg_10]
0x1401921e2  mov     edx, r14d
0x1401921e5  call    cs:__imp_NetioRetreatNetBufferList
0x1401921ec  nop     dword ptr [rax+rax+00h]
0x1401921f1  mov     edi, eax
0x1401921f3  test    eax, eax
0x1401921f5  jns     short loc_1401921FF
0x1401921f7  mov     dword ptr [rbx], 0Dh
0x1401921fd  jmp     short loc_140192276
0x1401921ff  mov     rcx, [rsp+0A8h+arg_10]
0x140192207  xor     r9d, r9d
0x14019220a  mov     [rsp+0A8h+var_80], 1
0x14019220f  xor     r8d, r8d
0x140192212  xor     edx, edx
0x140192214  mov     [rsp+0A8h+var_88], 1
0x140192219  call    cs:__imp_NetioAllocateAndReferenceVacantNetBufferList
0x140192220  nop     dword ptr [rax+rax+00h]
0x140192225  mov     rcx, [rsp+0A8h+arg_10]
0x14019222d  mov     edx, r14d
0x140192230  mov     [rsi+10h], rax
0x140192234  call    cs:__imp_NetioAdvanceNetBufferList
0x14019223b  nop     dword ptr [rax+rax+00h]
0x140192240  mov     rcx, [rsi+10h]
0x140192244  test    rcx, rcx
0x140192247  jnz     short loc_1401922AC
0x140192249  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, cl
0x14019224f  jge     short loc_14019226B
0x140192251  lea     r9, aFragmentNblFor; "fragment NBL for grouping (IPNG)"
0x140192258  lea     rdx, TCPIP_MEMORY_FAILURES
0x14019225f  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140192266  call    McTemplateK0z_EtwWriteTransfer
0x14019226b  mov     edi, 0C000009Ah
0x140192270  mov     dword ptr [rbx], 3
0x140192276  mov     dl, [rsp+0A8h+NewIrql]; NewIrql
0x14019227d  lea     rcx, [rbp+30h]; SpinLock
0x140192281  call    cs:__imp_KeReleaseSpinLock
0x140192288  nop     dword ptr [rax+rax+00h]
0x14019228d  test    rsi, rsi
0x140192290  jz      loc_1401923A7
0x140192296  xor     edx, edx; Tag
0x140192298  mov     rcx, rsi; P
0x14019229b  call    cs:__imp_ExFreePoolWithTag
0x1401922a2  nop     dword ptr [rax+rax+00h]
0x1401922a7  jmp     loc_1401923A7
0x1401922ac  mov     edx, r14d
0x1401922af  call    cs:__imp_NetioAdvanceNetBufferList
0x1401922b6  nop     dword ptr [rax+rax+00h]
0x1401922bb  jmp     loc_140192350
0x1401922c0  mov     r10d, [r15]
0x1401922c3  lea     rcx, [rax+10h]; MemoryDescriptorList
0x1401922c7  mov     r8d, 0FFFh
0x1401922cd  mov     qword ptr [rcx], 0
0x1401922d4  lea     rbx, [r14+10h]
0x1401922d8  mov     [rcx+28h], r10d
0x1401922dc  add     rbx, rsi
0x1401922df  mov     r9d, ebx
0x1401922e2  lea     rdx, [r10+0FFFh]
0x1401922e9  mov     eax, r9d
0x1401922ec  and     r9d, r8d
0x1401922ef  and     rax, r8
0x1401922f2  mov     [rcx+2Ch], r9d
0x1401922f6  add     rdx, rax
0x1401922f9  xor     eax, eax
0x1401922fb  shr     rdx, 0Ch
0x1401922ff  mov     [rcx+0Ah], ax
0x140192303  add     dx, 6
0x140192307  shl     dx, 3
0x14019230b  mov     rax, rbx
0x14019230e  and     rax, 0FFFFFFFFFFFFF000h
0x140192314  mov     [rcx+8], dx
0x140192318  mov     [rcx+20h], rax
0x14019231c  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140192323  nop     dword ptr [rax+rax+00h]
0x140192328  mov     rcx, [rsp+0A8h+var_60]
0x14019232d  lea     rax, [rsp+0A8h+var_58]
0x140192332  mov     r9d, [r15]
0x140192335  mov     r8, rbx
0x140192338  mov     qword ptr [rsp+0A8h+var_88], rax
0x14019233d  mov     edx, [rcx+10h]
0x140192340  mov     rcx, [rcx+8]
0x140192344  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x14019234b  nop     dword ptr [rax+rax+00h]
0x140192350  mov     rdx, [rsp+0A8h+var_68]
0x140192355  mov     r8, rsi
0x140192358  mov     rcx, rbp
0x14019235b  mov     qword ptr [rsi], 0
0x140192362  mov     [rsi+0Ah], r13w
0x140192367  mov     [rsi+8], r12w
0x14019236c  call    IppReassemblyInsertFragment
0x140192371  add     [rbp+7Ch], r12d
0x140192375  cmp     [rsp+0A8h+arg_28], 0
0x14019237d  jz      short loc_140192386
0x14019237f  lea     eax, [r12+r13]
0x140192383  mov     [rbp+78h], eax
0x140192386  mov     r9d, [r15]
0x140192389  mov     rdx, rbp
0x14019238c  mov     rcx, [rsp+0A8h+arg_0]
0x140192394  add     rcx, 5750h
0x14019239b  lea     r8d, [r9+100h]
0x1401923a2  call    IppIncreaseReassemblySize
0x1401923a7  mov     eax, edi
0x1401923a9  mov     rbx, [rsp+0A8h+arg_18]
0x1401923b1  add     rsp, 70h
0x1401923b5  pop     r15
0x1401923b7  pop     r14
0x1401923b9  pop     r13
0x1401923bb  pop     r12
0x1401923bd  pop     rdi
0x1401923be  pop     rsi
0x1401923bf  pop     rbp
0x1401923c0  retn
```
