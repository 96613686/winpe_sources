# IppCreateAndInsertFragmentIntoGroup

- ea: `0x140193e70`
- end: `0x1401941a2`
- name: `IppCreateAndInsertFragmentIntoGroup`
- size: `818`
- prototype: `__int64 __fastcall(int, int, int, int, int, char, __int64, KIRQL NewIrql, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400f8430`
- `0x1400ff954`

## callees

- `0x140014a08`
- `0x1400f201c`
- `0x1400f21f0`
- `0x140193e70`
- `0x1401941a8`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x140193f35`
- `ntoskrnl!MmSizeOfMdl` at `0x140193f35`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1401940fc`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1401940fc`
- `ntoskrnl!ExAllocatePool3` at `0x140193f75`
- `ntoskrnl!ExAllocatePool3` at `0x140193f75`
- `ntoskrnl!KeReleaseSpinLock` at `0x140194061`
- `ntoskrnl!KeReleaseSpinLock` at `0x140194061`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019407b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019407b`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x140194124`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x140194124`
- `NETIO!NetioAdvanceNetBufferList` at `0x140194014`
- `NETIO!NetioAdvanceNetBufferList` at `0x14019408f`
- `NETIO!NetioAdvanceNetBufferList` at `0x140194014`
- `NETIO!NetioAdvanceNetBufferList` at `0x14019408f`
- `NETIO!NetioAllocateAndReferenceVacantNetBufferList` at `0x140193ff9`
- `NETIO!NetioAllocateAndReferenceVacantNetBufferList` at `0x140193ff9`
- `NETIO!NetioRetreatNetBufferList` at `0x140193fc5`
- `NETIO!NetioRetreatNetBufferList` at `0x140193fc5`

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
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
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
        if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
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
0x140193e70  mov     r11, rsp
0x140193e73  mov     [r11+20h], rbx
0x140193e77  mov     [r11+18h], r8
0x140193e7b  mov     [r11+8], rcx
0x140193e7f  push    rbp
0x140193e80  push    rsi
0x140193e81  push    rdi
0x140193e82  push    r12
0x140193e84  push    r13
0x140193e86  push    r14
0x140193e88  push    r15
0x140193e8a  sub     rsp, 70h
0x140193e8e  mov     rax, [rdx+30h]
0x140193e92  xorps   xmm0, xmm0
0x140193e95  mov     rsi, [r8+8]
0x140193e99  mov     r12d, r9d
0x140193e9c  mov     rbx, [rsp+0A8h+arg_40]
0x140193ea4  mov     rbp, [rsp+0A8h+arg_30]
0x140193eac  mov     r13d, [rsp+0A8h+arg_20]
0x140193eb4  mov     rdx, rbp; int
0x140193eb7  mov     [r11-70h], rbx
0x140193ebb  mov     r8d, r13d; int
0x140193ebe  mov     qword ptr [r11-58h], 0
0x140193ec6  mov     al, [rax]
0x140193ec8  mov     [rsp+0A8h+arg_8], al
0x140193ecf  lea     rax, [r11-68h]
0x140193ed3  mov     [r11-78h], rax
0x140193ed7  mov     al, [rsp+0A8h+NewIrql]
0x140193ede  mov     byte ptr [rsp+0A8h+var_80], al; NewIrql
0x140193ee2  mov     al, [rsp+0A8h+arg_28]
0x140193ee9  mov     [rsp+0A8h+var_88], al; char
0x140193eed  mov     qword ptr [r11-68h], 0
0x140193ef5  mov     [rsp+0A8h+var_60], rsi
0x140193efa  movups  [rsp+0A8h+var_50], xmm0
0x140193eff  mov     dword ptr [rbx], 12h
0x140193f05  call    IppFindLocationInFragmentGroup
0x140193f0a  mov     edi, eax
0x140193f0c  test    eax, eax
0x140193f0e  js      loc_140194189
0x140193f14  lea     r15, [rsi+18h]
0x140193f18  mov     esi, 1
0x140193f1d  cmp     [rbp+0A8h], esi
0x140193f23  jnz     short loc_140193F2D
0x140193f25  xor     r14d, r14d
0x140193f28  lea     edx, [rsi+3Fh]
0x140193f2b  jmp     short loc_140193F53
0x140193f2d  mov     edx, [r15]; Length
0x140193f30  mov     ecx, 0FFFh; Base
0x140193f35  call    cs:__imp_MmSizeOfMdl
0x140193f3c  nop     dword ptr [rax+rax+00h]
0x140193f41  mov     edx, [r15]
0x140193f44  add     rdx, 10h
0x140193f48  lea     r14, [rax+7]
0x140193f4c  and     r14, 0FFFFFFFFFFFFFFF8h
0x140193f50  add     rdx, r14
0x140193f53  lea     r9, [rsp+0A8h+var_50]
0x140193f58  mov     qword ptr [rsp+0A8h+var_50+8], 0
0x140193f61  mov     ecx, 40h ; '@'
0x140193f66  mov     qword ptr [rsp+0A8h+var_50], rsi
0x140193f6b  mov     r8d, 65725049h
0x140193f71  mov     dword ptr [rsp+0A8h+var_88], esi
0x140193f75  call    cs:__imp_ExAllocatePool3
0x140193f7c  nop     dword ptr [rax+rax+00h]
0x140193f81  mov     rsi, rax
0x140193f84  test    rax, rax
0x140193f87  jnz     short loc_140193FA1
0x140193f89  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, al
0x140193f8f  jge     loc_14019404B
0x140193f95  lea     r9, aFragmentIpng; "fragment (IPNG)"
0x140193f9c  jmp     loc_140194038
0x140193fa1  cmp     dword ptr [rbp+0A8h], 1
0x140193fa8  jnz     loc_1401940A0
0x140193fae  movzx   r14d, [rsp+0A8h+arg_8]
0x140193fb7  xor     r8d, r8d
0x140193fba  mov     rcx, [rsp+0A8h+arg_10]
0x140193fc2  mov     edx, r14d
0x140193fc5  call    cs:__imp_NetioRetreatNetBufferList
0x140193fcc  nop     dword ptr [rax+rax+00h]
0x140193fd1  mov     edi, eax
0x140193fd3  test    eax, eax
0x140193fd5  jns     short loc_140193FDF
0x140193fd7  mov     dword ptr [rbx], 0Dh
0x140193fdd  jmp     short loc_140194056
0x140193fdf  mov     rcx, [rsp+0A8h+arg_10]
0x140193fe7  xor     r9d, r9d
0x140193fea  mov     byte ptr [rsp+0A8h+var_80], 1
0x140193fef  xor     r8d, r8d
0x140193ff2  xor     edx, edx
0x140193ff4  mov     [rsp+0A8h+var_88], 1
0x140193ff9  call    cs:__imp_NetioAllocateAndReferenceVacantNetBufferList
0x140194000  nop     dword ptr [rax+rax+00h]
0x140194005  mov     rcx, [rsp+0A8h+arg_10]
0x14019400d  mov     edx, r14d
0x140194010  mov     [rsi+10h], rax
0x140194014  call    cs:__imp_NetioAdvanceNetBufferList
0x14019401b  nop     dword ptr [rax+rax+00h]
0x140194020  mov     rcx, [rsi+10h]
0x140194024  test    rcx, rcx
0x140194027  jnz     short loc_14019408C
0x140194029  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, cl
0x14019402f  jge     short loc_14019404B
0x140194031  lea     r9, aFragmentNblFor; "fragment NBL for grouping (IPNG)"
0x140194038  lea     rdx, TCPIP_MEMORY_FAILURES
0x14019403f  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140194046  call    McTemplateK0z_EtwWriteTransfer
0x14019404b  mov     edi, 0C000009Ah
0x140194050  mov     dword ptr [rbx], 3
0x140194056  mov     dl, [rsp+0A8h+NewIrql]; NewIrql
0x14019405d  lea     rcx, [rbp+30h]; SpinLock
0x140194061  call    cs:__imp_KeReleaseSpinLock
0x140194068  nop     dword ptr [rax+rax+00h]
0x14019406d  test    rsi, rsi
0x140194070  jz      loc_140194187
0x140194076  xor     edx, edx; Tag
0x140194078  mov     rcx, rsi; P
0x14019407b  call    cs:__imp_ExFreePoolWithTag
0x140194082  nop     dword ptr [rax+rax+00h]
0x140194087  jmp     loc_140194187
0x14019408c  mov     edx, r14d
0x14019408f  call    cs:__imp_NetioAdvanceNetBufferList
0x140194096  nop     dword ptr [rax+rax+00h]
0x14019409b  jmp     loc_140194130
0x1401940a0  mov     r10d, [r15]
0x1401940a3  lea     rcx, [rax+10h]; MemoryDescriptorList
0x1401940a7  mov     r8d, 0FFFh
0x1401940ad  mov     qword ptr [rcx], 0
0x1401940b4  lea     rbx, [r14+10h]
0x1401940b8  mov     [rcx+28h], r10d
0x1401940bc  add     rbx, rsi
0x1401940bf  mov     r9d, ebx
0x1401940c2  lea     rdx, [r10+0FFFh]
0x1401940c9  mov     eax, r9d
0x1401940cc  and     r9d, r8d
0x1401940cf  and     rax, r8
0x1401940d2  mov     [rcx+2Ch], r9d
0x1401940d6  add     rdx, rax
0x1401940d9  xor     eax, eax
0x1401940db  shr     rdx, 0Ch
0x1401940df  mov     [rcx+0Ah], ax
0x1401940e3  add     dx, 6
0x1401940e7  shl     dx, 3
0x1401940eb  mov     rax, rbx
0x1401940ee  and     rax, 0FFFFFFFFFFFFF000h
0x1401940f4  mov     [rcx+8], dx
0x1401940f8  mov     [rcx+20h], rax
0x1401940fc  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140194103  nop     dword ptr [rax+rax+00h]
0x140194108  mov     rcx, [rsp+0A8h+var_60]
0x14019410d  lea     rax, [rsp+0A8h+var_58]
0x140194112  mov     r9d, [r15]
0x140194115  mov     r8, rbx
0x140194118  mov     qword ptr [rsp+0A8h+var_88], rax
0x14019411d  mov     edx, [rcx+10h]
0x140194120  mov     rcx, [rcx+8]
0x140194124  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x14019412b  nop     dword ptr [rax+rax+00h]
0x140194130  mov     rdx, [rsp+0A8h+var_68]
0x140194135  mov     r8, rsi
0x140194138  mov     rcx, rbp
0x14019413b  mov     qword ptr [rsi], 0
0x140194142  mov     [rsi+0Ah], r13w
0x140194147  mov     [rsi+8], r12w
0x14019414c  call    IppReassemblyInsertFragment
0x140194151  add     [rbp+7Ch], r12d
0x140194155  cmp     [rsp+0A8h+arg_28], 0
0x14019415d  jz      short loc_140194166
0x14019415f  lea     eax, [r12+r13]
0x140194163  mov     [rbp+78h], eax
0x140194166  mov     r9d, [r15]
0x140194169  mov     rdx, rbp
0x14019416c  mov     rcx, [rsp+0A8h+arg_0]
0x140194174  add     rcx, 5750h
0x14019417b  lea     r8d, [r9+100h]
0x140194182  call    IppIncreaseReassemblySize
0x140194187  mov     eax, edi
0x140194189  mov     rbx, [rsp+0A8h+arg_18]
0x140194191  add     rsp, 70h
0x140194195  pop     r15
0x140194197  pop     r14
0x140194199  pop     r13
0x14019419b  pop     r12
0x14019419d  pop     rdi
0x14019419e  pop     rsi
0x14019419f  pop     rbp
0x1401941a0  retn
```
