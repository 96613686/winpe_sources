# CWPage::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x1800118b0`
- end: `0x180011bfb`
- name: `?CanRunPage@CWPage@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `843`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002556`
- `0x18000addc`
- `0x18000ae04`
- `0x18000ae44`
- `0x1800118b0`
- `0x18001bf44`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001198a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001198a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011a19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011a19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011a0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011a0b`

## pseudocode

```c
__int64 __fastcall CWPage::CanRunPage(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        int a7,
        __int64 a8,
        void **a9)
{
  void **v9; // r12
  unsigned int *v10; // r14
  __int64 v13; // rsi
  __int64 (__fastcall *v15)(__int64); // rax
  unsigned int v16; // edi
  void *v17; // rax
  void *v18; // rsi
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  void *v22; // rbx
  HANDLE ProcessHeap; // rax
  PVOID *v24; // rcx
  __int64 v26; // rcx
  int WrappedCOMComponent; // eax
  __int64 v28; // r10
  unsigned int v29; // eax
  void *Src; // [rsp+90h] [rbp+8h] BYREF
  __int64 v31; // [rsp+98h] [rbp+10h]

  v31 = a2;
  v9 = a9;
  v10 = (unsigned int *)(a1 + 8);
  Src = 0;
  v13 = a2;
  *a9 = 0;
  v15 = *(__int64 (__fastcall **)(__int64))(a1 + 32);
  if ( !v15 )
    goto LABEL_28;
  v16 = v15(a1 + 8);
  if ( !v16 )
  {
    if ( !Src || a4 != 1 && a4 != 2 && a4 != 32 && a4 != 512 && a4 != 1024 )
      goto LABEL_23;
    if ( (unsigned int)(*(_DWORD *)Src - 1) > 0x67 )
    {
      v18 = 0;
      v16 = -2147467261;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_19;
      v20 = 13;
      v21 = 2147500035LL;
    }
    else
    {
      v17 = CoTaskMemAlloc(0x68u);
      v18 = v17;
      if ( v17 )
      {
        memcpy_0(v17, Src, *(unsigned int *)Src);
LABEL_19:
        v22 = Src;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v22);
        Src = v18;
        v13 = v31;
        goto LABEL_20;
      }
      v16 = -2147024882;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_19;
      v20 = 14;
      v21 = 2147942414LL;
    }
    WPP_SF_d(v19[2], v20, WPP_e1654684cf453d0a1f37ee0675a51505_Traceguids, v21);
    goto LABEL_19;
  }
LABEL_20:
  if ( v16 != -2147467263 )
  {
    v24 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_22;
  }
LABEL_28:
  v26 = *(_QWORD *)(a1 + 104);
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    *(_QWORD *)(a1 + 104) = 0;
  }
  WrappedCOMComponent = HrCreateWrappedCOMComponent((__int64)v10, a4, (__int64)&IID_IXWizardPageEvent, a1 + 104);
  v16 = WrappedCOMComponent;
  if ( WrappedCOMComponent >= 0 )
    goto LABEL_38;
  if ( WrappedCOMComponent == -2147467263 )
  {
    v24 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_e1654684cf453d0a1f37ee0675a51505_Traceguids,
        *v10,
        -2147467263);
LABEL_38:
      v24 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v24 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_e1654684cf453d0a1f37ee0675a51505_Traceguids,
        (unsigned int)WrappedCOMComponent);
      goto LABEL_38;
    }
  }
  v28 = *(_QWORD *)(a1 + 104);
  if ( v28 )
  {
    v29 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, int, __int64, int, __int64, void **))(*(_QWORD *)v28 + 56LL))(
            v28,
            v13,
            a3,
            a4,
            a5,
            a6,
            a7,
            a8,
            &Src);
    v24 = (PVOID *)WPP_GLOBAL_Control;
    v16 = v29;
  }
  if ( v16 == -2147467263 )
  {
    if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 0x10) != 0 )
      WPP_SF_(v24[2], 17, WPP_e1654684cf453d0a1f37ee0675a51505_Traceguids);
    Src = 0;
    v16 = 0;
    goto LABEL_23;
  }
LABEL_22:
  if ( !v16 )
  {
LABEL_23:
    *v9 = Src;
    v24 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 0x10) != 0 )
    WPP_SF_d(v24[2], 18, WPP_e1654684cf453d0a1f37ee0675a51505_Traceguids, v16);
  return v16;
}

```

## disassembly

```asm
0x1800118b0  mov     r11, rsp
0x1800118b3  mov     [r11+18h], rbx
0x1800118b7  mov     [r11+10h], rdx
0x1800118bb  push    rbp
0x1800118bc  push    rsi
0x1800118bd  push    rdi
0x1800118be  push    r12
0x1800118c0  push    r13
0x1800118c2  push    r14
0x1800118c4  push    r15
0x1800118c6  sub     rsp, 50h
0x1800118ca  mov     r12, [rsp+88h+arg_40]
0x1800118d2  lea     r14, [rcx+8]
0x1800118d6  mov     ebp, r9d
0x1800118d9  mov     qword ptr [r11+8], 0
0x1800118e1  mov     r13, r8
0x1800118e4  lea     rbx, WPP_GLOBAL_Control
0x1800118eb  mov     rsi, rdx
0x1800118ee  mov     r15, rcx
0x1800118f1  mov     qword ptr [r12], 0
0x1800118f9  mov     rax, [rcx+20h]
0x1800118fd  test    rax, rax
0x180011900  jz      loc_180011A99
0x180011906  lea     rcx, [r11+8]
0x18001190a  mov     [r11-50h], rcx
0x18001190e  mov     ecx, [rsp+88h+arg_30]
0x180011915  mov     [rsp+88h+var_58], ecx
0x180011919  mov     rcx, [rsp+88h+arg_28]
0x180011921  mov     [r11-60h], rcx
0x180011925  mov     ecx, [rsp+88h+arg_20]
0x18001192c  mov     [rsp+88h+var_68], ecx
0x180011930  mov     rcx, r14
0x180011933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011938  mov     edi, eax
0x18001193a  test    eax, eax
0x18001193c  jnz     loc_180011A2F
0x180011942  cmp     [rsp+88h+Src], 0
0x18001194b  jz      loc_180011A42
0x180011951  mov     eax, ebp
0x180011953  sub     eax, 1
0x180011956  jz      short loc_180011974
0x180011958  sub     eax, 1
0x18001195b  jz      short loc_180011974
0x18001195d  sub     eax, 1Eh
0x180011960  jz      short loc_180011974
0x180011962  sub     eax, 1E0h
0x180011967  jz      short loc_180011974
0x180011969  cmp     eax, 200h
0x18001196e  jnz     loc_180011A42
0x180011974  mov     rax, [rsp+88h+Src]
0x18001197c  mov     ecx, [rax]
0x18001197e  dec     ecx
0x180011980  cmp     ecx, 67h ; 'g'
0x180011983  ja      short loc_1800119D1
0x180011985  mov     ecx, 68h ; 'h'; cb
0x18001198a  call    cs:__imp_CoTaskMemAlloc
0x180011990  mov     rsi, rax
0x180011993  test    rax, rax
0x180011996  jz      short loc_1800119AD
0x180011998  mov     rdx, [rsp+88h+Src]; Src
0x1800119a0  mov     rcx, rax; void *
0x1800119a3  mov     r8d, [rdx]; Size
0x1800119a6  call    memcpy_0
0x1800119ab  jmp     short loc_180011A03
0x1800119ad  mov     edi, 8007000Eh
0x1800119b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119b9  cmp     rcx, rbx
0x1800119bc  jz      short loc_180011A03
0x1800119be  test    byte ptr [rcx+1Ch], 4
0x1800119c2  jz      short loc_180011A03
0x1800119c4  mov     edx, 0Eh
0x1800119c9  mov     r9d, 8007000Eh
0x1800119cf  jmp     short loc_1800119F3
0x1800119d1  xor     esi, esi
0x1800119d3  mov     edi, 80004003h
0x1800119d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119df  cmp     rcx, rbx
0x1800119e2  jz      short loc_180011A03
0x1800119e4  test    byte ptr [rcx+1Ch], 8
0x1800119e8  jz      short loc_180011A03
0x1800119ea  lea     edx, [rsi+0Dh]
0x1800119ed  mov     r9d, 80004003h
0x1800119f3  mov     rcx, [rcx+10h]
0x1800119f7  lea     r8, WPP_e1654684cf453d0a1f37ee0675a51505_Traceguids
0x1800119fe  call    WPP_SF_d
0x180011a03  mov     rbx, [rsp+88h+Src]
0x180011a0b  call    cs:__imp_GetProcessHeap
0x180011a11  mov     r8, rbx; lpMem
0x180011a14  xor     edx, edx; dwFlags
0x180011a16  mov     rcx, rax; hHeap
0x180011a19  call    cs:__imp_HeapFree
0x180011a1f  mov     [rsp+88h+Src], rsi
0x180011a27  mov     rsi, [rsp+88h+arg_8]
0x180011a2f  cmp     edi, 80004001h
0x180011a35  jz      short loc_180011A99
0x180011a37  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a3e  test    edi, edi
0x180011a40  jnz     short loc_180011A55
0x180011a42  mov     rax, [rsp+88h+Src]
0x180011a4a  mov     [r12], rax
0x180011a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a55  lea     rax, WPP_GLOBAL_Control
0x180011a5c  cmp     rcx, rax
0x180011a5f  jz      short loc_180011A7F
0x180011a61  test    byte ptr [rcx+1Ch], 10h
0x180011a65  jz      short loc_180011A7F
0x180011a67  mov     rcx, [rcx+10h]
0x180011a6b  lea     r8, WPP_e1654684cf453d0a1f37ee0675a51505_Traceguids
0x180011a72  mov     edx, 12h
0x180011a77  mov     r9d, edi
0x180011a7a  call    WPP_SF_d
0x180011a7f  mov     rbx, [rsp+88h+arg_10]
0x180011a87  mov     eax, edi
0x180011a89  add     rsp, 50h
0x180011a8d  pop     r15
0x180011a8f  pop     r14
0x180011a91  pop     r13
0x180011a93  pop     r12
0x180011a95  pop     rdi
0x180011a96  pop     rsi
0x180011a97  pop     rbp
0x180011a98  retn
0x180011a99  lea     rbx, [r15+68h]
0x180011a9d  mov     rcx, [rbx]
0x180011aa0  test    rcx, rcx
0x180011aa3  jz      short loc_180011AB8
0x180011aa5  mov     rax, [rcx]
0x180011aa8  mov     rax, [rax+10h]
0x180011aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ab1  mov     qword ptr [rbx], 0
0x180011ab8  mov     r9, rbx
0x180011abb  lea     r8, IID_IXWizardPageEvent
0x180011ac2  mov     edx, ebp
0x180011ac4  mov     rcx, r14
0x180011ac7  call    ?HrCreateWrappedCOMComponent@@YAJPEBU_GUID@@W4tagXW_WIZARD_TYPE@@0PEAPEAX@Z; HrCreateWrappedCOMComponent(_GUID const *,tagXW_WIZARD_TYPE,_GUID const *,void * *)
0x180011acc  mov     edi, eax
0x180011ace  test    eax, eax
0x180011ad0  jns     short loc_180011B47
0x180011ad2  cmp     eax, 80004001h
0x180011ad7  jnz     short loc_180011B14
0x180011ad9  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ae0  lea     rbx, WPP_GLOBAL_Control
0x180011ae7  cmp     rcx, rbx
0x180011aea  jz      short loc_180011B55
0x180011aec  test    byte ptr [rcx+1Ch], 8
0x180011af0  jz      short loc_180011B55
0x180011af2  mov     r9d, [r14]
0x180011af5  lea     r8, WPP_e1654684cf453d0a1f37ee0675a51505_Traceguids
0x180011afc  mov     rcx, [rcx+10h]
0x180011b00  mov     edx, 0Fh
0x180011b05  mov     [rsp+88h+var_68], 80004001h
0x180011b0d  call    WPP_SF_DD
0x180011b12  jmp     short loc_180011B4E
0x180011b14  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b1b  lea     rbx, WPP_GLOBAL_Control
0x180011b22  cmp     rcx, rbx
0x180011b25  jz      short loc_180011B55
0x180011b27  test    byte ptr [rcx+1Ch], 4
0x180011b2b  jz      short loc_180011B55
0x180011b2d  mov     rcx, [rcx+10h]
0x180011b31  lea     r8, WPP_e1654684cf453d0a1f37ee0675a51505_Traceguids
0x180011b38  mov     edx, 10h
0x180011b3d  mov     r9d, eax
0x180011b40  call    WPP_SF_d
0x180011b45  jmp     short loc_180011B4E
0x180011b47  lea     rbx, WPP_GLOBAL_Control
0x180011b4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b55  mov     r10, [r15+68h]
0x180011b59  test    r10, r10
0x180011b5c  jz      short loc_180011BBC
0x180011b5e  mov     rdx, [rsp+88h+arg_38]
0x180011b66  lea     rcx, [rsp+88h+Src]
0x180011b6e  mov     rax, [r10]
0x180011b71  mov     r9d, ebp
0x180011b74  mov     [rsp+88h+var_48], rcx
0x180011b79  mov     r8, r13
0x180011b7c  mov     ecx, [rsp+88h+arg_30]
0x180011b83  mov     [rsp+88h+var_50], rdx
0x180011b88  mov     rdx, rsi
0x180011b8b  mov     rax, [rax+38h]
0x180011b8f  mov     [rsp+88h+var_58], ecx
0x180011b93  mov     rcx, [rsp+88h+arg_28]
0x180011b9b  mov     [rsp+88h+var_60], rcx
0x180011ba0  mov     ecx, [rsp+88h+arg_20]
0x180011ba7  mov     [rsp+88h+var_68], ecx
0x180011bab  mov     rcx, r10
0x180011bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bba  mov     edi, eax
0x180011bbc  cmp     edi, 80004001h
0x180011bc2  jnz     loc_180011A3E
0x180011bc8  cmp     rcx, rbx
0x180011bcb  jz      short loc_180011BE8
0x180011bcd  test    byte ptr [rcx+1Ch], 10h
0x180011bd1  jz      short loc_180011BE8
0x180011bd3  mov     rcx, [rcx+10h]
0x180011bd7  lea     r8, WPP_e1654684cf453d0a1f37ee0675a51505_Traceguids
0x180011bde  mov     edx, 11h
0x180011be3  call    WPP_SF_
0x180011be8  mov     [rsp+88h+Src], 0
0x180011bf4  xor     edi, edi
0x180011bf6  jmp     loc_180011A42
```
