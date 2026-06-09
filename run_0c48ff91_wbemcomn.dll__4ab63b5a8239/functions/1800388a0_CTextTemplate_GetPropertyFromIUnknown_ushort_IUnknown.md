# CTextTemplate::GetPropertyFromIUnknown(ushort *,IUnknown *)

- ea: `0x1800388a0`
- end: `0x180038c14`
- name: `?GetPropertyFromIUnknown@CTextTemplate@@AEAAPEAGPEAGPEAUIUnknown@@@Z`
- size: `884`
- prototype: `unsigned __int16 *__fastcall(CTextTemplate *__hidden this, unsigned __int16 *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180038c20`

## callees

- `0x1800029a0`
- `0x180005ec0`
- `0x1800094f0`
- `0x180010770`
- `0x18001d970`
- `0x1800254d0`
- `0x180028484`
- `0x1800388a0`
- `0x180038c20`
- `0x180038ff0`
- `0x180039040`
- `0x180047010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180038921`
- `OLEAUT32!__imp_SysAllocString` at `0x18003897d`
- `OLEAUT32!__imp_SysAllocString` at `0x180038af6`
- `OLEAUT32!__imp_SysAllocString` at `0x180038bb2`
- `OLEAUT32!__imp_SysAllocString` at `0x180038921`
- `OLEAUT32!__imp_SysAllocString` at `0x18003897d`
- `OLEAUT32!__imp_SysAllocString` at `0x180038af6`
- `OLEAUT32!__imp_SysAllocString` at `0x180038bb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18003892d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003892d`
- `OLEAUT32!__imp_VariantInit` at `0x18003893c`
- `OLEAUT32!__imp_VariantInit` at `0x18003893c`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800389ee`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800389ee`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180038a0e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180038a0e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800389fe`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800389fe`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180038a3c`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180038a3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
unsigned __int16 *__fastcall CTextTemplate::GetPropertyFromIUnknown(
        CTextTemplate *this,
        unsigned __int16 *a2,
        struct IUnknown *a3)
{
  unsigned __int16 *v5; // rdi
  struct IWbemClassObject *v6; // rbx
  const OLECHAR *v7; // rax
  OLECHAR *v8; // rsi
  int v9; // eax
  const OLECHAR *v10; // rcx
  BSTR v11; // rax
  LONG i; // eax
  const OLECHAR *v13; // rdx
  LONG plUbound; // [rsp+40h] [rbp-69h] BYREF
  LONG rgIndices[2]; // [rsp+48h] [rbp-61h] BYREF
  LONG plLbound; // [rsp+50h] [rbp-59h] BYREF
  int v18; // [rsp+54h] [rbp-55h] BYREF
  struct IWbemClassObject *v19; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int16 *Text; // [rsp+60h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-41h] BYREF
  int (__fastcall ***pv)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp-29h] BYREF
  OLECHAR *psz[5]; // [rsp+88h] [rbp-21h] BYREF
  const OLECHAR *v24; // [rsp+B0h] [rbp+7h] BYREF
  struct IWbemClassObject *v25; // [rsp+B8h] [rbp+Fh]
  int v26; // [rsp+C0h] [rbp+17h] BYREF
  __int128 v27; // [rsp+C8h] [rbp+1Fh]
  int v28; // [rsp+D8h] [rbp+2Fh]
  int v29; // [rsp+DCh] [rbp+33h]
  __int64 v30; // [rsp+120h] [rbp+77h] BYREF
  const OLECHAR *v31; // [rsp+128h] [rbp+7Fh] BYREF

  v5 = 0;
  v19 = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IWbemClassObject **))a3->lpVtbl->QueryInterface)(
         a3,
         &IID_IWbemClassObject,
         &v19) < 0 )
    return v5;
  v6 = v19;
  v25 = v19;
  if ( CTextTemplate::IsEmbeddedObjectProperty(this, a2) )
  {
    v7 = CTextTemplate::HandleEmbeddedObjectProperties(this, a2, v19);
    v8 = (OLECHAR *)v7;
    if ( v7 )
    {
      v5 = SysAllocString(v7);
      SysFreeString(v8);
    }
    goto LABEL_33;
  }
  VariantInit(&pvarg);
  v18 = 0;
  v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, VARIANTARG *, int *, _QWORD))v19->lpVtbl->Get)(
         v19,
         a2,
         0,
         &pvarg,
         &v18,
         0);
  if ( v9 == -2147217406 )
  {
    v10 = L"<unknown>";
LABEL_7:
    v11 = SysAllocString(v10);
    goto LABEL_31;
  }
  if ( v9 < 0 )
  {
    v10 = L"<failed>";
    goto LABEL_7;
  }
  if ( pvarg.vt == 1 )
  {
    v10 = L"<null>";
    goto LABEL_7;
  }
  Text = 0;
  if ( pvarg.vt == 8205 )
  {
    psz[0] = (OLECHAR *)&unk_180070020;
    psz[1] = 0;
    psz[2] = 0;
    psz[3] = (OLECHAR *)50;
    psz[4] = (OLECHAR *)50;
    *(_QWORD *)rgIndices = 0;
    plLbound = 0;
    plUbound = 0;
    SafeArrayGetDim(pvarg.parray);
    SafeArrayGetLBound(pvarg.parray, 1u, &plLbound);
    SafeArrayGetUBound(pvarg.parray, 1u, &plUbound);
    WString2::operator+=(psz, L"{");
    for ( i = plLbound; ; i = rgIndices[0] + 1 )
    {
      rgIndices[0] = i;
      if ( i > plUbound )
        break;
      pv = 0;
      SafeArrayGetElement(pvarg.parray, rgIndices, &pv);
      v31 = 0;
      v30 = 0;
      if ( (**pv)(pv, &IID_IWbemClassObject, &v30) >= 0 )
      {
        (*(void (__fastcall **)(__int64, _QWORD, const OLECHAR **))(*(_QWORD *)v30 + 104LL))(v30, 0, &v31);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      v24 = v31;
      v13 = v31;
      if ( !v31 )
        v13 = L"<error>";
      WString2::operator+=(psz, v13);
      if ( rgIndices[0] < plUbound )
        WString2::operator+=(psz, L", ");
      CSysFreeMe::~CSysFreeMe((CSysFreeMe *)&v24);
    }
    WString2::operator+=(psz, L"}");
    Text = SysAllocString(psz[0]);
    WString2::DeleteString((WString2 *)psz, 1);
  }
  else if ( pvarg.vt == 13 )
  {
    v30 = 0;
    if ( (**(int (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(pvarg.llVal, &IID_IWbemClassObject, &v30) >= 0 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, unsigned __int16 **))(*(_QWORD *)v30 + 104LL))(v30, 0, &Text);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
  }
  else
  {
    v28 = 0;
    v26 = 0;
    v29 = 1;
    v27 = 0;
    CVar::SetVariant((CVar *)&v26, &pvarg, 0);
    Text = CVar::GetText((CVar *)&v26, 0, v18, 0);
    CVar::~CVar((CVar *)&v26);
  }
  v5 = Text;
  if ( !Text )
    v5 = SysAllocString(L"<error>");
  if ( (pvarg.vt & 0x2000) == 0 )
    goto LABEL_32;
  v11 = CTextTemplate::ProcessArray(this, &pvarg, v5);
LABEL_31:
  v5 = v11;
LABEL_32:
  _variant_t::~_variant_t((_variant_t *)&pvarg);
LABEL_33:
  if ( v6 )
    ((void (__fastcall *)(struct IWbemClassObject *))v6->lpVtbl->Release)(v6);
  v25 = 0;
  return v5;
}

```

## disassembly

```asm
0x1800388a0  mov     [rsp-8+arg_0], rbx
0x1800388a5  push    rbp
0x1800388a6  push    rsi
0x1800388a7  push    rdi
0x1800388a8  push    r14
0x1800388aa  push    r15
0x1800388ac  lea     rbp, [rsp-37h]
0x1800388b1  sub     rsp, 0E0h
0x1800388b8  mov     r9, r8
0x1800388bb  mov     rsi, rdx
0x1800388be  mov     r14, rcx
0x1800388c1  xor     r15d, r15d
0x1800388c4  mov     edi, r15d
0x1800388c7  mov     [rbp+57h+var_A8], r15
0x1800388cb  mov     rax, [r8]
0x1800388ce  lea     r8, [rbp+57h+var_A8]
0x1800388d2  lea     rdx, IID_IWbemClassObject
0x1800388d9  mov     rcx, r9
0x1800388dc  mov     rax, [rax]
0x1800388df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388e4  test    eax, eax
0x1800388e6  js      loc_180038BFA
0x1800388ec  mov     rbx, [rbp+57h+var_A8]
0x1800388f0  mov     [rbp+57h+var_48], rbx
0x1800388f4  mov     rdx, rsi; unsigned __int16 *
0x1800388f7  mov     rcx, r14; this
0x1800388fa  call    ?IsEmbeddedObjectProperty@CTextTemplate@@AEAAHPEAG@Z; CTextTemplate::IsEmbeddedObjectProperty(ushort *)
0x1800388ff  test    eax, eax
0x180038901  jz      short loc_180038938
0x180038903  mov     r8, [rbp+57h+var_A8]; struct IWbemClassObject *
0x180038907  mov     rdx, rsi; unsigned __int16 *
0x18003890a  mov     rcx, r14; this
0x18003890d  call    ?HandleEmbeddedObjectProperties@CTextTemplate@@AEAAPEAGPEAGPEAUIWbemClassObject@@@Z; CTextTemplate::HandleEmbeddedObjectProperties(ushort *,IWbemClassObject *)
0x180038912  mov     rsi, rax
0x180038915  test    rax, rax
0x180038918  jz      loc_180038BE2
0x18003891e  mov     rcx, rax; psz
0x180038921  call    cs:__imp_SysAllocString
0x180038927  mov     rdi, rax
0x18003892a  mov     rcx, rsi; bstrString
0x18003892d  call    cs:__imp_SysFreeString
0x180038933  jmp     loc_180038BE2
0x180038938  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003893c  call    cs:__imp_VariantInit
0x180038942  nop
0x180038943  mov     [rbp+57h+var_AC], r15d
0x180038947  mov     rcx, [rbp+57h+var_A8]
0x18003894b  mov     rax, [rcx]
0x18003894e  mov     [rsp+100h+var_D8], r15
0x180038953  lea     rdx, [rbp+57h+var_AC]
0x180038957  mov     [rsp+100h+var_E0], rdx
0x18003895c  lea     r9, [rbp+57h+pvarg]
0x180038960  xor     r8d, r8d
0x180038963  mov     rdx, rsi
0x180038966  mov     rax, [rax+20h]
0x18003896a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003896f  cmp     eax, 80041002h
0x180038974  jnz     short loc_180038988
0x180038976  lea     rcx, psz; "<unknown>"
0x18003897d  call    cs:__imp_SysAllocString
0x180038983  jmp     loc_180038BD5
0x180038988  test    eax, eax
0x18003898a  jns     short loc_180038995
0x18003898c  lea     rcx, aFailed; "<failed>"
0x180038993  jmp     short loc_18003897D
0x180038995  movzx   eax, word ptr [rbp+57h+pvarg]
0x180038999  mov     edi, 1
0x18003899e  cmp     ax, di
0x1800389a1  jnz     short loc_1800389AC
0x1800389a3  lea     rcx, aNull; "<null>"
0x1800389aa  jmp     short loc_18003897D
0x1800389ac  mov     [rbp+57h+var_A0], r15
0x1800389b0  mov     ecx, 200Dh
0x1800389b5  cmp     ax, cx
0x1800389b8  jnz     loc_180038B11
0x1800389be  lea     rax, unk_180070020
0x1800389c5  mov     [rbp+57h+psz], rax
0x1800389c9  mov     [rbp+57h+var_70], r15
0x1800389cd  mov     [rbp+57h+var_68], r15
0x1800389d1  mov     eax, 32h ; '2'
0x1800389d6  mov     [rbp+57h+var_60], rax
0x1800389da  mov     [rbp+57h+var_58], rax
0x1800389de  mov     qword ptr [rbp+57h+rgIndices], r15
0x1800389e2  mov     [rbp+57h+plLbound], r15d
0x1800389e6  mov     [rbp+57h+plUbound], r15d
0x1800389ea  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x1800389ee  call    cs:__imp_SafeArrayGetDim
0x1800389f4  lea     r8, [rbp+57h+plLbound]; plLbound
0x1800389f8  mov     edx, edi; nDim
0x1800389fa  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x1800389fe  call    cs:__imp_SafeArrayGetLBound
0x180038a04  lea     r8, [rbp+57h+plUbound]; plUbound
0x180038a08  mov     edx, edi; nDim
0x180038a0a  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x180038a0e  call    cs:__imp_SafeArrayGetUBound
0x180038a14  lea     rdx, asc_18004B7F0; "{"
0x180038a1b  lea     rcx, [rbp+57h+psz]
0x180038a1f  call    ??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180038a24  mov     eax, [rbp+57h+plLbound]
0x180038a27  jmp     loc_180038AD6
0x180038a2c  mov     [rbp+57h+pv], r15
0x180038a30  lea     r8, [rbp+57h+pv]; pv
0x180038a34  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180038a38  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x180038a3c  call    cs:__imp_SafeArrayGetElement
0x180038a42  mov     [rbp+57h+arg_18], r15
0x180038a46  mov     [rbp+57h+arg_10], r15
0x180038a4a  mov     rcx, [rbp+57h+pv]
0x180038a4e  mov     rax, [rcx]
0x180038a51  lea     r8, [rbp+57h+arg_10]
0x180038a55  lea     rdx, IID_IWbemClassObject
0x180038a5c  mov     rax, [rax]
0x180038a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a64  test    eax, eax
0x180038a66  js      short loc_180038A8E
0x180038a68  mov     rcx, [rbp+57h+arg_10]
0x180038a6c  mov     rax, [rcx]
0x180038a6f  lea     r8, [rbp+57h+arg_18]
0x180038a73  xor     edx, edx
0x180038a75  mov     rax, [rax+68h]
0x180038a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a7e  mov     rcx, [rbp+57h+arg_10]
0x180038a82  mov     rax, [rcx]
0x180038a85  mov     rax, [rax+10h]
0x180038a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a8e  mov     rax, [rbp+57h+arg_18]
0x180038a92  mov     [rbp+57h+var_50], rax
0x180038a96  mov     rdx, [rbp+57h+arg_18]
0x180038a9a  lea     rcx, [rbp+57h+psz]
0x180038a9e  test    rdx, rdx
0x180038aa1  jnz     short loc_180038AAA
0x180038aa3  lea     rdx, aError; "<error>"
0x180038aaa  call    ??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180038aaf  mov     eax, [rbp+57h+plUbound]
0x180038ab2  cmp     [rbp+57h+rgIndices], eax
0x180038ab5  jge     short loc_180038AC8
0x180038ab7  lea     rdx, asc_18004B1DC; ", "
0x180038abe  lea     rcx, [rbp+57h+psz]
0x180038ac2  call    ??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180038ac7  nop
0x180038ac8  lea     rcx, [rbp+57h+var_50]; this
0x180038acc  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x180038ad1  mov     eax, [rbp+57h+rgIndices]
0x180038ad4  add     eax, edi
0x180038ad6  cmp     eax, [rbp+57h+plUbound]
0x180038ad9  mov     [rbp+57h+rgIndices], eax
0x180038adc  jle     loc_180038A2C
0x180038ae2  lea     rdx, asc_18004B7F4; "}"
0x180038ae9  lea     rcx, [rbp+57h+psz]
0x180038aed  call    ??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180038af2  mov     rcx, [rbp+57h+psz]; psz
0x180038af6  call    cs:__imp_SysAllocString
0x180038afc  mov     [rbp+57h+var_A0], rax
0x180038b00  mov     dl, dil; bool
0x180038b03  lea     rcx, [rbp+57h+psz]; this
0x180038b07  call    ?DeleteString@WString2@@AEAAX_N@Z; WString2::DeleteString(bool)
0x180038b0c  jmp     loc_180038BA2
0x180038b11  cmp     ax, 0Dh
0x180038b15  jz      short loc_180038B5A
0x180038b17  mov     [rbp+57h+var_28], r15d
0x180038b1b  mov     [rbp+57h+var_40], r15d
0x180038b1f  mov     [rbp+57h+var_24], edi
0x180038b22  xorps   xmm0, xmm0
0x180038b25  movups  [rbp+57h+var_38], xmm0
0x180038b29  xor     r8d, r8d; int
0x180038b2c  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x180038b30  lea     rcx, [rbp+57h+var_40]; this
0x180038b34  call    ?SetVariant@CVar@@QEAAHPEAUtagVARIANT@@H@Z; CVar::SetVariant(tagVARIANT *,int)
0x180038b39  xor     r9d, r9d; unsigned __int16 *
0x180038b3c  mov     r8d, [rbp+57h+var_AC]; int
0x180038b40  xor     edx, edx; int
0x180038b42  lea     rcx, [rbp+57h+var_40]; this
0x180038b46  call    ?GetText@CVar@@QEAAPEAGJJPEBG@Z; CVar::GetText(long,long,ushort const *)
0x180038b4b  mov     [rbp+57h+var_A0], rax
0x180038b4f  lea     rcx, [rbp+57h+var_40]; this
0x180038b53  call    ??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180038b58  jmp     short loc_180038BA2
0x180038b5a  mov     [rbp+57h+arg_10], r15
0x180038b5e  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x180038b62  mov     rax, [rcx]
0x180038b65  lea     r8, [rbp+57h+arg_10]
0x180038b69  lea     rdx, IID_IWbemClassObject
0x180038b70  mov     rax, [rax]
0x180038b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b78  test    eax, eax
0x180038b7a  js      short loc_180038BA2
0x180038b7c  mov     rcx, [rbp+57h+arg_10]
0x180038b80  mov     rax, [rcx]
0x180038b83  lea     r8, [rbp+57h+var_A0]
0x180038b87  xor     edx, edx
0x180038b89  mov     rax, [rax+68h]
0x180038b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b92  mov     rcx, [rbp+57h+arg_10]
0x180038b96  mov     rax, [rcx]
0x180038b99  mov     rax, [rax+10h]
0x180038b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ba2  mov     rdi, [rbp+57h+var_A0]
0x180038ba6  test    rdi, rdi
0x180038ba9  jnz     short loc_180038BBB
0x180038bab  lea     rcx, aError; "<error>"
0x180038bb2  call    cs:__imp_SysAllocString
0x180038bb8  mov     rdi, rax
0x180038bbb  mov     eax, 2000h
0x180038bc0  test    word ptr [rbp+57h+pvarg], ax
0x180038bc4  jz      short loc_180038BD8
0x180038bc6  mov     r8, rdi; unsigned __int16 *
0x180038bc9  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x180038bcd  mov     rcx, r14; this
0x180038bd0  call    ?ProcessArray@CTextTemplate@@AEAAPEAGAEBUtagVARIANT@@PEAG@Z; CTextTemplate::ProcessArray(tagVARIANT const &,ushort *)
0x180038bd5  mov     rdi, rax
0x180038bd8  lea     rcx, [rbp+57h+pvarg]; this
0x180038bdc  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180038be1  nop
0x180038be2  test    rbx, rbx
0x180038be5  jz      short loc_180038BF6
0x180038be7  mov     rax, [rbx]
0x180038bea  mov     rcx, rbx
0x180038bed  mov     rax, [rax+10h]
0x180038bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bf6  mov     [rbp+57h+var_48], r15
0x180038bfa  mov     rax, rdi
0x180038bfd  mov     rbx, [rsp+100h+arg_0]
0x180038c05  add     rsp, 0E0h
0x180038c0c  pop     r15
0x180038c0e  pop     r14
0x180038c10  pop     rdi
0x180038c11  pop     rsi
0x180038c12  pop     rbp
0x180038c13  retn
```
