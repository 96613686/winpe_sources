# CImpDyn::CreateInst(IWbemServices *,ushort *,ushort *,IWbemClassObject * *,long,ushort *,CIndexCache *,IWbemContext *)

- ea: `0x180003700`
- end: `0x1800038d7`
- name: `?CreateInst@CImpDyn@@QEAAJPEAUIWbemServices@@PEAG1PEAPEAUIWbemClassObject@@J1PEAVCIndexCache@@PEAUIWbemContext@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(CImpDyn *this, struct IWbemServices *, unsigned __int16 *, unsigned __int16 *, struct IWbemClassObject **, unsigned int, unsigned __int16 *psz, struct CIndexCache *, struct IWbemContext *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000e110`

## callees

- `0x180003700`
- `0x1800038e0`
- `0x18000b178`
- `0x180017010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800037ae`
- `OLEAUT32!__imp_SysAllocString` at `0x1800037d3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800037ae`
- `OLEAUT32!__imp_SysAllocString` at `0x1800037d3`
- `OLEAUT32!__imp_SysFreeString` at `0x180003877`
- `OLEAUT32!__imp_SysFreeString` at `0x180003877`
- `OLEAUT32!__imp_VariantClear` at `0x1800037e6`
- `OLEAUT32!__imp_VariantClear` at `0x1800037e6`

## pseudocode

```c
__int64 __fastcall CImpDyn::CreateInst(
        CImpDyn *this,
        struct IWbemServices *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct IWbemClassObject **a5,
        unsigned int a6,
        unsigned __int16 *psz,
        struct CIndexCache *a8,
        struct IWbemContext *a9)
{
  HRESULT (__stdcall *GetObjectA)(IWbemServices *, const BSTR, int, IWbemContext *, IWbemClassObject **, IWbemCallResult **); // rax
  __int64 result; // rax
  struct IWbemClassObject **v13; // rsi
  int v14; // ebx
  BSTR KeyName; // rax
  OLECHAR *v16; // rbx
  struct IWbemClassObject *v17; // rcx
  VARIANTARG pvarg; // [rsp+40h] [rbp-38h] BYREF
  struct IWbemClassObject *v19; // [rsp+88h] [rbp+10h] BYREF

  GetObjectA = a2->lpVtbl->GetObjectA;
  v19 = 0;
  result = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *, _QWORD, struct IWbemContext *, struct IWbemClassObject **, _QWORD))GetObjectA)(
             a2,
             a3,
             0,
             a9,
             &v19,
             0);
  if ( (int)result >= 0 )
  {
    v13 = a5;
    v14 = ((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD, struct IWbemClassObject **))v19->lpVtbl->SpawnInstance)(
            v19,
            0,
            a5);
    if ( v14 < 0 )
    {
      v17 = v19;
    }
    else
    {
      *(_QWORD *)&pvarg.vt = 8;
      *(_OWORD *)&pvarg.decVal.Lo32 = (unsigned __int64)SysAllocString(a4);
      if ( !pvarg.llVal )
      {
        ((void (__fastcall *)(struct IWbemClassObject *))(*v13)->lpVtbl->Release)(*v13);
        ((void (__fastcall *)(struct IWbemClassObject *))v19->lpVtbl->Release)(v19);
        return 2147749894LL;
      }
      if ( psz )
        KeyName = SysAllocString(psz);
      else
        KeyName = CImpDyn::GetKeyName(0, *v13);
      v16 = KeyName;
      if ( KeyName )
      {
        ((void (__fastcall *)(struct IWbemClassObject *, BSTR, _QWORD, VARIANTARG *, _DWORD))(*v13)->lpVtbl->Put)(
          *v13,
          KeyName,
          0,
          &pvarg,
          0);
        SysFreeString(v16);
      }
      VariantClear(&pvarg);
      v14 = CImpDyn::EnumPropDoFunc(this, a6, *v13, 0, a4, a8, v19);
      ((void (__fastcall *)(struct IWbemClassObject *))v19->lpVtbl->Release)(v19);
      if ( v14 >= 0 )
        return (unsigned int)v14;
      v17 = *v13;
    }
    ((void (__fastcall *)(struct IWbemClassObject *))v17->lpVtbl->Release)(v17);
    return (unsigned int)v14;
  }
  return result;
}

```

## disassembly

```asm
0x180003700  push    rbp
0x180003702  push    rdi
0x180003703  push    r14
0x180003705  sub     rsp, 60h
0x180003709  mov     rax, [rdx]
0x18000370c  mov     rbp, rcx
0x18000370f  mov     r10, r8
0x180003712  lea     rcx, [rsp+78h+arg_8]
0x18000371a  mov     r11, rdx
0x18000371d  xor     r14d, r14d
0x180003720  mov     rdi, r9
0x180003723  mov     [rsp+78h+var_50], r14
0x180003728  mov     rax, [rax+30h]
0x18000372c  xor     r8d, r8d
0x18000372f  mov     r9, [rsp+78h+arg_40]
0x180003737  mov     rdx, r10
0x18000373a  mov     [rsp+78h+var_58], rcx
0x18000373f  mov     rcx, r11
0x180003742  mov     [rsp+78h+arg_8], r14
0x18000374a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000374f  test    eax, eax
0x180003751  js      loc_18000384C
0x180003757  mov     rcx, [rsp+78h+arg_8]
0x18000375f  xor     edx, edx
0x180003761  mov     [rsp+78h+arg_0], rbx
0x180003769  mov     [rsp+78h+arg_10], rsi
0x180003771  mov     rsi, [rsp+78h+arg_20]
0x180003779  mov     rax, [rcx]
0x18000377c  mov     r8, rsi
0x18000377f  mov     rax, [rax+78h]
0x180003783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003788  mov     ebx, eax
0x18000378a  test    eax, eax
0x18000378c  js      loc_180003882
0x180003792  xor     eax, eax
0x180003794  xorps   xmm0, xmm0
0x180003797  mov     qword ptr [rsp+78h+pvarg+10h], rax
0x18000379c  mov     rcx, rdi; psz
0x18000379f  mov     eax, 8
0x1800037a4  movups  xmmword ptr [rsp+78h+pvarg], xmm0
0x1800037a9  mov     word ptr [rsp+78h+pvarg], ax
0x1800037ae  call    cs:__imp_SysAllocString
0x1800037b4  mov     qword ptr [rsp+78h+pvarg+8], rax
0x1800037b9  test    rax, rax
0x1800037bc  jz      loc_18000389D
0x1800037c2  mov     rcx, [rsp+78h+psz]; this
0x1800037ca  test    rcx, rcx
0x1800037cd  jz      loc_1800038CA
0x1800037d3  call    cs:__imp_SysAllocString
0x1800037d9  mov     rbx, rax
0x1800037dc  test    rax, rax
0x1800037df  jnz     short loc_180003855
0x1800037e1  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1800037e6  call    cs:__imp_VariantClear
0x1800037ec  mov     rax, [rsp+78h+arg_8]
0x1800037f4  xor     r9d, r9d
0x1800037f7  mov     r8, [rsi]
0x1800037fa  mov     rcx, rbp
0x1800037fd  mov     edx, [rsp+78h+arg_28]
0x180003804  mov     [rsp+78h+var_48], rax
0x180003809  mov     rax, [rsp+78h+arg_38]
0x180003811  mov     [rsp+78h+var_50], rax
0x180003816  mov     [rsp+78h+var_58], rdi
0x18000381b  call    ?EnumPropDoFunc@CImpDyn@@QEAAJJPEAUIWbemClassObject@@W4FUNCTYPE@@PEAGPEAVCIndexCache@@0@Z; CImpDyn::EnumPropDoFunc(long,IWbemClassObject *,FUNCTYPE,ushort *,CIndexCache *,IWbemClassObject *)
0x180003820  mov     rcx, [rsp+78h+arg_8]
0x180003828  mov     ebx, eax
0x18000382a  mov     rdx, [rcx]
0x18000382d  mov     rax, [rdx+10h]
0x180003831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003836  test    ebx, ebx
0x180003838  js      short loc_180003898
0x18000383a  mov     eax, ebx
0x18000383c  mov     rbx, [rsp+78h+arg_0]
0x180003844  mov     rsi, [rsp+78h+arg_10]
0x18000384c  add     rsp, 60h
0x180003850  pop     r14
0x180003852  pop     rdi
0x180003853  pop     rbp
0x180003854  retn
0x180003855  mov     rcx, [rsi]
0x180003858  lea     r9, [rsp+78h+pvarg]
0x18000385d  xor     r8d, r8d
0x180003860  mov     dword ptr [rsp+78h+var_58], r14d
0x180003865  mov     rdx, rbx
0x180003868  mov     rax, [rcx]
0x18000386b  mov     rax, [rax+28h]
0x18000386f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003874  mov     rcx, rbx; bstrString
0x180003877  call    cs:__imp_SysFreeString
0x18000387d  jmp     loc_1800037E1
0x180003882  mov     rcx, [rsp+78h+arg_8]
0x18000388a  mov     rdx, [rcx]
0x18000388d  mov     rax, [rdx+10h]
0x180003891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003896  jmp     short loc_18000383A
0x180003898  mov     rcx, [rsi]
0x18000389b  jmp     short loc_18000388A
0x18000389d  mov     rcx, [rsi]
0x1800038a0  mov     rax, [rcx]
0x1800038a3  mov     rax, [rax+10h]
0x1800038a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038ac  mov     rcx, [rsp+78h+arg_8]
0x1800038b4  mov     rax, [rcx]
0x1800038b7  mov     rax, [rax+10h]
0x1800038bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038c0  mov     eax, 80041006h
0x1800038c5  jmp     loc_18000383C
0x1800038ca  mov     rdx, [rsi]; struct IWbemClassObject *
0x1800038cd  call    ?GetKeyName@CImpDyn@@QEAAPEAGPEAUIWbemClassObject@@@Z; CImpDyn::GetKeyName(IWbemClassObject *)
0x1800038d2  jmp     loc_1800037D9
```
