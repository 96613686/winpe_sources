# CDlpStateXml::Initialize(ushort const *,int)

- ea: `0x180064744`
- end: `0x180064adf`
- name: `?Initialize@CDlpStateXml@@QEAAJPEBGH@Z`
- size: `923`
- prototype: `__int64 __fastcall(CDlpStateXml *__hidden this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180063bb0`
- `0x180076190`

## callees

- `0x180002898`
- `0x18000aba4`
- `0x18000b9a8`
- `0x18000ea20`
- `0x18001fd60`
- `0x18004cd4c`
- `0x180064744`
- `0x18007ec9a`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064945`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064973`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800649a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064a62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064a84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064aa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064945`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064973`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800649a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064a62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064a84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064aa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064954`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064982`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800649b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064a71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064a93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064ab5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064954`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064982`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800649b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064a71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064a93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064ab5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800649d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064a0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064a42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064a56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800649d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064a0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064a42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064a56`
- `UNATTEND!UnattendCtxDeserializeFile` at `0x180064898`
- `UNATTEND!UnattendCtxDeserializeFile` at `0x1800648c2`
- `UNATTEND!UnattendCtxDeserializeFile` at `0x180064898`
- `UNATTEND!UnattendCtxDeserializeFile` at `0x1800648c2`

## string_xrefs

- `0x1800647eb`: `windlp.state-old.xml`
- `0x1800647c2`: `windlp.state.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDlpStateXml::Initialize(CDlpStateXml *this, const unsigned __int16 *a2, int a3)
{
  __int64 v5; // r13
  const WCHAR *v6; // rsi
  const WCHAR *v7; // r14
  __int64 v8; // rbx
  unsigned int v9; // edi
  __int64 v10; // rcx
  __int64 v11; // r15
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  int StringCch; // eax
  int Internal; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // r12
  __int64 v21; // rbx
  HANDLE ProcessHeap; // rax
  const WCHAR *v23; // r12
  __int64 v24; // rbx
  HANDLE v25; // rax
  const WCHAR *v26; // r12
  __int64 v27; // rbx
  HANDLE v28; // rax
  __int64 v29; // r12
  char *v30; // rcx
  __int64 v31; // r12
  char *v32; // rcx
  HANDLE v33; // rax
  HANDLE v34; // rax
  HANDLE v35; // rax
  LPCWSTR lpFileName; // [rsp+20h] [rbp-49h] BYREF
  LPCWSTR v38; // [rsp+28h] [rbp-41h] BYREF
  __int64 v39; // [rsp+30h] [rbp-39h] BYREF
  __int64 v40; // [rsp+38h] [rbp-31h]
  __int64 v41; // [rsp+40h] [rbp-29h] BYREF
  _DWORD v42[28]; // [rsp+50h] [rbp-19h] BYREF
  int v43; // [rsp+D8h] [rbp+6Fh] BYREF
  int v44; // [rsp+E0h] [rbp+77h]
  HANDLE hObject; // [rsp+E8h] [rbp+7Fh]

  v44 = a3;
  v5 = 0;
  v40 = 0;
  v6 = 0;
  lpFileName = 0;
  v7 = 0;
  v38 = 0;
  v8 = -1;
  v39 = -1;
  hObject = (HANDLE)-1LL;
  v41 = -1;
  memset_0(v42, 0, 0x40u);
  if ( !a2 )
  {
    v9 = -2147024809;
    goto LABEL_3;
  }
  v12 = CMiscHelpersT<CEmptyType>::CombinePath(a2, L"windlp.state.xml", 0, &lpFileName);
  v9 = v12;
  if ( v12 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v12);
    v6 = lpFileName;
    goto LABEL_5;
  }
  v13 = CMiscHelpersT<CEmptyType>::CombinePath(a2, L"windlp.state-old.xml", 0, &v38);
  v9 = v13;
  if ( v13 < 0 )
  {
    v14 = (unsigned int)v13;
LABEL_10:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v14);
    v6 = lpFileName;
    v7 = v38;
    goto LABEL_5;
  }
  v43 = 0;
  StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(L"WINDLP", &v43);
  v9 = StringCch;
  if ( StringCch >= 0 )
  {
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(L"WINDLP");
    v9 = Internal;
    if ( Internal < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
    v5 = v40;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( (v9 & 0x80000000) != 0 )
  {
    v14 = v9;
    goto LABEL_10;
  }
  v6 = lpFileName;
  v7 = v38;
  if ( v44 )
  {
    memset_0(v42, 0, 0x40u);
    if ( (int)UnattendCtxDeserializeFile((char *)this + 136, v6, v42) < 0 || v42[0] < 0 )
    {
      memset_0(v42, 0, 0x40u);
      v17 = UnattendCtxDeserializeFile((char *)this + 136, v7, v42);
      v9 = v17;
      if ( v17 < 0 )
      {
        v10 = (unsigned int)v17;
        goto LABEL_4;
      }
      v9 = v42[0];
      if ( v42[0] < 0 )
      {
LABEL_3:
        v10 = v9;
LABEL_4:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
LABEL_5:
        v11 = (__int64)hObject;
        goto LABEL_43;
      }
    }
  }
  v18 = CDlpHelpersT<CEmptyType>::CreateFileWithAcl(v6, &v39);
  v9 = v18;
  if ( v18 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v18);
    v8 = v39;
    goto LABEL_5;
  }
  v19 = CDlpHelpersT<CEmptyType>::CreateFileWithAcl(v7, &v41);
  v9 = v19;
  if ( v19 >= 0 )
  {
    *((_QWORD *)this + 16) = (char *)this + 136;
    v20 = v5;
    v5 = 0;
    v21 = *((_QWORD *)this + 12);
    if ( v21 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)(v21 - 4));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    *((_QWORD *)this + 12) = v20;
    v23 = v6;
    v6 = 0;
    v24 = *((_QWORD *)this + 10);
    if ( v24 )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, (LPVOID)(v24 - 4));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    *((_QWORD *)this + 10) = v23;
    v26 = v7;
    v7 = 0;
    v27 = *((_QWORD *)this + 11);
    if ( v27 )
    {
      v28 = GetProcessHeap();
      HeapFree(v28, 0, (LPVOID)(v27 - 4));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    *((_QWORD *)this + 11) = v26;
    v29 = v39;
    v8 = -1;
    v30 = (char *)*((_QWORD *)this + 13);
    if ( (unsigned __int64)(v30 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v30);
    if ( ((v29 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      v29 = -1;
    *((_QWORD *)this + 13) = v29;
    v31 = v41;
    v32 = (char *)*((_QWORD *)this + 14);
    if ( (unsigned __int64)(v32 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v32);
    if ( ((v31 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      v31 = -1;
    *((_QWORD *)this + 14) = v31;
    v11 = -1;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v19);
    v8 = v39;
    v11 = v41;
  }
LABEL_43:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v11);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v8);
  if ( v7 )
  {
    v33 = GetProcessHeap();
    HeapFree(v33, 0, (LPVOID)(v7 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v6 )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, (LPVOID)(v6 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v5 )
  {
    v35 = GetProcessHeap();
    HeapFree(v35, 0, (LPVOID)(v5 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v9;
}

```

## disassembly

```asm
0x180064744  mov     [rsp-8+arg_0], rbx
0x180064749  mov     [rsp-8+arg_10], r8d
0x18006474e  push    rbp
0x18006474f  push    rsi
0x180064750  push    rdi
0x180064751  push    r12
0x180064753  push    r13
0x180064755  push    r14
0x180064757  push    r15
0x180064759  lea     rbp, [rsp-27h]
0x18006475e  sub     rsp, 90h
0x180064765  mov     r12, rdx
0x180064768  mov     r15, rcx
0x18006476b  xor     r13d, r13d
0x18006476e  mov     [rbp+57h+var_88], r13
0x180064772  xor     esi, esi
0x180064774  mov     [rbp+57h+lpFileName], rsi
0x180064778  xor     r14d, r14d
0x18006477b  mov     [rbp+57h+var_98], r14
0x18006477f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180064783  mov     rbx, rax
0x180064786  mov     [rbp+57h+var_90], rax
0x18006478a  mov     [rbp+57h+hObject], rax
0x18006478e  mov     [rbp+57h+var_80], rax
0x180064792  xor     edx, edx; Val
0x180064794  lea     r8d, [r13+40h]; Size
0x180064798  lea     rcx, [rbp+57h+var_70]; void *
0x18006479c  call    memset_0
0x1800647a1  test    r12, r12
0x1800647a4  jnz     short loc_1800647BB
0x1800647a6  mov     edi, 80070057h
0x1800647ab  mov     ecx, edi
0x1800647ad  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800647b2  mov     r15, [rbp+57h+hObject]
0x1800647b6  jmp     loc_180064A2D
0x1800647bb  lea     r9, [rbp+57h+lpFileName]
0x1800647bf  xor     r8d, r8d
0x1800647c2  lea     rdx, aWindlpStateXml; "windlp.state.xml"
0x1800647c9  mov     rcx, r12
0x1800647cc  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800647d1  mov     edi, eax
0x1800647d3  test    eax, eax
0x1800647d5  jns     short loc_1800647E4
0x1800647d7  mov     ecx, eax
0x1800647d9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800647de  mov     rsi, [rbp+57h+lpFileName]
0x1800647e2  jmp     short loc_1800647B2
0x1800647e4  lea     r9, [rbp+57h+var_98]
0x1800647e8  xor     r8d, r8d
0x1800647eb  lea     rdx, aWindlpStateOld; "windlp.state-old.xml"
0x1800647f2  mov     rcx, r12
0x1800647f5  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800647fa  mov     edi, eax
0x1800647fc  test    eax, eax
0x1800647fe  jns     short loc_180064811
0x180064800  mov     ecx, eax
0x180064802  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180064807  mov     rsi, [rbp+57h+lpFileName]
0x18006480b  mov     r14, [rbp+57h+var_98]
0x18006480f  jmp     short loc_1800647B2
0x180064811  mov     [rbp+57h+arg_8], 0
0x180064818  lea     rdx, [rbp+57h+arg_8]
0x18006481c  lea     rcx, aWindlp; "WINDLP"
0x180064823  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180064828  mov     edi, eax
0x18006482a  test    eax, eax
0x18006482c  jns     short loc_180064837
0x18006482e  mov     ecx, eax
0x180064830  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180064835  jmp     short loc_18006485B
0x180064837  lea     r8, [rbp+57h+var_88]
0x18006483b  mov     edx, [rbp+57h+arg_8]
0x18006483e  lea     rcx, aWindlp; "WINDLP"
0x180064845  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18006484a  mov     edi, eax
0x18006484c  test    eax, eax
0x18006484e  jns     short loc_180064857
0x180064850  mov     ecx, eax
0x180064852  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180064857  mov     r13, [rbp+57h+var_88]
0x18006485b  mov     ecx, edi
0x18006485d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180064862  test    edi, edi
0x180064864  jns     short loc_18006486A
0x180064866  mov     ecx, edi
0x180064868  jmp     short loc_180064802
0x18006486a  mov     rsi, [rbp+57h+lpFileName]
0x18006486e  mov     r14, [rbp+57h+var_98]
0x180064872  cmp     [rbp+57h+arg_10], 0
0x180064876  jz      short loc_1800648E0
0x180064878  xor     edx, edx; Val
0x18006487a  lea     r8d, [rdx+40h]; Size
0x18006487e  lea     rcx, [rbp+57h+var_70]; void *
0x180064882  call    memset_0
0x180064887  lea     r12, [r15+88h]
0x18006488e  lea     r8, [rbp+57h+var_70]
0x180064892  mov     rdx, rsi
0x180064895  mov     rcx, r12
0x180064898  call    cs:__imp_UnattendCtxDeserializeFile
0x18006489e  test    eax, eax
0x1800648a0  js      short loc_1800648A9
0x1800648a2  mov     edi, [rbp+57h+var_70]
0x1800648a5  test    edi, edi
0x1800648a7  jns     short loc_1800648E0
0x1800648a9  xor     edx, edx; Val
0x1800648ab  lea     r8d, [rdx+40h]; Size
0x1800648af  lea     rcx, [rbp+57h+var_70]; void *
0x1800648b3  call    memset_0
0x1800648b8  lea     r8, [rbp+57h+var_70]
0x1800648bc  mov     rdx, r14
0x1800648bf  mov     rcx, r12
0x1800648c2  call    cs:__imp_UnattendCtxDeserializeFile
0x1800648c8  mov     edi, eax
0x1800648ca  test    eax, eax
0x1800648cc  jns     short loc_1800648D5
0x1800648ce  mov     ecx, eax
0x1800648d0  jmp     loc_1800647AD
0x1800648d5  mov     edi, [rbp+57h+var_70]
0x1800648d8  test    edi, edi
0x1800648da  js      loc_1800647AB
0x1800648e0  lea     rdx, [rbp+57h+var_90]
0x1800648e4  mov     rcx, rsi; lpFileName
0x1800648e7  call    ?CreateFileWithAcl@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAGPEAPEAX@Z; CDlpHelpersT<CEmptyType>::CreateFileWithAcl(ushort *,void * *)
0x1800648ec  mov     edi, eax
0x1800648ee  test    eax, eax
0x1800648f0  jns     short loc_180064902
0x1800648f2  mov     ecx, eax
0x1800648f4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800648f9  mov     rbx, [rbp+57h+var_90]
0x1800648fd  jmp     loc_1800647B2
0x180064902  lea     rdx, [rbp+57h+var_80]
0x180064906  mov     rcx, r14; lpFileName
0x180064909  call    ?CreateFileWithAcl@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAGPEAPEAX@Z; CDlpHelpersT<CEmptyType>::CreateFileWithAcl(ushort *,void * *)
0x18006490e  mov     edi, eax
0x180064910  test    eax, eax
0x180064912  jns     short loc_180064928
0x180064914  mov     ecx, eax
0x180064916  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18006491b  mov     rbx, [rbp+57h+var_90]
0x18006491f  mov     r15, [rbp+57h+var_80]
0x180064923  jmp     loc_180064A2D
0x180064928  lea     rax, [r15+88h]
0x18006492f  mov     [r15+80h], rax
0x180064936  mov     r12, r13
0x180064939  xor     r13d, r13d
0x18006493c  mov     rbx, [r15+60h]
0x180064940  test    rbx, rbx
0x180064943  jz      short loc_180064961
0x180064945  call    cs:__imp_GetProcessHeap
0x18006494b  mov     rcx, rax; hHeap
0x18006494e  lea     r8, [rbx-4]; lpMem
0x180064952  xor     edx, edx; dwFlags
0x180064954  call    cs:__imp_HeapFree
0x18006495a  xor     ecx, ecx
0x18006495c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180064961  mov     [r15+60h], r12
0x180064965  mov     r12, rsi
0x180064968  xor     esi, esi
0x18006496a  mov     rbx, [r15+50h]
0x18006496e  test    rbx, rbx
0x180064971  jz      short loc_18006498F
0x180064973  call    cs:__imp_GetProcessHeap
0x180064979  mov     rcx, rax; hHeap
0x18006497c  lea     r8, [rbx-4]; lpMem
0x180064980  xor     edx, edx; dwFlags
0x180064982  call    cs:__imp_HeapFree
0x180064988  xor     ecx, ecx
0x18006498a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006498f  mov     [r15+50h], r12
0x180064993  mov     r12, r14
0x180064996  xor     r14d, r14d
0x180064999  mov     rbx, [r15+58h]
0x18006499d  test    rbx, rbx
0x1800649a0  jz      short loc_1800649BE
0x1800649a2  call    cs:__imp_GetProcessHeap
0x1800649a8  mov     rcx, rax; hHeap
0x1800649ab  lea     r8, [rbx-4]; lpMem
0x1800649af  xor     edx, edx; dwFlags
0x1800649b1  call    cs:__imp_HeapFree
0x1800649b7  xor     ecx, ecx
0x1800649b9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800649be  mov     [r15+58h], r12
0x1800649c2  mov     r12, [rbp+57h+var_90]
0x1800649c6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800649ca  mov     rcx, [r15+68h]; hObject
0x1800649ce  lea     rax, [rcx-1]
0x1800649d2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800649d6  ja      short loc_1800649DE
0x1800649d8  call    cs:__imp_CloseHandle
0x1800649de  lea     rax, [r12+1]
0x1800649e3  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800649e9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800649f0  cmovz   r12, rax
0x1800649f4  mov     [r15+68h], r12
0x1800649f8  mov     r12, [rbp+57h+var_80]
0x1800649fc  mov     rcx, [r15+70h]; hObject
0x180064a00  lea     rax, [rcx-1]
0x180064a04  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180064a08  ja      short loc_180064A10
0x180064a0a  call    cs:__imp_CloseHandle
0x180064a10  lea     rax, [r12+1]
0x180064a15  test    rax, 0FFFFFFFFFFFFFFFEh
0x180064a1b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180064a22  cmovz   r12, rax
0x180064a26  mov     [r15+70h], r12
0x180064a2a  mov     r15, rax
0x180064a2d  mov     ecx, edi
0x180064a2f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180064a34  nop
0x180064a35  lea     rax, [r15-1]
0x180064a39  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180064a3d  ja      short loc_180064A49
0x180064a3f  mov     rcx, r15; hObject
0x180064a42  call    cs:__imp_CloseHandle
0x180064a48  nop
0x180064a49  lea     rax, [rbx-1]
0x180064a4d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180064a51  ja      short loc_180064A5D
0x180064a53  mov     rcx, rbx; hObject
0x180064a56  call    cs:__imp_CloseHandle
0x180064a5c  nop
0x180064a5d  test    r14, r14
0x180064a60  jz      short loc_180064A7F
0x180064a62  call    cs:__imp_GetProcessHeap
0x180064a68  mov     rcx, rax; hHeap
0x180064a6b  lea     r8, [r14-4]; lpMem
0x180064a6f  xor     edx, edx; dwFlags
0x180064a71  call    cs:__imp_HeapFree
0x180064a77  xor     ecx, ecx
0x180064a79  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180064a7e  nop
0x180064a7f  test    rsi, rsi
0x180064a82  jz      short loc_180064AA1
0x180064a84  call    cs:__imp_GetProcessHeap
0x180064a8a  mov     rcx, rax; hHeap
0x180064a8d  lea     r8, [rsi-4]; lpMem
0x180064a91  xor     edx, edx; dwFlags
0x180064a93  call    cs:__imp_HeapFree
0x180064a99  xor     ecx, ecx
0x180064a9b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180064aa0  nop
0x180064aa1  test    r13, r13
0x180064aa4  jz      short loc_180064AC2
0x180064aa6  call    cs:__imp_GetProcessHeap
0x180064aac  mov     rcx, rax; hHeap
0x180064aaf  lea     r8, [r13-4]; lpMem
0x180064ab3  xor     edx, edx; dwFlags
0x180064ab5  call    cs:__imp_HeapFree
0x180064abb  xor     ecx, ecx
0x180064abd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180064ac2  mov     eax, edi
0x180064ac4  mov     rbx, [rsp+0C0h+arg_0]
0x180064acc  add     rsp, 90h
0x180064ad3  pop     r15
0x180064ad5  pop     r14
0x180064ad7  pop     r13
0x180064ad9  pop     r12
0x180064adb  pop     rdi
0x180064adc  pop     rsi
0x180064add  pop     rbp
0x180064ade  retn
```
