# CImpReg::UpdateProperty(long,IWbemClassObject *,ushort *,CProvObj &,CObject *,CVariant *)

- ea: `0x1800121e0`
- end: `0x180012470`
- name: `?UpdateProperty@CImpReg@@UEAAJJPEAUIWbemClassObject@@PEAGAEAVCProvObj@@PEAVCObject@@PEAVCVariant@@@Z`
- size: `656`
- prototype: `__int64 __fastcall(CImpReg *this, __int64, struct IWbemClassObject *, unsigned __int16 *, struct CProvObj *, struct CObject *, struct CVariant *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001490`
- `0x180002770`
- `0x180002e90`
- `0x180002fa0`
- `0x180004260`
- `0x1800087c0`
- `0x1800087f0`
- `0x180008c00`
- `0x1800091e0`
- `0x1800094b0`
- `0x180009d80`
- `0x180011c18`
- `0x18001211c`
- `0x1800121e0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001242e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001242e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012423`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012423`

## pseudocode

```c
__int64 __fastcall CImpReg::UpdateProperty(
        CImpReg *this,
        __int64 a2,
        struct IWbemClassObject *a3,
        unsigned __int16 *a4,
        struct CProvObj *a5,
        struct CObject *a6,
        struct CVariant *a7)
{
  const unsigned __int16 *FullToken; // rax
  unsigned int Status; // ebx
  const unsigned __int16 *v12; // rax
  int v13; // edi
  unsigned __int16 *Token; // rax
  HKEY v15; // rbx
  const unsigned __int16 *v16; // rax
  const WCHAR *v17; // rsi
  unsigned __int16 v18; // r8
  unsigned int v19; // eax
  CImpReg *v20; // rcx
  BYTE *v21; // rdi
  LSTATUS v22; // eax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwType; // [rsp+44h] [rbp-BCh] BYREF
  int v26; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE *lpData; // [rsp+58h] [rbp-A8h] BYREF
  __int16 *v29; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v30; // [rsp+68h] [rbp-98h] BYREF
  int v31; // [rsp+6Ch] [rbp-94h]
  HKEY v32; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[8]; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvargDest; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v35[8]; // [rsp+A0h] [rbp-60h] BYREF
  int v36; // [rsp+A8h] [rbp-58h]

  lpData = 0;
  v30 = 0;
  v29 = &v30;
  v31 = 0;
  v26 = 0;
  hKey = 0;
  v32 = 0;
  dwType = 0;
  cbData = 0;
  FullToken = CProvObj::sGetFullToken(a5, 1);
  CProvObj::CProvObj((CProvObj *)v35, FullToken, 0x5Cu, 1);
  Status = CProvObj::dwGetStatus((CProvObj *)v35, 1);
  if ( !Status )
  {
    v12 = CProvObj::sGetFullToken(a5, 0);
    Status = CImpReg::GetRoot(this, &hKey, (struct CProvObj *)v35, v12, a6, &v26);
    if ( !Status )
    {
      v13 = v26;
      while ( ++v13 < v36 )
      {
        Token = (unsigned __int16 *)CProvObj::sGetToken((CProvObj *)v35, v13);
        Status = CImpReg::OpenKeyForWritting(this, hKey, Token, &v32, a6);
        if ( !Status )
        {
          v15 = v32;
          hKey = v32;
          v16 = CProvObj::sGetToken((CProvObj *)v35, v13);
          Status = CHandleCache::lAddToList(a6, v16, v15);
          if ( !Status )
            continue;
        }
        goto LABEL_24;
      }
      if ( *((int *)a5 + 2) <= 2 )
        v17 = 0;
      else
        v17 = CProvObj::sGetToken(a5, 2);
      CVariant::CVariant((CVariant *)v33);
      if ( a3 )
      {
        v19 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
                a3,
                a4,
                0,
                &pvargDest,
                0,
                0);
      }
      else
      {
        if ( !a7 )
        {
          Status = -2147217407;
LABEL_23:
          CVariant::~CVariant((CVariant *)v33);
          goto LABEL_24;
        }
        v19 = OMSVariantChangeType(&pvargDest, (VARIANTARG *)((char *)a7 + 8), v18, *((_WORD *)a7 + 4));
      }
      Status = v19;
      if ( !v19 )
      {
        Status = CImpReg::ConvertSetData(v20, (struct CVariant *)v33, (void **)&lpData, &dwType, &cbData);
        if ( !Status )
        {
          if ( !*((_QWORD *)this + 16) || *((_DWORD *)a6 + 24) )
          {
            v21 = lpData;
            v22 = RegSetValueExW(hKey, v17, 0, dwType, lpData, cbData);
          }
          else
          {
            v21 = lpData;
            v22 = (*((__int64 (__fastcall **)(HKEY, const WCHAR *, _QWORD, _QWORD, BYTE *, DWORD))this + 20))(
                    hKey,
                    v17,
                    0,
                    dwType,
                    lpData,
                    cbData);
          }
          Status = v22;
          CoTaskMemFree(v21);
        }
      }
      goto LABEL_23;
    }
  }
LABEL_24:
  CProvObj::~CProvObj((CProvObj *)v35);
  TString::Empty((TString *)&v29);
  return Status;
}

```

## disassembly

```asm
0x1800121e0  push    rbp
0x1800121e2  push    rbx
0x1800121e3  push    rsi
0x1800121e4  push    rdi
0x1800121e5  push    r12
0x1800121e7  push    r13
0x1800121e9  push    r14
0x1800121eb  push    r15
0x1800121ed  lea     rbp, [rsp-18h]
0x1800121f2  sub     rsp, 118h
0x1800121f9  mov     r13, r9
0x1800121fc  mov     r12, r8
0x1800121ff  mov     r15, rcx
0x180012202  xor     edi, edi
0x180012204  mov     [rsp+150h+var_F8], rdi
0x180012209  mov     [rsp+150h+var_E8], di
0x18001220e  lea     rax, [rsp+150h+var_E8]
0x180012213  mov     [rsp+150h+var_F0], rax
0x180012218  mov     [rsp+150h+var_E4], edi
0x18001221c  mov     [rsp+150h+var_108], edi
0x180012220  mov     [rsp+150h+hKey], rdi
0x180012225  mov     [rsp+150h+var_E0], rdi
0x18001222a  mov     [rsp+150h+dwType], edi
0x18001222e  mov     [rsp+150h+var_110], edi
0x180012232  lea     ebx, [rdi+5Ch]
0x180012235  lea     r14d, [rdi+1]
0x180012239  mov     edx, r14d; int
0x18001223c  mov     rsi, [rbp+50h+arg_20]
0x180012243  mov     rcx, rsi; this
0x180012246  call    ?sGetFullToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetFullToken(int)
0x18001224b  mov     rdx, rax; unsigned __int16 *
0x18001224e  mov     r9b, r14b; bool
0x180012251  movzx   r8d, bx; unsigned __int16
0x180012255  lea     rcx, [rbp+50h+var_B0]; this
0x180012259  call    ??0CProvObj@@QEAA@PEBGG_N@Z; CProvObj::CProvObj(ushort const *,ushort,bool)
0x18001225e  nop
0x18001225f  mov     edx, r14d; int
0x180012262  lea     rcx, [rbp+50h+var_B0]; this
0x180012266  call    ?dwGetStatus@CProvObj@@QEAAKH@Z; CProvObj::dwGetStatus(int)
0x18001226b  mov     ebx, eax
0x18001226d  test    eax, eax
0x18001226f  jnz     loc_180012446
0x180012275  xor     edx, edx; int
0x180012277  mov     rcx, rsi; this
0x18001227a  call    ?sGetFullToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetFullToken(int)
0x18001227f  mov     r9, rax; unsigned __int16 *
0x180012282  lea     rax, [rsp+150h+var_108]
0x180012287  mov     qword ptr [rsp+150h+cbData], rax; int *
0x18001228c  mov     r14, [rbp+50h+arg_28]
0x180012293  mov     [rsp+150h+lpData], r14; struct CHandleCache *
0x180012298  lea     r8, [rbp+50h+var_B0]; struct CProvObj *
0x18001229c  lea     rdx, [rsp+150h+hKey]; HKEY *
0x1800122a1  mov     rcx, r15; this
0x1800122a4  call    ?GetRoot@CImpReg@@QEAAHPEAPEAUHKEY__@@AEAVCProvObj@@PEBGPEAVCHandleCache@@AEAH@Z; CImpReg::GetRoot(HKEY__ * *,CProvObj &,ushort const *,CHandleCache *,int &)
0x1800122a9  mov     ebx, eax
0x1800122ab  test    eax, eax
0x1800122ad  jnz     loc_180012446
0x1800122b3  mov     edi, [rsp+150h+var_108]
0x1800122b7  inc     edi
0x1800122b9  cmp     edi, [rbp+50h+var_A8]
0x1800122bc  jge     short loc_18001231B
0x1800122be  mov     edx, edi; int
0x1800122c0  lea     rcx, [rbp+50h+var_B0]; this
0x1800122c4  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x1800122c9  mov     [rsp+150h+lpData], r14; struct CHandleCache *
0x1800122ce  lea     r9, [rsp+150h+var_E0]; HKEY *
0x1800122d3  mov     r8, rax; unsigned __int16 *
0x1800122d6  mov     rdx, [rsp+150h+hKey]; HKEY
0x1800122db  mov     rcx, r15; this
0x1800122de  call    ?OpenKeyForWritting@CImpReg@@QEAAHPEAUHKEY__@@PEAGPEAPEAU2@PEAVCHandleCache@@@Z; CImpReg::OpenKeyForWritting(HKEY__ *,ushort *,HKEY__ * *,CHandleCache *)
0x1800122e3  mov     ebx, eax
0x1800122e5  test    eax, eax
0x1800122e7  jnz     loc_180012446
0x1800122ed  mov     rbx, [rsp+150h+var_E0]
0x1800122f2  mov     [rsp+150h+hKey], rbx
0x1800122f7  mov     edx, edi; int
0x1800122f9  lea     rcx, [rbp+50h+var_B0]; this
0x1800122fd  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x180012302  mov     r8, rbx; void *
0x180012305  mov     rdx, rax; unsigned __int16 *
0x180012308  mov     rcx, r14; this
0x18001230b  call    ?lAddToList@CHandleCache@@QEAAJPEBGPEAX@Z; CHandleCache::lAddToList(ushort const *,void *)
0x180012310  mov     ebx, eax
0x180012312  test    eax, eax
0x180012314  jz      short loc_1800122B7
0x180012316  jmp     loc_180012446
0x18001231b  mov     edx, 2; int
0x180012320  cmp     [rsi+8], edx
0x180012323  jle     short loc_180012332
0x180012325  mov     rcx, rsi; this
0x180012328  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x18001232d  mov     rsi, rax
0x180012330  jmp     short loc_180012334
0x180012332  xor     esi, esi
0x180012334  lea     rcx, [rsp+150h+var_D8]; this
0x180012339  call    ??0CVariant@@QEAA@XZ; CVariant::CVariant(void)
0x18001233e  nop
0x18001233f  test    r12, r12
0x180012342  jz      short loc_180012372
0x180012344  mov     rax, [r12]
0x180012348  mov     qword ptr [rsp+150h+cbData], 0
0x180012351  mov     [rsp+150h+lpData], 0
0x18001235a  lea     r9, [rbp+50h+pvargDest]
0x18001235e  xor     r8d, r8d
0x180012361  mov     rdx, r13
0x180012364  mov     rcx, r12
0x180012367  mov     rax, [rax+20h]
0x18001236b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012370  jmp     short loc_180012393
0x180012372  mov     rdx, [rbp+50h+arg_30]
0x180012379  test    rdx, rdx
0x18001237c  jz      loc_180012436
0x180012382  add     rdx, 8; pvarSrc
0x180012386  movzx   r9d, word ptr [rdx]; unsigned __int16
0x18001238a  lea     rcx, [rbp+50h+pvargDest]; pvargDest
0x18001238e  call    ?OMSVariantChangeType@@YAJPEAUtagVARIANT@@0GG@Z; OMSVariantChangeType(tagVARIANT *,tagVARIANT *,ushort,ushort)
0x180012393  mov     ebx, eax
0x180012395  test    eax, eax
0x180012397  jnz     loc_18001243B
0x18001239d  lea     rax, [rsp+150h+var_110]
0x1800123a2  mov     [rsp+150h+lpData], rax; unsigned int *
0x1800123a7  lea     r9, [rsp+150h+dwType]; unsigned int *
0x1800123ac  lea     r8, [rsp+150h+var_F8]; void **
0x1800123b1  lea     rdx, [rsp+150h+var_D8]; struct CVariant *
0x1800123b6  call    ?ConvertSetData@CImpReg@@QEAAJAEAVCVariant@@PEAPEAXPEAK2@Z; CImpReg::ConvertSetData(CVariant &,void * *,ulong *,ulong *)
0x1800123bb  mov     ebx, eax
0x1800123bd  test    eax, eax
0x1800123bf  jnz     short loc_18001243B
0x1800123c1  cmp     qword ptr [r15+80h], 0
0x1800123c9  jz      short loc_180012401
0x1800123cb  cmp     [r14+60h], eax
0x1800123cf  jnz     short loc_180012401
0x1800123d1  mov     ecx, [rsp+150h+var_110]
0x1800123d5  mov     [rsp+150h+cbData], ecx
0x1800123d9  mov     rdi, [rsp+150h+var_F8]
0x1800123de  mov     [rsp+150h+lpData], rdi
0x1800123e3  mov     r9d, [rsp+150h+dwType]
0x1800123e8  xor     r8d, r8d
0x1800123eb  mov     rdx, rsi
0x1800123ee  mov     rcx, [rsp+150h+hKey]
0x1800123f3  mov     rax, [r15+0A0h]
0x1800123fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123ff  jmp     short loc_180012429
0x180012401  mov     eax, [rsp+150h+var_110]
0x180012405  mov     [rsp+150h+cbData], eax; cbData
0x180012409  mov     rdi, [rsp+150h+var_F8]
0x18001240e  mov     [rsp+150h+lpData], rdi; lpData
0x180012413  mov     r9d, [rsp+150h+dwType]; dwType
0x180012418  xor     r8d, r8d; Reserved
0x18001241b  mov     rdx, rsi; lpValueName
0x18001241e  mov     rcx, [rsp+150h+hKey]; hKey
0x180012423  call    cs:__imp_RegSetValueExW
0x180012429  mov     ebx, eax
0x18001242b  mov     rcx, rdi; pv
0x18001242e  call    cs:__imp_CoTaskMemFree
0x180012434  jmp     short loc_18001243B
0x180012436  mov     ebx, 80041001h
0x18001243b  lea     rcx, [rsp+150h+var_D8]; this
0x180012440  call    ??1CVariant@@UEAA@XZ; CVariant::~CVariant(void)
0x180012445  nop
0x180012446  lea     rcx, [rbp+50h+var_B0]; this
0x18001244a  call    ??1CProvObj@@UEAA@XZ; CProvObj::~CProvObj(void)
0x18001244f  nop
0x180012450  lea     rcx, [rsp+150h+var_F0]; this
0x180012455  call    ?Empty@TString@@QEAAXXZ; TString::Empty(void)
0x18001245a  mov     eax, ebx
0x18001245c  add     rsp, 118h
0x180012463  pop     r15
0x180012465  pop     r14
0x180012467  pop     r13
0x180012469  pop     r12
0x18001246b  pop     rdi
0x18001246c  pop     rsi
0x18001246d  pop     rbx
0x18001246e  pop     rbp
0x18001246f  retn
```
