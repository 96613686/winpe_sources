# GetBinaryValue(HKEY__ *,ushort *,ushort *,IWbemClassObject *)

- ea: `0x180012fe0`
- end: `0x180013131`
- name: `?GetBinaryValue@@YAJPEAUHKEY__@@PEAG1PEAUIWbemClassObject@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, unsigned __int16 *, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800043c0`

## callees

- `0x18000a650`
- `0x180012fe0`
- `0x180015646`
- `0x180017010`

## import_xrefs

- `wbemcomn!?GetBinary@Registry@@QEAAHPEBGPEAPEAEPEAK@Z` at `0x180013033`
- `wbemcomn!?GetBinary@Registry@@QEAAHPEBGPEAPEAEPEAK@Z` at `0x180013033`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18001311d`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18001311d`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180013007`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180013007`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800130f6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800130f6`
- `OLEAUT32!__imp_VariantClear` at `0x1800130e5`
- `OLEAUT32!__imp_VariantClear` at `0x1800130e5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180013061`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180013061`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001307e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001307e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001309e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001309e`

## pseudocode

```c
__int64 __fastcall GetBinaryValue(HKEY a1, unsigned __int16 *a2, unsigned __int16 *a3, struct IWbemClassObject *a4)
{
  unsigned int Binary; // ebx
  SAFEARRAY *v7; // rax
  SAFEARRAY *v8; // rdi
  size_t Size; // [rsp+30h] [rbp-19h] BYREF
  void *Src; // [rsp+38h] [rbp-11h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp-9h] BYREF
  void *ppvData; // [rsp+48h] [rbp-1h] BYREF
  _BYTE v14[20]; // [rsp+50h] [rbp+7h] BYREF
  unsigned int v15; // [rsp+64h] [rbp+1Bh]
  VARIANTARG pvarg; // [rsp+68h] [rbp+1Fh] BYREF

  Registry::Registry((Registry *)v14, a1, 1u, a2);
  Binary = v15;
  if ( !v15 )
  {
    LODWORD(Size) = 0;
    Src = 0;
    Binary = Registry::GetBinary((Registry *)v14, a3, (unsigned __int8 **)&Src, (unsigned int *)&Size);
    if ( Binary || !Src )
    {
      if ( (unsigned int)IsTypeMismatch((struct Registry *)v14, a3, 3u) )
        Binary = -2147217403;
    }
    else
    {
      rgsabound.lLbound = 0;
      rgsabound.cElements = Size;
      v7 = SafeArrayCreate(0x11u, 1u, &rgsabound);
      v8 = v7;
      if ( v7 )
      {
        ppvData = 0;
        Binary = SafeArrayAccessData(v7, &ppvData);
        if ( !Binary )
        {
          memcpy_0(ppvData, Src, (unsigned int)Size);
          SafeArrayUnaccessData(v8);
          *(_QWORD *)&pvarg.vt = 8209;
          *(_OWORD *)&pvarg.decVal.Lo32 = (unsigned __int64)v8;
          Binary = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))a4->lpVtbl->Put)(
                     a4,
                     L"uValue",
                     0,
                     &pvarg,
                     0);
          VariantClear(&pvarg);
        }
      }
      else
      {
        Binary = -2147217402;
      }
      CWin32DefaultArena::WbemMemFree(Src);
    }
  }
  Registry::~Registry((Registry *)v14);
  return Binary;
}

```

## disassembly

```asm
0x180012fe0  push    rbp
0x180012fe2  push    rbx
0x180012fe3  push    rsi
0x180012fe4  push    rdi
0x180012fe5  lea     rbp, [rsp-3Fh]
0x180012fea  sub     rsp, 88h
0x180012ff1  mov     rsi, r9
0x180012ff4  mov     rdi, r8
0x180012ff7  mov     r9, rdx
0x180012ffa  mov     r8d, 1
0x180013000  mov     rdx, rcx
0x180013003  lea     rcx, [rbp+57h+var_50]
0x180013007  call    cs:__imp_??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z; Registry::Registry(HKEY__ *,ulong,ushort const *)
0x18001300d  nop
0x18001300e  mov     ebx, [rbp+57h+var_3C]
0x180013011  test    ebx, ebx
0x180013013  jnz     loc_180013119
0x180013019  mov     dword ptr [rbp+57h+Size], ebx
0x18001301c  mov     [rbp+57h+Src], 0
0x180013024  lea     r9, [rbp+57h+Size]
0x180013028  lea     r8, [rbp+57h+Src]
0x18001302c  mov     rdx, rdi
0x18001302f  lea     rcx, [rbp+57h+var_50]
0x180013033  call    cs:__imp_?GetBinary@Registry@@QEAAHPEBGPEAPEAEPEAK@Z; Registry::GetBinary(ushort const *,uchar * *,ulong *)
0x180013039  mov     ebx, eax
0x18001303b  test    eax, eax
0x18001303d  jnz     loc_1800130FE
0x180013043  cmp     [rbp+57h+Src], 0
0x180013048  jz      loc_1800130FE
0x18001304e  mov     [rbp+57h+rgsabound.lLbound], eax
0x180013051  mov     eax, dword ptr [rbp+57h+Size]
0x180013054  mov     [rbp+57h+rgsabound.cElements], eax
0x180013057  lea     ecx, [rbx+11h]; vt
0x18001305a  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x18001305e  lea     edx, [rbx+1]; cDims
0x180013061  call    cs:__imp_SafeArrayCreate
0x180013067  mov     rdi, rax
0x18001306a  test    rax, rax
0x18001306d  jz      short loc_1800130ED
0x18001306f  mov     [rbp+57h+ppvData], 0
0x180013077  lea     rdx, [rbp+57h+ppvData]; ppvData
0x18001307b  mov     rcx, rax; psa
0x18001307e  call    cs:__imp_SafeArrayAccessData
0x180013084  mov     ebx, eax
0x180013086  test    eax, eax
0x180013088  jnz     short loc_1800130F2
0x18001308a  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x18001308e  mov     rdx, [rbp+57h+Src]; Src
0x180013092  mov     rcx, [rbp+57h+ppvData]; void *
0x180013096  call    memcpy_0
0x18001309b  mov     rcx, rdi; psa
0x18001309e  call    cs:__imp_SafeArrayUnaccessData
0x1800130a4  xorps   xmm0, xmm0
0x1800130a7  xor     eax, eax
0x1800130a9  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800130ad  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800130b1  mov     eax, 2011h
0x1800130b6  mov     word ptr [rbp+57h+pvarg], ax
0x1800130ba  mov     qword ptr [rbp+57h+pvarg+8], rdi
0x1800130be  mov     rax, [rsi]
0x1800130c1  mov     [rsp+0A0h+var_80], ebx
0x1800130c5  lea     r9, [rbp+57h+pvarg]
0x1800130c9  xor     r8d, r8d
0x1800130cc  lea     rdx, aUvalue; "uValue"
0x1800130d3  mov     rcx, rsi
0x1800130d6  mov     rax, [rax+28h]
0x1800130da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130df  mov     ebx, eax
0x1800130e1  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800130e5  call    cs:__imp_VariantClear
0x1800130eb  jmp     short loc_1800130F2
0x1800130ed  mov     ebx, 80041006h
0x1800130f2  mov     rcx, [rbp+57h+Src]
0x1800130f6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800130fc  jmp     short loc_180013119
0x1800130fe  mov     r8d, 3; unsigned int
0x180013104  mov     rdx, rdi; unsigned __int16 *
0x180013107  lea     rcx, [rbp+57h+var_50]; struct Registry *
0x18001310b  call    ?IsTypeMismatch@@YAHAEAVRegistry@@PEAGK@Z; IsTypeMismatch(Registry &,ushort *,ulong)
0x180013110  test    eax, eax
0x180013112  jz      short loc_180013119
0x180013114  mov     ebx, 80041005h
0x180013119  lea     rcx, [rbp+57h+var_50]
0x18001311d  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180013123  mov     eax, ebx
0x180013125  add     rsp, 88h
0x18001312c  pop     rdi
0x18001312d  pop     rsi
0x18001312e  pop     rbx
0x18001312f  pop     rbp
0x180013130  retn
```
