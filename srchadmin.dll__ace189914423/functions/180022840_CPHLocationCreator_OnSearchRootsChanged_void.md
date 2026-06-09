# CPHLocationCreator::OnSearchRootsChanged(void)

- ea: `0x180022840`
- end: `0x180022a98`
- name: `?OnSearchRootsChanged@CPHLocationCreator@@SAXXZ`
- size: `600`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003900`

## callees

- `0x180003290`
- `0x180005cc0`
- `0x180021668`
- `0x18002169c`
- `0x1800218c4`
- `0x1800218fc`
- `0x18002192c`
- `0x180021cd0`
- `0x180021f84`
- `0x180022698`
- `0x180022840`
- `0x180022b78`
- `0x180022cc0`
- `0x1800240ec`
- `0x18002ff1c`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x18002298d`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002298d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022a13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022a13`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CPHLocationCreator::OnSearchRootsChanged(int a1, __int64 a2, int a3, int a4)
{
  int v4; // r14d
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  struct _DSA *v8; // rbx
  int v9; // r12d
  struct _DSA *v10; // rdi
  int v11; // r13d
  int v12; // esi
  int v13; // r15d
  int v14; // esi
  LPCWSTR *v15; // rax
  int v16; // eax
  int v17; // eax
  HDSA v18; // [rsp+30h] [rbp-59h] BYREF
  HDSA v19; // [rsp+38h] [rbp-51h] BYREF
  LPCWSTR *ItemPtr; // [rsp+40h] [rbp-49h]
  HDSA v21; // [rsp+48h] [rbp-41h] BYREF
  __int64 v22; // [rsp+50h] [rbp-39h] BYREF
  HDSA hdsa; // [rsp+58h] [rbp-31h] BYREF
  LPVOID pv[4]; // [rsp+60h] [rbp-29h] BYREF
  _QWORD v25[2]; // [rsp+80h] [rbp-9h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      a1,
      (unsigned int)PHLocationCreator_ScanSearchRoots_Start,
      a3,
      a4,
      (__int64)v25);
  v4 = 0;
  hdsa = 0;
  if ( (int)EnumSearchRoots(&hdsa) >= 0 )
  {
    v21 = 0;
    v22 = 0;
    if ( (int)EnumProcessedSearchRoots(&v21, &v22) >= 0 )
    {
      memset(pv, 0, sizeof(pv));
      if ( (int)GetUsedKeys(&v21, &v22, pv) >= 0 )
      {
        v8 = hdsa;
        if ( hdsa )
          v9 = *(_DWORD *)hdsa;
        else
          v9 = 0;
        v10 = v21;
        if ( v21 )
          v11 = *(_DWORD *)v21;
        else
          v11 = 0;
        v12 = v11 - v9;
        if ( v11 - v9 < 0 )
          v12 = v9 - v11;
        v19 = 0;
        v18 = 0;
        if ( (unsigned int)CDSA_Base<SEARCH_ROOT>::Create(&v19, (unsigned int)(v12 + 1))
          && (unsigned int)CDSA_Base<PROCESSED_SEARCH_ROOT>::Create(&v18, (unsigned int)(v12 + 1)) )
        {
          v13 = 0;
          v14 = 0;
          while ( 1 )
          {
            if ( v14 >= v9 && v4 >= v11 )
            {
LABEL_29:
              if ( v13 >= 0 )
              {
                ProcessRemovedSearchRoots(&v18);
                ProcessAddedSearchRoots(&v19, pv);
              }
              break;
            }
            ItemPtr = (LPCWSTR *)DSA_GetItemPtr(v8, v14);
            v15 = (LPCWSTR *)DSA_GetItemPtr(v10, v4);
            v25[0] = v15;
            if ( v4 != v11 )
            {
              if ( v14 == v9 )
                goto LABEL_40;
              v16 = StrCmpICW(ItemPtr[1], v15[1]);
              if ( v16 >= 0 )
              {
                if ( v16 > 0 )
                {
                  v15 = (LPCWSTR *)v25[0];
LABEL_40:
                  ++v4;
                  v17 = CAutoDSA<PROCESSED_SEARCH_ROOT>::AppendAndClearItem(&v18, v15);
                  goto LABEL_27;
                }
                if ( *(_DWORD *)ItemPtr == *(_DWORD *)v25[0] )
                {
                  ++v14;
                  ++v4;
                  goto LABEL_28;
                }
                if ( (int)CAutoDSA<PROCESSED_SEARCH_ROOT>::AppendAndClearItem(&v18, v25[0]) < 0 )
                  break;
                ++v4;
              }
            }
            ++v14;
            v17 = CAutoDSA<SEARCH_ROOT>::AppendAndClearItem(&v19, ItemPtr);
LABEL_27:
            v13 = v17;
LABEL_28:
            if ( v13 < 0 )
              goto LABEL_29;
          }
        }
        CAutoDSA<PROCESSED_SEARCH_ROOT>::~CAutoDSA<PROCESSED_SEARCH_ROOT>(&v18);
        CAutoDSA<SEARCH_ROOT>::~CAutoDSA<SEARCH_ROOT>(&v19);
      }
      if ( pv[0] )
        CoTaskMemFree(pv[0]);
    }
    CAutoDSA<PROCESSED_SEARCH_ROOT>::~CAutoDSA<PROCESSED_SEARCH_ROOT>(&v22);
    CAutoDSA<PROCESSED_SEARCH_ROOT>::~CAutoDSA<PROCESSED_SEARCH_ROOT>(&v21);
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v5,
      (unsigned int)PHLocationCreator_ScanSearchRoots_Stop,
      v6,
      v7,
      (__int64)v25);
  CAutoDSA<SEARCH_ROOT>::~CAutoDSA<SEARCH_ROOT>(&hdsa);
}

```

## disassembly

```asm
0x180022840  push    rbp
0x180022842  push    rbx
0x180022843  push    rsi
0x180022844  push    rdi
0x180022845  push    r12
0x180022847  push    r13
0x180022849  push    r14
0x18002284b  push    r15
0x18002284d  lea     rbp, [rsp-1Fh]
0x180022852  sub     rsp, 0A8h
0x180022859  mov     rax, cs:__security_cookie
0x180022860  xor     rax, rsp
0x180022863  mov     [rbp+57h+var_50], rax
0x180022867  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18002286e  jz      short loc_180022885
0x180022870  lea     rax, [rbp+57h+var_60]
0x180022874  mov     [rsp+0E0h+var_C0], rax
0x180022879  lea     rdx, PHLocationCreator_ScanSearchRoots_Start
0x180022880  call    McGenEventWrite_EtwEventWriteTransfer
0x180022885  xor     r14d, r14d
0x180022888  mov     [rbp+57h+hdsa], r14
0x18002288c  lea     rcx, [rbp+57h+hdsa]
0x180022890  call    ?EnumSearchRoots@@YAJPEAV?$CAutoDSA@USEARCH_ROOT@@@@@Z; EnumSearchRoots(CAutoDSA<SEARCH_ROOT> *)
0x180022895  test    eax, eax
0x180022897  js      loc_180022A2D
0x18002289d  mov     [rbp+57h+var_98], r14
0x1800228a1  mov     [rbp+57h+var_90], r14
0x1800228a5  lea     rdx, [rbp+57h+var_90]
0x1800228a9  lea     rcx, [rbp+57h+var_98]
0x1800228ad  call    ?EnumProcessedSearchRoots@@YAJPEAV?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@0@Z; EnumProcessedSearchRoots(CAutoDSA<PROCESSED_SEARCH_ROOT> *,CAutoDSA<PROCESSED_SEARCH_ROOT> *)
0x1800228b2  test    eax, eax
0x1800228b4  js      loc_180022A1A
0x1800228ba  mov     [rbp+57h+pv], r14
0x1800228be  mov     [rbp+57h+var_78], r14
0x1800228c2  mov     [rbp+57h+var_70], r14
0x1800228c6  mov     [rbp+57h+var_68], r14
0x1800228ca  lea     r8, [rbp+57h+pv]
0x1800228ce  lea     rdx, [rbp+57h+var_90]
0x1800228d2  lea     rcx, [rbp+57h+var_98]
0x1800228d6  call    ?GetUsedKeys@@YAJAEBV?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@0PEAV?$CCoSimpleArray@H$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@H@@@@@Z; GetUsedKeys(CAutoDSA<PROCESSED_SEARCH_ROOT> const &,CAutoDSA<PROCESSED_SEARCH_ROOT> const &,CCoSimpleArray<int,4294967294,CSimpleArrayStandardCompareHelper<int>> *)
0x1800228db  test    eax, eax
0x1800228dd  js      loc_180022A0A
0x1800228e3  mov     rbx, [rbp+57h+hdsa]
0x1800228e7  test    rbx, rbx
0x1800228ea  jz      short loc_1800228F1
0x1800228ec  mov     r12d, [rbx]
0x1800228ef  jmp     short loc_1800228F4
0x1800228f1  mov     r12d, r14d
0x1800228f4  mov     rdi, [rbp+57h+var_98]
0x1800228f8  test    rdi, rdi
0x1800228fb  jz      short loc_180022902
0x1800228fd  mov     r13d, [rdi]
0x180022900  jmp     short loc_180022905
0x180022902  mov     r13d, r14d
0x180022905  mov     ecx, r12d
0x180022908  sub     ecx, r13d
0x18002290b  mov     esi, ecx
0x18002290d  neg     esi
0x18002290f  cmovs   esi, ecx
0x180022912  mov     [rbp+57h+var_A8], r14
0x180022916  mov     [rbp+57h+var_B0], r14
0x18002291a  lea     edx, [rsi+1]
0x18002291d  lea     rcx, [rbp+57h+var_A8]
0x180022921  call    ?Create@?$CDSA_Base@USEARCH_ROOT@@@@QEAAHH@Z; CDSA_Base<SEARCH_ROOT>::Create(int)
0x180022926  test    eax, eax
0x180022928  jz      loc_1800229F6
0x18002292e  lea     edx, [rsi+1]
0x180022931  lea     rcx, [rbp+57h+var_B0]
0x180022935  call    ?Create@?$CDSA_Base@UPROCESSED_SEARCH_ROOT@@@@QEAAHH@Z; CDSA_Base<PROCESSED_SEARCH_ROOT>::Create(int)
0x18002293a  test    eax, eax
0x18002293c  jz      loc_1800229F6
0x180022942  mov     r15d, r14d
0x180022945  mov     esi, r14d
0x180022948  cmp     esi, r12d
0x18002294b  jl      short loc_180022956
0x18002294d  cmp     r14d, r13d
0x180022950  jge     loc_1800229DA
0x180022956  mov     edx, esi; i
0x180022958  mov     rcx, rbx; hdsa
0x18002295b  call    DSA_GetItemPtr
0x180022960  mov     [rbp+57h+var_A0], rax
0x180022964  mov     edx, r14d; i
0x180022967  mov     rcx, rdi; hdsa
0x18002296a  call    DSA_GetItemPtr
0x18002296f  mov     [rbp+57h+var_60], rax
0x180022973  cmp     r14d, r13d
0x180022976  jz      short loc_1800229BF
0x180022978  cmp     esi, r12d
0x18002297b  jz      loc_180022A83
0x180022981  mov     rdx, [rax+8]; pszStr2
0x180022985  mov     rax, [rbp+57h+var_A0]
0x180022989  mov     rcx, [rax+8]; pszStr1
0x18002298d  call    cs:__imp_StrCmpICW
0x180022993  test    eax, eax
0x180022995  js      short loc_1800229BF
0x180022997  jg      loc_180022A7F
0x18002299d  mov     rdx, [rbp+57h+var_60]
0x1800229a1  mov     eax, [rdx]
0x1800229a3  mov     rcx, [rbp+57h+var_A0]
0x1800229a7  cmp     [rcx], eax
0x1800229a9  jz      loc_180022A75
0x1800229af  lea     rcx, [rbp+57h+var_B0]
0x1800229b3  call    ?AppendAndClearItem@?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@QEAAJPEAUPROCESSED_SEARCH_ROOT@@@Z; CAutoDSA<PROCESSED_SEARCH_ROOT>::AppendAndClearItem(PROCESSED_SEARCH_ROOT *)
0x1800229b8  test    eax, eax
0x1800229ba  js      short loc_1800229F6
0x1800229bc  inc     r14d
0x1800229bf  inc     esi
0x1800229c1  mov     rdx, [rbp+57h+var_A0]
0x1800229c5  lea     rcx, [rbp+57h+var_A8]
0x1800229c9  call    ?AppendAndClearItem@?$CAutoDSA@USEARCH_ROOT@@@@QEAAJPEAUSEARCH_ROOT@@@Z; CAutoDSA<SEARCH_ROOT>::AppendAndClearItem(SEARCH_ROOT *)
0x1800229ce  mov     r15d, eax
0x1800229d1  test    r15d, r15d
0x1800229d4  jns     loc_180022948
0x1800229da  test    r15d, r15d
0x1800229dd  js      short loc_1800229F6
0x1800229df  lea     rcx, [rbp+57h+var_B0]
0x1800229e3  call    ?ProcessRemovedSearchRoots@@YAXPEAV?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@@Z; ProcessRemovedSearchRoots(CAutoDSA<PROCESSED_SEARCH_ROOT> *)
0x1800229e8  lea     rdx, [rbp+57h+pv]
0x1800229ec  lea     rcx, [rbp+57h+var_A8]
0x1800229f0  call    ?ProcessAddedSearchRoots@@YAXPEAV?$CAutoDSA@USEARCH_ROOT@@@@AEBV?$CCoSimpleArray@H$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@H@@@@@Z; ProcessAddedSearchRoots(CAutoDSA<SEARCH_ROOT> *,CCoSimpleArray<int,4294967294,CSimpleArrayStandardCompareHelper<int>> const &)
0x1800229f5  nop
0x1800229f6  lea     rcx, [rbp+57h+var_B0]
0x1800229fa  call    ??1?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@QEAA@XZ; CAutoDSA<PROCESSED_SEARCH_ROOT>::~CAutoDSA<PROCESSED_SEARCH_ROOT>(void)
0x1800229ff  nop
0x180022a00  lea     rcx, [rbp+57h+var_A8]
0x180022a04  call    ??1?$CAutoDSA@USEARCH_ROOT@@@@QEAA@XZ; CAutoDSA<SEARCH_ROOT>::~CAutoDSA<SEARCH_ROOT>(void)
0x180022a09  nop
0x180022a0a  mov     rcx, [rbp+57h+pv]; pv
0x180022a0e  test    rcx, rcx
0x180022a11  jz      short loc_180022A1A
0x180022a13  call    cs:__imp_CoTaskMemFree
0x180022a19  nop
0x180022a1a  lea     rcx, [rbp+57h+var_90]
0x180022a1e  call    ??1?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@QEAA@XZ; CAutoDSA<PROCESSED_SEARCH_ROOT>::~CAutoDSA<PROCESSED_SEARCH_ROOT>(void)
0x180022a23  nop
0x180022a24  lea     rcx, [rbp+57h+var_98]
0x180022a28  call    ??1?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@QEAA@XZ; CAutoDSA<PROCESSED_SEARCH_ROOT>::~CAutoDSA<PROCESSED_SEARCH_ROOT>(void)
0x180022a2d  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180022a34  jz      short loc_180022A4C
0x180022a36  lea     rax, [rbp+57h+var_60]
0x180022a3a  mov     [rsp+0E0h+var_C0], rax
0x180022a3f  lea     rdx, PHLocationCreator_ScanSearchRoots_Stop
0x180022a46  call    McGenEventWrite_EtwEventWriteTransfer
0x180022a4b  nop
0x180022a4c  lea     rcx, [rbp+57h+hdsa]
0x180022a50  call    ??1?$CAutoDSA@USEARCH_ROOT@@@@QEAA@XZ; CAutoDSA<SEARCH_ROOT>::~CAutoDSA<SEARCH_ROOT>(void)
0x180022a55  mov     rcx, [rbp+57h+var_50]
0x180022a59  xor     rcx, rsp; StackCookie
0x180022a5c  call    __security_check_cookie
0x180022a61  add     rsp, 0A8h
0x180022a68  pop     r15
0x180022a6a  pop     r14
0x180022a6c  pop     r13
0x180022a6e  pop     r12
0x180022a70  pop     rdi
0x180022a71  pop     rsi
0x180022a72  pop     rbx
0x180022a73  pop     rbp
0x180022a74  retn
0x180022a75  inc     esi
0x180022a77  inc     r14d
0x180022a7a  jmp     loc_1800229D1
0x180022a7f  mov     rax, [rbp+57h+var_60]
0x180022a83  inc     r14d
0x180022a86  mov     rdx, rax
0x180022a89  lea     rcx, [rbp+57h+var_B0]
0x180022a8d  call    ?AppendAndClearItem@?$CAutoDSA@UPROCESSED_SEARCH_ROOT@@@@QEAAJPEAUPROCESSED_SEARCH_ROOT@@@Z; CAutoDSA<PROCESSED_SEARCH_ROOT>::AppendAndClearItem(PROCESSED_SEARCH_ROOT *)
0x180022a92  jmp     loc_1800229CE
```
