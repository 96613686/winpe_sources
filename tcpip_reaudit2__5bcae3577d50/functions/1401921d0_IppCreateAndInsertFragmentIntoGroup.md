# IppCreateAndInsertFragmentIntoGroup

- ea: `0x1401921d0`
- end: `0x140192502`
- name: `IppCreateAndInsertFragmentIntoGroup`
- size: `818`
- prototype: `__int64 __fastcall(int, int, int, int, int, char, __int64, KIRQL NewIrql, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400f1ab0`
- `0x1400f77a4`

## callees

- `0x140054138`
- `0x1400eac0c`
- `0x1400eade0`
- `0x1401921d0`
- `0x140192508`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x140192295`
- `ntoskrnl!MmSizeOfMdl` at `0x140192295`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14019245c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14019245c`
- `ntoskrnl!ExAllocatePool3` at `0x1401922d5`
- `ntoskrnl!ExAllocatePool3` at `0x1401922d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401923c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401923c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401923db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401923db`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x140192484`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x140192484`
- `NETIO!NetioAdvanceNetBufferList` at `0x140192374`
- `NETIO!NetioAdvanceNetBufferList` at `0x1401923ef`
- `NETIO!NetioAdvanceNetBufferList` at `0x140192374`
- `NETIO!NetioAdvanceNetBufferList` at `0x1401923ef`
- `NETIO!NetioAllocateAndReferenceVacantNetBufferList` at `0x140192359`
- `NETIO!NetioAllocateAndReferenceVacantNetBufferList` at `0x140192359`
- `NETIO!NetioRetreatNetBufferList` at `0x140192325`
- `NETIO!NetioRetreatNetBufferList` at `0x140192325`

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
  __int64 v26; // [rsp+40h] [rbp-68h] BYREF
  __int64 v27; // [rsp+48h] [rbp-60h]
  __int64 v28; // [rsp+50h] [rbp-58h] BYREF
  _OWORD v29[5]; // [rsp+58h] [rbp-50h] BYREF
  unsigned __int8 v31; // [rsp+B8h] [rbp+10h]

  v9 = *(unsigned __int8 **)(a2 + 48);
  v10 = *(_QWORD *)(a3 + 8);
  v28 = 0;
  v31 = *v9;
  v26 = 0;
  v27 = v10;
  v29[0] = 0;
  *a9 = 18;
  result = IppFindLocationInFragmentGroup(a1, a7, a5, a4, a6, NewIrql, (__int64)&v26, (__int64)a9);
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
    v29[0] = 1u;
    Pool3 = ExAllocatePool3(64, v16, 1701990473, v29, 1);
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
      v13 = NetioRetreatNetBufferList(a3, v31, 0);
      if ( v13 < 0 )
      {
        *a9 = 13;
        goto LABEL_16;
      }
      LOBYTE(v25) = 1;
      LOBYTE(v24) = 1;
      v19[2] = NetioAllocateAndReferenceVacantNetBufferList(a3, 0, 0, 0, v24, v25);
      NetioAdvanceNetBufferList(a3, v31);
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
      NetioAdvanceNetBufferList(v21, v31);
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
        *(_QWORD *)(v27 + 8),
        *(unsigned int *)(v27 + 16),
        (char *)v19 + v15 + 16,
        (unsigned int)*v14,
        &v28);
    }
    v23 = v26;
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
0x1401921d0  mov     r11, rsp
0x1401921d3  mov     [r11+20h], rbx
0x1401921d7  mov     [r11+18h], r8
0x1401921db  mov     [r11+8], rcx
0x1401921df  push    rbp
0x1401921e0  push    rsi
0x1401921e1  push    rdi
0x1401921e2  push    r12
0x1401921e4  push    r13
0x1401921e6  push    r14
0x1401921e8  push    r15
0x1401921ea  sub     rsp, 70h
0x1401921ee  mov     rax, [rdx+30h]
0x1401921f2  xorps   xmm0, xmm0
0x1401921f5  mov     rsi, [r8+8]
0x1401921f9  mov     r12d, r9d
0x1401921fc  mov     rbx, [rsp+0A8h+arg_40]
0x140192204  mov     rbp, [rsp+0A8h+arg_30]
0x14019220c  mov     r13d, [rsp+0A8h+arg_20]
0x140192214  mov     rdx, rbp; int
0x140192217  mov     [r11-70h], rbx
0x14019221b  mov     r8d, r13d; int
0x14019221e  mov     qword ptr [r11-58h], 0
0x140192226  mov     al, [rax]
0x140192228  mov     [rsp+0A8h+arg_8], al
0x14019222f  lea     rax, [r11-68h]
0x140192233  mov     [r11-78h], rax
0x140192237  mov     al, [rsp+0A8h+NewIrql]
0x14019223e  mov     byte ptr [rsp+0A8h+var_80], al; NewIrql
0x140192242  mov     al, [rsp+0A8h+arg_28]
0x140192249  mov     [rsp+0A8h+var_88], al; char
0x14019224d  mov     qword ptr [r11-68h], 0
0x140192255  mov     [rsp+0A8h+var_60], rsi
0x14019225a  movups  [rsp+0A8h+var_50], xmm0
0x14019225f  mov     dword ptr [rbx], 12h
0x140192265  call    IppFindLocationInFragmentGroup
0x14019226a  mov     edi, eax
0x14019226c  test    eax, eax
0x14019226e  js      loc_1401924E9
0x140192274  lea     r15, [rsi+18h]
0x140192278  mov     esi, 1
0x14019227d  cmp     [rbp+0A8h], esi
0x140192283  jnz     short loc_14019228D
0x140192285  xor     r14d, r14d
0x140192288  lea     edx, [rsi+3Fh]
0x14019228b  jmp     short loc_1401922B3
0x14019228d  mov     edx, [r15]; Length
0x140192290  mov     ecx, 0FFFh; Base
0x140192295  call    cs:__imp_MmSizeOfMdl
0x14019229c  nop     dword ptr [rax+rax+00h]
0x1401922a1  mov     edx, [r15]
0x1401922a4  add     rdx, 10h
0x1401922a8  lea     r14, [rax+7]
0x1401922ac  and     r14, 0FFFFFFFFFFFFFFF8h
0x1401922b0  add     rdx, r14
0x1401922b3  lea     r9, [rsp+0A8h+var_50]
0x1401922b8  mov     qword ptr [rsp+0A8h+var_50+8], 0
0x1401922c1  mov     ecx, 40h ; '@'
0x1401922c6  mov     qword ptr [rsp+0A8h+var_50], rsi
0x1401922cb  mov     r8d, 65725049h
0x1401922d1  mov     dword ptr [rsp+0A8h+var_88], esi
0x1401922d5  call    cs:__imp_ExAllocatePool3
0x1401922dc  nop     dword ptr [rax+rax+00h]
0x1401922e1  mov     rsi, rax
0x1401922e4  test    rax, rax
0x1401922e7  jnz     short loc_140192301
0x1401922e9  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x1401922ef  jge     loc_1401923AB
0x1401922f5  lea     r9, aFragmentIpng; "fragment (IPNG)"
0x1401922fc  jmp     loc_140192398
0x140192301  cmp     dword ptr [rbp+0A8h], 1
0x140192308  jnz     loc_140192400
0x14019230e  movzx   r14d, [rsp+0A8h+arg_8]
0x140192317  xor     r8d, r8d
0x14019231a  mov     rcx, [rsp+0A8h+arg_10]
0x140192322  mov     edx, r14d
0x140192325  call    cs:__imp_NetioRetreatNetBufferList
0x14019232c  nop     dword ptr [rax+rax+00h]
0x140192331  mov     edi, eax
0x140192333  test    eax, eax
0x140192335  jns     short loc_14019233F
0x140192337  mov     dword ptr [rbx], 0Dh
0x14019233d  jmp     short loc_1401923B6
0x14019233f  mov     rcx, [rsp+0A8h+arg_10]
0x140192347  xor     r9d, r9d
0x14019234a  mov     byte ptr [rsp+0A8h+var_80], 1
0x14019234f  xor     r8d, r8d
0x140192352  xor     edx, edx
0x140192354  mov     [rsp+0A8h+var_88], 1
0x140192359  call    cs:__imp_NetioAllocateAndReferenceVacantNetBufferList
0x140192360  nop     dword ptr [rax+rax+00h]
0x140192365  mov     rcx, [rsp+0A8h+arg_10]
0x14019236d  mov     edx, r14d
0x140192370  mov     [rsi+10h], rax
0x140192374  call    cs:__imp_NetioAdvanceNetBufferList
0x14019237b  nop     dword ptr [rax+rax+00h]
0x140192380  mov     rcx, [rsi+10h]
0x140192384  test    rcx, rcx
0x140192387  jnz     short loc_1401923EC
0x140192389  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, cl
0x14019238f  jge     short loc_1401923AB
0x140192391  lea     r9, aFragmentNblFor; "fragment NBL for grouping (IPNG)"
0x140192398  lea     rdx, TCPIP_MEMORY_FAILURES
0x14019239f  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401923a6  call    McTemplateK0z_EtwWriteTransfer
0x1401923ab  mov     edi, 0C000009Ah
0x1401923b0  mov     dword ptr [rbx], 3
0x1401923b6  mov     dl, [rsp+0A8h+NewIrql]; NewIrql
0x1401923bd  lea     rcx, [rbp+30h]; SpinLock
0x1401923c1  call    cs:__imp_KeReleaseSpinLock
0x1401923c8  nop     dword ptr [rax+rax+00h]
0x1401923cd  test    rsi, rsi
0x1401923d0  jz      loc_1401924E7
0x1401923d6  xor     edx, edx; Tag
0x1401923d8  mov     rcx, rsi; P
0x1401923db  call    cs:__imp_ExFreePoolWithTag
0x1401923e2  nop     dword ptr [rax+rax+00h]
0x1401923e7  jmp     loc_1401924E7
0x1401923ec  mov     edx, r14d
0x1401923ef  call    cs:__imp_NetioAdvanceNetBufferList
0x1401923f6  nop     dword ptr [rax+rax+00h]
0x1401923fb  jmp     loc_140192490
0x140192400  mov     r10d, [r15]
0x140192403  lea     rcx, [rax+10h]; MemoryDescriptorList
0x140192407  mov     r8d, 0FFFh
0x14019240d  mov     qword ptr [rcx], 0
0x140192414  lea     rbx, [r14+10h]
0x140192418  mov     [rcx+28h], r10d
0x14019241c  add     rbx, rsi
0x14019241f  mov     r9d, ebx
0x140192422  lea     rdx, [r10+0FFFh]
0x140192429  mov     eax, r9d
0x14019242c  and     r9d, r8d
0x14019242f  and     rax, r8
0x140192432  mov     [rcx+2Ch], r9d
0x140192436  add     rdx, rax
0x140192439  xor     eax, eax
0x14019243b  shr     rdx, 0Ch
0x14019243f  mov     [rcx+0Ah], ax
0x140192443  add     dx, 6
0x140192447  shl     dx, 3
0x14019244b  mov     rax, rbx
0x14019244e  and     rax, 0FFFFFFFFFFFFF000h
0x140192454  mov     [rcx+8], dx
0x140192458  mov     [rcx+20h], rax
0x14019245c  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140192463  nop     dword ptr [rax+rax+00h]
0x140192468  mov     rcx, [rsp+0A8h+var_60]
0x14019246d  lea     rax, [rsp+0A8h+var_58]
0x140192472  mov     r9d, [r15]
0x140192475  mov     r8, rbx
0x140192478  mov     qword ptr [rsp+0A8h+var_88], rax
0x14019247d  mov     edx, [rcx+10h]
0x140192480  mov     rcx, [rcx+8]
0x140192484  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x14019248b  nop     dword ptr [rax+rax+00h]
0x140192490  mov     rdx, [rsp+0A8h+var_68]
0x140192495  mov     r8, rsi
0x140192498  mov     rcx, rbp
0x14019249b  mov     qword ptr [rsi], 0
0x1401924a2  mov     [rsi+0Ah], r13w
0x1401924a7  mov     [rsi+8], r12w
0x1401924ac  call    IppReassemblyInsertFragment
0x1401924b1  add     [rbp+7Ch], r12d
0x1401924b5  cmp     [rsp+0A8h+arg_28], 0
0x1401924bd  jz      short loc_1401924C6
0x1401924bf  lea     eax, [r12+r13]
0x1401924c3  mov     [rbp+78h], eax
0x1401924c6  mov     r9d, [r15]
0x1401924c9  mov     rdx, rbp
0x1401924cc  mov     rcx, [rsp+0A8h+arg_0]
0x1401924d4  add     rcx, 5750h
0x1401924db  lea     r8d, [r9+100h]
0x1401924e2  call    IppIncreaseReassemblySize
0x1401924e7  mov     eax, edi
0x1401924e9  mov     rbx, [rsp+0A8h+arg_18]
0x1401924f1  add     rsp, 70h
0x1401924f5  pop     r15
0x1401924f7  pop     r14
0x1401924f9  pop     r13
0x1401924fb  pop     r12
0x1401924fd  pop     rdi
0x1401924fe  pop     rsi
0x1401924ff  pop     rbp
0x140192500  retn
```
