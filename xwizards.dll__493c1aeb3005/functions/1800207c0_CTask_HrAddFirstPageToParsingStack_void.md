# CTask::HrAddFirstPageToParsingStack(void)

- ea: `0x1800207c0`
- end: `0x180020b33`
- name: `?HrAddFirstPageToParsingStack@CTask@@AEAAJXZ`
- size: `883`
- prototype: `__int64 __fastcall(CTask *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021c98`
- `0x1800237d8`

## callees

- `0x18000addc`
- `0x18000ae04`
- `0x1800200f8`
- `0x1800207c0`
- `0x180020f0c`
- `0x180021634`
- `0x1800291f8`
- `0x180029a28`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020ae6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020ae6`

## pseudocode

```c
__int64 __fastcall CTask::HrAddFirstPageToParsingStack(CTask *this)
{
  __int64 v2; // rax
  int v3; // eax
  int v4; // ebx
  unsigned int v5; // esi
  int v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // eax
  unsigned int v16; // eax
  struct IXWizardPageEvent *v17; // r9
  bool v18; // zf
  int v19; // eax
  _QWORD *v20; // rax
  __int64 v21; // rdx
  unsigned int v23; // [rsp+70h] [rbp+30h] BYREF
  struct IEnumXWizardPage *v24; // [rsp+78h] [rbp+38h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+40h] BYREF
  struct IXWizardPageEvent *v26; // [rsp+88h] [rbp+48h] BYREF

  v18 = (*((_BYTE *)this + 116) & 0x20) == 0;
  v24 = 0;
  if ( !v18 )
  {
    v2 = *((_QWORD *)this + 39);
    if ( v2 != *((_QWORD *)this + 40) )
    {
      v24 = *(struct IEnumXWizardPage **)(*(_QWORD *)v2 + 32LL);
      (*(void (__fastcall **)(struct IEnumXWizardPage *))(*(_QWORD *)v24 + 8LL))(v24);
    }
  }
  CTask::ClearParsingStack(this);
  if ( v24 )
  {
    v3 = (*(__int64 (__fastcall **)(struct IEnumXWizardPage *))(*(_QWORD *)v24 + 40LL))(v24);
  }
  else if ( (*((_BYTE *)this + 116) & 0x20) != 0 )
  {
    v3 = CPEnumXWizardControlPage::HrCreateInstance(*((const struct IXWizardTaskEvent **)this + 32), 0, &v24);
  }
  else if ( *((_DWORD *)this + 8) == 2 )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, struct IEnumXWizardPage **))(**((_QWORD **)this + 31) + 128LL))(
           *((_QWORD *)this + 31),
           (char *)this + 16,
           0,
           &v24);
  }
  else
  {
    v3 = CPEnumXWizardControlTask::HrCreateInstance((const struct _GUID *)this + 1, &v24);
  }
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = 0;
    pv = 0;
    v6 = (*(__int64 (__fastcall **)(struct IEnumXWizardPage *, __int64, LPVOID *, _QWORD))(*(_QWORD *)v24 + 24LL))(
           v24,
           1,
           &pv,
           0);
    v7 = pv;
    v4 = v6;
    if ( !v6 )
      *(_OWORD *)((char *)this + 124) = *(_OWORD *)pv;
    v8 = *(_QWORD *)&GUID_NULL.Data1;
    v9 = *(_QWORD *)GUID_NULL.Data4;
    v10 = *(_QWORD *)((char *)this + 188) - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v10 )
      v10 = *(_QWORD *)((char *)this + 196) - *(_QWORD *)GUID_NULL.Data4;
    if ( v10 )
    {
      if ( !v4 )
      {
        while ( 1 )
        {
          v11 = *(_QWORD *)((char *)this + 188) - *v7;
          if ( !v11 )
            v11 = *(_QWORD *)((char *)this + 196) - v7[1];
          if ( !v11 )
            break;
          CoTaskMemFree(v7);
          pv = 0;
          v12 = (*(__int64 (__fastcall **)(struct IEnumXWizardPage *, __int64, LPVOID *))(*(_QWORD *)v24 + 24LL))(
                  v24,
                  1,
                  &pv);
          v7 = pv;
          ++v5;
          v4 = v12;
          if ( v12 )
          {
            v9 = *(_QWORD *)GUID_NULL.Data4;
            v8 = *(_QWORD *)&GUID_NULL.Data1;
            goto LABEL_23;
          }
        }
        v9 = *(_QWORD *)GUID_NULL.Data4;
        v8 = *(_QWORD *)&GUID_NULL.Data1;
        goto LABEL_24;
      }
    }
    else
    {
LABEL_23:
      if ( !v4 )
      {
LABEL_24:
        v13 = *(_QWORD *)((char *)this + 140) - v8;
        if ( !v13 )
          v13 = *(_QWORD *)((char *)this + 148) - v9;
        if ( !v13 )
        {
          *(_OWORD *)((char *)this + 140) = *(_OWORD *)v7;
          v9 = *(_QWORD *)GUID_NULL.Data4;
          v8 = *(_QWORD *)&GUID_NULL.Data1;
        }
        v14 = *(_QWORD *)((char *)this + 172) - v8;
        if ( !v14 )
          v14 = *(_QWORD *)((char *)this + 180) - v9;
        if ( !v14 )
          *(_OWORD *)((char *)this + 172) = *(_OWORD *)v7;
        v15 = (*(__int64 (__fastcall **)(struct IEnumXWizardPage *, __int64))(*(_QWORD *)v24 + 40LL))(v24, v9);
        v4 = v15;
        if ( v5 && v15 >= 0 )
          v4 = (*(__int64 (__fastcall **)(struct IEnumXWizardPage *, _QWORD))(*(_QWORD *)v24 + 32LL))(v24, v5);
        v16 = 0;
        v17 = 0;
        v23 = 0;
        v26 = 0;
        v18 = v4 == 0;
        if ( v4 >= 0 )
        {
          v19 = CTask::HrCreateParsingStackData(this, 0, &v26, &v24, &v23, 1);
          v17 = v26;
          v4 = v19;
          v16 = v23;
          v18 = v4 == 0;
        }
        if ( v18 )
        {
          v4 = CTask::HrAddPageToParsingStack(this, 0, 0, v17, v24, v16, 0, 1);
          if ( v4 >= 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids);
        }
        goto LABEL_51;
      }
    }
    if ( v4 == 1 )
    {
      v4 = 262657;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_52;
      v21 = 65;
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_52;
      v21 = 66;
    }
    WPP_SF_d(v20[2], v21, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, (unsigned int)v4);
LABEL_51:
    v7 = pv;
LABEL_52:
    if ( v7 )
      CoTaskMemFree(v7);
    (*(void (__fastcall **)(struct IEnumXWizardPage *, __int64))(*(_QWORD *)v24 + 16LL))(v24, v9);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      67,
      &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
      (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800207c0  push    rbp
0x1800207c2  push    rbx
0x1800207c3  push    rsi
0x1800207c4  push    rdi
0x1800207c5  push    r15
0x1800207c7  mov     rbp, rsp
0x1800207ca  sub     rsp, 40h
0x1800207ce  test    byte ptr [rcx+74h], 20h
0x1800207d2  mov     rdi, rcx
0x1800207d5  mov     [rbp+arg_8], 0
0x1800207dd  jz      short loc_180020806
0x1800207df  mov     rax, [rcx+138h]
0x1800207e6  cmp     rax, [rcx+140h]
0x1800207ed  jz      short loc_180020806
0x1800207ef  mov     rax, [rax]
0x1800207f2  mov     rcx, [rax+20h]
0x1800207f6  mov     [rbp+arg_8], rcx
0x1800207fa  mov     rax, [rcx]
0x1800207fd  mov     rax, [rax+8]
0x180020801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020806  mov     rcx, rdi; this
0x180020809  call    ?ClearParsingStack@CTask@@AEAAXXZ; CTask::ClearParsingStack(void)
0x18002080e  mov     rcx, [rbp+arg_8]
0x180020812  test    rcx, rcx
0x180020815  jz      short loc_180020825
0x180020817  mov     rax, [rcx]
0x18002081a  mov     rax, [rax+28h]
0x18002081e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020823  jmp     short loc_180020875
0x180020825  test    byte ptr [rdi+74h], 20h
0x180020829  jz      short loc_18002083F
0x18002082b  mov     rcx, [rdi+100h]; struct IXWizardTaskEvent *
0x180020832  lea     r8, [rbp+arg_8]; struct IEnumXWizardPage **
0x180020836  xor     edx, edx; struct IXWizardPageEvent *
0x180020838  call    ?HrCreateInstance@CPEnumXWizardControlPage@@SAJPEBUIXWizardTaskEvent@@PEBUIXWizardPageEvent@@PEAPEAUIEnumXWizardPage@@@Z; CPEnumXWizardControlPage::HrCreateInstance(IXWizardTaskEvent const *,IXWizardPageEvent const *,IEnumXWizardPage * *)
0x18002083d  jmp     short loc_180020875
0x18002083f  cmp     dword ptr [rdi+20h], 2
0x180020843  jz      short loc_180020854
0x180020845  lea     rdx, [rbp+arg_8]; struct IEnumXWizardPage **
0x180020849  lea     rcx, [rdi+10h]; struct _GUID *
0x18002084d  call    ?HrCreateInstance@CPEnumXWizardControlTask@@SAJPEBU_GUID@@PEAPEAUIEnumXWizardPage@@@Z; CPEnumXWizardControlTask::HrCreateInstance(_GUID const *,IEnumXWizardPage * *)
0x180020852  jmp     short loc_180020875
0x180020854  mov     rcx, [rdi+0F8h]
0x18002085b  lea     r9, [rbp+arg_8]
0x18002085f  xor     r8d, r8d
0x180020862  lea     rdx, [rdi+10h]
0x180020866  mov     rax, [rcx]
0x180020869  mov     rax, [rax+80h]
0x180020870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020875  lea     r15, WPP_GLOBAL_Control
0x18002087c  mov     ebx, eax
0x18002087e  test    eax, eax
0x180020880  js      loc_180020AFC
0x180020886  mov     rcx, [rbp+arg_8]
0x18002088a  lea     r8, [rbp+pv]
0x18002088e  xor     esi, esi
0x180020890  xor     r9d, r9d
0x180020893  mov     [rbp+pv], rsi
0x180020897  mov     rax, [rcx]
0x18002089a  lea     edx, [rsi+1]
0x18002089d  mov     rax, [rax+18h]
0x1800208a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208a6  mov     rcx, [rbp+pv]; pv
0x1800208aa  mov     ebx, eax
0x1800208ac  test    eax, eax
0x1800208ae  jnz     short loc_1800208B8
0x1800208b0  movups  xmm0, xmmword ptr [rcx]
0x1800208b3  movdqu  xmmword ptr [rdi+7Ch], xmm0
0x1800208b8  mov     rax, [rdi+0BCh]
0x1800208bf  mov     r8, qword ptr cs:GUID_NULL.Data1
0x1800208c6  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x1800208cd  sub     rax, r8
0x1800208d0  jnz     short loc_1800208DC
0x1800208d2  mov     rax, [rdi+0C4h]
0x1800208d9  sub     rax, rdx
0x1800208dc  test    rax, rax
0x1800208df  jz      short loc_18002094C
0x1800208e1  test    ebx, ebx
0x1800208e3  jnz     loc_180020A90
0x1800208e9  mov     rax, [rdi+0BCh]
0x1800208f0  sub     rax, [rcx]
0x1800208f3  jnz     short loc_180020900
0x1800208f5  mov     rax, [rdi+0C4h]
0x1800208fc  sub     rax, [rcx+8]
0x180020900  test    rax, rax
0x180020903  jz      loc_180020A7D
0x180020909  call    cs:__imp_CoTaskMemFree
0x18002090f  mov     rcx, [rbp+arg_8]
0x180020913  lea     r8, [rbp+pv]
0x180020917  mov     [rbp+pv], 0
0x18002091f  xor     r9d, r9d
0x180020922  mov     rax, [rcx]
0x180020925  lea     edx, [r9+1]
0x180020929  mov     rax, [rax+18h]
0x18002092d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020932  mov     rcx, [rbp+pv]
0x180020936  inc     esi
0x180020938  mov     ebx, eax
0x18002093a  test    eax, eax
0x18002093c  jz      short loc_1800208E9
0x18002093e  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x180020945  mov     r8, qword ptr cs:GUID_NULL.Data1
0x18002094c  test    ebx, ebx
0x18002094e  jnz     loc_180020A90
0x180020954  mov     rax, [rdi+8Ch]
0x18002095b  sub     rax, r8
0x18002095e  jnz     short loc_18002096A
0x180020960  mov     rax, [rdi+94h]
0x180020967  sub     rax, rdx
0x18002096a  test    rax, rax
0x18002096d  jnz     short loc_180020988
0x18002096f  movups  xmm0, xmmword ptr [rcx]
0x180020972  movdqu  xmmword ptr [rdi+8Ch], xmm0
0x18002097a  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x180020981  mov     r8, qword ptr cs:GUID_NULL.Data1
0x180020988  mov     rax, [rdi+0ACh]
0x18002098f  sub     rax, r8
0x180020992  jnz     short loc_18002099E
0x180020994  mov     rax, [rdi+0B4h]
0x18002099b  sub     rax, rdx
0x18002099e  test    rax, rax
0x1800209a1  jnz     short loc_1800209AE
0x1800209a3  movups  xmm0, xmmword ptr [rcx]
0x1800209a6  movdqu  xmmword ptr [rdi+0ACh], xmm0
0x1800209ae  mov     rcx, [rbp+arg_8]
0x1800209b2  mov     rax, [rcx]
0x1800209b5  mov     rax, [rax+28h]
0x1800209b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209be  mov     ebx, eax
0x1800209c0  test    esi, esi
0x1800209c2  jz      short loc_1800209DC
0x1800209c4  test    eax, eax
0x1800209c6  js      short loc_1800209DC
0x1800209c8  mov     rcx, [rbp+arg_8]
0x1800209cc  mov     edx, esi
0x1800209ce  mov     rax, [rcx]
0x1800209d1  mov     rax, [rax+20h]
0x1800209d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209da  mov     ebx, eax
0x1800209dc  xor     eax, eax
0x1800209de  xor     r9d, r9d
0x1800209e1  mov     [rbp+arg_0], eax
0x1800209e4  mov     [rbp+arg_18], r9
0x1800209e8  test    ebx, ebx
0x1800209ea  js      short loc_180020A1A
0x1800209ec  lea     rax, [rbp+arg_0]
0x1800209f0  mov     [rsp+40h+var_18], 1; int
0x1800209f8  lea     r9, [rbp+arg_8]; struct IEnumXWizardPage **
0x1800209fc  mov     [rsp+40h+var_20], rax; unsigned int *
0x180020a01  lea     r8, [rbp+arg_18]; struct IXWizardPageEvent **
0x180020a05  xor     edx, edx; struct _GUID *
0x180020a07  mov     rcx, rdi; this
0x180020a0a  call    ?HrCreateParsingStackData@CTask@@AEAAJPEAU_GUID@@PEAPEAUIXWizardPageEvent@@PEAPEAUIEnumXWizardPage@@PEAKH@Z; CTask::HrCreateParsingStackData(_GUID *,IXWizardPageEvent * *,IEnumXWizardPage * *,ulong *,int)
0x180020a0f  mov     r9, [rbp+arg_18]; struct IXWizardPageEvent *
0x180020a13  mov     ebx, eax
0x180020a15  mov     eax, [rbp+arg_0]
0x180020a18  test    ebx, ebx
0x180020a1a  jnz     loc_180020ADD
0x180020a20  mov     [rsp+40h+var_8], 1; int
0x180020a28  xor     r8d, r8d; struct _GUID *
0x180020a2b  mov     [rsp+40h+var_10], 0; int
0x180020a33  xor     edx, edx; struct _GUID *
0x180020a35  mov     [rsp+40h+var_18], eax; unsigned int
0x180020a39  mov     rcx, rdi; this
0x180020a3c  mov     rax, [rbp+arg_8]
0x180020a40  mov     [rsp+40h+var_20], rax; struct IEnumXWizardPage *
0x180020a45  call    ?HrAddPageToParsingStack@CTask@@AEAAJPEBU_GUID@@0PEBUIXWizardPageEvent@@PEBUIEnumXWizardPage@@KHH@Z; CTask::HrAddPageToParsingStack(_GUID const *,_GUID const *,IXWizardPageEvent const *,IEnumXWizardPage const *,ulong,int,int)
0x180020a4a  mov     ebx, eax
0x180020a4c  test    eax, eax
0x180020a4e  js      loc_180020ADD
0x180020a54  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a5b  cmp     rcx, r15
0x180020a5e  jz      short loc_180020ADD
0x180020a60  test    byte ptr [rcx+1Ch], 8
0x180020a64  jz      short loc_180020ADD
0x180020a66  mov     rcx, [rcx+10h]
0x180020a6a  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180020a71  mov     edx, 40h ; '@'
0x180020a76  call    WPP_SF_
0x180020a7b  jmp     short loc_180020ADD
0x180020a7d  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x180020a84  mov     r8, qword ptr cs:GUID_NULL.Data1
0x180020a8b  jmp     loc_180020954
0x180020a90  cmp     ebx, 1
0x180020a93  jnz     short loc_180020AB3
0x180020a95  mov     ebx, 40201h
0x180020a9a  mov     rax, cs:WPP_GLOBAL_Control
0x180020aa1  cmp     rax, r15
0x180020aa4  jz      short loc_180020AE1
0x180020aa6  test    byte ptr [rax+1Ch], 8
0x180020aaa  jz      short loc_180020AE1
0x180020aac  mov     edx, 41h ; 'A'
0x180020ab1  jmp     short loc_180020ACA
0x180020ab3  mov     rax, cs:WPP_GLOBAL_Control
0x180020aba  cmp     rax, r15
0x180020abd  jz      short loc_180020AE1
0x180020abf  test    byte ptr [rax+1Ch], 4
0x180020ac3  jz      short loc_180020AE1
0x180020ac5  mov     edx, 42h ; 'B'
0x180020aca  mov     rcx, [rax+10h]
0x180020ace  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180020ad5  mov     r9d, ebx
0x180020ad8  call    WPP_SF_d
0x180020add  mov     rcx, [rbp+pv]; pv
0x180020ae1  test    rcx, rcx
0x180020ae4  jz      short loc_180020AEC
0x180020ae6  call    cs:__imp_CoTaskMemFree
0x180020aec  mov     rcx, [rbp+arg_8]
0x180020af0  mov     rax, [rcx]
0x180020af3  mov     rax, [rax+10h]
0x180020af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020afc  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b03  cmp     rcx, r15
0x180020b06  jz      short loc_180020B26
0x180020b08  test    byte ptr [rcx+1Ch], 10h
0x180020b0c  jz      short loc_180020B26
0x180020b0e  mov     rcx, [rcx+10h]
0x180020b12  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x180020b19  mov     edx, 43h ; 'C'
0x180020b1e  mov     r9d, ebx
0x180020b21  call    WPP_SF_d
0x180020b26  mov     eax, ebx
0x180020b28  add     rsp, 40h
0x180020b2c  pop     r15
0x180020b2e  pop     rdi
0x180020b2f  pop     rsi
0x180020b30  pop     rbx
0x180020b31  pop     rbp
0x180020b32  retn
```
