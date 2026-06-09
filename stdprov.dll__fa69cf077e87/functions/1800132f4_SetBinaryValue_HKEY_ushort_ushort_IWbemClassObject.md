# SetBinaryValue(HKEY__ *,ushort *,ushort *,IWbemClassObject *)

- ea: `0x1800132f4`
- end: `0x180013456`
- name: `?SetBinaryValue@@YAJPEAUHKEY__@@PEAG1PEAUIWbemClassObject@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, unsigned __int16 *, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800043c0`

## callees

- `0x1800132f4`
- `0x180017010`

## import_xrefs

- `wbemcomn!?SetBinary@Registry@@QEAAHPEBGPEAEK@Z` at `0x18001340d`
- `wbemcomn!?SetBinary@Registry@@QEAAHPEBGPEAEK@Z` at `0x18001340d`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180013379`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180013424`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18001343d`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180013379`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180013424`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18001343d`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x18001331b`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x18001331b`
- `OLEAUT32!__imp_VariantInit` at `0x18001333a`
- `OLEAUT32!__imp_VariantInit` at `0x18001333a`
- `OLEAUT32!__imp_VariantClear` at `0x180013419`
- `OLEAUT32!__imp_VariantClear` at `0x180013432`
- `OLEAUT32!__imp_VariantClear` at `0x180013419`
- `OLEAUT32!__imp_VariantClear` at `0x180013432`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800133d0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800133d0`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800133bc`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800133bc`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800133eb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800133eb`

## pseudocode

```c
__int64 __fastcall SetBinaryValue(HKEY a1, unsigned __int16 *a2, unsigned __int16 *a3, struct IWbemClassObject *a4)
{
  unsigned int v6; // ebx
  SAFEARRAY *parray; // rsi
  HRESULT LBound; // ebx
  unsigned int v10; // edi
  LONG plUbound; // [rsp+40h] [rbp-40h] BYREF
  LONG plLbound; // [rsp+44h] [rbp-3Ch] BYREF
  void *ppvData; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v15[20]; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v16; // [rsp+7Ch] [rbp-4h]

  Registry::Registry((Registry *)v15, a1, 2u, a2);
  v6 = v16;
  if ( v16
    || (memset(&pvarg, 0, sizeof(pvarg)),
        VariantInit(&pvarg),
        (v6 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a4->lpVtbl->Get)(
                a4,
                L"uValue",
                0,
                &pvarg,
                0,
                0)) != 0) )
  {
    Registry::~Registry((Registry *)v15);
    return v6;
  }
  else if ( pvarg.vt == 8209 && (parray = pvarg.parray) != 0 )
  {
    plLbound = 0;
    plUbound = 0;
    LBound = SafeArrayGetLBound(pvarg.parray, 1u, &plLbound);
    v10 = LBound | SafeArrayGetUBound(parray, 1u, &plUbound);
    if ( !v10 )
    {
      ppvData = 0;
      v10 = SafeArrayAccessData(parray, &ppvData);
      if ( !v10 )
        v10 = Registry::SetBinary((Registry *)v15, a3, (unsigned __int8 *)ppvData, plUbound - plLbound + 1);
    }
    VariantClear(&pvarg);
    Registry::~Registry((Registry *)v15);
    return v10;
  }
  else
  {
    VariantClear(&pvarg);
    Registry::~Registry((Registry *)v15);
    return 2147749896LL;
  }
}

```

## disassembly

```asm
0x1800132f4  push    rbp
0x1800132f6  push    rbx
0x1800132f7  push    rsi
0x1800132f8  push    rdi
0x1800132f9  push    r14
0x1800132fb  mov     rbp, rsp
0x1800132fe  sub     rsp, 80h
0x180013305  mov     rdi, r9
0x180013308  mov     r14, r8
0x18001330b  mov     r9, rdx
0x18001330e  mov     r8d, 2
0x180013314  mov     rdx, rcx
0x180013317  lea     rcx, [rbp+var_18]
0x18001331b  call    cs:__imp_??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z; Registry::Registry(HKEY__ *,ulong,ushort const *)
0x180013321  nop
0x180013322  mov     ebx, [rbp+var_4]
0x180013325  test    ebx, ebx
0x180013327  jnz     short loc_180013375
0x180013329  xorps   xmm0, xmm0
0x18001332c  xor     eax, eax
0x18001332e  movups  xmmword ptr [rbp+pvarg], xmm0
0x180013332  mov     qword ptr [rbp+pvarg+10h], rax
0x180013336  lea     rcx, [rbp+pvarg]; pvarg
0x18001333a  call    cs:__imp_VariantInit
0x180013340  mov     rax, [rdi]
0x180013343  mov     [rsp+80h+var_58], 0
0x18001334c  mov     [rsp+80h+var_60], 0
0x180013355  lea     r9, [rbp+pvarg]
0x180013359  xor     r8d, r8d
0x18001335c  lea     rdx, aUvalue; "uValue"
0x180013363  mov     rcx, rdi
0x180013366  mov     rax, [rax+20h]
0x18001336a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001336f  mov     ebx, eax
0x180013371  test    eax, eax
0x180013373  jz      short loc_180013386
0x180013375  lea     rcx, [rbp+var_18]
0x180013379  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x18001337f  mov     eax, ebx
0x180013381  jmp     loc_180013448
0x180013386  mov     eax, 2011h
0x18001338b  cmp     word ptr [rbp+pvarg], ax
0x18001338f  jnz     loc_18001342E
0x180013395  mov     rsi, qword ptr [rbp+pvarg+8]
0x180013399  test    rsi, rsi
0x18001339c  jz      loc_18001342E
0x1800133a2  mov     [rbp+plLbound], 0
0x1800133a9  mov     [rbp+plUbound], 0
0x1800133b0  lea     r8, [rbp+plLbound]; plLbound
0x1800133b4  mov     edx, 1; nDim
0x1800133b9  mov     rcx, rsi; psa
0x1800133bc  call    cs:__imp_SafeArrayGetLBound
0x1800133c2  mov     ebx, eax
0x1800133c4  lea     r8, [rbp+plUbound]; plUbound
0x1800133c8  mov     edx, 1; nDim
0x1800133cd  mov     rcx, rsi; psa
0x1800133d0  call    cs:__imp_SafeArrayGetUBound
0x1800133d6  mov     edi, eax
0x1800133d8  or      edi, ebx
0x1800133da  jnz     short loc_180013415
0x1800133dc  mov     [rbp+ppvData], 0
0x1800133e4  lea     rdx, [rbp+ppvData]; ppvData
0x1800133e8  mov     rcx, rsi; psa
0x1800133eb  call    cs:__imp_SafeArrayAccessData
0x1800133f1  mov     edi, eax
0x1800133f3  test    eax, eax
0x1800133f5  jnz     short loc_180013415
0x1800133f7  mov     r9d, [rbp+plUbound]
0x1800133fb  sub     r9d, [rbp+plLbound]
0x1800133ff  inc     r9d
0x180013402  mov     r8, [rbp+ppvData]
0x180013406  mov     rdx, r14
0x180013409  lea     rcx, [rbp+var_18]
0x18001340d  call    cs:__imp_?SetBinary@Registry@@QEAAHPEBGPEAEK@Z; Registry::SetBinary(ushort const *,uchar *,ulong)
0x180013413  mov     edi, eax
0x180013415  lea     rcx, [rbp+pvarg]; pvarg
0x180013419  call    cs:__imp_VariantClear
0x18001341f  nop
0x180013420  lea     rcx, [rbp+var_18]
0x180013424  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x18001342a  mov     eax, edi
0x18001342c  jmp     short loc_180013448
0x18001342e  lea     rcx, [rbp+pvarg]; pvarg
0x180013432  call    cs:__imp_VariantClear
0x180013438  nop
0x180013439  lea     rcx, [rbp+var_18]
0x18001343d  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180013443  mov     eax, 80041008h
0x180013448  add     rsp, 80h
0x18001344f  pop     r14
0x180013451  pop     rdi
0x180013452  pop     rsi
0x180013453  pop     rbx
0x180013454  pop     rbp
0x180013455  retn
```
