# VmsNblHelperCreateDuplicateNblForInspection

- ea: `0x140073a60`
- end: `0x140073e7e`
- name: `VmsNblHelperCreateDuplicateNblForInspection`
- size: `1054`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14001c850`

## callees

- `0x140006620`
- `0x14001736c`
- `0x14002a1fc`
- `0x14006b248`
- `0x140073a60`
- `0x140114278`
- `0x140114908`
- `0x140114a0c`
- `0x1401bbbc2`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140073bde`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140073bde`
- `ntoskrnl!KeReleaseSpinLock` at `0x140073e0b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140073e0b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140073c7d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140073c7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073e33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073e33`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140073dda`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x140073dda`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x140073dcc`
- `NDIS!NdisCopyReceiveNetBufferListInfo` at `0x140073dcc`

## string_xrefs

- `0x140073aea`: `VmsNblHelperCreateDuplicateNblForInspection`

## pseudocode

```c
__int64 __fastcall VmsNblHelperCreateDuplicateNblForInspection(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        __int64 a5,
        struct _NET_BUFFER_LIST **a6)
{
  struct _NET_BUFFER_LIST **v6; // r13
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  bool v15; // bl
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned __int64 v18; // rax
  void *v19; // rsp
  struct _NET_BUFFER_LIST *v20; // rbx
  void *v21; // r14
  __int64 v22; // r15
  KIRQL v23; // al
  bool v24; // cf
  int MdlAndData; // esi
  SIZE_T v26; // r14
  int v27; // r8d
  __int64 NetBufferAndNetBufferList; // rax
  unsigned int v29; // edx
  _DWORD *v30; // rax
  _QWORD *v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // r8
  int v35; // [rsp+20h] [rbp-20h]
  SIZE_T v36; // [rsp+28h] [rbp-18h]
  char v37; // [rsp+40h] [rbp+0h] BYREF
  KIRQL NewIrql; // [rsp+41h] [rbp+1h]
  struct _NET_BUFFER_LIST **v39; // [rsp+48h] [rbp+8h]
  int v40[2]; // [rsp+50h] [rbp+10h]
  __int64 v41; // [rsp+58h] [rbp+18h]
  __int64 v42; // [rsp+60h] [rbp+20h]
  PKSPIN_LOCK SpinLock; // [rsp+68h] [rbp+28h]
  int v44[24]; // [rsp+70h] [rbp+30h] BYREF
  _UNKNOWN *retaddr; // [rsp+118h] [rbp+D8h]

  v6 = a6;
  v42 = a1;
  v37 = a4;
  v39 = a6;
  v41 = 0;
  memset(v44, 0, sizeof(v44));
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( a2 )
    {
      v9 = *(_QWORD *)(a2 + 288);
      if ( v9 )
      {
        v10 = *(_QWORD *)(v9 + 16);
        if ( v10 )
        {
          *(_DWORD *)(v10 + 184) = 1391;
          *(_QWORD *)(v10 + 176) = "VmsNblHelperCreateDuplicateNblForInspection";
          *(_QWORD *)(v10 + 168) = retaddr;
        }
      }
    }
  }
  v11 = 4;
  if ( byte_1401F96F0 )
    v11 = HIDWORD(qword_1401F96CC);
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( a2 )
    {
      v12 = *(_QWORD *)(a2 + 288);
      if ( v12 )
      {
        v13 = *(_QWORD *)(v12 + 16);
        if ( v13 )
        {
          *(_DWORD *)(v13 + 184) = 75;
          *(_QWORD *)(v13 + 176) = "VmsNblIsSourceNicUntrusted";
          *(_QWORD *)(v13 + 168) = retaddr;
        }
      }
    }
  }
  v14 = *(_QWORD *)(a2 + 288);
  v15 = 0;
  if ( v14 )
  {
    v16 = *(_QWORD *)(v14 + 16);
    if ( v16 )
    {
      v17 = *(_QWORD *)(v16 + 24);
      if ( v17 )
      {
        if ( *(_DWORD *)(v17 + 1872) == 3 )
          v15 = *(_BYTE *)(v17 + 1877) == 0;
      }
    }
  }
  v18 = 24 * v11 + 15;
  if ( v18 <= 24 * v11 )
    v18 = 0xFFFFFFFFFFFFFF0LL;
  v19 = alloca(v18 & 0xFFFFFFFFFFFFFFF0uLL);
  if ( !v15 || qword_1401F96E0 )
  {
    v44[0] = -267522035;
    v44[3] = KeGetCurrentProcessorNumberEx(0);
    LOBYTE(v44[1]) = 0;
    *(_QWORD *)&v44[6] = 0;
    *(_QWORD *)&v44[4] = 1;
    v44[2] = (qword_1401F96E0 != 0 ? 4 : 0) | v15;
    memset(&v44[11], 0, 24);
    LOBYTE(v44[10]) = 0;
    *(_QWORD *)&v44[8] = &v44[14];
    if ( &v37 )
    {
      v44[17] = v11;
      *(_QWORD *)&v44[18] = &v37;
    }
    else
    {
      v44[17] = 0;
      *(_QWORD *)&v44[18] = 0;
    }
    *(_QWORD *)&v44[20] = &g_BatchLibContext;
  }
  v20 = 0;
  *(_QWORD *)v40 = 0;
  v21 = 0;
  v22 = *(_QWORD *)(a2 + 288);
  if ( v22 )
    v22 = *(_QWORD *)(v22 + 16);
  SpinLock = (PKSPIN_LOCK)(a3 + 5904);
  v23 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 5904));
  v24 = *(_DWORD *)(a3 + 5896) < 0x80u;
  NewIrql = v23;
  if ( v24 )
  {
    v26 = *(unsigned int *)(*(_QWORD *)(a2 + 8) + 24LL);
    MdlAndData = VmsNblHelperAllocateMdlAndData(v26);
    if ( MdlAndData < 0 || (MdlAndData = VncDeferredCopyNetBufferData((int)v44), MdlAndData < 0) )
    {
      v21 = *(void **)v40;
    }
    else
    {
      v36 = v26;
      v21 = *(void **)v40;
      NetBufferAndNetBufferList = VmsNblHelperAllocateNetBufferAndNetBufferList(
                                    *(_QWORD *)(a3 + 5912),
                                    40,
                                    v27,
                                    v40[0],
                                    v35,
                                    v36,
                                    1);
      v20 = (struct _NET_BUFFER_LIST *)NetBufferAndNetBufferList;
      if ( NetBufferAndNetBufferList )
      {
        *(_WORD *)(NetBufferAndNetBufferList + 298) = *(_WORD *)(a2 + 298);
        *(_BYTE *)(NetBufferAndNetBufferList + 300) = *(_BYTE *)(a2 + 300);
        v29 = *(_DWORD *)(NetBufferAndNetBufferList + 300) & 0xFEFFFBFF | 0x400;
        *(_DWORD *)(NetBufferAndNetBufferList + 300) = v29;
        *(_DWORD *)(NetBufferAndNetBufferList + 300) = v29 ^ (*(_DWORD *)(a2 + 300) ^ v29) & 0x100;
        if ( !*(_DWORD *)(v22 + 68)
          || (MdlAndData = VmsNblHelperCopyNblDestinations(v42, NetBufferAndNetBufferList, v22 + 40), MdlAndData >= 0) )
        {
          v30 = v20->NetBufferListInfo[18];
          v30[6] = 1;
          *(_QWORD *)v30 = 4;
          *((_QWORD *)v30 + 4) = 0;
          v31 = v20->NetBufferListInfo[18];
          if ( v31 )
            v32 = v31[2];
          else
            v32 = 0;
          *(_QWORD *)(v32 + 24) = *(_QWORD *)(v22 + 24);
          if ( (*(_DWORD *)v22 & 1) != 0 )
            *(_DWORD *)v32 = 1;
          if ( v37 )
            NdisCopyReceiveNetBufferListInfo(v20, (PNET_BUFFER_LIST)a2);
          else
            NdisCopySendNetBufferListInfo(v20, (PNET_BUFFER_LIST)a2);
          v20->ParentNetBufferList = (_NET_BUFFER_LIST *)a2;
          VmsNblHelperRefCountIncrement(a2);
          ++*(_DWORD *)(a3 + 5896);
        }
      }
      else
      {
        MdlAndData = -1073741670;
      }
    }
    v6 = v39;
  }
  else
  {
    MdlAndData = -1073741756;
  }
  KeReleaseSpinLock(SpinLock, NewIrql);
  LOBYTE(v33) = 1;
  BLFlushBatchOpContextEx(v44, 0, v33);
  if ( MdlAndData < 0 )
  {
    if ( v21 )
      ExFreePoolWithTag(v21, 0);
    if ( v20 )
    {
      VmsNblHelperFreeNetBufferList(v20);
      v20 = 0;
    }
  }
  *v6 = v20;
  return (unsigned int)MdlAndData;
}

```

## disassembly

```asm
0x140073a60  push    rbp
0x140073a62  push    rsi
0x140073a63  push    rdi
0x140073a64  push    r12
0x140073a66  push    r13
0x140073a68  push    r14
0x140073a6a  push    r15
0x140073a6c  sub     rsp, 0E0h
0x140073a73  lea     rbp, [rsp+40h]
0x140073a78  mov     [rbp+0D0h+arg_18], rbx
0x140073a7f  mov     rax, cs:__security_cookie
0x140073a86  xor     rax, rbp
0x140073a89  mov     [rbp+0D0h+var_40], rax
0x140073a90  mov     r13, [rbp+0D0h+arg_28]
0x140073a97  xor     r15d, r15d
0x140073a9a  mov     r12, r8
0x140073a9d  mov     [rbp+0D0h+var_B0], rcx
0x140073aa1  mov     rdi, rdx
0x140073aa4  mov     [rbp+0D0h+var_D0], r9b
0x140073aa8  xor     edx, edx; Val
0x140073aaa  mov     [rbp+0D0h+var_C8], r13
0x140073aae  lea     r8d, [r15+60h]; Size
0x140073ab2  mov     [rbp+0D0h+var_B8], r15
0x140073ab6  lea     rcx, [rbp+0D0h+var_A0]; void *
0x140073aba  call    memset
0x140073abf  mov     eax, cs:VmsDiagnosticFlags
0x140073ac5  mov     rcx, [rbp+0D8h]
0x140073acc  test    al, 1
0x140073ace  jz      short loc_140073B09
0x140073ad0  test    rdi, rdi
0x140073ad3  jz      short loc_140073B09
0x140073ad5  mov     rax, [rdi+120h]
0x140073adc  test    rax, rax
0x140073adf  jz      short loc_140073B09
0x140073ae1  mov     rax, [rax+10h]
0x140073ae5  test    rax, rax
0x140073ae8  jz      short loc_140073B09
0x140073aea  lea     rdx, aVmsnblhelpercr; "VmsNblHelperCreateDuplicateNblForInspec"...
0x140073af1  mov     dword ptr [rax+0B8h], 56Fh
0x140073afb  mov     [rax+0B0h], rdx
0x140073b02  mov     [rax+0A8h], rcx
0x140073b09  cmp     cs:byte_1401F96F0, r15b
0x140073b10  mov     esi, 4
0x140073b15  mov     eax, cs:VmsDiagnosticFlags
0x140073b1b  cmovnz  esi, dword ptr cs:qword_1401F96CC+4
0x140073b22  mov     rcx, [rbp+0D8h]
0x140073b29  test    al, 1
0x140073b2b  jz      short loc_140073B66
0x140073b2d  test    rdi, rdi
0x140073b30  jz      short loc_140073B66
0x140073b32  mov     rax, [rdi+120h]
0x140073b39  test    rax, rax
0x140073b3c  jz      short loc_140073B66
0x140073b3e  mov     rax, [rax+10h]
0x140073b42  test    rax, rax
0x140073b45  jz      short loc_140073B66
0x140073b47  lea     rdx, aVmsnblissource; "VmsNblIsSourceNicUntrusted"
0x140073b4e  mov     dword ptr [rax+0B8h], 4Bh ; 'K'
0x140073b58  mov     [rax+0B0h], rdx
0x140073b5f  mov     [rax+0A8h], rcx
0x140073b66  mov     rax, [rdi+120h]
0x140073b6d  mov     bl, r15b
0x140073b70  test    rax, rax
0x140073b73  jz      short loc_140073B9B
0x140073b75  mov     rax, [rax+10h]
0x140073b79  test    rax, rax
0x140073b7c  jz      short loc_140073B9B
0x140073b7e  mov     rax, [rax+18h]
0x140073b82  test    rax, rax
0x140073b85  jz      short loc_140073B9B
0x140073b87  cmp     dword ptr [rax+750h], 3
0x140073b8e  jnz     short loc_140073B9B
0x140073b90  cmp     [rax+755h], r15b
0x140073b97  jnz     short loc_140073B9B
0x140073b99  mov     bl, 1
0x140073b9b  lea     rcx, [rsi+rsi*2]
0x140073b9f  shl     rcx, 3
0x140073ba3  lea     rax, [rcx+0Fh]
0x140073ba7  cmp     rax, rcx
0x140073baa  ja      short loc_140073BB6
0x140073bac  mov     rax, 0FFFFFFFFFFFFFF0h
0x140073bb6  and     rax, 0FFFFFFFFFFFFFFF0h
0x140073bba  call    __chkstk_0
0x140073bbf  sub     rsp, rax
0x140073bc2  lea     r14, [rsp+110h+var_D0]
0x140073bc7  cmp     bl, 1
0x140073bca  jnz     short loc_140073BD5
0x140073bcc  cmp     cs:qword_1401F96E0, r15
0x140073bd3  jz      short loc_140073C54
0x140073bd5  xor     ecx, ecx; ProcNumber
0x140073bd7  mov     [rbp+0D0h+var_A0], 0F00DF00Dh
0x140073bde  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140073be5  nop     dword ptr [rax+rax+00h]
0x140073bea  mov     [rbp+0D0h+var_94], eax
0x140073bed  mov     rax, cs:qword_1401F96E0
0x140073bf4  neg     rax
0x140073bf7  movzx   edx, bl
0x140073bfa  lea     rax, [rbp+0D0h+var_68]
0x140073bfe  mov     [rbp+0D0h+var_9C], r15b
0x140073c02  sbb     ecx, ecx
0x140073c04  mov     [rbp+0D0h+var_88], r15
0x140073c08  and     ecx, 4
0x140073c0b  mov     [rbp+0D0h+var_90], 1
0x140073c13  or      edx, ecx
0x140073c15  mov     [rbp+0D0h+var_70], r15
0x140073c19  mov     [rbp+0D0h+var_98], edx
0x140073c1c  mov     [rbp+0D0h+var_74], r15d
0x140073c20  mov     [rbp+0D0h+var_78], r15b
0x140073c24  mov     [rbp+0D0h+var_68], r15
0x140073c28  mov     [rbp+0D0h+var_60], r15d
0x140073c2c  mov     [rbp+0D0h+var_80], rax
0x140073c30  test    r14, r14
0x140073c33  jz      short loc_140073C3E
0x140073c35  mov     [rbp+0D0h+var_5C], esi
0x140073c38  mov     [rbp+0D0h+var_58], r14
0x140073c3c  jmp     short loc_140073C46
0x140073c3e  mov     [rbp+0D0h+var_5C], r15d
0x140073c42  mov     [rbp+0D0h+var_58], r15
0x140073c46  lea     rax, g_BatchLibContext
0x140073c4d  mov     [rbp+0D0h+var_50], rax
0x140073c54  mov     rbx, r15
0x140073c57  mov     qword ptr [rbp+0D0h+var_C0], r15
0x140073c5b  mov     r14, r15
0x140073c5e  mov     r15, [rdi+120h]
0x140073c65  test    r15, r15
0x140073c68  jz      short loc_140073C6E
0x140073c6a  mov     r15, [r15+10h]
0x140073c6e  lea     rax, [r12+1710h]
0x140073c76  mov     rcx, rax; SpinLock
0x140073c79  mov     [rbp+0D0h+SpinLock], rax
0x140073c7d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140073c84  nop     dword ptr [rax+rax+00h]
0x140073c89  cmp     dword ptr [r12+1708h], 80h
0x140073c95  mov     [rbp+0D0h+NewIrql], al
0x140073c98  jb      short loc_140073CA4
0x140073c9a  mov     esi, 0C0000044h
0x140073c9f  jmp     loc_140073E04
0x140073ca4  mov     r13, [rdi+8]
0x140073ca8  lea     r8, [rbp+0D0h+var_B8]
0x140073cac  lea     rdx, [rbp+0D0h+var_C0]
0x140073cb0  mov     r14d, [r13+18h]
0x140073cb4  mov     ecx, r14d; Length
0x140073cb7  call    VmsNblHelperAllocateMdlAndData
0x140073cbc  mov     esi, eax
0x140073cbe  test    eax, eax
0x140073cc0  js      loc_140073DFC
0x140073cc6  mov     r8, [rbp+0D0h+var_B8]
0x140073cca  lea     rcx, [rbp+0D0h+var_A0]; int
0x140073cce  mov     r9d, r14d
0x140073cd1  mov     rdx, r13
0x140073cd4  call    VncDeferredCopyNetBufferData
0x140073cd9  xor     r13d, r13d
0x140073cdc  mov     esi, eax
0x140073cde  test    eax, eax
0x140073ce0  js      loc_140073DFC
0x140073ce6  mov     rcx, [r12+1718h]; int
0x140073cee  lea     edx, [r13+28h]; int
0x140073cf2  mov     [rsp+110h+var_E0], 1; int
0x140073cfa  mov     [rsp+110h+var_E8], r14; SIZE_T
0x140073cff  mov     r14, qword ptr [rbp+0D0h+var_C0]
0x140073d03  mov     r9, r14; int
0x140073d06  call    VmsNblHelperAllocateNetBufferAndNetBufferList
0x140073d0b  mov     rbx, rax
0x140073d0e  test    rax, rax
0x140073d11  jnz     short loc_140073D1D
0x140073d13  mov     esi, 0C000009Ah
0x140073d18  jmp     loc_140073E00
0x140073d1d  movzx   eax, word ptr [rdi+12Ah]
0x140073d24  mov     [rbx+12Ah], ax
0x140073d2b  mov     al, [rdi+12Ch]
0x140073d31  mov     [rbx+12Ch], al
0x140073d37  mov     edx, [rbx+12Ch]
0x140073d3d  btr     edx, 18h
0x140073d41  bts     edx, 0Ah
0x140073d45  mov     [rbx+12Ch], edx
0x140073d4b  mov     eax, edx
0x140073d4d  xor     eax, [rdi+12Ch]
0x140073d53  and     eax, 100h
0x140073d58  xor     eax, edx
0x140073d5a  mov     [rbx+12Ch], eax
0x140073d60  cmp     [r15+44h], r13d
0x140073d64  jz      short loc_140073D80
0x140073d66  mov     rcx, [rbp+0D0h+var_B0]
0x140073d6a  lea     r8, [r15+28h]
0x140073d6e  mov     rdx, rbx
0x140073d71  call    VmsNblHelperCopyNblDestinations
0x140073d76  mov     esi, eax
0x140073d78  test    eax, eax
0x140073d7a  js      loc_140073E00
0x140073d80  mov     rax, [rbx+120h]
0x140073d87  mov     edx, 1
0x140073d8c  mov     [rax+18h], edx
0x140073d8f  mov     qword ptr [rax], 4
0x140073d96  mov     [rax+20h], r13
0x140073d9a  mov     rcx, [rbx+120h]
0x140073da1  test    rcx, rcx
0x140073da4  jnz     short loc_140073DAB
0x140073da6  mov     rcx, r13
0x140073da9  jmp     short loc_140073DAF
0x140073dab  mov     rcx, [rcx+10h]
0x140073daf  mov     rax, [r15+18h]
0x140073db3  mov     [rcx+18h], rax
0x140073db7  mov     eax, [r15]
0x140073dba  test    dl, al
0x140073dbc  jz      short loc_140073DC0
0x140073dbe  mov     [rcx], edx
0x140073dc0  mov     rdx, rdi; SrcNetBufferList
0x140073dc3  mov     rcx, rbx; DestNetBufferList
0x140073dc6  cmp     [rbp+0D0h+var_D0], r13b
0x140073dca  jz      short loc_140073DDA
0x140073dcc  call    cs:__imp_NdisCopyReceiveNetBufferListInfo
0x140073dd3  nop     dword ptr [rax+rax+00h]
0x140073dd8  jmp     short loc_140073DE6
0x140073dda  call    cs:__imp_NdisCopySendNetBufferListInfo
0x140073de1  nop     dword ptr [rax+rax+00h]
0x140073de6  mov     rcx, rdi
0x140073de9  mov     [rbx+18h], rdi
0x140073ded  call    VmsNblHelperRefCountIncrement
0x140073df2  inc     dword ptr [r12+1708h]
0x140073dfa  jmp     short loc_140073E00
0x140073dfc  mov     r14, qword ptr [rbp+0D0h+var_C0]
0x140073e00  mov     r13, [rbp+0D0h+var_C8]
0x140073e04  mov     dl, [rbp+0D0h+NewIrql]; NewIrql
0x140073e07  mov     rcx, [rbp+0D0h+SpinLock]; SpinLock
0x140073e0b  call    cs:__imp_KeReleaseSpinLock
0x140073e12  nop     dword ptr [rax+rax+00h]
0x140073e17  mov     r8b, 1
0x140073e1a  lea     rcx, [rbp+0D0h+var_A0]
0x140073e1e  xor     edx, edx
0x140073e20  call    BLFlushBatchOpContextEx
0x140073e25  test    esi, esi
0x140073e27  jns     short loc_140073E4E
0x140073e29  test    r14, r14
0x140073e2c  jz      short loc_140073E3F
0x140073e2e  xor     edx, edx; Tag
0x140073e30  mov     rcx, r14; P
0x140073e33  call    cs:__imp_ExFreePoolWithTag
0x140073e3a  nop     dword ptr [rax+rax+00h]
0x140073e3f  test    rbx, rbx
0x140073e42  jz      short loc_140073E4E
0x140073e44  mov     rcx, rbx; NetBufferList
0x140073e47  call    VmsNblHelperFreeNetBufferList
0x140073e4c  xor     ebx, ebx
0x140073e4e  mov     [r13+0], rbx
0x140073e52  mov     eax, esi
0x140073e54  mov     rcx, [rbp+0D0h+var_40]
0x140073e5b  xor     rcx, rbp; StackCookie
0x140073e5e  call    __security_check_cookie
0x140073e63  mov     rbx, [rbp+0D0h+arg_18]
0x140073e6a  lea     rsp, [rbp+0A0h]
0x140073e71  pop     r15
0x140073e73  pop     r14
0x140073e75  pop     r13
0x140073e77  pop     r12
0x140073e79  pop     rdi
0x140073e7a  pop     rsi
0x140073e7b  pop     rbp
0x140073e7c  retn
```
