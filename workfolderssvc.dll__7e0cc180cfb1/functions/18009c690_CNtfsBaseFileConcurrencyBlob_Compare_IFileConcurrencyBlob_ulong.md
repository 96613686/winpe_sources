# CNtfsBaseFileConcurrencyBlob::Compare(IFileConcurrencyBlob *,ulong *)

- ea: `0x18009c690`
- end: `0x18009c936`
- name: `?Compare@CNtfsBaseFileConcurrencyBlob@@UEBAJPEAUIFileConcurrencyBlob@@PEAK@Z`
- size: `678`
- prototype: `__int64 __fastcall(CNtfsBaseFileConcurrencyBlob *__hidden this, struct IFileConcurrencyBlob *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180007e10`
- `0x180009188`
- `0x180011314`
- `0x18001133c`
- `0x18009c690`
- `0x18009d860`
- `0x18013e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009c857`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009c857`
- `KERNEL32!CompareFileTime` at `0x18009c80a`
- `KERNEL32!CompareFileTime` at `0x18009c823`
- `KERNEL32!CompareFileTime` at `0x18009c80a`
- `KERNEL32!CompareFileTime` at `0x18009c823`

## string_xrefs

- `0x18009c707`: `CNtfsBaseFileConcurrencyBlob::Compare`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNtfsBaseFileConcurrencyBlob::Compare(
        CNtfsBaseFileConcurrencyBlob *this,
        struct IFileConcurrencyBlob *a2,
        unsigned int *a3)
{
  _BYTE *v6; // rax
  char v7; // cl
  __int16 v8; // ax
  int v9; // ebx
  __int64 v10; // rax
  int v11; // ecx
  __int64 v12; // rax
  int v13; // ebx
  int v14; // edi
  int v15; // ebx
  __int64 v16; // rax
  int v17; // edi
  unsigned int v18; // ebx
  PVOID *v19; // rcx
  int v21; // [rsp+20h] [rbp-28h] BYREF
  int v22; // [rsp+24h] [rbp-24h]
  char v23; // [rsp+28h] [rbp-20h]
  const char *v24; // [rsp+30h] [rbp-18h]
  __int64 v25; // [rsp+38h] [rbp-10h]
  __int64 v26; // [rsp+88h] [rbp+40h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, &WPP_890c008de0e73a0ab1c1dee316928dd8_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( (v6[68] & 0x20) != 0 && v6[65] >= 6u )
  {
    v7 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v7 = 0;
LABEL_9:
  v21 = 0;
  v22 = 559;
  v23 = v7;
  v24 = "CNtfsBaseFileConcurrencyBlob::Compare";
  v25 = 0;
  v26 = 0;
  if ( a3 )
    *a3 = 0;
  v8 = 566;
  if ( !a2 || (LOWORD(v22) = 566, v8 = 567, !a3) )
  {
    v9 = -2147024809;
    v21 = -2147024809;
LABEL_13:
    HIWORD(v22) = v8;
    goto LABEL_54;
  }
  v21 = 0;
  LOWORD(v22) = 567;
  v9 = (**(__int64 (__fastcall ***)(struct IFileConcurrencyBlob *, GUID *, __int64 *))a2)(
         a2,
         &GUID_688bc2e4_fd96_40fe_b902_1f3c0b9395f6,
         &v26);
  v21 = v9;
  v8 = 571;
  if ( v9 < 0 )
    goto LABEL_13;
  LOWORD(v22) = 571;
  CNtfsBaseFileConcurrencyBlob::TraceBlob(this, L"This Blob");
  CNtfsBaseFileConcurrencyBlob::TraceBlob(a2, L"Other Blob");
  v10 = *((_QWORD *)this + 4);
  if ( v10 && *((_QWORD *)a2 + 4) )
  {
    v11 = v10 != *((_QWORD *)a2 + 4);
  }
  else
  {
    v11 = 0;
    if ( *((_QWORD *)this + 3) != *((_QWORD *)a2 + 3) )
      v11 = 2;
  }
  v12 = *((_QWORD *)this + 1) - *((_QWORD *)a2 + 1);
  if ( !v12 )
    v12 = *((_QWORD *)this + 2) - *((_QWORD *)a2 + 2);
  if ( v12 )
    v11 |= 4u;
  v13 = v11 | 0x10000;
  if ( ((*((_BYTE *)this + 64) ^ *((_BYTE *)a2 + 64)) & 0x17) == 0 )
    v13 = v11;
  v14 = v13 | 0x80000;
  if ( !CompareFileTime((const FILETIME *)this + 5, (const FILETIME *)a2 + 5) )
    v14 = v13;
  v15 = v14 | 0x40000;
  if ( !CompareFileTime((const FILETIME *)this + 6, (const FILETIME *)a2 + 6) )
    v15 = v14;
  v16 = *(_QWORD *)((char *)this + 68) - *(_QWORD *)((char *)a2 + 68);
  if ( !v16 )
    v16 = *(_QWORD *)((char *)this + 76) - *(_QWORD *)((char *)a2 + 76);
  if ( v16 )
    v15 |= 0x100000u;
  v17 = v15 | 0x200000;
  if ( !(unsigned int)_o__wcsicmp((char *)this + 84, (char *)a2 + 84) )
    v17 = v15;
  if ( (*((_BYTE *)this + 64) & 0x10) != 0 )
  {
    if ( (v17 & 0xFFFF0004) == 0x40000 )
    {
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, &WPP_890c008de0e73a0ab1c1dee316928dd8_Traceguids);
        v19 = (PVOID *)WPP_GLOBAL_Control;
      }
      v18 = v17 & 0xFFFBFFEF | 0x10;
      goto LABEL_49;
    }
    v18 = v17;
  }
  else
  {
    v18 = v17 | 0x20000;
    if ( *((_QWORD *)this + 7) == *((_QWORD *)a2 + 7) )
      v18 = v17;
  }
  v19 = (PVOID *)WPP_GLOBAL_Control;
LABEL_49:
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 68) & 0x20) != 0 && *((_BYTE *)v19 + 65) >= 4u )
    WPP_SF_d(v19[7], 21, &WPP_890c008de0e73a0ab1c1dee316928dd8_Traceguids);
  *a3 = v18;
  v9 = v21;
LABEL_54:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v21);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18009c690  push    rbp
0x18009c692  push    rbx
0x18009c693  push    rsi
0x18009c694  push    rdi
0x18009c695  push    r14
0x18009c697  push    r15
0x18009c699  mov     rbp, rsp
0x18009c69c  sub     rsp, 48h
0x18009c6a0  mov     r15, r8
0x18009c6a3  mov     rsi, rdx
0x18009c6a6  mov     r14, rcx
0x18009c6a9  lea     rcx, WPP_GLOBAL_Control
0x18009c6b0  mov     rax, cs:WPP_GLOBAL_Control
0x18009c6b7  cmp     rax, rcx
0x18009c6ba  jz      short loc_18009C6E4
0x18009c6bc  test    byte ptr [rax+44h], 20h
0x18009c6c0  jz      short loc_18009C6F4
0x18009c6c2  cmp     byte ptr [rax+41h], 6
0x18009c6c6  jb      short loc_18009C6E4
0x18009c6c8  mov     edx, 13h
0x18009c6cd  lea     r8, WPP_890c008de0e73a0ab1c1dee316928dd8_Traceguids
0x18009c6d4  mov     rcx, [rax+38h]
0x18009c6d8  call    WPP_SF_
0x18009c6dd  mov     rax, cs:WPP_GLOBAL_Control
0x18009c6e4  test    byte ptr [rax+44h], 20h
0x18009c6e8  jz      short loc_18009C6F4
0x18009c6ea  cmp     byte ptr [rax+41h], 6
0x18009c6ee  jb      short loc_18009C6F4
0x18009c6f0  mov     cl, 1
0x18009c6f2  jmp     short loc_18009C6F6
0x18009c6f4  xor     cl, cl
0x18009c6f6  mov     [rbp+var_28], 0
0x18009c6fd  mov     [rbp+var_24], 22Fh
0x18009c704  mov     [rbp+var_20], cl
0x18009c707  lea     rax, aCntfsbasefilec_1; "CNtfsBaseFileConcurrencyBlob::Compare"
0x18009c70e  mov     [rbp+var_18], rax
0x18009c712  mov     [rbp+var_10], 0
0x18009c71a  mov     [rbp+arg_8], 0
0x18009c722  test    r15, r15
0x18009c725  jz      short loc_18009C72E
0x18009c727  mov     dword ptr [r15], 0
0x18009c72e  mov     eax, 236h
0x18009c733  test    rsi, rsi
0x18009c736  jnz     short loc_18009C749
0x18009c738  mov     ebx, 80070057h
0x18009c73d  mov     [rbp+var_28], ebx
0x18009c740  mov     word ptr [rbp+var_24+2], ax
0x18009c744  jmp     loc_18009C915
0x18009c749  mov     word ptr [rbp+var_24], ax
0x18009c74d  mov     eax, 237h
0x18009c752  test    r15, r15
0x18009c755  jz      short loc_18009C738
0x18009c757  mov     [rbp+var_28], 0
0x18009c75e  mov     word ptr [rbp+var_24], ax
0x18009c762  mov     rax, [rsi]
0x18009c765  lea     r8, [rbp+arg_8]
0x18009c769  lea     rdx, _GUID_688bc2e4_fd96_40fe_b902_1f3c0b9395f6
0x18009c770  mov     rcx, rsi
0x18009c773  mov     rax, [rax]
0x18009c776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c77b  mov     ebx, eax
0x18009c77d  mov     [rbp+var_28], eax
0x18009c780  test    eax, eax
0x18009c782  mov     eax, 23Bh
0x18009c787  js      short loc_18009C740
0x18009c789  mov     word ptr [rbp+var_24], ax
0x18009c78d  lea     rdx, aThisBlob; "This Blob"
0x18009c794  mov     rcx, r14; struct CNtfsBaseFileConcurrencyBlob *
0x18009c797  call    ?TraceBlob@CNtfsBaseFileConcurrencyBlob@@CAXPEBV1@PEBG@Z; CNtfsBaseFileConcurrencyBlob::TraceBlob(CNtfsBaseFileConcurrencyBlob const *,ushort const *)
0x18009c79c  lea     rdx, aOtherBlob; "Other Blob"
0x18009c7a3  mov     rcx, rsi; struct CNtfsBaseFileConcurrencyBlob *
0x18009c7a6  call    ?TraceBlob@CNtfsBaseFileConcurrencyBlob@@CAXPEBV1@PEBG@Z; CNtfsBaseFileConcurrencyBlob::TraceBlob(CNtfsBaseFileConcurrencyBlob const *,ushort const *)
0x18009c7ab  mov     rax, [r14+20h]
0x18009c7af  test    rax, rax
0x18009c7b2  jz      short loc_18009C7C6
0x18009c7b4  cmp     qword ptr [rsi+20h], 0
0x18009c7b9  jz      short loc_18009C7C6
0x18009c7bb  xor     ecx, ecx
0x18009c7bd  cmp     rax, [rsi+20h]
0x18009c7c1  setnz   cl
0x18009c7c4  jmp     short loc_18009C7D6
0x18009c7c6  xor     ecx, ecx
0x18009c7c8  mov     rax, [r14+18h]
0x18009c7cc  cmp     rax, [rsi+18h]
0x18009c7d0  lea     edx, [rcx+2]
0x18009c7d3  cmovnz  ecx, edx
0x18009c7d6  mov     rax, [r14+8]
0x18009c7da  sub     rax, [rsi+8]
0x18009c7de  jnz     short loc_18009C7E8
0x18009c7e0  mov     rax, [r14+10h]
0x18009c7e4  sub     rax, [rsi+10h]
0x18009c7e8  test    rax, rax
0x18009c7eb  jz      short loc_18009C7F0
0x18009c7ed  or      ecx, 4
0x18009c7f0  mov     eax, [rsi+40h]
0x18009c7f3  xor     eax, [r14+40h]
0x18009c7f7  mov     ebx, ecx
0x18009c7f9  bts     ebx, 10h
0x18009c7fd  test    al, 17h
0x18009c7ff  cmovz   ebx, ecx
0x18009c802  lea     rdx, [rsi+28h]; lpFileTime2
0x18009c806  lea     rcx, [r14+28h]; lpFileTime1
0x18009c80a  call    cs:__imp_CompareFileTime
0x18009c810  mov     edi, ebx
0x18009c812  bts     edi, 13h
0x18009c816  test    eax, eax
0x18009c818  cmovz   edi, ebx
0x18009c81b  lea     rdx, [rsi+30h]; lpFileTime2
0x18009c81f  lea     rcx, [r14+30h]; lpFileTime1
0x18009c823  call    cs:__imp_CompareFileTime
0x18009c829  mov     ebx, edi
0x18009c82b  bts     ebx, 12h
0x18009c82f  test    eax, eax
0x18009c831  cmovz   ebx, edi
0x18009c834  mov     rax, [r14+44h]
0x18009c838  sub     rax, [rsi+44h]
0x18009c83c  jnz     short loc_18009C846
0x18009c83e  mov     rax, [r14+4Ch]
0x18009c842  sub     rax, [rsi+4Ch]
0x18009c846  test    rax, rax
0x18009c849  jz      short loc_18009C84F
0x18009c84b  bts     ebx, 14h
0x18009c84f  lea     rdx, [rsi+54h]
0x18009c853  lea     rcx, [r14+54h]
0x18009c857  call    cs:__imp__o__wcsicmp
0x18009c85d  mov     edi, ebx
0x18009c85f  bts     edi, 15h
0x18009c863  test    eax, eax
0x18009c865  cmovz   edi, ebx
0x18009c868  test    byte ptr [r14+40h], 10h
0x18009c86d  jnz     short loc_18009C882
0x18009c86f  mov     rax, [r14+38h]
0x18009c873  mov     ebx, edi
0x18009c875  bts     ebx, 11h
0x18009c879  cmp     rax, [rsi+38h]
0x18009c87d  cmovz   ebx, edi
0x18009c880  jmp     short loc_18009C8D8
0x18009c882  mov     eax, edi
0x18009c884  and     eax, 0FFFF0004h
0x18009c889  cmp     eax, 40000h
0x18009c88e  jnz     short loc_18009C8D6
0x18009c890  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c897  lea     rsi, WPP_GLOBAL_Control
0x18009c89e  cmp     rcx, rsi
0x18009c8a1  jz      short loc_18009C8CB
0x18009c8a3  test    byte ptr [rcx+44h], 20h
0x18009c8a7  jz      short loc_18009C8CB
0x18009c8a9  cmp     byte ptr [rcx+41h], 4
0x18009c8ad  jb      short loc_18009C8CB
0x18009c8af  mov     edx, 14h
0x18009c8b4  lea     r8, WPP_890c008de0e73a0ab1c1dee316928dd8_Traceguids
0x18009c8bb  mov     rcx, [rcx+38h]
0x18009c8bf  call    WPP_SF_
0x18009c8c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c8cb  mov     ebx, edi
0x18009c8cd  btr     ebx, 12h
0x18009c8d1  or      ebx, 10h
0x18009c8d4  jmp     short loc_18009C8E6
0x18009c8d6  mov     ebx, edi
0x18009c8d8  lea     rsi, WPP_GLOBAL_Control
0x18009c8df  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c8e6  cmp     rcx, rsi
0x18009c8e9  jz      short loc_18009C90F
0x18009c8eb  test    byte ptr [rcx+44h], 20h
0x18009c8ef  jz      short loc_18009C90F
0x18009c8f1  cmp     byte ptr [rcx+41h], 4
0x18009c8f5  jb      short loc_18009C90F
0x18009c8f7  mov     edx, 15h
0x18009c8fc  mov     r9d, ebx
0x18009c8ff  lea     r8, WPP_890c008de0e73a0ab1c1dee316928dd8_Traceguids
0x18009c906  mov     rcx, [rcx+38h]
0x18009c90a  call    WPP_SF_d
0x18009c90f  mov     [r15], ebx
0x18009c912  mov     ebx, [rbp+var_28]
0x18009c915  lea     rcx, [rbp+arg_8]
0x18009c919  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009c91e  lea     rcx, [rbp+var_28]; this
0x18009c922  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18009c927  mov     eax, ebx
0x18009c929  add     rsp, 48h
0x18009c92d  pop     r15
0x18009c92f  pop     r14
0x18009c931  pop     rdi
0x18009c932  pop     rsi
0x18009c933  pop     rbx
0x18009c934  pop     rbp
0x18009c935  retn
```
